# Collecteur d'événements

Le Collecteur d'événements est le sous-système au sein du Nyroxis Agent responsable de la capture de toute l'activité pertinente en matière de sécurité sur l'appareil.
Il est conçu pour être léger, privé et entièrement hors ligne, tout en offrant une visibilité de niveau entreprise sur le comportement des points de terminaison.

---

## Objectif du Collecteur d'événements

L'objectif principal du Collecteur d'événements est de rassembler des informations structurées et exploitables qui aident les utilisateurs à comprendre :
- Ce qui se passe sur leur appareil
- Quand les événements se produisent
- Si l'activité est normale ou suspecte

Le tout sans exposer les données à l'extérieur.

---

## Ce que surveille le Collecteur d'événements

Nyroxis se concentre sur les catégories d'événements les plus critiques en matière de sécurité :

### 1. Événements de processus
- Création et terminaison de processus
- Relations parent/enfant
- Paramètres de ligne de commande (lorsque disponibles)
- Chemins d'exécution et métadonnées binaires

### 2. Événements réseau
- Connexions sortantes et entrantes
- Adresses IP et ports de destination
- Type de protocole
- Tentatives de connexion répétées

### 3. Activité du système de fichiers
- Création, modification et suppression de fichiers
- Accès aux répertoires sensibles
- Modifications du registre

### 4. Événements de privilèges et de sécurité
- Tentatives d'élévation
- Appels système sensibles
- Modifications du registre et de la configuration
- Accès aux ressources protégées

### 5. Événements système et de service
- Démarrage/arrêt de services
- Chargement de pilotes
- Entrées du Journal d'événements Windows (Sécurité, Système, Application)
- Indicateurs de mécanismes de persistance
- Exécution de PowerShell et de scripts

La portée exacte est optimisée pour Windows (v1.0). La prise en charge de macOS et Linux est en cours de développement.

---

## Pipeline de normalisation

Après la collecte, chaque événement est :
1. Analysé et structuré dans un format normalisé
2. Enrichi avec des métadonnées contextuelles (horodatage, source, indication de gravité)
3. Préparé pour le chiffrement et le stockage
4. Rendu disponible pour la consommation par Nyroxis Intelligence

Cette normalisation garantit une évaluation cohérente des règles pour tous les types d'événements.

---

## Collecte sécurisée et chiffrement immédiat

Chaque événement collecté par le collecteur est :
- Chiffré instantanément avec AES-256
- Stocké sous forme chaînée par hachage résistante aux manipulations
- Indexé avec des horodatages et des métadonnées
- Jamais écrit sur le disque en texte clair

---

## Implémentation légère

Le Collecteur d'événements est optimisé pour :
- Une surcharge CPU minimale (~0,1 %)
- Une faible utilisation de la mémoire (~57 Mo de RAM au total pour l'Agent)
- Aucun impact sur les tâches quotidiennes
- Un fonctionnement stable à long terme

---

## Hors ligne par conception

Le Collecteur d'événements fonctionne avec **zéro interaction cloud**.
Toute la surveillance, la normalisation, le chiffrement et le stockage s'effectuent localement — préservant la confidentialité de l'utilisateur même dans des environnements sensibles ou à air gap.

---

## Résumé

Le Collecteur d'événements est le fondement de la couche de visibilité de Nyroxis, capturant chaque activité importante liée à la sécurité tout en restant léger, chiffré et entièrement hors ligne.
