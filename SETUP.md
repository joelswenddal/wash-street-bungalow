# Vacation Rental Site — Setup & Dev Guide

## Project Structure

```
vacation-rental-site/
├── index.html          ← Welcome/landing page
├── css/
│   └── style.css       ← All styles (edit here)
├── js/
│   └── main.js         ← Nav toggle, scroll animations
├── pages/
│   ├── dining.html
│   ├── nightlife.html
│   ├── shopping.html
│   └── activities.html
└── img/                ← Drop photos here
```

---

## 1. One-Time GitHub Setup

### Create the repo
1. Go to [github.com/new](https://github.com/new)
2. Name it: `lakeview-suite` (or whatever you like)
3. Set to **Public** (required for free GH Pages)
4. Check **Add a README file**
5. Click **Create repository**

### Enable GitHub Pages
1. In your repo → **Settings** → **Pages** (left sidebar)
2. Source: **Deploy from a branch**
3. Branch: `main` / folder: `/ (root)`
4. Save
5. Your URL will be: `https://yourusername.github.io/lakeview-suite/`

---

## 2. Local Dev Environment (VS Code)

### Clone the repo
```bash
git clone https://github.com/yourusername/lakeview-suite.git
cd lakeview-suite
```

### Copy the site files in
Drop all the files from this project into that folder, maintaining the structure above.

### Install the Live Server extension in VS Code
- Extension ID: `ritwickdey.LiveServer`
- Right-click `index.html` → **Open with Live Server**
- Edits hot-reload in the browser automatically

### Recommended VS Code extensions
- **Live Server** — local preview with hot reload
- **Prettier** — auto-format HTML/CSS/JS on save
- **GitLens** — inline git blame and history

---

## 3. Day-to-Day Workflow

```bash
# Pull latest before editing
git pull

# Make edits in VS Code (Live Server previews instantly)

# When ready to publish:
git add .
git commit -m "Add new dining spot: Osteria Canto"
git push
```

GitHub Pages deploys automatically on push to `main`. Changes go live in ~30 seconds to 2 minutes.

---

## 4. Adding a New Recommendation

Open any page in `pages/` and copy this block inside `.rec-list`:

```html
<div class="rec-item fade-in">
  <div class="rec-body">
    <div class="rec-name">Place Name</div>
    <div class="rec-tags">
      <span class="tag">Tag 1</span>
      <span class="tag">$$</span>
    </div>
    <div class="rec-note">Your note about this place — what makes it special, insider tips, etc.</div>
  </div>
  <a class="rec-link" href="https://PLACE-URL-HERE" target="_blank" rel="noopener">Visit site →</a>
</div>
```

**Tag ideas for `$$` pricing:** `$` `$$` `$$$` `Free`
**Category tags:** anything descriptive — `Brunch`, `Cocktails`, `Outdoor`, `Live music`, etc.

---

## 5. Customizing the Welcome Page

In `index.html`, update:
- **Property name**: search for `The Lakeview Suite` (appears in header logo, footer, page title)
- **WiFi / check-out / parking info**: find the `.info-list` section
- **Intro text**: find `Your guide to the neighborhood`

---

## 6. Adding Photos

1. Drop your image into `/img/` (JPEG or WebP recommended, ~1200px wide)
2. Add an `<img>` tag wherever you want it, e.g.:

```html
<img src="img/your-photo.jpg" alt="Description" style="width:100%; border-radius:4px; margin-bottom:2rem;">
```

---

## 7. Custom Domain (Optional)

If you have a domain (e.g., `lakeviewsuite.com`):
1. In your DNS provider, add a CNAME record: `www` → `yourusername.github.io`
2. In GitHub repo → Settings → Pages → Custom domain → enter `www.lakeviewsuite.com`
3. Check **Enforce HTTPS**

---

## 8. QR Code for Guests

Once your site is live:
1. Go to [qr.io](https://qr.io) or [qrcode-monkey.com](https://qrcode-monkey.com)
2. Enter your GH Pages URL
3. Download as PNG or SVG
4. Print and laminate for the rental

---

*That's the full setup. Push to `main`, it's live. Happy hosting!*
