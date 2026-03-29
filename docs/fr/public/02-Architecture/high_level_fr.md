# Vue d'ensemble de l'architecture

Nyroxis repose sur une architecture légère et axée sur la confidentialité, conçue pour offrir une visibilité et une détection de niveau entreprise sans dépendre du cloud.
Le système fonctionne entièrement sur l'appareil de l'utilisateur et est composé de quatre composants indépendants qui travaillent ensemble de manière sécurisée.

---

## Composants principaux

### 1. Nyroxis Agent
Un moniteur de terminal léger qui :
- Collecte les événements pertinents pour la sécurité depuis plusieurs canaux système
- Les normalise et les chiffre immédiatement à la capture
- Stocke tout dans une base de données locale inviolable
- Fonctionne à 100 % hors ligne — ~57 Mo de RAM, ~0,1 % de CPU

### 2. Nyroxis Intelligence
Un moteur de détection et de corrélation à haute vitesse qui :
- Applique 27 règles de détection aux événements individuels
- Exécute 12 règles de corrélation sur les événements connexes dans le temps
- Exécute 2 règles de chaîne pour détecter des séquences d'attaques en plusieurs étapes
- Déclenche des alertes immédiates lors de toute correspondance de règle
- Accepte des règles personnalisées des professionnels de la sécurité
- ~87 Mo de RAM, ~1,8 % de CPU

### 3. Nyroxis System Guardian
Un gardien discret dans la barre des tâches qui :
- Surveille Nyroxis Agent et Intelligence toutes les 3 secondes
- Gère les sauvegardes et la validation de licence basée sur le HWID (entièrement hors ligne)
- Vérifie automatiquement les mises à jour
- Arrête automatiquement les services si la licence expire
- ~6,5 Mo de RAM, ~0,1 % de CPU

### 4. Nyroxis Dashboard
Une interface claire et intuitive qui :
- Affiche les événements, détections, corrélations et chaînes
- Fournit une recherche forensique, des graphiques et des rapports PDF/CSV
- Inclut un moteur IA/ML local (Isolation Forest + analyse statistique)
- Supporte l'anglais, le français et l'allemand

---

## Flux de données de haut niveau

```
[ Événements système ]
        ↓
[ Nyroxis Agent ]          ← collecte, normalisation, chiffrement
        ↓
[ Base de données locale chiffrée ] ← AES-256, SQLite, chaîné par hachage
        ↓
[ Nyroxis Intelligence ]   ← 27 détections + 12 corrélations + 2 règles de chaîne
        ↓
[ Nyroxis Dashboard ]      ← visibilité, IA/ML, forensique, rapports
        ↑
[ Nyroxis System Guardian ] ← surveille, sauvegarde, valide la licence
```

À aucune étape les journaux ou les données sensibles ne sont téléchargés vers des serveurs externes.

---

## Principes de conception

### Confidentialité par conception
- Aucune ingestion cloud
- Chiffrement local à la capture
- L'utilisateur conserve un contrôle total à tout moment

### Intégrité forensique
- Journaux chiffrés AES-256
- Blocs d'événements chaînés par hachage
- Stockage inviolable adapté aux procédures judiciaires

### Fonctionnement léger
Conçu pour fonctionner en douceur sur des ordinateurs portables et des postes de travail personnels sans impacter la productivité quotidienne.

### Sécurité hors ligne prioritaire
Aucune connexion internet n'est requise pour :
- La surveillance et la détection
- L'analyse IA/ML
- L'utilisation du Dashboard
- La validation de la licence

### Extensibilité
Les professionnels de la sécurité peuvent rédiger et déployer des règles de détection, de corrélation et de chaîne personnalisées sans modifier le système central.

---

## Résumé
Nyroxis offre une architecture moderne, modulaire et forensiquement solide qui apporte une visibilité et une détection de niveau professionnel aux appareils personnels — entièrement hors ligne, dans le plein respect de la vie privée de l'utilisateur.
