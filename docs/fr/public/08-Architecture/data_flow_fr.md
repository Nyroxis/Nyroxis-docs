# Flux de données — Vue d’ensemble

Cette section décrit le parcours des données dans Nyroxis — de la collecte à l’analyse IA — tout en restant totalement chiffrées, locales et privées.

---

##  1. Capture des événements (Agent Nyroxis)

L’agent surveille :
- Processus  
- Réseau  
- Fichiers  
- Actions de privilèges  

Chaque événement est capturé **en temps réel**, puis :
- Sérialisé  
- Chiffré immédiatement  
- Préparé pour le stockage  

Aucune donnée en clair n’est écrite.

---

##  2. Stockage chiffré (Base locale)

Les événements chiffrés sont stockés dans :
- La base de données sécurisée  
- Les blocs hash‑chaînés  
- Des chemins d’écriture protégés  

Chaque entrée contient :
- Horodatage  
- Charge utile chiffrée  
- Hash d’intégrité  
- Métadonnées IA  

Rien n’est envoyé en ligne.

---

##  3. Analyse IA locale (NyXIA)

NyXIA lit les événements :
- Toujours chiffrés à l’arrêt  
- Déchiffrés uniquement en mémoire  
- Analysés localement  

Elle réalise :
- Extraction comportementale  
- Regroupement en séquences  
- Scores d’anomalie  
- Détection de scénarios  

Sans cloud, sans télémétrie.

---

## ️ 4. Moteur de règles

En parallèle, le moteur analyse :
- Fréquences  
- Seuils  
- Motifs  
- Indices de corrélation  

Complémentaire à l’IA.

---

##  5. Affichage (Dashboard)

Le tableau de bord affiche :
- Résumés déchiffrés en mémoire  
- Résultats IA  
- Corrélations  
- Alertes  

Tout est local.

---

##  6. Actions utilisateur
L’utilisateur peut :
- Rechercher  
- Effacer les données  
- Ajuster les seuils  
- Exporter des sauvegardes chiffrées (à venir)  

---

##  Confidentialité par conception
À chaque étape :
- Aucun cloud  
- Aucune télémétrie  
- Aucun accès externe  
- Aucune dépendance réseau  

---

##  Résumé
Flux Nyroxis :
1. Capture → chiffrement  
2. Stockage sécurisé  
3. Analyse IA locale  
4. Affichage local  
5. Zéro cloud, zéro fuite  
