# 🚀 部署到 Cloudflare Pages 指南

## 方法 1: Cloudflare Pages Web 界面（推荐）

### 步骤：

1. **访问 Cloudflare Pages**
   - 打开: https://dash.cloudflare.com/pages
   - 登录你的 Cloudflare 账号

2. **创建项目**
   - 点击 **Create a project**
   - 选择 **Connect to Git**

3. **连接 GitHub**
   - 选择 **GitHub**
   - 授权 Cloudflare 访问你的 GitHub
   - 选择仓库: `haha11923/ai-tools-review`
   - 点击 **Begin setup**

4. **配置构建设置**
   ```
   Production branch: main
   Build command: hugo --minify --gc
   Build output directory: public
   Root directory: /
   ```

5. **点击 Deploy**
   - Cloudflare 会自动构建并部署
   - 等待 1-2 分钟
   - 完成后会显示预览链接

6. **访问你的网站**
   - 预览地址: https://ai-tools-review.pages.dev
   - 或通过自定义域名访问

---

## 方法 2: 使用 Cloudflare API Token

如果你已有 Cloudflare API Token:

```bash
export CLOUDFLARE_API_TOKEN='你的token'
cd ~/ai-tools-review
npx wrangler pages deploy public --project-name=ai-tools-review
```

---

## 方法 3: 直接上传到 Cloudflare

1. 构建站点:
```bash
cd ~/ai-tools-review
hugo --minify --gc
```

2. 访问 https://dash.cloudflare.com/pages
3. 点击 **Create a project** → **Direct upload**
4. 上传 `public/` 文件夹

---

## ✅ 完成！

部署成功后，你的网站将在:
- https://ai-tools-review.pages.dev
- 全球 CDN 加速
- 免费 SSL 证书

---

## 💡 自定义域名（可选）

1. 在 Cloudflare Pages 设置中绑定域名
2. 添加 DNS 记录:
   - CNAME: www → ai-tools-review.pages.dev
   - A: @ → 192.0.2.1 (Cloudflare 提供的 IP)
3. 启用 Always Use HTTPS
