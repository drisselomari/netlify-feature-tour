# Workflows n8n — Cabinet de conseil

## `veille-appels-offres.json`

Veille quotidienne des marchés/appels d'offres pertinents pour le cabinet, avec qualification automatique par Claude et envoi d'un digest par e-mail.

**Fonctionnement :**
1. Déclenchement quotidien (7h).
2. Lecture d'un flux RSS (typiquement une alerte Google Alerts sur des mots-clés comme "appel d'offres ingénierie pédagogique Maroc").
3. Filtrage des éléments déjà vus lors des exécutions précédentes.
4. Qualification de chaque opportunité par Claude (pertinence, score, client probable, échéance, angle d'approche).
5. Ne garde que les opportunités avec un score ≥ 3/5.
6. Construction et envoi d'un digest HTML récapitulatif par e-mail.

**Configuration requise :**
- Identifiant **Anthropic API** (déjà utilisé par le workflow `claude-linkedin-content-poster.json`, cf. PR dédiée).
- Une ou plusieurs alertes **Google Alerts** (google.com/alerts) sur les mots-clés de veille, dont on récupère l'URL du flux RSS pour le nœud "Flux RSS - Google Alerts".
- Identifiant **SMTP** pour l'envoi du digest (nœud "Envoyer le digest") — adapter `fromEmail` et `toEmail`.

**Personnalisation :**
- Ajouter plusieurs flux RSS (une alerte par thématique) en dupliquant le nœud RSS et en fusionnant les résultats avec un nœud *Merge* avant le filtrage.
- Ajuster le seuil de score (nœud "Score >= 3 ?") selon le volume d'opportunités souhaité.
- Remplacer l'envoi par e-mail par une notification Slack, une ligne ajoutée dans un Google Sheet, ou une carte créée dans Notion, selon les outils déjà utilisés par le cabinet.

## `claude-linkedin-content-poster.json`

Génération et publication automatique de contenu LinkedIn via l'API Claude — utile pour construire la visibilité du cabinet en amont de la prospection. Livré séparément (voir la pull request dédiée "Add n8n workflow connecting Claude and LinkedIn").
