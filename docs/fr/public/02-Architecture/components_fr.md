# Composants de l'architecture

Cette section décrit chaque composant majeur de la plateforme Nyroxis.
Tous les composants sont conçus pour fonctionner localement, efficacement et selon une approche axée sur la confidentialité.

---

## 1. Nyroxis Agent

Le service principal de surveillance et de collecte fonctionnant sur l'appareil.

### Responsabilités
- Collecte les événements de sécurité depuis plusieurs canaux système simultanément
- Surveille les processus, l'activité réseau, le système de fichiers, le registre et les actions liées aux privilèges
- Normalise les données d'événements en temps réel
- Chiffre le payload immédiatement et l'écrit dans la base de données locale
- Maintient une intégrité inviolable via des blocs d'événements chaînés par hachage

### Propriétés
- ~57 Mo de RAM, ~0,1 % de CPU
- Fonctionne silencieusement en tant que service Windows en arrière-plan
- Hors ligne prioritaire — rien ne quitte l'appareil

---

## 2. Nyroxis Intelligence

Le moteur de détection et de corrélation — le cœur analytique de la plateforme.

### Trois couches de détection

| Couche | Règles | Objectif |
|--------|--------|---------|
| nyroxis_detection | 27 | Identifier les patterns de menaces connus dans les événements individuels |
| nyroxis_correlations | 12 | Relier des événements suspects connexes dans le temps et entre les sources |
| nyroxis_chains | 2 | Détecter des séquences d'attaques en plusieurs étapes |

### Propriétés
- Fonctionne à haute vitesse sur les trois couches simultanément
- La bibliothèque de règles s'enrichit en continu à mesure que de nouvelles menaces émergent
- Entièrement extensible — les professionnels de la sécurité peuvent rédiger et déployer des règles personnalisées au format JSON sans modifier le système central
- ~87 Mo de RAM, ~1,8 % de CPU

---

## 3. Nyroxis System Guardian

Le gardien de la plateforme — fonctionne silencieusement en tant qu'application dans la barre des tâches Windows.

### Responsabilités
- Surveille Nyroxis Agent et Nyroxis Intelligence toutes les 3 secondes
- Détecte les arrêts de service inattendus et prend des mesures correctives
- Gère les sauvegardes de base de données planifiées et à la demande
- Valide la licence basée sur le HWID hors ligne (vérification AES-GCM + HMAC)
- Arrête automatiquement tous les services si la licence expire ou est invalidée
- Vérifie les mises à jour de la plateforme à intervalles configurables

### Propriétés
- ~6,5 Mo de RAM, ~0,1 % de CPU
- Validation de licence entièrement hors ligne — aucune connexion internet requise
- Essentiel pour la résilience de la plateforme et l'intégrité forensique

---

## 4. Base de données locale chiffrée

Nyroxis utilise une base de données SQLite sécurisée pour conserver tous les événements collectés.

### Caractéristiques
- Chiffrement intégral au repos (AES-256)
- Blocs d'événements chaînés par hachage pour la détection des altérations
- Stockage structuré des événements avec vérification de l'intégrité
- Optimisé pour les recherches rapides et la reconstruction de la chronologie
- Aucun envoi vers le cloud — l'utilisateur est le seul propriétaire des données

---

## 5. Nyroxis Dashboard

Une interface visuelle qui transforme les données de sécurité brutes en renseignements exploitables.

### Fournit
- Surveillance des événements en temps réel avec recherche forensique et filtrage
- Visualisation des résultats de détection, de corrélation et de chaîne
- Moteur IA/ML local intégré (Isolation Forest + analyse statistique)
- Rapports — export PDF/CSV
- Gestion des sauvegardes de base de données
- Interface multilingue : anglais, français, allemand

### Public cible
Les utilisateurs non techniques comme les professionnels de la cybersécurité peuvent l'utiliser efficacement.

---

## 6. Moteur IA/ML local

Un moteur de détection d'anomalies entièrement hors ligne intégré dans le Dashboard.

### Fonctions
- Algorithme Isolation Forest (100 arbres, 256 échantillons, 8 caractéristiques comportementales)
- Classification statistique Z-Score : Critique / Élevé / Moyen / Faible
- Détection d'anomalies IQR, moyennes mobiles, détection de pics
- Construction d'une référence comportementale et scoring des déviations
- Identification des caractéristiques contributives pour le contexte des analystes

Tout fonctionne localement — aucun cloud, aucune télémétrie, aucun partage de données.

---

## Résumé
Nyroxis est construit à partir de composants modulaires et locaux qui fonctionnent ensemble pour offrir aux utilisateurs une visibilité et une détection de niveau entreprise — de manière privée, efficace et sans dépendance au cloud.
