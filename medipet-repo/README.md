# Medipet

A gamified medicine-taking companion app for children with interactive pet growth and caregiver oversight.

## Deployment to Vercel

### Prerequisites
- GitHub account
- Vercel account (free tier at [vercel.com](https://vercel.com))

### Step 1: Push to GitHub

```bash
# Initialize git in your local repo
git init
git add .
git commit -m "Initial commit"

# Add your GitHub remote (replace YOUR_USERNAME and REPO_NAME)
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
git branch -M main
git push -u origin main
```

### Step 2: Connect to Vercel

1. Go to [vercel.com/dashboard](https://vercel.com/dashboard)
2. Click "Add New..." → "Project"
3. Select "Import Git Repository"
4. Search for your `medipet` repo and click "Import"
5. Vercel will auto-detect the settings
6. Click "Deploy"

**That's it!** Your app will be live at `https://your-project-name.vercel.app`

### Auto-Deploy
From now on, any push to the `main` branch will automatically trigger a new deployment.

### Optional: Custom Domain
1. In Vercel dashboard, go to your project → Settings → Domains
2. Add your custom domain
3. Follow DNS setup instructions

## Local Development

The app is a single `public/index.html` file — just open it in your browser. No build step needed.

```bash
# For development, you can use Python's built-in server
python3 -m http.server 8000
# Then visit http://localhost:8000/public
```

## File Structure

```
medipet/
├── public/
│   └── index.html          # Self-contained React app (all-in-one)
├── package.json            # Metadata for Vercel
├── vercel.json             # Deployment config
├── .gitignore              # Git ignore rules
└── README.md               # This file
```

## Notes

- **No build required** — the app is already transpiled and bundled in `index.html`
- **External CDN dependencies** — React, ReactDOM, and Babel are loaded from CDN inside the HTML
- **Single deployment** — Vercel simply serves the static files; no Node.js build step
- **Offline-capable** — data is stored in browser `localStorage` per child/caregiver device

## Troubleshooting

**Deploy failed?**
- Check that `vercel.json` is at the repo root
- Ensure `public/index.html` exists
- Wait 2–3 minutes for Vercel's build cache to clear

**App not loading?**
- Check browser console for errors
- Verify CDN links (React, Babel) are reachable
- Try a hard refresh (Ctrl+Shift+R or Cmd+Shift+R)

**Want to edit the code?**
- Edit `public/index.html` directly
- Push changes to GitHub → Vercel auto-deploys
