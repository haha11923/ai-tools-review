# 🤖 AI Tools Review - 自动维护系统

## 系统概述

这是一个全自动的 AI 工具评测网站维护系统，包括：

- ✅ **自动内容生成** - 每天自动生成新的 AI 工具评测文章
- ✅ **自动健康检查** - 每 6 小时检查网站状态
- ✅ **自动部署** - 每天凌晨 3 点自动部署到 Cloudflare Pages
- ✅ **自动备份** - 每周日创建完整备份
- ✅ **日志管理** - 自动清理旧日志，保留 30 天

## 快速命令

```bash
# 健康检查
bash /root/scripts/maintenance.sh check

# 生成新内容
bash /root/scripts/maintenance.sh content

# 部署网站
bash /root/scripts/maintenance.sh deploy

# 完整维护（检查 + 生成 + 部署 + 备份）
bash /root/scripts/maintenance.sh full

# 查看日志
bash /root/scripts/maintenance.sh logs
```

## 定时任务

| 时间 | 任务 | 说明 |
|------|------|------|
| 09:00 | 内容生成 | 每天生成 1-3 篇新评测文章 |
| 03:00 | 自动部署 | 每天凌晨部署最新代码 |
| 每 6 小时 | 健康检查 | 监控系统状态 |
| 周日 04:00 | 站点备份 | 每周备份完整站点 |
| 05:00 | 日志清理 | 每天清理 30 天前的日志 |

## 文件结构

```
/root/
├── ai-tools-review/          # Hugo 站点
│   ├── content/reviews/      # 评测文章 (9+ 篇)
│   ├── public/               # 构建输出
│   └── .health.json          # 健康状态
│
├── scripts/                  # 维护脚本
│   ├── auto_content.sh       # 内容生成
│   ├── auto_deploy.sh        # 自动部署
│   ├── health_monitor.sh     # 健康监控
│   ├── log_rotation.sh       # 日志管理
│   └── maintenance.sh        # 一键维护
│
└── backups/                  # 站点备份
    └── ai-tools-review/      # 按时间命名
```

## 网站信息

- **GitHub 仓库**: https://github.com/haha11923/ai-tools-review
- **Cloudflare Pages**: https://ai-tools-review.pages.dev
- **当前文章数**: 9 篇
- **状态**: ✅ 正常运行

## 监控日志

```bash
# 查看实时日志
tail -f /var/log/ai-tools-review/cron.log

# 查看健康状态
cat /root/ai-tools-review/.health.json

# 查看系统状态
bash /root/scripts/maintenance.sh status
```

## 自动化流程

### 1. 内容生成 (每天 9:00)
1. 随机选择 AI 工具
2. 生成完整评测文章（包括标题、元数据、正文）
3. 自动提交到 GitHub
4. 触发自动部署

### 2. 健康检查 (每 6 小时)
1. 检查 Hugo 是否安装
2. 检查 PaperMod 主题
3. 检查构建输出
4. 检查 GitHub 连接
5. 检查 Cloudflare 登录状态
6. 自动修复问题（如果可能）

### 3. 自动部署 (每天 3:00)
1. 拉取最新代码
2. 构建 Hugo 站点
3. 部署到 Cloudflare Pages
4. 记录部署日志

### 4. 站点备份 (每周日 4:00)
1. 创建完整站点备份
2. 排除 public/ 和 .git 目录
3. 保留最近 7 天的备份
4. 压缩存储

## 手动维护命令

```bash
# 立即生成内容
bash /root/scripts/auto_content.sh

# 立即部署
bash /root/scripts/auto_deploy.sh

# 健康检查
bash /root/scripts/health_monitor.sh check

# 创建备份
bash /root/scripts/health_monitor.sh backup

# 完整维护
bash /root/scripts/maintenance.sh full
```

## 扩展内容库

编辑 `/root/scripts/auto_content.sh` 添加更多 AI 工具：

```bash
declare -a TOOLS=(
    "工具名称:工具描述|分类|slug"
    "新工具:新描述|分类|new-tool"
)
```

## 故障排查

### 问题：Hugo 未安装
```bash
curl -L -o /tmp/hugo.tar.gz https://github.com/gohugoio/hugo/releases/download/v0.147.0/hugo_extended_0.147.0_linux-amd64.tar.gz
tar -xzf /tmp/hugo.tar.gz -C /tmp && mv /tmp/hugo /usr/local/bin/hugo
```

### 问题：PaperMod 主题缺失
```bash
cd ~/ai-tools-review
git clone https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

### 问题：Cloudflare 未登录
```bash
npx wrangler login
```

### 问题：Git 推送失败
```bash
cd ~/ai-tools-review
git status
git add .
git commit -m "Fix: maintenance script update"
git push origin main
```

## 系统状态

- ✅ 健康检查：正常
- ✅ 文章数量：9 篇
- ✅ 构建状态：正常
- ✅ GitHub 连接：正常
- ✅ Cloudflare 登录：正常
- ✅ Cron 任务：已配置

---

**创建时间**: 2026-08-18  
**维护者**: AI Tools Review 自动系统
