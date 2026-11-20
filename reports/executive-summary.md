# Synthèse exécutive – Évaluation de la sécurité web

- **Application :** OWASP Juice Shop
- **URL :** `http://localhost:3000`
- **Environnement :** instance locale Docker
- **Type d’évaluation :** préliminaire, manuelle et non destructive

## Objectif du projet

Documenter un exercice de portfolio débutant portant sur les parcours d’authentification et les informations de compte d’une application web pédagogique, dans un environnement local contrôlé.

## Périmètre et environnement

Le périmètre est limité à l’instance Juice Shop locale à l’adresse `http://localhost:3000`. Les interactions rapportées concernent un compte de test. Aucun autre système n’est inclus. Aucun changement de configuration Docker ou du code source de Juice Shop n’est décrit dans cette documentation.

Les outils indiqués pour l’évaluation sont Docker et un navigateur web. Aucune capture Burp Suite ni aucun résultat de scan automatisé n’est fourni.

## Méthodologie

La démarche est une exploration manuelle limitée : consulter les parcours d’authentification et de compte, consigner les comportements rapportés, distinguer les éléments observés des fonctions non testées, puis recommander des vérifications défensives. Aucun scan automatisé, aucune exploitation et aucune action destructive ne sont rapportés. Les observations n’ont pas été accompagnées de captures ou de traces HTTP dans le matériel fourni.

## Principales observations préliminaires

Les observations suivantes ont été rapportées lors de l’évaluation manuelle :

- Login et Logout ont fonctionné avec un compte de test.
- Le profil affichait le nom d’utilisateur et une URL d’image, qui restaient visibles après actualisation.
- Une erreur HTTP 500 aurait été rencontrée lors d’une interaction avec User Profile. Le texte rapporté est `Blocked illegal activity by ::ffff:172.17.0.1`, avec l’emplacement `userProfile.js:81:18`.
- Dans Forgot Password, seul le champ Email semblait accessible pendant l’observation.
- Le formulaire Change Password affichait Current Password, New Password et Repeat New Password ; aucun changement n’a été fait.
- Manage Passkeys était disponible sans passkey enregistré.
- La page de configuration TOTP affichait un QR code ; la 2FA n’a pas été activée.
- Last Login IP affichait `?`.

## Limites

Les observations ci-dessus sont rapportées par l’utilisateur et n’ont pas été vérifiées indépendamment lors de cette tâche documentaire. Les captures d’écran, requêtes/réponses HTTP et journaux d’origine sont **Non collectée**. La cause et l’impact de l’erreur 500 ne sont pas déterminés. Les parcours complets de récupération de mot de passe, de changement de mot de passe, d’enrôlement/révocation de passkey et d’activation TOTP sont **Non testé**.

## Recommandations

Prioriser la vérification de l’erreur du profil et des réponses réellement exposées au client, puis examiner le flux complet Forgot Password et l’exactitude de la valeur Last Login IP. Appliquer les contrôles serveur, la gestion sûre des erreurs, l’autorisation pour les opérations de compte, une gestion robuste des sessions et une journalisation qui n’expose pas de secrets.

Les constats détaillés et les recommandations sont disponibles dans le [registre des constats](../documentation/security-findings.md) et les [recommandations](../documentation/remediation-recommendations.md).

## Conclusion

Il s’agit d’une évaluation manuelle préliminaire. Les informations disponibles identifient des comportements qui méritent vérification, mais aucune vulnérabilité n’a été confirmée et aucune sévérité n’a été évaluée. Des preuves reproductibles et l’examen des réponses côté serveur sont nécessaires avant toute conclusion de sécurité.
