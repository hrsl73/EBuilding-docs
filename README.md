# 🏢 E-Building Documentation & PRD Hub

A centralized, cloud-deployable documentation repository for **E-Building Society Management System** Product Requirement Documents (PRDs), system architecture designs, database models, and API specifications.

---

## 📑 Available Documents

| Document | File | Direct Clean Route | Description |
| :--- | :--- | :--- | :--- |
| **Water Meter Flow PRD** | [`water-meter-flow-prd.html`](water-meter-flow-prd.html) | `/water-meter` or `/water-meter-prd` | Canonical product specification for integrating water meter readings into the regular maintenance billing cycle with smart recovery on bill deletion, inline editing, and dedicated APIs. |
| **Legacy Architecture Audit** | [`water-meter-flow-analysis-existing.html`](water-meter-flow-analysis-existing.html) | `/water-meter-analysis` or `/legacy-analysis` | Complete teardown of the legacy water meter system across backend and frontend, detailing 10 critical flaws and root causes. |
| **Monthly Collection Entry in Finance BRD** | [`finance-monthly-collection-entry-brd.html`](finance-monthly-collection-entry-brd.html) | `/finance-monthly-collection` or `/finance-brd` | System-generated monthly credit entry in Finance for all bill collections, with gateway payments at the Easebuzz settled amount, current-FY backfill, re-log and feature flags. |

---

## 🚀 Instant Vercel Deployment

This repository is structured for zero-configuration static deployment on **Vercel**.

### Option A: Via GitHub (Recommended)
1. Push this repository to your GitHub account:
   ```bash
   git remote add origin https://github.com/<your-username>/ebuilding-docs.git
   git branch -M main
   git push -u origin main
   ```
2. Go to [vercel.com/new](https://vercel.com/new).
3. Import `ebuilding-docs`.
4. Click **Deploy**. Vercel will instantly deploy the hub with fast worldwide edge caching and SSL!

### Option B: Via Vercel CLI
```bash
# Install Vercel CLI if not already installed
npm i -g vercel

# Deploy instantly
vercel --prod
```

---

## 💻 Local Preview

Run locally using any static HTTP server:

```bash
# Using npm
npm start

# Or using npx directly
npx serve .

# Or using Python 3
python3 -m http.server 3000
```
Then visit `http://localhost:3000`.

---

## 📁 Repository Structure

```
ebuilding-docs/
├── index.html                               # Hub homepage with search & cards
├── water-meter-flow-prd.html                # Canonical Water Meter PRD
├── water-meter-flow-analysis-existing.html  # Legacy system audit
├── finance-monthly-collection-entry-brd.html # Monthly Collection Entry in Finance BRD
├── vercel.json                              # Vercel rewrites, headers & clean URLs
├── package.json                             # Helper scripts for local preview
├── .gitignore                               # Git ignore rules
└── README.md                                # Hub documentation & deployment guide
```

---

## ➕ Adding New PRDs

To add a new PRD or design doc to this hub:
1. Place your standalone `.html` document in the root directory.
2. Add a rewrite in `vercel.json` for a clean URL:
   ```json
   {
     "source": "/my-feature",
     "destination": "/my-feature-prd.html"
   }
   ```
3. Add a card in `index.html` under `<main class="cards-grid">`.
4. Commit and push:
   ```bash
   git add .
   git commit -m "docs: add My Feature PRD"
   git push
   ```
Vercel will automatically trigger a new preview and production deployment.
