# FBA 退货定制分级就绪体检（Customized grading × Grade and Resell）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏运营 |
| 优先 | 是 |
| 更新 | 2026-10-30 |

## 一句话

帮美国站 FBA 卖家审计 Customized grading：高退货 ASIN 是否已设规则、封口/包装/配件标准是否写清、未覆盖 ASIN 是否仍走默认分级、Grade and Resell 二手价百分比是否对齐——输出「先配高退货 SKU / 按包装分规则 / 慎全仓一刀切 / 暂缓」分数卡。

## 为什么现在

Amazon Fulfillment by Amazon 团队在 Seller Central（Seller Forums 公告约 **2026-10-14**）上线 **Customized grading**：卖家可自定义「可按全新再售」标准（封口与包装、随附配件、真伪标识、设备功能等），规则可按单个 ASIN、整仓或 CSV 上传；Amazon 将规则作为**分级指导**（非保证结果），未覆盖 ASIN 继续走默认分级，并与 **FBA Grade and Resell** 等回收项目并行。一线拆解（eStore Factory / SellerKit 等同日复核）指出：默认分级不知道你的产品——缺配件或只拆封袋的良品可能进不可售，缺关键件的残次却可能被标全新再售招差评；假日购有长退货窗，**大量 Q4 退货会在 1 月落地**，规则宜在旺季退货浪前配好。路径在 Settings → Orders → Recovery → Customized grading。卖家缺的是「先给哪批 ASIN、封口类型怎么分组、二手价百分比怎么设」决策，不是再造一个 Seller Central 开关。与 `s8`（Shopify 服装退货原因→详情页修复）、`s14`（Shopify 退货窗 override）、`s22`（Amazon 多渠连接）不同，本条专盯 **FBA 退货再售分级标准与 ASIN 覆盖**。

## 目标客户

美国站 FBA、退货量可观的一人或小团队卖家；尤其是密封件、礼盒、配件依赖型（美妆套装、电子配件、服装配饰）品牌，以及已开或想开 Grade and Resell、担心「全新再售」标准失控的店。

## 一人怎么起步

两周 concierge：导出 FBA customer returns 报告，按退货量排 top 20–50 ASIN → 在 Customized grading 看是否已有规则、哪些仍默认 → 按封口/包装类型分组（同类型共用规则，不同类型拆规则）→ 写清「盒内必含配件 / 仅拆封是否仍可全新 / 可否重封或改标二手」→ 若已开 Grade and Resell，核对 Like New / Very Good / Good / Acceptable 二手价百分比 → 交「先配高退货 ASIN / 全仓一刀切风险高 / 暂用默认 + 盯投诉」分数卡换 waitlist / 预付；验证后再做月度：规则覆盖率、全新再售后差评/二次退货、与 reimbursement 抽检并跑（规则不替代丢件/未入库索赔）。

## 难度

中（规则与入口公开；US FBA 语境；Amazon 明示为 guidance 勿承诺「设了就 100% 按你的标准分级」；全仓一刀切易误伤；勿与 reimbursement 审计混为一谈）

## 变现路径

月订阅监测（示意 $29–$99，按 ASIN / 规则档）；一次性高退货 ASIN + 包装分组 + Grade and Resell 价百分比审计；可与 Amazon 侧 `s22` 并列为「多渠枢纽 × 退货分级」但不合并条目。

## 注意的坑

与 `s8-returns-listing`（独立站退货原因驱动 listing 文案）、`s14-return-window-overrides`（Shopify 退货天数覆盖）、`s22-amazon-multichannel-readiness`（多渠连接与 MCF）不同，焦点是 **FBA 仓内退货再售怎么定级**。规则是 guidance，不是 SLA。每个品类规则对同一 ASIN 通常只生效一条，新规则替换旧规则。低风险 ASIN 可留默认。分级规则不覆盖 Amazon 丢失/损坏/未入库——reimbursement 仍要单独盯。非美国站 / 纯 FBM 不是首批客户。

## 来源线索

- [Seller Central forums: Customize how your FBA returns are graded for resale](https://sellercentral.amazon.com/seller-forums/discussions/t/731e6e69-5bfa-4a4f-9685-acb9da76153b)
- [Sellers Ask Sellers: Set your own grading criteria for FBA returns (2026-10-14)](https://sellersasksellers.com/t/set-your-own-grading-criteria-for-fba-returns/7633)
- [eStore Factory: Amazon Lets FBA Sellers Set Their Own Grading Criteria (2026-10-14)](https://www.estorefactory.com/amazon-update/amazon-fba-customized-grading-returns-2026/)
- [SellerKit: Customized Grading for FBA Returns — sellable as new by ASIN/CSV (2026-10-14)](https://sellerkit.me/fba-updates/fba-returns-customized-grading-sellable-as-new-criteria-2026)
