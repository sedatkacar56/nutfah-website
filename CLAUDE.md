# Nutfah Single-cell Omics Website — AI Session Rules

## Project Overview
Pure HTML/CSS/JS website hosted on GitHub Pages at nutfahsinglecellomics.com.
No frameworks, no build step. All pages are static HTML files.

## Adding a New LinkedIn Post

### Current post count: 241 (post241.html is the newest)
- Higher numbers = older posts. post1.html is oldest, post241.html is newest.
- Next post to create: post242.html

### Step-by-step to add a new post

**1. Create `posts/post242.html`** (increment number each time)

Copy the structure from any recent post (e.g. post241.html):
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>POST TITLE | Nutfah</title>
  <link rel="stylesheet" href="../style.css"/>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet"/>
</head>
<body>
<nav class="navbar">...</nav>  <!-- copy from any existing post -->
<section class="page-hero"><div class="container"><div class="post-page-meta"><span class="post-category">CATEGORY</span><span class="post-date">YYYY-MM-DD</span></div><h1>POST TITLE</h1></div></section>
<section class="post-page-section"><div class="container"><div class="post-page-body">
<!-- post content as <p> tags, <pre><code> for code blocks -->
<a href="LINKEDIN_URL" target="_blank" class="post-linkedin-link">View on LinkedIn →</a>
<div class="post-back"><a href="../posts.html">← Back to Posts</a></div>
</div></div></section>
<footer>...</footer>  <!-- copy from any existing post -->
</body>
</html>
```

**Categories** (use exactly one):
- Tutorial
- Tool
- Career
- HPC
- Research

**2. Create `posts/post242.md`** (LOCAL ONLY — never git add this)

Plain text version of the LinkedIn post content (with emojis, hashtags preserved).
Used as a local draft reference for re-posting on LinkedIn.

**3. Update `posts.html`** — add the new post to the JS array at the TOP (newest first):

Find the `const posts = [` line and insert at the very beginning:
```js
{f:"posts/post242.html", cat:"CATEGORY", g:"GROUP", d:"YYYY-MM-DD", t:"POST TITLE"},
```

Group mapping (`g` field):
- Tutorial → `"tutorial"`
- Tool → `"tool"`
- Career → `"career"`
- HPC → `"hpc"`
- Research → `"research"`
- Anything else (Reflection, Networking, etc.) → `"other"`

Also update the hero text: change `"241 posts"` → `"242 posts"` and the All button count.

**4. Git: stage and push only HTML files**
```
git add posts/post242.html posts.html
git commit -m "Add post242: POST TITLE"
git push
```

**NEVER stage .md files.** They are local-only drafts.

---

## What the user provides to add a post

Option A — Paste the LinkedIn post text:
- User pastes the full post text (with emojis, hashtags)
- AI writes the HTML post page and .md file
- AI updates posts.html
- AI commits and pushes

Option B — Provide LinkedIn URL only:
- AI writes a post title and category based on the URL/context
- Same steps as Option A
- LinkedIn URL goes in the `<a class="post-linkedin-link">` tag

---

## Key file locations
- Post HTML files: `posts/postN.html`
- Post draft files (local only): `posts/postN.md`
- Posts index page: `posts.html`
- Stylesheet: `style.css`
- Homepage: `index.html`

## Git remote
- GitHub repo: https://github.com/sedatkacar56/nutfah-website
- Branch: main
- Live site: https://nutfahsinglecellomics.com

## Critical rules
1. `.md` files are NEVER committed or pushed. Local only.
2. Always add new posts to the TOP of the `posts` JS array in posts.html (newest first).
3. Post numbers go UP for new posts (241 → 242 → 243...).
4. The `posts.html` hero text and All badge count must be updated when adding a post.
5. Copy navbar and footer exactly from an existing post HTML file — do not rewrite them.
