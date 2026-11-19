# Lemon Squeezy 关停迁移就绪体检（12-02 工具上线 × 2027-03-31 停止处理交易含续费 × 官方不延期）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | |
| 更新 | 2026-11-19 |

## 一句话

帮还在用 Lemon Squeezy 收款的独立开发者、数字商品和 SaaS 一人公司，在 **2027-03-31** 平台停止处理交易（**含订阅续费**，官方写明**不延期**）之前，先盘点能不能迁到 Stripe Managed Payments、哪些订阅和功能迁不过去、结账链接 / webhook / 文件履约要改哪里；**2026-12-02** 官方迁移工具上线前先做完自查，避免拖到 1 月中以后来不及走完官方所说的 4–8 周流程。

## 为什么现在

- Lemon Squeezy 官方迁移指南与 FAQ（文档页标题即为 *Lemon Squeezy is winding down*）：平台正在关停，**所有现有店铺都必须在 2027-03-31 前迁到 Stripe Managed Payments 或其他服务商**。当天起停止处理交易，**包括订阅续费**；FAQ 写明 **不会延长** 这一截止日。现有店铺在此之前仍可照常收款，官方会发提醒。
- 官方关键日期：
  - **2026-11-16**：已停止接受新用户和新店铺注册（本条只面向已有店铺）；
  - **2026-12-02**：面向符合条件店铺的 Managed Payments 迁移工具在 [app.lemonsqueezy.com/migration](https://app.lemonsqueezy.com/migration) 上线，官方会发邮件通知；
  - **2027 年 1 月中**：官方建议的最晚启动时点（端到端含顾客通知、换链和残留订阅清理，预计 **4–8 周**）；
  - **2027-03-31**：停止处理交易，无延期。
- 官方推荐目的地是 Stripe 的 Merchant of Record 方案 **Managed Payments**（数字商品：SaaS、软件、电子书、数字下载、自助课程等）。指南写明：须对照资格页核对企业所在地和产品类型；若所在地不受支持，或依赖 Managed Payments 目前没有的能力，则须在同一天前改迁其他服务商。
- 对比页和 FAQ 点名的能力缺口（迁之前就要盘）：**PayPal 目前不支持**；**不包含**托管店铺、文件 / 许可证交付、联盟分销、邮件营销；结账改为 Stripe Checkout / Payment Links。PayPal 订阅**不能按原方式迁移**，顾客须用受支持的支付方式重新订阅。印度发卡须在迁到 Stripe 后重新授权；Cash App Pay 订阅可以迁到 Managed Payments，但**不能迁到其他服务商**。Lemon Squeezy 的结账链接、店铺 URL、嵌入结账、API 和 webhook **都不会自动跳转**。
- 产品迁移时还有几处格式变化：Lemon Squeezy 的 variant 在 Stripe 里会变成独立产品；描述里的 HTML 会转换且可能出错，超过 500 字符会被截断；每个产品只迁前 8 张图；数字履约不会自动接上，须另接方案或自建 webhook。
- 费用会变：FAQ 写 Lemon Squeezy 为每笔 5% + 50¢（另有部分附加费）；Managed Payments 标准价为每笔 3.5%，**另加** Stripe 支付处理费；从 Lemon Squeezy 迁过去的商户，在安装迁移工具后可获 **1.5%** 的 Managed Payments 优惠费率，截至 **2027-12-01**（最早 12-02 安装即可起算），**标准处理费仍要另计**，订阅还可能产生 Stripe Billing 费用。和 Lemon Squeezy 一样，Managed Payments 在覆盖范围内代算、代收、代缴间接税；若改迁**非** Merchant of Record 的服务商，税务合规责任会回到商家自己身上。
- 顾客侧也会变：至少提前 **14 天**收到迁移通知；账单描述从 `LEMSQZY*` 店铺标识改为 `LINK.COM*` 加你的 statement descriptor；订阅和支付方式改到 Link（Stripe 面向消费者的平台）管理，而不再是 Lemon Squeezy Customer Portal；下载和许可证走你接好的履约方案。

与 `s25`（Stripe 订阅暂停）、`s30`（Radar 续费筛查计费）不同：本条只覆盖 **仍在 Lemon Squeezy 上收款、必须在 03-31 前迁走** 的店铺，不覆盖已经完全在 Stripe 上运行、与这次关停无关的订阅产品。

## 目标客户

正在用 Lemon Squeezy 卖 SaaS、软件、模板、电子书、课程或数字下载的独立开发者和一人公司，尤其是：结账里开了 PayPal、用官方店铺或文件 / 许可证交付、有联盟链接，或 webhook / 邮件序列里还写死 Lemon Squeezy 链接的人。已经不用 Lemon Squeezy、或只在 Stripe 上收款的店铺不是本条首批。本条也不覆盖「新注册一个 Lemon Squeezy 店铺」——11-16 起已经不能新开店。

## 一人怎么起步

两周 concierge（12-02 工具上线前先做盘点）：先发一份自查表（「你现在是否还在用 Lemon Squeezy 收款？有多少有效订阅，其中有多少是 PayPal / Cash App Pay / 印度发卡？有没有用官方店铺、文件或许可证交付、联盟分销？结账链接、邮件序列、应用内购买和 webhook 分别写在哪里？企业注册地是否在 Managed Payments 支持范围？产品是不是官方所说的合格数字商品？」）到独立开发者社群、数字商品群和 X 换 waitlist。对报名的 5–10 家店铺：只根据对方导出或只读展示的后台信息，对照官方迁移指南、对比页、FAQ 和 Stripe 资格页，列出「能否走 Managed Payments / 须改其他服务商」、迁不过去的订阅和功能、12-02 前应先关掉或替换的支付方式、以及链接与履约的替换清单。只出书面对照和分步核对表，不代登录、不代提交迁移、不代建法律实体、不代做税务登记，也不保证 Stripe 审核结果或订阅能否自动迁出。先收一次性体检费；12-02 工具上线后若要对照 Migration Hub 的资格报告再复查，另报价。

## 难度

中（官方把关停日期、不延期、工具上线日和迁前清单写清楚了；真正费时的是盘清支付方式与链接依赖，以及判断所在地 / 产品是否符合 Managed Payments 资格。PayPal 订阅和自建履约是硬缺口，不能当成「到时候点一下工具就结束」）

## 变现路径

一次性迁出体检（示意 $99–$299 / 店铺，按订阅量和集成复杂度分档）；12-02 工具上线后对照 Migration Hub 资格报告再复查，或陪跑顾客通知与换链清单（示意 $200–$500）；需要另接文件履约、许可证或联盟工具的，作为独立小改造单另报。不包含代提交迁移、代注册 Stripe 或 Atlas、代做税务登记，也不保证资格审核或订阅迁移结果。

## 注意的坑

不要写成「所有 Lemon Squeezy 商户都能一键迁到 Stripe」：官方要求对照 Managed Payments 资格页核对企业所在地、产品类型和客户国家，这三份名单不是同一份；不符合的须改迁其他服务商，且只有卡支付订阅才能迁到其他服务商。不要把 1.5% 优惠费率写成「全包价」——官方写明还要另计 Stripe 支付处理费，订阅还可能有 Billing 费用。不要默认保留 PayPal：Managed Payments 目前不支持，PayPal 订阅必须让顾客用受支持方式重新订阅；官方建议现在就从 Lemon Squeezy 结账里拿掉 PayPal，以免继续新增迁不走的订阅。不要以为旧链接会自动跳转；也不要假定文件、许可证、店铺和联盟会跟着过去。不要把「1 月中」写成平台强制日，那只是官方建议的最晚启动时点，硬截止仍是 03-31。不要把 Stripe Atlas 说成默认方案，官方只是提到「可能是一个选项」，并要求先咨询税务和法律顾问。不要和已经在 Stripe 上的暂停挽留（s25）或 Radar 计费（s30）混成同一份交付。完成交易的收入在账户状态正常时会全额打款，但要提醒客户核对待打款账户，并在 03-31 失去后台访问前下载税务与订单记录（税务文件走原打款账户，如 Stripe Express、PayPal 或 Wise）。你不是律师或税务顾问，也不代表 Lemon Squeezy 或 Stripe；不代登录，不保证审核或迁移结果。价格只是示意，需自行验证。

## 来源线索

- [Lemon Squeezy 官方迁移指南：Lemon Squeezy is winding down（03-31 停止处理交易含续费且不延期；11-16 已停新注册；12-02 迁移工具上线；建议不晚于 1 月中启动；给出迁前清单与能力缺口）](https://docs.lemonsqueezy.com/migration)
- [Lemon Squeezy 官方 FAQ：关停与迁移常见问题（4–8 周周期、工具能力、PayPal / Cash App Pay / 印度发卡、链接不自动跳转、费率与税务、资格与改迁其他服务商）](https://docs.lemonsqueezy.com/migration/faq)
- [Lemon Squeezy 官方对比页：Comparing Lemon Squeezy and Stripe Managed Payments（店铺 / 履约 / 联盟 / 邮件营销缺口，支付方式与费率，顾客门户与账单描述变化）](https://docs.lemonsqueezy.com/migration/comparison)
- [Stripe 文档：Managed Payments eligibility（企业所在地、客户国家与合格数字商品类型，须按此页核对，不得自行推定）](https://docs.stripe.com/payments/managed-payments/eligibility)
- [Stripe 文档：Managed Payments 总览](https://docs.stripe.com/payments/managed-payments)
- 相关但独立：[s25 Stripe 订阅暂停留存就绪体检](s25-stripe-pause-retention-readiness.md)、[s30 Stripe Radar 续费筛查计费就绪体检](s30-stripe-radar-renewal-cost-readiness.md)
