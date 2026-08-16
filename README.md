# Workflow n8n — Claude + LinkedIn

Ce dépôt contient un workflow **n8n** prêt à importer qui connecte votre compte **Claude (Anthropic)** à votre compte **LinkedIn** pour générer et publier automatiquement des posts.

## Fonctionnement

```
Déclencheur (planifié ou manuel)
        │
        ▼
   Définir le sujet
        │
        ▼
 Claude génère le texte du post (API Anthropic)
        │
        ▼
 Extraction du texte généré
        │
        ▼
   Publication sur LinkedIn
```

Fichier du workflow : [`n8n-workflows/claude-linkedin-content-poster.json`](n8n-workflows/claude-linkedin-content-poster.json)

## Prérequis

1. Une instance **n8n** (cloud ou self-hosted) avec le nœud **LinkedIn** disponible (inclus par défaut dans n8n).
2. Une **clé API Anthropic** (Claude) : https://console.anthropic.com/ → *Settings → API Keys*.
3. Une **application LinkedIn** créée sur https://www.linkedin.com/developers/apps avec :
   - Le produit **"Share on LinkedIn"** (ou **"Community Management API"**) activé.
   - Les scopes OAuth2 `openid`, `profile`, `w_member_social` (pour publier en votre nom).
   - Une URL de redirection OAuth pointant vers votre instance n8n (n8n l'affiche automatiquement lors de la création des identifiants).

## Étape 1 — Importer le workflow

1. Dans n8n : **Workflows → Import from File**.
2. Sélectionnez `n8n-workflows/claude-linkedin-content-poster.json`.

## Étape 2 — Configurer les identifiants Claude

1. Dans n8n : **Credentials → New → Anthropic API**.
2. Collez votre clé API Anthropic.
3. Ouvrez le nœud **"Claude - Génération du contenu"** dans le workflow et sélectionnez cet identifiant.

## Étape 3 — Configurer les identifiants LinkedIn

1. Dans n8n : **Credentials → New → LinkedIn OAuth2 API**.
2. Renseignez le **Client ID** et le **Client Secret** de votre application LinkedIn.
3. Cliquez sur **Connect my account** et autorisez l'accès depuis votre compte LinkedIn.
4. Ouvrez le nœud **"Publier sur LinkedIn"** et sélectionnez cet identifiant.

## Étape 4 — Personnaliser

- **Sujet des posts** : modifiez les champs `topic` et `tone` dans le nœud **"Sujet du post"**, ou remplacez-les par une source dynamique (Google Sheets, Airtable, RSS, etc.) branchée avant ce nœud.
- **Fréquence de publication** : ajustez le nœud **"Planification quotidienne"** (`Schedule Trigger`) — heure, jours, intervalle.
- **Modèle Claude** : changez `"model"` dans le corps JSON du nœud HTTP Request (ex. `claude-sonnet-4-5`, `claude-opus-4-5`).
- **Longueur / ton du post** : ajustez le prompt envoyé à Claude dans ce même nœud.

## Étape 5 — Tester

1. Cliquez sur **"Test manuel"** puis **Execute Workflow**.
2. Vérifiez le texte généré dans le nœud **"Extraire le texte du post"**.
3. Vérifiez que le post apparaît bien sur votre profil LinkedIn.
4. Une fois validé, **activez** le workflow (toggle en haut à droite) pour que la planification automatique prenne le relais.

## Sécurité

- Les clés API (Anthropic, LinkedIn) sont stockées uniquement dans le gestionnaire d'identifiants chiffré de n8n, jamais dans le fichier du workflow.
- Le token OAuth2 LinkedIn est rafraîchi automatiquement par n8n.
- Pensez à limiter les scopes LinkedIn au strict nécessaire (`w_member_social` suffit pour publier des posts texte).
