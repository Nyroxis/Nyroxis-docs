# Nyroxis Agent — Vue d'ensemble

Le Nyroxis Agent est le composant principal de surveillance et de collecte de la plateforme.
Il s'exécute localement sur l'appareil de l'utilisateur, collectant et normalisant discrètement les événements de sécurité, les chiffrant et les stockant dans une base de données locale résistante aux manipulations — le tout avec une utilisation minimale des ressources.

---

## Ce que fait l'Agent

L'Agent observe en permanence l'activité du système et construit une chronologie de sécurité structurée et chiffrée.

Il surveille :
- La création et la terminaison de processus
- Les connexions réseau et les métadonnées de trafic
- Les modifications de fichiers et les changements de registre
- Les actions de privilèges et les tentatives d'accès aux informations d'identification
- Les événements système et de sécurité (Journaux d'événements Windows)
- L'exécution de PowerShell et de scripts

Tous les événements sont collectés **de manière privée et locale** — rien n'est transmis à l'extérieur.

---

## Pipeline de collecte

1. **Collecte** — les événements sont ingérés simultanément depuis plusieurs canaux système
2. **Normalisation** — les données brutes sont enrichies et standardisées pour le moteur de détection
3. **Chiffrement** — la charge utile est chiffrée avec AES-256 avant toute opération d'écriture
4. **Stockage** — les événements chiffrés sont écrits dans la base de données SQLite locale
5. **Alimentation** — les données transitent vers Nyroxis Intelligence pour l'évaluation des règles en temps réel

---

## Fonctionnement axé sur la confidentialité

L'Agent ne télécharge jamais de journaux ni n'envoie de données d'événements vers des serveurs externes.
Tout reste sur l'appareil et est :
- Chiffré au moment de la collecte
- Protégé contre les manipulations via des blocs d'événements chaînés par hachage
- Stocké dans une base de données SQLite locale sécurisée
- Sous le contrôle exclusif de l'utilisateur à tout moment

---

## Léger par conception

L'Agent est optimisé pour une empreinte minimale :
- ~57 Mo de RAM
- ~0,1 % de CPU
- Fonctionnement silencieux en arrière-plan en tant que service Windows
- Adapté à un fonctionnement continu sur des ordinateurs portables personnels sans impact sur la productivité quotidienne

---

## Résilient et conscient des manipulations

L'Agent intègre des mécanismes de protection pour garantir :
- Les données d'événements collectées ne peuvent être modifiées ou supprimées sans être détectées
- Les attaquants ne peuvent pas effacer silencieusement leur activité
- Les blocs d'événements chaînés par hachage exposent toute tentative de suppression, modification ou injection

Nyroxis System Guardian surveille l'état opérationnel de l'Agent toutes les 3 secondes et prend des mesures correctives si le service s'arrête de manière inattendue.

---

## Fonctionne entièrement hors ligne

Aucune connexion Internet n'est requise pour :
- La surveillance
- La normalisation et le chiffrement
- Le stockage des données
- L'alimentation de Nyroxis Intelligence

Nyroxis est entièrement fonctionnel dans des environnements isolés ou à air gap.

---

## Résumé

Le Nyroxis Agent offre une surveillance continue, chiffrée et hors ligne — donnant aux utilisateurs une visibilité de niveau entreprise sans exposer leurs données à des tiers, et fournissant des preuves de qualité forensique adaptées aux procédures judiciaires et réglementaires.
