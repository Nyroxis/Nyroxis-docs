# Scénarios IA

Les scénarios IA représentent des situations de sécurité de haut niveau que le moteur IA/ML local identifie sur la base de modèles comportementaux, de séquences d'événements et de corrélations d'anomalies.
Ils aident les utilisateurs à comprendre le *contexte* — pas seulement des événements individuels ou des anomalies isolées.

---

## Objectif des scénarios IA

Tandis que les détections mettent en évidence des anomalies spécifiques et que les correspondances de règles signalent des menaces individuelles, les **Scénarios** expliquent *pourquoi ces signaux sont importants* en regroupant les résultats connexes dans des contextes d'attaques réelles significatifs.

Les scénarios donnent aux utilisateurs de la clarté sur :
- Le type de menace observée
- Comment les événements et anomalies individuels sont liés
- Ce que le modèle combiné signifie en termes concrets
- Quelles sont les prochaines étapes recommandées

Cela rend les modèles de menaces sophistiqués compréhensibles même pour les utilisateurs non techniques.

---

## Types de scénarios

### 1. Chaîne de processus suspecte
Détecté lorsqu'une séquence d'activité de processus ressemble à un comportement malveillant connu :
- Processus inconnu lançant un moteur de scripts
- Moteur de scripts déclenchant une modification de fichier suivie d'un appel réseau
- Processus engendrant plusieurs enfants en succession rapide

Utile pour détecter les malwares en phase initiale, les comportements de dropper ou les techniques de living-off-the-land.

---

### 2. Activité réseau non autorisée
Déclenché lorsque le moteur observe :
- Des connexions sortantes vers des points de terminaison réseau inconnus ou rares
- Des tentatives de connexion répétées échouées suivies d'un appel sortant réussi
- Une activité réseau à volume élevé bien en dehors des modèles de base normaux

Peut indiquer un balayage, un beaconing ou des tentatives d'exfiltration de données.

---

### 3. Activité de fichiers anormale
Se produit lorsque :
- Des fichiers ou répertoires sensibles sont accédés de manière inattendue
- Un grand nombre de fichiers sont modifiés dans une courte fenêtre temporelle
- Les modifications de fichiers sont corrélées avec un comportement de processus ou réseau suspect

Utile pour détecter les comportements de type ransomware, la mise en scène de données ou la manipulation.

---

### 4. Tentative d'élévation de privilèges
Déclenché par :
- Des tentatives répétées d'élévation de privilèges
- Des appels système rares ou inhabituels
- Un comportement incompatible avec le modèle d'activité normal de l'utilisateur de l'appareil

Aide à identifier les tentatives d'exploitation locale ou l'abus d'informations d'identification.

---

### 5. Indicateur de persistance
Se produit lorsqu'un processus tente de :
- Modifier les emplacements de démarrage ou les tâches planifiées
- Modifier la configuration système pour survivre au redémarrage
- Installer des services ou des pilotes de manière inattendue

Avertit d'une compromission à long terme et de l'établissement d'un point d'ancrage par l'attaquant.

---

### 6. Modèle d'intrusion lent
Le moteur identifie des anomalies à long terme et à faible bruit telles que :
- Escalade graduelle d'une activité inhabituelle sur des heures ou des jours
- Activité périodique rare se répétant selon un calendrier
- Séquences comportementales multi-étapes réparties sur de longues fenêtres temporelles

Détecte les attaquants furtifs qui évitent délibérément de déclencher des règles basées sur des seuils.

---

## Détails du rapport de scénario

Chaque scénario fournit :
- Description de la situation en langage simple
- Événements et résultats affectés
- Explication de la séquence montrant comment les signaux sont connectés
- Niveau de gravité
- Interprétation réelle
- Prochaines étapes recommandées

---

## Entièrement local

Toute la logique des scénarios :
- S'exécute hors ligne sur l'appareil
- Utilise des données d'événements locaux chiffrées
- Ne contacte jamais les services cloud
- Préserve la confidentialité totale de l'utilisateur

---

## Résumé

Les scénarios IA aident les utilisateurs à voir la vue d'ensemble — donnant du sens aux anomalies individuelles et aux correspondances de règles en les associant à des contextes d'attaques réelles, permettant une détection précoce des menaces sophistiquées entièrement hors ligne et en privé.
