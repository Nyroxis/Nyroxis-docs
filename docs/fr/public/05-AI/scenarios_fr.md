# Scénarios IA

Les Scénarios IA représentent des situations de sécurité pré-définies que NyXIA peut identifier à partir de comportements, séquences et anomalies.  
Ils apportent une compréhension contextuelle des risques.

---

##  Objectif
Les scénarios expliquent *pourquoi* une détection est importante en regroupant plusieurs signaux dans un contexte cohérent.

Ils permettent de comprendre :
- Le type de menace  
- La cause probable  
- Le lien entre les événements  
- L’impact réel potentiel  

---

##  Types de scénarios

### **1. Chaîne de processus suspecte**
Exemples :
- Processus inconnu → moteur de script  
- Script → modification → connexion réseau  
- Multiplication rapide de processus enfants  

Permet de détecter malware ou automatisations malveillantes.

---

### **2. Activité réseau non autorisée**
Déclenché en cas de :
- Connexions sortantes inhabituelles  
- Endpoints rares  
- Tentatives répétées échouées  

Peut indiquer exfiltration ou beaconing.

---

### **3. Activité fichier anormale**
Inclut :
- Accès inattendu à des fichiers sensibles  
- Modifications massives  
- Corrélation avec des comportements suspects  

---

### **4. Tentative d’élévation de privilèges**
Signaux :
- Appels système rares  
- Répétition anormale d’actions élevées  
- Activité incohérente avec l’usage normal  

---

### **5. Indicateur de persistance**
Survient lorsque :
- Un processus modifie des zones de démarrage  
- Crée des tâches planifiées  
- Change la configuration système  

---

### **6. Intrusion lente**
Détecte :
- Escalade progressive  
- Activité périodique rare  
- Étapes espacées sur plusieurs heures/jours  

---

##  Rapport d’un scénario
Comprend :
- Description  
- Événements liés  
- Explication séquentielle  
- Sévérité  
- Interprétation  
- Recommandations  

---

##  Interprétation locale
Toute l’analyse :
- Se fait hors-ligne  
- Avec données chiffrées  
- Sans cloud  
- Respecte la vie privée  

---

## Résumé
Les Scénarios IA donnent du sens aux anomalies en identifiant des schémas d’attaque réels — tout en restant 100% locaux.
