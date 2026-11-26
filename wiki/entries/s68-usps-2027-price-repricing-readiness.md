# 美国邮政 2027 运费与短付再计价就绪体检（01-17 起 × 平均涨 5.9% × 燃油附加 11% × 短付加收 20%）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | |
| 更新 | 2026-11-25 |

## 一句话

帮用商业折扣走 USPS（USPS Ship、PC Postage、Amazon 购买配送、Shopify / ShipStation 等打单）的 FBM 和独立站卖家，在 **2027-01-17** 前把三件事算清楚：头程/尾程头部 SKU 在平均 **5.9%** 涨价加上初期 **11%** 燃油附加后成本会变成多少；现在有没有尺寸、重量或 Extra Service Code（ESC）漏填，以及历史上有没有被 Automated Package Verification（APV）改过价——因为从当天起，USPS Ship 或 APV 检出的短付不仅要补足欠付邮资，还要按欠付额加收 **20%**「Repricing Fee」，合计从邮资账户扣走。先出一份「费率影响 / 短付风险 / 清单字段」分数卡，再决定要不要改包装、默认重量或打单流程。

## 为什么现在

美国邮政 **2026-11-19** 在 Federal Register 公布国内竞争性产品定价与交寄标准终版规则（2026-23595），**生效日 2027-01-17**：

- **Priority Mail Express、Priority Mail、USPS Ground Advantage** 整体平均上调 **5.9%**（含零售与商业价；Flat Rate 信封和箱子同步调整）。Parcel Select 目的地交寄平均上调 5.9%，USPS Connect Local 上调 6.0%。
- **燃油附加费**：对零售和商业价的 Priority Mail Express、Priority Mail、USPS Ground Advantage（含 USPS Returns）以及 Parcel Select（**不含** USPS Connect Local）按基础邮资加收。初期全产品固定 **11%**，结构上预留日后按 EIA 油价浮动；官方新闻稿写明现阶段不加在国际产品上，并计划 **2027 年 7 月**再评估。
- **短付与超付**：商业 Priority Mail Express / Priority Mail / Ground Advantage / Parcel Select，经 USPS Ship 或 APV 检出邮资不足的，寄件人须承担全部欠付邮资，并就每件欠付额加收 **20%** Repricing Fee，合计从账户扣除。超付退款须自行申请，只有超过 **$5** 的申请才受理，且合格退款同样收取 20% Repricing Fee。
- **清单不合规**：2026-07-12 已实施的尺重不合规费第一阶段之后，第二阶段把该费改名为 Dimension and Weight Noncompliance Fee（金额仍为 **$3**），开始对清单中**漏填**全部尺寸、重量或 ESC 收费；官方写明本阶段不再把「准确性」作为该费的构成要素。量错尺寸或重量若导致邮资不足，走的是上面的短付 + 20%，不要和 $3 漏填费混为一谈。
- **超重超尺寸**附加费从 $200 提高到 **$400**。

11-12 官方新闻稿发出时仍写「已提交监管机构审议」；11-19 国内竞争性产品的 DMM 修订已作为 final rule 公布，生效日就是 1-17。Postal Explorer 的 2027 年 1 月价表页面应对照终版规则使用。现在距生效大约八周，覆盖假日高峰后的退货和补货旺季，卖家要在打单软件更新费率之前先知道自己的短付敞口。

本条不管海关申报。国际邮政小包进美国的 Entry Type 13 电子申报是 **2027-01-20**，见 [s35](s35-us-postal-entry-type13-readiness.md)，不要和本条的国内运费、燃油附加与再计价费混用。

## 目标客户

从美国仓或美国 3PL 用 USPS 商业折扣发货的 Amazon FBM、Walmart、eBay 和 Shopify / 独立站卖家，以及帮他们打单、对账的小代操或货代。尤其已经经常收到 APV 改价、默认重量常年不校准、或清仓期用轻小件 Ground Advantage / Priority Mail 走量的店。全部走 UPS / FedEx 的见 [s75](s75-ups-fedex-2027-rate-readiness.md)；走 DHL Express 美国账户的见 [s76](s76-dhl-express-2027-us-rate-readiness.md)；只在柜台零售窗口付钱、不用商业清单的，不是首要客户。

## 一人怎么起步

两周 concierge：先发一份公开自查表（「你用 USPS Ship、PC Postage 还是平台购买配送？过去 90 天有没有 APV 补扣？打单时尺寸、重量、ESC 是手填、默认值还是从仓库回传？1-17 之后的运费模板谁来更新？」）到 Amazon FBM、Shopify 履约和独立站卖家社群换 waitlist。对报名的 5–10 家：只读导出近期运费账单和 APV / 短付记录，按头部 SKU 估算 5.9% 加 11% 燃油附加后的单件成本；抽查清单是否会漏尺寸、重量或 ESC；列出 1-17 前要改的默认重量、包装规则和软件更新检查点。交付分数卡 + 成本对照表 + 一份「短付高发 SKU」清单。只出书面对照和流程建议，不代登录付款账户改默认值，也不保证某家打单软件会在 1-17 当天自动切换新费率。先收一次性体检费；需要按周复核短付或帮对 7 月燃油附加调整的，作为巡检另报。

## 难度

低–中（官方生效日、涨幅、11% 燃油附加和 20% 再计价费都写在终版规则里；真正费功夫的是把客户现有账单和包装数据对上，以及分清「漏填 $3」和「短付 20%」不是同一笔费用）

## 变现路径

一次性运费与短付风险体检（示意 $99–$299 / 店，含头部 SKU 成本对照和清单字段检查）；1–2 月每周短付 / APV 巡检（示意 $49–$99 / 月）。不包含代付邮资、不包改仓库系统。

## 注意的坑

以 Federal Register 终版规则和 Postal Explorer 价表为准，不要只引用 11-12 新闻稿里的「拟议」表述。燃油附加初期是固定 11%，官方预留日后浮动，新闻稿写 2027 年 7 月再评估，且现阶段不加在国际件上——国际件平均调价若要引用，须单独核对该产品的最终价表，不要把 5.9% 套到 PMEI / PMI 上。20% 是按**欠付邮资**加收，不是按整票邮资加收；超付不会自动退，须申请且有 $5 门槛。不要把本条写成「保证 1-17 后不再被扣款」，也不要教卖家故意低报重量。价格只是示意，需自行验证。

## 来源线索

- [Federal Register：Domestic Competitive Products Pricing and Mailing Standards Changes（终版规则，公布 2026-11-19，生效 2027-01-17；含 5.9% 调价、11% 燃油附加、短付 20% Repricing Fee、尺重漏填费和第二阶段更名）](https://www.federalregister.gov/documents/2026/11/19/2026-23595/domestic-competitive-products-pricing-and-mailing-standards-changes)
- [USPS 新闻稿：Recommends Shipping Price Adjustments for 2027（2026-11-12；说明 8% 运输相关加价转为燃油附加并再加 3% 至 11%，以及 7 月再评估、暂不加在国际产品上）](https://about.usps.com/newsroom/national-releases/2026/1112-usps-recommends-shipping-price-adjustments-for-2027.htm)
- [Postal Explorer：January 2027 Price Change（生效 2027-01-17 的价表与变更日志）](https://pe.usps.com/PriceChange/)
- 相关但独立：[s35 美国邮政小包 Entry Type 13 就绪体检](s35-us-postal-entry-type13-readiness.md)
- 相关但独立：[s75 UPS / FedEx 2027 运费就绪体检](s75-ups-fedex-2027-rate-readiness.md)
- 相关但独立：[s76 DHL Express 2027 美国运费就绪体检](s76-dhl-express-2027-us-rate-readiness.md)
