# Shopify 弃单恢复链接受保护顾客数据就绪体检（12-01 公开 App 须获准四字段 × 2027-01-01 自定义 App 须自助开通 × 未获准则 GraphQL 整查询失败）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 技术 |
| 优先 | |
| 更新 | 2026-11-23 |

## 一句话

帮会读取弃单恢复链接（`abandonedCheckoutUrl` / `abandoned_checkout_url`）的 Shopify 公开 App，以及在 Dev Dashboard 里维护的自定义 App 开发者，在各自截止日前核对是否已获准**全部四个**受保护顾客字段（姓名、邮箱、电话、地址）：官方 11-19 Changelog 写明，公开 App 从 **2026-12-01**、Partner 自定义 App 与商家在 Dev Dashboard 自建的 App 从 **2027-01-01** 起，未获准这四项再选取该字段时，GraphQL 列表查询会**整段返回空**，批量操作失败；REST 与 webhook 则**静默去掉**该字段，弃单邮件 / 短信里的恢复链接可能直接消失。先出一份「已获准四字段 / 只开了部分字段 / 仍在用该字段但未申请 / 已不用该字段 / Admin 自建因而不适用」分数卡，再决定要不要另报价协助申请或改查询。商家在 Shopify admin 里创建的 App，官方写明不受影响。

## 为什么现在

- Shopify 开发者 Changelog（**2026-11-19**，标记为 *Breaking API Change* 与 *Action required*）：弃单恢复 URL 会带上买家的姓名、邮箱、电话和地址并打开结账，因此读取 `AbandonedCheckout.abandonedCheckoutUrl` 或 REST 的 `abandoned_checkout_url`，必须获准全部四个受保护顾客字段（`read_customer_name`、`read_customer_email`、`read_customer_phone`、`read_customer_address`）。只获准其中几项不够。该要求适用于所有受支持的 Admin API 版本以及 `unstable`。
- **公开 App**：**2026-12-01** 起生效。须在 Dev Dashboard 申请这四个字段，并通过**数据保护审核**。官方写明审核**可能要几周**，要尽早提交。
- **Partner 自定义 App**（Partner 为特定店铺构建）和 **商家在 Dev Dashboard 自建的 App**：**2027-01-01** 起生效。可在 Dev Dashboard 自行开通这四个字段，**无需审核**。
- **在 Shopify admin 里创建的 App**：不受影响，不用做本条。
- 现在离公开 App 的 12-01 大约一周，而审核可能要几周，所以对仍在用恢复链接、但还没递交四字段申请的公开 App，应立刻核对状态，而不是等到截止日当天再交。开发店**不会**执行受保护顾客数据审批，那里看不到报错，不能当成已经过关。
- 这不是商家要改的店铺设置，也不是所有 Shopify App 的下架令。官方写的后果是接口取不到恢复链接（GraphQL 还会连累整次查询），没有写 App Store 下架。跟 s66（店面网络访问声明）、s33（过期离线令牌）、s47（自定义 App IP 白名单）、s65（退货 / 订阅 App 买家登录）是不同切口。

## 目标客户

在 Shopify App Store 上架、会发弃单挽回邮件 / 短信 / 直邮，或在代码、Webhook 里读取恢复链接的公开 App 开发者；以及在 Dev Dashboard 维护、同样会读该链接的 Partner 自定义 App / 商家自建 App 开发者。只做后台同步、确认从不读取该字段的工具，以及在 Shopify admin 里创建的 App，不是本条首批——但 REST 默认就会返回该字段，不用它的集成也要能接受字段突然消失。

## 一人怎么起步

两周 concierge：先发一份公开自查表（「你的 App 是公开、Partner 自定义，还是 Dev Dashboard / Admin 自建？有没有读 `abandonedCheckoutUrl` 或 `abandoned_checkout_url`？GraphQL、REST 的 `checkouts.json`、以及 `checkouts/create` / `checkouts/update` webhook 里有没有用到？Dev Dashboard 里受保护顾客数据是四个字段都已获准，还是只开了一部分？」）到 Shopify 开发者社区、r/shopifyDev 和 X 上的 Shopify app 圈换 waitlist。对报名的 5–10 个 App：只根据对方演示、查询/Webhook 样例和只读材料，标出是否在范围内、四字段审批状态、以及 GraphQL 查询会不会因为选了该字段而整段变空。交付分数卡 + 最小行动清单：公开 App 写出四个字段的申请理由和数据保护说明草稿，提醒对方官方审核可能要几周；自定义 App 写清在 Settings > Access requests > Protected customer data > Manage 里自行勾选四个字段的步骤；若其实不需要恢复链接，则列出应从 GraphQL 查询和批量操作里删掉的字段，并注明 REST / webhook 要能处理字段缺失。只出书面对照和申请/改查询草稿，不代登录 Dev Dashboard 提交审核或改生产配置，也不保证审核结果。先收一次性体检费；代写申请材料、改查询并做回归，作为独立单另报。

## 难度

中（官方把适用范围、截止日和「四个字段必须齐」写清楚了；真正费时间的是盘点 GraphQL / REST / webhook / 批量操作里所有读取点，以及为公开 App 写齐数据保护说明。开发店测不通这一条，截止日前必须看 Dev Dashboard 里的真实审批状态。完整申请和发版仍应由开发者本人确认）

## 变现路径

一次性弃单恢复链接就绪体检（示意 $99–$299 / App）；需要补齐四字段申请材料、改查询并做回归的固定价另报（示意 $300–$800，视集成点和是否走公开 App 审核而定）；临近 12-01 或 01-01 的复查可另报价。不包含代提交数据保护审核，也不保证能获准或保住挽回链接。

## 注意的坑

不要写成「所有 Shopify App 或所有商家必须在 12-01 前申请受保护顾客数据」：范围是会读取弃单恢复链接的公开 App，以及在 Dev Dashboard 里维护的自定义 / 商家自建 App；Admin 里创建的 App 官方写明不受影响。不要把「申请了受保护顾客数据」或只获准其中一两个字段当成已经过关——必须是姓名、邮箱、电话、地址四个都获准。不要只看 GraphQL 报 `ACCESS_DENIED`：列表查询（如 `abandonedCheckouts`）会变成 `data: null`，丢掉的是整段弃单数据，不只是 URL；`node` / `nodes` 查找会返回 `null`；选了该字段的批量操作会在重试数分钟后失败。不要指望 REST 或 webhook 会报错：到期后 `abandoned_checkout_url` 会从 `GET /admin/api/{version}/checkouts.json` 以及 `checkouts/create`、`checkouts/update` 载荷里直接消失，代码如果默认字段一定存在，挽回邮件 / 短信可能静默变成无链接。不要只在开发店里测就宣布通过。不要和 s66 的店面网络访问声明、s33 的过期令牌、s47 的 IP 白名单或 s65 的 Customer Account API 登录混成同一份交付。你不是 Shopify 审核员，不代登录 Partner / Dev Dashboard 提交生产配置或审核，不保证获准结果。价格只是示意，需自行验证。

## 来源线索

- [Shopify 开发者 Changelog：abandonedCheckoutUrl now requires level 2 protected customer data access（2026-11-19；公开 App 12-01、自定义 App 2027-01-01；未获准则 GraphQL 整查询失败，REST / webhook 静默去掉字段）](https://shopify.dev/changelog/posts/abandonedcheckouturl-now-requires-level-2-protected-customer-data-access)
- [Shopify 文档：Work with protected customer data（Level 2 字段范围、公开 App 须审核、在 Dev Dashboard 申请的步骤）](https://shopify.dev/docs/apps/launch/protected-customer-data)
- [Shopify 开发者博客：App security updates: IP allowlist due tomorrow（2026-11-19；再次写明弃单恢复 URL 的 12-01 / 01-01 要求）](https://shopify.dev/changelog/blog/app-security-updates-ip-allowlist-due-tomorrow)
- 相关但独立：[s66 Shopify 店面前端网络访问声明就绪体检](s66-shopify-network-access-declaration-readiness.md)、[s33 Shopify 公开 App 过期离线令牌迁移体检](s33-shopify-expiring-offline-token-readiness.md)、[s47 Shopify 自定义 App IP 白名单就绪体检](s47-shopify-custom-app-ip-allowlist-readiness.md)、[s65 Shopify 退货与订阅 App 买家登录就绪体检](s65-shopify-bfs-customer-account-api-readiness.md)
