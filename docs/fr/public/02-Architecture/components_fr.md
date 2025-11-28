# Composants de l’architecture

Cette section détaille les principaux composants de l’écosystème Nyroxis.  
Tous les éléments fonctionnent localement, de manière efficace et avec une approche Privacy‑First.

---

##  1. Nyroxis Agent
Le service de surveillance principal exécuté sur l’appareil.

### Rôle
- Collecte les événements système et sécurité  
- Analyse processus, réseau, fichiers, privilèges  
- Chiffre les journaux immédiatement  
- Assure l’intégrité anti‑falsification  

### Propriétés
- Léger (faible consommation CPU/RAM)  
- Hors‑ligne par défaut  
- Fonctionne discrètement en arrière‑plan  

---

##  2. Base de données locale chiffrée

### Caractéristiques
- Chiffrement complet des données  
- Stockage structuré des événements  
- Protection d’intégrité  
- Optimisée pour les recherches rapides  

Aucun envoi cloud — l’utilisateur reste l’unique propriétaire des données.

---

##  3. Nyroxis Dashboard
Interface visuelle permettant de rendre les données lisibles.

### Fournit
- Visualisation de journaux (filtres, recherche)  
- Graphiques, niveaux de sévérité, résumés quotidiens  
- Corrélation et regroupement d’événements  
- Explications simples des actions suspectes  

### Public
Adapté aux non‑techniciens comme aux experts cybersécurité.

---

##  4. Moteur d’analyse local
Un moteur léger responsable de l’intelligence embarquée.

### Fonctions
- Heuristiques comportementales  
- Scoring IA  
- Corrélation d’événements  
- Détection de comportements suspects  

Tout est traité localement pour préserver la confidentialité.

---

##  5. Licence & Vérification (Local‑First)
Nyroxis peut vérifier une licence sans exposer les journaux.

### Points clés
- Échange de métadonnées minimal  
- Aucun journal envoyé  
- Fonctionne même hors‑ligne  

---

##  6. Intégrations optionnelles (Future‑Ready)

Modules futurs possibles :
- Synchronisation locale entre appareils  
- Sauvegarde chiffrée (initiée par l’utilisateur)  
- Packs de corrélation étendus  

Toujours optionnels et respectueux de la vie privée.

---

## Résumé
Nyroxis repose sur des composants modulaires, locaux et sécurisés — offrant une visibilité de niveau entreprise, en toute simplicité.
