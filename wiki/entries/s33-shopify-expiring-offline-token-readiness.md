# Shopify 公开 App 过期离线令牌迁移体检（01-01 下架 × 01-15 商家警告 × 04-01 返回 403）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-11-04 |

## 一句话

帮在 Shopify App Store 上架公开 App 的独立开发者，在 **2027-01-01** 前把「永不过期的离线访问令牌」迁到「会过期 + 刷新令牌」：盘点每个 App 的拿令牌方式（官方模板 / 自己做 token exchange / 授权码流程），给存量店铺跑一次无需商家参与的直接迁移，补好刷新、403 和 401 处理——输出「已迁移 / 只差存量店铺 / 完全没动」分数卡和一份可直接合并的改动。

## 为什么现在

Shopify 在 2026-10-27 的开发者 Changelog 里写明：所有调用 Admin API 的公开 App 必须在 **2027-01-01** 前改用会过期的离线访问令牌，否则当天被**下架并禁止新安装**（已有安装暂时照常）；**01-15** 起用到它的商家会在后台看到服务可能中断的警告；**04-01** 起用旧令牌发的 GraphQL Admin API 请求直接返回 HTTP 403，商家要重新授权才能继续用。Shopify 还特意说明后面两个日期是留给商家的，不是给开发者的宽限期。

很多一人维护的老 App 是几年前按授权码流程手写的，存着从不过期的令牌，也没有刷新逻辑；只做 webhook、Flow 动作、App Proxy 的后台型 App 甚至没有用户会话来触发换新。迁移本身有坑：直接迁移会**永久作废旧令牌**，响应丢了只有 7 天内重试能找回。假日季是这些 App 最忙、最不敢动线上的时候，留给开发者的时间实际不到两个月。同一批更新还推出了客户端凭据找回、IP 白名单和 `shopify app security check`，可以顺手打包成一次「上架安全体检」。

## 目标客户

在 Shopify App Store 有公开 App、由 1–3 人维护的开发者或小工作室：尤其是 2026 年 4 月前创建、没用官方 Remix / React Router 模板、自己写 OAuth 的 App，以及只靠 webhook 或后台任务运行的工具型 App（库存同步、导单、发票、标签打印等）。自定义 App 和商家自建 App 不受影响，不是客户。

## 一人怎么起步

两周 concierge：先发一张公开自查清单（「你的 App 走哪种拿令牌方式？存量店铺有没有迁？丢了 refresh token 怎么办？」）到 Shopify 开发者社区、r/shopifyDev、Indie Hackers 和 X 上的 Shopify app dev 圈换 waitlist；也可以在 App Store 里按「上架多年、评价数中等、更新稀少」筛出候选，礼貌私信。对报名的 5–10 个 App，只读看代码和令牌存储表：判断属于模板、token exchange 还是授权码流程，存量店铺有多少还是旧令牌。交付一个 PR：开 `expiring=1` 或模板 flag，加刷新任务与 403/401 处理，再写一个分批、可重试、先在开发店验证的存量迁移脚本（保存返回的令牌对和过期时间后再丢旧令牌）。先收一次性迁移费，之后延伸为「令牌健康监控 + 平台变更提醒」订阅。

## 难度

中（要懂 Shopify OAuth、token exchange、令牌存储与并发刷新；存量迁移是不可逆操作，需要严格的备份、分批和日志）

## 变现路径

一次性迁移审计（示意 $99–$299）；固定价迁移项目（示意 $500–$1,500，含存量店铺迁移脚本与错误处理）；之后做令牌健康监控与 Shopify 平台变更月报订阅（示意 $29–$79 / 月）。可与 `s3`（平台伴生 App）、`s30`（Stripe Radar 计费）、`s32`（Google Play 拒付）组成「开发者平台合规」系列，但条目分开。

## 注意的坑

直接迁移会永久作废旧令牌：必须先把返回的 access token、refresh token 和两个过期时间落库，再丢旧令牌；响应丢失只能在 7 天内用原令牌重试找回，且一旦刷新过就不能再找回。刷新令牌用一次就换新，多个进程并发刷新容易互相作废，要加锁。403 可能是缺权限而不是旧令牌，要匹配 Shopify 给出的那句报错再决定是否重新授权；刷新令牌失效会返回 401，只能让商家重新打开 App。只动客户授权的代码与开发店，生产迁移由开发者本人点头、分批执行。别承诺「保证不被下架」，以 Shopify 官方迁移指南和后台提示为准；客户端凭据找回、IP 白名单等是可选加固，不是这次截止日的硬要求。

## 来源线索

- [Shopify Changelog: Migrate to expiring offline access tokens before January 1, 2027](https://shopify.dev/changelog/posts/migrate-to-expiring-offline-access-tokens-before-january-2027)
- [Shopify Changelog: Security update: Offline token dates, new security features（2026-10-27）](https://shopify.dev/changelog/blog/app-security-updates-october-2026)
- [Shopify Dev Docs: Migrate to expiring offline access tokens（直接迁移、7 天找回、403/401 处理）](https://shopify.dev/docs/apps/build/authentication-authorization/migrate-to-expiring-offline-access-tokens)
