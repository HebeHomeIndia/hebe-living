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
