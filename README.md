# zach-wang-site

Personal website for Zichen (Zachary) Wang. One static page — no framework, no build step required, nothing to install. Fonts come from Google Fonts; everything else is in this folder.

## What's here

| File | Purpose |
|---|---|
| `index.html` | The whole site: markup, styles and script in one file. |
| `Zach_Wang_CV.pdf` | Linked from the "CV (PDF)" buttons. Replace with a newer export any time. |
| `media/` | Headshot, demo videos, hobby photos. See `media/README.md` for the exact filenames — the page shows a labeled empty slot until each file exists. |
| `.nojekyll` | Tells GitHub Pages to serve files as-is. |

## Preview locally

Double-click `index.html`. The demo videos may not autoplay from `file://` in some browsers; to see the page exactly as it ships, serve the folder instead:

```bash
python -m http.server 8000
```

then open <http://localhost:8000>.

## Put it on GitHub Pages

1. On GitHub, create a new **public** repository named exactly `zichenzachwang.github.io`. Leave it empty (no README, no .gitignore).
2. Unzip this bundle, then in a terminal inside the unzipped folder:

   ```bash
   git init
   git add .
   git commit -m "Personal website"
   git branch -M main
   git remote add origin https://github.com/zichenzachwang/zichenzachwang.github.io.git
   git push -u origin main
   ```

3. In the repository on GitHub: **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, choose branch `main` and folder `/ (root)`, then Save.
4. Within a minute or two the site is live at **https://zichenzachwang.github.io/**.


## Add the headshot, videos and photos

Copy files into `media/` using the names in `media/README.md`, then:

```bash
git add media && git commit -m "Add media" && git push
```

No HTML edits are needed for the files themselves. Each slot shows a labeled placeholder until its file exists, so a missing file never appears as a broken image.

Demo videos load only as their card nears the viewport, and the matching `media/<name>.jpg` poster is what shows until then, so give every video a poster.

## Updating anything else

Everything is in `index.html`; sections are marked with `<!-- ===== NAME ===== -->` comments. Commit and push, and GitHub republishes automatically.

## Custom domain (optional)

Add a file named `CNAME` containing just the domain (e.g. `zachwang.bio`), point the domain's DNS at GitHub Pages per [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site), then enable **Enforce HTTPS** in Settings → Pages.
