# 🚀 AI Tools Review - 一键部署指南

## 快速部署到 Cloudflare Pages

### 方式 1: 使用 Wrangler CLI (推荐)

```bash
# 1. 登录 Cloudflare
npx wrangler login

# 2. 构建并部署
cd ~/ai-tools-review
hugo --minify --gc
npx wrangler pages deploy public --project-name=ai-tools-review
```

**网站地址**: https://ai-tools-review.pages.dev

---

### 方式 2: 通过 GitHub + Cloudflare

#### 第一步: 创建 GitHub 仓库

**选项 A - 使用 Personal Access Token:**
```bash
# 在 GitHub 设置中生成: https://github.com/settings/tokens
export GITHUB_TOKEN='ghp_xxxxxxxxxxxxxx'
cd ~/ai-tools-review
git remote set-url origin "https://$GITHUB_TOKEN@github.com/haha11923/ai-tools-review.git"
git push -u origin main
```

**选项 B - 使用 SSH 密钥:**
```bash
# 公钥已在 ~/.ssh/id_ed25519.pub
# 添加到 GitHub: https://github.com/settings/ssh/new
git remote set-url origin git@github.com:haha11923/ai-tools-review.git
git push -u origin main
```

#### 第二步: 连接 Cloudflare Pages

1. 访问 https://dash.cloudflare.com/pages
2. 点击 **Create a project** → **Connect to Git**
3. 选择 **GitHub** 并授权
4. 选择仓库 `haha11923/ai-tools-review`
5. 设置构建参数:
   - Build command: `hugo --minify --gc`
   - Output directory: `public`
6. 点击 **Save and Deploy**

---

## 📊 网站信息

| 项目 | 详情 |
|------|------|
| 框架 | Hugo + PaperMod 主题 |
| 文章数 | 8 篇 AI 工具评测 |
| 域名 | ai-tools-review.pages.dev |
| CDN | Cloudflare (全球加速) |
| SSL | 自动 HTTPS |
| 自动化 | GitHub Actions 定时更新 |

---

## 🤖 自动化设置

### 每日自动内容生成

GitHub Actions 配置在 `.github/workflows/auto-content.yml`

触发方式:
- 每天 UTC 9:00 自动运行
- 或手动触发: Settings → Actions → Run workflow

### 自动部署

每次推送到 `main` 分支会自动部署到 Cloudflare Pages。

---

## 💰 变现方式

1. **Amazon Associates** - 添加 AI 工具推荐链接
2. **软件联盟** - ChatGPT Plus、Cursor、Midjourney 等
3. **Google AdSense** - 流量上来后申请
4. **赞助商内容** - AI 公司付费评测

---

## 🔧 常用命令

```bash
# 本地预览
cd ~/ai-tools-review
hugo server -D

# 重新构建
hugo --minify --gc

# 生成新内容
bash /root/scripts/auto_generate_content.sh

# 部署到 Cloudflare
bash /root/scripts/cloudflare_deploy.sh
```

---

## ⚠️ 安全提醒

- 不要在聊天中分享密码
- 使用 SSH 密钥或 Personal Access Token
- 定期轮换 API Token
- 启用 GitHub 双因素认证
