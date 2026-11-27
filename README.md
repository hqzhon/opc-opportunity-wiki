<div align="center">

<img src="assets/social-preview.png" alt="一人公司机会 Wiki" width="720">

# 一人公司机会 Wiki

**平台每改一次规则，就有一批卖家需要有人帮他们查一遍——这就是一个人能接的单。**

跨境电商 / 独立站 × SaaS / 订阅的一人公司机会库：89 篇，**每日更新**，每篇都写清给谁、为什么现在、两周怎么起步、怎么收钱。

[![每日更新](https://img.shields.io/badge/更新-每日-brightgreen)](wiki/digests/)
[![条目](https://img.shields.io/badge/条目-89_篇-blue)](#全部条目)
[![Last commit](https://img.shields.io/github/last-commit/hqzhon/opc-opportunity-wiki)](https://github.com/hqzhon/opc-opportunity-wiki/commits/main)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](LICENSE)

[先看这些](#先看这些) · [临期窗口](#临期窗口) · [全部条目](#全部条目) · [English](#english) · [参与贡献](CONTRIBUTING.md)

</div>

> 觉得有用就点右上角 ⭐ Star，新条目会出现在你的 GitHub 首页；想每天收到更新，点 **Watch → Custom → Releases** 或订阅 [commits RSS](https://github.com/hqzhon/opc-opportunity-wiki/commits/main.atom)。

## 适合谁

- **跨境 / 独立站卖家**：Amazon、TikTok Shop、Shopify、eBay、Etsy、Walmart 新规一出，先知道影响谁、要改什么
- **独立开发者 / 做 SaaS 的一人团队**：从平台变更里找「刚出现、还没人做」的工具和服务切口
- **接单的自由职业者 / 小代运营**：把每条「就绪体检」直接变成一份能报价的服务

## 每篇长什么样

以 [订阅失败支付挽回](wiki/entries/s2-dunning.md) 为例：

| 一句话 | 为什么现在 | 两周怎么起步 | 怎么收钱 |
| --- | --- | --- | --- |
| 给 Shopify App / 会员站 / 课程站做智能重试和催收序列，减少拒卡流失 | Stripe 称智能重试比固定日程多挽回约 14% 收入，但横向工具不懂垂直话术 | 接 `invoice.payment_failed` webhook → 按失败码分流 → 催收序列 + 自助换卡页 → 找 5–10 家试点 | 月费或挽回金额分成 |

每篇还有「目标客户」「难度」「注意的坑」和可点击的公开来源（官方 Changelog、帮助中心、政策页）。

## 先看这些

### 常青精选（新手从这里开始）

- [★ 订阅失败支付挽回（垂直化 dunning）](wiki/entries/s2-dunning.md) — Stripe / Shopify 订阅的拒卡挽回，按挽回金额收费，ROI 一眼可算
- [★ 垂直 AEO / AI 可见度追踪](wiki/entries/s1-vertical-aeo.md) — 帮垂直行业品牌看「AI 搜索里有没有提到我」，月度报告即可起步
- [★ 数字商品独立站（模板 / 微课 / AI Prompt Pack）](wiki/entries/e7-digital-dtc.md) — 模板、微课、Prompt Pack，零库存、可自动交付
- [★ AI + POD 轻资产定制（TikTok / 独立站）](wiki/entries/e1-ai-pod.md) — AI 出图 + 按需印刷，不压货测款
- [★ 退货原因 → 详情页修复闭环（服装独立站）](wiki/entries/s8-returns-listing.md) — 把退货原因变成详情页修改清单，服装独立站最痛
- [平台伴生小工具（Shopify / Notion 等）](wiki/entries/s3-platform-addon.md) — 给 Shopify / Notion 做伴生小工具，借平台流量冷启动

### 临期窗口

按截止日排序：越靠前越急，也越容易接到「帮我查一遍」的单。日期为平台公布的时间（2026 年，除非注明 2027）。

<!-- 新的临期条目按日期插入下表；截止已过的移出 -->
| 截止 | 发生什么 | 条目 |
| --- | --- | --- |
| **10-01 起 / 2027-01-31** | Walmart Marketplace：10-01 至 12-31 合格订单可退到 1-31；无线电话、保护计划、大家电、Dyson、食品饮料等除外；卖家须遵守平台退货政策 | [s73](wiki/entries/s73-walmart-holiday-returns-readiness.md) |
| **11-01 起 / 2027-01-31** | Amazon.com：11-01 至 12-31 合格订单可退到 1-31（苹果品牌到 1-15），FBA/FBM 自动生效；原有不可退条件不变 | [s71](wiki/entries/s71-amazon-us-holiday-returns-readiness.md) |
| **11-01 起 / 2027-01-31** | Amazon 欧洲十站：多数站点 11-01 至 12-25 合格订单可退到 1-31 或收货后 30 天；西班牙买到 1-06、退到 2-06；德/法/意部分类目到 1-15；FBA/FBM 自动生效。不要套用美国站 12-31 | [s72](wiki/entries/s72-amazon-eu-uk-holiday-returns-readiness.md) |
| **11-01 起 / 2027-01-31** | Amazon 加/墨/巴/日/澳/新：多数站点 11-01 至 12-31 合格订单可退到 1-31；加拿大苹果到 1-15，墨西哥手机与苹果到 1-14；日本站苹果不在客户都合窗；澳站 FBM 可自选对齐。不要套用美国站或欧洲站日期 | [s74](wiki/entries/s74-amazon-ca-mx-br-jp-au-sg-holiday-returns-readiness.md) |
| **11-06 起 / 2027-01-31** | TikTok Shop 英国站：11-06 至 12-31 合格订单可退到 1-31，除外类目以商品页为准；不要套用美区 2-10 | [s69](wiki/entries/s69-tiktok-shop-uk-holiday-returns-readiness.md) |
| **11-11 起 / 2027-02-10** | TikTok Shop BFCM 订单退货窗延到 2-10，API 退货二维码有效期须跟着改 | [s48](wiki/entries/s48-tiktok-shop-bfcm-holiday-returns-readiness.md) |
| **11-11 起 / 11-19 起 / 2027-01-31** | TikTok Shop 欧盟八站：德/西/法/爱/意 11-11 至 12-31、比/荷/波 11-19 至 12-31 的合格订单可退到 1-31；二手、珠宝、电子和拍卖仍为 14 天；不要套用英区 11-06 或美区 2-10 | [s79](wiki/entries/s79-tiktok-shop-eu-holiday-returns-readiness.md) |
| **11-16 起** | Amazon 充电锂电智能硬件须经授权 TIC 送检，通知已发完，不合规 Listing 可能被下架 | [s51](wiki/entries/s51-amazon-lithium-battery-tic-readiness.md) |
| **11-20 / 2027-01-01** | Shopify 自定义 App 装到客户店须配 IP 白名单，漏一个影响全部外部安装 | [s47](wiki/entries/s47-shopify-custom-app-ip-allowlist-readiness.md) |
| **12-01** | Google Play 卖进或卖出日本须完成收款授权，否则全球打款可能被冻结 | [s60](wiki/entries/s60-google-play-japan-payout-authorization-readiness.md) |
| **12-01** | Shopify 退货 / 订阅 App 的买家自助登录须改用 Customer Account API，否则可能失去 Built for Shopify | [s65](wiki/entries/s65-shopify-bfs-customer-account-api-readiness.md) |
| **12-01 / 2027-01-01** | Shopify 在店面运行的 App 须声明 allowed_sources：12-01 起拒发版与提交，01-01 起公开 App 下架、自定义 App 外部安装连坐 | [s66](wiki/entries/s66-shopify-network-access-declaration-readiness.md) |
| **12-01 / 2027-01-01** | Shopify 弃单恢复 URL 须获准全部四个受保护顾客字段：公开 App 12-01 前要过审核（可能要几周），自定义 App 到 2027-01-01；未获准则 GraphQL 整查询失败，REST 静默丢链接 | [s70](wiki/entries/s70-shopify-abandoned-checkout-url-pcd-readiness.md) |
| **12-02 / 2027-03-31** | Lemon Squeezy 关停：12-02 迁移工具上线，3-31 停止处理交易（含续费），官方不延期 | [s64](wiki/entries/s64-lemon-squeezy-migration-readiness.md) |
| **12-08** | TikTok Shop BFCM 保护期结束，低分店触发禁上新 | [s28](wiki/entries/s28-tiktok-shop-ahr-bfcm-readiness.md) |
| **12-10** | Amazon 英德法意西站：APRL 退货在途遗失或交付拒收将自动退买家；亚马逊承运可走 SAFE-T，其他快递不能向平台索赔；官方建议先签收。不要和美国站 12-18 的 s27 混用 | [s77](wiki/entries/s77-amazon-eu-uk-aprl-auto-refund-readiness.md) |
| **12-18** | Amazon FBM 退货须预付面单，7 天不处理自动退款 | [s27](wiki/entries/s27-amazon-fbm-prepaid-return-label-readiness.md) |
| **12-21 / 2027-01-04** | UPS Daily / Retail / Ground Saver 平均净涨 5.9%，附加处理最低计费重改为 50 磅，区域附加与分区 ZIP 调整；FedEx 美国及进出口标准清单价平均涨 5.9%。不要和 USPS 1-17 的 s68 混用 | [s75](wiki/entries/s75-ups-fedex-2027-rate-readiness.md) |
| **12-21 / 2027-01-28** | TikTok Shop 英国站珠宝配饰须补齐标签与 REACH 文件，逾期存量可能被下架 | [s55](wiki/entries/s55-tiktok-shop-jewelry-compliance-readiness.md) |
| **2027-01-01** | Shopify 公开 App 须改用会过期的离线令牌 | [s33](wiki/entries/s33-shopify-expiring-offline-token-readiness.md) |
| **2027-01-01** | Shopify Tax 免费计算额度改按终身销售额，不再每年重置，过 10 万后对已开通征收的订单收费 | [s52](wiki/entries/s52-shopify-tax-lifetime-discount-readiness.md) |
| **2027-01-01** | DHL Express 美国账户 Time Definite 平均涨 5.9%；燃油附加改按每周 EIA USGC 即期计价；高风险附加改按票最低额或按公斤取高。不要和 UPS 12-21、FedEx 1-04 的 s75 或 USPS 1-17 的 s68 混用 | [s76](wiki/entries/s76-dhl-express-2027-us-rate-readiness.md) |
| **2027-01** | Walmart 单品卖家责任退货率高会被单独下架 | [s44](wiki/entries/s44-walmart-item-return-rate-readiness.md) |
| **2027-01-11** | Amazon 单 ASIN 捆绑须原厂包装 | [s34](wiki/entries/s34-amazon-bundle-manufacturer-packaging-readiness.md) |
| **2027-01-12** | Apple 年龄分级问卷须完成 Shared Location 与 Dating and Relationships 声明，约会类最低 18+ | [s62](wiki/entries/s62-apple-age-rating-descriptors-readiness.md) |
| **2027-01-15 / 02-01** | Amazon FBA 配送费上调、仓储费改按库龄计 | [s45](wiki/entries/s45-amazon-fba-2027-fee-readiness.md) |
| **2027-01-17** | 美国邮政商业件平均涨 5.9%，并加收 11% 燃油附加；USPS Ship / APV 短付按欠付额加收 20% 再计价费 | [s68](wiki/entries/s68-usps-2027-price-repricing-readiness.md) |
| **2027-01-18 / 01-31** | Amazon Ads 旧 Sponsored Ads / DVA+ 报表页：1-18 起不能新建或编辑、改为只读并继续投递，1-31 关闭并永久删除未迁移的保存报表、定期报表和历史数据。不要用仍写着 12-31 的 What's New | [s78](wiki/entries/s78-amazon-ads-unified-reporting-migration-readiness.md) |
| **2027-01-20** | 美国邮政小包 Entry Type 13 电子申报 | [s35](wiki/entries/s35-us-postal-entry-type13-readiness.md) |
| **2027-01-22** | Stripe Radar 续费筛查免费试用结束、按次计费 | [s30](wiki/entries/s30-stripe-radar-renewal-cost-readiness.md) |
| **2027-01-27** | Google Play 学生价等持续资格折扣须披露资格、核验与资格结束后的价格和权益 | [s57](wiki/entries/s57-google-play-eligibility-discount-disclosure-readiness.md) |
| **2027-01-31** | Google 商品图须 ≥500×500，AI 图须保留元数据 | [s43](wiki/entries/s43-google-merchant-image-500px-readiness.md) |
| **2027-01-31** | Apple 中国区上架的现有应用须完成并核验 AIGC 与安全评估合规声明，否则可能在中国区不可售；无相关功能也须选 No | [s63](wiki/entries/s63-apple-china-aigc-security-assessment-readiness.md) |
| **2027-02-01** | Etsy 卖进 EU/NI 的 Listing 须填制造商与欧盟负责人，否则被拒 | [s46](wiki/entries/s46-etsy-gpsr-economic-operator-readiness.md) |
| **2027-02-01** | Google Play 美区外链项目须上报成功下载并缴纳固定安装费 | [s53](wiki/entries/s53-google-play-external-link-fee-readiness.md) |
| **2027-02-01** | Google Play 须在 Console 声明交易者身份，逾期可能被拦截更新或全球下架 | [s61](wiki/entries/s61-google-play-trader-status-declaration-readiness.md) |
| **2027-02-01 / 03-01** | Amazon AWD / MCD：02-01 起处理费每箱 $1.55、运输每立方英尺 $1.58，燃油与物流附加 3.5% 扩到 AWD 运输费和 MCD 费用，单 SKU 托盘入库处理可享最高 40% 折扣；03-01 起仓储按库龄，超 12 个月按标准费率 2.5 倍。MCF 标准配送和 Buy with Prime 01-15 起平均涨 3.5%。不要和 s45 的 FBA 配送费及「FBA 燃油附加维持不变」混用 | [s81](wiki/entries/s81-amazon-awd-mcd-2027-fee-readiness.md) |
| **2027-03-01** | Shopify 停止向店面注入 script tag，须改为 app embed 或 web pixel | [s67](wiki/entries/s67-shopify-script-tag-deprecation-readiness.md) |
| **2027-06-01** | FCC 新规：美国站无线电子产品须在卖点展示 FCC ID，eBay 已开始拦缺 ID 的 Listing | [s50](wiki/entries/s50-fcc-id-marketplace-listing-readiness.md) |
| **2027-07-01** | Shopify 运费从档案迁到按市场配置，多条费率改收最高一条，旧 API 写入静默失效 | [s49](wiki/entries/s49-shopify-market-driven-shipping-readiness.md) |

已生效、仍值得逐店检查：TikTok Shop 电子品类责任险 [s38](wiki/entries/s38-tiktok-shop-liability-insurance-readiness.md)、API 取消计入 SFCR [s39](wiki/entries/s39-tiktok-shop-api-sfcr-readiness.md)、运费与重量结算 [s41](wiki/entries/s41-tiktok-shop-shipping-fee-weight-readiness.md)、Listing 新规 [s42](wiki/entries/s42-tiktok-shop-listing-policy-readiness.md)；Amazon 安全类目责任险 [s36](wiki/entries/s36-amazon-liability-insurance-readiness.md)、广告宣称举证 [s56](wiki/entries/s56-amazon-ads-claims-substantiation-readiness.md)、加拿大跨境退货与免退 [s59](wiki/entries/s59-amazon-canada-returnless-cross-border-readiness.md)、巴西站 FBA 索赔窗口 [s58](wiki/entries/s58-amazon-brazil-fba-claim-window-readiness.md)；Apple 取消挽留消息 [s40](wiki/entries/s40-apple-retention-messages-readiness.md)、多席位 [s31](wiki/entries/s31-apple-multiseat-subscription-readiness.md)；Google Play 拒付 [s32](wiki/entries/s32-google-play-chargeback-review-readiness.md)；Etsy 商品图 [s29](wiki/entries/s29-etsy-listing-image-ai-readiness.md)；EU 低货值包裹 [s16](wiki/entries/s16-eu-product-identifiers.md) / [s17](wiki/entries/s17-eu-uhf-duty-recovery.md)；Shopify 公开 App IP 白名单 [s37](wiki/entries/s37-shopify-ip-allowlist-readiness.md)。

## 全部条目

共 89 篇，按市场分组、组内按平台细分，一篇不漏。★ 为 [Catalog](wiki/Catalog.md) 中的优先验证方向。

<!-- 新条目：加到对应市场与平台小节末尾，并更新上方篇数与徽章 -->
### 跨境电商 / 独立站

#### 经营模式（常青）

- [★ AI + POD 轻资产定制（TikTok / 独立站）](wiki/entries/e1-ai-pod.md)
- [区域细分 + TikTok Shop 短视频自然流](wiki/entries/e2-tiktok-regional.md)
- [★ 高客单差异化独立站（先平台验证）](wiki/entries/e3-high-aov-dtc.md)
- [内容 SEO + Reddit / YouTube 有机引流独立站](wiki/entries/e4-organic-seo.md)
- [消耗品 / 宠物 / 美妆补货型订阅盒](wiki/entries/e5-subscription-box.md)
- [平台测款 → 品牌站沉淀的双通道模型](wiki/entries/e6-dual-channel.md)
- [★ 数字商品独立站（模板 / 微课 / AI Prompt Pack）](wiki/entries/e7-digital-dtc.md)

### SaaS / 订阅

#### 常青 SaaS 切口

- [★ 垂直 AEO / AI 可见度追踪](wiki/entries/s1-vertical-aeo.md)
- [★ 订阅失败支付挽回（垂直化 dunning）](wiki/entries/s2-dunning.md)
- [平台伴生小工具（Shopify / Notion 等）](wiki/entries/s3-platform-addon.md)
- [自由职业者轻量客户中枢](wiki/entries/s4-freelancer-hub.md)
- [长视频 → 短视频的垂直切片工具](wiki/entries/s5-video-clips.md)
- [购买意向线索预警（单一行业）](wiki/entries/s6-intent-leads.md)
- [★ 退货原因 → 详情页修复闭环（服装独立站）](wiki/entries/s8-returns-listing.md)
- [★ COM 客户自带物料入站追踪（定制家具 / 软装独立站）](wiki/entries/s10-com-inbound.md)

#### AI 购物代理 / Agentic Commerce

- [★ Shopify Agentic Catalog 就绪体检](wiki/entries/s7-agentic-catalog.md)
- [★ AI 购物代理政策 / 履约就绪体检（shipping · cancel · pickup）](wiki/entries/s9-agent-policy.md)
- [★ Google AI Mode / Gemini 直购结账就绪体检](wiki/entries/s11-google-direct-checkout.md)
- [★ UCP 零售门店发现就绪体检（Physical storefront × 库存 × 自提）](wiki/entries/s12-ucp-location.md)
- [★ Agentic Knowledge base 发布就绪体检（draft → publish × 冲突 × 迁移）](wiki/entries/s13-knowledge-base-publish.md)
- [★ 退货窗覆盖规则就绪体检（Override × 最短优先 × 政策页）](wiki/entries/s14-return-window-overrides.md)
- [★ Compare-at / list_price 代理可见就绪体检](wiki/entries/s15-compare-at-list-price.md)
- [★ 渠道商品数据映射就绪体检（Google / Meta / TikTok / Catalog）](wiki/entries/s20-channel-mapping-readiness.md)

#### Shopify 商家与 App 开发者

- [★ Managed Markets 保价一口价运费就绪体检](wiki/entries/s18-mm-flat-rate-shipping.md)
- [★ Shop Promise 就绪体检（US 履约徽章 × Catalog 排序信号）](wiki/entries/s21-shop-promise-readiness.md)
- [★ Shopify 公开 App 过期离线令牌迁移体检（01-01 下架 × 01-15 商家警告 × 04-01 返回 403）](wiki/entries/s33-shopify-expiring-offline-token-readiness.md)
- [★ Shopify 公开 App IP 白名单就绪体检（11-12 批量失败 × 11-20 下架 × ASN/静态 IP）](wiki/entries/s37-shopify-ip-allowlist-readiness.md)
- [★ Shopify 自定义 App IP 白名单就绪体检（11-20 新装须配 × 2027-01-01 存量须配 × 漏一个连坐全部）](wiki/entries/s47-shopify-custom-app-ip-allowlist-readiness.md)
- [Shopify 按市场配运费迁移体检（自动迁移进行中 × 多费率改取最高 × 2027-07-01 不可退出）](wiki/entries/s49-shopify-market-driven-shipping-readiness.md)
- [Shopify Tax 免费额度改按终身销售额就绪体检（2027-01-01 起不再每年重置 × 10 万门槛 × 超线按单计费）](wiki/entries/s52-shopify-tax-lifetime-discount-readiness.md)
- [Shopify Shop 刊登资格更新体检（11-10 起非 Shopify Payments 店也可出现在 Shop × 全店资格已更新 × 未达标会被拿下）](wiki/entries/s54-shopify-shop-eligibility-readiness.md)
- [Shopify 退货与订阅 App 买家登录就绪体检（12-01 起须用 Customer Account API × 否则可能失去 Built for Shopify）](wiki/entries/s65-shopify-bfs-customer-account-api-readiness.md)
- [Shopify 店面前端网络访问声明就绪体检（12-01 拒发版与提交 × 2027-01-01 下架 × 须声明 allowed_sources）](wiki/entries/s66-shopify-network-access-declaration-readiness.md)
- [Shopify 店面 Script Tag 停用迁移体检（10-01 已禁新建 × 2027-03-01 停止注入 × 须改为 App embed 或像素）](wiki/entries/s67-shopify-script-tag-deprecation-readiness.md)
- [Shopify 弃单恢复链接受保护顾客数据就绪体检（12-01 公开 App 须获准四字段 × 2027-01-01 自定义 App 须自助开通 × 未获准则 GraphQL 整查询失败）](wiki/entries/s70-shopify-abandoned-checkout-url-pcd-readiness.md)

#### Amazon 卖家

- [★ Amazon Seller Central 多渠道就绪体检（eBay / Shopify / TikTok / Walmart）](wiki/entries/s22-amazon-multichannel-readiness.md)
- [★ FBA 退货定制分级就绪体检（Customized grading × Grade and Resell）](wiki/entries/s23-fba-customized-grading-readiness.md)
- [★ FBA 部分退款按原因就绪体检（Partial Refunds × return reason）](wiki/entries/s24-fba-partial-refund-readiness.md)
- [★ Amazon 虚拟多件装就绪体检（Virtual Multipacks × 单件费率 × 不可恢复删除）](wiki/entries/s26-amazon-virtual-multipack-readiness.md)
- [★ Amazon FBM 预付退货面单就绪体检（12-18 起 × 7 天时钟 × 自动免退退款）](wiki/entries/s27-amazon-fbm-prepaid-return-label-readiness.md)
- [★ Amazon 捆绑商品原厂包装新规体检（01-11 起 × 授权信 × 不合规下架记违规）](wiki/entries/s34-amazon-bundle-manufacturer-packaging-readiness.md)
- [★ Amazon 安全类目百万责任险就绪体检（11-02 起 × 不论销量 × 中国卖家须走 AIA）](wiki/entries/s36-amazon-liability-insurance-readiness.md)
- [★ Amazon 2027 FBA 费用调整利润体检（01-15 配送费上调 × 02-01 库龄仓储费 × 低库存费改规则）](wiki/entries/s45-amazon-fba-2027-fee-readiness.md)
- [Amazon 锂电消费电子 TIC 送检就绪体检（9-30 已生效 × 11-16 通知发完 × 须经授权实验室）](wiki/entries/s51-amazon-lithium-battery-tic-readiness.md)
- [Amazon Ads 健康背书与比较宣称举证就绪体检（11-15 政策页更新 × 证据须在 24 个月内 × 包装已印可免再举证）](wiki/entries/s56-amazon-ads-claims-substantiation-readiness.md)
- [Amazon 巴西站 FBA 遗失索赔窗口就绪体检（11-27 起 90 天从建单起算 × 8-24 前 PCP 在途遗失须在 11-26 前申报）](wiki/entries/s58-amazon-brazil-fba-claim-window-readiness.md)
- [Amazon 加拿大站跨境退货与免退规则就绪体检（11-23 起 × 无加拿大退货地址则 CAD 25 及以下自动免退 × 可自建规则）](wiki/entries/s59-amazon-canada-returnless-cross-border-readiness.md)
- [Amazon 美国站假日退货窗就绪体检（11-01 至 12-31 订单可退到 2027-01-31 × 苹果品牌到 1-15 × FBA/FBM 自动生效）](wiki/entries/s71-amazon-us-holiday-returns-readiness.md)
- [Amazon 欧洲站与英国站假日退货窗就绪体检（多数站点 11-01 至 12-25 可退到 2027-01-31 × 西班牙到 2-06 × 德法意部分类目到 1-15）](wiki/entries/s72-amazon-eu-uk-holiday-returns-readiness.md)
- [Amazon 加墨巴日澳新站假日退货窗就绪体检（多数买到 12-31 可退到 2027-01-31 × 加拿大苹果到 1-15 × 墨西哥手机与苹果到 1-14 × 日本苹果不在客户都合窗）](wiki/entries/s74-amazon-ca-mx-br-jp-au-sg-holiday-returns-readiness.md)
- [Amazon 英德法意西站 FBM 预付面单退货自动退款就绪体检（12-10 起 × 遗失或拒收自动退买家 × 非亚马逊承运商不获平台赔付）](wiki/entries/s77-amazon-eu-uk-aprl-auto-refund-readiness.md)
- [Amazon Ads 旧报表迁到统一报表就绪体检（01-18 起只读 × 01-31 关闭并删除未迁移数据 × 不要用 What's New 的 12-31）](wiki/entries/s78-amazon-ads-unified-reporting-migration-readiness.md)
- [Amazon AWD / MCF / MCD 2027 费用与燃油附加就绪体检（02-01 燃油附加扩到 AWD 运输和 MCD × 处理/运输新费率 × 03-01 库龄仓储 × MCF 1-15 平均涨 3.5%）](wiki/entries/s81-amazon-awd-mcd-2027-fee-readiness.md)

#### TikTok Shop 卖家

- [★ TikTok Shop 账户健康分 BFCM 就绪体检（11-04 新扣分 × 保护期只停处罚 × 12-08 回归）](wiki/entries/s28-tiktok-shop-ahr-bfcm-readiness.md)
- [★ TikTok Shop 美区电子品类责任险就绪体检（$10k 月 GMV × BD TikTok USA LLC × 持续维持）](wiki/entries/s38-tiktok-shop-liability-insurance-readiness.md)
- [★ TikTok Shop API 取消单计入 SFCR 就绪体检（11-02 起 × IM 取消卡 24h × ≤2.5%）](wiki/entries/s39-tiktok-shop-api-sfcr-readiness.md)
- [★ TikTok Shop 运费与重量结算加严就绪体检（11-12 起 × 虚高运费 × 改重降结算）](wiki/entries/s41-tiktok-shop-shipping-fee-weight-readiness.md)
- [★ TikTok Shop 商品 Listing 新规就绪体检（11-06 更新 × 禁外链 QR × 禁夸张宣称）](wiki/entries/s42-tiktok-shop-listing-policy-readiness.md)
- [TikTok Shop 假日退货窗就绪体检（11-11 至 12-31 订单可退到 2027-02-10 × 覆盖卖家设置 × API 二维码有效期）](wiki/entries/s48-tiktok-shop-bfcm-holiday-returns-readiness.md)
- [TikTok Shop 珠宝配饰合规就绪体检（英国站 12-21 生成待办 × 2027-01-28 可能下架 × 英/欧均须交标签与 REACH 文件）](wiki/entries/s55-tiktok-shop-jewelry-compliance-readiness.md)
- [TikTok Shop 英国站假日退货窗就绪体检（11-06 至 12-31 订单可退到 2027-01-31 × 与美区 2-10 不同 × 除外类目看商品页）](wiki/entries/s69-tiktok-shop-uk-holiday-returns-readiness.md)
- [TikTok Shop 欧盟站假日退货窗就绪体检（德法意西爱 11-11、比荷波 11-19 至 12-31 可退到 2027-01-31 × 与英区 11-06 / 美区 2-10 不同 × 除外类目看商品页）](wiki/entries/s79-tiktok-shop-eu-holiday-returns-readiness.md)
- [TikTok Shop 美国站 Virtual Bundles 开放就绪体检（11-26 页更新：全体卖家可用 × Product Bundle 转换会删 SKU 并作废促销 × 跨仓/拆包裹仍要白名单）](wiki/entries/s82-tiktok-shop-us-virtual-bundles-readiness.md)

#### Etsy / Walmart / Google Merchant

- [★ Etsy 商品图与 AI 新规就绪体检（一张未修图 × AI 教程禁售 × 不符被判退款）](wiki/entries/s29-etsy-listing-image-ai-readiness.md)
- [★ Google Merchant Center 商品图 500px 新规就绪体检（01-31 起 × AI 图须留元数据 × 促销标题禁写日期）](wiki/entries/s43-google-merchant-image-500px-readiness.md)
- [★ Walmart 单品退货率下架就绪体检（2027-01 起 × 账户达标也会单品下架 × 60 天卖家责任退货）](wiki/entries/s44-walmart-item-return-rate-readiness.md)
- [Walmart Marketplace 假日退货窗就绪体检（10-01 至 12-31 订单可退到 2027-01-31 × 除外类目看政策 × 须遵守平台退货政策）](wiki/entries/s73-walmart-holiday-returns-readiness.md)
- [★ Etsy EU GPSR 制造商与欧盟负责人就绪体检（2027-02-01 起 × 缺字段 Listing 被拒 × 经济运营方记录）](wiki/entries/s46-etsy-gpsr-economic-operator-readiness.md)
- [Google Merchant Center 促销价 30 天窗就绪体检（sale_price 持续期不宜超过 30 天 × 过长可能失去划线价与促销标 × 与 s43 图规、促销标题分开）](wiki/entries/s80-google-merchant-sale-price-30-day-readiness.md)

#### 跨境物流、税务与合规（EU / UK / US）

- [★ EU 低货值包裹三件套商品标识符就绪体检](wiki/entries/s16-eu-product-identifiers.md)
- [★ EU €2 处理费 + €3 关税结账回收就绪体检](wiki/entries/s17-eu-uhf-duty-recovery.md)
- [★ UK VAT 履约仓路由就绪体检（>£135 GB）](wiki/entries/s19-uk-vat-fulfillment-routing.md)
- [★ 美国邮政小包 Entry Type 13 就绪体检（01-20 起 × 301 关税与 FDA/CPSC 类商品 × 缺数据被扣或退回）](wiki/entries/s35-us-postal-entry-type13-readiness.md)
- [美国站无线电子产品 FCC ID 就绪体检（10-13 已生效 × 缺 FCC ID 的 Listing 被拦 × 2027-06-01 卖点处须展示）](wiki/entries/s50-fcc-id-marketplace-listing-readiness.md)
- [美国邮政 2027 运费与短付再计价就绪体检（01-17 起 × 平均涨 5.9% × 燃油附加 11% × 短付加收 20%）](wiki/entries/s68-usps-2027-price-repricing-readiness.md)
- [UPS / FedEx 2027 运费就绪体检（12-21 UPS 平均涨 5.9% × 01-04 FedEx 平均涨 5.9% × 附加处理最低计费重 40→50 磅）](wiki/entries/s75-ups-fedex-2027-rate-readiness.md)
- [DHL Express 2027 美国运费就绪体检（01-01 美国账户平均涨 5.9% × 燃油附加改按周 USGC 即期 × 高风险附加改按票或按公斤取高）](wiki/entries/s76-dhl-express-2027-us-rate-readiness.md)

#### 订阅收款（Stripe / App Store / Google Play）

- [★ Stripe 订阅暂停留存就绪体检（Portal pause × flexible billing × auto-pause）](wiki/entries/s25-stripe-pause-retention-readiness.md)
- [★ Stripe Radar 续费筛查计费就绪体检（10-21 续费计费 × 01-22 试用结束 × Lite 还是 Standard）](wiki/entries/s30-stripe-radar-renewal-cost-readiness.md)
- [★ Apple 订阅多席位就绪体检（10-22 默认开启 × 关错开关会停续费 × 冬季群组购买）](wiki/entries/s31-apple-multiseat-subscription-readiness.md)
- [★ Google Play 拒付成本就绪体检（8-03 后订单由开发者承担 × 24 小时 ReviewRefund × 只认第一次回应）](wiki/entries/s32-google-play-chargeback-review-readiness.md)
- [★ Apple 订阅取消挽留消息就绪体检（11-04 上线 × 取消流程文案/优惠 × 审核禁写价格）](wiki/entries/s40-apple-retention-messages-readiness.md)
- [Google Play 美区外链下载上报与服务费就绪体检（2027-02-01 须上报成功下载并缴费 × 游戏 $3.65 / 应用 $2.85 × 外链后 24 小时）](wiki/entries/s53-google-play-external-link-fee-readiness.md)
- [Google Play 资格折扣订阅披露就绪体检（2027-01-27 起 × 学生价等须写明资格、核验与资格结束后的价格）](wiki/entries/s57-google-play-eligibility-discount-disclosure-readiness.md)
- [Google Play 进出日本打款授权就绪体检（12-01 前完成 PSA 授权否则全球冻结打款 × 卖进或卖出日本都可能要做）](wiki/entries/s60-google-play-japan-payout-authorization-readiness.md)
- [Google Play 交易者身份声明就绪体检（2027-02-01 前须在 Console 声明 × 未完成可能被拦截更新或全球下架 × 3-01 起向用户展示）](wiki/entries/s61-google-play-trader-status-declaration-readiness.md)
- [Apple 年龄分级新内容描述就绪体检（2027-01-12 前须完成 Shared Location 与 Dating and Relationships 声明 × 约会类至少 18+）](wiki/entries/s62-apple-age-rating-descriptors-readiness.md)
- [Apple 中国大陆 AIGC 与安全评估合规就绪体检（2027-01-31 前现有应用须完成并核验声明否则中国区不可售 × 无相关功能也须选 No）](wiki/entries/s63-apple-china-aigc-security-assessment-readiness.md)
- [Lemon Squeezy 关停迁移就绪体检（12-02 工具上线 × 2027-03-31 停止处理交易含续费 × 官方不延期）](wiki/entries/s64-lemon-squeezy-migration-readiness.md)

### 其他导航

- [Wiki 首页](wiki/Home.md) — 用法与画像建议
- [完整索引表 Catalog](wiki/Catalog.md)
- [更新日志 digests](wiki/digests/)

## 怎么用

1. 从「常青精选」或「临期窗口」挑一条和你画像匹配的
2. 按「一句话 → 为什么现在 → 一人怎么起步」做 **2–4 周**最小验证
3. 没有付费信号就换切口，不要加预算硬扛

**收录标准**：一人可冷启动、有清晰客户与变现路径、有公开线索、能在 2–4 周内验证，至少满足两条。跳过空泛风口、纯广告和无法验证的「暴利」承诺。

## English

**One-Person Company Opportunity Wiki**: 89 Chinese-language playbooks for solopreneurs and indie hackers in cross-border e-commerce and SaaS/subscriptions, updated daily. Most entries turn a fresh platform policy change (Amazon, TikTok Shop, Shopify, eBay, Stripe, Lemon Squeezy, App Store, Google Play, Walmart, Etsy, Google Merchant Center, USPS, UPS, FedEx, DHL Express) into a sellable "readiness audit" service: who is affected, why now, how one person can start in two weeks, how to charge, and the pitfalls, with links to official sources. Start with the [evergreen picks](#常青精选新手从这里开始) or the [deadline table](#临期窗口). ⭐ Star to follow along.

## 参与贡献

发现新的平台变更、过时信息或想补一手经验，欢迎 [提 Issue](https://github.com/hqzhon/opc-opportunity-wiki/issues/new/choose) 或 PR，规则见 [CONTRIBUTING.md](CONTRIBUTING.md)。如果某条帮你接到了单或避开了坑，也欢迎在 Issue 里分享。

## 免责与许可

本仓库内容仅供信息整理与学习交流，不构成投资、经营或法律建议。每条机会需自行验证可行性、合规与成本；外链原文版权归原作者。

内容采用 [CC BY 4.0](LICENSE) 许可：可自由转载和改编（含商用），请注明「一人公司机会 Wiki」并附本仓库链接。

---

<div align="center">

**每日更新** · 如果这份清单对你有帮助，点个 ⭐ 让更多做一人公司的人看到

</div>
