# Website — Posts Page Plan
*Created: 2026-07-18*

---

## Goal
Add a **Posts** page to the Nutfah website that displays LinkedIn posts in a clean, browsable format. Serves as a content hub to show expertise and drive engagement.

---

## Navigation Changes

### Navbar
- Rename "Figure Builder" nav item → **"Tools"**
- "Tools" links to a new `tools.html` page (Figure Builder is the first tool there)
- Add **"Posts"** to navbar between "About" and "Tools":

```
Home | Services | About | Posts | Tools | Get a Quote
```

### All 5 HTML files need navbar updated:
- index.html
- services.html
- about.html
- contact.html
- figure-panel-builder.html

---

## Posts Page — posts.html

### Layout
- Single page — no separate file per post
- Posts displayed as **cards in a grid**
- Each card shows: **title + date + short summary (1-2 lines)**
- **Hover** on card → summary becomes visible (or highlighted)
- **Click** on card → post expands inline (accordion/expand panel)
- Expanded view shows full post text + any images
- A **"View on LinkedIn →"** link at the bottom of each expanded post

### Categories (deferred)
- No category filter for now — add later when posts are populated
- Each post will have a `category` field in the HTML so filtering can be added later without restructuring

### Structure of each post block (HTML template)
```html
<div class="post-card" data-category="tutorial">
  <div class="post-header">
    <span class="post-date">2026-06-10</span>
    <h3 class="post-title">Your Post Title Here</h3>
    <p class="post-summary">One or two sentence summary visible on the card.</p>
  </div>
  <div class="post-body" style="display:none;">
    <p>Full post text goes here...</p>
    <img src="posts/images/post1.jpg" alt="..." /> <!-- optional -->
    <a href="https://linkedin.com/..." target="_blank">View on LinkedIn →</a>
  </div>
</div>
```

### How to add a new post
1. Copy the post block template above
2. Paste it at the TOP of the posts list (newest first)
3. Fill in: date, title, summary, full text, optional image, LinkedIn URL
4. Save and upload to GitHub — done

---

## Tools Page — tools.html

### Purpose
A landing page listing all free tools offered by Nutfah. Replaces the direct "Figure Builder" navbar link.

### Current tools
1. **Figure Panel Builder** — browser-based tool to build publication-ready figure panels

### Future tools (to be added)
- TBD — Sedat will provide list

### Layout
- Simple grid of tool cards
- Each card: tool name + short description + "Open Tool →" button

---

## Files to Create
- `posts.html` — the Posts page
- `tools.html` — the Tools landing page

## Files to Edit
- `index.html` — update navbar
- `services.html` — update navbar
- `about.html` — update navbar
- `contact.html` — update navbar
- `figure-panel-builder.html` — update navbar
- `style.css` — add styles for post cards, expand/collapse, tools grid

---

## Open Questions (resolve before building)
- [ ] Do you want images inside posts stored in a `posts/images/` subfolder in the GitHub repo?
- [ ] Should expanded posts show images inline or as a link?
- [ ] How many posts to add at launch — start with 5-10 as a batch?
