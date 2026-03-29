# Flux de Données — Vue d'Ensemble de Haut Niveau

Cette section explique comment les données circulent à l'intérieur de Nyroxis — de la collecte des événements à l'analyse IA et à l'affichage dans le Dashboard — tout en restant entièrement chiffrées, hors ligne et privées à chaque étape.

---

## 1. Capture des Événements (Nyroxis Agent)

Le flux commence avec Nyroxis Agent qui surveille :
- Les processus et services
- Les connexions réseau et les métadonnées de trafic
- Les opérations du système de fichiers et les modifications du registre
- Les actions de privilèges
- Les entrées du journal d'événements Windows (Sécurité, Système, Application)
- L'exécution de PowerShell et des scripts

Chaque événement est capturé **en temps réel**.

Immédiatement après la capture :
- L'événement est normalisé et enrichi avec du contexte
- Chiffré à l'aide de la clé locale dérivée du HWID de l'appareil (AES-256)
- Préparé pour le stockage

Aucun texte en clair ne touche jamais le disque.

---

## 2. Stockage Chiffré (Base de Données Locale)

Une fois chiffrés, les événements sont écrits dans :
- La base de données SQLite locale sécurisée
- Les structures d'événements enchaînées par hachage
- Les chemins d'écriture protégés

Chaque entrée comprend :
- Horodatage
- Charge utile chiffrée
- Hash d'intégrité
- Index séquentiel lié au bloc précédent
- Métadonnées requises pour l'évaluation des règles et l'analyse IA

Toutes les données restent sur l'appareil de l'utilisateur — jamais synchronisées ni téléchargées.

---

## 3. Évaluation des Règles (Nyroxis Intelligence)

Nyroxis Intelligence lit depuis la base de données chiffrée et évalue les événements selon trois niveaux :
- **27 règles de détection** — correspondance de patterns d'événements individuels
- **12 règles de corrélation** — patterns multi-événements dans le temps et entre les sources
- **2 règles de chaîne** — détection de séquences d'attaques en plusieurs étapes

Lorsqu'une règle se déclenche :
- Une alerte est immédiatement générée
- Le résultat est écrit dans une base de données de détections dédiée
- L'utilisateur est notifié via le Dashboard

---

## 4. Traitement IA/ML Local

En parallèle, le moteur IA/ML lit les événements depuis la base de données :
- Déchiffrés uniquement en mémoire — jamais réécrits en clair
- Traités par l'algorithme Isolation Forest
- Évalués par les méthodes Z-Score, IQR et détection de pics

Résultats :
- Score d'anomalie (0,0–1,0)
- Classification de la sévérité
- Caractéristiques contributives avec valeurs Z-Score
- Mise à jour de la référence comportementale

Aucune partie de l'IA ne nécessite un accès au cloud ou une communication externe.

---

## 5. Affichage dans le Dashboard (Interface Utilisateur Locale)

Le Dashboard récupère uniquement :
- Des résumés déchiffrés en mémoire
- Les résultats de détection, corrélation et de chaîne
- Les résultats IA/ML avec décomposition des caractéristiques contributives
- Les graphiques et données de tendance

Tout le rendu de l'interface s'effectue localement sans communication externe.

---

## 6. Actions Utilisateur

Les utilisateurs peuvent :
- Rechercher dans les journaux chiffrés (déchiffrés en mémoire lors de la recherche)
- Exporter les résultats au format PDF ou CSV
- Effacer ou réinitialiser les données à tout moment
- Gérer les opérations de sauvegarde depuis la section Sauvegarde
- Ajuster les paramètres et la rétention depuis la vue Paramètres

Toutes les actions restent locales et privées.

---

## Confidentialité par Architecture

Chaque étape garantit :
- Aucune utilisation du cloud
- Aucune télémétrie
- Aucun accès à distance
- Aucune dépendance en ligne

Nyroxis maintient une confidentialité totale par l'architecture — pas seulement par la configuration.

---

## Résumé

```
Événement capturé   →  chiffré immédiatement
Stocké en sécurité  →  enchaîné par hachage, protégé en intégrité
Évaluation des règles → 27 détection + 12 corrélation + 2 chaîne
Analyse IA/ML       →  Isolation Forest + moteur statistique
Affiché localement  →  dashboard, forensique, rapports
Aucun cloud         →  aucun téléchargement, aucune exposition, jamais
```
