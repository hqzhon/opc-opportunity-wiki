# FBA 部分退款按原因就绪体检（Partial Refunds × return reason）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏运营 |
| 优先 | 是 |
| 更新 | 2026-10-30 |

## 一句话

帮 FBA 卖家审计 Partial Refunds：退货原因是否已按经济性开关、全仓三套配置 vs 选定 ASIN Excel、百分比是否对齐单位退货成本——输出「先开高退货低损因 / 慎全仓一刀切 / 暂缓或关」分数卡。

## 为什么现在

Amazon Seller Forums（美站帖约三周前；英站公告约 **2026-10-09**）为 FBA Partial Refunds 增加 **按退货原因配置**：卖家可决定哪些原因提供「客户留货 + 部分退款」以降低退货运费与仓内处理，覆盖 **美国、英国、德国、法国、意大利、西班牙、加拿大**。两条路径：① 全仓最多三套「原因 → 退款百分比」配置；② 选定 ASIN 上传 Excel（同一 ASIN 可按原因多行）。未列入的产品/原因仍走标准退货。一线拆解（Method FBA **2026-10-18**、Big Internet Commerce 等）强调：程序本身不新，新增的是**原因级控制**；且 **买家仍须过 Amazon 资格审核**（画像与购买史），配置不等于每笔都会给出部分退款。已报名卖家默认继续对全部合格原因开部分退款——旺季退货浪前若未按原因收窄，可能在「买错」与「缺陷/错货」上用同一百分比伤利润或养坏预期。路径在 Settings → Fulfillment by Amazon → FBA returns evaluations → Partial refunds。卖家缺的是「哪些原因值得留货、百分比怎么按边际、全仓还是先 top ASIN」决策，不是再造 Seller Central 开关。与 `s8`（Shopify 退货原因→详情页）、`s14`（Shopify 退货窗）、`s23`（FBA 退货再售**分级**标准）不同，本条专盯 **留货式部分退款的原因开关与百分比经济性**。

## 目标客户

美/英/德/法/意/西/加 FBA、退货量可观的一人或小团队卖家；尤其是低件重、留货成本低于退回再售的品类（配件、低客单消耗品、包装完好的非卫生/非危险品），以及已开 Partial Refunds、担心「全原因默认」在假日退货浪里烧利润的店。

## 一人怎么起步

两周 concierge：导出近 90 天 customer returns，按原因 × ASIN 看量与单位全退成本（退回运费 + 处理 + 再售残值）→ 对照 Settings 里 Partial refunds：已关 / 全仓三配置 / 选定 ASIN Excel → 标「可留货」原因（如买错、不想要）vs「必须收回」原因（缺陷、错货、缺件、安全、疑似假货）→ 对 top 退货 ASIN 试算 10%/20%/30% 留货是否优于全退 → 交「先开选定 ASIN + 温和原因 / 全仓一刀切风险高 / 暂关盯数据」分数卡换 waitlist / 预付；验证后再做月度：部分退款接受率、二次退货、原因漂移与高退货费 ASIN 复盘（部分退款仍计入退货率与「经常退货」徽章逻辑，勿当「退货率化妆」）。

## 难度

中（规则与入口公开；多站点语境一致；Amazon 资格层不可控勿承诺「设了就每单省运费」；卫生品/危险品/不可退项不可入组；百分比过低则无人接受、过高则不如收回；勿与 `s23` 分级或 reimbursement 混为一谈）

## 变现路径

月订阅监测（示意 $29–$99，按 ASIN / 原因档）；一次性「原因 × 百分比 × 全仓 vs 选定」审计；可与 `s23` 并列为「FBA 退货：留货退款 × 再售分级」但不合并条目。

## 注意的坑

与 `s8-returns-listing`（独立站文案修复）、`s14-return-window-overrides`（Shopify 天数覆盖）、`s23-fba-customized-grading-readiness`（仓内再售怎么定级）不同，焦点是 **客户不寄回时按原因给多少钱**。配置后仅对新创建的退货请求生效。客户接受部分退款后仍可能再申请退货，状态有站点等待窗（美约 58 天、欧部分约 45 天）才落定。部分退款计入退货率相关指标。非上述七站 / 纯 FBM 不是首批客户。

## 来源线索

- [Seller Central (US): Return reasons now available for FBA Partial Refunds](https://sellercentral.amazon.com/seller-forums/discussions/t/ffe58695-e1e4-42a2-831d-357263b85d97)
- [Seller Central (UK): Return reasons now available for FBA Partial Refunds (~2026-10-09)](https://sellercentral.amazon.co.uk/seller-forums/discussions/t/89bd4625-599e-4938-9fd8-c327c1b4eeb5)
- [Method FBA: FBA Partial Refunds by Return Reason — UK Setup Guide (2026-10-18)](https://methodfba.com/blog/amazon-fba-partial-refunds-return-reasons-uk)
- [Big Internet Commerce: Keep the Customer, Cut the Return Cost — FBA Partial Refunds guide](https://biginternetcommerce.com/blogs/keep-the-customer-cut-the-return-cost-a-sellers-guide-to-amazon-fba-partial-refunds)
