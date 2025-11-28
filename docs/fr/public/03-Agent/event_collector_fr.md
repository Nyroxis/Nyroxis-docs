# Event Collector — Collecteur d’événements

Le Collecteur d’événements est le sous‑système du Nyroxis Agent chargé de capturer toute l’activité liée à la sécurité sur l’appareil.  
Il est léger, privé et totalement hors‑ligne, tout en offrant une visibilité de niveau entreprise.

---

##  Objectif du Collecteur
Le Collecteur permet de comprendre :
- Ce qui se passe sur l’appareil  
- À quel moment les événements surviennent  
- Si l’activité est normale ou suspecte  

Le tout sans exposer les données.

---

##  Types d’événements surveillés

### **1. Événements de processus**
- Création de processus  
- Arrêt  
- Relations parent/enfant  
- Paramètres de commande (selon plateforme)

### **2. Événements réseau**
- Connexions sortantes et entrantes  
- IP/ports de destination  
- Type de protocole  
- Tentatives répétées suspectes  

### **3. Activité du système de fichiers**
- Création  
- Suppression  
- Modification  
- Accès à des répertoires sensibles  

### **4. Événements de privilège & sécurité**
- Tentatives d’élévation  
- Appels système sensibles  
- Modifications de configuration/registre  
- Accès à des ressources sensibles  

### **5. Événements système & bas‑niveau**
- Démarrage/arrêt de services  
- Chargement de pilotes  
- Avertissements système  
- Mécanismes potentiels de persistance  

---

##  Sécurisation & chiffrement immédiat
Chaque événement est :
- Chiffré instantanément  
- Stocké avec protection anti‑falsification  
- Indexé avec horodatage et métadonnées  

Aucun journal non chiffré n’est écrit sur le disque.

---

##  Implémentation légère
Le Collecteur est optimisé pour :
- Une faible utilisation CPU  
- Un minimum de mémoire  
- Aucune gêne pour l’utilisateur  
- Une stabilité longue durée  

---

##  Protection anti‑falsification
Pour empêcher toute manipulation :
- Vérifications d’intégrité  
- Chemins d’écriture sécurisés  
- Surveillance de fichiers critiques  

---

##  Fonctionnement hors‑ligne
Aucune interaction cloud.  
Toute la logique est locale — surveillance, chiffrement, stockage et analyse.

---

## Résumé
Le Collecteur d’événements constitue la base de la visibilité Nyroxis — capturant toute activité pertinente de manière chiffrée, légère et totalement locale.
