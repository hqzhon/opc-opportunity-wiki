# Shop Promise 就绪体检（US 履约徽章 × Catalog 排序信号）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-29 |

## 一句话

帮美国履约 Shopify 店审计 Shop Promise：店铺资格（US 仓 / Shop Pay / ≥90% 追踪）、品类 Trusted delivery、退货权益徽章、主题模块展示与 Paused 漂移——输出「可开 / 先补追踪或履约速度 / 徽章未露出」分数卡，并盯 Catalog / Shop 排序信号侧的徽章覆盖率。

## 为什么现在

Shopify Fall **'26 Edition**（**2026-10-28**）把 Shop Promise 写成网络侧主推：面向合格美国店的免费计划，商品页 / 结账 / Shop app 展示 Trusted delivery、Free returns、Returns accepted 等徽章；并写明 **merchant eligibility 已扩大约 20×**，带徽章商品可在 **Shop app 搜索与 Shopify Catalog 驱动的购物代理体验**里获得排序信号。Help Center 同步描述「更新版 Shop Promise」逐步切换：资格每日重评；店级要求含 active plan、至少一个向美国履约的美国 Location、开启 Shop Pay、合格订单追踪覆盖 ≥90%、账户良好；开启后按品类承运商首扫速度判 Trusted delivery、按退货规则判 Free returns / Returns accepted（Final sale 无退货权益）。旧版 $5 Shop Cash 晚达保障在迁到新计划后对新单不再适用，迁前订单索赔窗口至 **2026-12-16**。大量美仓店处在 Eligible 未开、Paused、或店级已 Active 但 top SKU 无徽章——Admin 有状态卡，但缺跨品类覆盖率与主题露出体检。与 `s7`（Catalog 商品资格/字段）、`s9`（代理政策问答）、`s14`（退货窗 override 矩阵）不同，本条专盯 **Shop Promise 店级资格 × 品级徽章 × Catalog/Shop 排序信号**。

## 目标客户

有美国履约仓、开或想开 Shop Pay、卖美本土或美仓发货的 Shopify DTC / 独立站；尤其想吃 Shop app 与 Catalog 代理发现、假日前需要「可信送达/退货」信任标的中小品牌与代运营。

## 一人怎么起步

两周 concierge：截图 Shipping and delivery → Shop Promise 状态（Eligible / Not eligible / Active / Paused）与 How to qualify 缺口 → 核 US Location、Shop Pay、追踪覆盖率报表 → 抽 top 20–50 SKU：Trusted delivery（品类承运商首扫 vs 目标、是否开 automated delivery dates）、Free returns vs Returns accepted vs Final sale → 主题编辑器确认 `delivery-promise__promise-container` / 徽章是否露出 → 对照 Catalog 是否已开、知识库退货事实是否与徽章一致 → 交「可开 / 先补追踪或履约 / 改退货规则 / 修主题」分数卡换 waitlist / 预付；验证后再做月度追踪覆盖与 Paused / 品类掉标漂移监测。

## 难度

中（规则公开；仅美国履约语境；新计划逐步 rollout，勿假设人人已迁完；勿承诺「开徽章一定涨 Shop/Catalog 排名」；履约速度是品类级历史表现，短期难「调设置即绿」）

## 变现路径

月订阅监测（示意 $29–$99，按 SKU / 品类档）；一次性 Shop Promise + 主题露出审计；可与 `s7`/`s9`/`s14` 打包成「Catalog 发现 + 信任徽章 + 退货规则」但不合并条目。

## 注意的坑

与 `s7-agentic-catalog`（商品能否进 Catalog）、`s9-agent-policy`（代理能否答运费/取消/自提）、`s14-return-window-overrides`（覆盖天数最短优先）不同，焦点是 **Shop Promise 资格与徽章权益**。Trusted delivery 依赖 automated delivery dates + 品类达目标，关自动预估会掉 Trusted delivery 但店级计划可仍 Active。退货权益跟 return rules，不是 override 矩阵本身。非美国仓 / 未开 Shop Pay 的店不是客户。平台原生有状态页——卖诊断优先级、品类覆盖率与漂移，而非再造 Admin 开关。

## 来源线索

- [Shopify News: Exponential — Fall '26 Edition (2026-10-28)](https://www.shopify.com/news/fall-26-edition-merchant)
- [Shopify Help: Shop Promise](https://help.shopify.com/en/manual/fulfillment/setup/shop-promise)
- [Shopify Help: Eligibility for Shop Promise](https://help.shopify.com/en/manual/fulfillment/setup/shop-promise/eligibility)
- [Shopify Help: Displaying Shop Promise on your product page](https://help.shopify.com/en/manual/fulfillment/setup/shop-promise/product-page)
- [Shop Help: Shop Promise](https://help.shop.app/en/shop/delivery-tracking/shop-promise)
