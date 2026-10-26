# UCP 零售门店发现就绪体检（Physical storefront × 库存 × 自提）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-26 |

## 一句话

对多门店 Shopify 零售商跑「UCP location.search / lookup」专用体检：哪些 Admin Location 会（或错误地）被代理发现、缺 geo / 错标 Physical storefront、Available 与货架不一致、以及「搜到店 ≠ 可自提结账」的裂缝——给出可修分数卡与持续漂移报警。

## 为什么现在

2026-10-22 Shopify 为 UCP `2026-08-25` 上线 `dev.ucp.common.location.search` 与 `lookup`：有合格零售 Location 的店在 `/.well-known/ucp` 广告能力，代理可经 storefront MCP 按店名/城市/买家同意的距离与最多 10 个 variant 过滤找店。官方明确：匹配只是 provisional（非库存数、非预约、非自提承诺），且 **所选门店的自提结账尚未经该 API 支持**；不支持营业时间/设施等过滤。假日季 agentic 购物首年，多门店品牌若把仓库标成 Physical storefront、缺坐标、或把 On hand 当 Available，代理会把买家导到错店或空承诺。Neat Digital 等已有 7 点运营清单与测试矩阵（内容/顾问），App Store 有 AgentReady（偏 schema/llms.txt 通识）、Driftwatch（夜间全目录漂移）、SAAS 店找器（店面 UX）等相邻产品，但仍缺轻量「UCP 发现面 ↔ Physical 开关 ↔ 分店 Available ↔ 自提/履约设置」对照的订阅楔子。

## 目标客户

已开 Shopify POS / 多 Location、至少一家真门店、希望吃 ChatGPT / 其他 UCP 代理「附近有货」问询的 DTC 与跨境品牌；客服已开始收到「AI 说某店有货但到店没有 / 不能自提」类工单的中小零售商。

## 一人怎么起步

两周 concierge：拉 Location 名册 → 标出应公开的 Physical storefront vs 仓/办/3PL → 核对地址与 geo、分店 Available（对比 On hand/Committed）→ 对 10–20 个主力 variant 用兼容客户端或手工测 `search_locations` / `lookup_locations` → 对照 Shipping 里「到店自提」与路由规则 → 交一份「可被发现 / 发现但勿承诺自提 / 须先修数据」分数卡，换 waitlist / 预付；验证付费后再做 Embedded App（定时重扫、新品/新店漂移、假日高峰报警）。

## 难度

中（规则与能力边界写在公开 changelog；一人可两周探针。难点：需商家授权读 Location/库存、代理侧协商因客户端而异勿承诺「一定出现在某 AI」；与纯 Catalog / 政策 FAQ / Google 直购体检边界要划清）

## 变现路径

月订阅监测（示意 $29–$99，按 Location × SKU 档）；一次性深度审计；可打包给代运营 / POS 实施商。

## 注意的坑

与 `s7-agentic-catalog`（跨代理 Catalog 可发现性）不同，焦点是 **零售 Location 发现路径**；与 `s9-agent-policy`（政策工具答运费/取消/自提文案）不同，这里查的是 Location 是否该被搜到、库存状态是否支撑答案；与 `s11-google-direct-checkout`（Google 直购 SKU 排除）亦不同。AgentReady / UCPtools 等通识就绪若很快覆盖 Location 矩阵，楔子会变窄——需保留「发现 vs 自提/履约设置对账 + 分店 Available 漂移」。勿把仓库标成门店「冲发现」；勿宣称法律或平台流量保证。

## 来源线索

- [Shopify Changelog: Discover a merchant's retail stores with UCP location search and lookup (2026-10-22)](https://shopify.dev/changelog/posts/discover-a-merchant-s-retail-stores-with-ucp-location-search-and-lookup)
- [Neat Digital: Shopify UCP Store Finder retail location readiness guide (2026-10-23)](https://neat.digital/blogs/blogs/shopify-ucp-retail-location-search-inventory-readiness-guide-2026)
- [Shopify Help: inventory states (Available vs On hand / Committed)](https://help.shopify.com/en/manual/inventory-and-locations/fundamentals/inventory-states)
- [AgentReady App Store listing](https://apps.shopify.com/agentreadyapp)（通识 AI 就绪，边界对照）
- [Driftwatch App Store listing](https://apps.shopify.com/driftwatch)（夜间库存漂移，边界对照）
