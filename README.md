# Vikash Kumar — Academic Website

Personal academic website built in plain HTML/CSS — fast, self-maintained, fully portable.

**Live at:** `https://vikashkumar.com` *(once deployed)*

---

## 📁 Files in This Repository

| File | Purpose |
|---|---|
| `index.html` | The entire website — everything is in this one file |
| `cv.pdf` | Your CV (you'll add this — see Step 2 below) |
| `photo.jpg` | Your headshot (optional — see Step 3 below) |
| `README.md` | This guide |

---

## 🚀 Part 1 — Deployment (One-Time Setup, ~30 Minutes)

### Step 1: Create a GitHub Account & Repository
1. Sign up at [github.com](https://github.com) if you don't have an account.
2. Create a new repository named **exactly** `yourusername.github.io`
   (e.g., if your GitHub username is `vikashkumar`, the repo must be `vikashkumar.github.io`).
3. Make it **Public** (required for free GitHub Pages).

### Step 2: Upload the Files
1. On the new repository page, click **"uploading an existing file"** (or **Add file → Upload files**).
2. Drag `index.html` and `README.md` into the upload area.
3. Commit changes.

### Step 3: Add Your CV
1. Save your CV as `cv.pdf` (exact filename, lowercase).
2. Upload it to the repository the same way.
3. The "Download Full CV" button on the site will now work.

### Step 4: Add Your Photo (Optional but Recommended)
1. Save a square headshot as `photo.jpg` (or `.png`).
2. Upload it to the repository.
3. In `index.html`, find this block (around line 240):
   ```html
   <div class="hero-photo">
       <!-- Replace this div with: <img src="photo.jpg" alt="Vikash Kumar"> -->
       Add your<br>headshot here
   </div>
   ```
4. Replace it with:
   ```html
   <div class="hero-photo">
       <img src="photo.jpg" alt="Vikash Kumar">
   </div>
   ```

### Step 5: Enable GitHub Pages
1. In your repository, go to **Settings → Pages** (left sidebar).
2. Under "Source", select **Deploy from a branch**.
3. Branch: **main**, Folder: **/ (root)**.
4. Click **Save**.
5. Wait 1–2 minutes. Your site is now live at `https://yourusername.github.io`.

### Step 6: Connect Your Custom Domain
1. In your registrar (Cloudflare/Porkbun), add these DNS records:

   | Type | Name | Value |
   |---|---|---|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | yourusername.github.io |

2. In GitHub repo → **Settings → Pages → Custom domain**: enter `vikashkumar.com`.
3. Wait 10–60 minutes for propagation.
4. Check **"Enforce HTTPS"** once GitHub finishes issuing the SSL certificate (usually ~10 minutes after DNS propagates).

✅ Your site is now live at `https://vikashkumar.com`.

---

## ✏️ Part 2 — How to Update the Site

All updates happen by editing `index.html`. You can do this two ways:

**Way A — In your browser (easiest):**
1. Go to your GitHub repo → click `index.html` → click the pencil icon ✏️
2. Make your edit
3. Click **Commit changes**
4. Site updates within 30 seconds.

**Way B — On your computer:**
1. Open `index.html` in any text editor (VS Code, Sublime, Notepad++)
2. Edit and save
3. Drag-drop back to GitHub, or use `git push`

---

### How to Update a Paper Status

Find the paper in the `<section id="research">` block. Each paper looks like this:

```html
<div class="paper">
    <div class="paper-title">Closing the Loop on EV Batteries...</div>
    <div class="paper-authors">with Jay Nguyen</div>
    <span class="paper-status">Final manuscript — ready for submission</span>
    <p class="paper-abstract">...</p>
    <p class="paper-meta">Target: M&amp;SOM, by Winter 2026 · Funded by SSHRC</p>
</div>
```

To change the status, just edit the text inside `<span class="paper-status">`:

| Stage | Suggested status text |
|---|---|
| Drafting | `Working paper · Draft in progress` |
| Ready to submit | `Final manuscript — ready for submission` |
| Submitted | `Under review at [Journal Name]` |
| R&R | `Revise and resubmit at [Journal]` |
| Accepted | `Forthcoming at [Journal]` |
| Published | Remove the status span; add the citation instead |

---

### How to Add a New Paper

Copy this template and paste it inside `<section id="research">` (above or below an existing paper):

```html
<div class="paper">
    <div class="paper-title">YOUR PAPER TITLE HERE</div>
    <div class="paper-authors">with [Coauthor Names]</div>
    <span class="paper-status">Working paper · 2026</span>
    <p class="paper-abstract">
        [3–4 sentence abstract describing the paper's contribution.]
    </p>
    <p class="paper-meta">Target: [Journal Name]</p>
</div>
```

---

### How to Add a News Item

Inside `<section id="news">`, copy this template and add it at the **top** of the news list (newest first):

```html
<div class="news-item">
    <div class="news-date">Month YYYY</div>
    <div class="news-text">[Your news, e.g., "Presented at INFORMS Annual Meeting, Seattle."]</div>
</div>
```

**Tip:** Keep the news list to 4–6 items. When adding a new one, delete the oldest.

---

### How to Update the Bio

Find `<div class="bio">` and edit the text inside the `<p>` tags. Keep it under 120 words.

---

### How to Update CV / Awards / Service

Each entry follows the same pattern:

```html
<div class="cv-item">
    <div class="cv-year">YEAR</div>
    <div class="cv-text">
        <strong>Title or Award</strong>
        <div class="detail">Optional secondary detail in muted text</div>
    </div>
</div>
```

Copy, paste, edit.

---

### How to Swap the Photo

1. Upload a new `photo.jpg` to the repo (overwriting the old one).
2. Hard-refresh your browser (Ctrl+Shift+R on Windows, Cmd+Shift+R on Mac) to bypass cache.

---

### How to Update the CV PDF

1. Upload your new `cv.pdf` to the repo (overwriting the old one).
2. That's it — the download link automatically serves the new file.

---

## 🎨 Part 3 — Customization (Optional)

### Change the Accent Colour
Open `index.html`, find the `:root` block near the top (around line 25):

```css
:root {
    --ivey-green: #034638;          /* main heading colour */
    --ivey-green-light: #0a6b54;    /* hover state */
    --accent: #c8aa6e;              /* warm gold accent */
    ...
}
```

Change the hex codes to re-theme the whole site. Some safe alternatives:
- Navy blue: `#1a3a5c`
- Burgundy: `#7d2935`
- Forest green: `#1f4a30`
- Charcoal (minimalist): `#1a1a1a`

### Add Social Links
Find the `<div class="contact-row">` block in the About section. The links currently show `href="#"` for Google Scholar, SSRN, and ORCID. Replace `#` with your actual profile URLs once you have them.

---

## 🧭 Part 4 — What to Do Right After Going Live

| Task | Why | Time |
|---|---|---|
| Create [Google Scholar](https://scholar.google.com) profile | Indexes future work, even before publications | 5 min |
| Register for [ORCID](https://orcid.org) | Permanent researcher ID, journals require it | 5 min |
| Set LinkedIn custom URL to `/in/vikashkumar` | Matches your domain | 2 min |
| Generate a QR code at [qr-code-generator.com](https://qr-code-generator.com) pointing to `vikashkumar.com` | For Slide 6 of your workshop deck and CV footer | 5 min |
| Add `vikashkumar.com` to your email signature | Passive promotion | 1 min |
| Add the URL to your Ivey PhD profile page | Drives institutional traffic to your real site | 5 min |
| Submit your site URL to Google Search Console | Helps Google index you faster | 5 min |

---

## 💡 Maintenance Cadence

| Frequency | What to do |
|---|---|
| **After every paper status change** | Update the relevant `<span class="paper-status">` line |
| **After every conference talk or award** | Add a news item |
| **Once a semester** | Trim old news items, refresh photo if needed |
| **Once a year** | Verify domain auto-renewal is on; update CV PDF |

A well-maintained academic site takes ~10 minutes per month.

---

## 🆘 Troubleshooting

| Problem | Fix |
|---|---|
| Site shows old content after I updated | Hard-refresh (Ctrl+Shift+R / Cmd+Shift+R) to bypass browser cache |
| Custom domain not working | Wait up to 24 hours for DNS propagation; check DNS records at [dnschecker.org](https://dnschecker.org) |
| HTTPS not working | Wait 10–15 min after DNS propagates, then toggle "Enforce HTTPS" in GitHub Pages settings |
| I broke the HTML | Go to GitHub repo → click `index.html` → "History" → restore previous version |

---

**Built once. Yours forever.**
