# Reconnaissance initiale – OWASP Juice Shop

## 1. Informations générales

- **Application :** OWASP Juice Shop
- **Version affichée :** v20.4.0-SNAPSHOT
- **Environnement :** conteneur Docker local
- **URL :** [http://localhost:3000](http://localhost:3000)
- **Date :** 13 novembre 2026

## 2. Fonctionnalités identifiées

Les fonctionnalités suivantes ont été repérées lors d’une navigation manuelle préliminaire :

1. Page d’accueil (Home)
2. Authentification : Login / Register
3. Recherche de produits (Search)
4. Catalogue des produits (Products)
5. Panier d’achat (Basket)
6. Contact / commentaires clients (Customer Feedback)

## 3. Observations

- **Page d’accueil (Home)** — Présente l’application et permet d’accéder à ses principales sections. Elle est utile pour comprendre les parcours proposés et les points d’entrée visibles par un visiteur.
- **Authentification : Login / Register** — Permet de se connecter ou de créer un compte. Ces fonctions sont pertinentes pour examiner ultérieurement la validation des entrées, la gestion des comptes et les sessions.
- **Recherche de produits (Search)** — Aide à retrouver des articles à partir d’une requête. La façon dont une application traite et affiche cette requête peut être pertinente lors d’une analyse de sécurité.
- **Catalogue des produits (Products)** — Affiche les articles disponibles et leurs informations. Cette section permet de repérer les données présentées et les interactions possibles avec les produits.
- **Panier d’achat (Basket)** — Regroupe les articles sélectionnés avant une commande. Il pourra être utile d’observer comment le panier et son contenu sont associés à une session ou à un compte.
- **Contact / commentaires clients (Customer Feedback)** — Permet de transmettre un message ou un commentaire. Les champs de saisie et l’affichage des commentaires peuvent être pertinents pour une analyse ultérieure.

Ces éléments sont des observations de fonctionnalités. Ils ne constituent pas des constats de vulnérabilité.

## 4. Limites de cette reconnaissance

Cette étape correspond uniquement à une exploration manuelle préliminaire de l’application. Aucune vulnérabilité n’a été confirmée. Aucune exploitation ni aucun balayage automatisé n’a été effectué.

## 5. Prochaines étapes

- Inspecter les parcours d’authentification et d’inscription.
- Observer les requêtes HTTP avec Burp Suite Community.
- Documenter les problèmes de sécurité potentiels uniquement après vérification.
