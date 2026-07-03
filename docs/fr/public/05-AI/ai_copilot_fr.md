# AI Copilot — Analyse assistée par le cloud (optionnelle)

L'**AI Copilot** est une fonctionnalité optionnelle, activée explicitement, qui vous fournit une explication en langage naturel, de niveau expert, d'une alerte précise — ce qu'elle signifie, sa gravité, et les actions à entreprendre.

Contrairement au moteur IA/ML local (qui s'exécute entièrement sur votre appareil), l'AI Copilot est **assisté par le cloud** : il envoie les détails d'une seule alerte à un service hébergé dans l'UE (nyroxis.ai) qui utilise un grand modèle de langage pour produire l'analyse. Comme cela implique l'envoi de données hors de l'appareil, Nyroxis traite cette fonctionnalité comme un choix délibéré et transparent — elle est **désactivée par défaut** et ne s'exécute jamais automatiquement.

---

## IA locale vs AI Copilot

Nyroxis dispose de deux couches d'intelligence distinctes et clairement différentes. Il est important de ne pas les confondre :

| | Moteur IA/ML local | AI Copilot |
|---|--------------------|------------|
| Où il s'exécute | Entièrement sur votre appareil | Service cloud hébergé dans l'UE (nyroxis.ai) |
| Réseau | Aucun — entièrement hors ligne | Envoie les données d'une alerte via HTTPS |
| Quand il s'exécute | À la demande, localement | Uniquement quand vous cliquez sur « Analyser » |
| Activé par défaut | Oui (hors ligne) | Non — sur activation uniquement |
| Ce qu'il fait | Détection d'anomalies (Isolation Forest + statistiques) | Explication en langage naturel d'une seule alerte |

Le moteur local est décrit dans les pages **IA locale**. Cette page concerne uniquement le Copilot cloud optionnel.

---

## Comment ça fonctionne

1. Vous connectez un compte AI Copilot depuis **Paramètres → AI Copilot** et cochez une case de consentement explicite.
2. Vous ouvrez une alerte précise et cliquez sur **Analyser**.
3. Le Dashboard envoie les informations de cette seule alerte à nyroxis.ai.
4. Le service renvoie une analyse en langage naturel dans la langue de votre interface (anglais, français ou allemand), avec un contexte MITRE ATT&CK et les prochaines étapes recommandées.

Il n'y a aucune transmission en arrière-plan, aucun envoi en masse et aucune analyse automatique. Chaque analyse porte sur une seule alerte, envoyée uniquement lorsque vous le demandez. Vous pouvez vous déconnecter à tout moment, ce qui supprime l'identifiant local.

---

## Ce qui est envoyé — et ce qui ne l'est pas

Lorsque vous analysez une alerte, le Dashboard envoie à nyroxis.ai :

- Les métadonnées de l'alerte (règle, sévérité, canal, horodatage, statut)
- L'adresse IP source associée à l'alerte
- Votre propre note sur l'alerte (le cas échéant)
- La définition de la règle correspondante

**Jamais envoyés :** vos journaux d'événements Windows bruts, la base de données d'événements chiffrée, ni aucun résultat du moteur IA/ML local.

Côté serveur, nyroxis.ai est hébergé sur une infrastructure de l'UE. Avant qu'un enregistrement d'analyse ne soit stocké, l'adresse IP source est remplacée par un hachage à sens unique et les motifs courants de chemins/noms d'utilisateur dans la note sont masqués. Pour produire son analyse, le service traite effectivement les informations d'alerte décrites ci-dessus — c'est le compromis inhérent à toute analyse assistée par le cloud, et c'est précisément pourquoi la fonctionnalité repose sur une activation explicite et un traitement alerte par alerte plutôt qu'automatique.

---

## Forfaits

L'AI Copilot est un abonnement distinct et optionnel, doté d'un niveau gratuit permettant un essai sans frais :

| Forfait | Prix | Analyses par mois |
|---------|------|-------------------|
| Free | 0 € | 30 |
| Pro | 29 € / mois | 1 000 |
| Team | 59 € / mois | 5 000 |
| Business | 149 € / mois | 15 000 |

Tous les forfaits AI Copilot sont hébergés dans l'UE et alignés sur le RGPD. La plateforme Nyroxis de bureau et l'abonnement AI Copilot sont indépendants — la plateforme est pleinement fonctionnelle sans aucun abonnement AI Copilot. Consultez la page *AI Copilot*. Les tarifs et limites sont indicatifs et peuvent évoluer ; voir [www.nyroxis.com](https://www.nyroxis.com) pour les informations à jour.

---

## Résumé

L'AI Copilot apporte un second avis expert, en langage naturel, à n'importe quelle alerte — proposé en toute transparence, hébergé dans l'UE, sur activation, et entièrement sous votre contrôle. Si vous préférez une configuration entièrement hors ligne, laissez-le simplement désactivé : tout le reste de Nyroxis continue de fonctionner sur l'appareil.
