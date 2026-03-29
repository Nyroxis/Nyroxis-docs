# Correspondance de règles & Détection

Le module de correspondance de règles est la façon dont Nyroxis Intelligence évalue les événements de sécurité et génère des alertes.
Il apporte une logique de détection de style SIEM aux appareils personnels — entièrement hors ligne, axé sur la confidentialité et extensible par les professionnels de la sécurité.

---

## Ce que fait la correspondance de règles

Nyroxis Intelligence évalue les événements selon trois couches de règles locales pour identifier :
- Les modèles de menaces connus dans des événements individuels
- Les relations suspectes entre événements au fil du temps
- Les séquences d'attaques en plusieurs étapes

Aucune règle ni aucun journal n'est jamais envoyé en ligne.

---

## Trois couches de détection

### Couche 1 — Règles de détection (27 règles)
Correspondance de modèles contre des événements individuels.

**Types de déclencheurs :**
- Exécution suspecte de processus
- Installation non autorisée de service
- Comportement réseau anormal
- Tentatives d'accès aux informations d'identification
- Indicateurs d'activité de logiciels malveillants connus

Lorsqu'une règle de détection se déclenche, une alerte immédiate est générée et stockée dans la base de données de détections.

---

### Couche 2 — Règles de corrélation (12 règles)
Correspondance de modèles à travers des événements liés dans le temps et selon différentes sources.

**Types de déclencheurs :**
- Échec de connexion suivi d'un succès depuis un emplacement différent
- Nouveau processus se lançant immédiatement après la connexion d'un périphérique USB
- Tentatives de connexion répétées échouées suivies d'un appel sortant réussi
- Exécution de script suivie d'une modification du système de fichiers

Les règles de corrélation révèlent des modèles de menaces qu'aucun événement isolé ne pourrait exposer seul.

---

### Couche 3 — Règles de chaîne (2 règles)
Détection de séquences d'attaques en plusieurs étapes réparties sur plusieurs événements et fenêtres temporelles.

Les règles de chaîne sont les alertes de la plus haute priorité dans le système. Elles représentent des intrusions coordonnées et progressives — le type caractéristique des menaces persistantes avancées.

Chaque résultat de chaîne inclut une reconstruction complète de la séquence d'attaque détectée.

---

## Extensible par les professionnels de la sécurité

Le moteur de règles est entièrement ouvert à l'extension. Les professionnels de la sécurité peuvent :
- Écrire des règles de détection, de corrélation ou de chaîne personnalisées en format JSON
- Les déployer directement dans le système sans modifier les composants principaux
- Tester les règles sur des données d'événements existantes avant le déploiement
- Gérer leur bibliothèque de règles personnalisées avec versioning

Cela permet à Nyroxis d'être adapté à des environnements, des modèles de menaces ou des exigences organisationnelles spécifiques.

---

## Comment le moteur évalue les règles

Nyroxis Intelligence fait correspondre les règles avec :
- Les métadonnées et le contenu des événements
- Les horodatages et fenêtres temporelles
- La lignée des processus
- Les points de terminaison réseau
- Les indicateurs de gravité
- Les relations inter-événements

Toutes les évaluations sont en temps réel et entièrement locales.

---

## Quand une règle se déclenche

Lorsqu'une règle est correspondante, Nyroxis :
- Déclenche une alerte immédiate
- Stocke le résultat dans la base de données de détections dédiée
- Enregistre les événements correspondants, le niveau de gravité et les détails de la règle
- Rend le résultat visible dans la vue Détection, Corrélation ou Chaîne du tableau de bord

---

## Garantie de confidentialité

Toute correspondance de règles :
- Se produit localement sur l'appareil
- Ne communique pas avec des services externes
- Utilise uniquement des données d'événements chiffrées
- Ne télécharge jamais des journaux, des règles ou des correspondances de modèles

---

## Résumé

Le moteur de correspondance de règles de Nyroxis apporte une détection structurée de style SIEM aux points de terminaison personnels — sur trois couches, en croissance continue et extensible par les professionnels de la sécurité — sans dépendance au cloud ni compromis sur la vie privée.
