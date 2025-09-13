
# Simon Game — Deploy to Vercel (GitHub import)

This is a small static site (HTML/CSS/JS). The easiest production-friendly flow is to push the project to GitHub and import it into Vercel for automatic deployments.

Step 1 — Prepare the repo locally

1. Open PowerShell in the project folder (where `index.html` lives).

2. (Optional) Create a `.gitignore` to avoid committing unnecessary files. A sample is included in this repo.

Step 2 — Create a GitHub repository and push

You can create a GitHub repo via the website or use the `gh` CLI. Below are plain `git` commands for PowerShell; replace `<your-username>` and `<repo-name>` with your values.

```powershell
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

If you prefer `gh` (GitHub CLI) and have it installed:

```powershell
gh repo create <your-username>/<repo-name> --public --source=. --remote=origin --push
```

Step 3 — Import into Vercel

1. Visit https://vercel.com and log in (or sign up).
2. Click "New Project" → "Import Git Repository" and connect your GitHub account if you haven't already.
3. Select the repo you just pushed.
4. Vercel will detect a static project. Defaults are fine. Click "Deploy".

Vercel will build and deploy your site. After the first deploy, any new pushes to `main` will trigger automatic redeploys.

Troubleshooting & tips

- If Vercel shows a 404 on first load, ensure `vercel.json` is present at the repository root — this repo includes it and sets a fallback to `index.html`.
- If your push fails due to authentication, follow GitHub's prompts to authenticate or use a personal access token as instructed by GitHub.
- To preview locally, you can install a tiny static server (optional):

```powershell
npm i -g serve
serve .
```

If you'd like, I can:
- Create a `package.json` and a `preview` script that runs a dev server locally.
- Walk through creating the GitHub repository from the web UI and then complete the Vercel import step-by-step while you follow along.

