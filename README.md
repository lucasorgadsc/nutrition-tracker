# Nutrition Tracker — PWA

App de tracking calories et macros avec analyse IA par photo.

## Déploiement sur Vercel (5 min)

### 1. Push sur GitHub
```bash
git init
git add .
git commit -m "init nutrition tracker"
git branch -M main
git remote add origin https://github.com/TON_USERNAME/nutrition-tracker.git
git push -u origin main
```

### 2. Déployer sur Vercel
1. Va sur [vercel.com](https://vercel.com) → connecte ton GitHub
2. Clique **"Add New Project"** → importe ton repo `nutrition-tracker`
3. Clique **Deploy** (les settings par défaut suffisent)

### 3. Ajouter ta clé API Anthropic
1. Dans ton projet Vercel → **Settings** → **Environment Variables**
2. Ajoute :
   - Name : `ANTHROPIC_API_KEY`
   - Value : `sk-ant-...` (ta clé depuis console.anthropic.com)
3. Clique **Save** → **Redeploy**

### 4. Installer sur ton iPhone
1. Ouvre l'URL Vercel dans **Safari** (obligatoire, pas Chrome)
2. Clique le bouton **Partager** (carré avec flèche)
3. **"Sur l'écran d'accueil"**
4. C'est installé comme une vraie app

## Structure
```
calorie-tracker/
├── index.html          # App complète (UI + logique)
├── manifest.json       # Config PWA
├── vercel.json         # Config routing
└── api/
    └── claude.js       # Proxy sécurisé → API Anthropic
```

## Fonctionnalités
- Analyse photo par IA (Claude Vision)
- Saisie manuelle avec lookup automatique des macros
- Journal du jour avec totaux en temps réel
- Historique 30 jours
- Objectifs personnalisables
- 100% offline-capable (données en localStorage)
