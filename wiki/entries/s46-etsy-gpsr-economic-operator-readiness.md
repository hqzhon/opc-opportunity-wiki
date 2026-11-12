# Etsy EU GPSR 制造商与欧盟负责人就绪体检（2027-02-01 起 × 缺字段 Listing 被拒 × 经济运营方记录）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | 是 |
| 更新 | 2026-11-12 |

## 一句话

帮卖进 EU / 北爱尔兰的 Etsy「trader」店铺，在 **2027-02-01** 强制执行前把受 GPSR 约束的 Listing 逐条补上「制造商 + 欧盟负责人」：先判定哪些店、哪些类目、哪些 Listing 真正受影响，再建好可复用的经济运营方（economic operator）记录并批量回填、回读校验——不然 2 月起这些 Listing 创建或更新会直接被拒。

## 为什么现在

- Etsy 官方开发者公告（etsy/open-api Discussion #1774，2026-10-29「Action Required: GPSR Economic Operator Updates」）：Open API 新增店铺级经济运营方接口（`createShopEconomicOperator` 等）和 Listing 上的 `gpsr_manufacturer_*`、`gpsr_responsible_person_*`、`gpsr_serial_number`、`gpsr_safety_warnings` 字段。
- 同一公告：通知期内字段可选，但**现在发送的值就会被立即校验**；**2027-02-01** 起，向 EU/NI 销售的 trader 在适用类目下的 Listing **必须**带制造商和欧盟负责人，否则 Listing 被拒。
- 只有三条同时成立才受约束：店铺是 trader、卖进 EU/NI、Listing 在须提供 GPSR 信息的类目；个人非 trader 卖家不需要。第三方解读（Ankka，2026-11-06）提醒：公告写 EU/NI，教程写 EEA，范围不同要先核清；`who_made = someone_else` 时制造商不能填 seller；欧盟负责人若填 seller，店铺须有欧盟法定地址。
- 中国与非欧盟的 Etsy 卖家大多没有欧盟负责人（Authorized Representative），手工逐条在后台改也很费时——「判定范围 + 找/对接欧盟代表 + 批量回填」正是一人可接的活，而离截止还有约 11 周。

与 `s16`（EU 低货值包裹商品标识符）、`s29`（Etsy 商品图与 AI 新规）不同：本条只管 **Etsy Listing 上的 GPSR 制造商与欧盟负责人字段**。

## 目标客户

卖进欧盟/北爱尔兰的 Etsy trader 店铺（尤其中国与美国等非欧盟卖家、玩具/首饰/家居/儿童用品等适用类目）；做 Etsy 多店铺管理或刊登工具的小型 SaaS 与代运营（可白标）。

## 一人怎么起步

两周 concierge：先拿客户的 Listing 导出和类目 → 按「trader × 是否卖进 EU/NI × 类目」标出受影响清单 → 整理每个商品的真实制造商信息，没有欧盟负责人的介绍现成的 EU 代表服务（只做对接，不冒充代表）→ 在 Shop Manager 建好经济运营方记录 → 用 Open API 批量回填字段并回读核对，输出「已就绪 / 缺资料 / 范围存疑」三栏报告。先做 3–5 家试单，跑通后把脚本做成按店收费的小工具。

## 难度

低到中（判定规则清楚、API 字段简单；难点是逐个商品拿到真实制造商与欧盟代表信息）

## 变现路径

一次性 GPSR 就绪体检与回填（示意 $149–$499 / 店，按 Listing 数分档）；新品上架持续补字段的月度服务（示意 $39–$129 / 月）；与欧盟代表服务商的转介绍分成；给 Etsy 刊登工具开发者的字段映射咨询。同样的流程可迁移到其他要求 GPSR 的平台。

## 注意的坑

这是平台规则就绪，不等于法律意见：GPSR 法律义务早已生效，2 月 1 日只是 Etsy 开始拒 Listing 的日子；是否算 trader、是否需要欧盟代表让客户自己或律师判断。EU/NI 与 EEA 范围的差异以 Etsy 最新指引为准，存疑的标出来不要硬判。经济运营方 ID 只能用本店的，不要跨店复制。不要编造制造商或代表信息。上面价格只是示意，需自行验证。

## 来源线索

- [Etsy Open API: Action Required: GPSR Economic Operator Updates（Discussion #1774）](https://github.com/etsy/open-api/discussions/1774)
- [Etsy Help: How to Add an Economic Operator](https://help.etsy.com/hc/en-us/articles/19880002187927-How-to-Add-an-Economic-Operator)
- [Ankka: Etsy GPSR fields are live: prepare eligible listings before February 1, 2027（2026-11-06）](https://ankka.ai/b/etsy-gpsr-fields-are-live-prepare-eligible-listings-before-february-1-2027/)
- 相关但独立：[s29 Etsy 商品图与 AI 新规就绪体检](s29-etsy-listing-image-ai-readiness.md)、[s16 EU 低货值包裹三件套商品标识符就绪体检](s16-eu-product-identifiers.md)
