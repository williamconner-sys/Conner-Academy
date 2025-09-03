# Deploying to conner.academy (GitHub Pages + Porkbun)

## 1) Create a GitHub repository
- Name it anything (e.g., `conner-academy`), Public or Private is fine.
- Upload *all files* from this folder (including `icons/`, `assets/`).

## 2) Turn on GitHub Pages
- In the repo: **Settings → Pages**.
- Source: **Deploy from a branch** → `main` → `/ (root)` → Save.
- After a minute you’ll get a temporary site URL.

## 3) Connect your domain on GitHub
- Still in **Settings → Pages**, set **Custom domain**: `conner.academy` (or `www.conner.academy`).

## 4) Add DNS at Porkbun (Domain Management → DNS)
Pick your primary domain style:

### Option A: `www.conner.academy` primary (recommended)
- **CNAME** — Host: `www` → Answer: `YOUR_GITHUB_USERNAME.github.io.`
- **URL Redirect 301** — Host: `@` → Destination: `https://www.conner.academy`

### Option B: apex `conner.academy` primary
- **ALIAS/ANAME** — Host: `@` → Answer: `YOUR_GITHUB_USERNAME.github.io.`
  *(If ALIAS isn’t offered, use four A records)*
- **A** — Host: `@` → `185.199.108.153`
- **A** — Host: `@` → `185.199.109.153`
- **A** — Host: `@` → `185.199.110.153`
- **A** — Host: `@` → `185.199.111.153`
- **CNAME** — Host: `www` → Answer: `YOUR_GITHUB_USERNAME.github.io.` *(or URL redirect to the apex)*

## 5) Enforce HTTPS
- Back in GitHub **Settings → Pages**, enable **Enforce HTTPS** once DNS is detected.