# GitHub 安全配置指南

## ⚠️ 安全提醒
- 不要分享密码到聊天窗口
- 建议使用 SSH 密钥或 Personal Access Token

## 方案 1: SSH 密钥（推荐）

SSH 密钥已生成，请添加到 GitHub：

1. 复制公钥：
```bash
cat ~/.ssh/id_ed25519.pub
```

2. 访问 https://github.com/settings/ssh/new
3. 粘贴公钥，标题填 "AI Tools Review"
4. 点击 Add SSH key

5. 推送代码：
```bash
cd ~/ai-tools-review
git push -u origin main
```

## 方案 2: Personal Access Token

1. 访问 https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Note: 勾选 `repo` 权限
4. 点击 Generate token
5. 复制 token（只显示一次！）
6. 运行：
```bash
export GITHUB_TOKEN='你的token'
cd ~/ai-tools-review
git remote set-url origin "https://$GITHUB_TOKEN@github.com/haha11923/ai-tools-review.git"
git push -u origin main
```

## 方案 3: GitHub CLI

```bash
# 安装 gh (如未安装)
npm install -g @github/cli

# 登录
gh auth login
# 选择: GitHub.com → HTTPS → Login with a web browser

# 推送
cd ~/ai-tools-review
gh repo create ai-tools-review --public --push
```
