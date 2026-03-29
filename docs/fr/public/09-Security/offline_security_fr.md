# Sécurité Hors Ligne

Nyroxis est conçu pour fonctionner entièrement hors ligne sans aucune dépendance aux services cloud, aux API externes ou aux serveurs distants.
Cela garantit une autonomie complète, une confidentialité totale et une protection même dans des environnements déconnectés ou en mode air-gap.

---

## 1. Aucune Communication Cloud

Nyroxis ne :
- Envoie jamais de télémétrie ou de données d'utilisation
- Synchronise jamais les journaux avec des serveurs distants
- Contacte jamais des services cloud pour quelque fonction que ce soit
- Utilise jamais l'IA cloud ou des API ML externes
- Nécessite jamais une activation en ligne

Chaque fonction est locale.

---

## 2. Gestion des Clés Locale Uniquement

Les clés de chiffrement sont :
- Dérivées localement des identifiants matériels (HWID)
- Liées à l'appareil spécifique
- Jamais transmises à aucun serveur
- Jamais stockées en clair
- Reconstruites uniquement en mémoire lorsque nécessaire

Toutes les opérations cryptographiques s'effectuent hors ligne.

---

## 3. Validation de Licence Hors Ligne

Nyroxis System Guardian valide la licence entièrement hors ligne :
- Licence liée à la clé cryptographique dérivée du HWID
- La validation utilise le chiffrement AES-GCM et la vérification HMAC localement
- Aucune connexion Internet requise pour quelque aspect que ce soit de la gestion des licences
- Les services s'arrêtent automatiquement si la licence est invalide — appliqué localement

---

## 4. Moteur IA/ML Hors Ligne

L'Isolation Forest et le moteur d'analyse statistique fonctionnent entièrement hors ligne :
- Détection d'anomalies comportementales
- Classification statistique Z-Score
- Détection de pics et comparaison avec les références

Tout est calculé directement à partir des événements locaux chiffrés — aucune inférence cloud, aucun accès réseau.

---

## 5. Stockage Chiffré Local

Tous les journaux d'événements, résultats de détection et résultats IA restent :
- Entièrement chiffrés (AES-256)
- Stockés dans une base de données locale protégée
- Accessibles uniquement sur le même appareil
- Protégés par des structures d'intégrité enchaînées par hachage

Aucun risque de violation à distance ou de fuite cloud.

---

## 6. Aucune Récupération Externe

Nyroxis ne télécharge pas :
- Les règles de détection ou leurs mises à jour
- Les modèles IA ou leurs mises à jour
- Les signatures ou flux de renseignements sur les menaces

Tout est intégré et géré localement. Les mises à jour des règles s'effectuent par installation manuelle.

---

## 7. Fonctionne dans les Environnements Air-Gap

Nyroxis fonctionne parfaitement sur :
- Les ordinateurs portables entièrement hors ligne
- Les environnements d'entreprise isolés
- Les configurations gouvernementales à haute sécurité
- Les lieux à haut risque sans accès Internet

Les fonctionnalités complètes ne nécessitent **aucune connectivité**.

---

## Résumé

La sécurité hors ligne de Nyroxis garantit :
- Autonomie totale — aucune dépendance à une infrastructure externe
- Zéro exposition au cloud
- IA/ML local uniquement
- Stockage chiffré privé
- Indépendance complète vis-à-vis de la connectivité Internet

Un modèle de sécurité conçu pour une confidentialité et un contrôle maximaux.
