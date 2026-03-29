# Journaux & Recherche

La section Journaux du tableau de bord Nyroxis offre une vue claire, consultable et structurée de tous les événements pertinents en matière de sécurité collectés par le Nyroxis Agent.
C'est le cœur forensique de la plateforme — conçu pour donner aux utilisateurs non techniques comme aux professionnels de la sécurité une visibilité instantanée sur ce qui se passe sur leur appareil.

---

## Objectif de la vue Journaux

Le module Journaux aide les utilisateurs à comprendre :
- Quels événements se sont produits et quand
- Quels processus, fichiers ou connexions réseau étaient impliqués
- Si l'activité semble normale ou suspecte
- Le contexte complet de tout événement pour une investigation forensique

Il transforme les données d'événements chiffrées brutes en entrées lisibles, horodatées et consultables.

---

## Catégories d'événements

Nyroxis organise les journaux en groupes intuitifs :

### 1. Événements de processus
- Démarrage et arrêt de processus
- Relations parent/enfant
- Chemins d'exécution et paramètres de ligne de commande

### 2. Événements réseau
- Connexions sortantes et entrantes
- Adresses IP et détails des ports
- Types de protocoles

### 3. Événements du système de fichiers
- Création, modification et suppression de fichiers
- Accès aux répertoires sensibles
- Modifications du registre

### 4. Événements de privilèges & sécurité
- Tentatives d'élévation
- Accès aux ressources restreintes
- Changements de politique système
- Activité liée aux informations d'identification

### 5. Activité système
- Démarrage et arrêt de services
- Chargement de pilotes
- Entrées du Journal d'événements Windows (Sécurité, Système, Application)
- Exécution de PowerShell et de scripts

---

## Recherche & Filtrage

L'interface Journaux comprend un puissant panneau de filtrage :

### Filtres disponibles
- Plage de date et d'heure
- Catégorie d'événement
- Niveau de gravité (Critique / Élevé / Avertissement / Info)
- Source et canal
- Nom du processus
- Chemin du fichier
- Point de terminaison réseau
- Mots-clés

### Capacités de recherche
- Filtrage en temps réel
- Recherche multi-champs
- Export en CSV pour documentation légale ou analyse externe

Conçu pour prendre en charge aussi bien les débutants que les analystes professionnels.

---

## Détails des événements

Cliquer sur un événement ouvre un panneau de détails affichant :
- Métadonnées complètes de l'événement
- Lignée du processus
- Fichiers ou connexions réseau associés
- Score de gravité
- Détails de la charge utile brute

---

## Confidentialité & priorité au mode hors ligne

Tous les journaux :
- Sont stockés localement dans la base de données SQLite chiffrée
- Sont entièrement chiffrés (AES-256)
- Ne quittent jamais l'appareil
- Sont traités sans aucune interaction avec le cloud

---

## Résumé

Le module Journaux & Recherche offre un moyen transparent, organisé et entièrement privé d'explorer l'activité du système — donnant aux utilisateurs une véritable visibilité forensique sans exposer aucune donnée à l'extérieur.
