# Glossaire

**AES-256** — Advanced Encryption Standard avec une clé de 256 bits. Utilisé pour chiffrer tous les journaux d'événements Nyroxis et le stockage de la base de données au repos.

**Agent** — Voir *Nyroxis Agent*.

**Score d'Anomalie** — Une valeur entre 0,0 et 1,0 produite par le moteur Isolation Forest. Des scores plus élevés indiquent un comportement plus anormal. Les scores supérieurs à 0,6 déclenchent une détection.

**Référence Comportementale** — Un profil local de l'activité normale de l'appareil construit au fil du temps par le moteur IA/ML, utilisé pour identifier les déviations.

**Règle de Chaîne** — Une règle de détection ciblant les séquences d'attaques en plusieurs étapes réparties sur plusieurs événements et fenêtres temporelles. Nyroxis v1.0 inclut 2 règles de chaîne.

**Règle de Corrélation** — Une règle de détection qui connecte des événements liés dans le temps et entre les sources pour révéler des patterns qu'aucun événement unique n'exposerait. Nyroxis v1.0 inclut 12 règles de corrélation.

**Règle de Détection** — Une règle ciblant les patterns de menaces connues dans des événements individuels. Nyroxis v1.0 inclut 27 règles de détection.

**Preuves Forensiques** — Journaux d'événements inviolables et chiffrés de qualité forensique, adaptés à l'investigation de sécurité.

**Chaîne de Hachage** — Une structure cryptographique où chaque bloc d'événement contient le hash du bloc précédent, rendant la suppression, la modification, l'injection ou le réordonnancement immédiatement détectables.

**HMAC** — Hash-based Message Authentication Code. Utilisé dans la validation de licence Nyroxis pour vérifier l'intégrité des fichiers hors ligne.

**HWID** — Identifiant Matériel (Hardware Identifier). Une valeur unique dérivée des caractéristiques physiques d'un appareil, utilisée pour lier une licence Nyroxis à une machine spécifique et dériver les clés de chiffrement.

**Isolation Forest** — Un algorithme d'apprentissage automatique qui détecte les anomalies en construisant des arbres de décision aléatoires et en mesurant la rapidité avec laquelle chaque point de données est isolé. Implémenté en Rust dans Nyroxis sans bibliothèque ML externe.

**IQR** — Interquartile Range (Écart Interquartile). Une méthode statistique pour la détection des valeurs aberrantes utilisée dans le moteur d'analyse statistique de Nyroxis.

**Nyroxis Agent** — Le service de surveillance central. Collecte, normalise, chiffre et stocke les événements de sécurité localement (~57 Mo de RAM, 0,1 % du CPU).

**Nyroxis Dashboard** — L'interface utilisateur pour la visibilité, l'analyse forensique, les informations IA/ML et les rapports.

**Nyroxis Intelligence** — Le moteur de détection et de corrélation. Fonctionne sur 27 règles de détection, 12 règles de corrélation et 2 règles de chaîne (~87 Mo de RAM, 1,8 % du CPU).

**Nyroxis System Guardian** — Le gardien de la plateforme. Surveille tous les services en continu, gère les sauvegardes, valide la licence hors ligne et vérifie les mises à jour (~6,5 Mo de RAM, 0,1 % du CPU).

**Moteur de Règles** — Le composant à l'intérieur de Nyroxis Intelligence qui évalue les événements entrants par rapport aux règles de détection, de corrélation et de chaîne en temps réel.

**SIEM** — Security Information and Event Management (Gestion des Informations et des Événements de Sécurité). Un système qui collecte, corrèle et analyse les événements de sécurité. Nyroxis fonctionne comme un SIEM personnel endpoint.

**SQLite** — Le moteur de base de données local utilisé par Nyroxis pour stocker les journaux d'événements chiffrés et les résultats de détection.

**Protection contre la Falsification** — Mécanismes incluant les blocs d'événements enchaînés par hachage et la vérification de l'intégrité qui empêchent les attaquants de supprimer, modifier ou injecter des journaux sans être détectés.

**Z-Score** — Une mesure statistique indiquant de combien d'écarts-types une valeur s'éloigne de la moyenne. Utilisé par Nyroxis pour classer la sévérité des anomalies : Critique (>3,0), Élevé (>2,0), Moyen (>1,5), Faible (>1,0).
