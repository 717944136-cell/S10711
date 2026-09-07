# S10711 · 个人 AI 概念学习仓库

> 课程作业仓库：用 **项目级 Skill** 沉淀"概念学习法"，并产出可核查的概念学习资料。
> 仓库结构可复用、可持续迭代——既是工具，也是作品集。

---

## 1. 这个仓库是做什么的？

本仓库把一个完整的**概念学习流程**做成了可复用的 **项目级 Skill**（`concept-explainer`），并首次用它生成了三份概念学习资料：**Agent、大模型的上下文、Skill**。

学习任何新概念时，只需在 WorkBuddy 中打开本仓库并对 AI 说"用 concept-explainer 学习 XXX"，即可按同一套标准流程产出结构化学习资料。后续课程项目可在此仓库上继续添加新资料与个人 Skill。

## 2. 仓库结构

```
S10711/
├── .workbuddy/                        # WorkBuddy 项目配置（项目级 Skill 的存放处）
│   └── skills/
│       └── concept-explainer/         # 项目级 Skill：概念学习资料生成器
│           └── SKILL.md               # Skill 定义（YAML 元数据 + 流程 + 自检要求）
├── learning-materials/                # 学习资料（由 concept-explainer 生成）
│   ├── agent.html                     # 概念①：Agent（AI 智能体）
│   ├── llm-context.html               # 概念②：大模型的上下文（Context / 上下文窗口）
│   ├── skill.html                     # 概念③：Skill（AI 技能 / Agent Skills）
│   └── concept-relationship.md        # 三概念关系说明（含 Mermaid 关系图）
├── README.md                          # 本说明文件
└── .gitignore                         # 版本与安全：排除敏感/缓存文件
```

## 3. Skill 是什么、放在哪、怎么用

| 问题 | 说明 |
|---|---|
| Skill 名称 | `concept-explainer`（概念学习资料生成器） |
| 存放路径 | `.workbuddy/skills/concept-explainer/SKILL.md`（仓库内项目级 Skill） |
| 作用 | 输入任意概念名 → 按固定流程生成含"学习目标 / 核心问题 / 个人解释 / 核心机制 / 应用场景 / 概念辨析 / 自测问题 / 资料来源"的学习资料 |
| 为什么可复用 | 它不是为本次三个概念写的一次性提示词，而是"能接收任何新概念"的通用流程，含输入、步骤、输出结构、资料来源与自检要求 |

**在 WorkBuddy 中调用它的方式：**

1. 用 WorkBuddy 打开本仓库文件夹（把它作为项目工作区）；
2. 在对话框中直接提出需求，例如：
   - "用 concept-explainer 学习 MCP" —— 显式点名；
   - "帮我学习一下 RAG 这个概念" —— 不点名也没关系，WorkBuddy 会根据 SKILL.md 中 `description` 的描述自动匹配并加载该 Skill；
3. Skill 被触发后，AI 会读取 SKILL.md 正文，按其七步流程生成 `learning-materials/<概念名>.html`，并同步更新本 README 的资料清单与 `concept-relationship.md`。

## 4. 已生成的学习资料

| 文件 | 对应概念 | 内容要点 | 核查状态 |
|---|---|---|---|
| `learning-materials/agent.html` | Agent（AI 智能体） | 定义与组成（规划/记忆/工具）、环境反馈循环、Workflow 辨析、边界与护栏 | 已生成；来源①②③⑤已联网核实，④待人工复核 |
| `learning-materials/llm-context.html` | 大模型的上下文 | 工作记忆类比、什么占上下文、窗口管理、context rot、中间遗忘 | 已生成；来源①已核实，②③（arXiv）待复核 |
| `learning-materials/skill.html` | Skill（Agent Skills） | 渐进式披露三层机制、触发流程、与 Prompt/Tool/MCP 辨析、最简 SKILL.md 示例 | 已生成；来源①②③已核实，④待复核 |
| `learning-materials/concept-relationship.md` | 三概念关系 | 文字＋对照表＋两张 Mermaid 图；重点回答"上下文如何影响 Agent""Skill 如何沉淀知识" | 已生成；核心论断与上述资料来源一致 |

> 说明：三份概念资料用独立 HTML 便于浏览器直接阅读；关系说明用 Markdown（Mermaid 图在 GitHub 自动渲染）。

## 5. 使用 AI 之后的人工核查与修改记录

> 按作业要求：可以使用 AI 生成，但必须阅读、理解、核查，且不伪造来源。以下如实记录本仓库的核查过程（持续更新）。

**AI 辅助完成的部分（2026-09-07）**
- 用网络搜索核实了关键资料链接的真实性：Anthropic《Building Effective Agents》、Agent Skills 官方发布页与文档、Lil'Log、Anthropic Context windows 文档、OpenAI 学习轨道等（已在各 HTML 的"资料来源"中标注"已联网核实"）。
- 少量拿不准的链接（arXiv 论文、MCP 官网）**没有伪称已核实**，而是明确标注"请点开复核"，避免资料造假。
- 关键术语与权威来源做过交叉对照（如 context rot、渐进式披露、Workflow vs Agent 的定义）。

**本人（仓库作者）的核查清单**
- [ ] 通读三份 HTML，确认"个人解释"与类比符合自己的理解（这是费曼学习法的核心，请改成自己顺口的说法再提交）；
- [ ] 点开所有标着"请点开复核"的链接，确认能打开、标题正确；
- [ ] 自测问题自己先做一遍再对照答案；
- [ ] 确认 `.gitignore` 生效，仓库内无任何密钥/隐私文件；
- [ ] 若对内容做了修改，请在本节下方追加一条"修改记录"。

**修改记录**
- 2026-09-07：初稿生成，AI 联网核实来源、交叉核对术语；等待作者人工通读后更新本清单。

## 6. 版本与安全

- 提交与推送：本仓库全部内容通过 git 提交并推送至 GitHub（公开仓库），提交历史见仓库 commits。
- 敏感信息防护：`.gitignore` 已排除 `.env`、密钥文件、编辑器缓存、WorkBuddy 会话数据（`.workbuddy/memory/`）等；仓库中不含 API Key、密码或个人隐私。
- 建议：在 GitHub 设置中开启邮箱隐私（用 `noreply` 邮箱提交），避免暴露个人邮箱。

## 7. 后续迭代方向

- 用 `concept-explainer` 继续学习新概念（RAG、MCP、提示词工程、Transformer……），扩充 `learning-materials/`；
- 把其他可复用流程（如"周报生成""论文笔记整理"）做成新的项目级 Skill，继续沉淀个人工作方法；
- 本仓库即个人 AI 学习作品集，可持续演进。
