# Shopify 自定义 App IP 白名单就绪体检（11-20 新装须配 × 2027-01-01 存量须配 × 漏一个连坐全部）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 技术 |
| 优先 | 是 |
| 更新 | 2026-11-12 |

## 一句话

帮给客户店铺做「自定义 App」（custom app）的外包开发者、小代理和 Shopify Partner，在 **2026-11-20**（新装）和 **2027-01-01**（存量）前把自己名下每个装在外部店铺上的自定义 App 都配好 IP 白名单：先盘点「哪些 App 装在了别的组织的店上」，再查每个 App 实际从哪儿打 Admin API，填 IP/CIDR 或托管商 ASN+国家、用最近 30 天流量测过再打开 Enforcement——因为 1 月 1 日起**漏掉一个，会影响你往外部店铺安装任何 App**。

## 为什么现在

- Shopify 官方 changelog（**2026-11-11**，「IP allowlists are now required for custom apps installed outside your organization」）：装在**所属组织之外**店铺上的自定义 App 必须配 IP 白名单。
  - **2026-11-20 11:59 PM ET**：新安装须已有白名单，否则装不上外部店铺；
  - **2027-01-01 11:59 PM ET**：已装在外部店铺上的存量 App 也必须有白名单；
  - 同一 Partner 名下有多个 App 时，从 1 月 1 日起**只要有一个没配，就会影响你往外部店铺安装任何 App**（官方原话没细说具体怎么影响，只能当成「全部配完」处理）。
- 不受影响：只装在本组织店铺上的 App；商家自己在 Dev Dashboard 或后台建的 App；公开 App（另有一套更早的强制，见 `s37`）。
- 这推翻了此前「自定义 App 不受强制」的说法（`s37` 写于 11-06 时如此）。做外包的人往往手上有一堆多年前给不同客户做的「库存同步 / 导单 / ERP 对接」小 App，很多跑在 Vercel、Lambda、Cloudflare Workers 这类动态出口上，没人记得清楚——盘点本身就是活。
- 配置规则（官方文档）：最多 250 个 IP/CIDR（IPv4 `/16` 或更窄）；最多 10 个 ASN、最多 10 个国家，ASN 建议必配国家；Flow「Send HTTP request」和 Oxygen 店面里用该令牌打 Admin API 的请求**一律被拒**，要先改架构。

与 `s37`（公开 App IP 白名单：11-12 批量失败 / 11-20 下架 / 04-01 返回 403）、`s33`（公开 App 过期离线令牌）不同：本条只管 **Partner 名下、装在客户店铺上的自定义 App**，客户是做外包的人而不是 App Store 开发者，后果是「装不上外部店铺」而不是下架。

## 目标客户

给 Shopify 商家做定制开发的自由职业者、1–5 人代理和 Shopify Partner（尤其手上有多个历年客户自定义 App、跑在 serverless / 动态 IP 上的）；以及请过外包、店里装着自定义 App、想确认「1 月后还能不能正常用」的商家（他们可以把这份清单转给原外包）。

## 一人怎么起步

两周 concierge：先发一张公开自查表（「你名下有几个自定义 App 装在客户店上？每个跑在哪个托管商？有没有用 Flow Send HTTP 或 Oxygen 调 Admin API？Dev Dashboard 里白名单是关着、已配未强制，还是已强制？」），发到 Shopify Partner 社区、r/shopifyDev、X 和国内 Shopify 外包群换 waitlist。对报名的 5–10 家：只读看 Dev Dashboard 里的 App 清单与安装店铺、各 App 的 Logs 出口地址；静态出口整理 CIDR，动态出口对照托管商 ASN 并定国家；跑「Test against recent traffic」，标出会被挡的地址；Flow / Oxygen 调用单列「须改架构」。交付「App × 店铺 × 出口类型 × 白名单状态」总表和逐步截图清单，11-20 前先保住要新装的 App，12 月内清完存量。之后延伸为按 App 数收费的出口 IP/ASN 变更监控，可与 `s33`/`s37` 打包成「Shopify App 安全双检」。

## 难度

中（技术本身不难，难在盘点清楚历年散落的 App 与真实出口；Flow / Oxygen 是硬限制）

## 变现路径

一次性盘点+配置（示意 $99–$299 / App，或按 Partner 整包 $499–$1,499）；月度出口变更监控与 API 日志巡检（示意 $29–$99 / 月）；顺带承接迁移到固定出口（NAT 网关 / 静态代理）的小改造单。

## 注意的坑

以 Shopify 官方 changelog 和文档为准，「漏一个影响全部」的具体机制官方没写细，不要夸大成「全部 App 立即停用」。ASN 是托管商共享网络，能填 IP 就别只填 ASN，填 ASN 一定配国家。只用客户授权的只读权限，不要索要或保存客户的访问令牌。价格只是示意，需自行验证。

## 来源线索

- [Shopify changelog: IP allowlists are now required for custom apps installed outside your organization（2026-11-11）](https://shopify.dev/changelog/posts/ip-allowlists-are-now-required-for-custom-apps-installed-outside-your-organization)
- [Shopify Docs: Restrict API access with an IP allowlist](https://shopify.dev/docs/apps/build/dev-dashboard/ip-allowlist)
- [Shopify Docs: About app security](https://shopify.dev/docs/apps/build/security)
- [Sid Techno: Shopify IP allowlists for custom apps — the 20 November deadline and the clause agencies should read twice](https://sidtechno.com/blog/shopify-ip-allowlist-custom-apps-deadline)
- 相关但独立：[s37 Shopify 公开 App IP 白名单就绪体检](s37-shopify-ip-allowlist-readiness.md)、[s33 Shopify 公开 App 过期离线令牌迁移体检](s33-shopify-expiring-offline-token-readiness.md)
