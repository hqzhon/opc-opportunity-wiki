# 渠道商品数据映射就绪体检（Google / Meta / TikTok / Catalog）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-29 |

## 一句话

帮多渠道 Shopify 店审计「每个销售渠道实际收到的商品字段」：覆盖率缺口、标题/品牌/色号组合规则、Liquid 清洗、与渠道内编辑器冲突——输出「可开映射 / 先补源数据 / 仍需 feed 工具」分数卡与漂移报警。

## 为什么现在

Shopify Changelog（**2026-10-28**）上线 **Map product data by sales channel**：统一 Channel mapping 页可按渠道改标题、图片、类目、颜色等字段来源，支持组合字段（如 `brand — title`）、Liquid 过滤器（append / replace / truncate 等，**不含** if/for/assign）、按商品覆盖、批量改，以及每字段 **coverage %**。Help Center 明确：改的是发往渠道的数据，**不影响网店前台**；空源回落到渠道默认；Shop / Shopify Collective 不在映射范围；Shopify Catalog 也走同一套页（含 list_price / 变体分组）。一线解读（Ecommerce Paradise、Power Commerce）指出：Google 前 70 字可读性、禁止促销/店名进标题、共享 metafield 一改多渠、以及「渠道内标题编辑 vs mapping 谁赢」仍未写清——中小店缺的是跨渠策略与补数优先级，不是再造一个 Admin 页。与 `s7`（Catalog 资格/可发现性）、`s15`（compare-at → list_price）不同，本条专盯 **多销售渠道字段映射与覆盖率治理**。

## 目标客户

同时开 Google/YouTube、Meta、TikTok 等销售渠道、SKU 百级以上的 Shopify DTC / 跨境独立站；或刚开 Agentic Catalog、标题仍是供应商型号、Merchant Center / 渠道诊断常因缺属性被拒的店。

## 一人怎么起步

两周 concierge：盘已启用渠道 → 导出各渠 coverage %（title / brand / identifier / color 等）→ 抽 top 20 SKU 预览 Google vs Meta vs Catalog 标题与图 → 核对 Google 前 70 字与违禁词、共享 metafield 副作用、渠道内是否另有标题覆盖 → 交「先补上游 / 改默认映射 / 保留 feed 工具做条件规则」分数卡换 waitlist / 预付；验证后再做月度覆盖率与拒登漂移监测。

## 难度

中（规则公开；勿承诺「改 mapping 一定涨 CTR」；条件逻辑仍可能要 DataFeedWatch 等；plan / 渠道名单 Shopify 未全写死）

## 变现路径

月订阅监测（示意 $29–$99，按渠道数 / SKU 档）；一次性多渠 mapping 审计；可与 `s7`/`s15` 打包成「Catalog + 广告渠数据三线」但不合并条目。

## 注意的坑

与 `s7-agentic-catalog`（Catalog 资格与代理可发现）和 `s15-compare-at-list-price`（划线价是否进 list_price）不同，焦点是 **各广告/社交销售渠道字段源与覆盖率**。Shop 与 Collective 不可映射。共享源 metafield 改一次影响所有引用渠。预览≠渠道是否过审。勿把平台便利项当成护城河——卖诊断优先级、跨渠模板与漂移，而非再画一张 mapping UI。

## 来源线索

- [Shopify Changelog: Map product data by sales channel (2026-10-28)](https://changelog.shopify.com/posts/map-product-data-by-sales-channel)
- [Shopify Help: Customizing product data for sales channels](https://help.shopify.com/en/manual/online-sales-channels/channel-mapping)
- [Shopify Help: Customizing your product data for Shopify Catalog](https://help.shopify.com/en/manual/shopify-catalog/mapping)
- [Ecommerce Paradise: Shopify Lets Each Sales Channel Get Its Own Product Titles](https://ecommerceparadise.com/shopify-channel-mapping-product-data/)
- [Power Commerce: Map product data by sales channel](https://powercommerce.com/blogs/shopify-updates/shopify-s-channel-mapping-control-and-optimize-product-data-sent-to-each-sales-channel)
