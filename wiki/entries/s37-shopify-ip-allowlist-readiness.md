# Shopify 公开 App IP 白名单就绪体检（11-12 批量失败 × 11-20 下架 × ASN/静态 IP）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 技术 |
| 优先 | 是 |
| 更新 | 2026-11-06 |

## 一句话

帮在 Shopify App Store 上架公开 App 的独立开发者，在 **2026-11-12 / 11-20** 前把 Dev Dashboard 的 IP 白名单配好并打开 Enforcement：分清自己是静态 IP 还是 serverless/动态出口、该填 CIDR 还是 ASN+国家、Flow Send HTTP / Oxygen 店面这类会 403 的调用要不要改架构——输出「未配 / 已配未强制 / 已强制且最近 30 天流量测过」分数卡和一份可直接照做的清单。

## 为什么现在

Shopify 10-27 还只是**建议**开 IP 白名单；**2026-11-05** 起改成公开 App **硬性要求**——假日季临近，官方希望尽快限制令牌能从哪些网络打 Admin API。截止日（均为 ET 11:59 PM）：

- **11-12**：未配白名单的公开 App，批量查询 / 批量变更直接失败
- **11-20**：未配白名单的公开 App 从 App Store **下架**、禁止新安装，并在商家 Settings > Apps 里被标记
- **2027-01-15**：商家后台看到警告
- **2027-04-01**：该 App 的 Admin API 请求被拒（与过期离线令牌同一终态）

不受影响：自定义 App；商家在 Dev Dashboard 或后台自建的 App。配置路径：Dev Dashboard → Settings → IP allowlist → Manage；静态出口填 IP/CIDR，serverless/动态出口填 Networks/ASN + 建议勾选国家；用最近 30 天流量跑 Test，再打开 Enforcement，并在白名单外发一次请求确认拿到 403。

规则上限：最多 100 个 IP/CIDR（IPv4 `/16` 或更窄，IPv6 `/32` 或更窄）；最多 10 个 ASN + 最多 10 个国家；只要公网地址，NAT 后填网关地址。**不能**靠白名单保住的调用：Shopify Flow「Send HTTP request」用的令牌、Oxygen 店面里打 Admin API（Shopify 确认不了源 IP → 一律拒）。开发店 preview、嵌入式页面上的 Direct API **永远不会**因白名单被拒。

这和 `s33`（过期离线令牌：01-01 下架 / 04-01 403）同属 App Security Hub，但是**另一套控制**：截止日更早、要动的是出口网络而不是令牌刷新。可以一次卖「安全双检」，条目必须分开。

## 目标客户

在 Shopify App Store 有公开 App、由 1–3 人维护的开发者或小工作室：尤其是走 serverless / 动态 IP（Vercel、Cloudflare Workers、Lambda 等）、还没摸过 Dev Dashboard IP allowlist 的；以及依赖批量操作、Flow Send HTTP、或从 Oxygen 店面打 Admin API 的工具型 App。自定义 App 和商家自建 App 不受强制，不是首要客户。

## 一人怎么起步

两周 concierge：先发一张公开自查表（「你的 App 是静态 IP 还是 serverless？有没有开过批量操作？有没有 Flow Send HTTP 或 Oxygen 店面调 Admin API？Dev Dashboard 里 IP allowlist 现在是关着还是已强制？」），发到 Shopify 开发者社区、App Security 版、r/shopifyDev 和 X 上的 Shopify app 圈换 waitlist。对报名的 5–10 个 App：只读看部署方式与最近 Admin API 流量来源；静态出口整理 CIDR 清单，动态出口对照托管商 ASN 文档并建议国家列表；跑一遍「Test against recent traffic」，标出会被挡的自家地址；对 Flow / Oxygen 调用单独标「架构要改 / 可申请延期」。交付一份分数卡 + 逐步截图清单（填白名单 → Test → Enforcement → 白名单外验 403）。先收一次性就绪体检费，再延伸为「出口 IP/ASN 变更监控 + 与 `s33` 令牌健康打包」的月度订阅。

## 难度

中（要分清静态 IP vs ASN、读懂 CIDR/NAT、会用 Dev Dashboard 流量测试；Flow / Oxygen 不兼容是硬限制，延期申请只适合「令牌跑在商家基础设施上」的架构，不能当成通用逃课）

## 变现路径

一次性 IP 白名单就绪体检（示意 $99–$299 / App）；固定价「静态 CIDR 或 ASN+国家配置 + 流量测试 + Enforcement 验收」项目（示意 $300–$800）；之后做出口网络变更与 Shopify 安全变更月报订阅（示意 $29–$79 / 月）。可与 `s33`（过期离线令牌）、`s3`（平台伴生 App）组成「Shopify App 安全双检」套餐，但条目分开。App 若从商家基础设施调 Admin API，可协助整理延期申请材料，但定位仍是体检与清单，不是代运维。

## 注意的坑

白名单只管「令牌从哪来」，不管「令牌会不会过期」——别告诉客户「开了白名单就不用迁过期令牌」，`s33` 的 01-01 / 04-01 照旧。ASN 是共享网络：同一 ASN 里别的租户若偷到令牌也能打，能填静态 IP 就别只填 ASN；填了 ASN 务必收窄国家。NAT 后填的是网关公网地址，别把内网段写进去。Flow Send HTTP 与 Oxygen 店面 Admin API **配了也会 403**，唯一正道是改掉这类暴露令牌的架构；延期只适用于「从商家基础设施调 Admin API」且应尽快收敛令牌暴露面。Enforcement 打开前必须先跑最近 30 天流量测试，否则把自己的合法出口也挡掉。开发店 preview 和嵌入式 Direct API 测不出白名单效果，验收要在真实出口外打一次。别承诺「保证不被下架」，以 Shopify Changelog、App Security 博文和 Dev Dashboard IP allowlist 文档为准。

## 来源线索

- [Shopify Changelog: IP allowlists are now required for public apps（2026-11-05）](https://shopify.dev/changelog/posts/ip-allowlists-are-now-required-for-public-apps)
- [Shopify Changelog Blog: App security updates — IP allowlist is now required（10-27 建议 → 11-05 强制；与过期令牌对照表）](https://shopify.dev/changelog/blog/app-security-updates-ip-allowlist-is-now-required)
- [Shopify Dev Docs: Restrict API access with an IP allowlist（设置、CIDR/ASN 规则、Flow/Oxygen 不兼容、测试与 Enforcement）](https://shopify.dev/docs/apps/build/dev-dashboard/ip-allowlist)
- 相关但独立：[s33 Shopify 公开 App 过期离线令牌迁移体检](s33-shopify-expiring-offline-token-readiness.md)
