# Moteur IA — Mécanismes internes

Le moteur d’IA Nyroxis (NyXIA) fonctionne entièrement en local, analysant les événements de sécurité chiffrés sans aucun recours au cloud.  
Ce document présente son fonctionnement interne de manière simple et semi‑technique.

---

##  Principes fondamentaux

### **1. Confidentialité absolue**
- Aucun cloud  
- Aucune API externe  
- Aucune transmission de données  

### **2. IA légère**
Modèles optimisés pour :
- Faible usage CPU  
- Faible mémoire  
- Exécution en temps réel  

### **3. Analyse comportementale**
NyXIA détecte des *modèles* plutôt que des événements isolés.

### **4. Fonctionnement hors‑ligne**
Toutes les analyses sont locales.

---

##  Traitement interne

### **1. Réception des événements**
Le Nyroxis Agent collecte :
- Processus  
- Réseau  
- Fichiers  
- Privilèges  

Les événements arrivent chiffrés.

### **2. Construction de séquences**
Les événements sont regroupés :
```
w(t) = {event_t ... event_t+k}
```

### **3. Extraction de caractéristiques**
NyXIA extrait des informations clés :
- Arbre de processus  
- Modèles réseau  
- Activité fichiers  
- Anomalies temporelles  

### **4. Inférence locale**
Le moteur évalue :
- Score d’anomalie  
- Classe comportementale  
- Déviation du profil normal  

Tous les calculs sont locaux.

### **5. Cartographie des scénarios**
NyXIA identifie :
- Persistance  
- Activités réseau suspectes  
- Escalade de privilèges  
- Intrusion multi‑étapes  

---

##  Profil comportemental local
NyXIA construit un profil :
- Processus habituels  
- Connexions typiques  
- Activités normales  

Stocké et chiffré localement.

---

##  IA éthique
NyXIA :
- Ne trace pas  
- N’apprend pas dans le cloud  
- Ne collecte aucune donnée personnelle  

---

## Résumé
NyXIA combine confidentialité totale et détection comportementale avancée, sans dépendre du cloud.