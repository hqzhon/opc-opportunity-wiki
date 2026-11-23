# Shopify 店面 Script Tag 停用迁移体检（10-01 已禁新建 × 2027-03-01 停止注入 × 须改为 App embed 或像素）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 技术 |
| 优先 | |
| 更新 | 2026-11-23 |

## 一句话

帮仍在用店面 script tag 往店铺注入 JavaScript 的 Shopify App 开发者，在 **2027-03-01** 前把现有标签迁走：只做分析 / 转化追踪的改用 web pixel，其他店面脚本改成主题 App 扩展里的 **app embed block**，并确认已在**已发布主题**上打开。官方 8-24 已宣布，**2026-10-01** 起已不能再创建或更新 script tag（锁旧 API 版本也无效）；现有标签还能跑到 3-01，到期 Shopify **不再往店面注入**，依赖它的功能会直接停。先出一份「还有哪些标签在跑 / 替代方案选哪条 / 已发布主题有没有打开 embed」分数卡，再决定要不要另报价做迁移。

## 为什么现在

- Shopify 开发者 Changelog（**2026-08-24**，标记为 *Action required*）与现行 [Storefront script tags](https://shopify.dev/docs/apps/build/online-store/script-tag-deprecation/storefront) 文档写明同一条时间表：
  - **2026-10-01**（已过）：`scriptTagCreate` / `scriptTagUpdate` 在所有 API 版本返回错误，REST 的 `ScriptTag` `POST` / `PUT` 同样失败。已有标签暂时继续运行；读取和删除接口仍可用，方便盘点和清理。
  - **2027-03-01**：Shopify 停止向店面注入 script tag，脚本不再加载，依赖它的功能会停。残留记录届时没有效果，不必为了「合规」再删一遍。
- 过了 10-01，还没备好替代方案的 App，**新安装已经补不上 script tag**，功能会缺一块；老安装则只剩到 3-01 的窗口。官方建议在替代方案确认跑起来之前，不要删掉旧标签，否则会出现「两头都没有」的空窗；两者同时跑又可能让统计翻倍或界面出现两次。
- 本条针对 `display_scope` 为 `online_store` 的 script tag。订单状态页（`order_status`）是更早、单独的停用，不要和本条截止日混用。官方一度计划给仍用 script tag 的新安装展示横幅，后来决定暂时不展示，所以不能靠商家有没有看到警告来判断自己还要不要迁。

与 s66（须在 toml 声明 `allowed_sources`）可以一起看：迁到主题 App 扩展后，店面若还要请求外部 API / CDN，仍须按 s66 声明；但本条的截止日和交付物是「把 script tag 换掉」，不是改 toml。

## 目标客户

仍在用 `display_scope = online_store` 的 script tag 往店面加载脚本的公开 App，以及 Partner 给客户店做的自定义 App。尤其是 10-01 前就挂在老店铺上、还没上 app embed 或 web pixel 的一人维护工具（评论、弹窗、礼品选项、追踪脚本等）。商家在 Admin 里自建的自定义 App **不能使用 App 扩展或 web pixel**，不是同一套迁法（要把脚本挪进主题，优先用自定义 Liquid；这会让主题离开自动升级路径，只在无法用扩展时才做）。第三方让商家「建一个 App、把 token 贴进后台」的服务，需要对方先发布真正的扩展或像素 App，不是本条能单独收尾的对象。

## 一人怎么起步

两周 concierge：先发一份公开自查表（「你的 App 现在还在创建或依赖 storefront script tag 吗？10-01 之后新安装功能缺了吗？替代方案是 app embed 还是 web pixel？已发布主题上打开了吗？」）到 Shopify 开发者社区、r/shopifyDev 和 X 上的 Shopify app 圈换 waitlist。对报名的 5–10 个 App：用该 App 已持有的店铺令牌只读查询 `scriptTags`（多个客户店要逐个查），标出 `online_store` 范围的存量标签、脚本用途（店面 UI 还是纯分析），以及有没有已上线的 app embed / web pixel。交付分数卡 + 最小迁移清单：UI 类走主题 App 扩展的 app embed（并用官方深链把商家带到主题编辑器打开）；纯分析 / 转化走 web pixel（商家装订或更新时授权即可，不必在主题编辑器里再开一次）；确认已发布主题已激活后，再用 `scriptTagDelete` 删旧标签。只出书面对照和迁移步骤，不代发布生产版本，也不代登录商家主题编辑器。先收一次性体检费；需要代做扩展或像素、跟商家完成激活的，作为独立开发单另报。

## 难度

中偏高（官方时间表、替代方案和「先确认再删除」写得很清楚；查询存量标签也不难。真正费功夫的是把旧脚本改成 app embed 或 web pixel，并确认每家店的**已发布主题**都已打开。主题一换，embed 不会自动带到新主题上。Admin 自建 App 没有扩展可用，只能改主题，要单独说明风险。完整迁移不要写成「保证 3-01 前改完且零中断」）

## 变现路径

一次性 script tag 存量盘点与迁移路径体检（示意 $99–$299 / App）；改为 app embed 或 web pixel 的固定价开发另报（示意 $500–$2,000，视脚本复杂度和要跟进的店铺数）；帮客户确认已发布主题激活、再删旧标签的复查可另报价。不包含代提交审核，也不保证迁移后功能完全一致。

## 注意的坑

不要写成「所有 Shopify App 必须在 3-01 前做主题扩展」：范围是仍在用店面 script tag 的 App；纯分析脚本应优先 web pixel，而不是一律做 embed。不要和订单状态页 script tag 的旧截止日混用。不要在替代方案还没被已发布主题激活时就删旧标签；也不要长期让两者并行，以免统计翻倍或 UI 出现两次。不要以为主题编辑器里打开一次就永远有效：app embed 是按主题启用的，店铺改用新主题后要再确认。不要把 s66 的网络访问声明当成已经完成了本条迁移。Admin 自建 App 不要承诺「做成主题扩展」——官方写明它用不了扩展和像素，只能把脚本放进主题，且脚本会在卸载 App 后留在主题里。你不是 Shopify 审核员，不代登录 Partner / Dev Dashboard 或商家主题编辑器，不保证审核或上架结果。价格只是示意，需自行验证。

## 来源线索

- [Shopify 开发者 Changelog：Script tags are deprecated and will stop running on March 1, 2027（2026-08-24；10-01 起禁新建 / 更新，2027-03-01 停止向店面注入）](https://shopify.dev/changelog/posts/online-store-script-tags-deprecation)
- [Shopify 文档：Storefront script tags（时间表、如何盘点、选 app embed 还是 web pixel、先激活再删除）](https://shopify.dev/docs/apps/build/online-store/script-tag-deprecation/storefront)
- [Shopify 文档：Use theme app extensions instead of script tags (required)](https://shopify.dev/docs/apps/build/security/storefront/use-theme-app-extensions-instead-of-script-tags)
- [Shopify 文档：About app security（Upcoming security deadlines 表，2027-03-01 全部 App 停用 script tag）](https://shopify.dev/docs/apps/build/security)
- 相关但独立：[s66 Shopify 店面前端网络访问声明就绪体检](s66-shopify-network-access-declaration-readiness.md)
