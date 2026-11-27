# TikTok Shop 美国站 Virtual Bundles 开放就绪体检（11-26 页更新：全体卖家可用 × Product Bundle 转换会删 SKU 并作废促销 × 跨仓/拆包裹仍要白名单）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | |
| 更新 | 2026-11-27 |

## 一句话

帮 TikTok Shop **美国站**多 SKU 卖家确认后台已经出现 Virtual Bundles 入口，用对「新建组合」还是「转换已有 listing」的路径，算清组合库存和毛利；尤其不要在促销或订阅还在走的时候，用 Product Bundle 去转换——那会删掉原有 SKU，并让订阅、促销和活动报名失效。不要把这次开放套到英区或其他站点，也不要以为跨仓、拆包裹履约已经一起放开。

## 为什么现在

美国站 Seller University《Virtual Bundles》页（[knowledge_id=894944353240878](https://seller-us.tiktok.com/university/essay?knowledge_id=894944353240878&lang=en)）**Updated at: 11/26/2026**，文首写明：**This feature is now available to all sellers. All sellers can access and use it through the entry point described in this article.** 页面没有另给正式生效日，也没有写费用、处罚或强制截止日期。下午那一轮已看到第三方转述，但当时还没有可引用的官方链接，本轮以这份官方页为准补上。

开放的是**创建入口**，不是物流白名单。官方仍写：FBT 跨仓履约一般可用，用不了要找 AM；经 3PL/4PL 的拆包裹或跨仓履约，以及同一仓拆成多运单，仍须由 AM 申请额外白名单。FBT 与第三方仓之间的跨仓组合「currently not supported」，组合里的货必须同一履约类型：要么都在 FBT，要么都在海外仓。

两条搭建路径后果差很多：

- **新建组合**：生成新的 PID，不继承任何评价或销量；活动、促销和达人合作按普通新品处理。
- **转换已有商品**：PID、销量和评价保留，达人带货视频也可以保留。若用 **Product Bundle** 转换，原 listing 上的 SKU 会被删除，订阅、促销和活动报名失效；若在 **Edit Product** 里加 **SKU Bundle**，原 SKU、订阅、促销和活动不受影响。SKU Bundle 转换入口写明：**目前不适用于跨境直邮商品**。

库存由组件自动计算，卖家不能手改。官方公式按「每种组件能凑出的套数取最小值、向下取整」。同一仓库里 A=10、B=8、一套要 1 件 A + 2 件 B 时，可售是 4 套；组件分散在不同仓库且没有跨仓白名单时，总数看起来够，可售是 **0**。组合价不得超过组件价格之和。Product Bundle 最多选 30 个商品；SKU Bundle 最多 25 个组件 SKU，同一组件最多进入 50 个组合。同时在多国销售的商品、已经是 Virtual Bundle 的商品、经 Global Product Management 发布的商品，以及部分二手奢侈品等，不能组或不能转。

FBT 使用组合 listing **没有额外功能费**，按组合里的件数和每件重量，依 FBT 费率卡收取履约费。用 API 自动发货或售后的，拆包裹/售后须按官方提示升级；不升级就只能在 Seller Center 手动处理。不用 API 的卖家不受影响。官方写 Virtual Bundle「generally」比单品有更高 AOV 和 GPM，这是概括，不是对单店的承诺。

本条只覆盖**美国站官方页**已经写明的规则。本轮尝试打开先前被引用的英区 Virtual Bundle 页时返回 404，不要把「美国站已对全体卖家开放」套到英区、欧盟站或其他市场。也不要和 Amazon 代建的虚拟多件装 [s26](s26-amazon-virtual-multipack-readiness.md) 混用。

## 目标客户

在 TikTok Shop 美国站卖多 SKU 的中小卖家，尤其美妆套装、服装鞋包、配件、耗材补货，或想把爆款和滞销款、单件和多件装放在同一条 listing 里卖的店；以及给这些店做代运营或 ERP / 仓储对接的小团队。只做英区或欧盟站、或只有单个 SKU 的不是本条首批。跨境直邮、多国同时在售、走 Global Product Management 的 listing，先核官方限制，不要默认能转。

## 一人怎么起步

两周 concierge：先让客户在 Seller Center 的 Product Management 核对是否已出现「Product-level virtual bundle」或「Create SKU-Level Virtual Bundle」入口（官方写全体美国卖家可从该文入口进入）。选出 3–5 组自然搭配，标清组件仓位（是否同一仓、FBT 还是 3PL）、是否有进行中的促销、订阅或活动，以及是否跨境直邮。定价先卡在「不超过组件价之和」，再按官方库存公式算可售套数；仓位不一致就先记「可能显示 0，须申请 Cross-Warehouse Bundle 白名单」，不要上架后再问为什么没货。推荐路径：无历史的组合用新建；要保住评价和销量时，优先 SKU Bundle 转换，避开正在跑促销或订阅的 Product Bundle 转换。对使用 ERP / API 自动发货的店，先做一单端到端：看订单能否拆到子 SKU、能否正常出单，并确认要不要升级拆包裹接口。交付「可新建 / 可 SKU 转换 / 先申请白名单 / 本轮不要动」对照表，附库存与毛利假设（履约按件数计，拆包裹非 FBT 可能按两张面单计）。只出书面方案和后台操作清单，不代改活动报名，也不承诺组合一定提高 AOV。

## 难度

低到中（核心是核对入口、转换路径和仓库位置，不需要写代码；难点在避开 Product Bundle 误转换，以及跨仓 / 拆包裹仍要白名单。ERP 店要加一单实测。不承诺流量或转化。）

## 变现路径

一次性组合路径体检（示意 $99–$299 / 店，按 SKU 组合数分档）；帮选新建或转换路径并复盘首单（示意 $79–$199）；旺季期间库存与仓位巡检（示意 $49–$149 / 月）。价格只是示意，需自行验证。

## 注意的坑

不要写成「全球已开放」或「物流限制也取消了」——官方只改了美国站创建入口的表述。不要在促销、SNS 订阅或活动进行中用 Product Bundle 转换：SKU 会被删，订阅会失效并通知买家，活动须重配。转换后，旧 listing 关联的达人样品申请会显示已删除或停售；新品组合才支持新的样品申请。组件不在同一仓、又没有跨仓白名单时，库存是 0，不是把两个仓加总。FBT 和第三方仓不能混在同一个跨仓组合里。拆出的任一包裹晚发，都会影响整单时效。不要把 Amazon 的 Virtual Multipacks（s26，平台代建、删除不可逆）套到这条。价格只是示意。

## 来源线索

- [TikTok Shop US Seller University: Virtual Bundles（Updated at: 11/26/2026；文首写明现已对所有卖家开放；新建与转换路径、库存公式、跨仓/拆包裹白名单、FBT 费用与限制）](https://seller-us.tiktok.com/university/essay?knowledge_id=894944353240878&lang=en)
- 相关但独立：[s26 Amazon 虚拟多件装就绪体检](s26-amazon-virtual-multipack-readiness.md)
