# Hebe Living — Starter Repo (MVP)

This starter repo contains a minimal scaffold for **Hebe Living**:
- Frontend: React + Vite + Tailwind (simple starter files)
- Backend: Node.js + Express + SQLite (simple API and admin endpoints)
- CSV sample for product import
- Instructions to run locally and deploy

**What you get**
- `client/` — React + Vite app (components, hero, product list with mock data)
- `server/` — Express server with SQLite DB seed, product endpoints, and admin placeholders
- `sample-products.csv` — CSV format for bulk import

## How to use

### 1) Clone or download and open terminal here
```bash
# if downloaded zip, unzip and cd into folder
cd hebe-living-starter
```

### 2) Install & run backend (port 4000)
```bash
cd server
npm install
# create .env (see .env.example) or set env vars
npm run dev
# Server runs at http://localhost:4000
```

### 3) Install & run frontend (port 5173)
```bash
cd client
npm install
npm run dev
# Frontend runs at http://localhost:5173
# Update API base URL in client/src/config.js if needed
```

### 4) Deploy
- Frontend: build (`npm run build`) and host on GitHub Pages / Netlify / Vercel.
- Backend: deploy to Render / Railway / Fly.io with `server/` folder.

---

If you want, I can:
- Convert the frontend to a plain static HTML site for direct GitHub Pages deployment (no Node needed).
- Add Cloudinary image upload integration.
- Add JWT admin login scaffolding (currently placeholder).

## CI / CD (GitHub Actions) — auto-deploy

This repo includes two GitHub Actions workflows (in `.github/workflows/`):

1. **deploy-client.yml** — builds the React client and deploys `client/dist` to GitHub Pages using `peaceiris/actions-gh-pages`.
   - Triggers on push to `main` or `master`.
   - Requires no extra secrets (uses `GITHUB_TOKEN`).

2. **deploy-server.yml** — after pushing to `main`/`master`, this workflow triggers a Render deploy via their API.
   - You must add two repository **secrets**:
     - `RENDER_API_KEY` — a Render API key with permission to trigger deploys.
     - `RENDER_SERVICE_ID` — the Render service ID (available in your Render dashboard for the service connected to this repo).
   - The workflow sends a POST to `https://api.render.com/v1/services/$RENDER_SERVICE_ID/deploys` to trigger a deploy.

### How to set secrets (GitHub)
1. In your GitHub repo, go to **Settings → Secrets and variables → Actions → New repository secret**.
2. Add `RENDER_API_KEY` and `RENDER_SERVICE_ID` with values from your Render account.

### Notes
- Render also supports automatic deploys from GitHub when you connect your repo. Using the `deploy-server.yml` workflow is optional — it simply triggers a deploy if you prefer manual control via Actions.
- If you prefer using Render's native GitHub integration (recommended), you can skip adding `RENDER_API_KEY` and `RENDER_SERVICE_ID` and set up continuous deploys in the Render console.
