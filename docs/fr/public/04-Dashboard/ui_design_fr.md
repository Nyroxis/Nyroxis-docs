# Conception de l'interface du tableau de bord

Le tableau de bord Nyroxis est conçu pour donner aux utilisateurs — qu'ils soient non techniques ou professionnels — une vue claire, intuitive et exploitable de l'état de sécurité de leur appareil.
Sa conception suit des principes de clarté, de minimalisme, de confidentialité et de conscience en temps réel.

---

## Philosophie de conception

### La clarté avant la complexité
Les données de sécurité ne doivent jamais submerger l'utilisateur.
Le tableau de bord transforme les journaux bruts en insights lisibles avec des mises en page épurées, des indicateurs de gravité codés par couleur et des explications simples.

### Visualisation axée sur la confidentialité
Toutes les données affichées dans le tableau de bord :
- Proviennent du stockage local chiffré
- Ne quittent jamais l'appareil
- Sont traitées entièrement hors ligne

### UX cohérente pour tous les profils
L'interface sert aussi bien les cadres non techniques, les professionnels juridiques, les familles que les analystes en cybersécurité — chacun reçoit la même mise en page propre et structurée.

---

## Sections principales du tableau de bord

### 1. Vue d'ensemble principale
Le point d'entrée — fournit une vue instantanée de la posture de sécurité actuelle :
- Total des événements collectés dans les dernières 24 heures
- Alertes actives par gravité : Critique, Élevé, Avertissement, Info
- Chronologie des événements en temps réel
- Graphique de répartition par gravité
- État du système : état de l'agent, taille de la base de données, santé du moteur de règles, validité de la licence, état de sauvegarde

### 2. Événements
Le cœur forensique du tableau de bord :
- Accès complet à la base de données d'événements bruts
- Recherche dans tous les champs d'événements : source, canal, gravité, contenu
- Filtrage par plage temporelle, gravité, source et canal
- Inspection forensique des événements individuels avec détail complet de la charge utile
- Export en CSV pour documentation légale

### 3. Détection
Tous les résultats de la couche de détection à 27 règles de Nyroxis Intelligence :
- Règle ayant déclenché l'alerte
- Événements spécifiques qui ont correspondu
- Classification de gravité et horodatage
- Lien direct vers les événements bruts sous-jacents pour une analyse forensique approfondie

### 4. Corrélation
Résultats du moteur de corrélation à 12 règles :
- Modèles qui émergent des relations entre événements au fil du temps
- Fenêtre temporelle et cartographie des sources
- Là où les signaux isolés deviennent des renseignements exploitables

### 5. Chaîne
Résultats de la couche de détection de chaîne à 2 règles :
- Détection de séquences d'attaques en plusieurs étapes
- Alertes de la plus haute priorité dans le système
- Reconstruction complète de la séquence d'attaque détectée

### 6. Rapports
Documentation structurée et exportable :
- Fenêtres temporelles configurables
- Export en PDF et CSV
- Approprié pour révision interne, soumission réglementaire ou procédures légales

### 7. Analyse IA / ML
Accès au moteur d'apprentissage automatique local :
- Résultats de détection d'anomalies avec décomposition des caractéristiques contributives
- Classifications Z-Score : Critique / Élevé / Moyen / Faible
- Suivi de l'évolution de la ligne de base comportementale
- Identification des valeurs aberrantes statistiques et des pics
- Toutes les analyses effectuées localement — aucune donnée ne quitte l'appareil

### 8. Paramètres
Configuration complète de la plateforme :
- Chemin du fichier de base de données et gestion du stockage
- Intervalle d'actualisation du tableau de bord
- Fenêtre de consultation par défaut et limite d'échantillons
- Sélection de la langue de l'interface : Anglais, Français, Allemand
- Configuration du thème
- Affichage de l'ID matériel pour référence de licence

### 9. Sauvegarde
Gestion directe des opérations de sauvegarde de la base de données :
- Exécution planifiée et à la demande
- Historique des sauvegardes avec horodatages et tailles de fichiers
- Toutes les sauvegardes chiffrées et stockées localement

---

## Style visuel

- **Rouge / Critique :** alertes de gravité critique
- **Ambre / Orange :** gravité élevée et avertissement
- **Bleu :** événements informationnels
- **Vert :** statut normal / sûr

---

## Réactivité

Le tableau de bord est optimisé pour les ordinateurs de bureau et les ordinateurs portables :
- Ordinateurs portables 13" aux moniteurs ultra-larges
- Écrans haute résolution

---

## Résumé

Le tableau de bord Nyroxis ne demande pas à ses utilisateurs de choisir entre puissance et simplicité. Les professionnels de la sécurité ont la profondeur forensique dont ils ont besoin. Les utilisateurs non techniques ont la clarté dont ils ont besoin. Une protection de niveau entreprise, accessible à tous ceux qu'elle protège.
