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

## Writing content in Markdown

Rather than editing HTML directly, you write posts and guides as plain
Markdown (`.md`) files. GitHub Pages runs Jekyll automatically when you push,
so the Markdown-to-HTML conversion happens on GitHub's servers — no build
step on your end.

---

### How it works

1. You write a `.md` file with a short block of metadata at the top (called
   frontmatter), then plain prose below.
2. You commit and push.
3. GitHub Pages runs Jekyll, converts your `.md` files to HTML, and serves
   the result. The whole process takes about 30–60 seconds.

---

### Frontmatter format

Every Markdown post or guide starts with a `---` block:

```
---
layout: post
title: Mac Keyboard Shortcuts Worth Memorizing
date: 2026-03-18
tag: tip
---

Your post content starts here...
```

The `layout` field tells Jekyll which template to use. Use `post` for posts
and `guide` for guides. Valid tag values are `tip`, `review`, and `misc`.

---

### Folder layout

| File you create | URL on the live site |
|---|---|
| `posts/my-new-post.md` | `/posts/my-new-post.html` |
| `guides/my-new-guide.md` | `/guides/my-new-guide.html` |

---

### Updating the posts list on the homepage

After adding a new post, open `index.html` and add an entry to the top of
the post list:

```html
<article>
  <div class="post-meta">
    2026-03-18 | <span class="tag tag-tip">TIP</span>
  </div>
  <h2><a href="{{ '/posts/my-new-post.html' | relative_url }}">My New Post Title</a></h2>
  <p class="post-excerpt">A one or two sentence description.</p>
</article>

<hr>
```

The homepage list stays hand-edited so you have full control over order
and excerpts.

---

### Publishing changes (the everyday workflow)

```bash
# 1. Stage your new or changed files
git add .

# 2. Commit with a short description
git commit -m "Add post: Mac keyboard shortcuts"

# 3. Push — GitHub Pages builds and deploys automatically
git push
```

That's it. Three commands and your changes are live within about a minute.

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
