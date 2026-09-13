# alberhasky.github.io

Personal academic website for Max Alberhasky, Ph.D. — Assistant Professor of Marketing, California State University, Long Beach.

Single-page static site. No build step, no dependencies, no frameworks. Everything lives in `index.html`.

---

## Publish it

### Option A — command line

From inside this folder:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/alberhasky/alberhasky.github.io.git
git push -u origin main
```

You'll need to create the empty repo first at <https://github.com/new> — name it exactly `alberhasky.github.io`, set it Public, and leave every initialization checkbox unticked.

### Option B — no command line

1. Go to <https://github.com/new>.
2. **Repository name:** `alberhasky.github.io` — exactly that. (This name is what makes GitHub serve it at `https://alberhasky.github.io`.)
3. Set it **Public**, leave every checkbox unticked, click **Create repository**.
4. On the empty repo page, click **uploading an existing file**.
5. Drag in `index.html`, `README.md`, `.nojekyll`, and the whole `assets` folder. Click **Commit changes**.

### Then, either way

Go to **Settings → Pages**. Under "Build and deployment", set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, and Save. Wait about a minute, then open <https://alberhasky.github.io>.

---

## What's in here

```
index.html                    the entire site
assets/cv.pdf                 your CV (August 2026) — all "CV" links point here
assets/max-alberhasky.jpg     your headshot
.nojekyll                     tells GitHub Pages to serve the files as-is
```

To post a newer CV later, just overwrite `assets/cv.pdf`. No code change needed.

---

## Using your own domain

If you want `maxalberhasky.com` to point here instead of Weebly:

1. Create a file named `CNAME` in this repo containing one line: `www.maxalberhasky.com`
2. At your registrar, add a CNAME record for `www` pointing to `alberhasky.github.io`
3. In **Settings → Pages**, enter the domain under "Custom domain" and tick **Enforce HTTPS**.

---

## Editing content

Everything is in `index.html`. The lists that change most often are plain JavaScript arrays near the bottom of the file:

| What | Where |
|---|---|
| Peer-reviewed publications | `<div class="pub-list" id="pubList">` — one `<article class="pub">` each |
| Working papers | the second `.pub-list`, under "Working papers & work in progress" |
| Conference presentations | the `CONFS` array |
| Awards and fellowships | the `HONORS` array |
| Psychology Today posts | the `POSTS` array — `["YYYY-MM", "Title", "slug-from-the-url"]` |
| Press mentions | `<div class="press-grid">` |

To add a blog post, copy its URL from Psychology Today and take everything after `.../psychology-money-and-happiness/` — for example `202607/can-your-social-network-shape-your-economic-future`. Add a line at the top of `POSTS`; the year chip appears on its own.

Colors are CSS custom properties in the `:root` block at the top of the `<style>` tag. Change `--gold`, `--accent`, and `--bg2` and the whole site follows.

---

## Two things to know before you retire the Weebly site

**Three publication PDFs still point at maxalberhasky.com.** These three papers have no DOI link on the site, so their "PDF →" buttons load from your old Weebly uploads:

- *Framing Zero* (2021)
- *On the Psychology of the Psychology Subject Pool* (2020)
- *Temporal Discounting Correlates with Directed Exploration…* (2020)

If Weebly goes away, those three buttons break. The fix: save the PDFs into `assets/papers/`, then update each `href` to e.g. `assets/papers/framing-zero.pdf`. Everything else on the site is self-contained.

**Four blog titles were reconstructed from their URLs**, because your Weebly blog page listed posts as images with no text. The links are correct — only the display titles may need a word adjusted:

- *Why You Avoid Skilled Activities Even Though They Make You Happier* (2025-04)
- *Timeless Principles From History to Live a Successful Life* (2025-05)
- *How Money Impacts Your Attention and Pleasurable Experiences* (2026-03)
- *What Old Psychology Can Teach Us About New Betting* (2026-04)
