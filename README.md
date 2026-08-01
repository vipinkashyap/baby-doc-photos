# Baby Document Photo Kit

Client-side tool to turn one photo of a baby into correctly sized, compressed photos for:

- **US Passport (DS-11)** — 600×600 digital + 4×6 print sheet (four 2×2 photos, 300 dpi)
- **OCI Card** — 900×900 JPEG, auto-compressed ≤200 KB (ociservices.gov.in spec)
- **India e-Visa** — 1000×1000 JPEG, auto-compressed ≤300 KB (indianvisaonline.gov.in spec)

All processing happens in the browser (canvas). No uploads, no backend, no dependencies.

## Run locally
Open `index.html` in any browser. On mobile, "Take photo" uses the rear camera via `capture="environment"`.

## Deploy
Static single file — works on GitHub Pages, Cloudflare Pages, anything.

## Roadmap ideas
- [ ] Background whitening (segmentation via MediaPipe selfie-segmentation, still client-side)
- [ ] Indian passport format (630×810, 35×45mm) for Passport Seva
- [ ] Head-height auto-check against spec ranges
- [ ] PWA manifest for home-screen install
