# Agentic Knowledge base 发布就绪体检（draft → publish × 冲突 × 迁移）

| 字段 | 内容 |
| --- | --- |
| 市场 | SaaS / 订阅 |
| 适配 | 偏技术 |
| 优先 | 是 |
| 更新 | 2026-10-27 |

## 一句话

对 Shopify 独立站跑「Agentic Knowledge base」专用体检：店面扫描草稿哪些仍未 Publish、Admin 源事实与店面文案/退货窗是否冲突、Suggested update 积压、以及旧 Knowledge Base App（>1000 facts）在 2027-01-15 前的迁移缺口——给出可修分数卡与持续漂移报警。

## 为什么现在

2026-10-26 Shopify 把 Knowledge base 收进 Admin（Sales channels → Agentic → Knowledge base），替代独立 App（2027-01-15 后下线）。官方明确：从店面扫描生成的事实**默认 Unpublished**，不 Publish 就进不了 Storefront MCP，AI 渠道答不到；与 Admin 绑定的政策/联系类事实创建时即 Published。容量上限 1000 facts；旧 App 里 ≤1000 的商户自建/覆盖事实已迁并发布，**>1000 的店须在截止日前手工补回**。假日季 agentic 首年，大量店「看起来有 Knowledge base」实则关键类草稿未发、退货窗与 Returns & warranty 字段对不上、或 Suggested update 无人批。AgentReady 等偏 schema / Catalog / llms.txt；Power Commerce 等偏企业迁移顾问——仍缺轻量「Publish 面 × 源冲突 × 1000 上限迁移」订阅楔子。

## 目标客户

已开 Agentic / 希望 AI 购物代理答对非商品问答（退货、礼品、履约、品牌）的 DTC 与跨境独立站；客服已出现「AI 说的政策跟网站不一致」、或收到 Shopify 大库迁移邮件的中小品牌与代运营。

## 一人怎么起步

两周 concierge：进 Knowledge base 导出/截图各 category 的 Published vs Unpublished → 对照 Shipping / Returns 政策页与 Admin 退货规则抽 20–40 个字段做冲突表 → 标出 Suggested update 与 Missing policies → 若曾用旧 App 且接近/超过 1000，做迁移优先级清单 → 交「须先 Publish / 冲突勿发 / 可维持」分数卡换 waitlist / 预付；验证后再做 Embedded 监测（定时重扫、源页变更报警、容量逼近提醒）。

## 难度

中（规则写在公开 Changelog + Help Center；一人可两周探针。难点：需商家授权读 Agentic Knowledge base；勿承诺「Publish 后一定被某第三方代理引用」；与政策 MCP 探针、Catalog 体检边界要划清）

## 变现路径

月订阅监测（示意 $29–$99，按店铺/事实量档）；一次性发布就绪审计 + 大库迁移协助；可打包给代运营 / 客服外包。

## 注意的坑

与 `s9-agent-policy`（用买家问题探针 policy tool / agents.md / 履约声明）不同，焦点是 **Knowledge base 事实语料的 Publish 闸门与源一致性**；与 `s7-agentic-catalog`（商品可发现性）亦不同。Admin 源事实创建即发布，勿误报「全未发布」。容量 1000 含自动生成 + 附加事实；Custom storefront / Agentic plan 仅能加 additional facts。Published facts 经 Storefront MCP **公开可检索**——勿把内部备注、合同条款当事实发布。Shopify 若默认自动 Publish 扫描草稿，楔子会变窄——需保留「冲突对账 + Suggested update 治理 + 迁移/容量」。

## 来源线索

- [Shopify Changelog: Knowledge base is now built into your admin (2026-10-26)](https://changelog.shopify.com/posts/knowledge-base-is-now-available-in-your-admin)
- [Shopify Help: Answering customer questions with your knowledge base](https://help.shopify.com/en/manual/online-sales-channels/agentic-storefronts/knowledge-base)（扫描草稿默认 Unpublished、Admin 源即 Published、1000 上限、Publish 控件、Storefront MCP）
- [Shopify Help: Shopify Knowledge Base app migration note](https://help.shopify.com/en/manual/promoting-marketing/knowledge-base)（旧 App ≤1000 迁并发布；>1000 须在 2027-01-15 前手工补）
- [OpenTools: Knowledge base admin migration / published facts / app deadline](https://opentools.ai/news/shopify-knowledge-base-admin-migration-published-facts-app-deadline)
- [AgentReady App Store listing](https://apps.shopify.com/agentreadyapp)（通识 AI 就绪，边界对照）
