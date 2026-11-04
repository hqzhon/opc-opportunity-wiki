# 一人公司机会 Wiki

**一人公司机会清单：跨境电商 / 独立站与 SaaS，每日更新。**

面向正在做（或准备做）**一人公司（OPC）** 的运营者与独立开发者：把近期可公开验证的趋势与平台变更，整理成可执行的 wiki 条目——说清给谁、为什么现在、两周怎么起步、怎么变现，以及要注意的坑。适合跨境电商 / 独立站卖家，以及做 SaaS / 订阅产品（含 App Store 订阅 App）的技术与运营一人团队。

公开仓库：[github.com/hqzhon/opc-opportunity-wiki](https://github.com/hqzhon/opc-opportunity-wiki)

## 为什么看这里

- **每日更新**：跟平台 Changelog、政策窗口与一线信号同步追加，不是一年一更的「风口清单」
- **可两周验证**：每条都写「一人怎么起步」，先做最小探针，再决定是否加码
- **来源可点**：条目附公开线索链接（Changelog、Help、官方新闻等），便于自行核对
- **按画像筛选**：跨境/独立站 × SaaS/订阅分开；优先项标 ★，方便从时效窗口下手
- **一人可冷启动**：偏轻资产、可 concierge / 订阅起步，跳过空泛「暴利」话术

## 先看这些（优先 ★）

近期截止日与假日旺季相关（TikTok Shop 卖家先看第一条，Etsy 卖家看第二条，Amazon 卖家看第三、四条，用 Stripe 收订阅的 SaaS 看第五条，在 App Store 卖订阅的独立开发者看第六条，在 Google Play 卖订阅或内购的看第七条，维护 Shopify 公开 App 的开发者看第八条），建议优先打开：

- [★ TikTok Shop 账户健康分 BFCM 就绪体检（11-04 新扣分 × 保护期只停处罚 × 12-08 回归）](wiki/entries/s28-tiktok-shop-ahr-bfcm-readiness.md) — **2026-11-04** 起更多违规扣分，BFCM 保护期只停处罚不停扣分，12-08 低分店的下一张违规单就触发禁上新
- [★ Etsy 商品图与 AI 新规就绪体检（一张未修图 × AI 教程禁售 × 不符被判退款）](wiki/entries/s29-etsy-listing-image-ai-readiness.md) — 10-22 起多数 listing 须有一张**未修图**，AI 生成的图纸/食谱禁售；图不合规又遇「与描述不符」纠纷可能被判退款，旺季前先过全店
- [★ Amazon FBM 预付退货面单就绪体检（12-18 起 × 7 天时钟 × 自动免退退款）](wiki/entries/s27-amazon-fbm-prepaid-return-label-readiness.md) — **2026-12-18** 起 US 自发货退货须预付面单，7 天内不上传/不退款就被自动免退扣款
- [★ Amazon 虚拟多件装就绪体检（Virtual Multipacks × 单件费率 × 不可恢复删除）](wiki/entries/s26-amazon-virtual-multipack-readiness.md) — **2026-11-10** 前审核 Amazon 代建的 `VMP_` 多件装，11-11 自动开售；删了不能恢复
- [★ Stripe Radar 续费筛查计费就绪体检（10-21 续费计费 × 01-22 试用结束 × Lite 还是 Standard）](wiki/entries/s30-stripe-radar-renewal-cost-readiness.md) — 10-21 起付费 Radar 连续费和被拒尝试都按次计费；受影响的美国账户 **2027-01-22** 免费试用结束后自动按 $0.05/次扣，先算账再决定限轮还是切 Lite
- [★ Apple 订阅多席位就绪体检（10-22 默认开启 × 关错开关会停续费 × 冬季群组购买）](wiki/entries/s31-apple-multiseat-subscription-readiness.md) — 10-22 起你的 App 订阅可能已被**默认**挂上 Apple Business / School Manager 卖给机构；关错开关会让机构客户下次续费后取消，冬季群组购买前先审一遍
- [★ Google Play 拒付成本就绪体检（8-03 后订单由开发者承担 × 24 小时 ReviewRefund × 只认第一次回应）](wiki/entries/s32-google-play-chargeback-review-readiness.md) — **2026-08-03** 之后的 Play 订单被拒付，货款和发卡行手续费改由开发者承担；用 ReviewRefund API 在 24 小时内交证据帮 Google 抗辩，且只认第一次回应，假日拒付到来前先接好
- [★ Shopify 公开 App 过期离线令牌迁移体检（01-01 下架 × 01-15 商家警告 × 04-01 返回 403）](wiki/entries/s33-shopify-expiring-offline-token-readiness.md) — **2027-01-01** 前公开 App 不改用会过期的离线令牌就被下架、禁止新安装；**04-01** 起旧令牌请求直接 403，假日季不敢动线上，越早迁越稳
- [★ EU 低货值包裹三件套商品标识符就绪体检](wiki/entries/s16-eu-product-identifiers.md) — **11-01 已生效**：€150 以下发欧盟须齐三件套，缺项可能买不了面单，现在查漏
- [★ EU €2 处理费 + €3 关税结账回收就绪体检](wiki/entries/s17-eu-uhf-duty-recovery.md) — 11-01 已生效的 UHF + 关税，结账侧是否已回收、文案是否覆盖「UHF 不退」
- [★ Managed Markets 保价一口价运费就绪体检](wiki/entries/s18-mm-flat-rate-shipping.md) — 假日前锁国际运费成本：一口价该不该开、担保面单有没有买对
- [★ UK VAT 履约仓路由就绪体检（>£135 GB）](wiki/entries/s19-uk-vat-fulfillment-routing.md) — 高客单发英是否因路由到非英国仓而在结账跳过 VAT
- [★ Shop Promise 就绪体检（US 履约徽章 × Catalog 排序信号）](wiki/entries/s21-shop-promise-readiness.md) — Fall '26 扩大资格，美仓店的可信送达/退货徽章与 Catalog 信号
- [★ Amazon Seller Central 多渠道就绪体检（eBay / Shopify / TikTok / Walmart）](wiki/entries/s22-amazon-multichannel-readiness.md) — Amazon 作多渠枢纽刚 rollout，先判「可连 / 慎同步 / 暂缓」
- [★ FBA 退货定制分级就绪体检（Customized grading × Grade and Resell）](wiki/entries/s23-fba-customized-grading-readiness.md) — 假日退货浪前配好「全新再售」标准，高退货 ASIN 先覆盖
- [★ FBA 部分退款按原因就绪体检（Partial Refunds × return reason）](wiki/entries/s24-fba-partial-refund-readiness.md) — 退货原因级「留货+部分退款」开关与百分比，假日浪前先收窄
- [★ Stripe 订阅暂停留存就绪体检（Portal pause × flexible billing × auto-pause）](wiki/entries/s25-stripe-pause-retention-readiness.md) — Endive 原生 pause + 门户自助暂停；classic→flexible 单向门槛先审再开

完整优先表见 [Catalog](wiki/Catalog.md)。

## 文档目录（每篇入口）

以下按市场列出**全部**机会条目（与 `wiki/entries/` 一致，一篇不漏）。标 ★ 为 Catalog 中的优先验证方向。

### 跨境电商 / 独立站

- [★ AI + POD 轻资产定制（TikTok / 独立站）](wiki/entries/e1-ai-pod.md)
- [区域细分 + TikTok Shop 短视频自然流](wiki/entries/e2-tiktok-regional.md)
- [★ 高客单差异化独立站（先平台验证）](wiki/entries/e3-high-aov-dtc.md)
- [内容 SEO + Reddit / YouTube 有机引流独立站](wiki/entries/e4-organic-seo.md)
- [消耗品 / 宠物 / 美妆补货型订阅盒](wiki/entries/e5-subscription-box.md)
- [平台测款 → 品牌站沉淀的双通道模型](wiki/entries/e6-dual-channel.md)
- [★ 数字商品独立站（模板 / 微课 / AI Prompt Pack）](wiki/entries/e7-digital-dtc.md)

### SaaS / 订阅

- [★ 垂直 AEO / AI 可见度追踪](wiki/entries/s1-vertical-aeo.md)
- [★ 订阅失败支付挽回（垂直化 dunning）](wiki/entries/s2-dunning.md)
- [平台伴生小工具（Shopify / Notion 等）](wiki/entries/s3-platform-addon.md)
- [自由职业者轻量客户中枢](wiki/entries/s4-freelancer-hub.md)
- [长视频 → 短视频的垂直切片工具](wiki/entries/s5-video-clips.md)
- [购买意向线索预警（单一行业）](wiki/entries/s6-intent-leads.md)
- [★ Shopify Agentic Catalog 就绪体检](wiki/entries/s7-agentic-catalog.md)
- [★ 退货原因 → 详情页修复闭环（服装独立站）](wiki/entries/s8-returns-listing.md)
- [★ AI 购物代理政策 / 履约就绪体检（shipping · cancel · pickup）](wiki/entries/s9-agent-policy.md)
- [★ COM 客户自带物料入站追踪（定制家具 / 软装独立站）](wiki/entries/s10-com-inbound.md)
- [★ Google AI Mode / Gemini 直购结账就绪体检](wiki/entries/s11-google-direct-checkout.md)
- [★ UCP 零售门店发现就绪体检（Physical storefront × 库存 × 自提）](wiki/entries/s12-ucp-location.md)
- [★ Agentic Knowledge base 发布就绪体检（draft → publish × 冲突 × 迁移）](wiki/entries/s13-knowledge-base-publish.md)
- [★ 退货窗覆盖规则就绪体检（Override × 最短优先 × 政策页）](wiki/entries/s14-return-window-overrides.md)
- [★ Compare-at / list_price 代理可见就绪体检](wiki/entries/s15-compare-at-list-price.md)
- [★ EU 低货值包裹三件套商品标识符就绪体检](wiki/entries/s16-eu-product-identifiers.md)
- [★ EU €2 处理费 + €3 关税结账回收就绪体检](wiki/entries/s17-eu-uhf-duty-recovery.md)
- [★ Managed Markets 保价一口价运费就绪体检](wiki/entries/s18-mm-flat-rate-shipping.md)
- [★ UK VAT 履约仓路由就绪体检（>£135 GB）](wiki/entries/s19-uk-vat-fulfillment-routing.md)
- [★ 渠道商品数据映射就绪体检（Google / Meta / TikTok / Catalog）](wiki/entries/s20-channel-mapping-readiness.md)
- [★ Shop Promise 就绪体检（US 履约徽章 × Catalog 排序信号）](wiki/entries/s21-shop-promise-readiness.md)
- [★ Amazon Seller Central 多渠道就绪体检（eBay / Shopify / TikTok / Walmart）](wiki/entries/s22-amazon-multichannel-readiness.md)
- [★ FBA 退货定制分级就绪体检（Customized grading × Grade and Resell）](wiki/entries/s23-fba-customized-grading-readiness.md)
- [★ FBA 部分退款按原因就绪体检（Partial Refunds × return reason）](wiki/entries/s24-fba-partial-refund-readiness.md)
- [★ Stripe 订阅暂停留存就绪体检（Portal pause × flexible billing × auto-pause）](wiki/entries/s25-stripe-pause-retention-readiness.md)
- [★ Amazon 虚拟多件装就绪体检（Virtual Multipacks × 单件费率 × 不可恢复删除）](wiki/entries/s26-amazon-virtual-multipack-readiness.md)
- [★ Amazon FBM 预付退货面单就绪体检（12-18 起 × 7 天时钟 × 自动免退退款）](wiki/entries/s27-amazon-fbm-prepaid-return-label-readiness.md)
- [★ TikTok Shop 账户健康分 BFCM 就绪体检（11-04 新扣分 × 保护期只停处罚 × 12-08 回归）](wiki/entries/s28-tiktok-shop-ahr-bfcm-readiness.md)
- [★ Etsy 商品图与 AI 新规就绪体检（一张未修图 × AI 教程禁售 × 不符被判退款）](wiki/entries/s29-etsy-listing-image-ai-readiness.md)
- [★ Stripe Radar 续费筛查计费就绪体检（10-21 续费计费 × 01-22 试用结束 × Lite 还是 Standard）](wiki/entries/s30-stripe-radar-renewal-cost-readiness.md)
- [★ Apple 订阅多席位就绪体检（10-22 默认开启 × 关错开关会停续费 × 冬季群组购买）](wiki/entries/s31-apple-multiseat-subscription-readiness.md)
- [★ Google Play 拒付成本就绪体检（8-03 后订单由开发者承担 × 24 小时 ReviewRefund × 只认第一次回应）](wiki/entries/s32-google-play-chargeback-review-readiness.md)
- [★ Shopify 公开 App 过期离线令牌迁移体检（01-01 下架 × 01-15 商家警告 × 04-01 返回 403）](wiki/entries/s33-shopify-expiring-offline-token-readiness.md)

### 其他导航

- [Wiki home](wiki/Home.md) — 用法与画像建议
- [完整索引表 Catalog](wiki/Catalog.md)
- [更新日志 digests](wiki/digests/)

## 如何使用

1. 从上方「先看这些」或 [Catalog](wiki/Catalog.md) 的优先列挑一条与你画像匹配的机会
2. 打开对应 `wiki/entries/` 条目，按「一句话 → 为什么现在 → 一人怎么起步」做 **2–4 周**最小验证
3. 没有付费信号或验证不成立就换切口，不要加预算硬扛
4. 需要总览与画像对照时看 [wiki/Home.md](wiki/Home.md)

### 收录标准

一条机会通常至少满足两条：

1. 一人可冷启动（不大团队、不大预算）
2. 有清晰目标客户与变现路径
3. 有公开线索（报道、Changelog、一线反馈等）
4. 可在 2–4 周内做最小验证

跳过：空泛风口、纯广告、无法验证的「暴利」承诺。

### 目录结构

```
wiki/
  Home.md          # 总览与用法
  Catalog.md       # 全部机会索引表
  entries/         # 每条机会一个 markdown
  digests/         # 更新日志
meta/
  last-scan.json   # 维护游标 / 去重状态
```

## 贡献与免责

欢迎通过 Issue / PR 补充公开线索或修正过时信息；合并前会按收录标准与可验证性审阅。

**本仓库内容仅供信息整理与学习交流，不构成投资、经营或法律建议。** 每条机会需自行验证可行性、合规与成本；外链原文版权仍归原作者。

本仓库内容为 [CC BY 4.0](LICENSE)。

---

工作日持续整理公开信号（Asia/Shanghai 时区），过质量关后写入 `wiki/entries/`，并同步更新本 README 文档目录；对外按**每日更新**维护。
