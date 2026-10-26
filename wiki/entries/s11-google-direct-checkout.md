# Google AI Mode / Gemini 直购结账就绪体检

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-26 |

## 一句话

对 Shopify 独立站跑「Google AI Mode / Gemini 直购结账」专用体检：哪些 SKU 因订阅/捆绑/定制/B2B/自提被排除、GMC 同步与政策闸门、Admin Direct checkout 开关，以及直购订单与 GA4/像素对不上的归因裂缝——给出可修清单与持续报警。

## 为什么现在

2026 假日季是 agentic 购物首年；Shopify 已把 Google AI Mode and Gemini 做成 Agentic Storefronts 渠道，合格店默认可直购结账（买家美/加/澳，店可在任意国家）。发现路径走 Google Merchant Center，与 ChatGPT 的 Shopify Catalog 路由不同。官方明确直购不支持订阅、捆绑、可定制、B2B-only、本地配送/自提，且标准 GA/自定义像素在直购结账不触发——大量店「Catalog 过了」仍有大半 SKU 进不了 in-chat Buy，或订单进了渠道报表却在 GA4 消失。StoreKnows / SearchCounselCo 等已有免费清单与说明文，但 App Store 仍缺轻量「SKU 排除矩阵 + GMC 同步漂移 + 归因对账」订阅楔子；现有 StoreKnows App 偏 AI 答商品事实，不覆盖直购结账路径。

## 目标客户

已上 Shopify、卖向美/加/澳、希望吃 Google AI Mode / Gemini 假日增量的 DTC 与跨境独立站；目录里混有订阅/捆绑/定制 SKU、或客服/财务在吵「AI 渠道单对不上 GA」的中小店。

## 一人怎么起步

两周 concierge：抽 20–50 个主力 SKU 对照官方不支持类型打标 → 查 Google & YouTube「自动同步商品/运费」、Settings → Policies 三件套、Sales channels → Agentic 里 Google Direct checkout 实态 → 交一份「可直购 / 须回站结账 / 须先修 feed」分数卡 + 归因对账说明，换 waitlist / 预付；验证付费后再做 Embedded App（定时重扫、新品入目录报警、渠道订单 vs 会话基线）。

## 难度

中（规则来自公开 Help Center，一人可两周探针；难点在 GMC 诊断需商家授权、rollout 因店而异勿承诺「一定出现 Buy」；与纯 Catalog / 政策 MCP 体检边界要划清）

## 变现路径

月订阅监测（示意 $29–$99，按 SKU/市场档）；一次性深度审计；可打包给代运营/SEO 顾问。

## 注意的坑

与 `s7-agentic-catalog`（跨代理 Catalog 可发现性）不同，焦点是 **Google 直购结账路径**（产品类型排除、GMC 同步、Admin 开关、像素缺口）；与 `s9-agent-policy`（政策工具答运费/取消/自提）也不同。Shopify/Google 若放宽捆绑/订阅直购支持，楔子会变窄——需保留「跨渠道归因对账 + 新品漂移报警」。文档地域要求会改版，探针要以当下 Help Center 为准，勿照抄过期「仅美国建店」旧文。勿宣称法律或平台准入保证。

## 来源线索

- [Shopify Help: Selling on Google AI Mode and Gemini](https://help.shopify.com/en/manual/online-sales-channels/agentic-storefronts/google)（直购资格、不支持类型、像素限制、政策要求）
- [Shopify Help: Managing agentic storefronts](https://help.shopify.com/en/manual/online-sales-channels/agentic-storefronts/agentic-home)
- [Shopify News: Welcome to the first holiday season of the agentic era (2026-10-06)](https://www.shopify.com/news/agentic-holiday-2026)
- [StoreKnows: Google AI Mode store eligibility gates (2026-10-02)](https://storeknows.com/resources/google-ai-mode-store-eligibility/)
- [SearchCounselCo: Google AI Mode Checkout setup, eligibility & tracking (2026-09-23)](https://searchcounselco.com/google-ai-mode-checkout-for-shopify-setup-eligibility-tracking/)
