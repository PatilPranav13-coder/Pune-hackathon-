# KnowledgeBridge

**Evidence-based knowledge continuity and handover platform**

KnowledgeBridge helps teams preserve critical operational knowledge when people change roles or leave. It organizes claims, links them to source evidence, surfaces gaps and contradictions, and produces reviewable handover documents.

## Demo

This repository deploys the KnowledgeBridge V2.1 frontend to GitHub Pages:

https://patilpranav13-coder.github.io/Pune-hackathon-/

The demo uses synthetic Helios Payments Platform sample data. It is a frontend prototype, not a production backend: authentication, durable multi-user storage, server-side evidence verification, and live AI extraction are not implemented.

## Project source

The source bundle is reassembled by GitHub Actions from the text parts under `.deploy-source/`, then installed and built in the workflow. The application is extracted into the runner workspace under `app/` and its Vite build is published.

## Local development

After extracting the source bundle into a local `app/` directory:

```bash
cd app
npm ci
npm run dev
npm test
npm run build
```

Use Node.js 22.22.2 or newer, matching the package engine requirement.

## Deployment

Every push to `main` runs `.github/workflows/pages.yml`. It reconstructs the source bundle, runs `npm ci` and `npm run build`, then deploys `app/dist` using GitHub Pages. Repository Pages source must be set to **GitHub Actions** under **Settings → Pages**.
