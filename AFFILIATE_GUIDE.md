# 🤝 联盟营销配置指南

## 快速开始

### 1. 配置联盟链接

编辑配置文件：
```bash
nano ~/ai-tools-review/config/affiliate_links.toml
```

添加格式：
```toml
# 格式: slug:program_name:url:commission_type:notes
chatgpt:OpenAI ChatGPT Plus:https://help.openai.com/en/articles/7544947:subscription:Priority access
```

### 2. 使用管理工具

```bash
# 查看所有链接
bash /root/scripts/affiliate_manager.sh list

# 搜索链接
bash /root/scripts/affiliate_manager.sh search chatgpt

# 添加新链接
bash /root/scripts/affiliate_manager.sh add chatgpt "ChatGPT Plus" "https://..." subscription

# 更新链接
bash /root/scripts/affiliate_manager.sh update chatgpt "https://new-url.com"

# 生成文章中的联盟部分
bash /root/scripts/affiliate_manager.sh generate ChatGPT
```

---

## 推荐的联盟计划

### 🥇 高佣金 (20-40%)

| 工具 | 联盟计划 | 佣金 | 申请链接 |
|------|---------|------|---------|
| ChatGPT | OpenAI Affiliate | 20% | https://openai.com/partners |
| Claude | Anthropic Partners | 25% | https://www.anthropic.com/partners |
| Midjourney | MJ Affiliate | 20% | https://midjourney.com/affiliates |
| Cursor | Cursor Affiliates | 30% | https://www.cursor.com/affiliates |
| Jasper | Jasper Affiliate | 30% | https://www.jasper.ai/affiliates |

### 🥈 中佣金 (10-20%)

| 工具 | 联盟计划 | 佣金 | 申请链接 |
|------|---------|------|---------|
| Notion | Notion Affiliate | 20% | https://www.notion.so/affiliate |
| Runway | Runway Affiliates | 15% | https://runwayml.com/affiliates |
| ElevenLabs | ElevenLabs Partners | 20% | https://elevenlabs.io/partners |
| Perplexity | Perplexity Affiliate | 25% | https://www.perplexity.ai/affiliate |
| Copy.ai | Copy.ai Affiliate | 30% | https://www.copy.ai/affiliate |

### 🥉 低佣金 (4-10%)

| 平台 | 联盟计划 | 佣金 | 申请链接 |
|------|---------|------|---------|
| Amazon | Amazon Associates | 4-10% | https://affiliate-program.amazon.com |
| Coursera | Coursera Affiliate | 20% | https://www.coursera.org/affiliate |
| Udemy | Udemy Affiliate | 12% | https://www.udemy.com/affiliate-program |

---

## 佣金类型说明

| 类型 | 说明 | 收益模式 |
|------|------|---------|
| subscription | 订阅分成 | 用户订阅期内持续获得佣金 |
| freemium | 免费增值 | 免费用户转化付费时获得佣金 |
| pay_per_use | 按使用量付费 | 按使用量比例分成 |
| commission | 销售佣金 | 一次性销售佣金 |
| enterprise | 企业方案 | 高价值企业客户佣金 |

---

## 最佳实践

### ✅ 应该做的

1. **自然插入链接**
   - 在价格部分推荐订阅
   - 在总结部分添加 CTA
   - 使用"立即试用"等行动号召

2. **提供真实价值**
   - 客观评价产品优缺点
   - 基于实际使用体验
   - 不夸大功能

3. **遵守法规**
   - 添加免责声明
   - 明确标注联盟链接
   - 符合 FTC 指南

4. **定期更新**
   - 检查链接有效性
   - 更新价格信息
   - 优化推荐文案

### ❌ 不应该做的

1. **虚假推荐**
   - 不推荐未使用的产品
   - 不夸大收益潜力
   - 不隐瞒佣金关系

2. **链接滥用**
   - 不在无关内容中强行插入
   - 不过度堆砌联盟链接
   - 不隐藏链接来源

3. **侵犯版权**
   - 不使用他人品牌素材
   - 不抄袭竞品内容
   - 遵守各平台政策

---

## 收益预期

### 月度预估（基于 1000 独立访客）

| 转化率 | 订阅数 | 月收入（30%佣金） |
|--------|--------|------------------|
| 1% | 10 | $120 |
| 2% | 20 | $240 |
| 5% | 50 | $600 |
| 10% | 100 | $1,200 |

*注：实际收益取决于转化率、客单价和留存率*

---

## 优化建议

### 1. 内容优化

```markdown
## 优化前
价格：$12/月

## 优化后
### 💰 限时优惠
- 免费版：永久可用
- 专业版：**$12/月** [点击获取优惠]
- 企业版：免费试用 14 天
```

### 2. 链接优化

- 使用锚文本描述而不是裸链接
- 在关键位置放置 CTA
- 添加紧迫感（限时优惠）

### 3. 转化优化

- 添加对比表格
- 突出独家优惠
- 提供使用教程

---

## 跟踪与分析

### 使用 UTM 参数

```
https://example.com/ref/?utm_source=ai-tools-review&utm_medium=affiliate&utm_campaign=chatgpt
```

### 关键指标

- **CTR (点击率)**: 链接点击 / 页面浏览
- **CVR (转化率)**: 购买用户 / 点击用户
- **AOV (客单价)**: 平均订单价值
- **EPC (单次点击收益)**: 佣金 / 点击数

---

## 常见问题

### Q: 如何申请联盟计划？
A: 大多数 AI 工具的联盟计划需要在官网申请，通常要求：
- 至少 1000 月访问量
- 高质量内容
- 明确的流量来源

### Q: 佣金何时结算？
A: 通常是月结，达到最低阈值（如 $50）后支付。

### Q: 如何处理退款？
A: 如果用户退款，佣金会被扣除。

### Q: 可以修改佣金比例吗？
A: 不可以，但可以尝试谈判更高比例（需要高流量）。

---

## 下一步

1. ✅ 申请高价值联盟计划
2. ✅ 配置 affiliate_links.toml
3. ✅ 运行 `bash affiliate_manager.sh update-all`
4. ✅ 监控收益数据
