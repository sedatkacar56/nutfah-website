# Posts Build Progress
*Last updated: 2026-07-18*

---

## What We Are Doing
Converting all LinkedIn posts into individual HTML pages for the Nutfah website.

- **Source file:** `website/posts/linkedinposts.md` — 279 links, one per line
- **Line 1 = post1.html, line 2 = post2.html**, etc. (consecutive numbering)
- **Skip:** Line 197 (jonnytooze — not Sedat's post)
- **No images** — posts are text only, each has a "View on LinkedIn →" link

---

## File Structure
```
website/
  posts.html                  ← index page (all cards go here, newest first)
  posts/
    post1.html                ← individual post pages
    post2.html
    post3.html
    ...
    linkedinposts.md          ← source list of all 279 LinkedIn links
    posts_build_progress.md   ← this file
    example1.html             ← ignore (example/test files)
    example2.html             ← ignore (example/test files)
    images/                   ← ignore for now (no images in new posts)
```

---

## How Each Post Is Built

### Step 1 — Fetch
Use WebFetch on the LinkedIn URL to extract:
- Full post text
- Post date
- Hashtags (to determine category)

### Step 2 — Determine Category
Based on hashtags/content:
- `Tutorial` — how-to, tips, code snippets
- `Single-Cell` — scRNA-seq biology/analysis concepts
- `Tool` — specific tools (Seurat, Scanpy, Cell Ranger, etc.)
- `Career` — postdoc life, motivation, career advice
- `Publication` — paper announcements
- `HPC` — SLURM, Linux, HPC, cloud computing
- `Science` — general science/biology

### Step 3 — Create post HTML
Save as `website/posts/postN.html`
Template: copy structure from example1.html (navbar uses `../` paths, style uses `../style.css`)

### Step 4 — Add card to posts.html
Add card block at the TOP of the posts grid in `website/posts.html` (newest = top)
Card shows: category tag, date, title, summary (visible on hover)

---

## HTML Templates

### Card block for posts.html
```html
<!-- POST N -->
<a href="posts/postN.html" target="_blank" class="post-card">
  <div class="post-card-meta">
    <span class="post-category">Category</span>
    <span class="post-date">YYYY-MM-DD</span>
  </div>
  <h2 class="post-title">Post title here</h2>
  <p class="post-summary">One or two sentence summary visible on hover.</p>
</a>
```

### Individual post page (postN.html)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Post Title | Nutfah Single-cell Omics LLC</title>
  <link rel="stylesheet" href="../style.css"/>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet"/>
</head>
<body>
<nav class="navbar">
  <div class="nav-container">
    <a href="../index.html" class="nav-logo">
      <img src="../LOGO.png" alt="Nutfah Single-cell Omics" class="logo-img"/>
      <span class="nav-company-name">Nutfah Single-cell Omics LLC</span>
    </a>
    <ul class="nav-links">
      <li><a href="../index.html">Home</a></li>
      <li><a href="../services.html">Services</a></li>
      <li><a href="../about.html">About</a></li>
      <li><a href="../posts.html">Posts</a></li>
      <li><a href="../tools.html">Tools</a></li>
      <li><a href="../contact.html" class="nav-cta">Get a Quote</a></li>
    </ul>
  </div>
</nav>
<section class="page-hero">
  <div class="container">
    <div class="post-page-meta">
      <span class="post-category">Category</span>
      <span class="post-date">YYYY-MM-DD</span>
    </div>
    <h1>Post Title</h1>
  </div>
</section>
<section class="post-page-section">
  <div class="container">
    <div class="post-page-body">
      <!-- full post text here -->
      <a href="LINKEDIN_URL" target="_blank" class="post-linkedin-link">View original on LinkedIn →</a>
      <div class="post-back">
        <a href="../posts.html">← Back to Posts</a>
      </div>
    </div>
  </div>
</section>
<footer>
  <div class="container">
    <p>© 2026 Nutfah Single-cell Omics LLC · Remote, Serving Clients Nationwide · <a href="mailto:sedat@nutfahsinglecellomics.com">sedat@nutfahsinglecellomics.com</a></p>
  </div>
</footer>
</body>
</html>
```

---

## Progress

| Batch | Posts | Status | Notes |
|-------|-------|--------|-------|
| Batch 1 | post1–post20 | ⏳ Data fetched, HTML files pending | Lines 1–20 in linkedinposts.md. Data: batch1_data.json |
| Batch 2 | post21–post40 | ⏳ Not started | Lines 21–40 |
| Batch 3 | post41–post60 | ⏳ Not started | Lines 41–60 |
| Batch 4 | post61–post80 | ⏳ Not started | Lines 61–80 |
| Batch 5 | post81–post100 | ⏳ Not started | Lines 81–100 |
| Batch 6 | post101–post120 | ⏳ Not started | Lines 101–120 |
| Batch 7 | post121–post140 | ⏳ Not started | Lines 121–140 |
| Batch 8 | post141–post160 | ⏳ Not started | Lines 141–160 |
| Batch 9 | post161–post180 | ⏳ Not started | Lines 161–180 |
| Batch 10 | post181–post200 | ⏳ Not started | Lines 181–200, skip line 197 |
| Batch 11 | post201–post220 | ⏳ Not started | Lines 201–220 |
| Batch 12 | post221–post240 | ⏳ Not started | Lines 221–240 |
| Batch 13 | post241–post260 | ⏳ Not started | Lines 241–260 |
| Batch 14 | post261–post279 | ⏳ Not started | Lines 261–279 |

---

## After Each Batch
1. Update the batch status above to ✅ Done
2. Push to GitHub:
```bash
git add .
git commit -m "Add posts postX–postY"
git push
```

---

## Notes for Next Session
- Use **Haiku** model for fetching and building (saves tokens)
- Read this file first to see where we left off
- Read `linkedinposts.md` to get the URLs for the next batch
- Cards in `posts.html` go at the TOP (newest first) — but since we're adding oldest-first from the list, add each new card ABOVE the previous one
- After all batches done: consider adding category filter to posts.html
