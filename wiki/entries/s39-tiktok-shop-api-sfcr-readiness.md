# TikTok Shop API 取消单计入 SFCR 就绪体检（11-02 起 × IM 取消卡 24h × ≤2.5%）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | 是 |
| 更新 | 2026-11-06 |

## 一句话

帮已对接 TikTok Shop Open API / ERP / WMS / 客服系统的美区店，在 **2026-11-02** 起「凡经 API 发起的取消一律算卖家过错并计入 SFCR」之后，把取消路径拆成「必须走 Seller IM 取消卡 + 买家 24 小时确认」与「仅保留真正卖家过错的 API 取消」，输出「哪些触发器会抬高 SFCR × 客服 SOP 差哪步 × 库存同步会不会批量误取消」分数卡——和 `s28`（AHR 扣分与 BFCM 里程碑）是另一套指标。

## 为什么现在

TikTok Shop Seller University *Policy Pulse (October 2026)*（页面更新 **2026-11-05**）写明：**2026-11-02** 起，所有经 API 发起的订单取消一律归为卖家过错，并计入 **Seller-Fault Cancellation Rate（SFCR）**；现有 API 对接与取消接口本身不变。卖家应：

- 复查更新后的取消原因，把 **买家主动要求取消** 全部改走 **Seller IM Cancellation Card**；只有买家在 **24 小时内确认** 后，该取消才算买家过错
- 把 API 取消留给真正的卖家过错场景，避免 ERP / WMS / 客服工具 / 库存同步在缺货、改价、批量清单时用 API 一把取消，直接抬高 SFCR

官方 *Seller-Fault Cancellation Rate Requirements* 仍要求 SFCR **≤ 2.5%**（硬门槛）。超标可扣 AHR、降曝光、拉长结算、限单量，严重时可下架或限制售卖；极端「卖家过错取消率 ≥90% 且长期不履约」可停店。SFCR 与 OTDR 一起进入履约侧，直接影响 **Shop Performance Score（SPS）**——而 BFCM 报名与流量又看 SPS / AHR。FBT 订单对卖家过错取消有保护；Creator 样品单不计入。

这和 `s28`（11-04 起更多违规扣 AHR、保护期只停处罚、12-08 回归禁上新）**同属旺季账户健康**，但管的是**取消归因与履约指标**，不是违规扣分表：可以一次卖「AHR + SFCR 双检」，条目必须分开。下午扫描曾把「TTS API SFCR」误标成已有 `s28` 覆盖——`s28` 正文未写 SFCR / API 取消 / IM 取消卡，本轮单独成条。

## 目标客户

TikTok Shop US 上已接 Open API、第三方 ERP/WMS、自动客服或库存同步、近几周有缺货取消或批量取消习惯的中小卖家与小代运营；以及做 TTS 订单中台 / 客服机器人、要在 BFCM 前改取消逻辑的一人开发者。纯手点 Seller Center、几乎不用 API 取消的店不是首要客户。

## 一人怎么起步

两周 concierge：先发一张公开自查表（「你们用哪家 ERP/WMS/客服？有没有 API 批量取消或缺货自动取消？买家要取消时客服是点后台取消还是发 IM 取消卡？当前 7 日 / 30 日 SFCR 是多少？有没有逼近 2.5%？」），发到 TTS 卖家群、跨境 ERP 用户群、r/Flipping 与 X 换 waitlist。对 5–10 个报名店：只读列出所有会调取消接口的触发器（缺货、超卖、改价、客服快捷键、夜间脚本）；标出必须改成 IM 取消卡的买家请求路径，并写「发卡片 → 24h 内跟确认 → 超时升级」SOP；对库存同步误取消给出「先锁单 / 回拨 / 再人工」的最小改法；对照 Seller Center 的 Account Health → SPS 与 Orders → Fulfillment Performance 读 30 日 / 7 日 SFCR，交付分数卡 + 本周必改清单。先收一次性就绪体检费；对代运营可加多店 SFCR 周报订阅；对 ISV 可卖「取消原因映射 + IM 卡流程」改包，但定位仍是体检与行动清单，不替客户改生产库除非另签开发合同。

## 难度

中（要读懂 SFCR 计算与例外、分清 API 取消 vs IM 取消卡、能读 ERP 触发器；不强制会写代码，但对接方是 API 店时要能看日志或让对方导出取消来源）

## 变现路径

一次性 TTS API×SFCR 就绪体检（示意 $99–$299 / 店）；「取消触发器清单 + IM 取消卡 SOP + 本周 SFCR 对照」固定价项目（示意 $300–$800）；之后做 SFCR / 取消来源周报（示意 $49–$149 / 月）。可与 `s28`（AHR BFCM）、`s38`（电子品类责任险）组成「旺季账户健康」系列，条目分开。ISV / 中台改包另报价，本条不承诺「保证 SFCR 降到某值」。

## 注意的坑

政策写的是「API 发起的取消**一般**算卖家过错」——不要向客户保证「改完就一定不算」；以 Seller Center 实际归因与申诉结果为准。买家请求取消**必须**走 IM 取消卡且买家 24 小时内确认，才可能算买家过错；客服图省事直接调 API 取消，会继续计 SFCR。缺货 / 定价错误 / 超时未上传有效运单等本身就是卖家过错场景，改通道也消不掉，只能靠库存与履约。FBT 对卖家过错取消有保护，但不要把「全部转 FBT」当成万能答案。SFCR 超 2.5% 的执法与申诉窗口（首次 30 天、驳回后再 15 天、每案最多 2 次）以 *SFCR Requirements* 与 Seller Enforcement Policy 为准。本条不管 AHR 里程碑与 12-08 禁上新，那是 `s28`。以 Policy Pulse（Updated Nov 5, 2026）与 *Seller-Fault Cancellation Rate Requirements* 为准。

## 来源线索

- [TikTok Shop Seller University: Policy Pulse (October 2026) — Update to API-Initiated Order Cancellations（页面更新 2026-11-05）](https://seller-us.tiktok.com/university/essay?knowledge_id=6747273381791534&lang=en)
- [TikTok Shop Seller University: Seller-Fault Cancellation Rate Requirements](https://seller-us.tiktok.com/university/essay?knowledge_id=7953001314830094&lang=en)
- [Niceggie: TikTok Shop US to Count API-Initiated Cancellations Toward Seller-Fault Rate（2026-11-05）](https://www.niceggie.com/en/news/tiktok-shop-us-to-count-api-initiated-cancellations-toward-seller-fault-rate-2026-6aec7cdf1bc406cba4c7cf60)
- 相关但独立：[s28 TikTok Shop 账户健康分 BFCM 就绪体检](s28-tiktok-shop-ahr-bfcm-readiness.md)、[s38 TikTok Shop 美区电子品类责任险就绪体检](s38-tiktok-shop-liability-insurance-readiness.md)
