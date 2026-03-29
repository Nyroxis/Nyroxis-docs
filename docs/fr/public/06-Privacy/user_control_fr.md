# Contrôle utilisateur et transparence

Nyroxis est conçu pour donner aux utilisateurs un contrôle total sur leurs données de sécurité, le comportement du système et les paramètres de confidentialité.
Pas de processus cachés, pas de téléchargements en arrière-plan, pas de connexions cloud — tout est transparent et géré localement.

---

## Principes fondamentaux du contrôle utilisateur

Nyroxis garantit que les utilisateurs peuvent :
- Voir ce qui est surveillé
- Contrôler ce qui est stocké et pour combien de temps
- Réinitialiser ou supprimer des données à tout moment
- Vérifier que la plateforme fonctionne hors ligne
- Comprendre comment les décisions IA/ML sont prises

L'utilisateur garde toujours le contrôle.

---

## 1. Pas de collecte de données silencieuse

Nyroxis collecte **uniquement** ce qui est nécessaire à l'analyse de sécurité :
- Journaux de processus et de services
- Événements de connexion réseau
- Modifications du système de fichiers et du registre
- Actions de privilèges
- Entrées du journal des événements Windows

Aucun fichier personnel, photo, message, données de navigation ou identifiant n'est jamais collecté.
Tout ce qui est collecté est documenté dans cette documentation.

---

## 2. Réinitialisation complète des données

Les utilisateurs peuvent réinitialiser à tout moment depuis le tableau de bord :
- Journaux d'événements
- Résultats de détection et de corrélation
- Référence comportementale IA/ML
- Toutes les métadonnées

Une réinitialisation complète restaure Nyroxis à un état propre sans résidus.

---

## 3. Stockage local uniquement

Toutes les données sont :
- Stockées localement dans la base de données SQLite chiffrée
- Entièrement chiffrées (AES-256)
- Jamais transmises à l'extérieur
- Sous le contrôle exclusif de l'utilisateur

Les utilisateurs ne dépendent pas de comptes cloud, d'authentification en ligne ou de stockage distant.

---

## 4. IA/ML transparent

Le moteur IA/ML fournit :
- Un score d'anomalie clair avec classification de gravité
- Les caractéristiques contributives — les dimensions comportementales spécifiques qui ont conduit à la détection, avec les valeurs Z-score
- Des résumés de raisonnement basés sur des scénarios

Les décisions de l'IA sont conçues pour être compréhensibles et explicables — pas des boîtes noires.

---

## 5. Options de personnalisation

Les utilisateurs peuvent ajuster depuis la vue Paramètres :
- Chemin du fichier de base de données et emplacement de stockage
- Intervalle de rafraîchissement du tableau de bord
- Fenêtre de consultation par défaut pour les requêtes d'événements
- Limite d'échantillon par défaut
- Langue de l'interface : anglais, français, allemand
- Configuration du thème

Tous les paramètres sont locaux.

---

## 6. Contrôle des sauvegardes

Depuis la section Sauvegarde, les utilisateurs peuvent :
- Planifier des sauvegardes automatiques
- Effectuer des sauvegardes à la demande
- Consulter l'historique des sauvegardes avec horodatages et tailles de fichiers
- Toutes les sauvegardes sont chiffrées et stockées localement

---

## 7. Vérification du fonctionnement hors ligne

Le tableau de bord et Nyroxis System Guardian exposent des indicateurs permettant aux utilisateurs de vérifier :
- Aucune connexion réseau sortante depuis les processus Nyroxis
- Aucune télémétrie en arrière-plan
- Aucune dépendance cloud
- État des services Agent et Intelligence en temps réel

La confiance est mesurable — pas supposée.

---

## Résumé

Nyroxis donne aux utilisateurs un contrôle total sur leurs données, une transparence totale de ses opérations, et la capacité de gérer, réinitialiser, sauvegarder ou vérifier tout localement — sans dépendance cloud ni processus cachés.
