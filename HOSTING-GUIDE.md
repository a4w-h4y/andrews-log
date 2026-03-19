# Hosting Guide — Andrew's Log

---

## Hosting on GitHub Pages (free)

Your site lives in a Git repository, which means GitHub Pages can serve it
directly. Every time you push changes to GitHub, the site updates automatically
within a minute or two.

---

### One-time setup

**Step 1 — Create a GitHub account**

Go to https://github.com and sign up if you don't have an account.

**Step 2 — Create a new repository**

1. Click the **+** in the top-right corner → **New repository**
2. Name it `andrewslog` (or anything you like)
3. Leave it **Public**
4. Do NOT check "Add a README" — your files are already ready
5. Click **Create repository**

**Step 3 — Connect your local folder to GitHub**

GitHub will show you a page with setup commands. Run these in Terminal,
inside your `my-website` folder:

```bash
git remote add origin https://github.com/YOUR-USERNAME/andrewslog.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your actual GitHub username.

**Step 4 — Enable GitHub Pages**

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (in the left sidebar)
3. Under "Source", select **Deploy from a branch**
4. Set the branch to **main** and the folder to **/ (root)**
5. Click **Save**

Your site will be live at:
`https://YOUR-USERNAME.github.io/andrewslog`

It may take a minute or two the first time.

**Step 5 — Custom domain (optional, ~$12/year)**

If you want `andrewslog.com` instead of the GitHub URL:

1. Buy a domain at Namecheap (https://namecheap.com) or
   Porkbun (https://porkbun.com)
2. In your repo's **Settings → Pages**, enter your custom domain
3. Follow GitHub's DNS instructions — it takes about 10 minutes to configure

---

### Publishing changes (the everyday workflow)

Every time you add or edit a post, guide, or any other file:

```bash
# 1. Stage your changed files
git add .

# 2. Commit with a short description of what you changed
git commit -m "Add post: Mac keyboard shortcuts"

# 3. Push to GitHub — the site updates automatically
git push
```

That's it. Three commands and your changes are live.

---

### Useful Git commands to know

| Command | What it does |
|---|---|
| `git status` | Shows which files have changed since your last commit |
| `git add .` | Stages all changed files for the next commit |
| `git add filename.html` | Stages one specific file |
| `git commit -m "message"` | Saves a snapshot with a description |
| `git push` | Sends your commits to GitHub |
| `git log --oneline` | Shows a compact history of all your commits |
| `git diff` | Shows exactly what changed in your files |

---

### If something goes wrong

If you accidentally break something and want to go back to your last
working version:

```bash
# Discard all unsaved changes (use with care)
git restore .

# See the history to find a good commit to go back to
git log --oneline

# Go back to a specific commit (replace abc1234 with the commit ID)
git checkout abc1234 -- filename.html
```
