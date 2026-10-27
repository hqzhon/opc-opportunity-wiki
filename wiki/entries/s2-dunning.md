# 订阅失败支付挽回（垂直化 dunning）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-27 |

## 一句话

针对 Shopify App / 会员站 / 课程平台做智能重试与催收序列，减少因拒卡、过期卡导致的非自愿流失，并按垂直话术优化挽回率。

## 为什么现在

Stripe 把 Smart Retries、失败邮件、自动换卡更新做成 Billing 标准能力，并称智能重试可比固定日程多挽回约 14% 收入；第三方基准样本里失败支付挽回率可到约五成量级，但因行业差异大。Shopify Subscriptions 也允许配置重试次数/间隔与最终动作（跳过/暂停/取消）。横向工具（Stripe 原生、Churn Buster、ProfitWell Revive 等）对**小平台与垂直话术**照顾不足——课程站、Shopify App 订阅、会员站的失败码分布与「如何开口催」不同。ROI 话术清晰：挽回金额可直接对账。

## 目标客户

用 Stripe / Shopify 的 $10k–$100k MRR 独立创始人、会员站与课程卖家、中小 Shopify App 开发者。

## 一人怎么起步

两周验证：接 Stripe webhook（`invoice.payment_failed` 等）→ 按失败码分流（软拒重试 vs 硬拒只引导换卡）→ 邮件/应用内催收序列 + 客户自助更新支付页 → 仪表盘展示「可挽回 / 已挽回」金额 → 向 5–10 家目标客户做 concierge 分成或月费试点。可上架 Stripe Apps 或做 Shopify 伴生。

## 难度

中（支付合规、邮件送达、过度催收风险）

## 变现路径

订阅费或挽回金额分成；可上架 Stripe Apps / Shopify App Store。

## 注意的坑

过度催收伤品牌；硬拒不要死磕重试；遵守支付与隐私规则（地区差异）；Stripe/Shopify 原生能力变强时，楔子要留在「垂直话术 + 多平台统一看板 + 挽回实验」；勿承诺固定挽回率。

## 来源线索

- [Stripe Docs: Revenue recovery](https://docs.stripe.com/billing/revenue-recovery)（Smart Retries、邮件、换卡）
- [Stripe Docs: Automate payment retries](https://docs.stripe.com/billing/revenue-recovery/smart-retries)
- [Shopify Help: Managing Shopify Subscriptions app settings](https://help.shopify.com/en/manual/products/purchase-options/subscriptions/shopify-subscriptions/manage-subscriptions/manage-app-settings)（重试与最终动作）
- [Shopify Blog: What is subscription recovery (2026)](https://www.shopify.com/blog/subscription-recovery)
- [Swipe Again: Failed payment recovery benchmarks](https://swipeagain.com/pages/failed-payment-recovery-benchmarks)（第三方样本，须标注非官方）
