# Apple 订阅取消挽留消息就绪体检（11-04 上线 × 取消流程文案/优惠 × 审核禁写价格）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | 是 |
| 更新 | 2026-11-09 |

## 一句话

帮在 App Store 卖自动续订订阅的独立开发者，在 **2026-11-04** Retention Messages 正式向所有开发者开放之后，用 App Store Connect 原生配置（不必写代码）把「用户点取消 → 确认前」那一屏的标题/正文、可选配图或挽留优惠配齐，并过一遍审核红线（标题和正文**不得出现价格或折扣**），输出「有没有配 × 文案会不会拒审 × 要不要上折扣」分数卡——和 `s31`（多席位默认开启）是另一套订阅留存问题。

## 为什么现在

Apple Developer News（**2026-11-04**）宣布 Retention Messages 现已可用：用户在系统取消订阅流程里确认前，会看到开发者配置的标题与正文，以及可选的配图或挽留优惠（按期折扣、一次付清折扣或免费期）。App Store Connect 即可配置；每 App 最多 **10** 条消息，每个订阅组计划同时只能挂 **1** 条；文案要过 App Review，标题和正文不得写价格或折扣（如 “$9.99”“50% off”“one month free”），否则拒审。已发布后再改会出草稿版；优惠有资格与 Wait Between Offers 间隔。程序化配置走 App Store Connect API，需单独申请。

这和已有的 Win-Back（取消**之后**再触达）不同：Retention Messages 卡在取消**完成前**。Holiday 季取消高峰到来前，大量独立开发者还没配；RevenueCat（2026-11-05）指出 ASC 原生优惠最短付费时长从 1 个月起（试用用户拿不到），并引用 Dipsea 实验：折扣挽救率略高，但人均收入不到一半——「只写留下的理由」还是「上折扣」会直接影响 LTV。

本条不管机构多席位开关（那是 `s31`），也不管 Stripe 门户暂停（`s25`）或失败支付 dunning（`s2`）。

## 目标客户

在 App Store 有自动续订订阅、尚未在 ASC 配 Retention Messaging、或文案里仍写了价格/折扣的独立开发者与小团队；以及用 RevenueCat / Adapty / Superwall、想评估「先上 ASC 原生还是上 API/第三方个性化」的一人开发者。没有自动续订、或取消率极低且已配合规消息的 App 不是首要客户。

## 一人怎么起步

两周 concierge：在 iOS 独立开发者群、r/iOSProgramming、RevenueCat / Indie Hackers 圈发自查表（有没有自动续订？ASC Subscriptions 页有没有 Retention Messaging 入口？几个订阅计划？取消主因是价格还是不用？）。对 5–10 个报名 App 只读检查：是否已配消息、文案是否踩审核红线（价格/折扣/无法证实的「最好/92%」类措辞）、图片尺寸（3840×2160 或 5244×2950）、优惠资格与本地化是否覆盖在售 storefront。为每 App 起草 1 条不含价格的合规文案 +「不上折扣 vs 上折扣」建议，用 ASC preview 出图。先收一次性 ASC 配置 + 合规文案体检费；明确要 Retention Messaging API 或第三方个性化再加价。不承诺「配置后取消率一定降多少」。

## 难度

低到中（ASC 点选即可上线；难在合规文案、优惠资格与「折扣 vs 纯文案」取舍；API/第三方路径才需要开发）

## 变现路径

一次性 Retention Messages 就绪体检 + 合规文案（示意 $99–$299 / App）；「文案 + 配图规格 + 优惠策略建议 + ASC 代配」固定价（示意 $200–$600）；之后可做取消原因 / 消息表现月报（示意 $49–$99 / 月）。可与 `s31`（多席位）组成「App Store 订阅健康」系列，条目分开。API 申请与 RevenueCat 等集成另报价。

## 注意的坑

标题和正文**禁止**出现价格或折扣数字与「免费一个月」类表述——优惠本身在系统优惠控件里展示，不要写进文案。每订阅同时只能挂 1 条消息；改已发布消息会出草稿，要重新过审。ASC 原生优惠对仍在试用的用户可能拿不到（最短付费时长从 1 个月起）——不要向试用期高的 App 保证「上折扣就能救」。API 与第三方个性化需额外申请/集成，本条默认交付仍是 ASC 原生配置。以 Apple Developer News（2026-11-04）与 App Store Connect 帮助页为准。

## 来源线索

- [Apple Developer News: Retention messages now available（2026-11-04）](https://developer.apple.com/news/?id=fk9ps3gv)
- [App Store Connect Help: Configure retention messages](https://developer.apple.com/help/app-store-connect/manage-subscriptions/configure-retention-messages/)
- [App Store Connect API: Setting up retention messaging](https://developer.apple.com/documentation/appstoreconnectapi/setting-up-retention-messaging)
- [9to5Mac: Apple now lets developers offer discounts when users move to cancel（2026-11-04）](https://9to5mac.com/2026/11/04/apple-now-lets-developers-offer-discounts-when-users-move-to-cancel-subscriptions/)
- [MacRumors: App Store Subscription Retention（2026-11-04）](https://www.macrumors.com/2026/11/04/app-store-subscription-retention/)
- [RevenueCat: Apple Retention Messaging（2026-11-05）](https://www.revenuecat.com/blog/growth/apple-retention-messaging)
- 相关但独立：[s31 Apple 订阅多席位就绪体检](s31-apple-multiseat-subscription-readiness.md)、[s25 Stripe 订阅暂停留存就绪体检](s25-stripe-pause-retention-readiness.md)、[s2 订阅失败支付挽回](s2-dunning.md)
