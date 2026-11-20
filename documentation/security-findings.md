# Registre des observations et constats potentiels

- **Cible :** OWASP Juice Shop, instance locale `http://localhost:3000`
- **Statut global :** observations préliminaires ; aucune vulnérabilité confirmée

Les éléments ci-dessous sont des observations préliminaires communiquées par l’utilisateur. Les preuves originales (captures, requêtes/réponses HTTP ou journaux) ne sont pas disponibles ; leur collecte est **Non collectée**. Les éléments sont à investiguer et ne sont pas des vulnérabilités confirmées.

## OBS-01 — Réponse HTTP 500 lors d’une interaction avec le profil

- **Description :** Une erreur HTTP 500 inattendue aurait été affichée lors d’une interaction antérieure avec User Profile. Le texte rapporté est `Blocked illegal activity by ::ffff:172.17.0.1`. L’emplacement indiqué dans le message est `userProfile.js:81:18`. Le déclencheur exact, le contenu complet de la réponse et la cause ne sont pas établis ici.
- **Fonctionnalité concernée :** User Profile.
- **Preuve disponible :** Texte d’erreur et emplacement fournis par l’utilisateur. Capture d’écran, requête HTTP, réponse brute et journal serveur : **Non collectée**.
- **Impact :** Non déterminé.
- **Sévérité :** Not assessed (non évaluée).
- **Statut :** À investiguer (*Requires further investigation*).
- **Vérification recommandée :** Reproduire manuellement dans l’instance locale avec un compte de test, conserver la réponse HTTP et le journal correspondant, puis déterminer si des détails internes sont effectivement exposés au client et dans quelles conditions. Ne pas tester de charge utile destructive.

## OBS-02 — Parcours « Forgot Password » : seul le champ Email semblait accessible

- **Description :** Lors de l’observation manuelle, seul un champ Email semblait accessible. L’observation ne permet pas de déterminer si d’autres champs apparaissent à une étape ultérieure ou dans un autre état du parcours.
- **Fonctionnalité concernée :** récupération de mot de passe.
- **Preuve disponible :** Observation rapportée par l’utilisateur. Capture d’écran, requête HTTP et réponse : **Non collectée**.
- **Impact :** Non déterminé.
- **Sévérité :** Not assessed (non évaluée).
- **Statut :** À investiguer (*Requires further investigation*).
- **Vérification recommandée :** Parcourir manuellement le flux complet avec un compte de test, noter les champs et messages à chaque étape, puis vérifier les réponses HTTP et les contrôles serveur sans finaliser une modification de compte.

## OBS-03 — « Last Login IP » affiche `?`

- **Description :** La valeur affichée dans le champ ou la section Last Login IP était `?`. L’exactitude de cette information et sa source côté serveur n’ont pas été vérifiées.
- **Fonctionnalité concernée :** informations de dernière connexion du compte.
- **Preuve disponible :** Valeur rapportée par l’utilisateur. Capture d’écran, requête HTTP et réponse : **Non collectée**.
- **Impact :** Non déterminé.
- **Sévérité :** Not assessed (non évaluée).
- **Statut :** À investiguer (*Requires further investigation*).
- **Vérification recommandée :** Comparer l’affichage avec les données de connexion générées par une connexion de test contrôlée et avec la source serveur prévue, en tenant compte de la configuration des proxys. Éviter de conclure sur la base de la seule valeur `?`.

## Conclusion du registre

Ces trois éléments sont des observations à vérifier. Aucun n’est qualifié ici de vulnérabilité confirmée et aucune sévérité n’est attribuée.
