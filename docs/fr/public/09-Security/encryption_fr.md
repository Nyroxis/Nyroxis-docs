# Modèle de chiffrement

Nyroxis applique un modèle de chiffrement strict conçu pour garantir qu’aucune donnée en clair n’est jamais stockée et que tous les événements restent protégés, privés et vérifiables.

---

##  Objectifs principaux
Le chiffrement Nyroxis garantit :

- **Confidentialité**  
- **Intégrité**  
- **Isolation locale**  
- **Aucune donnée en clair**  
- **Fonctionnement hors‑ligne**  

---

##  1. Chiffrement lors de la capture
Chaque événement est chiffré **dès sa collecte**.

Étapes :
1. Sérialisation en mémoire  
2. Chargement d’une clé dérivée localement  
3. Chiffrement AES  
4. Stockage uniquement du bloc chiffré  

Aucune trace en clair.

---

##  2. Base locale chiffrée
Base sécurisée contenant :

- Pages AES chiffrées  
- Métadonnées chiffrées  
- Hash‑chaining  
- Vérification d’intégrité  
- Aucun cache en clair  

Impossible à lire en dehors de Nyroxis.

---

##  3. Déchiffrement uniquement en mémoire
Utilisé uniquement par :
- NyXIA (analyse)  
- Tableau de bord (visualisation)  

Les données sont :
- Déchiffrées en RAM  
- Non écrites en clair  
- Effacées après traitement  

---

##  4. Clés liées à l’appareil
Générées à partir de :
- Identifiants matériels  
- Sels locaux  
- Secrets divisés  

Jamais stockées, jamais transmises.

---

##  5. Protection d’intégrité
Chaque bloc contient :
- Hash d’intégrité  
- Marqueur de séquence  
- Lien vers le bloc précédent  

Permet de détecter :
- Suppression  
- Modification  
- Réinsertion  
- Réordonnancement  

---

##  6. Aucun cloud
Pas de :
- Vault distant  
- API externe  
- Activation en ligne  
- Télémétrie  

---

##  Résumé
Un modèle moderne :
- Chiffrement complet  
- IA locale  
- Logs protégés  
- Clés locales  
- Respect total de la vie privée  
