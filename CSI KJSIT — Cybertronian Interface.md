# CSI KJSIT — Cybertronian Interface

A responsive, static React + TypeScript website that presents CSI KJSIT through a Transformers-inspired visual story while retaining verified content from the public CSI KJSIEIT website.

## Run locally

Requirements: Node.js and pnpm 10.18.0 (the version is pinned in `package.json`).

```bash
pnpm install --frozen-lockfile
pnpm run dev:static
```

Open `http://localhost:3000`. To type-check and create the production static build:

```bash
pnpm run check
pnpm run build:static
```

The static build is written to `dist/public/`. It can be served by any static host. For clean routes and legacy `.php` aliases, configure that host to fall back to `index.html` for page routes while continuing to serve existing assets normally. The complete page route list is in `client/public/manus-routes.json`.

## Site content and assets

The site includes Home, Events, Team, Gallery, Technical Saturdays, Alumni, Newsletters and Sponsors. Reconstructed copy, registration links, image attribution and notes about content unavailable from the public-only source are recorded in `client/src/data/` and `research-sources.md`.

User-supplied audio is kept byte-for-byte, with its original filename, under `client/public/audio/`:

- `my-name-is-optimus-prime.mp3`
- `bumblebees-transformation-3.mp3`

Audio starts only from the character controls; it does not autoplay. Bumblebee uses a clearly labeled, silent rendered-video prototype scrubbed by scroll; it is not a rigged 3D model. Optimus uses a credited, hosted Sketchfab animation viewer with a static fallback if the external viewer is unavailable. Its runtime animation should be checked in the Preview before being represented as a verified transformation. Model and license credits are visible on the site and documented in `research-sources.md`.

## Architecture

The site uses React, Vite, Wouter, GSAP ScrollTrigger and Three.js. It is configured as a static-only project with no application server or database. Project-level branding metadata is in `app.config.ts`.
