# Flux de données

Cette section explique comment les données circulent à l'intérieur de Nyroxis — de la collecte des événements à l'interprétation par l'utilisateur — tout en restant entièrement locales, chiffrées et privées à chaque étape.

---

## 1. Collecte des événements (Nyroxis Agent)

Nyroxis Agent surveille en continu :
- Les processus et services
- Les connexions réseau et les métadonnées de trafic
- Les modifications du système de fichiers et du registre
- Les actions liées aux privilèges
- Les événements système et de sécurité (Journaux d'événements Windows)
- L'exécution de PowerShell et de scripts

Toutes les données sont collectées **localement**, sans aucune interaction avec le cloud.

---

## 2. Normalisation et chiffrement à la source

Immédiatement après la collecte :
- Les événements sont normalisés et enrichis avec du contexte
- Le payload est chiffré avec AES-256
- Un hachage d'intégrité est appliqué
- Les données sont écrites dans la base de données locale uniquement sous forme chiffrée

Aucun texte en clair ne touche jamais le disque.

---

## 3. Base de données locale chiffrée

Les événements chiffrés sont stockés dans une base de données SQLite sécurisée.

Propriétés :
- Entièrement chiffrée au repos (AES-256)
- Blocs d'événements chaînés par hachage pour la détection des altérations
- Structurée pour des recherches rapides et la reconstruction de la chronologie
- Aucune transmission externe — jamais

La base de données ne quitte jamais l'appareil.

---

## 4. Nyroxis Intelligence — Moteur de règles

Nyroxis Intelligence lit depuis la base de données chiffrée et évalue les événements sur trois couches :
- **27 règles de détection** — correspondance de patterns d'événements individuels
- **12 règles de corrélation** — détection de patterns multi-événements dans le temps
- **2 règles de chaîne** — détection de séquences d'attaques en plusieurs étapes

Lorsqu'une règle est déclenchée :
- Une alerte est immédiatement levée
- La constatation est stockée dans une base de données de détections dédiée
- L'utilisateur est notifié via le Dashboard

---

## 5. Moteur IA/ML local

En parallèle, le moteur IA/ML traite les événements localement :
- Scoring d'anomalies par Isolation Forest
- Classification statistique Z-Score
- Comparaison avec la référence comportementale
- Identification des caractéristiques contributives

Tout le calcul reste sur l'appareil — aucune inférence cloud, aucun partage de données.

---

## 6. Visualisation dans le Dashboard

Le Nyroxis Dashboard transforme tout ce qui précède en :
- Journaux d'événements avec recherche forensique et filtrage
- Résultats de détection, de corrélation et de chaîne
- Résultats d'anomalies IA/ML avec décomposition des caractéristiques contributives
- Graphiques, indicateurs de gravité et analyse de tendances
- Rapports exportables (PDF/CSV)

Tout reste local et privé.

---

## Cycle de vie complet des données

```
[ Événements système ]
        ↓
[ Nyroxis Agent ]          ← collecte, normalisation, chiffrement
        ↓
[ Base de données locale chiffrée ] ← AES-256, SQLite, chaîné par hachage
        ↓
[ Nyroxis Intelligence ]   ← 27 détections + 12 corrélations + 2 règles de chaîne
        ↓
[ Moteur IA/ML local ]     ← Isolation Forest + analyse statistique
        ↓
[ Nyroxis Dashboard ]      ← visibilité, forensique, rapports
        ↑
[ Nyroxis System Guardian ] ← surveille, sauvegarde, valide la licence
```

À aucune étape les journaux ou les données sensibles ne sont téléchargés vers des serveurs externes.

---

## Résumé
Nyroxis maintient un flux de données strictement local, chiffré et axé sur la confidentialité — offrant aux utilisateurs une visibilité complète et des preuves forensiques sans exposer aucune information au cloud ou à des tiers.
