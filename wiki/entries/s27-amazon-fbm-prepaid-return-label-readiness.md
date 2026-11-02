# Amazon FBM 预付退货面单就绪体检（12-18 起 × 7 天时钟 × 自动免退退款）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | 是 |
| 更新 | 2026-11-02 |

## 一句话

帮 US 自发货（FBM）卖家在 **2026-12-18** 前把退货流程改到合规：找出还在用「仅地址」退货或靠买家消息发面单的 SKU 与流程，按 SKU 定「上传预付面单 / 直接免退退款」阈值，排好每日队列与 7 天到期提醒——别让 Amazon 替你自动退款、钱货两空。

## 为什么现在

Amazon Services 团队给 US 卖家的通知写明：**2026-12-18** 起，US 自发货订单的所有退货（重货/大件暂时除外）**必须提供预付退货面单**；让买家自付邮费的「仅地址」方式不再合规。每个退货申请起算 **7 个自然日**内，卖家必须二选一：

- 在 **Manage seller-fulfilled returns** 流程里把预付面单**上传到该退货申请**；或
- **全额退款且不要求退货**（returnless refund）。

两样都没做，Amazon 可能**自动免退退款并从卖家账户扣款**——买家留货、卖家扣钱。通过 Buyer-Seller Messaging 或其他渠道发的面单**不算数**。

坑点：

- **时机最差**：正好压在假日退货高峰与 USPS 2026 假日临时涨价窗口（10-04 至 2027-01-17）里；若 Amazon 照去年延长假日退货期，大部分假日单的退货都会落在新规下。
- **说明不一致**：PPC Land 对照发现邮件与帮助页至少四处对不上（国际退货 2 天还是 7 天、SKU 豁免是否还有效、重货大件怎么定义、自动免退退款能否走 SAFE-T 索赔），必须逐店实测。
- **旧流程里的隐患**：「买面单 → 发消息给买家」这种 VA 常用做法直接失效；24 小时手动授权时限并未取消，不能把 7 天当成统一响应期。
- **低价 vs 高价 SKU**：低价品退货邮费可能接近货值，主动免退退款更划算；高价品一旦漏掉 7 天，就是丢货又丢钱。

与 `s23`（FBA 定制分级）、`s24`（FBA 按原因部分退款）不同：本条专盯 **自发货（FBM）退货面单合规与免退阈值**，Amazon 不替卖家处理这些退货。

## 目标客户

US 站自发货占比高的卖家：自有仓发货的品牌、跨境自发货卖家（含有 US 退货地址的中国卖家）、手工/定制以外的中小件品类；以及给这些卖家做客服/VA 的小团队。重货大件卖家暂缓，但值得先建监控等豁免结束。

## 一人怎么起步

两周 concierge（12-18 前完成）：拉客户近 90 天 FBM 退货报告 → 标出哪些退货已由 Amazon 预付面单覆盖、哪些仍是仅地址/手动面单/消息发面单 → 按 SKU 算「退货邮费 + 处理成本」vs「可回收残值」，定免退退款阈值与审批额度 → 写一页 SOP（谁上传、在哪上传、如何确认完成、何时升级）并培训 VA → 用表格或轻脚本做每日未处理退货队列 + 第 5 天预警 → 交「已覆盖 / 需改流程 / 直接免退 / 重货观察」分数卡。12-18 后跟踪自动扣款与退货成本，转月度监测。

## 难度

低到中（主要是报表、单位经济与 SOP；可选用 SP-API 拉退货报告做提醒，但不必写代码起步）

## 变现路径

一次性 FBM 退货合规审计（示意 $149–$399，按 SKU 数/退货量分档）；假日退货季月度队列监测与免退阈值复核（示意 $49–$149/月）；可做给 VA 团队的 SOP 模板包；与 `s24` 打包成「Amazon 假日退货体检」但不合并条目。

## 注意的坑

邮件与帮助页说法不一，以客户 Seller Central 内的通知与实测为准，不要替客户承诺 SAFE-T 能追回自动退款。「预付」不等于卖家一定承担邮费：谁付按退货原因（是否卖家责任）判定，测算时别把所有面单都算成新增成本。重货大件豁免是「暂时」的，无定义无截止日，只能监控不能依赖。任何免退退款阈值和审批额度要客户书面确认。

## 来源线索

- [PPC Land: Amazon forces prepaid return labels on US seller orders from December 18（邮件原文与帮助页对照）](https://ppc.land/amazon-forces-prepaid-return-labels-on-us-seller-orders-from-december-18/)
- [Seller Central Forums: Can Someone Explain Amazon's New Return Label Policy（官方澄清）](https://sellercentral.amazon.com/seller-forums/discussions/t/60d44d60-a781-4e6b-8a61-166ff5fa082d)
- [Seller Essentials: Amazon's December 18 Return Label Change — What FBM Sellers Need to Know](https://selleressentials.com/amazon-fbm-prepaid-return-labels/)
- [AMZ Scaler: Amazon FBM Prepaid Return Label Rule — Dec 18 Deadline](https://amzscaler.com/amazon-fbm-prepaid-return-labels/)
- [Sell on Amazon: How to manage seller-fulfilled customer returns](https://sell.amazon.com/es/blog/manage-customer-returns)
