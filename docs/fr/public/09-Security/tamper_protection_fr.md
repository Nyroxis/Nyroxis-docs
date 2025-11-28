# Protection contre la falsification

Nyroxis intègre des mécanismes avancés empêchant toute modification, suppression ou insertion de journaux — toute falsification est détectable immédiatement, sans cloud.

---

##  1. Blocs chaînés par hash
Chaque événement inclut :
- Données chiffrées  
- Hash d’intégrité  
- Index séquentiel  
- Lien vers le bloc précédent  

Ce mécanisme agit comme une **chaîne de blocs**.

Toute falsification brise la chaîne.

---

##  2. Vérification à la lecture
Lors de chaque lecture :
- Le hash est recalculé  
- L’index est vérifié  
- Le lien au bloc précédent est validé  

En cas d’échec :
- Données rejetées  
- Alerte de falsification  

---

##  3. Écriture protégée
L’agent utilise :
- Écriture atomique  
- Séquence vérifiée  
- Tampons chiffrés  

Empêche :
- Écritures partielles  
- Corruption  
- Injections  

---

##  4. Protection anti‑suppression
Si un bloc est supprimé :
- Le hash suivant ne correspond plus  
- Une alerte est générée  

---

##  5. Protection anti‑modification
Toute modification entraîne :
- Hash incorrect  
- Chaîne cassée  
- Incohérence d’index  

---

##  6. Protection anti‑injection
Les faux journaux échouent sur :
- Hash  
- Séquence  
- Intégrité  

---

##  Résumé
Les journaux Nyroxis sont :
- Inaltérables  
- Indélébiles  
- Vérifiables  
- Entièrement locaux et hors‑ligne  
