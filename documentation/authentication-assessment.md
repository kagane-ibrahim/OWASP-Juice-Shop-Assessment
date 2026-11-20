# Évaluation du parcours d’authentification

- **Date de mise à jour :** 20 novembre 2026
- **Cible :** OWASP Juice Shop, instance Docker locale, `http://localhost:3000`
- **Type :** évaluation manuelle préliminaire et non destructive

## Objectif et méthode

Ce document rassemble les observations préliminaires d’authentification communiquées pour le compte de test. Il distingue les comportements rapportés de ceux qui n’ont pas été testés. Aucune observation ci-dessous ne constitue à elle seule une vulnérabilité confirmée. Aucun nouveau test n’a été réalisé pour cette mise à jour documentaire.

## Observations préliminaires rapportées

| Fonctionnalité | Observation | État | Preuve disponible |
|---|---|---|---|
| Connexion (Login) | La connexion a fonctionné avec un compte de test. | Rapportée comme vérifiée par l’utilisateur ; non reproduite indépendamment dans cette mise à jour. | Non collectée |
| Déconnexion (Logout) | La déconnexion a fonctionné avec le compte de test. | Rapportée comme vérifiée par l’utilisateur ; non reproduite indépendamment dans cette mise à jour. | Non collectée |
| Profil utilisateur | Le nom d’utilisateur et l’URL de l’image étaient affichés et restaient présents après actualisation de la page. | Rapportée comme vérifiée par l’utilisateur. | Non collectée |
| Mot de passe oublié | Seul le champ Email semblait accessible pendant l’observation ; d’autres champs n’étaient pas accessibles. Cela ne permet pas de conclure qu’ils n’existent pas dans d’autres états du parcours. | Observation rapportée ; parcours complet et requêtes non testés. | Non collectée |
| Changement de mot de passe | Le formulaire affichait Current Password, New Password et Repeat New Password. Aucun changement n’a été effectué. | Champs rapportés comme observés ; soumission non testée. | Non collectée |
| Gestion des passkeys | La page Manage Passkeys était disponible et aucun passkey n’était enregistré. | État rapporté ; ajout et suppression non testés. | Non collectée |
| Configuration 2FA | La page de configuration TOTP et un code QR étaient affichés. La 2FA n’a pas été activée. | Page rapportée comme observée ; activation et vérification du TOTP non testées. | Non collectée ; aucun QR conservé |
| Adresse IP de dernière connexion | La valeur affichée était `?`. | Valeur rapportée ; source et exactitude non vérifiées. | Non collectée |

## Limites

Les observations du tableau sont fournies par l’utilisateur ; aucune capture d’écran, requête ou réponse HTTP n’a été remise pour cette mise à jour. Les détails de compte et l’URL d’image n’ont pas été consignés. Les opérations de changement de mot de passe, d’activation de la 2FA, de gestion des passkeys et les parcours complets de récupération restent **Non testé**.

La présence d’un champ ou d’une valeur d’interface ne suffit pas à confirmer une vulnérabilité. Toute conclusion technique nécessiterait des éléments reproductibles et une vérification adaptée.
