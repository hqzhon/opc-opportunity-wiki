# Stripe 订阅暂停留存就绪体检（Portal pause × flexible billing × auto-pause）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-30 |

## 一句话

帮 Stripe Billing 订阅产品审计「暂停」链路：是否已迁 flexible billing、Customer Portal 是否开放 pause、失败支付是 cancel 还是 auto-pause、entitlement webhook 是否真正停权/复权——输出「可开门户暂停 / 先迁模式再开 / 慎首败即停 / 暂缓」分数卡。

## 为什么现在

Stripe Endive 在 **2026-09-30** 上线原生 **pause / resume**（`paused` 状态 + `status_details`），并提供失败支付后**自动暂停**（首败或重试耗尽可独立配置），替代「重试失败就取消」的旧默认；前提是订阅使用 **flexible billing mode**（classic → flexible **单向**，改分摊与用量计费规则）。**2026-10-28** 起 Customer Portal 可允许客户自助暂停订阅，并把过期门户会话用邮箱验证恢复。一线拆解（CancelFlow **2026-10-03** 等）强调：auto-pause 与自愿取消流里的「留一留」暂停解决的是不同问题——前者是卡失效的非自愿路径，后者是客户主动 churn；二者都落在同一 `paused`，但 `status_details.paused.subscription.type`（如 `pause_requested` / `first_payment_failure` / `final_payment_failure`）必须分流话术与复权。许多一人 SaaS 仍停在 classic、门户只有 cancel+优惠券、webhook 未处理 `customer.subscription.paused` / `resumed`，等于新能力开了却用不了。与 `s2`（失败支付**催收重试与换卡序列**）不同，本条专盯 **暂停作为取消/取消式非自愿流失的可逆替代，以及 flexible 迁移门槛**。

## 目标客户

用 Stripe Billing 的一人或小团队 SaaS（尤其 MRR 已有、取消率或非自愿流失可感知）；门户目前只有「取消 / 换计划」、尚未开放 pause；或仍有大量 classic 订阅、想开 portal pause / auto-pause 却怕一刀切迁移翻车的独立开发者。课程站、会员站、工具类订阅皆可，不要求已上 Stripe Apps。

## 一人怎么起步

两周 concierge：拉取订阅样本标 classic vs flexible 占比 → 查 Billing Portal 配置是否启用 subscription pause、取消流是否只有 coupon → 查失败支付最终动作（cancel / past_due / auto-pause）与是否误开「首败即停」（会跳过 Smart Retries）→ 核对是否监听 `customer.subscription.paused` / `resumed` 与 entitlements 摘要、复权时 `payment_behavior`（推荐 `resume_on_payment_success`）与 billing cycle anchor 策略 → 交「先迁 flexible 试点仓 + 开门户暂停 / 仅开耗尽后 auto-pause / 暂缓等迁移审计」分数卡换 waitlist / 预付；验证后再做月度：pause 接受率、pause→resume、非自愿取消占比、classic 剩余库存。

## 难度

中（官方文档与 changelog 齐全；flexible 单向迁移与分摊行为必须先小仓试；勿把 pause 与 `pause_collection` 混为一谈；勿承诺固定挽回率；门户 pause 对不可暂停状态——试用中、send_invoice、已挂 schedule 等——有硬限制）

## 变现路径

一次性「flexible × portal × auto-pause × webhook」审计；月订阅监测 classic 残留与 pause/resume 健康度（示意 $29–$99）；可与 `s2` 并列售「失败催收 × 暂停留存」套餐但不合并条目。

## 注意的坑

与 `s2-dunning`（失败码分流重试、催收邮件、换卡页）正交：那边优化的是**尽量收到钱**，这边优化的是**收不到或不想用时先冻结可逆状态**。pause 会停开票并应停权；若只想停扣款但保留使用权，应用 pause payment collection。迁移 classic→flexible 不可回滚，成熟账本先审计再切。首败即停会放弃 Smart Retries 约一成量级的挽回空间，多数产品更适合「重试耗尽后再 pause」。非 Stripe Billing / 纯一次性收款不是首批客户。

## 来源线索

- [Stripe Docs: Pause subscriptions](https://docs.stripe.com/billing/subscriptions/pause)
- [Stripe Changelog: Pause/resume on demand (2026-09-30.endive)](https://docs.stripe.com/changelog/endive/2026-09-30/pause-subscription)
- [Stripe Changelog: Endive Oct 28 — customer portal subscription pausing](https://docs.stripe.com/changelog/endive)
- [CancelFlow: Stripe auto-pause on payment failure × flexible billing catch (2026-10-03)](https://cancelflow.dev/blog/stripe-auto-pause-payment-failure-dunning)
