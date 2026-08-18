---
title: "AI Tools Review - 网站仪表板"
date: 2026-08-18
draft: true
---

# 📊 网站运营仪表板

## 基本信息

| 项目 | 数值 |
|------|------|
| 📝 文章总数 | {{ .Site.Params.articles_count | default "11" }} |
| 🌐 网站访问 | 实时统计 |
| 💰 月收益预估 | $200-1200 |
| 📅 最后更新 | {{ now.Format "2006-01-02" }} |

## 内容统计

```bash
# 查看文章数量
ls -1 content/reviews/*.md | wc -l

# 查看最新内容
tail -20 /var/log/ai-tools-review/content.log
```

## 自动化状态

- ✅ 内容生成: 每天 9:00 自动运行
- ✅ 健康检查: 每 6 小时自动运行
- ✅ 自动部署: 每天 3:00 自动运行
- ✅ 定期备份: 每周日自动运行

## 快速链接

- [GitHub 仓库](https://github.com/haha11923/ai-tools-review)
- [Cloudflare Pages](https://dash.cloudflare.com/pages)
- [联盟营销配置](/config/affiliate_links.toml)
- [维护脚本](/root/scripts/)
