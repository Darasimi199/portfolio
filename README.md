# Darasimi Oyebisi — AI Creative Producer

A one-page portfolio for Oluwadarasimi “Darasimi” Oyebisi. Built as a static site with hand-written HTML, CSS, and vanilla JavaScript — no framework and no build step.

**Live site:** https://darasimi199.github.io/portfolio/  
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
- Working contact form via FormSubmit with a direct email fallback

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

## Deploy to GitHub Pages

The site is designed to deploy with no build step.

1. Create a **public** GitHub repository.
   - For a clean root URL, name it `<your-username>.github.io`.
   - For a project URL, any repository name works; the site will live at `<username>.github.io/<repo>/`.
2. Push the site files to the `main` branch.
3. In the repository, go to **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and the root folder (`/`), then save.
6. GitHub will publish the site at the URL shown on the Pages settings screen.

The `.nojekyll` file is included so GitHub Pages serves the static files as-is.

## Contact form

The form currently posts to:

```text
https://formsubmit.co/daraoyebisi@gmail.com
```

FormSubmit requires a one-time activation. Submit the form once after deployment, then click the activation link sent to `daraoyebisi@gmail.com`. After activation, submissions will arrive by email.

If you prefer a different service, replace the form `action` in `index.html` with a Formspree or FormSubmit endpoint.

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

- FormSubmit activation (submit the form once and approve the email)
- Any additional social links (LinkedIn, Behance, Vimeo, YouTube)
- CV PDF and headshot, if desired
- Any real campaign metrics, credits, or client quotes
- Custom domain, if one is purchased later

## Credits

Design and build for Darasimi Oyebisi. All campaign work is credited to Darasimi Oyebisi unless updated in the project data.
