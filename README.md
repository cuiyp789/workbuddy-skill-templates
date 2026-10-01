# WorkBuddy Skill Templates / WorkBuddy 技能模板库

为 [腾讯 WorkBuddy 开放平台](https://open.workbuddy.cn) 开发者提供的开源技能模板与结构参考。

Open-source templates and structure references for WorkBuddy Open Platform skill developers.

## 为什么开源 / Why

市面上关于"怎么写 SKILL.md"的资料大多只讲语法，不讲**质量检测的评分逻辑**（任务完成度 / 指令遵从性 / 事实辨别性 / 规则遵从性）。本仓库的模板按这四个维度设计，并经过真实提审验证（一次通过）。

## 模板清单 / Templates

| 模板 | 场景 | 核心设计 |
|---|---|---|
| weekly-report | 周报 | 三格式（KPI表/叙事/简洁）+ 不编造数据铁律 |
| meeting-minutes | 会议纪要 | 行动项三要素（负责人+动作+截止）+ 占位符降级 |
| daily-report | 日报 | 轻量三段式，30 字/条 |
| year-end-summary | 年终总结 | 主线提炼 + 目标对照 + 可验收规划 |
| performance-review | 述职报告 | STAR 拆解 + 个人贡献显性化 |
| email-polish | 邮件润色 | 四语气模板 + 事实不变原则 |
| ppt-outline | PPT 大纲 | 结论式页标题 + 每页 ≤3 要点 + 可视化建议 |
| okr | OKR | KR 可衡量改写 + 上下对齐检查 |

## 使用 / Usage

1. 复制对应目录，替换 SKILL.md 中 frontmatter 的 `name`（全平台唯一）与 `author`
2. 按你的领域改写 `references/formats.md` 的模板与 `references/examples.md` 的示例
3. 本地用 WorkBuddy 客户端实测后再提审（平台质量检测 4 维度：任务完成度/指令遵从性/事实辨别性/规则遵从性）

## 踩坑速查 / Gotchas

- frontmatter 所有含冒号的长值一律加双引号
- 平台要求 `display_name_en`（英文展示名），文档未提及但必填
- `name` 全平台唯一，通用词（如 `weekly-report`）已被占用
- 专家包 plugin.json 的展示字段均为 i18n 结构 `{en, zh}`；`tags` 为 i18nField 数组（3 个）
- 专家内置技能：`plugin.json.skills` 写 `./skills/<name>`，技能目录真实打进包内

## License

MIT
