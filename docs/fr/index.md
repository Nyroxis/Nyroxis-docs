# Qu'est-ce que Nyroxis ?

Nyroxis est une plateforme de cybersécurité légère et assistée par IA, conçue pour protéger les **endpoints personnels et non gérés** — les appareils que les outils de sécurité d'entreprise traditionnels ignorent souvent.

Elle assure une surveillance continue axée sur la confidentialité et apporte une détection de niveau SOC aux appareils personnels, sans nécessiter de connectivité cloud, d'expertise technique ou d'infrastructure d'entreprise.

## Pourquoi Nyroxis Existe

Les cyberattaques modernes ne ciblent plus uniquement les entreprises. Les dirigeants, les avocats, les juges, les médecins, les journalistes et même les familles sont ciblés sur **leurs appareils personnels** — là où il n'y a ni SOC, ni SIEM, ni équipe de sécurité pour les surveiller.

Nyroxis comble ce vide en apportant **une visibilité et une détection de niveau entreprise** au niveau personnel — silencieusement, localement, et sans compromis.

## À Qui S'adresse Nyroxis ?

- Dirigeants et personnes à profil élevé
- Avocats, juges, médecins et professionnels traitant des données sensibles
- Familles recherchant une visibilité sur leur sécurité numérique
- Ingénieurs en cybersécurité et analystes SOC à domicile
- Voyageurs fréquents et travailleurs à distance
- Contractants indépendants et consultants

## Comment Fonctionne Nyroxis (Vue d'Ensemble)

Nyroxis est construit autour de quatre composants fondamentaux fonctionnant de concert :

### Nyroxis Agent
- Surveillance silencieuse continue depuis plusieurs canaux système
- Normalise, chiffre et stocke tout localement
- Fonctionne entièrement hors ligne — conception inviolable
- ~57 Mo de RAM, 0,1 % du CPU

### Nyroxis Intelligence
- Moteur de détection à trois niveaux
- 27 règles de détection, 12 règles de corrélation, 2 règles de chaîne (en croissance continue)
- Extensible par les professionnels de la sécurité — règles personnalisées au format JSON
- ~87 Mo de RAM, 1,8 % du CPU

### Nyroxis System Guardian
- Gardien silencieux dans la barre d'état système
- Surveille tous les services en continu
- Gère les sauvegardes, la validation de licence hors ligne et la vérification des mises à jour
- Arrête les services automatiquement si la licence expire
- ~6,5 Mo de RAM, 0,1 % du CPU

### Nyroxis Dashboard
- Visibilité en temps réel sur les événements, détections, corrélations et chaînes
- Recherche forensique, analyse IA/ML, rapports PDF/CSV
- Anglais, français et allemand

```
[ Appareil ]
   |--> Nyroxis Agent          (collecte & chiffrement)
   |--> Nyroxis Intelligence   (détection & corrélation)
   |--> Nyroxis System Guardian (surveillance & protection)
   |--> Nyroxis Dashboard      (visibilité & analyse)
```

## Avantages Clés

- Vos données de sécurité restent sur votre appareil par défaut
- Stockage chiffré de qualité forensique (AES-256)
- 27 + 12 + 2 couches de règles de détection, extensibles par les professionnels de la sécurité
- Détection d'anomalies IA/ML locale — s'exécute entièrement sur l'appareil, sans cloud
- AI Copilot optionnel — un assistant cloud hébergé dans l'UE, sur activation, pour l'analyse en langage naturel d'une seule alerte (désactivé par défaut)
- Licence hors ligne basée sur le HWID
- Léger et silencieux — invisible pour les attaquants

> **Sur la confidentialité :** Nyroxis est hors ligne par défaut. La collecte d'événements, la détection, la corrélation, l'analyse de chaînes et le moteur IA/ML local s'exécutent tous sur votre appareil. La seule exception optionnelle est l'**AI Copilot**, que vous activez et déclenchez explicitement par alerte ; consultez la page AI Copilot pour savoir exactement ce qu'il envoie.

## Guide de la Documentation

Cette documentation comprend :
- Architecture & Composants
- Agent, Intelligence & System Guardian
- Dashboard & Moteur IA/ML
- Sécurité & Confidentialité
- Cas d'Usage
- Feuille de Route
- Licence
- FAQ & Glossaire
