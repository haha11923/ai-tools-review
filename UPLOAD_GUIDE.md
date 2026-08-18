# GitHub 快速上传指南

## ⚠️ 重要说明
GitHub 已禁用密码认证，需要使用 **Personal Access Token (PAT)**。

---

## 方法 1: 使用 Token (推荐)

### 第 1 步: 创建 Token
1. 访问: https://github.com/settings/tokens/new
2. 填写:
   - **Note**: `AI Tools Review`
   - **Expiration**: `90 days`
   - **Scopes**: 勾选 `repo`
3. 点击 **Generate token**
4. **复制 token** (只显示一次！)

### 第 2 步: 上传代码
```bash
export GITHUB_TOKEN='ghp_你的token'
bash /root/scripts/github_upload.sh
```

---

## 方法 2: 使用 SSH 密钥

### 第 1 步: 添加 SSH 公钥
你的公钥已经生成:
```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGd5+pXn3VxVmlzLsFv7id6uz1VhY6u6ZnTbpMhlasZx ai-tools-review@github.com
```

1. 访问: https://github.com/settings/ssh/new
2. 粘贴上面的公钥
3. 点击 **Add SSH key**

### 第 2 步: 推送代码
```bash
cd ~/ai-tools-review
git remote set-url origin git@github.com:haha11923/ai-tools-review.git
git push -u origin main
```

---

## 方法 3: 网页上传 (最简单)

1. 访问: https://github.com/new
2. 填写:
   - Repository name: `ai-tools-review`
   - Description: `AI Tools Review - Automated content website`
   - Public/Private: 选 Public
3. 点击 **Create repository**
4. 复制 Git 命令:
   ```bash
   cd ~/ai-tools-review
   git remote add origin https://github.com/haha11923/ai-tools-review.git
   git branch -M main
   git push -u origin main
   ```

---

## 上传后连接 Cloudflare Pages

1. 访问: https://dash.cloudflare.com/pages
2. 点击 **Create a project** → **Connect to Git**
3. 选择 GitHub 仓库 `haha11923/ai-tools-review`
4. 设置:
   - Build command: `hugo --minify --gc`
   - Output directory: `public`
5. 点击 **Save and Deploy**

🌐 网站地址: https://ai-tools-review.pages.dev
