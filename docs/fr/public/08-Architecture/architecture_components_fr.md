# Composants de l'Architecture

Cette section décrit chaque composant central de la plateforme Nyroxis et explique comment ils fonctionnent ensemble pour offrir une sécurité privée, hors ligne et inviolable.

---

## 1. Nyroxis Agent

Le service d'arrière-plan léger responsable de :
- La surveillance des processus, des connexions réseau, des modifications de fichiers et des activités de privilèges
- La capture des entrées du journal d'événements Windows (Sécurité, Système, Application)
- La surveillance de l'exécution de PowerShell et des scripts
- La normalisation des données d'événements en temps réel
- Le chiffrement de chaque événement immédiatement avant l'écriture

Propriétés :
- ~57 Mo de RAM, ~0,1 % du CPU
- Service Windows silencieux
- Entièrement hors ligne — rien ne quitte l'appareil

---

## 2. Nyroxis Intelligence

Le moteur de détection et de corrélation :
- **27 règles de détection** — patterns de menaces connues dans des événements individuels
- **12 règles de corrélation** — patterns entre des événements liés dans le temps
- **2 règles de chaîne** — détection de séquences d'attaques en plusieurs étapes

Propriétés :
- ~87 Mo de RAM, ~1,8 % du CPU
- Entièrement extensible — les professionnels de la sécurité peuvent écrire et déployer des règles personnalisées au format JSON
- Génère des alertes immédiates lors de correspondances de règles
- Stocke les résultats dans des bases de données de détection dédiées

---

## 3. Nyroxis System Guardian

Le gardien de la plateforme fonctionnant en tant qu'application de la barre d'état système :
- Surveille Nyroxis Agent et Intelligence toutes les 3 secondes
- Gère les sauvegardes planifiées et à la demande de la base de données
- Valide la licence basée sur le HWID hors ligne (AES-GCM + HMAC)
- Arrête automatiquement les services si la licence expire
- Vérifie les mises à jour de la plateforme à des intervalles configurables

Propriétés :
- ~6,5 Mo de RAM, ~0,1 % du CPU
- Validation de licence entièrement hors ligne
- Critique pour la résilience de la plateforme et l'intégrité forensique

---

## 4. Base de Données Locale Sécurisée

Une base de données SQLite protégée contenant :
- Les journaux d'événements chiffrés
- Les résultats de détection et de corrélation
- Les résultats d'analyse IA/ML
- Les données de référence comportementale
- Les métadonnées pour la reconstruction de la chronologie forensique

Fonctionnalités de sécurité :
- Chiffrement AES-256 au repos
- Blocs d'événements enchaînés par hachage pour la détection de falsification
- Chemins d'écriture protégés
- Vérification de l'intégrité à chaque lecture

La base de données **ne quitte jamais l'appareil**.

---

## 5. Moteur IA/ML Local

Le moteur de détection d'anomalies hors ligne intégré dans le Dashboard :
- Isolation Forest personnalisé (100 arbres, 256 échantillons, 8 caractéristiques comportementales)
- Classification statistique Z-Score : Critique / Élevé / Moyen / Faible
- Détection de valeurs aberrantes IQR, moyennes mobiles, détection de pics
- Identification des caractéristiques contributives avec valeurs Z-Score
- Construction locale de la référence comportementale

Aucun cloud, aucune bibliothèque ML externe, aucun partage de données.

---

## 6. Nyroxis Dashboard

L'interface utilisateur offrant :
- La surveillance des événements en temps réel avec recherche forensique et filtrage
- La visualisation des résultats de détection, de corrélation et de chaîne
- L'analyse IA/ML avec décomposition des caractéristiques contributives
- Les rapports — export PDF/CSV
- La gestion des sauvegardes de la base de données
- Les paramètres et le contrôle de la rétention
- Multilingue : anglais, français, allemand

Tout ce qui est affiché est récupéré localement depuis la base de données sécurisée.

---

## Résumé

Les composants de Nyroxis fonctionnent comme un écosystème intégré, privé et hors ligne — offrant une visibilité de niveau entreprise, une détection multicouche, une intelligence IA/ML locale et des preuves de qualité forensique sans exposer aucune donnée utilisateur vers le cloud.
