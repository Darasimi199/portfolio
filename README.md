# Darasimi Oyebisi — AI Creative Producer

A one-page portfolio for Oluwadarasimi “Darasimi” Oyebisi. Built as a static site with hand-written HTML, CSS, and vanilla JavaScript — no framework and no build step.

**Live site:** https://darasimi-oyebisi.pages.dev/  
**Backup:** https://darasimi199.github.io/portfolio/  
**Repository:** https://github.com/Darasimi199/portfolio

## What is included

- One-page editorial portfolio with selected work for Goodnews, Efamol, and PharmacyOS
- Desktop hover previews with muted vertical loops
- In-page case-study overlays with full films, project notes, and stills
- Shareable case-study hashes: `#goodnews`, `#efamol`, `#pharmacyos`
- Light/dark mode with persisted preference
- Live Lagos time in the header and footer
- Responsive layouts for desktop, tablet, and mobile
- Keyboard-accessible dialog, skip link, reduced-motion support, alt text, and focus states
- SEO metadata, Person structured data, social preview image, and favicon
- Working contact form via Web3Forms with a direct email fallback
- One-page A4 resume linked from the About and Contact sections

## Resume

- `resume.pdf` — the downloadable one-page PDF
- `resume.html` — the print-ready A4 source with a Print / Save PDF button

## Structure

```text
index.html                 Main page and static copy
assets/
  css/styles.css           Design system and all layout
  js/main.js               Project data and interactions
  fonts/                   Self-hosted WOFF2 fonts
  img/                     Favicon and social preview image
  media/
    goodnews/              Full films, previews, posters, stills
    efamol/
    pharmacyos/
    stills/
robots.txt
.nojekyll
```

Original source media and local tooling are intentionally excluded from Git:

- `assets/source/` — downloaded originals
- `assets/contact-sheets/` — review frames
- `.tools/` — local ffmpeg and preview harnesses

## Preview locally

Open `index.html` directly in a modern browser, or serve the folder with any static server:

```sh
npx serve .
# or
python -m http.server 8000
```

The contact form only submits when the site is served over HTTP(S); direct file previews are for layout and interaction testing.

## Deployments

The site is static and has no build step.

- **Primary:** Cloudflare Pages, connected to `Darasimi199/portfolio`. Pushing to `main` deploys automatically to https://darasimi-oyebisi.pages.dev/.
- **Backup:** GitHub Pages, deployed from `main` at https://darasimi199.github.io/portfolio/.

Cloudflare Pages settings:

- Framework preset: None
- Build command: blank
- Build output directory: `/`
- Production branch: `main`

The GitHub Pages backup uses **Deploy from a branch → `main` → `/`**. The `.nojekyll` file is included so GitHub Pages serves the static files as-is.

## Contact form

The form posts to **Web3Forms**:

```text
https://api.web3forms.com/submit
```

The public access key is stored in the hidden `access_key` field in `index.html`. The free plan includes 250 submissions per month, spam protection, and a custom redirect. Successful submissions redirect to `thanks.html` and arrive at `daraoyebisi@gmail.com`.

If you change the destination email later, create a new Web3Forms access key and replace the existing key.

## Editing project content

All case-study content is in `assets/js/main.js` inside the `projects` object:

- titles and descriptions
- project metadata
- video and poster paths
- still paths and alt text
- next-project links
- preview labels

A project row can be repointed by changing its `data-project` attribute in `index.html`.

## Media notes

- Full films: H.264 MP4, 1080 × 1920, AAC stereo, max ~3 Mbps, `faststart`
- Hover loops: 540 × 960, muted, no audio
- Posters and stills: WebP
- Google Drive is not used at runtime; all media is served from the site
- Keep the optimized media in `assets/media/`; do not commit the original camera/Drive files

## Still to add

- Any additional social links (LinkedIn, Behance, Vimeo, YouTube)
- CV PDF and headshot, if desired
- Any real campaign metrics, credits, or client quotes
- Custom domain, if one is purchased later

## Credits

Design and build for Darasimi Oyebisi. All campaign work is credited to Darasimi Oyebisi unless updated in the project data.
