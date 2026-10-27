# Compare-at / list_price 代理可见就绪体检

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-27 |

## 一句话

对 Shopify 独立站跑「划线价进 AI 渠道」专用体检：变体 Compare-at 是否真实高于现价、Catalog Mapping 的 Compare-at 开关与买家区域展示是否一致、过期大促价是否仍被当成 `list_price` 广播——给出可修分数卡与假日漂移报警。

## 为什么现在

2026-10-09 Shopify Changelog 与 Catalog API 更新：AI 购物代理经 Shopify Catalog 可读到商品的 compare-at，并以 UCP `list_price`（及 `list_price_range`）返回；此前代理往往只见现价、看不到店面划线折扣。官方三道闸——(1) Admin → Sales channels → Agentic → Shopify Catalog → Review product data mapping 里分享 Compare-at；(2) 该买家上下文下 compare-at **高于** `price`；(3) 该区域店面确实展示划线价（对 EEA 隐藏划线价的店不会对该买家返回 `list_price`）。多数店默认打开分享，但用 compare-at 当 MSRP/参考价的店会被默认关掉。假日季首年 agentic，错把过期活动价、空/零/颠倒变体价、或固定市场价覆盖后的脏数据广播出去，会让代理「理直气壮」讲错误折扣。MlabsGrowth 等有检查清单，AgentReady / 通识 Catalog 体检偏资格与属性——仍缺轻量「划线价可信度 × Mapping 开关 × 区域/市场一致性」订阅楔子。

## 目标客户

假日前后有明确大促/清仓、希望 ChatGPT / Copilot / Gemini 等代理正确展示「原价→现价」的 DTC 与跨境独立站；商品 feed 或客服已出现「AI 说的折扣跟结账不一致」的中小品牌。

## 一人怎么起步

两周 concierge：抽样主力变体导出 Price / Compare-at → 标空值、≤现价、过期活动残留、MSRP 误用 → 按优先市场核对固定市场价是否覆盖主档 → 对照店面集合卡/PDP/购物车与 Google 等自有 feed → 检查 Catalog Mapping 的 Compare-at 开关与 EEA 展示策略 → 用兼容 Catalog/代理预览（勿假设预览=某渠道最终 UI）抽查 `list_price` 有无 → 交「可开分享 / 先洗价再开 / 须关分享」分数卡换 waitlist / 预付；验证后再做 Embedded 监测（变体价变更、市场价覆盖、开关被误触报警）。

## 难度

中（字段与闸门写在公开 Changelog + Catalog API + Help；一人可两周探针。难点：勿承诺「开启后一定出现划线徽章或提升排名」；折扣码/自动折扣与商品级划线价不是同一机制；区域价格与广告合规需商家自行法务把关）

## 变现路径

月订阅监测（示意 $29–$99，按 SKU / 市场档）；大促前一次性划线价审计；可与 `s7` Catalog 体检打包给代运营。

## 注意的坑

与 `s7-agentic-catalog`（Catalog 资格、标题/属性、GTIN、可发现性）不同，焦点是 **compare-at → `list_price` 的可信与可控广播**；与 `s11-google-direct-checkout`（Google 直购结账就绪）不同，这里不绑 Google 结账路径。Shopify 文档用「might」描述代理如何展示划线——产品只保证「数据层一致」，不保证渠道 UI。MSRP/参考价场景应保持 Mapping 关闭或改真实原价字段，避免把虚高参考价当「折扣」。`list_price` 缺失只表示该买家上下文没有可展示划线价，不一定是故障。

## 来源线索

- [Shopify Changelog: Compare-at prices now shared to agentic channels (2026-10-09)](https://changelog.shopify.com/posts/compare-at-prices-now-displayed-to-agentic-channels)
- [Shopify Dev Changelog: Catalog API now returns compare-at prices as list_price (2026-10-09)](https://shopify.dev/changelog/posts/catalog-api-now-returns-compare-at-prices-as-list_price)
- [Shopify Help: Customizing your product data for Shopify Catalog](https://help.shopify.com/en/manual/shopify-catalog/mapping)
- [MlabsGrowth: Shopify Compare-at Prices — 6 Checks for AI Shopping](https://www.mlabsgrowth.com/blog/shopify-compare-at-prices-ai-agents)
