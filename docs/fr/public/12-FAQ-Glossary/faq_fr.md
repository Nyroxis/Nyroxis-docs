# Foire Aux Questions

## Général

**Qu'est-ce que Nyroxis ?**
Nyroxis est un SIEM personnel endpoint — une plateforme de cybersécurité légère et capable de fonctionner hors ligne qui apporte une surveillance, une détection et des preuves forensiques de niveau SOC aux appareils personnels. Il est conçu pour les dirigeants, les professionnels du droit, les familles et les praticiens de la sécurité qui ont besoin d'une protection de niveau entreprise sans la complexité d'une entreprise.

**À qui s'adresse Nyroxis ?**
Les dirigeants, les cadres supérieurs, les juges, les avocats, les médecins, les journalistes, les administrateurs SOC, les familles, les contractants indépendants et les professionnels de la sécurité — toute personne dont l'appareil personnel est un vecteur d'attaque potentiel.

**Nyroxis est-il entièrement hors ligne ?**
Oui. Aucun cloud, aucune télémétrie, aucune transmission de données d'aucune sorte. Toute la surveillance, la détection, l'analyse IA/ML et la validation de licence s'effectuent entièrement sur votre appareil.

**Quelles plateformes Nyroxis prend-il en charge ?**
Actuellement Windows (v1.0). La prise en charge de macOS et Linux est en développement actif.

**Quelles langues le Dashboard prend-il en charge ?**
L'anglais, le français et l'allemand.

---

## Détection et Règles

**Combien de règles de détection Nyroxis possède-t-il ?**
La version 1.0 comprend 27 règles de détection, 12 règles de corrélation et 2 règles de chaîne. La bibliothèque s'enrichit continuellement au fur et à mesure que de nouveaux patterns de menaces sont identifiés.

**Quelle est la différence entre les règles de détection, de corrélation et de chaîne ?**
- **Détection** — identifie les patterns de menaces connues dans des événements individuels
- **Corrélation** — connecte des événements liés dans le temps et entre les sources pour révéler des patterns qu'aucun événement unique n'exposerait
- **Chaîne** — détecte les séquences d'attaques en plusieurs étapes réparties sur plusieurs événements et fenêtres temporelles

**Les professionnels de la sécurité peuvent-ils ajouter leurs propres règles ?**
Oui. Le moteur de règles est entièrement extensible. Les professionnels de la sécurité peuvent écrire et déployer des règles personnalisées au format JSON sans modifier le système central.

---

## Confidentialité et Données

**Nyroxis lit-il mes fichiers personnels ?**
Non. Nyroxis collecte uniquement des événements techniques pertinents pour la sécurité — processus, connexions réseau, activité du système de fichiers et actions de privilèges. Il ne lit jamais le contenu de vos documents, e-mails, photos ou historique de navigation.

**Où mes données sont-elles stockées ?**
Toutes les données sont stockées localement dans une base de données SQLite chiffrée en AES-256 sur votre appareil. Elles ne quittent jamais votre machine.

**Les journaux peuvent-ils être exportés ?**
Oui — depuis le Dashboard, vous pouvez exporter les résultats au format PDF ou CSV pour les rapports ou les procédures judiciaires.

**Le moteur IA/ML est-il local ?**
À 100 % local. L'algorithme Isolation Forest est implémenté en Rust sans bibliothèque ML externe. Aucune donnée comportementale n'est jamais envoyée à un serveur.

**Puis-je réinitialiser mes données ?**
Oui. Depuis le Dashboard, vous pouvez réinitialiser les journaux d'événements, les résultats de détection, la référence comportementale IA et toutes les métadonnées à tout moment.

---

## Licence

**Comment fonctionne la licence ?**
Chaque licence est liée à votre matériel (HWID). La clé cryptographique est dérivée du profil matériel de votre appareil. La validation est entièrement hors ligne — aucune connexion Internet requise.

**Y a-t-il un essai gratuit ?**
Oui. Chaque nouvelle installation inclut un mois d'accès complet sans restriction. Aucune carte bancaire requise.

**Que se passe-t-il si ma licence expire ?**
Nyroxis System Guardian arrête automatiquement Nyroxis Agent et Nyroxis Intelligence lorsque la licence expire ou est invalidée.

---

## Technique

**Quelles ressources Nyroxis utilise-t-il ?**
- Nyroxis Agent : ~57 Mo de RAM, 0,1 % du CPU
- Nyroxis Intelligence : ~87 Mo de RAM, 1,8 % du CPU
- Nyroxis System Guardian : ~6,5 Mo de RAM, 0,1 % du CPU
- Nyroxis Dashboard : ~32 Mo de RAM lorsqu'ouvert

**Qu'est-ce que Nyroxis System Guardian ?**
Une application silencieuse dans la barre d'état système qui surveille tous les services de la plateforme toutes les 3 secondes, gère les sauvegardes, valide la licence basée sur le HWID hors ligne et vérifie les mises à jour. Il arrête automatiquement les services si la licence expire.

**Avec quelle technologie Nyroxis est-il construit ?**
Les services principaux sont construits en Rust. Le Dashboard utilise Tauri + WebView. La base de données locale est SQLite. Le chiffrement utilise AES-256, les signatures Ed25519 et le hachage SHA-256. Le moteur IA/ML est une implémentation personnalisée de Isolation Forest en Rust sans bibliothèque ML externe.

**Nyroxis fonctionne-t-il dans des environnements air-gap ?**
Oui. Les fonctionnalités complètes ne nécessitent aucune connectivité Internet — la surveillance, la détection, l'analyse IA/ML et la validation de licence fonctionnent toutes entièrement hors ligne.
