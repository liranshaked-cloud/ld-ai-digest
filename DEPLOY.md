# Deploy Instructions — L&D + AI Digest

## One-time setup (takes ~5 minutes)

### Step 1: Create GitHub repo

1. Go to https://github.com/new
2. Name: `ld-ai-digest`
3. Set to **Public** (required for free Render hosting)
4. Click "Create repository"

### Step 2: Push these files to GitHub

Open Terminal, navigate to the `ld-digest-site` folder, then run:

```bash
cd /path/to/ld-digest-site   # replace with actual path

git init
git add .
git commit -m "Issue #1 — July 1, 2026"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ld-ai-digest.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username.

### Step 3: Connect to Render

1. Go to https://render.com and sign in with GitHub
2. Click **New → Static Site**
3. Select the `ld-ai-digest` repo
4. Settings:
   - **Build Command**: (leave empty)
   - **Publish Directory**: `.`
5. Click **Create Static Site**

Your site will be live at: `https://ld-ai-digest.onrender.com`

---

## Every Monday (automated)

Claude generates the new issue HTML and adds it to:
```
issues/YYYY-MM-DD/index.html
```

To publish, commit and push:
```bash
git add .
git commit -m "Issue #N — DATE"
git push
```

Render auto-deploys on every push. The new issue appears on the site within ~30 seconds.

---

## Monthly digest

End of each month, Claude generates:
```
monthly/YYYY-MM/index.html
```

Same process — commit and push.
