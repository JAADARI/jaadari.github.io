# Firas Jaadari — Portfolio

Single-file HTML portfolio. No build step. No dependencies. Just one `index.html` that loads three Google Fonts and runs.

## Preview locally

Open `index.html` in any browser. That's it. No `npm install`, no dev server.

If you want a local server (recommended for proper file:// behavior with fonts):

```bash
# Python (you almost certainly have it)
python3 -m http.server 8000
# then open http://localhost:8000

# or Node, if you prefer
npx serve .
```

---

## Deploy for free — three good options

### Option 1: GitHub Pages (recommended for devs)

This gives you `https://jaadari.github.io` — clean, professional, free forever, ties to your GitHub identity.

**Steps:**

1. Create a **public** repo on GitHub named **exactly** `JAADARI.github.io` (must match your GitHub username, case-sensitive).
2. From this folder:
   ```bash
   git init
   git add index.html README.md
   git commit -m "portfolio v1"
   git branch -M main
   git remote add origin https://github.com/JAADARI/JAADARI.github.io.git
   git push -u origin main
   ```
3. Wait ~1–2 minutes. Visit `https://jaadari.github.io` — you're live.

**To update later:** edit `index.html`, then `git add . && git commit -m "update" && git push`. Live in under a minute.

> If you'd rather use a project repo (e.g. `firas-portfolio`), the URL becomes `https://jaadari.github.io/firas-portfolio/`. You'll also need to enable Pages in **Settings → Pages → Source: main / root**.

---

### Option 2: Netlify Drop (zero CLI, drag-and-drop)

The easiest possible deployment. No git required.

1. Go to <https://app.netlify.com/drop>.
2. Drag this folder onto the page.
3. Done. You get a URL like `https://random-words-12345.netlify.app`.
4. (Optional) Rename the site in **Site settings → Site information → Change site name** to something like `firas-jaadari` → `https://firas-jaadari.netlify.app`.

---

### Option 3: Vercel

Similar to Netlify, integrates well with GitHub.

1. Create the GitHub repo (steps 1–2 from Option 1).
2. Go to <https://vercel.com/new>, import the repo.
3. Deploy with default settings. URL becomes `https://JAADARI.vercel.app` or similar.

---

## Customizing

Everything is in `index.html`:

- **Colors / fonts** — top of the `<style>` block, in the `:root { ... }` CSS variables.
- **Hero copy** — search for `<header class="hero`.
- **Experience** — search for `<!-- CREDIT AGRICOLE -->`, `<!-- CARREFOUR -->`, etc.
- **Impact numbers** — the `<div class="stat reveal">` blocks in the `IMPACT` section. Edit `data-target` to change the value.
- **Contact links** — bottom of the file, search for `<!--  CONTACT  -->`.

The accent color (the warm tangerine) is defined once as `--accent: #ff5b1e;` — change it in `:root` to recolor the whole site.

---

## What's used

- **Fonts** (Google Fonts CDN): Fraunces (display serif), Manrope (body), JetBrains Mono (technical accents).
- **No JS framework.** ~80 lines of vanilla JavaScript for the scroll reveals and count-up animations.
- **No build tools.** No bundler, no npm, no package.json.

## Adding a custom domain (later, if you want one)

If you ever buy a domain (e.g. `firasjaadari.com`):

- **GitHub Pages:** add a `CNAME` file with `firasjaadari.com` in the repo, then point your DNS A records to GitHub's IPs. Full guide: <https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site>.
- **Netlify / Vercel:** Add the domain in the dashboard, follow their DNS instructions.
