# Aperçu de la Sécurité

Nyroxis est conçu avec une philosophie stricte de sécurité d'abord : toutes les opérations sont locales, chiffrées, inviolables et conçues pour protéger l'utilisateur sans exposer aucune donnée à des tiers.

Cette vue d'ensemble résume les principaux principes et mécanismes de sécurité utilisés sur l'ensemble de la plateforme.

---

## Principes Fondamentaux de Sécurité

### 1. Confidentialité par Conception
Nyroxis ne télécharge, synchronise ni transmet aucune donnée vers des serveurs.
Toute la logique de sécurité, la surveillance, la détection et l'analyse IA s'exécutent entièrement sur l'appareil.

### 2. Chiffrement Partout
Chaque événement capturé est :
- Chiffré instantanément à la capture (AES-256)
- Stocké uniquement sous forme chiffrée — jamais en clair
- Déchiffré exclusivement en mémoire lors du traitement
- Protégé par des hashes d'intégrité

Aucun journal en clair n'existe jamais sur le disque.

### 3. Zéro Dépendance Cloud
Nyroxis ne s'appuie pas sur :
- Le stockage ou traitement cloud
- Les API externes
- Les serveurs distants
- Les pipelines de télémétrie
- L'authentification en ligne

Les utilisateurs maintiennent une autonomie totale et une exposition externe nulle.

### 4. Détection Multi-Couches
Nyroxis Intelligence offre :
- 27 règles de détection — patterns de menaces connues
- 12 règles de corrélation — patterns multi-événements dans le temps
- 2 règles de chaîne — séquences d'attaques en plusieurs étapes
- Extensible par les professionnels de la sécurité sans modifier les composants centraux

### 5. IA/ML Local
Le moteur IA/ML traite les données localement :
- Détection d'anomalies Isolation Forest
- Classification statistique Z-Score
- Identification des caractéristiques contributives

Aucun entraînement cloud, aucune inférence cloud, aucun partage de données.

---

## Mécanismes de Sécurité Clés

### 1. Capture Sécurisée des Événements
Nyroxis Agent capture :
- Les processus et services
- Les modifications du système de fichiers et du registre
- Les connexions réseau
- Les actions de privilèges
- Les entrées du journal d'événements Windows

Tous les événements sont chiffrés immédiatement à la capture.

### 2. Stockage Inviolable
La base de données SQLite locale comprend :
- Le chiffrement AES-256
- Les blocs d'événements enchaînés par hachage
- Les chemins d'écriture protégés
- La vérification de l'intégrité à chaque lecture

Les attaquants ne peuvent pas modifier, supprimer ou injecter des journaux sans être détectés.

### 3. Résilience de la Plateforme
Nyroxis System Guardian :
- Surveille Agent et Intelligence toutes les 3 secondes
- Détecte immédiatement les arrêts de service inattendus
- Enregistre les tentatives d'arrêt comme événements de sécurité
- Gère les sauvegardes et la validation de licence hors ligne

La plateforme ne peut pas être désactivée silencieusement.

### 4. Licences Basées sur le HWID
La validation de licence :
- Liée au matériel de l'appareil (clé dérivée du HWID)
- Validée hors ligne avec AES-GCM et HMAC
- Appliquée par System Guardian — les services s'arrêtent automatiquement si la licence est invalide

### 5. Sécurité du Dashboard
Le Dashboard :
- Lit les résumés déchiffrés uniquement en RAM
- Ne réécrit jamais de données déchiffrées sur le disque
- Ne se connecte pas à des sources externes
- Fournit un accès en lecture seule au stockage des journaux

---

## Résumé des Couches de Sécurité

Nyroxis intègre plusieurs couches de défense :
- Chiffrement AES-256 à la capture
- Stockage inviolable enchaîné par hachage
- Gardien de plateforme pour la résilience des services
- Moteur IA/ML local uniquement
- Validation de licence hors ligne
- Zéro exposition au cloud
- Architecture axée sur la confidentialité tout au long

---

## Résumé

Nyroxis offre un modèle de sécurité moderne, privé et hors ligne qui protège les utilisateurs sans les tracer — combinant transparence, contrôle, intégrité forensique et conception défensive robuste à chaque niveau.
