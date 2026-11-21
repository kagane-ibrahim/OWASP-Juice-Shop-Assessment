# Détection de prompt injection

## Présentation

Projet académique de détection et de blocage local de tentatives de prompt injection. La solution combine un moteur de règles fondé sur des expressions régulières et une analyse sémantique confiée à un juge LLM. Elle comprend un score de risque et une journalisation au format JSON.

## Technologies

Python, Ollama, Phi-3 Mini, Streamlit, expressions régulières et JSON.

## Évaluation rapportée

L’évaluation porte sur 30 scénarios : 19 attaques et 11 demandes légitimes. Les informations disponibles ne fournissent pas de métriques chiffrées séparées pour le moteur de règles et le juge LLM. Aucun taux de détection, de faux positifs ou autre score par composant n’est donc avancé ici.

## Cadre et limites

Le projet est décrit comme une solution exécutée localement. Cette présentation reprend les informations fournies pour le portfolio ; le code source et les documents de travail n’ont pas été copiés dans ce dépôt.
