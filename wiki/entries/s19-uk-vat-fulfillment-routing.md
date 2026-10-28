# UK VAT 履约仓路由就绪体检（>£135 GB）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-28 |

## 一句话

帮发往 Great Britain 的 Shopify 店检查：>£135 订单是否被 order routing 指到非英国仓、结账是否因此跳过 VAT、UK location 库存与路由规则是否对齐——输出「会/不会在结账收 VAT」分数卡与修复清单。

## 为什么现在

Shopify Changelog（**2026-10-23**）起，发往 Great Britain 的 VAT 按 **order routing 选定的履约仓** 计算（与美国一致）：税前+运费前货值 **>£135 GBP** 且路由到非英国仓时，视为进口，**结账不收 VAT**——即便店里另有英国仓。≤£135、北爱尔兰、以及变更前已有订单不受影响。Help Center 明确：>£135 收 VAT 须有 **Active 英国履约仓**；Store Details 地址不是 location；英国仓停用或路由到海外 = 适用进口门槛；不能用 tax override 强行收 VAT；履约仓在结账时定，改单后不重算；draft order 可能不分配履约仓，>£135 须用真实结账测；英国仓无库存时路由可能改走海外。二级覆盖见 theshopifist（10-24）与 shopify-customize 多仓/3PL 解读。与 `s16`（欧盟海关三件套）、`s17`（€3+€2 结账回收）、`s18`（Managed Markets 一口价运费）不同，本条专盯 **UK VAT × order routing**。

## 目标客户

卖向英国（尤其高客单 >£135）且有多仓 / 海外仓 / 3PL 的 Shopify DTC；或英国有仓但库存不全导致 GB 单被路由到海外仓的店；假日旺季前要核税的跨境独立站。

## 一人怎么起步

两周 concierge：盘 Locations（是否有 Active UK 仓、Store Details 是否被误当成仓）→ 读 order routing 规则 → 用真实结账测 £130 vs £140 GB 地址、UK 仓有货 vs 无货 → 看 Tax 行是否出现/消失 → 交「路由会跳过 VAT / 需补库存 / 改路由 / 或改收 duties」分数卡 + FAQ/政策文案建议换 waitlist/预付；验证后再做漂移监测（路由改回、UK 仓缺货、新 SKU 未入 UK 仓）。

## 难度

中（规则公开；勿给税务法律意见；NI 规则不同；draft order 测税会误导须写进产品）

## 变现路径

月订阅监测（示意 $29–$99）；一次性路由税审计；可与发欧盟的 `s16`/`s17` 并列为「英欧税仓双线」但不合并条目。

## 注意的坑

与 `s16-eu-product-identifiers`、`s17-eu-uhf-duty-recovery`、`s18-mm-flat-rate-shipping` 不同，焦点是 **UK VAT 是否因履约仓路由在结账被跳过**。≤£135 仍收 VAT；数字货不走 £135 阈值；勿用 tax override 强行收 VAT；勿把 Store Details 当地址当 fulfillment location。

## 来源线索

- [Shopify Changelog: More accurate UK VAT based on fulfillment location (2026-10-23)](https://changelog.shopify.com/posts/more-accurate-uk-vat-based-on-fulfillment-location)
- [Shopify Help: Charge VAT on orders over £135 GBP](https://help.shopify.com/en/manual/taxes/uk/uk-tax-migrate)
- [The Shopifist: Oct 24 2026 — UK VAT tied to the fulfillment](https://theshopifist.com/p/the-shopifist-oct-24-2026-uk-vat-tied-to-the-fulfillment)
- [Shopify Customize: UK VAT gets smarter — fulfillment location drives tax on orders over £135](https://www.shopify-customize.com/blog/uk-vat-gets-smarter-fulfillment-location-drives-accurate-tax-on-orders-over-135)
