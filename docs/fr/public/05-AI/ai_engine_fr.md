# Moteur IA — Mécanique interne

Le moteur IA/ML de Nyroxis est conçu pour fonctionner entièrement en local, effectuant une analyse intelligente sur des événements de sécurité chiffrés sans dépendre de services cloud.

---

## Principes de conception fondamentaux

### 1. Confidentialité en premier
- Aucun traitement cloud
- Aucune API externe
- Aucun partage de données

Toute l'intelligence s'exécute sur l'appareil propre de l'utilisateur.

### 2. Implémentation légère
Entièrement développé en Rust sans bibliothèques ML externes :
- ~Faible utilisation CPU
- Empreinte mémoire minimale
- Exécution en temps réel

### 3. Compréhension comportementale
Au lieu d'analyser les événements individuellement, le moteur comprend les *modèles* qui se produisent dans le temps et à travers plusieurs dimensions d'événements.

### 4. Fonctionnement entièrement hors ligne
Toute l'analyse, la notation et l'extraction de caractéristiques se déroulent localement — aucune connexion internet requise à aucun stade.

---

## Isolation Forest — Comment ça fonctionne

L'algorithme Isolation Forest isole les anomalies en construisant des arbres de décision aléatoires et en mesurant à quelle vitesse chaque point de données est séparé des autres.

**Le principe :**
- Les événements normaux nécessitent de nombreuses divisions pour être isolés (ils se fondent avec les autres)
- Les événements anormaux nécessitent moins de divisions (ils se distinguent)
- Chemin d'isolation plus court = score d'anomalie plus élevé

**Implémentation Nyroxis :**
- 100 arbres d'isolation construits par cycle d'analyse
- 256 échantillons aléatoires utilisés par arbre
- Les 8 caractéristiques comportementales normalisées avant l'analyse
- Seuil du score d'anomalie : 0,6 (au-dessus = détection déclenchée)
- Caractéristiques contributives identifiées via la déviation Z-score (seuil : 2,0 écarts-types)

---

## Pipeline d'analyse statistique

### Classification Z-Score
Chaque valeur surveillée est évaluée par rapport à sa ligne de base historique :

```
z = (valeur - moyenne) / écart_type
```

| |z| | Gravité | Confiance |
|------|----------|------------|
| > 3,0 | Critique | 99,7 % |
| > 2,0 | Élevé | 95 % |
| > 1,5 | Moyen | 86 % |
| > 1,0 | Faible | 68 % |

### Détection des valeurs aberrantes IQR
```
borne_inférieure = Q1 - 1,5 × IQR
borne_supérieure = Q3 + 1,5 × IQR
```
Les valeurs en dehors de cette plage sont signalées comme des valeurs aberrantes statistiques.

### Moyennes mobiles
- **Moyenne mobile simple** — tendance de la ligne de base sur des fenêtres temporelles configurables
- **Moyenne mobile exponentielle** — pondère davantage l'activité récente pour une réponse plus rapide aux modèles émergents

### Détection des pics
```
valeur_actuelle > moyenne + (multiplicateur_seuil × écart_type)
```

---

## Ce que le moteur produit

Pour chaque cycle d'analyse :
- `is_anomaly` — indicateur booléen
- `anomaly_score` — 0,0 à 1,0 (plus élevé = plus anormal)
- `confidence` — 0,0 à 0,95
- `contributing_features` — liste de caractéristiques avec Z-scores qui ont conduit à la détection

Ces sorties sont affichées dans la section Analyse IA / ML du tableau de bord.

---

## Ligne de base comportementale locale

Le moteur construit une ligne de base privée par appareil :
- Modèles de processus normaux
- Comportement typique des connexions réseau
- Activité de fichiers attendue
- Comportement habituel selon l'heure du jour et le jour de la semaine

La ligne de base est :
- Stockée localement sous forme chiffrée
- Réinitialisable par l'utilisateur à tout moment
- Jamais transmise ni partagée

---

## Résumé

Le moteur IA combine Isolation Forest avec une analyse statistique pour offrir une détection d'anomalies transparente, explicable et respectueuse de la vie privée — entièrement sur l'appareil de l'utilisateur, sans dépendance cloud.
