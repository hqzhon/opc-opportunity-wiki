# Walmart 单品退货率下架就绪体检（2027-01 起 × 账户达标也会单品下架 × 60 天卖家责任退货）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | 是 |
| 更新 | 2026-11-10 |

## 一句话

帮 Walmart Marketplace 自发货卖家在 **2027 年 1 月** 单品退货率执法开始前，把 Seller Center「View returns insight」里的单品数据导出来，按「退货率 × 退货件数 × 卖家责任原因」排出高风险 SKU，逐个定位是详情页（图、尺码表、材质、UPC 挂错）、产品质量、包装还是物流时效的问题——输出「会被警告或下架的 SKU 清单 × 每个 SKU 该改什么、谁改、哪天前改」的动作表。

## 为什么现在

- Walmart Marketplace Learn 发布说明 *Prepare for item-level Return Rate enforcement*（**2026-11-06**）：Walmart 除账户整体退货率外开始提供单品级退货率；**自 2027 年 1 月起**，卖家责任退货比例高的单品可能收到警告或被**临时下架**，即使账户整体退货率仍满足 Seller Performance Standard。
- Walmart 的 Return Rate 政策页：退货率按**过去 60 天**已送达商品中「卖家责任原因」（次品、破损、发错货、迟到）的退货占比计算；整体标准为新品 ≤6%、Resold 商品 ≤9%；使用 WFS 的卖家多数指标由 Walmart 代为满足——所以受冲击的主要是自发货卖家。
- Walmart **没有公布**单品「高」的阈值，第三方（Eva）也提醒不要相信任何给出具体数字的说法。没有阈值，卖家只能自己按品类对比找出离群 SKU——这恰好是可以卖的人工 + 脚本服务。
- 时间点：60 天回看窗口意味着 **11 月中到 1 月**的假日订单与退货，正好是 1 月执法时 Walmart 看的数据。现在修，赶得上；1 月再修，被下架的单品已经停卖。

与 `s8`（服装独立站退货原因 → 详情页修复）、`s23` / `s24`（FBA 退货分级与部分退款）、`s27`（Amazon FBM 预付面单）不同：本条只管 **Walmart 单品退货率执法**这一个硬门槛，可打包「多平台退货体检」销售，但条目分开。

## 目标客户

在 Walmart Marketplace 自发货（非 WFS 或部分 WFS）的中小卖家，尤其是服装鞋类、家具、电子配件、尺码/适配容易写错的品类；同时铺 Amazon / TikTok Shop / Walmart 的多渠道卖家（含中国跨境卖家）；以及管多个 Walmart 店的小代运营（可白标）。

## 一人怎么起步

两周 concierge：请客户从 Seller Center 的 Returns → View returns insight 导出单品退货数据（或截图/共享只读权限）→ 脚本按退货率与退货件数双排序，拆出卖家责任原因 → 对 Top 10–20 SKU 逐个看详情页、图片、尺码表、UPC 关联与评价，对照 Walmart 政策页给的四类原因（次品 / 破损 / 发错 / 迟到）归因 → 交付「立即改 / 观察 / 无需动」三档表，附详情页改写稿、包装与 lag time / 承运商建议，以及可在 dashboard 里直接加的 Replacement / Keep it 等退货规则建议。先做 3–5 家低价试单验证工时，再做成 1 月前的月度巡检。

## 难度

低到中（数据导出与排序是标准表格活；归因需要懂一点品类与详情页写作，可先人工做）

## 变现路径

一次性单品退货率体检（示意 $149–$499 / 店，按 SKU 数分档）；详情页改写与尺码表修复按 SKU 计费；1–3 月月度巡检订阅（示意 $49–$199 / 月）；给代运营的白标报告。可与 `s27` / `s24` 打成「假日退货季多平台体检」。

## 注意的坑

Walmart 未公布单品阈值，不要向客户承诺「改完一定不会被下架」，只承诺「按数据找出离群 SKU 并给出修复动作」。只有卖家责任原因计入，先分清哪些退货原因算在卖家头上，别把买家改主意的退货也当成要修的问题。WFS 商品多数指标由 Walmart 承担，先确认客户哪些 SKU 是自发货。上面价格只是示意，需自行验证。

## 来源线索

- [Walmart Marketplace Learn: Prepare for item-level Return Rate enforcement（2026-11-06）](https://marketplacelearn.walmart.com/releasenotes/prepare-for-item-level-return-rate-enforcement)
- [Walmart Marketplace Learn: Return Rate 政策页（60 天、新品 ≤6%、Resold ≤9%、四类卖家责任原因）](https://marketplacelearn.walmart.com/guides/Policies%20&%20standards/Performance/performance-dashboard-return-rate)
- [Walmart Marketplace Learn: Returns insights overview（单品退货数据与退货规则建议）](https://marketplacelearn.walmart.com/guides/Order%20management/Returns%20&%20refunds/returns-insights-overview)
- [Eva: Walmart Item-Level Return Rate: Prepare for Jan 2027（阈值未公布的提醒与自查步骤）](https://eva.guru/blog/walmart-item-level-return-rate-2027/)
- 相关但独立：[s8 退货原因 → 详情页修复闭环](s8-returns-listing.md)、[s27 Amazon FBM 预付退货面单就绪体检](s27-amazon-fbm-prepaid-return-label-readiness.md)、[s24 FBA 部分退款按原因就绪体检](s24-fba-partial-refund-readiness.md)、[s22 Amazon Seller Central 多渠道就绪体检](s22-amazon-multichannel-readiness.md)
