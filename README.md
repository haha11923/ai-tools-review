# AI Tools Review

Automated AI tools review website built with Hugo + Cloudflare Pages.

## Features

- 🤖 Auto-generated content (cron jobs)
- 🚀 Lightning fast (Cloudflare CDN)
- 📱 Fully responsive
- 🌙 Dark/Light theme
- 📊 SEO optimized
- 💰 Affiliate-ready

## Tech Stack

- **Hugo** - Static site generator
- **PaperMod** - Beautiful Hugo theme
- **Cloudflare Pages** - Hosting + CDN
- **GitHub Actions** - CI/CD automation

## Deploy to Cloudflare Pages

### Option 1: GitHub Integration (Recommended)

1. Push this repo to GitHub
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com) → Pages
3. Click "Create a project" → Connect to GitHub
4. Select this repo
5. Build settings:
   - Build command: `hugo --minify --gc`
   - Output directory: `public`
6. Click "Save and Deploy"

### Option 2: Using Wrangler CLI

```bash
# Login to Cloudflare
npx wrangler login

# Deploy
npx wrangler pages deploy public --project-name=ai-tools-review
```

### Option 3: Manual Upload

1. Run `hugo --minify --gc`
2. Go to Cloudflare Pages dashboard
3. Click "Create a project" → Direct upload
4. Upload the `public/` folder

## Custom Domain

1. In Cloudflare Pages, go to "Custom domains"
2. Add your domain (e.g., `ai-tools-review.com`)
3. Follow DNS configuration instructions
4. Cloudflare will auto-configure SSL

## Monetization

Add affiliate links to reviews:

- **Amazon Associates** - AI tools, books
- **OpenAI Partners** - ChatGPT Plus
- **Cursor Affiliate** - AI code editor
- **Midjourney** - Image generation
- **Various SaaS affiliates**

## Content Generation

Scripts run automatically via GitHub Actions:

- Daily: Generate 2-3 new AI tool reviews
- Weekly: Full site rebuild

## Local Development

```bash
# Install Hugo
brew install hugo  # macOS
# or follow: https://gohugo.io/getting-started/installing/

# Clone and run
cd ai-tools-review
hugo server -D
# Visit http://localhost:1313
```

## Directory Structure

```
ai-tools-review/
├── content/
│   └── reviews/      # All review articles
├── layouts/          # Custom templates
├── static/           # Static assets
├── themes/           # PaperMod theme
├── scripts/          # Automation scripts
├── public/           # Built site (generated)
├── hugo.toml         # Site configuration
└── wrangler.toml     # Cloudflare Pages config
```

## License

MIT
