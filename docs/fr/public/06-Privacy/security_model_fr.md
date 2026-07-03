# Modèle de sécurité

Le modèle de sécurité Nyroxis garantit que toute la surveillance, la détection, l'analyse IA et le stockage des événements fonctionnent selon des principes stricts de priorité à la vie privée et de résistance aux altérations.
Ce modèle est conçu pour les particuliers, les professionnels et les cadres qui nécessitent une sécurité fiable sans sacrifier la confidentialité.

---

## Objectifs fondamentaux

Nyroxis protège :
- La confidentialité des données — pas d'accès non autorisé aux journaux d'événements
- L'intégrité du système — chaîne de preuves résistante aux altérations
- La vie privée des utilisateurs — pas de transmission cloud, pas de profilage comportemental
- La résilience de la plateforme — surveillance continue, protégée contre les interférences

Le résultat : une protection de niveau entreprise sur un appareil personnel.

---

## 1. Chiffrement local de bout en bout

Toutes les données d'événements sont :
- Chiffrées au moment de la capture (AES-256)
- Stockées uniquement sous forme chiffrée — jamais écrites en clair
- Accessibles uniquement via des chemins de lecture sécurisés
- Déchiffrées uniquement en mémoire lors du traitement

Les clés de chiffrement sont :
- Dérivées du matériel de l'appareil (HWID)
- Locales à l'appareil
- Jamais stockées dans l'application
- Jamais transmises à l'extérieur

---

## 2. Stockage résistant aux altérations

Nyroxis utilise des blocs d'événements à chaîne de hachage :
- Chaque bloc contient un hash du bloc précédent
- L'intégrité est vérifiée à chaque opération de lecture
- Toute suppression, modification, injection ou réordonnancement brise la chaîne et déclenche une alerte
- Des chemins d'écriture protégés empêchent les écritures partielles ou corrompues

Les attaquants ne peuvent pas modifier les journaux ni effacer leurs traces sans être détectés.

---

## 3. Résilience de la plateforme (Nyroxis System Guardian)

Nyroxis System Guardian surveille l'état opérationnel de Nyroxis Agent et Nyroxis Intelligence en continu.

Si l'un ou l'autre service est arrêté — par un crash, un événement système ou une interférence délibérée :
- Guardian détecte immédiatement la perturbation
- Une action corrective est prise
- La tentative d'arrêt est enregistrée comme un événement de sécurité

La plateforme ne peut pas être désactivée silencieusement.

---

## 4. Moteur IA/ML local

Le moteur IA/ML :
- Fonctionne entièrement hors ligne
- Traite uniquement les données d'événements chiffrées localement
- Génère des détections d'anomalies et des résultats statistiques localement
- N'envoie jamais de données à des serveurs
- Ne télécharge jamais de profils comportementaux ou de retours de modèles

Vos données restent sur votre appareil, toujours.

---

## 5. Fonctionnement entièrement hors ligne

Nyroxis ne nécessite pas :
- Traitement ou stockage cloud
- Authentification en ligne
- APIs externes
- Serveurs distants de quelque nature que ce soit

Cela supprime des catégories entières de risques pour la vie privée — violations cloud, accès tiers et attaques réseau contre la plateforme de sécurité elle-même.

---

## 6. Rétention minimale des données

Nyroxis stocke uniquement :
- Événements de sécurité chiffrés
- Résultats de détection et de corrélation
- Résultats d'analyse IA/ML
- Métadonnées nécessaires à la détection et à la forensique

Il ne stocke **pas** :
- Documents personnels ou fichiers
- Historique de navigation
- Identifiants ou mots de passe
- Données de localisation
- Tout contenu non lié aux événements de sécurité

---

## 7. Logique transparente

Le modèle de sécurité est intentionnellement simple et vérifiable :
- Collecte locale → chiffrement local → détection locale → IA locale → alertes locales
- Pas de téléchargements silencieux, pas de télémétrie, pas de connexions réseau cachées

Les utilisateurs peuvent vérifier le comportement de la plateforme via le tableau de bord et la surveillance réseau du système.

---

## Résumé

Nyroxis fournit un modèle de sécurité robuste, axé sur la confidentialité et forensiquement solide :
- Stockage d'événements chiffré AES-256
- Protection anti-altération à chaîne de hachage
- IA/ML local uniquement
- Gardien de plateforme pour la résilience
- Pas de risques cloud, pas de télémétrie, pas de dépendances externes
