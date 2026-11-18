# Apple 中国大陆 AIGC 与安全评估合规就绪体检（2027-01-31 前现有应用须完成并核验声明否则中国区不可售 × 无相关功能也须选 No）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 皆可 |
| 优先 | |
| 更新 | 2026-11-18 |

## 一句话

帮在中国大陆 App Store 上架的开发者，对照官方帮助文，在 App Store Connect 新的 **App Compliance** 页完成两项声明——**AI-Generated or Synthetic Content**（人工智能生成或合成内容）和 **Security Assessment**（安全评估）——并在 **2027-01-31** 前拿到已核验（verified）状态；没有相关功能、或已在中国区关闭 / 按地区屏蔽的，也必须选 **No**，不是可以跳过。

## 为什么现在

App Store Connect 帮助文《View China mainland compliance information》写明：只要应用在中国大陆 App Store 上架，就须声明是否向中国区用户提供受监管功能，并在需要时提交已获批准的合规材料。官方分两项：

- **AI-generation or Synthetic services**：依据《人工智能生成合成内容标识办法》，若应用提供 AI 聊天机器人、图像或视频生成、语音或人脸编辑等服务，须声明并提交已获批准的大模型（LLM）或算法（Algo）备案信息；若功能由第三方技术提供，还须上传授权或使用协议。
- **Features requiring a Security Assessment**：若应用包含分发人工智能生成或合成内容，或提供端到端加密即时通讯（EIM），须提交在「全国互联网安全管理服务平台」已完成安全评估的证明，以及评估报告副本。

更关键的是范围和截止日。官方写的是：**所有在中国大陆 App Store 上架的应用都必须完成这些合规声明**——有相关功能选 Yes，没有、或已在中国区关闭 / 按地区屏蔽则选 No。**2027 年 1 月 31 日前，中国区所有现有应用必须完成并核验（completed and verified）这些声明，才能继续在 App Store 上架。** 未通过核验时，应用仍会在你所选的其他国家或地区发布，但在中国大陆 App Store 不可售。

App Store Connect 发行说明 **2026-11-16** 也写了：ICP、游戏版号、医疗器械声明等材料已从 App Information 迁到新的 App Compliance 页，并在同一页管理上述 AIGC 与安全评估声明。入口已经可见，离 01-31 大约还有十周；而官方要的是「完成并核验」，不是只点保存。帮助文还写：若声明未通过核验，更新后的材料会在你提交下一个应用版本接受审核时再审。所以现在就该对照后台状态，而不是卡着截止日才填。

这不是年龄分级问卷里的 Shared Location / Dating and Relationships（s62，截止 2027-01-12），也不是 11-17 那篇税费 / 价格调整新闻，更不要和早已存在的 ICP 备案、游戏版号、网络出版或宗教 / 新闻许可混成同一份交付——那些要求不是这次新加的，只是和这两项新声明一起出现在 App Compliance 页。

## 目标客户

应用目前在中国大陆 App Store 上架、还没在 App Compliance 页完成这两项声明并看到已核验状态的独立开发者、小工作室和订阅产品。首批最值得找的是两类：一是默认勾了「所有地区」上架、其实没有 AI 或加密聊天功能、但还没去选 No 的人；二是带聊天机器人、图像 / 视频生成、语音或人脸编辑、AIGC 分发或端到端加密即时通讯的应用——后一类除了声明，还要备备案号、第三方授权协议或安全评估材料。没有在中国区上架、也不打算上架的应用不是本条首批。本条也不覆盖同一时期的年龄分级新描述（s62）或税费 / 价格调整。

## 一人怎么起步

两周 concierge（01-31 前先做页面核对）：先发一份自查表（「App Store Connect 里，这个应用的 Availability 是否包含中国大陆？侧边栏 General 下有没有 App Compliance？AI-Generated or Synthetic Content 和 Security Assessment 当前是 Missing Info、Pending Verification、Verification Failed 还是 Active？应用有没有向中国区用户提供 AI 聊天机器人、图像或视频生成、语音或人脸编辑？这些功能是否已在中国区关闭或按地区屏蔽？有没有分发 AIGC 内容，或提供端到端加密即时通讯？如果要选 Yes，有没有已批准的 LLM / 算法备案号和备案名称？若用了第三方模型，授权协议上的权利人名称是否与网信办批准名录一致？安全评估有没有平台『已通过』截图和带公章的报告？」）到独立开发者社群、订阅产品群和 X 换 waitlist。对报名的 5–10 个应用：对照官方帮助文和后台页面，列出该选 Yes 还是 No、缺哪些材料、当前状态距离「已核验」还差哪一步，以及要不要预留提交下一版本的时间。只出书面对照和后台路径说明，不代登录、不代填写声明、不代办法备案或安全评估、不代写或代盖章授权协议，也不保证核验结果或中国区能否继续上架。先收一次性体检费，需要在提交更新或补材料后再复查状态的另报价。

## 难度

中（官方把「所有中国区上架应用都须声明」、Yes / No 的选法、01-31 前须完成并核验、以及两项所需材料写清楚了；真正费时的是判断功能是否对中国区开放，以及 Yes 场景下备案号、授权协议和安全评估材料是否齐、是否与名录一致。帮助文还提示核验失败后要等下一次版本提交再审，不能把「点了保存」当成已经过关）

## 变现路径

一次性中国区 AIGC / 安全评估声明体检（示意 $79–$199 / 应用或开发者账户）；多应用打包或 01-31 前加急核对（示意 $150–$400）；提交更新或补材料后再复查状态（示意 $29–$79 / 次）。不包含代填写声明、代办大模型 / 算法备案、代做安全评估或代准备授权协议，也不保证核验或上架结果。可与年龄分级新描述（s62）、取消挽留消息（s40）并列介绍，报价和交付分开。

## 注意的坑

不要写成只有 AI 应用才要管：官方要求是所有在中国大陆 App Store 上架的现有应用，都须在 2027-01-31 前完成并核验这两项声明；即使两项都选 No，也要在 App Compliance 页完成。不要漏掉「默认向所有地区上架」的应用——没在后台关掉中国区，就落在这条规定里。不要把「应用用了定位 / 普通聊天 / 滤镜」直接当成必须选 Yes；官方对 AIGC 的例子是聊天机器人、图像或视频生成、语音或人脸编辑，安全评估则点名 AIGC 分发和端到端加密即时通讯。若这些功能已在中国区关闭或按地区屏蔽，官方写明应选 No。不要和 ICP、游戏版号、网络出版、宗教或新闻许可、医疗器械声明混成一份清单，那些是原有材料，只是搬到了同一页。不要和 s62 的年龄分级问卷、或 11-17 税费 / 价格新闻混用截止日。不要替客户勾选或上传材料；选错或材料不符可能导致中国区不可售。第三方技术的授权协议须写明备案名称与备案号、被授权方是你或你的组织，且授权方名称须与网信办批准名录中的模型 / 算法权利人一致，缺一项都可能核验失败。帮助文要求提交材料时涂黑保密或专有信息；安全评估截图须能看出应用名、提供方和「通过 / 已通过审核」，报告须有应用名、提供方和公章。官方要的是 completed and verified，不是只提交；若状态不是 Active，以页面提示为准，不要自行保证「保存当天就会过」。你不是律师，也不是 Apple 员工，不代登录，不代向网信办或全国互联网安全管理服务平台提交评估，不保证核验或上架结果。价格只是示意，需自行验证。

## 来源线索

- [App Store Connect 帮助：View China mainland compliance information（所有中国区上架应用须完成声明；无相关功能或已在中国区关闭 / 屏蔽则选 No；现有应用须在 2027-01-31 前完成并核验才能继续在中国区上架；给出 App Compliance 页操作步骤与所需材料）](https://developer.apple.com/help/app-store-connect/manage-compliance-information/view-china-mainland-compliance-information)
- [App Store Connect 帮助：App and compliance information（中国区合规项定义：AIGC 须提交已批准的 LLM / 算法备案信息，第三方技术另须授权或使用协议；安全评估须提交全国互联网安全管理服务平台的通过证明和报告副本）](https://developer.apple.com/help/app-store-connect/reference/app-information/app-and-compliance-information)
- [App Store Connect 发行说明（2026-11-16）：ICP、游戏版号等材料迁至新的 App Compliance 页，并在同一页管理中国区 AIGC 与安全评估声明](https://developer.apple.com/help/app-store-connect/release-notes/)
- 相关但独立：[s62 Apple 年龄分级新内容描述就绪体检](s62-apple-age-rating-descriptors-readiness.md)、[s40 Apple 订阅取消挽留消息就绪体检](s40-apple-retention-messages-readiness.md)、[s31 Apple 订阅多席位就绪体检](s31-apple-multiseat-subscription-readiness.md)
