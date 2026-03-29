# How to add content

---

## Adding a post

### Step 1 — Create a new Markdown file

In the `posts/` folder, create a new file. You can duplicate `_TEMPLATE.md`
as a starting point, or create one from scratch. Use a short, descriptive
filename with no spaces:

    tip-gmail-filters.md
    review-kindle-paperwhite.md
    misc-thoughts-on-hiking.md

---

### Step 2 — Fill in the frontmatter

At the very top of the file, add a block like this (called frontmatter):

```
---
layout: post
title: Your Post Title Here
date: 2026-03-18
tag: tip
---
```

- `layout` should always be `post` for posts
- `date` uses the format `YYYY-MM-DD`
- `tag` must be one of: `tip`, `review`, or `misc`

---

### Step 3 — Write your content

Everything below the closing `---` is your post body, written in plain
Markdown. Common formatting:

```markdown
A paragraph is just plain text. Leave a blank line between paragraphs.

### a section heading

- A bulleted list item
- Another item

`Cmd + C` renders as inline code (good for keyboard shortcuts)

> A blockquote — good for verdicts or callouts.
```

---

### Step 4 — Add it to the posts page

Open `index.html` and paste this block at the **top** of the
`<section class="post-list">`, filling in your details:

```html
<article>
  <div class="post-meta">
    2026-03-18 | <span class="tag tag-tip">TIP</span>
  </div>
  <h2><a href="{{ '/posts/your-filename.html' | relative_url }}">Your Post Title Here</a></h2>
  <p class="post-excerpt">
    One or two sentence description of the post.
  </p>
</article>

<hr>
```

Note: the link uses `your-filename.html` even though you wrote a `.md` file —
Jekyll converts it automatically.

---

### Step 5 — Deploy

```bash
git add .
git commit -m "Add post: your title here"
git push
```

GitHub Pages builds the site automatically. It's live within about a minute.

---

## Adding a guide

Guides live in the `guides/` folder. Each guide is a single page covering
one topic, with prose sections and links to related posts.

### Step 1 — Create the guide file

In the `guides/` folder, create a new Markdown file named after the topic:

    streaming.md
    iphone.md
    productivity.md

---

### Step 2 — Fill in the frontmatter

```
---
layout: guide
title: Topic Name Here
---
```

- `layout` should always be `guide` for guides
- `title` is what appears as the page heading automatically

---

### Step 3 — Write your content

Same Markdown syntax as posts. To link to a related post from within a guide:

```markdown
See: [Post title here](../posts/your-post-filename.html)
```

---

### Step 4 — Add it to the guides index

Open `guides/index.html` and add an entry inside the
`<section class="guide-list">`:

```html
<article>
  <h2><a href="{{ '/guides/your-topic.html' | relative_url }}">Topic Name</a></h2>
  <p>One sentence describing what the guide covers.</p>
</article>

<hr>
```

---

### Step 5 — Deploy

```bash
git add .
git commit -m "Add guide: topic name"
git push
```

---

## General tips

- Keep filenames lowercase with hyphens, no spaces.
- Always add new posts at the TOP of the list in `index.html`.
- If a post grows into something reference-worthy, consider turning it
  into a guide (or linking to it from one).
