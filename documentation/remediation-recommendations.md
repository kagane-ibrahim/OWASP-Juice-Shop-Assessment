# Recommandations de sécurité

Les recommandations sont séparées entre les vérifications liées aux observations du registre et les bonnes pratiques générales. Elles ne supposent pas qu’une vulnérabilité a été confirmée.

## Recommandations liées aux observations

| Référence | Recommandation défensive | Vérification à effectuer |
|---|---|---|
| OBS-01 — erreur HTTP 500 du profil | Valider côté serveur les entrées du profil selon les formats attendus. Traiter les exceptions de façon sûre : message client générique, détails techniques conservés dans les journaux internes avec accès contrôlé. | Reproduire l’erreur dans le périmètre local et vérifier séparément le contenu présenté au client et les détails consignés côté serveur. Confirmer si le nom de fichier et la ligne de code sont réellement exposés dans la réponse. |
| OBS-02 — récupération de mot de passe | Revoir le parcours complet, ses champs et ses états. Vérifier que les réponses ne révèlent pas si un compte existe, que les jetons sont temporaires et à usage unique et que les tentatives sont limitées. | Parcourir les étapes manuellement avec un compte de test et examiner les réponses sans achever ni changer le mot de passe. |
| OBS-03 — adresse IP de dernière connexion | Vérifier que la valeur affichée provient de la source prévue, est mise à jour correctement et que les valeurs inconnues sont présentées de manière explicite. | Comparer une connexion de test contrôlée, les données côté serveur et la valeur du profil ; vérifier la confiance accordée aux en-têtes proxy. |
| Profil utilisateur | Protéger les opérations de modification du profil par authentification et autorisation côté serveur. Valider l’URL d’image et limiter les schémas/ressources acceptés selon le besoin produit. | Tester uniquement les contrôles autorisés avec le compte de test et confirmer qu’un utilisateur ne peut modifier que son propre profil. |

## Bonnes pratiques générales

- **Authentification et autorisation :** vérifier côté serveur les droits pour les opérations sensibles, notamment le profil, les mots de passe, les passkeys et la 2FA.
- **Gestion des sessions :** utiliser des identifiants de session imprévisibles, renouveler la session après authentification, expirer et invalider la session à la déconnexion, et configurer les cookies avec `HttpOnly`, `Secure` (lorsque HTTPS est utilisé) et `SameSite` adapté.
- **Changement et récupération de mot de passe :** demander une authentification récente pour les changements, contrôler les jetons de récupération et ne jamais journaliser les mots de passe, réponses secrètes, jetons ou codes TOTP.
- **Passkeys et 2FA :** appliquer l’autorisation au compte et vérifier l’enrôlement, la révocation et la récupération de manière cohérente. Les parcours de cette instance restent à tester.
- **Journalisation :** journaliser les événements de sécurité utiles avec horodatage et identifiant de corrélation, tout en limitant l’accès et en excluant les secrets et données sensibles inutiles.
- **Erreurs :** fournir des messages compréhensibles sans détails internes, et conserver les informations de diagnostic uniquement dans des journaux protégés.

Ces recommandations sont des mesures de défense à considérer. Leur mise en œuvre et leur efficacité ne sont pas évaluées dans ce portfolio.
