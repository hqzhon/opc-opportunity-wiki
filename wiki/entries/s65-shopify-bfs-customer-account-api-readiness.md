# Shopify 退货与订阅 App 买家登录就绪体检（12-01 起须用 Customer Account API × 否则可能失去 Built for Shopify）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 技术 |
| 优先 | |
| 更新 | 2026-11-19 |

## 一句话

帮已经拿到或正在申请 Built for Shopify 的退货 / 换货 App、订阅 App 开发者，在 **2026-12-01** 前核对买家自助流程（查退货、跟换货、改订阅等）是不是已经把 **Customer Account API 作为主要登录方式**；官方 Changelog 写明，到期未达到这条要求的 App **可能失去 Built for Shopify 状态**。先出一份「已切主登录 / 新旧混用 / 仍用旧登录 / 无买家自助因而本条截止日可能不适用」分数卡，再决定要不要另报价做接入。

## 为什么现在

- Shopify 开发者 Changelog（**2026-06-17**，标记为 *Action required*）：自 **2026-12-01** 起，提供买家自助体验的 **Returns and exchanges** 与 **Subscription** App，必须使用 Customer Account API 做顾客身份验证，以便店面、App 和顾客账户共用一套登录。到期未达到要求的 App，**有失去 Built for Shopify 状态的风险**。
- 现行 [Built for Shopify 要求](https://shopify.dev/docs/apps/launch/built-for-shopify/requirements) 把同一句话写进了分类条款：
  - **5.12.4**（退货与换货 App）：须将 Customer Account API 作为顾客认证的**主要方式**；
  - **5.14.5**（订阅 App）：同样要求。订阅 App 另有 **5.14.4**，须用 Customer Account UI extensions 让顾客查看和管理订阅——这是并列的 BFS 条款，但 6-17 Changelog 点名的截止日针对的是登录方式。
- 现在离 12-01 大约两周。接入授权码流程 + PKCE、改买家自助入口并做回归，通常比勾选配置更久，所以适合先做差距体检，而不是默认两周内做完改造并保住徽章。
- 这不是全站商家必办，也不是所有 Shopify App 的下架令。官方后果写的是 BFS 状态风险，没有写 App Store 下架或 Admin API 被拒。没有买家自助、或不走 BFS 的退货 / 订阅 App，不要套用这条截止日。

与 s33（过期离线令牌）、s37 / s47（IP 白名单）不同：那几条管的是 App 调 Admin API 的安全与令牌；本条管的是**买家**在自助流程里如何登录。

## 目标客户

在 Shopify App Store 上架退货 / 换货或订阅类公开 App、已经有或正在冲 Built for Shopify，并且给买家做了自助退货、换货跟踪或订阅管理（跳过、换货、改周期等）的独立开发者和小工作室。尤其是买家登录还在用旧 Customer API、Multipass、自建账号或魔法链接，或只把 Customer Account API 当作备用选项的人。没有买家自助界面的后台退货工具、商家自建 App、以及不做 BFS 的工具，不是本条首批。

## 一人怎么起步

两周 concierge：先发一份公开自查表（「你的 App 是退货 / 换货还是订阅？有没有买家自助入口？现在买家怎么登录？有没有或是否在申请 Built for Shopify？」）到 Shopify 开发者社区、r/shopifyDev 和 X 上的 Shopify app 圈换 waitlist。对报名的 5–10 个 App：只根据对方演示或只读材料，核对买家自助链路的登录方式是否已把 Customer Account API 当作主要方式；标出仍走旧登录、新旧并行、或订阅管理尚未用 Customer Account UI extensions 的页面。交付分数卡 + 最小改造清单（授权码 + PKCE、回跳与注销、令牌刷新、订阅侧 UI extension 是否另要做）。只出书面对照，不代改代码、不代提交 BFS 审核，也不保证审核结果。先收一次性体检费；需要接入或补 UI extension 的作为独立开发单另报。

## 难度

中偏高（官方把适用类目、截止日和「主要登录方式」写清楚了；判断一条流程算不算买家自助、旧登录能不能退，需要看实际产品。完整接入 Customer Account API 是正经的工程改造，两周体检不要写成「保证 12-01 前改完并保住 BFS」）

## 变现路径

一次性登录方式就绪体检（示意 $99–$299 / App）；需要接入 Customer Account API 或补 Customer Account UI extensions 的固定价改造另报（示意 $500–$2,000，视页面数和现有认证架构）；临近 12-01 的复查或 BFS 材料整理可另报价。不包含代提交 BFS 申请，也不保证能保住或拿到徽章。

## 注意的坑

不要写成「所有 Shopify App 或所有商家必须在 12-01 前迁移」：官方范围是提供买家自助体验的退货 / 换货与订阅 App，后果是可能失去 Built for Shopify，不是下架或 API 403。不要把「支持一下 Customer Account API」当成合规：要求写的是 **primary method**（主要方式）。不要和 s33 / s37 / s47 混成同一份交付：那些是开发者调 Admin API 的安全要求，截止日和对象都不同。不要把商家后台登录、Partner 账号 MFA，或店铺自己的顾客账户设置，当成已经满足本条。订阅 App 不要只查登录、漏掉 5.14.4 的 Customer Account UI extensions；但也别把所有 BFS 分类条款都说成 12-01 强制项——6-17 Changelog 点名的是认证方式。你不是 Shopify Partner 审核员，不代登录 Partner Dashboard 或 Dev Dashboard，不保证 BFS 审计结果。价格只是示意，需自行验证。

## 来源线索

- [Shopify 开发者 Changelog：Built for Shopify requirements for Returns and exchanges apps and Subscription apps（2026-06-17；12-01 起买家自助须用 Customer Account API 认证，否则可能失去 BFS）](https://shopify.dev/changelog/posts/built-for-shopify-requirements-for-returns-and-exchanges-and-subscription-apps)
- [Shopify 官方 Built for Shopify 要求（5.12.4 退货 / 换货、5.14.5 订阅：须将 Customer Account API 作为主要认证方式；5.14.4 订阅须用 Customer Account UI extensions）](https://shopify.dev/docs/apps/launch/built-for-shopify/requirements)
- [Shopify 文档：Authenticate customers with the Customer Account API](https://shopify.dev/docs/storefronts/headless/building-with-the-customer-account-api/authenticate-customers)
- [Shopify 文档：Getting started with the Customer Account API](https://shopify.dev/docs/storefronts/headless/building-with-the-customer-account-api/getting-started)
- 相关但独立：[s33 Shopify 公开 App 过期离线令牌迁移体检](s33-shopify-expiring-offline-token-readiness.md)、[s37 Shopify 公开 App IP 白名单就绪体检](s37-shopify-ip-allowlist-readiness.md)、[s47 Shopify 自定义 App IP 白名单就绪体检](s47-shopify-custom-app-ip-allowlist-readiness.md)
