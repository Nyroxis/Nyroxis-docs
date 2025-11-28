# Protection Core — Cœur de protection

Le Cœur de protection constitue l’ossature de sécurité du Nyroxis Agent.  
Il garantit l’intégrité de la surveillance, protège les journaux et empêche toute tentative de manipulation par un attaquant.

---

##  Objectifs principaux
Le Cœur de protection assure :
- L’impossibilité de modifier les événements  
- Le chiffrement complet des journaux  
- La difficulté de désactiver l’Agent  
- La protection des composants sensibles  

---

##  1. Chiffrement local de bout en bout
Chaque événement est :
- Chiffré immédiatement  
- Écrit uniquement sous forme chiffrée  
- Indexé avec horodatage et métadonnées  
- Jamais stocké en clair  

Le modèle garantit confidentialité et intégrité.

---

##  2. Protection d’intégrité (Anti-tamper)
Nyroxis applique :
- Des chemins d’écriture protégés  
- Hashing & vérification des blocs  
- Surveillance de ses propres fichiers critiques  
- Alertes en cas de modification suspecte  

---

##  3. Auto‑protection de l’Agent
Le Cœur de protection empêche la désactivation silencieuse de l’Agent.

Il inclut :
- Surveillance de l’état d’exécution  
- Détection d’arrêts inattendus  
- Redémarrage automatique  
- Journalisation des tentatives d’arrêt  

---

##  4. Sécurité hors-ligne
Aucun besoin de :
- Validation cloud  
- API externe  
- Serveur distant  

Tout est vérifié localement.

---

##  5. Interaction sécurisée avec le Dashboard
Le Dashboard accède aux données via :
- Des chemins de lecture vérifiés  
- Accès en lecture seule  
- Une séparation stricte entre stockage et interface  

---

## Résumé
Le Cœur de protection garantit l’intégrité, le chiffrement et la fiabilité de la surveillance — même en environnement hostile — tout en restant 100% local.
