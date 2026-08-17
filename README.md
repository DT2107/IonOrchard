[README.md](https://github.com/user-attachments/files/31138873/README.md)
# ION Orchard Food Directory — Mario Edition

A single-page, static food directory for ION Orchard's dining tenants — Mario-themed,
filterable by cuisine and price, with live Google ratings, Google Maps links,
one-tap "Reserve" calling, and a "?" block randomiser button.

Curated by **Dorothy Tay**.

This is a pure static site (one `index.html`, no build step needed), so deployment
is just a matter of pushing it to GitHub and connecting it to Vercel.

---

## 1. Push this project to GitHub

If you don't already have a repo, run these commands from inside this folder:

```bash
git init
git add .
git commit -m "Initial commit — ION Orchard Food Directory"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

Replace `<your-username>` and `<your-repo-name>` with your own GitHub username and
a repo name of your choice (e.g. `ion-food-directory`). You can create the empty
repo first at https://github.com/new, or use the GitHub CLI:

```bash
gh repo create ion-food-directory --public --source=. --remote=origin --push
```

## 2. Deploy on Vercel

**Option A — via the Vercel dashboard (no CLI needed)**
1. Go to https://vercel.com/new
2. Click **"Import Git Repository"** and select the repo you just pushed
3. Framework Preset: choose **"Other"** (it's a static site — no build step)
4. Leave Build Command and Output Directory blank
5. Click **Deploy**

Vercel will auto-detect `index.html` at the project root and serve it directly.
Your site will be live at `https://<your-repo-name>.vercel.app` within seconds.

**Option B — via the Vercel CLI**
```bash
npm i -g vercel
vercel login
vercel        # deploy a preview
vercel --prod # deploy to production
```

## 3. Custom domain (optional)

In the Vercel dashboard → your project → **Settings → Domains**, add your own
domain and follow the DNS instructions shown.

---

## Project structure

```
.
├── index.html      ← the entire app (HTML/CSS/JS, no dependencies)
├── vercel.json      ← static site config
├── package.json     ← metadata only, no build step required
├── .gitignore
└── README.md
```

## Updating store data

All restaurant data lives in the `stores` array near the bottom of `index.html`
(inside the `<script>` tag). Edit that array, commit, and push — Vercel will
auto-redeploy on every push to `main`.
