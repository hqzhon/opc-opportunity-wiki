# Apple 订阅多席位就绪体检（10-22 默认开启 × 关错开关会停续费 × 冬季群组购买）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-11-04 |

## 一句话

帮在 App Store 卖自动续期订阅的独立开发者理清 Apple 新的「多席位购买」：自己的订阅是否已被默认挂上 Apple Business / Apple School Manager、要不要设批量阶梯价、哪个开关一关就会让机构客户下次续费直接取消，以及冬季上线的 C 端群组购买要提前做哪些 StoreKit 2 准备——输出「保持开启并设阶梯价 / 只关多席位 / 暂不卖机构 / 先迁 StoreKit 2」分数卡。

## 为什么现在

**2026-10-22** 起，企业与学校可以通过 Apple Business、Apple School Manager 一次性买多个订阅席位，再用自己的设备管理分配、随时增减。Apple 写明这项多席位购买在 App Store Connect 里**默认开启**（除非你改过设置）；只有 2026-09-14 前创建、且没用 StoreKit 2 或开了家人共享的订阅才默认关闭。也就是说，大量用 StoreKit 2 的一人 App，没做任何决定就已经在机构渠道上架了。

两个开关后果不同：**关闭多席位**只停新机构销售，已有机构客户继续续费；而**把 Apple Business / School Manager 从可售渠道移除**，已有机构订阅会在下一次续费后被取消（且只有 Account Holder 能改）。定价上，默认每个席位按原价卖，可另设最多 5 档批量阶梯价；多席位涨价时，群组总价涨超 50% 需要购买者同意，不同意整组到期。另外 **2026 年 11 月**起可在沙盒测试 C 端「群组购买」，今冬上线 App Store，开发者要自己做选席位数的界面、处理邀请。很多做效率工具、教育、团队类订阅的一人开发者既不知道已经被默认开启，也没想过机构客户怎么定价、怎么在报表里识别。

## 目标客户

在 App Store 卖自动续期订阅、产品有团队/课堂/家庭共用场景的独立开发者与小团队：效率工具、笔记/任务、教育与学习、开发者工具、健身与户外等；尤其还在用旧 StoreKit（原版 IAP）、或开了家人共享不确定怎么办的 App。

## 一人怎么起步

两周 concierge：先做一张公开自查表（「你的订阅是否已被默认挂上 Apple Business？」+ 两个开关的后果对照）发到 Indie Hackers、r/iOSProgramming、X 的 indie dev 圈换 waitlist → 对报名的 5–10 个 App，由开发者截图或只读分享 App Store Connect 的 Purchase Options 与价格页，逐个订阅判断：是否适合机构渠道、是否该设阶梯价（给出 1–20 / 21–40 / 41+ 档的示意价与毛利测算）、哪些订阅应该只关多席位而不要移除渠道 → 再给一份群组购买的 StoreKit 2 准备清单（选席位数 UI、邀请链接由 Apple 管还是自建、服务端群组成员查询）。先收一次性审计费，验证后可延伸为「机构席位报表与续费提醒」小工具。

## 难度

低到中（规则写在 App Store Connect 帮助页与 WWDC26 session 里；需要懂 StoreKit 2 与订阅组；机构购买在销售报表与分析工具中如何呈现 Apple 尚未说明，需要按客户实际数据核对，不能拍脑袋）

## 变现路径

一次性订阅多席位审计（示意 $99–$299，按订阅数）；StoreKit 2 迁移 / 群组购买接入的固定价小项目；之后做机构席位与续费监测的月订阅（示意 $19–$49）。可与 `s2`（失败催收）、`s25`（暂停留存）一起做成「订阅收入体检」系列，但条目分开。

## 注意的坑

别劝所有人都关掉：对有团队场景的 App，机构渠道可能是新收入；要先看产品是否适合被批量分配。务必分清「关多席位」和「移除渠道」两个动作，后者会让已有机构客户下次续费后被取消，任何调整都由开发者本人在后台操作，你只给建议。定制 App（Custom apps）的订阅自动在机构渠道上架且不能退出，不属于可调范围。群组购买的 App Store 上线日 Apple 只说「今冬 / 今年晚些时候」，不要承诺具体日期；佣金按原有订阅条款，Apple 未说明机构重新分配席位后一年 15% 的时钟如何计，别替客户下结论。只在 Web 用 Stripe 收费、不走 App Store 订阅的产品不是首批客户。

## 来源线索

- [Apple Developer News: Offer your subscriptions to businesses and schools（2026-10-22）](https://developer.apple.com/news/?id=yfo21auu)
- [App Store Connect Help: Manage purchase options for an auto-renewable subscription](https://developer.apple.com/help/app-store-connect/manage-subscriptions/manage-purchase-options-for-auto-renewable-subscriptions/)
- [App Store Connect Help: Manage pricing for auto-renewable subscriptions（多席位涨价规则）](https://developer.apple.com/help/app-store-connect/manage-subscriptions/manage-pricing-for-auto-renewable-subscriptions)
- [WWDC26: Offer subscriptions to groups and organizations](https://developer.apple.com/videos/play/wwdc2026/391/)
- [PPC Land: Apple puts developers' subscriptions on sale to schools and firms by default](https://ppc.land/apple-puts-developers-subscriptions-on-sale-to-schools-and-firms-by-default/)
