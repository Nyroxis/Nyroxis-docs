# Mode hors ligne

Nyroxis est conçu de fond en comble pour fonctionner entièrement hors ligne — sans nécessiter d'accès au cloud, d'authentification à distance ou d'API externes.
Cette conception offre aux utilisateurs sécurité, confidentialité et pleine autonomie sur leur appareil.

---

## Pourquoi le mode hors ligne est important

Fonctionner hors ligne garantit :
- **Aucune donnée ne quitte l'appareil** — jamais
- **Aucune exposition aux violations cloud** ni aux défaillances d'infrastructures tierces
- **Aucune dépendance envers des serveurs externes** pour la surveillance ou la détection
- **Aucun risque de surveillance tierce** ou de profilage comportemental
- **Fonctionnalité complète même sans internet** — y compris dans les environnements à isolation physique (air-gapped)

Les utilisateurs conservent un contrôle total sur leurs données de sécurité.

---

## 1. Fonctionnement entièrement local

Chaque fonction de la plateforme Nyroxis fonctionne localement :
- Collecte et normalisation des événements (Nyroxis Agent)
- Détection, corrélation et évaluation des règles de chaîne (Nyroxis Intelligence)
- Surveillance des services, sauvegarde et validation de licence (Nyroxis System Guardian)
- Détection d'anomalies IA/ML et analyse statistique
- Visualisation du tableau de bord et reporting

Rien n'est téléchargé. Rien n'est transmis.

---

## 2. Pas de cloud, pas de serveurs

Nyroxis n'utilise pas :
- Traitement ou stockage cloud
- Télémétrie ou suivi d'utilisation
- Journalisation à distance
- Analyse en ligne ou flux de renseignements sur les menaces
- Services d'authentification externes

Cela élimine des catégories entières de risques pour la vie privée et les risques d'attaque.

---

## 3. Validation de licence hors ligne

Nyroxis System Guardian valide la licence basée sur le HWID entièrement hors ligne :
- Aucune connexion internet requise
- La validation utilise le chiffrement AES-GCM et la vérification HMAC localement
- L'intégrité de la licence est appliquée sans contacter de serveur externe

---

## 4. Moteur IA/ML local

Le moteur Isolation Forest et d'analyse statistique fonctionne entièrement hors ligne :
- Détection d'anomalies comportementales
- Classification Z-Score
- Détection de pics et comparaison de référence

Tout est calculé directement à partir des événements locaux chiffrés — pas d'inférence cloud, pas de mises à jour de modèles via le réseau.

---

## 5. Vérification des mises à jour (optionnel)

Nyroxis System Guardian peut vérifier les mises à jour à des intervalles configurables.
L'installation des mises à jour reste manuelle — il n'y a pas de connexions cloud forcées ou automatiques.
La plateforme fonctionne à pleine capacité indépendamment du statut des mises à jour.

---

## 6. Architecture transparente

Nyroxis expose des indicateurs clairs dans le tableau de bord qui permettent aux utilisateurs de vérifier :
- Aucune connexion réseau sortante depuis les processus Nyroxis
- Aucune télémétrie en arrière-plan
- Aucune dépendance cloud

La confiance est mesurable — pas supposée.

---

## Résumé

Le mode hors ligne garantit que Nyroxis reste privé, chiffré, autonome et entièrement local — une plateforme de sécurité conçue pour protéger les utilisateurs sans jamais exposer leurs données.
