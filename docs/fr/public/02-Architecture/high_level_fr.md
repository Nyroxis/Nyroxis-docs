# Vue d’ensemble de l’architecture

Nyroxis repose sur une architecture légère et centrée sur la confidentialité, offrant une visibilité de niveau entreprise sans dépendance au cloud.  
Tout fonctionne localement sur l’appareil de l’utilisateur.

---

##  Composants principaux

### **1. Nyroxis Agent**
Un moniteur léger qui :
- Collecte les événements de sécurité  
- Les chiffre et les stocke localement  
- Protège l’intégrité des journaux  
- Fonctionne 100% hors‑ligne  

### **2. Base de données locale chiffrée**
Les événements collectés sont enregistrés dans :
- Un stockage local sécurisé  
- Chiffré au repos  
- Optimisé pour l’analyse rapide  

### **3. Nyroxis Dashboard**
Interface claire permettant :
- Affichage des journaux et alertes  
- Graphiques et timelines  
- Explications et niveaux de sévérité  
- Utilisation par experts et débutants  

### **4. Moteur d’analyse local**
Inclut :
- Heuristiques comportementales  
- Scoring IA léger  
- Logique de corrélation  
Tout est traité **localement**.

### **5. Validation de licence (optionnelle)**
Nyroxis peut vérifier l’intégrité d’une licence sans envoyer les journaux.  
Aucune donnée sensible n'est transmise.

---

## 🔄 Flux de données (High-Level)

```
[ Événements système ]  
        ↓  
[ Nyroxis Agent ]  
        ↓ (chiffré)
[ Base locale chiffrée ]  
        ↓  
[ Moteur d’analyse ]  
        ↓  
[ Nyroxis Dashboard ]
```

Aucune donnée n’est envoyée vers l’extérieur.

---

##  Principes de conception

### **Confidentialité par conception**
- Pas d’ingestion cloud  
- Chiffrement local  
- Contrôle total par l’utilisateur  

### **Simplicité & clarté**
- Architecture propre  
- Facile à comprendre  
- Adaptée aux familles et professionnels  

### **Léger & efficace**
Fonctionne même sur des ordinateurs anciens.

### **Sécurité hors‑ligne**
Pas besoin d’internet pour :
- Le monitoring  
- L’analyse  
- Le dashboard  
- La corrélation  

---

## Résumé
Nyroxis apporte une architecture moderne, minimaliste et sécurisée — offrant une visibilité professionnelle aux appareils personnels, tout en restant entièrement locale.
