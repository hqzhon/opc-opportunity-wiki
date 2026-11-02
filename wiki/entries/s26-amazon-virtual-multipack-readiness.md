# Amazon 虚拟多件装就绪体检（Virtual Multipacks × 单件费率 × 不可恢复删除）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | 是 |
| 更新 | 2026-11-02 |

## 一句话

帮被 Amazon 选入「虚拟多件装」试点的 US FBA 品牌卖家，在 **2026-11-10** 审核截止前把每个 `VMP_` 多件装过一遍：按真实佣金 + 逐件 FBA 配送费 + 旺季附加费算毛利，核对价格/图片/文案与单件是否同步、单件库存够不够被多件装吃——输出「保留原价 / 设折扣 / 只改图文 / 慎删」分数卡。

## 为什么现在

Amazon FBA 团队 **2026-10-13** 通知部分品牌卖家：新一波虚拟多件装（Virtual Multipacks, VMP）将在 **2026-10-28** 前**自动创建**（卖家不能报名也不能退出），**2026-11-10** 前可审核或删除，**2026-11-11** 起未删除的全部对买家开售——正好压在黑五/网一前。每个多件装有独立 ASIN 与 `VMP_` 前缀 SKU，挂在原单件详情页做变体，从单件 FBA 库存直接拣货发出。坑集中在几处：

- **费用没有规模效应**：无项目费，但配送费按件收，2 件装 = 2 倍单件 FBA 费；叠加 **2026-10-15 至 2027-01-14** 旺季配送费与 3.5% 燃油/物流附加费，一旦再打折，折扣全部从毛利里出。
- **删除不可逆**：Amazon 帮助页写明试点期内删掉的多件装**无法重新激活**，顺手「清理目录」会永久丢掉一个变体位。
- **只能在一个入口改**：只能用 Edit virtual multipack 改价格/标题/图片/描述，走 flat file、API 或第三方改价工具可能把 listing 改坏；包装数量不能改。
- **图文与价格是否跟随单件**：图片由单件图自动生成且不会随单件更新；价格是否跟随单件，各家解读不一致（见来源），必须逐个实查。
- **库存被放大消耗**：多件装一单吃多件单件库存，旺季更容易断货；单件断货时多件装同步下架。

大部分一人/小团队品牌卖家没有逐 ASIN 的单位经济表，8 天窗口里最缺的是「哪些该留、该不该打折、哪些别删」的快速判断。与 `s23`（退货定制分级）、`s24`（按原因部分退款）不同，本条专盯 **Amazon 代建的多件装 listing 的保留/定价/库存决策**。

## 目标客户

收到 2026-10-13 FBA 通知、`Manage All Inventory` 里能筛出 `VMP_` SKU 的 US FBA 品牌卖家（Brand Registry），尤其是消耗品、宠物、个护、小家居等适合多件购买的品类；以及服务这些卖家的小型代运营。对 4 月英国站等先前波次的卖家，可作为后续波次的模板。

## 一人怎么起步

两周 concierge（前 8 天赶 11-10 截止）：让客户导出 `VMP_` SKU 列表与对应单件 ASIN → 用 Fee Preview / 收费明细拉佣金与单件 FBA 费，算「多件装价 − 佣金 − N × 配送费（含旺季附加）− N × 货本」的单位毛利，与卖 N 次单件对比 → 核对自动图片、标题、价格与单件是否一致，标出需手动同步项 → 按近 30 天单件销量 × 预计多件装占比估算断货日 → 交「保留原价 / 设 x% 折扣 / 只改图文 / 慎删（说明不可恢复）」分数卡，换一次性审计费或旺季陪跑预付；11-11 上线后跟踪多件装销量、AOV、单件断货与利润，作为下一波的复用模板。

## 难度

低到中（纯表格与 Seller Central 操作，不需要写代码；难点在拿准真实费率与库存节奏；勿用改价工具或 API 直接改 VMP；不承诺销量提升）

## 变现路径

一次性 VMP 审计（示意按 ASIN 数分档 $99–$499）；旺季期间月度监测多件装毛利、价格/图片同步与断货风险（示意 $49–$149/月）；可与 `s23`/`s24` 打包成「FBA 假日旺季体检」，但不合并条目。

## 注意的坑

只有被 Amazon 选中并通知的卖家才在本波，先确认客户真有 `VMP_` SKU 再报价。删除不可逆，任何「建议删除」都要客户书面确认；更稳妥的做法通常是改价或改图而不是删。各家对「价格是否随单件变化」说法不一，以客户后台实测为准。多件装与实体捆绑装（physical bundle）不同：后者单件费更省但要备货改包装，别混为一谈。旺季附加费与佣金类目变更（如 10-31 部分 ASIN 重新归类）要实时取数，不要用旧费率表。

## 来源线索

- [Amazon Seller Forums (UK): Review your virtual multipack listings（先前波次官方通知原文）](https://sellercentral.amazon.co.uk/seller-forums/discussions/t/14449267-870f-479e-ac59-1045df72d7d8)
- [Nova Data: Amazon virtual multipacks — next wave goes live on November 11](https://novadata.io/resources/news/amazon-virtual-multipacks-next-wave-november-11-2026)
- [SellerKit: Next Virtual Multipack Wave — Oct 28 / Nov 10 / Nov 11, 2026](https://sellerkit.me/fba-updates/virtual-multipacks-next-wave-october-28-live-november-11-2026)
- [AMZScaler: Amazon Virtual Multipacks — what FBA sellers must check now](https://amzscaler.com/amazon-virtual-multipacks/)
- [Marketplace Officer: Amazon Seller News November 2026（旺季费、附加费与截止日历）](https://www.marketplaceofficer.com/blog/amazon-seller-news)
