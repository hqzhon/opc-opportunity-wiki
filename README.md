# 一人公司机会 Wiki

面向一人公司（OPC）的可公开机会清单：聚焦 **跨境电商 / 独立站** 与 **SaaS / 订阅**，按小时扫描公开趋势与信号，沉淀成可复用的 wiki 条目。

## Browse

- [Wiki home](wiki/Home.md)
- [Catalog](wiki/Catalog.md)
- [Hourly digests](wiki/digests/)
- [Agent Skills Wiki](https://github.com/hqzhon/agent-skills-wiki) — 可复用 agent skills 目录

## 收录标准

一条机会通常至少满足两条：

1. 一人可冷启动（不大团队、不大预算）
2. 有清晰目标客户与变现路径
3. 有公开线索（报道、支付验证目录、一线反馈等）
4. 可在 2–4 周内做最小验证

跳过：空泛风口、纯广告、无法验证的「暴利」承诺。

## Layout

```
wiki/
  Home.md          # 总览与用法
  Catalog.md       # 全部机会索引
  entries/         # 每条机会一个 markdown
  digests/         # 每小时扫描摘要
meta/
  last-scan.json   # 扫描游标 / 去重状态
```

## License

本仓库内容为 [CC BY 4.0](LICENSE)。外链原文版权仍归原作者。

## Maintenance

扫描约每小时一次（Asia/Shanghai 白天）。新信号写入 digests，过质量关后晋升到 `wiki/entries/`。
