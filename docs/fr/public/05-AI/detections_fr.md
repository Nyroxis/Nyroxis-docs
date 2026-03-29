# Détections IA

La vue Détections IA affiche les anomalies identifiées par le moteur IA/ML local — lorsqu'il identifie une activité inhabituelle ou suspecte sur l'appareil basée sur une analyse comportementale et une notation statistique.
Toutes les détections sont générées localement, sans traitement cloud ni partage de données.

---

## Objectif des détections IA

Le moteur IA détecte :
- Les anomalies comportementales — des déviations par rapport à la ligne de base établie de l'appareil
- Les séquences d'activités suspectes
- Les modèles rares ou inattendus
- Les valeurs aberrantes statistiques à travers les caractéristiques comportementales
- Les déviations à haut risque identifiées par la notation Isolation Forest

Ces détections complètent les résultats basés sur les règles de Nyroxis Intelligence, ajoutant une couche d'intelligence comportementale qui ne repose pas sur des règles prédéfinies.

---

## Types de détections IA

### 1. Détections basées sur les anomalies
Déclenchées lorsque le score d'anomalie Isolation Forest dépasse 0,6 — ce qui signifie que le modèle comportemental observé est statistiquement isolé de la ligne de base normale.

Exemples de cas :
- Activité de processus inhabituelle à des moments inattendus
- Modèles de connexion réseau irréguliers
- Bursts inattendus de modifications de fichiers
- Activité très en dehors de la ligne de base typique selon l'heure du jour ou le jour de la semaine

---

### 2. Valeurs aberrantes statistiques (Z-Score)
Déclenchées lorsqu'une caractéristique comportementale spécifique dévie significativement de la moyenne historique :
- Critique : Z-score > 3,0 (confiance à 99,7 %)
- Élevé : Z-score > 2,0 (confiance à 95 %)
- Moyen : Z-score > 1,5 (confiance à 86 %)
- Faible : Z-score > 1,0 (confiance à 68 %)

---

### 3. Détections de pics
Déclenchées lorsqu'une métrique surveillée saute soudainement bien au-dessus de sa moyenne historique :
- Burst soudain d'événements par heure
- Pic de nouvelles destinations réseau
- Augmentation rapide des sources uniques

---

### 4. Anomalies persistantes
Déviations à long terme qui s'accumulent dans le temps :
- Augmentation graduelle du ratio de nouvelles destinations
- Modèles d'activité inhabituelle se construisant lentement
- Anomalies répétées à faible score formant une tendance

---

## Détails de détection

Chaque détection IA inclut :
- Description de l'anomalie
- Score d'anomalie (0,0 – 1,0)
- Classification de gravité
- Caractéristiques contributives — les dimensions comportementales spécifiques qui se sont le plus écartées de la ligne de base, avec les valeurs Z-score
- Horodatage et fenêtre d'analyse

---

## 100 % Local & Privé

Toutes les détections IA sont :
- Calculées hors ligne sur l'appareil
- Stockées localement dans la base de données chiffrée
- Dérivées des journaux d'événements chiffrés
- Jamais téléchargées vers des serveurs ni partagées avec des tiers

---

## Résumé

Les détections IA fournissent des alertes d'anomalies intelligentes et respectueuses de la vie privée qui complètent la détection basée sur les règles — aidant les utilisateurs à identifier tôt les activités dangereuses ou anormales, avec un traitement entièrement local et sans dépendance cloud.
