# GitHub 登录指南

## 为什么密码认证失败？
GitHub 已禁用密码认证，需要使用 Personal Access Token (PAT)。

## 创建 Personal Access Token

1. 访问: https://github.com/settings/tokens/new
2. 填写:
   - **Note**: AI Tools Review
   - **Expiration**: 选择合适的时间
   - **Scopes**: 勾选 `repo`
3. 点击 **Generate token**
4. **复制 token** (只显示一次！)

## 使用 Token 推送代码

```bash
# 设置 token
export GITHUB_TOKEN='ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'

# 推送代码到 GitHub
cd ~/ai-tools-review
git remote set-url origin "https://haha11923:$GITHUB_TOKEN@github.com/haha11923/ai-tools-review.git"
git add -A
git commit -m "Initial commit: AI Tools Review website with 8 articles"
git push -u origin main
```

## 或者使用 gh CLI 登录

```bash
# 安装 gh
npm install -g @github/cli

# 登录
gh auth login
# 选择:
#   - GitHub.com
#   - HTTPS
#   - Login with a web browser

# 推送
cd ~/ai-tools-review
gh repo create ai-tools-review --public --push --source=. --remote=origin
```
