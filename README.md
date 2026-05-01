# Placid Security Website

Static HTML/CSS website for [placidsecurity.com](https://placidsecurity.com).

## Deploying to GitHub Pages

### First-time setup

1. Create a new repository on GitHub: `github.com/new`
   - Name it `placid-security` (or anything you like)
   - Set to Public
   - Don't initialize with README

2. Upload these files:
   ```
   git init
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/YOUR_USERNAME/placid-security.git
   git push -u origin main
   ```

3. Enable GitHub Pages:
   - Go to repo Settings → Pages
   - Source: Deploy from branch → `main` → `/ (root)`
   - Save

4. Your site will be live at `https://YOUR_USERNAME.github.io/placid-security/`

### Connect your custom domain (placidsecurity.com)

1. In your repo, create a file named `CNAME` with one line:
   ```
   placidsecurity.com
   ```

2. In your DNS registrar (wherever placidsecurity.com is registered), add:
   - Type: `A`, Name: `@`, Values: GitHub's IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Type: `CNAME`, Name: `www`, Value: `YOUR_USERNAME.github.io`

3. Back in GitHub Pages settings, enter `placidsecurity.com` as your custom domain
4. Check "Enforce HTTPS" once DNS propagates (15 min – a few hours)

## Activating the Contact Form

The contact form uses [Formspree](https://formspree.io) — free for up to 50 submissions/month.

1. Go to formspree.io, create an account, create a new form
2. Point it to info@placidsecurity.com
3. Copy your Form ID (looks like `xpzgwakb`)
4. In `contact.html`, replace `YOUR_FORM_ID` with your actual ID:
   ```javascript
   const FORMSPREE_ID = 'xpzgwakb'; // your actual ID
   ```

## Updating the Hero Banner

When your designer delivers the corrected hero image (with "Attack Surface Management"):
1. Name it `hero-banner.png`
2. Replace `assets/images/hero-banner.png`
3. Commit and push — GitHub Pages deploys in ~1 minute

## File Structure

```
placid-security/
├── index.html          ← Home page
├── services.html       ← Services page
├── about.html          ← About page
├── contact.html        ← Contact page
├── CNAME               ← Custom domain (create this)
├── README.md
└── assets/
    ├── style.css       ← All styles
    └── images/
        ├── hero-banner.png
        ├── logo-horizontal-darkblue.png   ← Used in nav
        ├── logo-horizontal-white.png
        ├── logo-stacked-darkblue.png      ← Used in footer
        ├── logo-stacked-white.png         ← Used on About page
        ├── logo-icon-darkblue.png         ← Used as favicon
        └── logo-icon-white.png
```
