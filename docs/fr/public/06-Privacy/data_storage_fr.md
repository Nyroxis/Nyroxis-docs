# Stockage sécurisé des données

Nyroxis ne stocke que le minimum de données nécessaires pour fournir des informations de sécurité — et toutes les données stockées sont entièrement chiffrées, locales et résistantes aux altérations.
Cela garantit la confidentialité des particuliers, des familles et des professionnels qui font confiance à Nyroxis pour une protection réelle sans exposition.

---

## Ce que Nyroxis stocke

Nyroxis conserve **uniquement les informations liées à la sécurité** :

### 1. Journaux d'événements
Entrées chiffrées pour :
- Activité des processus
- Connexions réseau
- Modifications de fichiers et du registre
- Actions de privilèges
- Entrées du journal système et du journal des événements Windows

### 2. Résultats de détection et de corrélation
Résultats de l'évaluation des règles Nyroxis Intelligence :
- Résultats de détection (27 règles)
- Résultats de corrélation (12 règles)
- Résultats de chaîne (2 règles)

### 3. Résultats d'analyse IA/ML
Sortie du moteur local Isolation Forest et du moteur statistique :
- Scores d'anomalie et classifications de gravité
- Décompositions des caractéristiques contributives
- Données de référence comportementale

### 4. Métadonnées pour l'analyse
Métadonnées légères nécessaires pour :
- Correspondance de règles et corrélation
- Construction de la référence comportementale IA
- Reconstruction de la chronologie

---

## Ce que Nyroxis ne stocke PAS

Nyroxis évite délibérément de collecter ou de sauvegarder du contenu personnel ou sensible.

Il ne stocke **PAS** :
- Documents personnels ou fichiers de projet
- Images ou vidéos
- Historique de navigation
- Données de localisation
- Mots de passe ou identifiants
- Contenu des fichiers
- Messages ou e-mails des utilisateurs
- Toute donnée non liée aux événements de sécurité

Seules les données techniques orientées sécurité sont conservées.

---

## Modèle de chiffrement

Toutes les données stockées sont :
- Chiffrées au moment de la capture (AES-256)
- Enregistrées uniquement sous forme chiffrée — jamais écrites en clair
- Déchiffrées uniquement en mémoire lors des opérations de lecture
- Protégées par des structures d'intégrité à chaîne de hachage

Les clés de chiffrement sont :
- Locales à l'appareil
- Dérivées des identifiants matériels (HWID)
- Jamais intégrées dans l'application
- Jamais transmises aux serveurs

---

## Structures résistantes aux altérations

Nyroxis utilise des blocs d'événements à chaîne de hachage où chaque bloc contient :
- Charge utile chiffrée
- Hash d'intégrité
- Index séquentiel
- Lien vers le bloc précédent

Cela rend toute altération immédiatement détectable :
- La suppression, la modification, l'injection ou le réordonnancement brise la chaîne
- Toute discordance est signalée comme un événement de sécurité

---

## Conservation des données

Les utilisateurs ont un contrôle total sur leurs données :
- Réinitialiser les journaux à tout moment
- Effacer la référence comportementale IA
- Gérer la durée de conservation depuis la vue Paramètres
- Exporter des sauvegardes chiffrées depuis la section Sauvegarde

---

## Stockage entièrement local

Tout le stockage est :
- Local uniquement sur l'appareil de l'utilisateur
- Entièrement hors ligne
- Chiffré AES-256
- Aucun téléchargement cloud — jamais

Vos données de sécurité restent sur votre machine — toujours.

---

## Résumé

Nyroxis ne stocke que des informations chiffrées, minimales et axées sur la sécurité — jamais de contenu personnel — garantissant une véritable confidentialité et une protection de qualité forensique pour chaque utilisateur.
