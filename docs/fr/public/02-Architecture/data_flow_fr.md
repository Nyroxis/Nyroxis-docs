# Flux de données

Cette section explique comment les données circulent dans Nyroxis — de la collecte des événements jusqu’à leur interprétation par l’utilisateur — tout en restant entièrement locales et chiffrées.

Nyroxis suit un cycle simple et transparent, orienté confidentialité.

---

##  1. Collecte des événements
Le Nyroxis Agent surveille en continu :
- Processus  
- Connexions réseau  
- Modifications de fichiers  
- Actions liées aux privilèges  
- Événements système & sécurité  

Toutes les données sont collectées **localement**, sans interaction cloud.

---

##  2. Chiffrement à la source
Dès la collecte :
- Les événements sont chiffrés  
- L’intégrité est protégée  
- Les données deviennent résistantes à la falsification  

Aucun attaquant ne peut lire ou modifier les journaux.

---

##  3. Base de données locale chiffrée
Les événements chiffrés sont stockés dans une base sécurisée.

Caractéristiques :
- Chiffrement complet  
- Stockage structuré  
- Optimisée pour les recherches rapides  
- Aucune transmission externe  

La base ne quitte jamais l’appareil.

---

##  4. Moteur d’analyse local
Le moteur analyse les données localement pour produire :
- Insights comportementaux  
- Détection d’anomalies  
- Scoring IA  
- Corrélation d’événements  

Aucun serveur externe n’intervient.

---

##  5. Visualisation dans le Dashboard
Le Nyroxis Dashboard convertit les données techniques en :
- Journaux  
- Alertes  
- Graphiques & tendances  
- Indicateurs de sévérité  
- Explications simples  

Tout reste local.

---

##  Diagramme du cycle de données

```
[ Événements système ]
        ↓
[ Nyroxis Agent ]
        ↓ (chiffré)
[ Base locale chiffrée ]
        ↓
[ Moteur d’analyse ]
        ↓
[ Dashboard ]
```

---

## Résumé
Nyroxis garantit un flux de données strictement local, chiffré et respectueux de la confidentialité — offrant visibilité et sécurité sans exposer les informations de l’utilisateur.
