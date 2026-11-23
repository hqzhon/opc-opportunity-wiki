# Shopify 店面前端网络访问声明就绪体检（12-01 拒发版与提交 × 2027-01-01 下架 × 须声明 allowed_sources）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 技术 |
| 优先 | |
| 更新 | 2026-11-23 |

## 一句话

帮在店面运行代码的 Shopify 公开 App，以及装到客户店上的自定义 App 开发者，在 **2026-12-01** 前核对 `shopify.app.toml` 是否已声明 `[network_access]` 的 `allowed_sources`：官方 11-19 Changelog 写明，到期未声明的公开 App **会被拒绝发版和 App Store 提交**，商家后台会出现警告；**2027-01-01** 起公开 App 可能被下架并禁止新安装，外部安装的自定义 App 则是**漏掉一个，就会连带拦下你往外部店铺的全部新安装**。先出一份「在范围内已声明 / 在范围内未声明 / 不在本条范围」分数卡，再决定要不要另报价补声明并在开发店测过。

## 为什么现在

- Shopify 开发者 Changelog（**2026-11-19**）：在线商店上运行代码的 App，必须在 `shopify.app.toml` 的 `[network_access]` 里声明 `allowed_sources`。官方现行 [About app security](https://shopify.dev/docs/apps/build/security) 的 Upcoming security deadlines 表写了同一组日期。
- **公开 App**：
  - **2026-12-01**：拒绝发版和 App Store 提交；商家在后台看到警告。已发布的旧版本暂时还能运行。
  - **2027-01-01**：从 App Store 下架并禁止新安装。已有安装暂时照常。
- **装在本组织以外店铺上的自定义 App**：
  - **2026-12-01**：拒绝发版。
  - **2027-01-01**：已装到外部店铺、且属于本条范围的 App 也必须声明；**直到全部声明完，你都不能再往其他外部店铺安装自己的任何 App**。
- 现在离 12-01 大约一周。声明本身可能只是改 toml 再发一版，但要先判断 App 是否在范围内，再把店面实际请求的外部源逐条列全，并在「Network access testing」预览开发店里测过——漏源、格式不对或只在主题预览里点一下，都可能发版失败或测不准。
- 这不是所有 Shopify App 的下架令，也不是商家自己要改的店铺设置。只写内容（metafield、菜单、商品）、只有结账 UI 扩展而没有下面这些能力、只装在本组织店铺里的自定义 App、商家在 Admin / Dev Dashboard 自建的 App，以及默认严格沙箱里的 web pixel，都不在本条范围。

与 s37 / s47（IP 白名单）不同：那两条管的是 App 调用 **Admin API** 时请求从哪些 IP / ASN 出来；本条管的是 App 在**店面**上会从哪些外部服务器加载代码或发请求。与 s33（过期离线令牌）也不同。

## 目标客户

在 Shopify App Store 上架、并且会在在线商店运行代码的公开 App 开发者；以及把自定义 App 装到客户（本组织以外）店铺上的 Partner / 小工作室。尤其是用了下列任一能力、但 toml 里还没有 `allowed_sources` 的人：主题 App 扩展的 block 或 app embed、店面 script tags、App proxy、`write_themes` 权限、带 `write_open_pixels` 的 web pixel。只做后台同步、不碰店面的工具，以及只装在自己组织店铺里的自定义 App，不是本条首批。

## 一人怎么起步

两周 concierge：先发一份公开自查表（「你的 App 是公开还是装到客户店的自定义 App？有没有主题扩展 / script tag / App proxy / 写主题 / 开放像素？toml 里有没有 `[network_access]`？`allowed_sources` 是空数组还是已列域名？」）到 Shopify 开发者社区、r/shopifyDev 和 X 上的 Shopify app 圈换 waitlist。对报名的 5–10 个 App：只根据对方演示、toml 和只读材料，判断是否在官方范围内；若在范围内，对照店面实际加载 / 请求的外部源，标出未声明、格式不符（须为不带路径和尾斜杠的 HTTPS origin），或把 Shopify 自己提供的资源（主题扩展 `assets`、App proxy 网址）误写进去的项。交付分数卡 + 最小声明清单（含「没有任何外部源时应写成 `allowed_sources = []`」，空数组也算已声明；`allowed_navigation_hosts` 是可选项）。需要的话，指导对方在开启 Network access testing 预览的开发店、用商店的 `myshopify.com` 地址测试（不要只在主题编辑器预览或 CLI 的 127.0.0.1 预览里点一下，那里不会加上 Content-Security-Policy）。只出书面对照和一份可粘贴的 toml 片段，不代发布生产版本，也不保证审核结果。先收一次性体检费；代为补声明、在开发店回归或跟一次发版，作为独立单另报。

## 难度

中（官方把适用范围、截止日和「空数组也算声明」写清楚了；真正费时间的是盘点店面所有外部源，并在正确的预览环境里看 CSP 警告。发版前格式校验失败、或漏了 Google Fonts 这类要同时声明 `fonts.googleapis.com` 和 `fonts.gstatic.com` 的源，都是常见坑。完整发版和回归仍应由开发者本人确认）

## 变现路径

一次性网络访问声明就绪体检（示意 $99–$299 / App）；需要补 toml、在开发店测过并协助发版的固定价另报（示意 $300–$800，视店面入口数量和第三方源多少）；临近 12-01 或 01-01 的复查可另报价。不包含代提交 App Store 审核，也不保证能保住上架或外部安装能力。

## 注意的坑

不要写成「所有 Shopify App 或所有商家必须在 12-01 前改 toml」：范围是在店面运行代码的公开 App，以及装到本组织以外店铺、且具备官方点名能力的自定义 App。不要和 s37 / s47 的 IP 白名单混成同一份交付，那是 Admin API 出口，不是店面加载源。不要以为「支持一下 network_access」或只填 `allowed_navigation_hosts` 就算合规：12-01 起要查的是 `allowed_sources`；没有外部源也必须显式写成空数组。不要在主题预览里测试就宣布通过。不要把结账 UI 扩展自己的 `network_access` capability（写在 `shopify.extension.toml`）当成已经满足本条。自定义 App 一侧不要只看单个 App 有没有声明：01-01 起是漏一个连坐全部外部新安装，和 s47 的连坐逻辑类似、但对象是网络访问声明。你不是 Shopify 审核员，不代登录 Partner / Dev Dashboard 发生产版本，不保证审核或上架结果。价格只是示意，需自行验证。

## 来源线索

- [Shopify 开发者 Changelog：Network access declarations are now required for apps that run on the online store（2026-11-19；12-01 起拒发版与提交，2027-01-01 起公开 App 下架、自定义 App 外部安装连坐）](https://shopify.dev/changelog/posts/network-access-declarations-are-now-required-for-apps-that-run-on-the-online-store)
- [Shopify 文档：Declare your app's network access（谁必须声明、空数组算声明、如何测试与发版）](https://shopify.dev/docs/apps/build/security/storefront/declare-network-access)
- [Shopify 文档：About app security（Upcoming security deadlines 表，含公开 / 自定义店面 App 的 12-01 与 01-01）](https://shopify.dev/docs/apps/build/security)
- 相关但独立：[s37 Shopify 公开 App IP 白名单就绪体检](s37-shopify-ip-allowlist-readiness.md)、[s47 Shopify 自定义 App IP 白名单就绪体检](s47-shopify-custom-app-ip-allowlist-readiness.md)、[s33 Shopify 公开 App 过期离线令牌迁移体检](s33-shopify-expiring-offline-token-readiness.md)
