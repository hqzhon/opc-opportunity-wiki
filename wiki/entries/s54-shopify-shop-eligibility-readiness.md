# Shopify Shop 刊登资格更新体检（11-10 起非 Shopify Payments 店也可出现在 Shop × 全店资格已更新 × 未达标会被拿下）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 运营 |
| 优先 | |
| 更新 | 2026-11-16 |

## 一句话

帮没用 Shopify Payments 的独立站，以及可能被新资格条件挡在外面的店，核对能不能出现在 Shop、顾客是被带到自己网站结账还是可以在 Shop 里直接买，以及 Shop Campaigns 是不是仍然要先开通 Shopify Payments。

## 为什么现在

Shopify 官方 Changelog（**2026-11-10**）写了两处变化。第一，Shop **现在对不使用 Shopify Payments 的店开放**：以前只有用 Shopify Payments 的店才能出现在 Shop；现在只要满足资格要求，不论支付服务商是谁都可以出现在 Shop，并**可能**开始看到从 Shop app 和 Shop.com 转到自己网店的流量。第二，**所有店铺**的资格要求已更新：满足的会出现在 Shop，不满足的在改好之前不会出现。

这两件事要分开看。能出现在 Shop，不等于能在 Shop 里直接成交，更不等于能开 Shop Campaigns。官方写明：不用 Shopify Payments 的店可以出现在 Shop，但**没有资格**使用 Shop Campaigns；用 Shopify Payments 且满足更新后要求的店，才有 Shop Campaigns 资格。商家随时可以在后台 Shop 渠道查看资格状态，不合格时会看到要处理的项目。

帮助中心把要求分成两套。只满足「展示」要求时，顾客能在 Shop 浏览商品，但会被转到你的网店完成购买；两套都满足时，顾客可以不离开 Shop 就下单。展示要求包括：遵守服务条款和可接受使用政策、店铺计划有效、已填写业务信息、至少完成过一笔履约订单、已启用 Online Store 且不是私人模式、网店不仅限 B2B 顾客、未使用 Advanced Registration、B2B Login Access Management、Login to View Price、MagicPass Wholesale 等密码或年龄验证类应用（Locksmith 是例外：店仍会展示，被锁定的商品在 Shop 保持隐藏）。在 Shop 内直接销售还要加上：已启用 Shopify Payments、过去 90 天拒付率低于 5%（统计走 Shopify Payments 的交易）、至少有一件商品符合 Shop 的商品资格。

还有两个容易忽略的点。符合资格的店会被**自动加入** Shop，不必先安装 Shop 渠道才算合格；安装渠道主要是为了额外功能和设置。如果店已具备「在 Shop 内直接销售」的资格，即使还没安装渠道，也**仍可能**通过 Shop 接到订单。改完资格项之后，状态更新最多可能要 **48 小时**。帮助中心还注明：要求清单可能不经通知就变更，有些检查项不一定写在该页上——所以最终以后台 Shop 渠道显示的状态为准。

与 `s21`（Shop Promise 履约徽章）不同：本条管的是**能不能出现在 Shop、顾客在哪里结账、Campaigns 资格还在不在**，不是配送时效徽章。

## 目标客户

支付走 Stripe、PayPal 或其他非 Shopify Payments 服务商、以前认为自己进不了 Shop 的独立站；以及已经在 Shop 露过面、但可能因为新的资格条件（私人模式、仅 B2B、密码门禁应用、没填业务信息、还没有一笔已履约订单）被拿下来的店。已经用 Shopify Payments、后台显示完全合格、只想优化广告投放的店不是本条的首批；Shop Campaigns 要另看官方活动要求，不要把「能展示」当成「能投 Shop 广告」。

## 一人怎么起步

两周 concierge：先发一份公开自查表（「你现在用的是不是 Shopify Payments？后台 Shop 渠道此刻显示合格还是缺哪几项？顾客从 Shop 进来是在店内下单，还是被送到你自己的结账？你有没有在用密码或年龄验证类应用、私人模式或仅 B2B？」）到 Shopify 社区、r/shopify、跨境店主群和 X 换 waitlist。对报名的 5–10 家：先截下当前资格状态；按官方两套要求逐项核对（展示 vs 店内直售）；列出可在两周内改完的阻断项（业务信息、私人模式、不兼容应用、履约订单、拒付率）；改完后按 48 小时窗口复查状态；帮店主分开统计 Shop 推荐流量和实际成交，避免把「出现在 Shop」当成已经多卖了货。若店主主动问要不要改用 Shopify Payments 以换店内结账和 Campaigns 资格，只给对照清单，不替他做支付迁移。先收一次性体检费，资格波动较大的店可做月度复查。

## 难度

低（官方把两套要求和自查入口写清楚了；关键是分清「能展示 / 能店内成交 / 能开 Campaigns」三层，并且以后台状态为准，不要只对照帮助中心清单）

## 变现路径

一次性 Shop 资格体检（示意 $49–$149 / 店）；需要改设置、拆掉不兼容门禁或补业务信息的跟进（示意 $150–$400）；资格尚不稳定时的月度复查（示意 $19–$49 / 月）。可与 `s21`（Shop Promise）并列介绍，但条目和报价分开。

## 注意的坑

不要承诺「出现在 Shop 就会涨流量或涨销量」，官方只说「可能」开始看到推荐流量。不要把展示资格、店内直售和 Shop Campaigns 写成同一件事：不用 Shopify Payments 的店现在可以展示，但官方明确写了没有 Campaigns 资格。符合直售资格的店即使没装 Shop 渠道也可能接到 Shop 订单，不要只看渠道是否安装。帮助中心写明要求可能不经通知变更，且有些检查项不一定列在该页，必须以 Shop 渠道里的状态为准。改完后最多等 48 小时再下结论，不要当天反复改设置。你不是支付服务商的实施方，不代开 Shopify Payments、不保证拒付率或商品能否通过 Shop 审核。价格只是示意，需自行验证。

## 来源线索

- [Shopify Changelog：Updated eligibility requirements for Shop（2026-11-10，非 Shopify Payments 店也可展示；全店资格已更新）](https://changelog.shopify.com/posts/updated-eligibility-requirements-for-shop)
- [Shopify Help Center：Requirements to display and sell products on Shop（展示 vs 店内直售两套要求、自动加入、48 小时生效）](https://help.shopify.com/en/manual/online-sales-channels/shop/eligibility/requirements)
- 相关但独立：[s21 Shop Promise 就绪体检](s21-shop-promise-readiness.md)
