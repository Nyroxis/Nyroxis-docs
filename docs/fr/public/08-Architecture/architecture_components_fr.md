# Composants de l’architecture

Cette section décrit les composants essentiels de la plateforme Nyroxis et leur rôle dans une sécurité privée, hors‑ligne et résistante à la falsification.

---

##  1. Agent Nyroxis
Service léger en arrière‑plan qui :
- Surveille les processus  
- Analyse les connexions réseau  
- Suit les modifications de fichiers  
- Observe les actions de privilèges  
- Capture les événements système  

Tous les événements sont **chiffrés immédiatement**.

Optimisé pour :
- Une faible consommation  
- Un fonctionnement discret  
- Une autonomie hors‑ligne  

---

##  2. Base de données locale sécurisée
Stocke :
- Journaux d’événements  
- Métadonnées  
- Profils comportementaux  
- Index de corrélation  

Sécurisée par :
- Chiffrement AES  
- Vérification d’intégrité  
- Hash‑chaining  
- Aucun stockage en clair  

La base reste **strictement locale**.

---

##  3. Moteur IA NyXIA
Moteur IA hors‑ligne assurant :
- Détection comportementale  
- Génération de scénarios  
- Scores de risque  
- Analyse de séquences  

Sans cloud, sans télémétrie, sans connexion réseau.

---

## ️ 4. Moteur de règles
Utilisé pour :
- Détection de motifs  
- Comptage de fréquences  
- Alertes basées sur seuils  
- Support de corrélations  

Complète l’IA avec une logique transparente.

---

##  5. Tableau de bord
Propose :
- Visualisation  
- Recherche  
- Analyses IA  
- Graphiques  
- Réglages  

Toutes les données viennent de la base locale sécurisée.

---

##  6. Couche de sécurité
Chaque composant bénéficie de :
- Chiffrement local  
- Vérification d’intégrité  
- Aucune communication cloud  
- Mécanismes anti‑tamper  

---

##  Résumé
Les composants Nyroxis forment un écosystème hors‑ligne, privé et sécurisé — aucune donnée n’est exposée.
