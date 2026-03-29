# Fonctionnalités clés

Nyroxis apporte une visibilité et une détection de niveau entreprise aux appareils personnels et professionnels, tout en restant léger, privé et entièrement utilisable hors ligne.

---

## Moteur de détection multicouche

Nyroxis Intelligence opère sur trois couches de détection séquentielles :

### Couche 1 — Détection (27 règles)
Identifie les patterns de menaces connus dans les événements individuels :
- Exécution de processus suspects
- Installation de services non autorisés
- Comportement réseau anormal
- Tentatives d'accès aux identifiants

### Couche 2 — Corrélation (12 règles)
Relie des événements connexes dans le temps et entre les sources pour révéler des patterns qu'aucun événement isolé n'exposerait :
- Échec de connexion suivi d'une connexion réussie depuis un emplacement différent
- Nouveau processus lancé immédiatement après la connexion d'un périphérique USB

### Couche 3 — Chaîne (2 règles)
Détecte des séquences d'attaques en plusieurs étapes — les intrusions coordonnées et progressives qui caractérisent les menaces persistantes avancées.

La bibliothèque de règles s'enrichit en continu. Les professionnels de la sécurité peuvent rédiger et déployer leurs propres règles personnalisées directement dans le moteur sans modifier le système central.

---

## Surveillance locale des événements

L'agent Nyroxis collecte en continu les activités pertinentes pour la sécurité :
- Création et arrêt de processus
- Connexions réseau et métadonnées de trafic
- Modifications de fichiers et du registre
- Actions liées aux privilèges
- Événements système et de sécurité (Journaux d'événements Windows)
- Exécution de PowerShell et de scripts

Toute la surveillance s'effectue **localement**, sans envoi de données vers le cloud.

---

## Stockage chiffré de qualité forensique

Tous les événements collectés sont :
- Chiffrés au repos (AES-256)
- Protégés contre la falsification via des blocs d'événements chaînés par hachage
- Stockés uniquement sur l'appareil de l'utilisateur
- Appropriés aux procédures juridiques et réglementaires

---

## Moteur IA/ML local

Nyroxis intègre une implémentation personnalisée d'Isolation Forest développée en Rust — aucune bibliothèque ML externe requise :
- 100 arbres d'isolation par cycle d'analyse
- 8 caractéristiques comportementales analysées par fenêtre
- Analyse statistique Z-Score : Critique / Élevé / Moyen / Faible
- Détection d'anomalies IQR, moyennes mobiles, détection de pics
- Tout le calcul s'effectue sur l'appareil — jamais dans le cloud

---

## Gardien de plateforme (Nyroxis System Guardian)

Un service discret dans la barre des tâches qui :
- Surveille tous les services de la plateforme toutes les 3 secondes
- Gère les sauvegardes de base de données planifiées et à la demande
- Valide la licence basée sur le HWID entièrement hors ligne
- Vérifie automatiquement les mises à jour
- Arrête automatiquement les services si la licence expire

---

## Tableau de bord intuitif

Le tableau de bord offre :
- Chronologie des événements en temps réel et indicateurs de gravité
- Vues des résultats de détection, de corrélation et de chaîne
- Recherche forensique avec filtrage avancé
- Analyse IA/ML avec décomposition des caractéristiques contributives
- Rapports — export PDF/CSV
- Gestion des sauvegardes de base de données
- Disponible en anglais, français et allemand

---

## Fonctionnement hors ligne prioritaire

Nyroxis fonctionne entièrement sans :
- Connexion cloud
- Dépendance à Internet
- Authentification externe

La plateforme est conçue pour les environnements à haute confidentialité et fonctionne dans des configurations isolées (air-gapped).

---

## Architecture résistante aux manipulations

Nyroxis protège :
- Tous les services de la plateforme via Nyroxis System Guardian
- Les journaux locaux via des blocs d'événements chaînés par hachage
- L'intégrité des données d'événements grâce à une vérification continue

Les attaquants ne peuvent pas effacer leurs traces sans être détectés.
