# Personal website — Jiaxin Huang

The site is five pages: `index.html` (home) and one page per research perspective, `spatial.html`,
`reconstruction.html`, `navigation.html` and `safety.html`. `cv.pdf` is the CV it links to. The folders:
`figs` (paper figures), `posters` (NeurIPS 2025 posters, PDF plus preview), `videos` (demo videos with
preview frames), `fonts` (the Charter web font; its notice is in `fonts/LICENSE-Charter.txt`) and `photos`.
Nothing else is needed: no build step, no framework, no tracking.

## Publish on GitHub Pages (free)

1. Sign in to GitHub and create a **public** repository named `Habseligkeiten87.github.io`
   (your GitHub username followed by `.github.io`).
2. In the new repository choose **Add file → Upload files**, drag in the five `.html` files, `cv.pdf` and the whole
   `figs`, `posters`, `videos` and `fonts` folders (and `photos` once it has pictures), and commit. Keep the folder names as they are.
3. Open **Settings → Pages**. Under *Build and deployment*, set *Source* to **Deploy from a branch**,
   branch **main**, folder **/ (root)**, then **Save**.
4. After a minute or two the site is live at `https://habseligkeiten87.github.io`.

## Optional: your own domain (about USD 10–15 a year)

1. Buy a domain, for example `jiaxinhuang.com`, from any registrar (Cloudflare, Namecheap, Porkbun).
2. In the registrar's DNS settings add four **A** records for the bare domain (`@`) pointing to
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153` and `185.199.111.153`,
   and one **CNAME** record for `www` pointing to `habseligkeiten87.github.io`.
3. In the repository's **Settings → Pages**, enter the domain under *Custom domain*, save,
   and tick **Enforce HTTPS** once it becomes available.

## Updating

- New CV: replace `cv.pdf` in the repository with the new file (keep the name).
- New paper or news item: edit `index.html` on GitHub (pencil icon) or ask Claude to update it.
- The four perspective pages are generated together with `index.html`; ask Claude to regenerate all five when the
  research text, papers or materials change, so the pages stay consistent.
- The publication list on the site is generated from the CV's `04_Publication.tex`,
  so the item numbers (S16, C9, ...) match the CV.

## Adding photos

1. Put the image files in the `photos` folder next to `index.html`
   (JPEG, about 1600 px on the long side keeps the page fast).
2. Open `index.html`, search for `window.PHOTOS = [];` and list the photos, for example:

       window.PHOTOS = [
         { src: "photos/hiking-1.jpg", alt: "Ridge trail above the clouds", caption: "Hiking, 2026" },
         { src: "photos/hyrox-2026.jpg", alt: "Sled push at a HYROX race", caption: "HYROX, 2026" }
       ];

3. The Photos block in the Life section appears as soon as the list has one entry;
   each photo opens in a viewer with Previous / Next.
4. Upload the `photos` folder to the GitHub repository together with `index.html`.

## Paper figures

- Each figure comes in two sizes: `*-1100.webp` is shown on the page, `*-full.webp` opens in the viewer.
- They sit under SURPRISE3D (teaser), MLLM-For3D (framework), GuidedNav (teaser and framework) and HUGE-Bench (teaser),
  both in the Research section and in the publication list, folded until a visitor opens them.
- To show a figure for another paper, send the image to Claude; it is added the same way.

## Fonts

- Headings and quotations: Charter (in `fonts/`). Running text: Aptos where the visitor has it installed,
  otherwise Lato. Small labels: Lato (from Google Fonts). Chinese: Noto Serif SC and Ma Shan Zheng.
- Aptos is Microsoft's font and cannot be bundled with the site, so most visitors see Lato for running text.

## Posters and videos

- `posters/*-1100.webp` is the preview shown on the page; clicking it opens the PDF in `posters/`.
- `videos/*.mp4` are small H.264 files (about 1 to 4 MB each) that play muted while on screen and pause when
  scrolled away; `*-poster.webp` is the frame shown before playback. To add a demo, send Claude the video and the
  paper it belongs to.
