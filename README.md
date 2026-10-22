# AutoShorts AI — Legal pages

Static, dependency-free legal website for **AutoShorts AI**, an independent personal project based in Vietnam.

Pages:

- `/terms/` — Terms of Service
- `/privacy/` — Privacy Policy
- `/` — Legal overview

The site is plain HTML + CSS (no JavaScript, no cookies, no analytics, no external fonts). It is designed to be
deployed on **GitHub Pages** for free.

## Files

```
legal-site/
├── index.html          # legal overview
├── terms/index.html    # Terms of Service
├── privacy/index.html  # Privacy Policy
├── assets/legal.css    # shared responsive styles
├── .nojekyll           # serve folders as-is
└── README.md
```

## Deploy to GitHub Pages

The intended public repository is:

```
https://github.com/nduy28092008-collab/autoshorts-ai-legal
```

1. Create a **public** repository named `autoshorts-ai-legal` under `nduy28092008-collab`.
   Do **not** reuse the private AutoShorts AI backend repository.
2. Upload the **contents** of this `legal-site/` folder to the repository root (not the folder itself).
   You can use the GitHub web uploader or Git:
   ```bash
   cd legal-site
   git init
   git add .
   git commit -m "Add AutoShorts AI legal pages"
   git branch -M main
   git remote add origin https://github.com/nduy28092008-collab/autoshorts-ai-legal.git
   git push -u origin main
   ```
   Authenticate with your own GitHub account (browser/`gh auth login`). Never paste a PAT into a chat.
3. In the repository: **Settings → Pages → Build and deployment**
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
   - Save.
4. Wait 1–3 minutes for the first deployment. In **Settings → Pages**, GitHub shows the published URL.
5. Enable **Enforce HTTPS** once the certificate is available.

### Public URLs

After the repository is deployed, the pages are available at:

- **Terms of Service:** `https://nduy28092008-collab.github.io/autoshorts-ai-legal/terms/`
- **Privacy Policy:** `https://nduy28092008-collab.github.io/autoshorts-ai-legal/privacy/`
- Legal overview: `https://nduy28092008-collab.github.io/autoshorts-ai-legal/`

GitHub Pages redirects `/terms` → `/terms/` and `/privacy` → `/privacy/`. Both forms work in a browser.

Verify after deployment:

```bash
curl -I https://nduy28092008-collab.github.io/autoshorts-ai-legal/terms/
curl -I https://nduy28092008-collab.github.io/autoshorts-ai-legal/privacy/
```

Each should return `HTTP/2 200` with `content-type: text/html`.

## Use these URLs in TikTok Developer

In your TikTok developer app configuration, set:

- **Terms of Service URL:** `https://nduy28092008-collab.github.io/autoshorts-ai-legal/terms/`
- **Privacy Policy URL:** `https://nduy28092008-collab.github.io/autoshorts-ai-legal/privacy/`

Do **not** change the OAuth Redirect URI to these pages. The redirect URI stays as configured for the local
OAuth callback, for example:

```
http://127.0.0.1:8710/callback
```

The legal pages are public documents only; they are not the OAuth callback.

## What is intentionally not here

This repository contains **only** public legal pages. Do not add:

- backend source code;
- `.env`, API keys, or client secrets;
- `secrets/tiktok_token.json` or any OAuth token;
- databases, product images, generated videos, or logs;
- private customer or account data.

GitHub Pages on a public repository publishes all files in the deployment branch.

## Custom domain (optional)

If you add a custom domain in **Settings → Pages → Custom domain**, GitHub creates a `CNAME` file and gives you
new HTTPS URLs. Update the URLs in TikTok Developer and in the pages’ contact/links accordingly.

## Editorial rules for these pages

- Operator is described as an **independent personal project in Vietnam**, not a registered company.
- Contact: `nduy28092008@gmail.com`.
- Effective/last updated: **22 October 2026**.
- Do not invent a company address, registration number, security certification, or email.
- Keep claims limited to what the software actually does: local processing, optional official TikTok OAuth
  and Content Posting API, no TikTok password collection, local token storage, disconnect/revoke, and local
  data deletion.
