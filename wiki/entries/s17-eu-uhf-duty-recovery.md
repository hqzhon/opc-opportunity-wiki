# EU €2 处理费 + €3 关税结账回收就绪体检

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-28 |

## 一句话

对发往欧盟的 DTC / 跨境独立站跑「关税与 Union Handling Fee 结账回收」专用体检：平均申报行数 ×（€3 关税 + €2 UHF）是否已通过运费/市场价/Duties 功能回收、Managed Markets 与自有承运商路径是否分清、结账文案与退货政策是否覆盖「UHF 不退」——给出可修分数卡与上新后漂移报警。

## 为什么现在

欧盟自 **2026-07-01** 取消 €150 以下免税并以每申报行 **€3** 临时关税取代；自 **2026-11-01** 起再对所有电商包裹按申报行加收 **€2 Union Handling Fee（UHF）**，不论货值高低，且退货/拒收亦不退。荷兰海关、爱尔兰 Revenue 等已公开规则与算例。Shopify Changelog（2026-06-26）已让 Managed Markets / Duties 自动含 €3；但据 EAS（2026-10-22 更新）实务指南，**Shopify Duties 当时仍未把 €2 UHF 算进 duty 总额**——商家须用欧盟运费加价或市场价补洞，否则要么自己吞利，要么买家货到付款惊讶。截止日已到假日前夜，且与海关三件套标识符同一天生效，结账侧回收与标签侧数据是两条线，中小店仍缺轻量「行均成本 × 回收路径 × 文案合规」订阅楔子。

## 目标客户

从欧盟外（含英国）发欧盟消费者的 Shopify / Woo / Wix 独立站与代运营；SKU 组合多（多申报行）、自有承运商/邮政清关、或 Duties 已开但未核对 UHF 的中小品牌；客服已出现「到付多收 / 退货不退处理费」投诉者优先。

## 一人怎么起步

两周 concierge：导出近月欧盟订单 → 按订单统计申报行（不同品类/HS 分行，同款合计一行）→ 算行均 × €5（或 Duties 已收 €3 时只盯 €2）→ 核对 Settings→Shipping 欧盟区费率名与加价、Markets 欧盟定价、Duties/Managed Markets 开关 → 向承运商/3PL 确认谁垫 UHF、哪些国家邮政不覆盖预付 → 抽测欧盟结账总价与政策页文案 → 检查退货政策是否写明 UHF 不退 → 交「可上线 / 先补运费再开欧盟 / 须改承运商」分数卡换 waitlist / 预付；验证后再做 Embedded 监测（费率被改回、新品行数飙升、Duties 开关漂移）。

## 难度

中（规则写在海关官网 + EAS 实务文 + Shopify Changelog；一人可两周探针。难点：勿承诺「加价后一定无到付」——邮政覆盖国别不一；勿把 €3/€2 伪装成 VAT 税率；UHF 永不退须写进退货政策；Managed Markets 商家身份与自有面单路径收费方不同，不能一套结论套所有店）

## 变现路径

月订阅监测（示意 $29–$99，按欧盟单量 / SKU 档）；截止前一次性结账回收审计；可与 `s16` 海关标识符体检打包成「11-01 欧盟双线就绪」。

## 注意的坑

与 `s16-eu-product-identifiers`（面单/海关单能否买成、三件套 PID）不同，焦点是 **结账与运费侧是否回收了 €3+€2、买家是否被到付惊吓**；两条可同一天到期但交付物不同。€3 只管 ≤€150；€2 UHF 管所有货值。按「申报行」计费 ≠ 按包裹件数、≠ 按购物车行（同款多件通常一行）。IOSS 只处理 VAT，不代收关税与 UHF。假 VAT 税率回收属错误做法。

## 来源线索

- [Dutch Customs: Handling fee for e-commerce (€2 from 2026-11-01)](https://www.douane.nl/en/themes/import-and-export/import/e-commerce/handling-fee-for-e-commerce/)
- [Dutch Customs: Timeline for new e-commerce rules](https://www.douane.nl/en/themes/import-and-export/import/e-commerce/timeline-for-new-e-commerce-rules/)
- [Irish Revenue: Union Handling Fee press release (2026-09-29)](https://www.revenue.ie/en/corporate/press-office/press-releases/2026/pr-092926-handling-fee.aspx)
- [Shopify Changelog: €3 EU import customs duty collection (2026-06-26)](https://changelog.shopify.com/posts/new-3-eu-import-customs-duty-arrives-july-1)
- [EAS: Setting up €3 duty and €2 handling fee collection on Shopify/Wix/Woo (updated 2026-10-22)](https://help.easproject.com/hc/en-gb/articles/5944792222111-Setting-up-3-EU-customs-duty-and-2-handling-fee-collection-Shopify-Wix-WooCommerce-and-EAS-API)
