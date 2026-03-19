# Hosting Guide — Andrew's Log

---

## Recommended: Neocities (free)

**Why Neocities?**
It's the spiritual successor to GeoCities — built specifically for personal,
handcrafted websites like this one. It's free, has no ads, and the community
is full of people making retro, text-heavy, personal sites. It's also
extremely fitting for a site designed to look like 1996.

**How to publish:**

1. Go to https://neocities.org and create a free account.
   - Pick a site name (e.g. `andrewsnotebook`) — your URL will be
     `andrewsnotebook.neocities.org`

2. Once logged in, click **Dashboard**.

3. Click **Upload** and select all the files in your `my-website/` folder.
   - Upload `index.html`, `style.css`, `about.html`
   - Then create a `posts` folder and upload all files inside `posts/`

4. Your site is live immediately.

**How to update (add a new post):**

1. Follow the steps in HOW-TO-ADD-A-POST.md to create and edit your files locally.
2. Log into Neocities > Dashboard > Upload.
3. Upload the new post file (e.g. `posts/tip-gmail-filters.html`)
   and the updated `index.html`.
4. Done. Changes are live in seconds.

---

## Alternative: Netlify Drop (also free, slightly simpler uploading)

**Why Netlify?**
More "professional" infrastructure. Drag-and-drop publishing.
Good if you want a custom domain later.

**How to publish:**

1. Go to https://app.netlify.com/drop
2. Drag your entire `my-website/` folder onto the page.
3. Netlify gives you a random URL (e.g. `lucky-cat-a3f92.netlify.app`).
   You can rename it to something better in the site settings.

**How to update:**

1. Edit your files locally.
2. Go back to https://app.netlify.com/drop
3. Drag the folder again. It asks if you want to update the existing site — say yes.

---

## Custom domain (optional, ~$12/year)

If you want `andrewsnotebook.com` instead of a free subdomain:

1. Buy a domain at Namecheap (https://namecheap.com) or Porkbun (https://porkbun.com).
   Porkbun tends to be slightly cheaper.
2. Both Neocities and Netlify have simple instructions for pointing a custom
   domain at your site — it's about a 10-minute setup.

---

## Summary recommendation

| Option          | Cost  | Ease of updating | Vibe match |
|-----------------|-------|------------------|------------|
| Neocities       | Free  | Good             | Perfect    |
| Netlify Drop    | Free  | Very easy        | Good       |
| Custom domain   | ~$12/yr | Same as above  | Great      |

**Start with Neocities.** It fits the aesthetic perfectly, the community
will appreciate what you're building, and it costs nothing.
