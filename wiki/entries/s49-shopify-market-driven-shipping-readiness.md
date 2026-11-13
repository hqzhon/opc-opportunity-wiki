# Shopify 按市场配运费迁移体检（自动迁移进行中 × 多费率改取最高 × 2027-07-01 不可退出）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | |
| 更新 | 2026-11-13 |

## 一句话

帮 Shopify 商家和给商家写自定义 App 的开发者，在店铺被自动迁到「按市场配运费」（market-driven shipping / shipping options by market）之前或刚迁完时，把运费结果对一遍：导出旧的运费档案、区域和费率，按新规则（同一运费选项内多条费率命中时**只收最高那条**，而不是相加；拆单发货强制开启）重算典型购物车的运费，找出少收或多收的组合；再查店里有没有脚本、ERP 或自定义 App 还在读写商家的 delivery profile，迁移后这些写入会「成功但不生效」。

## 为什么现在

Shopify 官方 Dev 博客「The next generation of Shopify fulfillment is coming」与 Help Center 写明：

- **时间线**：2026-10-01 起商家可主动切换、新店默认就是新系统；2026-10-01 至 2027-07-01 期间 Shopify 分批**自动迁移**存量店（用了运费类 App 的店，等 App 兼容后再迁）；**2027-07-01 起所有店都用新系统，不能退出**。
- **费率合并规则变了**：旧系统一个购物车命中多条费率时把它们相加；新系统同一运费选项内只收最高的一条，命中多个运费选项时才相加。按商品分档案收运费的店（比如超大件另收费），迁移后可能少收运费。
- **拆单发货强制开启**：迁移后所有店都开拆单，结账页会显示预计包裹数，原来关掉拆单的店也会被打开。
- **跨国区域会被拆开**：一个旧运费区域里如果含多个国家的州/省，迁移时会为每个国家各建一个市场。
- **API 层的坑**：Shopify Dev Changelog（2026-07-01）把商家自有 delivery profile 相关的 GraphQL 接口（`deliveryProfiles`、`deliveryProfileUpdate` 等）对已迁移店标为弃用：读到的可能是过期快照，**写入可能不报错却不改变实际运费**。自研脚本、小众 ERP、自定义 App 改运费的逻辑会静默失效。2026-10-01 起，不兼容的 App 在新安装时会显示警告。

现在正是 BFCM 与年底旺季，有店在迁移窗口里被切过去而没人对过运费，问题会直接体现在毛利和客诉上。官方说「多数商家无需操作」，但这句话对按商品分档案、多仓、自定义运费逻辑的店不成立，这就是一人服务的切口。

与 `s18`（Managed Markets 保价一口价运费决策）、`s47`（自定义 App IP 白名单）不同：本条只管 **运费配置从档案迁到市场后的金额差异与 API 失效**。

## 目标客户

用了多个运费档案（超大件、冷链、易碎品另收费）、多仓发货或多国市场的 Shopify 中小独立站；给商家维护自定义 App、运费脚本或 ERP 对接的自由开发者与小代运营团队。

## 一人怎么起步

两周 concierge：先发一份公开自查清单（「你的店是旧的运费档案还是已经按市场配置？有几个运费档案？同一单里普通件 + 超大件现在收多少、迁移后收多少？有没有脚本或 App 改运费？」），发到 r/shopify、Shopify Community、X 和国内独立站群换 waitlist。对报名的 5–10 家：在 Settings > Shipping and delivery 确认所处系统，导出现有费率，挑 10–20 个典型购物车按新规则重算，出一张「少收/多收运费 × 建议改法（新增运费选项或调整费率条件）」表；对有开发的店，搜代码里的 delivery profile 读写调用，列出要改到 Markets API 或 App 自有档案的位置。可以先用 Shopify 的 feature preview 开发店复现。交付后延伸为迁移后两周的运费与订单抽查。

## 难度

中（运费重算靠表格即可；API 排查要会读 Shopify GraphQL）

## 变现路径

运费迁移对账（示意 $99–$249 / 店）；自定义 App / 脚本 delivery profile 调用排查与改造报价（示意 $299 起）；迁移后两周抽查或按月运费巡检（示意 $49 / 月）。

## 注意的坑

以 Shopify 官方 Help Center 与 shopify.dev 说明为准，迁移节奏因店而异，不要承诺迁移日期，也不要把「可能少收运费」说成必然。迁移后有一段可切回旧系统的窗口，具体以店铺后台为准。只用商家授权的协作者或只读权限，不索要密码。价格只是示意，需自行验证。

## 来源线索

- [Shopify Dev 博客：The next generation of Shopify fulfillment is coming（市场驱动运费时间线与 App 须改造）](https://shopify.dev/changelog/blog/next-gen-fulfillment)
- [Shopify Help Center：Upgrading from shipping profiles to shipping options by market（费率合并、拆单、区域拆分对比）](https://help.shopify.com/en/manual/fulfillment/setup/shipping-options/whats-changing-with-shipping)
- [Shopify Dev Changelog（2026-07-01）：Merchant-owned delivery profile APIs are deprecated for market-driven shipping](https://shopify.dev/changelog/posts/merchant-owned-delivery-profile-apis-are-deprecated-for-market-driven-shipping)
- [Shopify 博客：Shopify's new fulfillment: How to prepare for what's coming in 2027](https://www.shopify.com/enterprise/blog/shopify-fulfillment-2027)
- 相关但独立：[s18 Managed Markets 保价一口价运费就绪体检](s18-mm-flat-rate-shipping.md)、[s47 Shopify 自定义 App IP 白名单就绪体检](s47-shopify-custom-app-ip-allowlist-readiness.md)
