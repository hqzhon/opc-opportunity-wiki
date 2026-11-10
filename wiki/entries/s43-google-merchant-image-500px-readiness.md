# Google Merchant Center 商品图 500px 新规就绪体检（01-31 起 × AI 图须留元数据 × 促销标题禁写日期）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | 是 |
| 更新 | 2026-11-10 |

## 一句话

帮投 Google Shopping / 免费商品列表的独立站卖家，在 **2027-01-31** 图片下限生效前把整份商品 feed 扫一遍：找出主图与附加图低于 500×500 的 SKU、主图上贴字/水印/促销角标会被拒的、AI 生成图被剥掉 IPTC 元数据的，再顺带清掉促销（Promotions）标题里写日期的老习惯——输出「会被拒的 SKU 清单 × 该重拍/重导出/改 feed 的动作表」。

## 为什么现在

- Google Merchant Center Help 的 *Image link [image_link]* 页面写明：**自 2027-01-31 起，所有类目的商品图须至少 500×500 像素**，建议 1500×1500 以上；不达标的图不会出现在 Google 各展示面，并在 Diagnostics 报错。公开汇编（MerchantLion）补充：部分小图会被自动放大并提示警告，另一些会被拒，商品因此停展；Google 自 2026-04-14 已开始对小图发警告。
- 同一页面要求：**用生成式 AI 制作的图片须保留 AI 元数据**（如 IPTC `DigitalSourceType` = TrainedAlgorithmicMedia / CompositeSynthetic），不要在导出、压缩、CDN 处理时剥掉。很多主题/压图插件默认清 EXIF/IPTC，这是批量踩坑点。
- 主图禁促销叠字、水印、价格/包邮文案、「Best」类形容词、二维码、后期 logo、占位图与边框——旺季前大量卖家给主图加「BFCM -30%」角标，正好撞上。
- **2026-11-09**（PPC News Feed 报道、Google *Editorial requirements* 页）：Merchant Center 促销标题不再允许写兑换日期（任何格式），只允许短月份缩写；Google 可自行改写促销标题；原 60 字符上限取消。BFCM 期间大批促销正在提交，带日期的标题会被拒或被改写。

窗口：假日季促销是当下的痛点，01-31 是硬截止；一月本就是换季重拍与清 feed 的时间，正好成单。

与 `s20`（渠道商品数据映射）、`s16`（EU 商品标识符）、`s29`（Etsy 图规）、`s42`（TikTok Shop listing）不同：本条只管 **Google 商品图规格、AI 图元数据与促销标题**，可打包销售但条目分开。

## 目标客户

Shopify / WooCommerce 独立站、投 Performance Max 或靠 Google 免费列表拿流量的中小卖家（几百到几万 SKU）；供应商图直接搬运、老商品图分辨率低、用 AI 生成场景图或给主图加营销角标的店；以及管多个 Merchant Center 账户的小代运营与 feed 管理服务商（可白标）。

## 一人怎么起步

两周 concierge：拿客户的 feed 导出（CSV/XML 或 Merchant API）→ 脚本批量抓 `image_link` 与 `additional_image_link`，记录宽高、格式与扩展名是否一致、文件大小、是否带 IPTC DigitalSourceType → 标出 <500px、<1500px（建议线）、扩展名与格式不符、可疑叠字（可先人工抽检 Top SKU）→ 对照 Diagnostics 里现有图片警告 → 交付「必改 / 建议改 / 无需动」三档表与按销量排序的重拍清单；同时把在跑的 Promotions 标题过一遍，改成不带日期的写法。先做 3–5 家低价试单验证工时，再做成月度 feed 图片巡检。

## 难度

低到中（图片尺寸与元数据扫描是标准脚本活；叠字识别可先人工抽检，后续接 OCR/视觉模型半自动）

## 变现路径

一次性 feed 图片体检（示意 $99–$499 / 店，按 SKU 数分档）；代重导出/放大/去叠字按张或按包；月度 feed 健康巡检订阅（示意 $29–$149 / 月）；给 feed 工具与代运营的白标报告。可与 `s20` 打成「Google 购物 feed 年前体检」。

## 注意的坑

不要承诺「改完一定通过 / 一定提量」——审核与展示由 Google 决定。AI 放大低清图可以过尺寸线，但若放大后与实物不符或出现伪影，可能引出其他图片问题；AI 生成或增强的图要保留元数据，别为「过审」去剥标签。主图叠字的修复常要回到原始素材，先确认客户有没有无字原图。促销标题规则以 Google *Editorial requirements* 页正文为准；第三方报道只作线索。上面价格只是示意，需自行验证。

## 来源线索

- [Google Merchant Center Help: Image link [image_link]（500×500 自 2027-01-31 起、AI 图元数据、主图禁叠字）](https://support.google.com/merchants/answer/6324350?hl=en)
- [Google Merchant Center Help: Editorial requirements（促销标题禁写兑换日期）](https://support.google.com/merchants/answer/2877578?hl=en)
- [PPC News Feed: No More Dates in Titles in Merchant Center Promotions（2026-11-09）](https://ppcnewsfeed.com/ppc-news/2026-11/no-more-dates-titles-merchant-center-promotions/)
- [MerchantLion: Google Merchant Center 2026 Changes（小图自 2026-04-14 警告、部分自动放大部分被拒）](https://merchantlion.com/guides/google-merchant-center-2026-changes)
- 相关但独立：[s20 渠道商品数据映射就绪体检](s20-channel-mapping-readiness.md)、[s11 Google AI Mode / Gemini 直购结账就绪体检](s11-google-direct-checkout.md)、[s29 Etsy 商品图与 AI 新规就绪体检](s29-etsy-listing-image-ai-readiness.md)、[s42 TikTok Shop 商品 Listing 新规就绪体检](s42-tiktok-shop-listing-policy-readiness.md)
