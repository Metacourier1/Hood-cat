# HoodCat ($HoodCat) — Website

Static landing page for the HoodCat meme coin on Solana.
No build step, no framework. Plain HTML + CSS + vanilla JS.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire site (markup, CSS, JS inline) |
| `logo.jpg` | Logo — used in nav, hero, footer, CTA background |
| `banner.jpg` | Hero background banner |
| `cat-bag.jpg` | Narrative section artwork |
| `cat-cash.jpg` | Community section artwork |
| `vercel.json` | Caching + security headers |
| `robots.txt` | Crawler allow rule |

All image references are **relative**, so the 5 site files must stay in the same folder.

## Deploy to Vercel — Option A: drag & drop (no CLI, fastest)

1. Go to https://vercel.com/new
2. Drag the whole `hoodcat-site` folder onto the page (or click **Browse** and select it).
3. Framework Preset: **Other**. Build Command: leave empty. Output Directory: leave empty.
4. Click **Deploy**. You get a live `*.vercel.app` URL in ~20 seconds.

## Deploy to Vercel — Option B: CLI

```bash
npm i -g vercel
cd hoodcat-site
vercel          # preview deploy
vercel --prod   # production deploy
```

## Deploy to Vercel — Option C: Git

```bash
cd hoodcat-site
git init && git add . && git commit -m "HoodCat site"
gh repo create hoodcat-site --public --source=. --push
```
Then in Vercel: **Add New → Project → Import Git Repository → hoodcat-site → Deploy**.
No framework, no build command, no output directory.

## Adding the contract address later

Open `index.html` and search for **TBA** (2 places):

```html
<span class="ca-val" id="caVal">TBA — mint address dropping soon</span>
<button class="copy-btn" id="copyBtn" data-ca="TBA">Copy</button>
```

Replace both `TBA` values with the real mint address, for example:

```html
<span class="ca-val" id="caVal">7xKXtg2CW87d97TXJSDpbD5jBkheTqA83TZRuJosgAsU</span>
<button class="copy-btn" id="copyBtn" data-ca="7xKXtg2CW87d97TXJSDpbD5jBkheTqA83TZRuJosgAsU">Copy</button>
```

The copy button auto-enables: it switches to a working clipboard copy and shows a "Contract address copied" toast.

## Custom domain

Vercel dashboard → your project → **Settings → Domains → Add** → enter your domain →
point the shown A / CNAME records at your registrar. SSL is automatic.

## Other hosts

The folder is fully static and works as-is on Netlify, Cloudflare Pages,
GitHub Pages, or any cPanel / nginx host — just upload all 5 files to the web root.
