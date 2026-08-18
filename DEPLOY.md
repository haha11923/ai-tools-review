# AI Tools Review - Quick Start Guide

## 🚀 Deploy in 3 Steps

### Step 1: Create GitHub Repository

```bash
# Option A: Using GitHub CLI (if gh is installed)
gh repo create nousresearch/ai-tools-review --public --push

# Option B: Using HTTPS with token
export GITHUB_TOKEN="your_pat_token"
cd ~/ai-tools-review
git remote set-url origin "https://$GITHUB_TOKEN@github.com/nousresearch/ai-tools-review.git"
git push -u origin main
```

### Step 2: Connect to Cloudflare Pages

1. Go to [Cloudflare Pages](https://dash.cloudflare.com/pages)
2. Click **Create a project** → **Connect to Git**
3. Select the `ai-tools-review` repository
4. Configure build settings:
   ```
   Production branch: main
   Build command: hugo --minify --gc
   Build output directory: public
   Root directory: /
   ```
5. Click **Save and Deploy**

### Step 3: Your Site is Live! 🎉

- Preview URL: `https://ai-tools-review.pages.dev`
- Custom domain: Add in Cloudflare Pages settings

---

## 📋 Manual Deployment (Alternative)

If you prefer direct upload:

```bash
# 1. Build the site
cd ~/ai-tools-review
hugo --minify --gc

# 2. Deploy via Wrangler
npx wrangler login
npx wrangler pages deploy public --project-name=ai-tools-review
```

---

## 🔧 Troubleshooting

### Git Push Failed
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "ai-tools-review@github.com"
# Add public key to GitHub: Settings → SSH Keys

# Or use personal access token
git remote set-url origin https://<token>@github.com/nousresearch/ai-tools-review.git
```

### Cloudflare Build Error
- Ensure Hugo extended version is installed
- Check `hugo.toml` baseURL configuration

---

## 📊 Current Site Stats

- **Pages**: 18
- **Reviews**: 8
- **Theme**: PaperMod (Dark/Light)
- **Hosting**: Cloudflare Pages (Free)

---

## 🤖 Automation

GitHub Actions are configured for:
- Auto-deploy on push to main
- Daily content generation (cron)

---

## 💰 Monetization Ready

Add affiliate links in reviews:
- Amazon Associates
- OpenAI Partners
- Cursor Affiliate
- Midjourney Affiliate
- And more...
