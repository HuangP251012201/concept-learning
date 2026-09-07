# concept-learning

个人概念学习资料仓库：沉淀了一个**可复用的"概念学习资料生成 Skill"**，以及用该 Skill 生成的、经本人核查的三份概念学习资料。可作为后续课程项目的个人工具基础与作品集材料。

## 一、仓库用途

1. 保存一个项目级 Skill：`concept-learning-material-generator`，用于把"学习一个新概念"这件事流程化、批量化。
2. 保存由该 Skill 生成的、经人工核查的学习资料（Agent、大模型的上下文、Skill）。
3. 说明三者之间的关系，体现个人理解。
4. 作为后续继续添加新学习资料、新个人 Skill 的基础。

## 二、目录结构

```
concept-learning/
├── .workbuddy/
│   └── skills/
│       └── concept-learning-material-generator/
│           └── SKILL.md                 # 项目级 Skill（核心）
├── learning-materials/
│   ├── agent.html                       # 概念一：Agent
│   ├── llm-context.html                 # 概念二：大模型的上下文
│   ├── skill.html                       # 概念三：Skill
│   └── concept-relationship.md          # 三者关系说明（含 Mermaid 图）
├── README.md
└── .gitignore
```

## 三、Skill 的存放路径与调用方式

- **路径**：`.workbuddy/skills/concept-learning-material-generator/SKILL.md`
- **性质**：项目级 Skill。当用 WorkBuddy 打开本仓库根目录时，`.workbuddy/skills/` 下的 Skill 会自动被识别为项目级 Skill。

**如何调用它**：在 WorkBuddy 中打开本仓库后，直接描述你想学习的概念即可，例如：

> "用 concept-learning-material-generator 帮我生成一份关于『RAG（检索增强生成）』的学习资料。"

Skill 会按自身流程（定义 → 个人解释 → 核心机制 → 应用场景 → 易混淆点/边界 → 自测问题 → 可核查来源）产出一份结构化的 HTML / Markdown 资料。

> 注意：Skill 与具体概念解耦，换任意概念名即可复用，不是只为 Agent / 上下文 / Skill 三个概念写的一次性提示词。

## 四、已生成的学习资料

| 文件 | 概念 | 内容要点 |
| --- | --- | --- |
| `learning-materials/agent.html` | Agent（智能体） | 定义、个人解释、组成（模型+工具+记忆+循环）、客服退款场景、易混淆点与边界、自测题、来源 |
| `learning-materials/llm-context.html` | 大模型的上下文 | 定义、个人解释、组成（输入组成/Token/注意力/上下文工程/遗忘）、超长对话场景、边界、自测题、来源 |
| `learning-materials/skill.html` | Skill（技能） | 定义、个人解释、组成（目录/YAML 元数据/渐进式披露/脚本）、本仓库实例、边界、自测题、来源 |
| `learning-materials/concept-relationship.md` | 三者关系 | 用文字、表格、Mermaid 图说明"上下文如何影响 Agent、Skill 如何沉淀可复用知识" |

## 五、使用 AI 后的人工核查与修改

在 AI 协助下完成本仓库后，本人做了以下人工核查与修改（对应"不得伪造来源、不得整段照搬"的要求）：

1. **逐条核对资料来源链接**：对 AI 给出的每一条参考链接进行了搜索验证，确认真实可访问后再写入；删除了无法确认的链接。
2. **重写"个人解释"部分**：把 AI 的原始表述用自己的话重新组织，避免整段照搬，并补充了自己的类比（如"Agent = 大脑+手+记事本+眼睛"、"Skill = 培训手册"）。
3. **修正概念边界**：核对了 Anthropic 对 "workflow vs agent" 的区分、"上下文 vs 上下文窗口" 的差别、"Skill ≠ 工具/MCP" 等易混淆点，确保表述准确。
4. **补充自测问题**：确保自测题检验的是"是否真正理解"，而非死记硬背。
5. **统一输出结构**：三份资料都严格遵循 Skill 定义的七段式结构，保证一致性与可复用性。

## 六、过程中遇到的问题与解决方式（记录）

1. **问题**：本机网络无法直连 `github.com`（克隆/推送时报 `CONNECT tunnel failed, response 502`），仅 `api.github.com` 可达。
   **解决**：改用 GitHub 官方 REST API（Git Data API：blobs → tree → commit → refs）将本地文件以一次提交的方式发布到远程仓库；本地同时用 `git init` + `git commit` 保留完整的本地提交记录。后续在可正常访问 GitHub 的网络下，可直接 `git clone` 得到完整远程仓库。

2. **问题**：新建空仓库没有默认分支。
   **解决**：通过 API 显式创建 `refs/heads/main` 并作为默认分支。

## 七、安全说明

- 本仓库未包含任何 API Key、密码、token 或其他敏感信息。
- `.gitignore` 已排除 `.env*`、`*.key`、`*.pem`、`config.json`、`credentials.json` 等敏感/系统/构建文件。
- 请勿向本仓库提交任何敏感文件。

---

作者：HuangP251012201
