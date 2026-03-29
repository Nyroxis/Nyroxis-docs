# Noyau de protection

Le Noyau de protection est l'épine dorsale de sécurité du Nyroxis Agent.
Il renforce l'intégrité de la surveillance, garantit un traitement chiffré des événements et empêche les attaquants de manipuler les journaux ou de désactiver la plateforme.

Sa conception suit des principes stricts axés sur la confidentialité et le mode hors ligne.

---

## Objectifs fondamentaux

Le Noyau de protection garantit :
- Les événements de sécurité ne peuvent être modifiés ou supprimés sans être détectés
- Les journaux restent chiffrés de la source au stockage
- La plateforme ne peut pas être désactivée silencieusement
- Les composants sensibles sont protégés contre les modifications non autorisées

Cela crée une confiance dans la couche de visibilité et forensique.

---

## 1. Chiffrement local de bout en bout

Chaque événement capturé par Nyroxis est :
- Chiffré immédiatement au moment de la capture
- Écrit sur le disque uniquement sous forme chiffrée (AES-256)
- Indexé avec des horodatages et des métadonnées
- Jamais stocké en texte clair

Le modèle de chiffrement empêche les attaquants de lire ou de modifier l'historique des événements.

---

## 2. Protection de l'intégrité — Blocs d'événements chaînés par hachage

Nyroxis stocke les événements dans une structure chaînée par hachage où chaque bloc contient :
- Charge utile chiffrée
- Hachage d'intégrité
- Index séquentiel
- Lien vers le bloc précédent

Cela rend toute manipulation immédiatement détectable :
- **Suppression** — le hachage précédent du bloc suivant ne correspondra pas
- **Modification** — le hachage du bloc modifié ne correspondra pas
- **Injection** — les numéros de séquence et les hachages de chaîne échoueront

Toute manipulation est signalée comme un événement de sécurité.

---

## 3. Protection du service de la plateforme

Nyroxis System Guardian est responsable de s'assurer que Nyroxis Agent et Nyroxis Intelligence restent en fonctionnement à tout moment.

Toutes les 3 secondes, Guardian vérifie l'état opérationnel des deux services. Si l'un ou l'autre service s'arrête de manière inattendue — en raison d'un événement système, d'un plantage ou d'une interférence délibérée — Guardian le détecte immédiatement et prend des mesures correctives.

Les tentatives d'arrêt sont enregistrées comme des événements de sécurité, préservant ainsi les preuves d'interférence.

---

## 4. Sécurité hors ligne

Le Noyau de protection ne nécessite jamais :
- Validation cloud
- APIs externes
- Serveurs distants

Toutes les vérifications d'intégrité et les validations s'effectuent **à 100 % hors ligne**.
La validation de licence fonctionne également entièrement hors ligne via le chiffrement AES-GCM et la vérification HMAC.

---

## 5. Interaction sécurisée avec le tableau de bord

Le tableau de bord accède aux données d'événements via :
- Des chemins de lecture sécurisés vérifiés
- Un accès en lecture seule aux journaux
- Une séparation stricte entre la visualisation et le stockage des événements

Cela empêche les attaques au niveau de la couche d'interface utilisateur de modifier les données réelles.

---

## Résumé

Le Noyau de protection — combiné avec Nyroxis System Guardian — garantit que la surveillance, le chiffrement et l'intégrité des événements restent fiables même dans des environnements hostiles, tout en maintenant toutes les données privées, locales et forensiquement fiables.
