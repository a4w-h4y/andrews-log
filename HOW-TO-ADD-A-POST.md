# How to add content

---

## Adding a post

### Step 1 — Copy the template

In the `posts/` folder, duplicate `_TEMPLATE.html` and rename it.
Use a short, descriptive filename with no spaces. Examples:

    tip-gmail-filters.html
    review-kindle-paperwhite.html
    misc-thoughts-on-hiking.html

---

### Step 2 — Edit the post file

Open your new file in any text editor (TextEdit on Mac works fine;
BBEdit or VS Code are better if you have them).

Change these four things:

1. **Title tag** (line 6): `<title>Your Title Here — ANDREW'S LOG</title>`
2. **Date** (in the `post-meta` div): `YYYY-MM-DD`
3. **Tag** (same div): choose one:
   - `<span class="tag tag-tip">TIP</span>`
   - `<span class="tag tag-review">REVIEW</span>`
   - `<span class="tag tag-misc">MISC</span>`
4. **Post title heading**: `<h2>Your Post Title Here</h2>`

Then write your content inside the `<div class="post-body">` section.

Useful HTML you'll use often:

```html
<!-- A paragraph -->
<p>Your text here.</p>

<!-- A section heading -->
<h3>my section</h3>

<!-- A bulleted list -->
<ul>
  <li>Item one</li>
  <li>Item two</li>
</ul>

<!-- Inline code or keyboard shortcut -->
<code>Cmd + C</code>

<!-- A callout / verdict box -->
<blockquote>Verdict: worth it.</blockquote>
```

---

### Step 3 — Add it to the posts page

Open `index.html` in your text editor.

Find this comment near the top of the `<section class="post-list">`:

```html
<!-- POSTS — newest first. To add a new post: ... -->
```

Paste this block **directly below that comment**, filling in your details:

```html
<article>
  <div class="post-meta">
    2026-03-18 | <span class="tag tag-tip">TIP</span>
  </div>
  <h2><a href="posts/your-filename.html">Your Post Title Here</a></h2>
  <p class="post-excerpt">
    One or two sentence description of the post.
  </p>
</article>

<hr>
```

---

### Step 4 — Deploy

See HOSTING-GUIDE.md for how to publish your changes.

---

## Adding a guide

Guides live in the `guides/` folder. Each guide is a single HTML page covering
one topic, with prose sections and links to related posts.

### Step 1 — Create the guide file

In the `guides/` folder, create a new file named after the topic. Examples:

    streaming.html
    iphone.html
    productivity.html

Copy the structure from `guides/macos.html` as your starting point.

---

### Step 2 — Edit the guide file

Change these things:

1. **Title tag**: `<title>Topic — Guides — ANDREW'S LOG</title>`
2. **The `<h2>` heading**: your topic name
3. **The body content**: write topical sections using `<h3>` subheadings and `<p>` paragraphs

To link to a related post from within a guide:

```html
<p>See: <a href="../posts/your-post-filename.html">Post title here</a></p>
```

Note the `../` prefix — guide pages are one level deeper than the root,
so links to posts need to go up one directory first.

---

### Step 3 — Add it to the guides index

Open `guides/index.html` and add an entry inside the
`<section class="guide-list">`:

```html
<article>
  <h2><a href="your-topic.html">Topic Name</a></h2>
  <p>One sentence describing what the guide covers.</p>
</article>

<hr>
```

---

### Step 4 — Deploy

See HOSTING-GUIDE.md for how to publish your changes.

---

## General tips

- Keep filenames lowercase with hyphens, no spaces.
- Always add new posts at the TOP of the list in `index.html`.
- You can preview the site locally by double-clicking any HTML file —
  no server needed.
- If a post grows into something reference-worthy, consider turning it
  into a guide (or linking to it from one).
