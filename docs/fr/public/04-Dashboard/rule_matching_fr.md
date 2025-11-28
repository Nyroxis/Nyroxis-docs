# Rule Matching — Correspondance de règles

Le module Rule Matching permet à Nyroxis d’identifier les événements correspondant à des règles de sécurité prédéfinies.  
Il apporte une logique de type SIEM aux appareils personnels — entièrement hors-ligne.

---

##  Objectif
Identifier :
- Comportements suspects  
- Schémas anormaux répétés  
- Combinaisons d’événements à risque  
- Indicateurs de compromission  

---

##  Types de règles

### **1. Règles de seuil**
Déclenchées lorsque quelque chose se produit trop souvent :
- Connexions échouées répétées  
- Tentatives d’élévation multiples  
- Modifications de fichiers en masse  

---

### **2. Règles de séquence**
Détectent des chaînes d’événements :
- Processus → réseau → persistance  
- Script → modification système  
- Processus inconnu → fichier sensible  

---

### **3. Règles temporelles**
Visent des modèles visibles uniquement sur une période :
- Escalade progressive de privilèges  
- Mouvement latéral lent  
- Tentatives échouées récurrentes  

---

### **4. Règles spécifiques**
Basées sur :
- Un fichier  
- Un processus  
- Une clé de configuration  

---

##  Évaluation
L’analyse compare les règles à :
- Métadonnées  
- Horodatage  
- Arbre de processus  
- Endpoints réseau  
- Sévérité  

Tout est local et en temps réel.

---

##  Détails des correspondances
Lors d’un déclenchement :
- Explication claire  
- Événements associés  
- Niveau de sévérité  
- Actions recommandées  
- Contexte détaillé  

---

##  Confidentialité
Aucune communication externe :
- Correspondances locales  
- Journaux chiffrés  
- Aucune transmission  

---

## Résumé
Rule Matching apporte une détection structurée de type SIEM aux appareils personnels — sans cloud.
