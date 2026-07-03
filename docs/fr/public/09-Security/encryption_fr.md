# Modèle de Chiffrement

Nyroxis met en œuvre un modèle de chiffrement strict et multicouche conçu pour garantir qu'**aucune donnée lisible ne touche jamais le disque**, et que tous les événements de sécurité restent protégés, privés et vérifiables.

---

## Objectifs Fondamentaux

Le chiffrement Nyroxis garantit :
- **Confidentialité** — personne ne peut lire les données utilisateur
- **Intégrité** — personne ne peut modifier les journaux sans être détecté
- **Isolation** — les données ne quittent jamais l'appareil
- **Zéro stockage en clair** — tout est chiffré à la capture
- **Fonctionnement hors ligne** — aucune clé ou serveur cloud requis

---

## 1. Chiffrement à la Capture des Événements

Chaque événement système est chiffré au moment où il est collecté par Nyroxis Agent.

Étapes :
1. L'événement est sérialisé en mémoire
2. Une clé spécifique à l'appareil est dérivée des identifiants matériels (HWID)
3. L'événement est chiffré avec AES-256
4. Seul le bloc chiffré est écrit dans le stockage

Aucun journal en clair n'est jamais écrit.

---

## 2. Base de Données Locale Chiffrée

Tous les journaux, résultats de détection, résultats IA et métadonnées sont stockés dans une base de données SQLite sécurisée.

Fonctionnalités :
- Pages de données chiffrées en AES-256
- Métadonnées chiffrées
- Blocs de stockage enchaînés par hachage
- Vérification de l'intégrité par enregistrement
- Aucune mise en cache en clair

La base de données ne peut pas être ouverte ou lue en dehors de Nyroxis, et ne peut pas être déchiffrée sur un autre appareil.

---

## 3. Déchiffrement en Mémoire Uniquement

Nyroxis déchiffre les enregistrements *uniquement lors de leur traitement* :
- Le moteur IA/ML déchiffre les lots d'événements dans la RAM pendant l'analyse
- Le Dashboard déchiffre uniquement ce qu'il doit afficher, en mémoire
- Rien n'est réécrit en clair
- Les tampons mémoire sont effacés après utilisation

Cela élimine le risque de récupération forensique de données en clair depuis le disque.

---

## 4. Clés Liées à l'Appareil

Les clés de chiffrement sont :
- Dérivées des identifiants matériels de l'utilisateur (HWID)
- Générées localement sur l'appareil
- Jamais stockées directement dans l'application
- Jamais transmises à aucun serveur

Même si le fichier de base de données est copié sur un autre appareil, il ne peut pas être déchiffré — il est lié au matériel d'origine.

---

## 5. Protection de l'Intégrité — Chaîne de Hachage

Chaque bloc chiffré contient :
- Le hash d'intégrité du contenu du bloc
- L'index de séquence des événements
- Le hash du bloc précédent

Cela forme une **chaîne de hachage** qui expose :
- La suppression de journaux — le hash-précédent du bloc suivant ne correspondra pas
- La modification de journaux — le hash du bloc ne correspondra pas
- Le réordonnancement des journaux — l'index de séquence sera incorrect
- L'injection de journaux — les vérifications de chaîne et de séquence échoueront

La falsification est immédiatement détectable.

---

## 6. Aucune Implication du Cloud

Nyroxis n'utilise pas :
- Les coffres-forts de clés cloud
- Les serveurs de clés distants
- L'activation en ligne
- Les systèmes de télémétrie

Tout le chiffrement, la dérivation de clés et la vérification de l'intégrité sont entièrement locaux.

---

## Résumé

Le chiffrement Nyroxis garantit :
- Zéro stockage en clair
- Conception chiffrée partout
- Clés locales liées à l'appareil
- Journaux inviolables enchaînés par hachage
- Déchiffrement en mémoire uniquement

Un modèle de chiffrement moderne conçu pour la sécurité personnelle et l'autonomie hors ligne complète.
