# S10711 · 个人 AI 概念学习仓库

> 课程作业仓库：用 **项目级 Skill** 沉淀"概念学习法"，并产出可核查的概念学习资料。
> 仓库结构可复用、可持续迭代——既是工具，也是作品集。

---

## 1. 这个仓库是做什么的？

本仓库把一个完整的**概念学习流程**做成了可复用的**项目级 Skill**（`concept-learner`），
并已用该 Skill 生成三份概念学习资料：**Agent、大模型的上下文、Skill**。

学习任何新概念时，只需在 WorkBuddy 中打开本仓库并对 AI 说
"用 concept-learner 学习 XXX"，即可按同一套标准流程产出结构化学习资料。
后续课程项目可在此仓库上继续添加新资料与个人 Skill。

## 2. 仓库结构

```
S10711/
├── .workbuddy/                        # WorkBuddy 项目配置（项目级 Skill 存放处）
│   └── skills/
│       └── concept-learner/           # 项目级 Skill：概念学习资料生成器（唯一现行版）
│           └── SKILL.md               # Skill 定义（YAML 元数据 + 流程 + 自检要求）
├── archive/                           # 已归档内容（WorkBuddy 不会自动加载）
│   └── concept-explainer/             # 早期同名 Skill 第一版，已归档留档
├── learning-materials/                # 学习资料（由 concept-learner 生成）
│   ├── agent.html                     # 概念①：Agent（AI 智能体）
│   ├── llm-context.html               # 概念②：大模型的上下文（Context / 上下文窗口）
│   ├── skill.html                     # 概念③：Skill（AI 技能 / Agent Skills）
│   └── concept-relationship.md        # 三概念关系说明（含 Mermaid 关系图）
├── README.md                          # 本说明文件
├── .gitattributes                     # 统一换行符（git 规范）
└── .gitignore                         # 版本与安全：排除敏感/缓存文件
```

## 3. Skill 是什么、放在哪、怎么用

| 问题 | 说明 |
|---|---|
| Skill 名称 | `concept-learner`（概念学习资料生成器） |
| 存放路径 | `.workbuddy/skills/concept-learner/SKILL.md`（仓库内项目级 Skill） |
| 作用 | 输入任意概念名 → 按固定流程生成含"个人解释 / 核心机制 / 应用场景 / 易混淆与边界 / 自测问题 / 可核查来源"的学习资料 HTML |
| 为什么可复用 | 它不是为本次三个概念写的一次性提示词，而是"能接收任何新概念"的通用流程：SKILL.md 中写明适用场景、输入信息、生成步骤、输出结构、资料来源要求与自检要求 |

**在 WorkBuddy 中调用它的方式：**

1. 用 WorkBuddy 打开本仓库文件夹（把它作为项目工作区）；
2. 在对话框中直接提出需求，例如：
   - "用 concept-learner 学习 MCP" —— 显式点名；
   - "帮我学习一下 RAG 这个概念" —— 不点名也没关系，WorkBuddy 会根据 SKILL.md 中 `description` 的描述自动匹配并加载该 Skill；
3. Skill 被触发后，AI 会读取 SKILL.md 正文，按其流程生成 `learning-materials/<概念名>.html`。

> 历史说明：早期曾存在同名第一版 Skill `concept-explainer`（8 章节结构），
> 后经迭代统一为 `concept-learner`（六区块结构），旧版已移入 `archive/` 留档，
> 避免仓库中出现两个功能相同的"概念学习 Skill"。

## 4. 已生成的学习资料

| 文件 | 对应概念 | 内容要点 | 来源核查状态 |
|---|---|---|---|
| `learning-materials/agent.html` | Agent（AI 智能体） | 个人解释（大脑+工具+反馈循环）、核心机制、代码助手场景、4 条辨析（vs 聊天机器人/工作流/单轮助手/多 Agent）、3 道自测 | 4/4 已联网核实（Anthropic、IBM、Microsoft 课程、LangGraph 文档） |
| `learning-materials/llm-context.html` | 大模型的上下文 | 书桌类比、token 计量与注意力 n²、窗口构成、Context Rot、压缩/笔记/子 Agent 三板斧、4 条辨析、3 道自测 | 3/3 已联网核实（Anthropic、IBM、arXiv Lost in the Middle） |
| `learning-materials/skill.html` | Skill（Agent Skills） | 岗位手册类比、目录结构与渐进式披露、代码分工、开放标准、4 条辨析、3 道自测 | 3/3 已联网核实（Anthropic 博客、agentskills.io、GitHub 官方仓库） |
| `learning-materials/concept-relationship.md` | 三概念关系 | 对照表 + 两张 Mermaid 图；重点回答"上下文如何影响 Agent""Skill 如何沉淀可复用知识" | 论断与三份资料中已核实来源一致 |

> 说明：三份概念资料用独立 HTML 便于浏览器直接阅读；关系说明用 Markdown（Mermaid 图在 GitHub 自动渲染）。
> 每份 HTML 页脚含"生成与自检记录"，如实写明来源核实情况与待人工复核项。

## 5. 使用 AI 之后的人工核查与修改记录

> 按作业要求：可以使用 AI 生成，但必须阅读、理解、核查，且不伪造来源。以下如实记录（持续更新）。

**AI 辅助完成的部分**

- 2026-09-07：用 `concept-learner` 流程生成/重生成三份资料，输出前逐条联网核实来源：
  Anthropic《Building Effective Agents》《Effective Context Engineering》《Agent Skills》、
  IBM《What Are AI Agents? / What is a context window?》、Microsoft《AI Agents for Beginners》、
  LangGraph 官方文档、arXiv《Lost in the Middle》、agentskills.io 等，**共 9 个链接逐一打开确认有效**。
- 无法核实真实性的候选来源（如被访问拦截的页面）一律未收录，未编造任何 URL。
- 关键术语（context rot、渐进式披露、Workflow vs Agent 等）均与权威来源交叉对照。
- 2026-09-08：做作业收尾审计——归档早期重复 Skill（`concept-explainer` 移入 `archive/`），
  统一文档中的 Skill 名称引用，合并本地与远程历史并推送。

**本人（仓库作者）的核查清单**

- [ ] 通读三份 HTML，确认"个人解释"与类比符合自己的理解（这是费曼学习法的核心，请改成自己顺口的说法再提交）；
- [ ] 点开三份资料"资料来源"里的全部链接，确认能打开、标题正确；
- [ ] 自测问题自己先做一遍再对照答案；
- [ ] 确认 `.gitignore` 生效，仓库内无任何密钥/隐私文件；
- [ ] 若对内容做了修改，请在本节下方追加一条"修改记录"。

**修改记录**

- 2026-09-07：初稿生成（concept-explainer 版）；同日改用 `concept-learner` 流程重新生成三份资料，来源逐一联网核实。
- 2026-09-08：归档 `concept-explainer` 至 `archive/`，统一为唯一 Skill `concept-learner`；同步更新 README 与概念关系说明；合并历史并推送。等待作者人工通读后勾选上方清单。

## 6. 版本与安全

- 远程仓库：`https://github.com/717944136-cell/S10711`（公开，无需权限即可访问）。
- 历史说明：本地与远程曾存在两条内容相同但互无祖先的提交历史，已于 2026-09-08 对齐合并；
  旧本地历史完整保留在分支 `backup/original-local-main` 中，可随时回溯。
- 敏感信息防护：`.gitignore` 已排除 `.env`、密钥文件、编辑器缓存、WorkBuddy 本地会话数据
  （`.workbuddy/memory/`）等；`.workbuddy/skills/` 与 `learning-materials/` 按要求入库。
- git 提交身份使用 GitHub 的 `noreply` 邮箱，避免暴露个人邮箱。
- 仓库中不含 API Key、密码或个人隐私。

## 7. 后续迭代方向

- 用 `concept-learner` 继续学习新概念（RAG、MCP、提示词工程、Transformer……），扩充 `learning-materials/`；
- 把其他可复用流程（如"周报生成""论文笔记整理"）做成新的项目级 Skill，继续沉淀个人工作方法；
- 本仓库即个人 AI 学习作品集，可持续演进。
