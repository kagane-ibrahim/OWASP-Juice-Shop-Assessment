# OWASP Juice Shop – Évaluation de la sécurité d’une application web

## Objectifs du projet

Ce projet constitue un portfolio d’apprentissage en cybersécurité. Il vise à découvrir, de manière progressive et documentée, comment évaluer la sécurité d’une application web dans un environnement local autorisé.

Les objectifs sont de :

- comprendre les principales étapes d’une évaluation de sécurité web ;
- consigner les observations et les preuves de façon claire ;
- proposer des recommandations de correction compréhensibles ;
- produire un rapport final adapté à un public débutant.

## À propos d’OWASP Juice Shop

OWASP Juice Shop est une application web volontairement vulnérable, conçue à des fins de formation et de sensibilisation à la sécurité. Elle permet d’apprendre dans un environnement contrôlé, sans viser de véritables services ou utilisateurs.

## Périmètre autorisé

Le seul système concerné par ce projet est **mon instance locale d’OWASP Juice Shop**, accessible à l’adresse suivante : [http://localhost:3000](http://localhost:3000).

Le projet ne couvre aucun site public, système tiers, réseau externe ou autre cible. Le statut actuel et les limites de l’évaluation sont résumés ci-dessous et détaillés dans les documents du projet.

## Environnement et outils

- **Docker** : hébergement local de l’instance Juice Shop.
- **Navigateur web** : consultation manuelle de l’interface locale.
- **Codex** : aide à l’organisation et à la rédaction de la documentation.
- **Burp Suite Community** : outil envisagé pour l’observation HTTP ; aucune capture Burp n’est disponible dans les éléments documentés.

## Méthodologie

Les étapes seront réalisées une par une et documentées dans ce dépôt :

1. **Reconnaissance** : comprendre les pages, fonctions et parcours disponibles dans l’application locale.
2. **Tests d’authentification** : examiner les mécanismes de connexion et de gestion de session dans le périmètre autorisé.
3. **Analyse des vulnérabilités** : identifier et comprendre les faiblesses observées, sans dépasser le périmètre défini.
4. **Collecte des preuves** : conserver des captures d’écran, notes ou détails techniques utiles, en évitant les données personnelles.
5. **Recommandations de remédiation** : expliquer comment réduire ou corriger chaque risque constaté.
6. **Rapport final** : présenter le périmètre, la méthode, les résultats et les recommandations dans un format clair.

## Structure de la documentation

- [Reconnaissance initiale](notes/reconnaissance.md) — périmètre et fonctionnalités repérés lors de l’exploration préliminaire.
- [Évaluation de l’authentification](documentation/authentication-assessment.md) — parcours de compte, états rapportés et limites de vérification.
- [Registre des constats](documentation/security-findings.md) — observations à investiguer, sans vulnérabilité confirmée.
- [Recommandations](documentation/remediation-recommendations.md) — vérifications liées aux observations et bonnes pratiques défensives.
- [Synthèse exécutive](reports/executive-summary.md) — objectif, périmètre, résultats, limites et conclusion.
- `evidence/` — réservé aux preuves réelles ; aucune capture ou trace HTTP n’a été fournie pour cette mise à jour.

## Considérations éthiques et légales

Toutes les activités doivent rester limitées à l’instance Juice Shop hébergée localement et contrôlée par moi-même. Je n’effectuerai aucun test sur un système sans autorisation explicite de son propriétaire. Les résultats et les preuves seront utilisés uniquement à des fins d’apprentissage et de portfolio, et seront présentés de manière responsable.

Ce projet pédagogique ne constitue ni une certification ni une garantie qu’un système est sécurisé. Toute activité doit respecter les lois et règles applicables.

## État actuel de l’évaluation

- L’interface locale a été accessible lors d’une reprise antérieure et les pages Login et Register ont été consultées. Les observations de compte détaillées dans les documents sont celles rapportées par l’utilisateur ; elles n’ont pas été reproduites pendant cette mise à jour documentaire.
- Le registre contient trois observations préliminaires à investiguer : une erreur HTTP 500 rapportée sur User Profile, l’accès limité au formulaire Forgot Password et la valeur `?` pour Last Login IP.
- **Aucune vulnérabilité n’est confirmée et aucune sévérité n’est évaluée.**
- Les captures, requêtes/réponses HTTP et journaux d’origine sont indiqués **Non collectée** ; aucune preuve artificielle n’a été créée.
- Les parcours complets de récupération et de changement de mot de passe, l’enrôlement des passkeys et l’activation TOTP sont **Non testé**.
- Aucun scan automatisé ni exploitation n’est rapporté dans cette évaluation.

## Portfolio académique et projets

Cette section rassemble des projets académiques, des travaux pratiques et une évaluation préliminaire. Les descriptions reflètent les informations disponibles et ne présentent pas les projets académiques comme une expérience professionnelle.

### Projets académiques

- [SOC académique](projects/soc-academique/README.md) — collecte et analyse de journaux, détection d’alertes réseau et tableaux de bord.
- [Détection de prompt injection](projects/prompt-injection-detection/README.md) — solution locale associant règles, analyse sémantique, score de risque et journalisation JSON.
- [Détection d’attaques réseau](projects/network-attack-detection/README.md) — capture et analyse de trafic, découverte réseau et examen d’alertes IDS.
- [Plateforme Moodle](projects/moodle-platform/README.md) — plateforme éducative avec gestion des utilisateurs, cours, quiz et base de données.

### Laboratoire

- [AWS Academy Lab](projects/aws-academy-lab/README.md) — exercice cloud avec EC2, équilibrage de charge, mise à l’échelle, RDS et bastion ; score déclaré : 35/35 (100 %).

### Évaluation préliminaire

- [OWASP Juice Shop](documentation/security-findings.md) — évaluation manuelle limitée à l’instance locale. Les trois observations restent préliminaires ; aucune vulnérabilité n’est confirmée.
