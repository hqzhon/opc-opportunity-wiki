# Amazon 2027 FBA 费用调整利润体检（01-15 配送费上调 × 02-01 库龄仓储费 × 低库存费改规则）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | 是 |
| 更新 | 2026-11-12 |

## 一句话

帮 Amazon US 的 FBA 卖家在 **2027-01-15** 新配送费和 **2027-02-01** 新仓储费生效前，按 SKU 算清「涨多少、哪些反而降了、哪些库龄一过 180 天就变贵」，输出「改价 / 调包装尺寸 / 1 月前清库或移除 / 补货节奏」的逐 SKU 动作表——把一封面向所有卖家的调费通知，变成每家店自己的利润表。

## 为什么现在

- Amazon 官方（Selling Partners，2026-11-05，Sunny Jain，VP Worldwide FBA）：**2027-01-15** 起 FBA 配送费平均每件上调 **$0.19**（约售价 0.8%），按商品、尺寸、价格有涨有降；燃油与物流附加费维持不变。
- 同一公告：**2027-02-01** 起取消仓储利用率附加费，把库龄附加费并入「按库龄分档」的统一月度仓储费——周转 6 个月内的库存持平或更低，**库龄长的更贵**；低库存水平费改为只在库存低于 **28 天供应量**（同时看评估日前后各四周的实际出货）时收取。
- 第三方汇总（SimplFulfillment、Odla）补充：$10–$50 的小号标准件平均涨约 $0.40，>$50 的小号标准件约 $0.70；五个类目失去 Low-Price FBA 低价费率；大件与超大件分档重排；退货处理费随新尺寸分档调整（服装鞋类 01-15，其他 02-01）。具体以 Seller Central 费率页为准。
- Amazon 自己给了 Profit Analytics 里的 **Fee Change Comparison** 面板和 Revenue Calculator，但中小卖家没人把它和自己的售价、广告费、库龄报表合起来算——这正是一个人能卖的「表格 + 判断」服务。
- 窗口很明确：1 月中前要定新价，2 月 1 日前要决定哪些老库存移除或清仓，而现在正是假日季备货与定价的时候。

与 `s23` / `s24`（FBA 退货分级与部分退款）、`s26`（虚拟多件装）、`s34`（捆绑原厂包装）不同：本条只管 **2027 FBA 费用结构变化对每个 SKU 利润的影响**，可与 `s26` 一起卖「多件装/单件费率」优化。

## 目标客户

Amazon US FBA 中小卖家（年销售几十万到几百万美元、没有专职财务分析的团队），尤其是 $10–$50 小件、库龄长或季节性强的品类、大件家居；中国跨境卖家与小代运营（可白标）。

## 一人怎么起步

两周 concierge：请客户导出 Fee Change Comparison、FBA 库龄（Inventory Age）、近 90 天订单与广告花费 → 脚本把每个 SKU 的旧/新配送费、按新库龄档估算的仓储费、低库存费触发风险合到一张表 → 标出三类：利润被吃掉要提价或改包装的、因降费可以降价抢量的、库龄将过 180 天应在 02-01 前移除或促销的 → 交付逐 SKU 动作表和一页结论。先给 3–5 家低价试单，跑通后做成 1–3 月月度复盘。

## 难度

低到中（核心是表格合并与费率对照；需要读懂 Amazon 费率表，可先人工做）

## 变现路径

一次性 2027 费用影响体检（示意 $199–$599 / 店，按 SKU 数分档）；包装尺寸复测与改分档建议按 SKU 计费；1–3 月利润复盘订阅（示意 $79–$249 / 月）；给代运营的白标报告。以后每年 Amazon 调费都能复用。

## 注意的坑

平均 $0.19 不等于每个 SKU 的涨幅，一定以客户自己的 Fee Change Comparison 数据为准，不要拿平均数报给客户。第三方汇总的分档细节以 Seller Central 官方费率页为准，交付前核对一遍。移除和清仓有自己的费用，建议移除前要把移除费算进去。不要承诺「省多少钱」，只承诺「逐 SKU 算清影响并给出动作」。上面价格只是示意，需自行验证。

## 来源线索

- [Amazon Selling Partners: Update to US Referral and Fulfillment by Amazon fees for 2027（2026-11-05）](https://sellingpartners.aboutamazon.com/update-to-us-referral-and-fulfillment-by-amazon-fees-for-2027)
- [SimplFulfillment: Amazon FBA Fees for 2026 and 2027（分档与库龄费率汇总）](https://www.simplfulfillment.com/blog/amazon-fba-fees)
- [Chain Store Age: Amazon to increase, streamline shipping and logistics fees in 2027](https://chainstoreage.com/amazon-increase-streamline-shipping-and-logistics-fees-2027)
- [Odla: Amazon FBA fee changes 2027: US seller guide](https://odla.com/insights/amazon-fba-fee-changes-2027/)
- 相关但独立：[s26 Amazon 虚拟多件装就绪体检](s26-amazon-virtual-multipack-readiness.md)、[s34 Amazon 捆绑商品原厂包装新规体检](s34-amazon-bundle-manufacturer-packaging-readiness.md)、[s24 FBA 部分退款按原因就绪体检](s24-fba-partial-refund-readiness.md)
