# Moteur IA & Apprentissage automatique — Vue d'ensemble

Le moteur IA/ML de Nyroxis est un système de détection d'anomalies entièrement local et hors ligne, intégré dans le tableau de bord.
Il analyse les événements de sécurité sans envoyer de données vers le cloud, offrant une intelligence comportementale avec une forte confidentialité.

> **Remarque :** Cette page décrit le moteur IA/ML **local, sur l'appareil**, qui s'exécute entièrement hors ligne. Nyroxis propose aussi un **AI Copilot** séparé et optionnel — un assistant cloud hébergé dans l'UE, sur activation, pour l'analyse en langage naturel d'alertes individuelles. Les deux sont indépendants ; voir la page *AI Copilot*.

---

## Une approche différente de l'IA

La plupart des solutions de sécurité alimentées par IA s'appuient sur une infrastructure cloud — envoyant des données télémétriques vers des serveurs distants pour analyse.
Nyroxis adopte l'approche opposée : chaque aspect du moteur IA s'exécute localement, sur l'appareil propre de l'utilisateur.
Aucune donnée n'est transmise. Aucun service externe n'est consulté. Aucun profil comportemental ne quitte jamais la machine.

Ce n'est pas une limitation — c'est un engagement architectural délibéré envers la confidentialité.

---

## Ce que le moteur IA fournit

- Détection d'anomalies comportementales via Isolation Forest
- Analyse statistique : Z-Score, IQR, moyennes mobiles, détection de pics
- Classification de gravité : Critique / Élevé / Moyen / Faible
- Identification des caractéristiques contributives — explique *pourquoi* quelque chose a été signalé
- Construction d'une ligne de base comportementale par appareil

---

## Isolation Forest — Algorithme de base

Au cœur du moteur se trouve une implémentation personnalisée de l'algorithme Isolation Forest, développée entièrement en Rust — aucune bibliothèque ML externe requise.

**Fonctionnement :**
Isolation Forest construit une forêt d'arbres de décision aléatoires. Les événements anormaux sont statistiquement rares ou structurellement inhabituels — ils nécessitent moins de divisions pour être isolés et reçoivent donc un score d'anomalie plus élevé.

**Implémentation :**
- 100 arbres d'isolation par cycle d'analyse
- 256 échantillons maximum par arbre
- 8 caractéristiques comportementales par fenêtre d'analyse
- Score d'anomalie > 0,6 déclenche une détection

---

## 8 caractéristiques comportementales analysées

| Caractéristique | Description |
|---------|-------------|
| Nombre d'événements | Total des événements dans la fenêtre d'analyse |
| Sources uniques | Nombre de sources d'événements distinctes |
| Destinations uniques | Nombre de destinations réseau distinctes |
| Heure du jour | Contexte temporel pour la ligne de base comportementale |
| Jour de la semaine | Reconnaissance de modèles hebdomadaires |
| Événements par heure | Normalisation du taux d'activité |
| Ratio de nouvelles sources | Proportion de sources jamais vues auparavant |
| Ratio de nouvelles destinations | Proportion de destinations jamais vues auparavant |

Toutes les caractéristiques sont normalisées via la standardisation z-score avant l'analyse.

---

## Moteur d'analyse statistique

Fonctionnant en parallèle avec Isolation Forest :

| Z-Score | Gravité | Confiance |
|---------|----------|------------|
| > 3,0 | Critique | 99,7 % |
| > 2,0 | Élevé | 95 % |
| > 1,5 | Moyen | 86 % |
| > 1,0 | Faible | 68 % |

Méthodes supplémentaires : détection des valeurs aberrantes IQR, moyenne mobile, moyenne mobile exponentielle, détection de pics, analyse de corrélation.

---

## Garantie de confidentialité totale

Le moteur IA :
- Fonctionne entièrement hors ligne
- Traite uniquement des données d'événements chiffrées localement
- N'envoie jamais de données à des serveurs
- Ne télécharge jamais de profils comportementaux
- N'utilise jamais d'inférence cloud ou d'APIs en ligne

Le moteur IA appartient entièrement à l'appareil de l'utilisateur.

---

## Résumé

Le moteur IA/ML de Nyroxis fournit une détection d'anomalies Isolation Forest sur l'appareil combinée à une analyse statistique — offrant une intelligence comportementale de qualité cloud sans compromis sur la vie privée.
