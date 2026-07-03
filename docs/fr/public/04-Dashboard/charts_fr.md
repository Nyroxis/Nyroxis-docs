# Graphiques & Analyses

La section Graphiques & Analyses du tableau de bord Nyroxis transforme les événements de sécurité bruts en insights visuels, aidant les utilisateurs à comprendre rapidement les tendances, les anomalies et les risques potentiels.
Toutes les analyses sont générées localement, préservant une confidentialité totale.

---

## Objectif de l'analyse visuelle

Les graphiques aident les utilisateurs à répondre immédiatement aux questions clés :
- L'activité augmente-t-elle ou diminue-t-elle au fil du temps ?
- Y a-t-il des pics inhabituels dans les processus ou le trafic réseau ?
- Quelles catégories d'événements surviennent le plus souvent ?
- Comment les résultats de détection et de corrélation sont-ils répartis par gravité ?
- Y a-t-il des modèles suspects récurrents au fil du temps ?

Les visuels rendent les données de sécurité complexes immédiatement compréhensibles.

---

## Types de graphiques disponibles

### 1. Fréquence des événements dans le temps
Affiche le nombre d'événements survenant par heure, par jour et par semaine.
Utile pour repérer les pics, les rafales d'activité ou les périodes de calme inattendues pouvant indiquer qu'un élément a été désactivé.

### 2. Répartition par gravité
Décomposition visuelle des événements par niveau de gravité : Critique, Élevé, Avertissement, Info.
Aide les utilisateurs à voir le profil de risque global en un coup d'œil.

### 3. Principales sources d'événements
Met en évidence les processus, fichiers ou points de terminaison réseau qui génèrent le plus d'événements :
- Processus les plus actifs
- Fichiers les plus consultés
- Connexions réseau les plus fréquentes

### 4. Tendance de détection & corrélation
Suit l'évolution des correspondances de règles dans le temps :
- Résultats de détection
- Résultats de corrélation
- Résultats de chaîne

Aide les utilisateurs à détecter les schémas d'escalade avant qu'une compromission complète ne survienne.

### 5. Tendance du score d'anomalie IA/ML
Visualise la sortie du moteur Isolation Forest local dans le temps :
- Évolution du score d'anomalie
- Classifications de gravité : Critique / Élevé / Moyen / Faible
- Événements de pic par rapport à la ligne de base comportementale

---

## Moteur d'analyse local

Tous les graphiques sont alimentés par le moteur d'analyse local :
- Pas de cloud
- Pas d'APIs externes
- Tous les calculs restent sur l'appareil

Les graphiques sont générés directement depuis la base de données locale chiffrée et la sortie du moteur IA/ML.

---

## Confidentialité & fonctionnement hors ligne

Les graphiques sont générés entièrement sur l'appareil ; vos données d'événements ne sont pas envoyées à des services externes.
Les analyses sont calculées et rendues localement à partir d'événements chiffrés, entièrement hors ligne.

---

## Résumé

Graphiques & Analyses offrent un moyen visuel et respectueux de la vie privée pour comprendre l'activité du système, suivre les tendances de détection, surveiller les résultats IA/ML et obtenir une vue immédiate de la posture de sécurité de l'appareil.
