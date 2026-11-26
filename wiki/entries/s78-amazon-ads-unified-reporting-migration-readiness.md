# Amazon Ads 旧报表迁到统一报表就绪体检（01-18 起只读 × 01-31 关闭并删除未迁移数据 × 不要用 What's New 的 12-31）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | |
| 更新 | 2026-11-26 |

## 一句话

帮仍在 Amazon Ads Console 旧的 **Sponsored Ads reports** 或 **DVA+**（Display, Video, and Audio，即原 Amazon DSP 报表页）拉保存报表、定期报表的卖家和代理，在 **2027-01-18** 旧页改为只读、**01-31** 关闭之前，把报表迁到 Unified Reporting（Measurement and Reporting > Reporting），并对照新旧口径。先出一份「仍在旧页的报表清单 × 能否迁移 × 须人工重建的类型」。不要用 2026-06-08 What's New 里仍写着的 **12-31** 日期。

## 为什么现在

本轮在浏览器打开了两篇可公开访问的 Amazon Ads Support Center 帮助文（未登录抓取这两篇 URL 仍会得到空页，日期以帮助文正文为准）：

- *Understand unified reporting*（[帮助文](https://advertising.amazon.com/help/GMH8A8AJSH4ATV6T)，页面标注 Updated on Nov 25, 2026）顶部写明：We are shutting down sponsored ads reports and DVA+ reports by **January 31, 2027**。
- *Migrate your scheduled reports to unified reporting*（[帮助文](https://advertising.amazon.com/help/GK3JZZE5QLTF8U8A)，页面标注 Updated on Nov 24, 2026）顶部写明：Sponsored ads reports 与 Display, Video, and Audio campaigns reports 将于 **January 31, 2027** 关闭；此日后，仍留在这些页面上的 **保存报表、定期报表和历史数据将被永久删除**。页面另有注明：**These dates are subject to change.**

官方迁移关键日期表（同一篇迁移帮助文）是：

- **2026-06-08**：可以开始手动把保存报表和定期报表迁到新报表页。
- **2026 年 9 月**：自助迁移工具可用，须在 2027-01-31 前完成迁移。
- **2027-01-18**：现有报表改为只读；当天起不能新建或编辑，已有报表在关闭前仍会按原计划投递。
- **2027-01-31**：旧报表中心永久下线，剩余保存报表、定期安排和历史数据被删除，立即失去访问。

不要用 [What's New：Streamline campaign analysis with unified reporting](https://advertising.amazon.com/resources/whats-new/streamline-campaign-analysis-with-unified-reporting) 里仍写着的 **December 31, 2026**。那是 6 月 8 日统一报表一般可用时的旧截止，本轮核对该页仍未改口，但 11-24 / 11-25 更新的两篇帮助文已经改到 01-18 / 01-31。第三方曾写过 12-17 只读，与现行官方表不符，不要采用。

另外：*Understand unified reporting* 仍列出若干「planned for release later in 2026」、尚未进入统一报表的类型（如 MRC viewability、Benchmarks、Conversion Path、Sponsored Products across retailers，以及旧版 Sponsored Brands 的 targeting / search term reporting）；迁移帮助文也列有 Coming soon 的类型。不能承诺所有旧报表都能原样迁过去，缺的要单独标出。

## 目标客户

在 Amazon Ads Console 定期从旧 Sponsored Ads 或 DVA+ / 原 DSP 报表页出数、再写入表格或 BI 的卖家、Vendor 和广告代理，尤其是多广告账户、多站点、有多份定期投递的团队。只做商品合规、不跑广告的店不是首要客户。广告宣称举证见 [s56](s56-amazon-ads-claims-substantiation-readiness.md)，不是同一件事。

## 一人怎么起步

两周 concierge：在 Ads Console 清点旧页上的保存报表和定期报表（接收人、频率、维度、广告产品、站点）；用官方自助迁移工具或在 Unified Reporting 重建；抽 1–2 个完整投放周期对照费用、点击和关键转化指标，记下对得上与对不上的项；把官方尚未纳入或写明即将进入统一报表的类型单独列表，并写明日期可能调整。只出迁移清单、对照记录和切换步骤，不代登录改出价或改预算，也不保证新旧口径完全一致。先收一次性体检费；迁移后第一个完整周期的对照巡检另报。

## 难度

低到中（官方已给出迁移入口、自助工具和两档日期；费功夫的是报表盘点、口径对照，以及尚未进入统一报表的类型怎么过渡）

## 变现路径

一次性统一报表迁移体检（示意 $149–$499 / 广告账户，按报表份数和账户数分档）；代理多账户可打包；迁移后一个月的投递与口径对照巡检另报。不包代运营广告或保证指标完全一致。

## 注意的坑

不要用 What's New 上的 12-31，也不要写已经过时的 12-17 只读日；以 11-24 / 11-25 更新的帮助文为准：01-18 只读、01-31 关闭并删除。官方写明日期可能再改，执行前要再打开帮助文核对。01-31 后未迁移数据是永久删除，不要承诺能找回。部分报表类型尚未进入统一报表，不要保证「全部一键迁移」。DVA+ 就是原 Amazon DSP 报表页的现行名称，不是另一套截止日期。本条与 [s56](s56-amazon-ads-claims-substantiation-readiness.md) 的广告宣称举证无关。价格只是示意，需自行验证。

## 来源线索

- [Amazon Ads Support Center: Understand unified reporting（Updated on Nov 25, 2026；banner 写明 Sponsored Ads reports 与 DVA+ reports 于 2027-01-31 关闭）](https://advertising.amazon.com/help/GMH8A8AJSH4ATV6T)
- [Amazon Ads Support Center: Migrate your scheduled reports to unified reporting（Updated on Nov 24, 2026；01-18 只读、01-31 关闭并永久删除未迁移的保存报表 / 定期报表 / 历史数据；日期可能调整）](https://advertising.amazon.com/help/GK3JZZE5QLTF8U8A)
- [Amazon Ads What's New: Streamline campaign analysis with unified reporting（仍写 2026-12-31 停用 Sponsored Ads reports 与 Amazon DSP reports，本轮核对此页已过时，不要作为截止日）](https://advertising.amazon.com/resources/whats-new/streamline-campaign-analysis-with-unified-reporting)
- 相关但独立：[s56 Amazon Ads 健康背书与比较宣称举证就绪体检](s56-amazon-ads-claims-substantiation-readiness.md)
