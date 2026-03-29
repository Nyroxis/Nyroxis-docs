# Architecture de Haut Niveau

L'architecture Nyroxis est conçue pour offrir une sécurité robuste, une confidentialité totale et une autonomie hors ligne complète.
Cette vue d'ensemble de haut niveau explique comment tous les composants majeurs fonctionnent ensemble tout en maintenant les données utilisateur protégées et chiffrées localement.

---

## Principes Architecturaux Fondamentaux

### 1. Fonctionnement Entièrement Local
Tout le traitement — collecte, détection, analyse IA, stockage, rapports — s'effectue sur l'appareil. Rien n'est téléchargé ou transmis.

### 2. Confidentialité par Conception
Aucun cloud. Aucune télémétrie. Aucune surveillance à distance. Aucun profilage comportemental.

### 3. Léger et Efficace
Conçu pour fonctionner en continu sur des ordinateurs portables personnels sans impacter la productivité quotidienne.

### 4. Intégrité Forensique
Les journaux d'événements sont chiffrés, enchaînés par hachage et inviolables — adaptés aux procédures juridiques et réglementaires.

---

## Composants de Haut Niveau

### 1. Nyroxis Agent
- Capture les événements système en temps réel depuis plusieurs canaux
- Normalise et chiffre immédiatement
- Stocke les événements chiffrés dans la base de données locale
- ~57 Mo de RAM, ~0,1 % du CPU

### 2. Nyroxis Intelligence
- Évalue les événements selon 27 règles de détection + 12 règles de corrélation + 2 règles de chaîne
- Génère des alertes immédiates lors de correspondances de règles
- Entièrement extensible par les professionnels de la sécurité (format de règle JSON)
- ~87 Mo de RAM, ~1,8 % du CPU

### 3. Nyroxis System Guardian
- Surveille Agent et Intelligence toutes les 3 secondes
- Gère les sauvegardes et la validation de licence HWID hors ligne
- Arrête les services si la licence expire
- ~6,5 Mo de RAM, ~0,1 % du CPU

### 4. Base de Données Locale Sécurisée
- SQLite avec chiffrement AES-256
- Blocs d'événements enchaînés par hachage pour la détection de falsification
- Stocke les événements, résultats, résultats IA et références comportementales
- Ne quitte jamais l'appareil

### 5. Moteur IA/ML Local
- Détection d'anomalies Isolation Forest (100 arbres, 8 caractéristiques)
- Z-Score, IQR, moyenne mobile, détection de pics
- Décomposition des caractéristiques contributives pour les analystes
- Entièrement hors ligne — aucune inférence cloud

### 6. Nyroxis Dashboard
- Visibilité en temps réel : événements, détections, corrélations, chaînes, IA/ML
- Recherche forensique, graphiques, rapports (PDF/CSV)
- Gestion des sauvegardes, paramètres, multilingue (EN/FR/DE)
- Toutes les données récupérées localement

---

## Couches de Sécurité

L'architecture comprend plusieurs couches de défense :
- Chiffrement à la capture (AES-256)
- Structures d'événements enchaînées par hachage
- Chemins d'écriture protégés
- Gardien de plateforme pour la résilience des services
- Validation de licence hors ligne
- Aucune communication externe d'aucune sorte

---

## Résumé du Flux de Données

```
[ Événements Système ]
        ↓
[ Nyroxis Agent ]          ← collecte, normalise, chiffre
        ↓
[ Base de Données Chiffrée Locale ]  ← AES-256, SQLite, enchaîné par hachage
        ↓
[ Nyroxis Intelligence ]   ← 27 détection + 12 corrélation + 2 règles de chaîne
        ↓
[ Moteur IA/ML Local ]     ← Isolation Forest + analyse statistique
        ↓
[ Nyroxis Dashboard ]      ← visibilité, forensique, rapports
        ↑
[ Nyroxis System Guardian ] ← surveille, sauvegarde, valide la licence
```

---

## Résumé

L'architecture Nyroxis offre une sécurité puissante, privée et hors ligne en combinant quatre composants essentiels — Agent, Intelligence, System Guardian et Dashboard — fonctionnant ensemble avec une IA/ML locale et un stockage de qualité forensique, entièrement sans exposition au cloud.
