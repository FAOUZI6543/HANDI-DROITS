# CarthagoLex - Dashboard Handi-Droits avec Assistant IA

Dashboard juridique expert sur le droit du handicap, avec assistant IA intégré propulsé par Qwen 3.6 Plus.

## 🚀 Déploiement en 1 clic

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/VOTRE-USERNAME/carthagolex-site)

## ⚙️ Configuration requise

Après le déploiement, ajoutez votre clé API OpenRouter :

1. Allez dans **Netlify Dashboard** → **Site settings** → **Environment variables**
2. Cliquez sur **Add a variable**
3. Ajoutez :
   - **Key** : `OPENROUTER_KEY`
   - **Value** : votre clé API OpenRouter (créez-la sur https://openrouter.ai/keys)
   - **Scopes** : cochez **Functions**
4. Cliquez sur **Save**
5. Redéployez le site (**Deploys** → **Trigger deploy** → **Deploy site**)

## 📋 Fonctionnalités

- **Dashboard juridique complet** : AAH, PCH, MDPH, CMI, RQTH, AEEH, logement, emploi
- **Assistant IA CarthagoLex** : chatbot juridique avec recherche web en temps réel
- **Citations précises** : articles CASF, CSS, Code du travail + jurisprudence récente
- **Recherche web activée** : le modèle Qwen consulte Internet pour vérifier les textes à jour

## 🔒 Sécurité

- La clé API OpenRouter reste côté serveur (Netlify Functions)
- Jamais exposée dans le code HTML ni dans le navigateur
- Pas de données utilisateur stockées

## 🛠️ Architecture technique

```
┌─────────────────┐
│  index.html     │  (Frontend : contenu juridique + chatbot)
└────────┬────────┘
         │ fetch('/.netlify/functions/ask')
         ▼
┌─────────────────┐
│  ask.mjs        │  (Netlify Function - relais sécurisé)
└────────┬────────┘
         │ API OpenRouter (Qwen 3.6 Plus :online)
         ▼
┌─────────────────┐
│  OpenRouter AI  │  (Recherche web + génération réponse)
└─────────────────┘
```

## 📝 Licence

Contenu juridique : Domaine public (textes officiels)
Code : MIT License
