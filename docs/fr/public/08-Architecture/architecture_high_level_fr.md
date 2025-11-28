# Architecture — Vue d’ensemble

L’architecture Nyroxis fournit une sécurité forte, une confidentialité totale et une autonomie complète hors-ligne.  
Cette vue d’ensemble décrit comment les composants interagissent tout en protégeant les données localement.

---

##  Principes fondamentaux

### **1. Fonctionnement entièrement local**
Toutes les analyses et stockages sont réalisés sur l’appareil.

### **2. Confidentialité dès la conception**
Aucun cloud, aucune télémétrie, aucun envoi externe.

### **3. Légèreté**
Optimisé pour les appareils personnels et professionnels.

### **4. Résistance aux falsifications**
Logs chiffrés, baselines sécurisées, vérifications d’intégrité.

---

##  Composants principaux

### **1. Agent Nyroxis**
Collecte :
- Processus  
- Réseau  
- Fichiers  
- Actions de privilèges  

Chiffre immédiatement les événements.

---

### **2. Base de données locale sécurisée**
Stocke :
- Journaux chiffrés  
- Métadonnées  
- Profils comportementaux  

Toujours chiffrée et locale.

---

### **3. Moteur IA NyXIA**
Assure :
- Détection comportementale  
- Analyse des scénarios  
- Scores d’anomalie  

Fonctionne hors-ligne.

---

### **4. Moteur de règles**
Fournit :
- Détection de motifs  
- Alertes basées sur seuils  
- Corrélations simples  

Complémentaire au moteur IA.

---

### **5. Tableau de bord**
Affiche :
- Journaux  
- Alertes  
- Scénarios  
- Analyses IA  

Permet la gestion locale des réglages.

---

##  Couches de sécurité
- Chiffrement à la capture  
- Stockage chiffré  
- Hash-chaining  
- IA hors-ligne  
- Vérifications anti-tamper  

---

##  Résumé
Une architecture privée, locale, légère et puissante — sans cloud.