# Google Merchant Center 促销价 30 天窗就绪体检（sale_price 持续期不宜超过 30 天 × 过长可能失去划线价与促销标 × 与 s43 图规、促销标题分开）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | |
| 更新 | 2026-11-27 |

## 一句话

帮投 Google 免费商品列表 / Shopping 广告的独立站卖家，把假日季 feed 里的促销价扫一遍：对照官方「临时降价」说明，找出 sale_price 持续期超过 **30 天**、或把促销价当成日常价一直挂着的 SKU，改成不超过 30 天的 sale_price_effective_date 窗口，并抽查搜索结果里的划线价和促销标还在不在。不要和商品图尺寸、促销标题里能不能写日期混在一起。

## 为什么现在

Google Merchant Center Help 的 *About sale price annotations* 在 Requirements 一节顶部有一条说明：**要使促销被识别为临时降价，原价最好在某些时段是唯一生效价，且 sale price [sale_price] 的持续期不应超过 30 天。** 满足条件时，免费商品列表、Shopping 广告和本地库存广告上可能同时出现划线原价和促销标。

这条用的是 **should / 不应**，不是同一页里其他规则用的 **must / 必须**。官方没有写「超过 30 天就拒审或下架」，也写明即使满足要求，标注也不保证一定出现。第三方报道（PPC News Feed / PPC Land、AdShift，约 2026-11-17 起记录）指出帮助页新出现了这条持续期说明；帮助页本身没有标注更新日期。不要把「促销价最长 30 天」理解成已经写在页上的另一条规则——部分市场要求**原价**在过去 200 天里至少有效 30 天（或美国 Shopping 广告的 5/30、15/200），那是原价历史，不是促销能挂多久。

假日季很多店会把 sale_price 从 11 月一直挂到年底，或从黑五挂到圣诞，窗口超过 30 天；今天起就是黑五周末。先出一份「哪些 SKU 的促销窗超过 30 天、建议怎么拆窗、页面上划线价是否还在」的对照表，比等徽章消失后再改 feed 更合适。

与 [s43](s43-google-merchant-image-500px-readiness.md) 不同：本条只管 **促销价持续期、划线价与促销标**，不管 2027-01-31 的 500px 图规、AI 图元数据和促销（Promotions）标题禁写日期。可打包销售，条目分开。

## 目标客户

用 Merchant Center 投免费列表或 Shopping / Performance Max 的 Shopify、WooCommerce 等独立站中小卖家，尤其把假日折扣写进商品 feed、或长期把 sale_price 当成日常售价的店；以及管多个 Merchant Center 账户的小代运营与 feed 服务商。只做 Amazon / TikTok Shop、不投 Google 购物的不是本条首批。

## 一人怎么起步

两周 concierge：先发一张公开自查表（「你的假日促销是写在商品 feed 的 sale_price 里，还是只做了 Merchant Center Promotions？sale_price_effective_date 是从哪天到哪天？有没有从 11 月一直挂到年底？搜索结果里还有没有划线价和促销标？」），发到独立站社群和跨境群换 waitlist。对报名的 5–10 家：只读导出 feed（或 Merchant API），列出带 sale_price 的 SKU，按 sale_price_effective_date 计算持续天数（没有日期的标成「未设窗口，可能一直生效」），把超过 30 天和折扣不在 5%–90% 的项标出来；抽查落地页是否同时展示原价与促销价，并在 Shopping 结果里核对划线价 / 促销标。交付「必改 / 建议拆窗 / 先观察」三档表：拆窗时把每一段有效期控制在 30 天以内，窗口之间回到原价，不要把促销价写成长期日常价。先做 3–5 家低价试单，再做成月度 feed 促销巡检。只出书面对照和改 feed 建议，不代改广告出价，也不承诺「改完一定重新出现划线价」。

## 难度

低（核心是读 feed 里的日期区间并对一下搜索结果；各地原价历史规则不同，表里要分市场标注，不要写成全球同一套）

## 变现路径

一次性促销价窗口体检（示意 $79–$199 / 店，按 SKU 数分档）；帮改 sale_price_effective_date 并复查徽章（示意 $49–$149）；月度 feed 促销巡检（示意 $29–$99 / 月）。可与 s43 打成「Google 购物 feed 年前体检」，报价分开。

## 注意的坑

不要说「超过 30 天一定被拒或被罚」——官方只谈是否被识别为临时降价，标注本身也不保证展示。不要把原价须在过去 200 天里有效 30 天的市场规则，说成「所有国家的促销都不能超过 30 天」。落地页仍要同时展示原价和促销价，折扣一般须大于 5%、小于 90%，具体以官方分市场、分广告类型的要求为准。促销活动（Promotions）不要当成 sale_price 提交。价格只是示意，需自行验证。

## 来源线索

- [Google Merchant Center Help: About sale price annotations（Requirements 顶部说明：临时降价的 sale_price 持续期不应超过 30 天；划线价与促销标；标注不保证展示）](https://support.google.com/merchants/answer/9017019?hl=en)
- [Google Merchant Center Help: Sale price [sale_price]](https://support.google.com/merchants/answer/6324471?hl=en)
- [Google Merchant Center Help: Sale price effective date [sale_price_effective_date]（ISO 8601 起止时间）](https://support.google.com/merchants/answer/6324460?hl=en)
- [PPC Land: Merchant Center sales running past 30 days may miss Google's sale badge（2026-11-22）](https://ppc.land/merchant-center-sales-running-past-30-days-may-miss-googles-sale-badge/)
- [AdShift: Merchant Center now says a sale_price shouldn't run longer than 30 days（记录于 2026-11-17；无统一截止日）](https://adshift.co/changes/google-merchant-center-sale-price-annotation-30-day-sale-limit/)
- 相关但独立：[s43 Google Merchant Center 商品图 500px 新规就绪体检](s43-google-merchant-image-500px-readiness.md)、[s20 渠道商品数据映射就绪体检](s20-channel-mapping-readiness.md)
