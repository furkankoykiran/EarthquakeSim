# EarthquakeSim

**Live demo: [furkankoykiran.com.tr/EarthquakeSim](https://furkankoykiran.com.tr/EarthquakeSim/)**

EarthquakeSim is a web-based 3D earthquake emergency training simulator for office environments. It focuses on take-cover behavior, aftershock awareness, and object stability under seismic motion.

## Overview

This project is built with Three.js and Vite. It simulates shaking intensity, object topple risk, and a simple scoring/reporting flow to reinforce safe decisions during an earthquake.

## Key Features

- Camera shake with adjustable intensity and aftershocks
- Object shake, topple, and damage cues
- Take-cover interaction with scoring feedback
- CSV training report export
- FPS navigation with pointer lock controls
- Prerender-free static build with verified SEO/AIO metadata and discovery files

## Requirements

- Node.js 24+ (recommended; CI and the Pages workflow use Node 24)
- npm 10+

## Quick Start

```bash
npm install
npm run dev -- --port 5175
```

Open: http://localhost:5175

## Production Build

```bash
npm run build      # vite build + scripts/verify-build.js
npm run preview -- --host --port 5175
```

The build output is generated under `dist/`. `scripts/verify-build.js` fails the
build if the document metadata, JSON-LD, discovery files or hashed assets are
missing, and CI runs the same command on every pull request.

## SEO, AI discovery and accessibility

- Turkish document language, descriptive title, canonical URL, Open Graph and Twitter cards.
- `WebApplication` + `LearningResource` JSON-LD with author, licence and repository links.
- `robots.txt`, `sitemap.xml`, `llms.txt`, `ai.txt`, `.well-known/security.txt` and a web manifest in `public/`.
- Zoom is no longer disabled, the page keeps a readable `<noscript>` fallback, and headings/links are labelled.

`robots.txt` only applies when the site is served from a host root. On
`furkankoykiran.com.tr/EarthquakeSim/` the portfolio's root `robots.txt` is the
authoritative one; the file here keeps the repo self-contained for Docker and
standalone deployments.

## Docker

```bash
docker compose up --build
```

Open: http://localhost:8080

## Configuration

- Port and host settings are defined in `vite.config.js`.
- Earthquake intensity, cover logic, and object physics live in `main.js`.
- UI copy and instruction content live in `index.html`.

## Model Guide

See `MODELS-GUIDE.md` for sourcing and integrating 3D models.

## Project Structure

- `index.html`: UI layout and scenario copy
- `main.js`: core simulation logic
- `styles/style.css`: UI styling
- `public/assets/3D`: 3D models used by the scene
- `public/assets/hdri`: environment lighting

## Best Practices

- Keep model files optimized and low-poly for stable FPS
- Use consistent units (meters) for all object positioning
- Test quake intensity changes with multiple runs to avoid extreme camera roll
- Verify cover logic near the desk and exit flow after aftershocks

## Safety Note

This simulator is for training and awareness only. It is not a substitute for certified safety training or official emergency procedures.

## License

This project is licensed under the MIT License. See `LICENSE` for details.
