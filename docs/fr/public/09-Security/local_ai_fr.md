# Moteur IA/ML Local

Le moteur IA/ML de Nyroxis est entièrement local et hors ligne.
Il effectue toutes les analyses comportementales, la détection d'anomalies et la notation statistique **sans envoyer aucune donnée vers le cloud**.

---

## 1. Moteur Entièrement Hors Ligne

Le moteur IA/ML fonctionne entièrement sur l'appareil :
- Aucune communication avec des serveurs
- Aucune mise à jour de modèle en ligne
- Aucune télémétrie
- Aucune dépendance externe

Toute inférence et tout traitement sont isolés dans l'environnement d'exécution local.
Construit en Rust sans dépendance à une bibliothèque ML externe.

---

## 2. Isolation Forest — Algorithme Central

Le moteur implémente un algorithme Isolation Forest personnalisé :
- 100 arbres d'isolation par cycle d'analyse
- 256 échantillons maximum par arbre
- 8 caractéristiques comportementales par fenêtre d'analyse
- Seuil de score d'anomalie : 0,6

Les événements anormaux nécessitent moins de divisions pour être isolés — un chemin d'isolation plus court = un score d'anomalie plus élevé.

**8 caractéristiques comportementales analysées :**

| Caractéristique | Description |
|----------------|-------------|
| Nombre d'événements | Total des événements dans la fenêtre d'analyse |
| Sources uniques | Sources d'événements distinctes |
| Destinations uniques | Destinations réseau distinctes |
| Heure du jour | Contexte temporel pour la référence comportementale |
| Jour de la semaine | Reconnaissance des schémas hebdomadaires |
| Événements par heure | Normalisation du taux d'activité |
| Ratio de nouvelles sources | Proportion de sources précédemment inconnues |
| Ratio de nouvelles destinations | Proportion de destinations précédemment inconnues |

---

## 3. Moteur d'Analyse Statistique

Fonctionnant en parallèle avec Isolation Forest :

| Z-Score | Sévérité | Confiance |
|---------|----------|-----------|
| > 3,0 | Critique | 99,7 % |
| > 2,0 | Élevée | 95 % |
| > 1,5 | Moyenne | 86 % |
| > 1,0 | Faible | 68 % |

Méthodes supplémentaires :
- Détection de valeurs aberrantes IQR
- Moyennes mobiles simples et exponentielles
- Détection de pics par rapport aux références historiques
- Analyse de corrélation entre les signaux comportementaux

---

## 4. Résultats Explicables

Chaque détection comprend :
- Score d'anomalie (0,0–1,0)
- Classification de la sévérité
- Caractéristiques contributives — les dimensions comportementales spécifiques qui ont le plus dévié, avec les valeurs Z-Score

Le système met en évidence **pourquoi** quelque chose est suspect — transparent et vérifiable localement.

---

## 5. Références Comportementales Locales

Chaque appareil construit son propre profil de référence privé :
- Activité normale des processus
- Schémas typiques de connexions réseau
- Schémas d'accès aux fichiers attendus
- Comportement habituel selon l'heure du jour et le jour de la semaine

Les références :
- Stockées localement sous forme chiffrée
- Réinitialisables par l'utilisateur à tout moment
- Jamais transmises ni partagées

---

## 6. Aucun Entraînement ni Téléchargement vers le Cloud

Le moteur IA/ML ne télécharge **pas** :
- Les journaux ou données d'événements
- Les échantillons d'anomalies
- Les profils comportementaux
- Les retours sur les modèles
- Aucune donnée utilisateur

L'entraînement et l'inférence sont exclusivement hors ligne.

---

## 7. Léger et Efficace en Ressources

Optimisé pour les ordinateurs portables personnels, les appareils de direction et les systèmes en mode air-gap — le moteur IA/ML fournit une détection comportementale robuste sans nécessiter de matériel d'entreprise.

---

## Résumé

Le moteur IA/ML de Nyroxis garantit :
- Inférence locale uniquement — aucune dépendance cloud
- Confidentialité totale — aucun partage de données
- Détection comportementale robuste via Isolation Forest
- Profondeur statistique via Z-Score, IQR et détection de pics
- Résultats transparents et explicables avec caractéristiques contributives
