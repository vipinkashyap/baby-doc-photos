# Baby Document Photo Kit

Client-side tool to turn one photo of a baby into correctly sized, compressed photos for:

- **US Passport (DS-11)** — 600×600 digital + 4×6 print sheet (four 2×2 photos, 300 dpi)
- **OCI Card** — 900×900 JPEG, auto-compressed ≤200 KB (ociservices.gov.in spec)
- **India e-Visa** — 1000×1000 JPEG, auto-compressed ≤300 KB (indianvisaonline.gov.in spec)

All processing happens in the browser (canvas). No uploads, no backend, no dependencies.

## How the cropping works

The US and Indian specs demand *different* head sizes — 50–69% of frame for a US
passport, 70–80% for OCI and Indian visas — so no single crop satisfies both.

Rather than making you crop once per document, the tool asks for one
measurement: drag two lines onto the crown and the chin. That fixes the head's
position and height in image coordinates, from which each output's square crop
is derived to hit its own required ratio (`SPECS` in `index.html`). One marking,
correctly-sized files for every document.

If the required square would fall outside the photo, the page says so before you
download rather than silently padding with white.

## Run locally
Open `index.html` in any browser. On mobile, "Take photo" uses the rear camera via `capture="environment"`.

## Deploy
Static single file — works on GitHub Pages, Cloudflare Pages, anything.

## Roadmap ideas
- [ ] Background whitening (segmentation via MediaPipe selfie-segmentation, still client-side)
- [ ] Indian passport format (630×810, 35×45mm) for Passport Seva
- [ ] PWA manifest for home-screen install
- [ ] Auto-detect crown/chin (MediaPipe face landmarks) to pre-place the lines
