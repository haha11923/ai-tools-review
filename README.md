# AI Tools Review

English-language AI tools review website. Built with Hugo + PaperMod theme.

## Setup

```bash
cd ~/ai-tools-review
hugo server --buildDrafts
```

## Automated Content

Use cron jobs to auto-generate new reviews:
```bash
hugo new content reviews/<tool-name>-review.md
```

## Deployment

Push to GitHub for automatic deployment via GitHub Pages.
