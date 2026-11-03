# Stripe Radar 续费筛查计费就绪体检（10-21 续费计费 × 01-22 试用结束 × Lite 还是 Standard）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-11-03 |

## 一句话

帮用 Stripe Billing 的订阅产品算清 Radar 新计费下「每月多付多少」：哪些续费、重试、被拒/被拦尝试在被计费筛查，免费试用到 **2027-01-22** 结束后会自动按 Standard 计费多少，续费筛查轮数该设几轮、该不该切回免费的 Radar Lite——输出「留 Standard 并限轮 / 切 Lite / 升 Plus 写规则 / 暂不动」分数卡。

## 为什么现在

**2026-10-21** 起，Stripe 付费 Radar（Standard / Plus / Pro）把此前未单独计费的**订阅续费**与非卡支付方式也纳入按次计费（单价不变，Standard 约 $0.05/次、Plus $0.07、Pro $0.09 + 按客户费）。按官方文档：Stripe Billing 订阅的**首期付款**与**换卡后的首笔**总会被筛查计费，其后可在 Dashboard 配置继续筛查几轮成功续费，跳过的不收费；并且**被拒、被拦的尝试也会计费**，不只成功交易。另一边，今年被迁到 Radar Standard **免费试用**的美国账户（不少商户收到邮件「你一直免费用的接近 Standard」）在 **2027-01-22** 试用结束后，若不处理会自动按 $0.05/次扣费；想继续免费需自己在 Dashboard 一键切 Lite。对客单低的订阅（$5–$10/月），每次续费 $0.05 就是 0.5%–1% 的毛利；失败催收的多次重试若都被筛查，成本还会叠加——很多一人 SaaS 根本不知道自己现在是哪个 Radar 计划、续费筛查设了几轮。

## 目标客户

用 Stripe Billing、月活订阅数百到数万的一人或小团队 SaaS、会员站、课程订阅、Newsletter 付费订阅；尤其低客单月付、试用转付费多、或催收重试频繁的产品。收到「New Stripe Radar Plans and Pricing」邮件却没处理的美国账户是首批。

## 一人怎么起步

两周 concierge：用只读 API key 或导出数据拉近 90 天支付尝试（含失败/被拦）→ 按「首期 / 换卡首笔 / 第 N 次续费 / 催收重试」分桶，估算 Standard、Plus、Lite 三种情形的月 Radar 费用与占 MRR 比例 → 对照近 90 天欺诈争议与卡测试事件，判断续费筛查轮数（如前 3 轮后停）是否够用 → 交分数卡 + Dashboard 调整清单，并标出 01-22 前要做的决定。先在 Indie Hackers / Reddit r/stripe / X 发「Radar 新计费自查表」换 waitlist，再收一次性审计费；验证后做成月度监测（Radar 费用、欺诈率、被拦尝试占比）。

## 难度

低到中（官方文档写明计费规则与可配置项；需要读懂 Billing 与 Radar 事件、按尝试而非按成功订单计；切 Lite 会失去自定义规则与部分支付方式保护，必须结合欺诈史判断，不能一律劝降级）

## 变现路径

一次性 Radar 计费审计（示意 $49–$199，按订阅量）；月订阅监测（示意 $19–$49）；可与 `s2`（失败催收）、`s25`（暂停留存）打包成「Stripe 订阅成本与留存体检」，但条目分开。

## 注意的坑

与 `s2-dunning` 互补：那边追求多收回失败付款，这边算的是每次筛查（含重试与被拒尝试）的成本，两者要一起看。01-22 的试用结束据公开通知主要针对受影响的**美国账户**，别泛化到全球所有 Stripe 商户；按次计费是默认路径，不是自动订 $10 月费方案。降级到 Lite 可能放大卡测试与免费试用滥用风险，先看数据；结论只给建议，不代操作客户 Dashboard 设置，除非客户明确授权。非 Stripe 或纯一次性收款的店不是首批客户。

## 来源线索

- [Stripe Docs: How Radar works（计划、计费与续费筛查配置）](https://docs.stripe.com/radar/how-radar-works)
- [Subscription Insider: Stripe Expands Radar Fees to Subscription Renewals](https://www.subscriptioninsider.com/blog/stripe-expands-radar-fees-to-subscription-renewals)
- [Beyond the News: Stripe Radar bills more screened renewals (effective 2026-10-21)](https://beyondthe.news/dossiers/stripe-radar-october-2026-renewal-screening-billing-payment-method-expansion)
- [Squarespace Forum: 商户收到的 Radar Standard 试用至 2027-01-22 通知](https://forum.squarespace.com/topic/349568-new-stripe-radar-plans-and-pricing/)
- [Corgi Labs: Stripe Radar pricing tiers and the January 2027 deadline](https://www.corgilabs.ai/insights/stripe-radar-pricing-change)
