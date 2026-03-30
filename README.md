1. Superpowers（:star: 90k+）: [https://github.com/obra/superpowers](https://github.com/obra/superpowers)
类型：Skills Framework，准确的说，这其实是一整套工程方法论系统
兼容：Claude Code（Marketplace 已收录）、Codex、Gemini CLI、OpenCode、Cursor
强制 coding agents 走 TDD+代码审查，不让 coding agent 偷懒

2. SuperClaude Framework（:star: 21.8k）：[https://github.com/SuperClaude-Org/SuperClaude_Framework](https://github.com/SuperClaude-Org/SuperClaude_Framework)
类型：Skills 命令框架
兼容：Claude Code
这是一个元编程配置框架而不是标准的 skill.md 的格式，但做的事情却和 skills 高度相似，SuperClaude Framework定义了 Coding Agent 的行为模式、工作流程、输出约束，所以我还是把这个项目放到了 skills 推荐专栏，它和 Superpowers 的区别是，Superpowers 管的是“怎么正确地开发”（TDD、代码审查），SuperClaude 管的是怎么高效地指挥 coding agent 干活。两个可以配合着用。

3. MiniMax Skills（:star: 1.8k）： [https://github.com/MiniMax-AI/skills](https://github.com/MiniMax-AI/skills)
类型：Skills 集合包（10 个）
兼容：Claude Code / Cursor / Codex / OpenCode
MiniMax 官方出的 10 个技能，每个都带完整工作流、设计系统、质量门控，是可以开箱即用的。

4. Anthropic Official Skills（官方出品）： [https://github.com/anthropics/skills](https://github.com/anthropics/skills)
类型：官方 Skills
兼容：Claude Code（原生支持）
Anthropic 自己出的 Skills，算是 Skills 的标杆了，这个 skill-creator 在站内也有很多佬友推荐， frontend-design 也很不错。

5. Vercel Agent Skills（:star: 23.6k）：[https://github.com/vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)
类型：Skills 集合包（前端最佳实践）
兼容：Claude Code / Cursor / Codex / 通用
Vercel 工程团队出品的 5 个 Skills，每个都是 SKILL.md 标准格式。做 React / Next.js / Web 开发的佬友可能会感兴趣，它不教如何写代码，而是教 coding agent 按 Vercel 团队的工程标准来审查和优化代码。

6. Planning with Files ： [https://github.com/OthmanAdi/planning-with-files](https://github.com/OthmanAdi/planning-with-files)
类型：专项 Skill（上下文工程）
兼容：Claude Code / Codex / 通用
做过长任务的佬都知道，coding agent 做到一半就忘了最初的目标，上下文太长前面的指令就被稀释掉了。这个 Skill 用 Markdown 文件给 coding agent 做了一个外挂记忆库：
- task_plan.md → 任务规划
- findings.md → 调研发现
- progress.md → 进度追踪
- coding agent 做重大决策会先重读计划，在推进过程中更新进度，十分适合跨多轮对话的复杂任务。

7. Context Engineering Skills： [https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering)
类型：Skills 集合包（上下文治理）
兼容：通用
现在社区慢慢意识到了：提示词工程只是冰山一角，左右 coding agent 输出质量的还有很大的一部分是上下文工程，给它看什么、按什么顺序看、什么时候该压缩、什么时候该忘掉是很重要的一环。

8. Composio Skills： [https://github.com/ComposioHQ/skills](https://github.com/ComposioHQ/skills)
类型：Skills + MCP（双层配合）
兼容：通用（npx skills add composiohq/skills 一键安装）
日常开发里 coding agent 经常要和外部服务打交道——读写 GitHub Issues、发 Slack 通知、操作 Google Sheets、查 Jira。每个服务都自己写 MCP Server 来对接对很麻烦，Composio 把这些都封装好了。
它比较特殊的一点是：MCP + Skills 配合。Composio 本身提供 MCP Server（composio mcp），coding agent 通过标准 MCP 协议调用外部服务；同时还有一层 SKILL.md + rules 文件，教 coding agent 怎么正确地使用这些 MCP 工具——session 怎么管、多用户怎么隔离、OAuth 怎么走、各框架怎么集成。光有 MCP 工具 coding agent 只知道能调，加上 Skills 它才知道怎么调才对。
Composio Skills 的模式也是我觉得很有参考价值的模式，用 MCP + Skills 配合来提高agent调用工具的质量和效率。

9. Antfu Skills ： [https://github.com/antfu/skills](https://github.com/antfu/skills)
类型：个人 Skills
兼容：通用
Anthony Fu 的个人 Skills 仓库。他是 Vue / Vite / UnoCSS / Vitest 的核心维护者，代码风格和工程标准就是行业标杆。与其一口气装一堆别人写的 Skills，不如先看看顶级大佬是怎么组织和写 Skills 的，学到手之后自己写的才好用。

10. Awesome Agent Skills（:star: 12.4k）： [https://github.com/VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills)
类型：Skills 索引
兼容：Claude Code / Codex / Antigravity / Gemini CLI / Cursor 等
严格说这不是一个 Skill，而是一个 500+ Skills 的索引仓库，正因为它整合的 skills 实在是全面，所以我决定放进来。里面收录的都是 Anthropic、Google Labs、Vercel、Stripe、Cloudflare、Netlify、Trail of Bits、Sentry、Expo、Hugging Face 这些团队贡献的高质量 skills。


## 附录一：Skills 整合平台
除了上面推荐的 10 个，找更多 Skills 可以去这些地方翻：

|平台|	特点|	链接 |
| :---   | :---       | :---        |
|Skills.sh	|Vercel 出的，3.5 万+ 技能包，支持一键安装|	[skills.sh](https://github.com/SuperClaude-Org/SuperClaude_Framework)|
|SkillsMP	|聚合 GitHub 12.1 万+ 开源技能，AI 语义搜索	|[skillsmp.com](https://github.com/SuperClaude-Org/SuperClaude_Framework)|
|Agent Skills Me	|人工精选 |	[agentskills.me](https://agentskills.me/)|
|agent-skills.md	|6000+ 高频技能 |	[agent-skills.md](https://agentskills.me/)|
|Agent Skills Hub	|29,000+ Skills + MCP Servers |	[agentskillshub.top](https://agentskillshub.top/)|
|agent-skills.cc	|从 63,000+ GitHub Skills 里精选 1,000+ |	[agent-skills.cc](https://agent-skills.cc/)|
|Claude Marketplaces |	Claude Code 插件市场 |	[claudemarketplaces.com](https://claudemarketplaces.com/)|
|AI Templates |	1000+ Agents / Commands / Skills / MCP |	[aitmpl.com](https://www.aitmpl.com/)|
|SkillStore |	中文友好，有安全审查 |	[skillstore.io](https://skillstore.io/zh-hans)|
|Skills Directory |	Reddit 社区推荐的口碑榜 |	[skillsdirectory.com](https://www.skillsdirectory.com/)|
|SkillHub（腾讯）|	2.2 万+ 技能，国内高速镜像	| [skillhub.tencent.com](https://skillhub.tencent.com/)|
|ClawHub |	OpenClaw 官方技能仓库，像 npm 一样管理 |	[clawhub.ai](https://clawhub.ai/)|

## 附录二：Repo推荐
|仓库	| 定位 |
| :---   | :---       |
|[anthropics/skills](https://github.com/anthropics/skills)	| Anthropic 官方 Skills|
|[obra/superpowers](https://github.com/obra/superpowers)	| Superpowers 框架|
|[SuperClaude-Org/SuperClaude_Framework](https://github.com/SuperClaude-Org/SuperClaude_Framework)	| SuperClaude 命令框架|
|[MiniMax-AI/skills](https://github.com/MiniMax-AI/skills)	| MiniMax 10 个生产级 Skills|
|[VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills)	| 500+ Skills 索引|
|[ComposioHQ/skills](https://github.com/ComposioHQ/skills)	| Composio MCP + Skills|
|[vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)	| Vercel 官方|
|[antfu/skills](https://github.com/antfu/skills)	| Antfu 的个人实践|
|[ZhanlinCui/Agent-Skills-Hunter](https://github.com/ZhanlinCui/Agent-Skills-Hunter)	| 大杂烩（400+ Skills）|
