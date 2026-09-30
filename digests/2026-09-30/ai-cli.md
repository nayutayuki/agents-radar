# AI CLI 工具社区动态日报 2026-09-30

> 生成时间: 2026-09-30 01:32 UTC | 覆盖工具: 9 个

- [Claude Code](https://github.com/anthropics/claude-code)
- [OpenAI Codex](https://github.com/openai/codex)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)
- [GitHub Copilot CLI](https://github.com/github/copilot-cli)
- [Kimi Code CLI](https://github.com/MoonshotAI/kimi-cli)
- [OpenCode](https://github.com/anomalyco/opencode)
- [Pi](https://github.com/badlogic/pi-mono)
- [Qwen Code](https://github.com/QwenLM/qwen-code)
- [DeepSeek TUI](https://github.com/Hmbown/DeepSeek-TUI)
- [Claude Code Skills](https://github.com/anthropics/skills)

---

## 横向对比

好的，作为专注于 AI 开发工具生态的资深技术分析师，我将基于您提供的各工具社区动态摘要，为您生成一份横向对比分析报告。

---

### AI CLI 工具生态横向对比分析报告（2026-09-30）

#### 1. 生态全景

当前 AI CLI 工具生态已进入**功能深化与安全治理并重**的阶段。一方面，以 **Claude Code** 和 **Qwen Code** 为代表，社区对 **Mods/插件系统、高级 Agent 能力（如 Managed Agent）** 等扩展性需求极为强烈，标志着从“单工具”向“平台化”演进的趋势。另一方面，**安全与权限控制**成为贯穿几乎所有工具的绝对焦点，从组织级管控（安全默认值）到细粒度的工具调用许可，再到对安全分类器误报的广泛抱怨，显示出工具在能力边界扩张后，如何平衡**智能性与可控性**是当前最大的挑战。同时，跨平台稳定性（特别是Windows）和**Token 成本优化**仍是开发者最直接的痛点。

#### 2. 各工具活跃度对比

| 工具名称 | 今日Release数 | 热点Issues数 (精选) | 重要PRs数 (精选) | 最热Issue (👍) | 社区活跃度评级 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 1 | 10 | 10 | 841 (多账户管理) | 🔥🔥🔥🔥🔥 |
| **OpenAI Codex** | 7 | 10 | 10 | 139 (Windows闪烁) | 🔥🔥🔥🔥🔥 |
| **Gemini CLI** | 2 | 10 | 10 | 8 (通用代理挂起) | 🔥🔥🔥🔥 |
| **Qwen Code** | 3 | 10 | 10 | 0 (架构提案) | 🔥🔥🔥🔥 |
| **OpenCode** | 0 | 10 | 10 | 112 (内存问题) | 🔥🔥🔥🔥 |
| **GitHub Copilot CLI** | 5 | 10 | 1 | 13 (CLI 400错误) | 🔥🔥🔥 |
| **Pi** | 1 | 10 | 10 | 6 (ChatGPT登录) | 🔥🔥🔥 |
| **DeepSeek TUI** | 0 | 10 | 10 | 0 (EPIC-005架构) | 🔥🔥🔥 |
| **Kimi Code CLI** | 0 | 0 | 0 | - | ⚪️ (静默) |

*注：活跃度评级综合了Release频率、热点问题关注度（评论数、👍数）、PR数量及社区讨论热度。*

#### 3. 共同关注的功能方向

| 共同方向 | 涉及工具 | 具体诉求 |
| :--- | :--- | :--- |
| **安全与权限控制** | Claude Code, OpenAI Codex, OpenCode, DeepSeek TUI | - **组织级策略**：Claude Code的“安全默认值”引入组织级Deny/Allow规则。 <br> - **误报与残留**：多工具的安全分类器对合法操作（杀毒开发、网络研究）误报，或在退出自动模式后仍阻止用户授权操作。 <br> - **精细权限**：DeepSeek TUI的Full Access权限未被正确传递。 |
| **多模型与兼容性** | Claude Code, OpenAI Codex, Gemini CLI, Pi, Qwen Code | - **默认模型切换**：GPT-6.1 Sol成为OpenAI Codex和Pi的默认模型。 <br> - **推理模型适配**：Pi和Qwen Code在处理推理模型的`thinking` token、`finish_reason`等方面出现兼容性问题。 <br> - **自定义提供商**：OpenCode用户抱怨自定义OpenAI兼容模型在图像输入后会话不可恢复。 |
| **Windows平台稳定性** | Claude Code, OpenAI Codex, Pi, DeepSeek TUI | - **更新/启动故障**：Claude Code和OpenCode出现因静默更新或端口冲突导致的无法启动问题。 <br> - **UI/渲染问题**：OpenAI Codex的控制台窗口闪烁、Pi的Windows生态支持碎片化。 <br> - **文本处理**：DeepSeek TUI多行粘贴自动提交问题。 |
| **会话管理与Undo** | Claude Code, OpenAI Codex, DeepSeek TUI, GitHub Copilot CLI | - **状态同步**：DeepSeek TUI的`/retry`仅回滚UI，模型上下文未同步，是严重Bug。 <br> - **会话恢复**：GitHub Copilot CLI的锁文件“僵尸”化，导致会话无法恢复。 <br> - **压缩失败**：Pi和Gemini CLI在特定模型下的会话压缩失败，影响长对话。 |
| **成本与Token治理** | Claude Code, Qwen Code, Gemini CLI | - **隐性Token消耗**：Claude Code社区抱怨Unexpected的Schema加载增加了上下文开销。 <br> - **用量透明**：Qwen Code发起“非对话上下文Token治理”专项Issue。 <br> - **计费Bug**：OpenCode将OAuth预算误判为端点限制，导致token被提前截断。 |

#### 4. 差异化定位分析

| 工具名称 | 核心定位 | 目标用户 | 技术路线/特点 |
| :--- | :--- | :--- | :--- |
| **Claude Code** | **全能型AI Agent平台** | 高级开发者、团队/企业 | 强调**插件生态 (Mods)** 和**组织级安全策略**，意图成为开发者在终端里的“操作系统”。 |
| **OpenAI Codex** | **生态集成的核心网关** | OpenAI生态开发者 | 深度集成OpenAI产品矩阵（ChatGPT桌面版、GPTs），侧重**MCP协议兼容性**和多提供商切换。 |
| **Gemini CLI** | **Google AI能力的前沿实验场** | 谷歌云开发者、A2A爱好者 | 强力推进**A2A (Agent-to-Agent)** 协议和**AST感知工具链**，技术探索性强，但稳定性稍弱。 |
| **Qwen Code** | **专注于Managed Agent的企业生产力工具** | 企业、平台开发者 | 提出**双路径Agent架构**，侧重**Runtime Broker、SDK生态**和**内存治理**，平台化意图明显。 |
| **OpenCode** | **开源、高度可定制的全能型CLI** | 开源社区、隐私敏感用户 | 基于插件的架构，支持**自定义提供商、本地模型（Zen网关）**，社区以解决底层性能和兼容性问题为主。 |
| **GitHub Copilot CLI** | **GitHub工作流的无缝延伸** | GitHub重度用户 | 与**GitHub生态（GitHub Actions、MCP）** 紧密绑定，侧重MCP服务器兼容和认证流程的便捷性。 |
| **Pi** | **推理友好、跨平台的个人Agent** | 技术爱好者、多模型用户 | 大胆尝试**Codemode**和MCP集成，对**推理模型**支持激进，同时也暴露了更多兼容性问题。 |
| **DeepSeek TUI** | **专注于Codewhale上游的TUI客户端** | DeepSeek/Codewhale社区 | **问题追踪细致**，聚焦于TUI渲染、MCP握手、权限传递等底层细节，处于快速迭代修复期。 |
| **Kimi Code CLI** | - (今日无活动) | - | 暂无法判断。 |

#### 5. 社区热度与成熟度

- **🔥 社区热度最高**：**Claude Code** 和 **OpenAI Codex**。两者的功能请求（多账户管理、Windows修复）均获得了极高的社区关注（👍数），反映了庞大的用户基础。Claude Code的Mods话题讨论空前，OpenAI Codex的版本发布频率（7次/日）也印证了其背后强大的开发支持。

- **🔥 快速迭代与探索期**：**Gemini CLI**、**Qwen Code**、**Pi** 和 **DeepSeek TUI**。这些工具社区活跃，但议题从重大架构提案（Qwen Code的双路径）到核心功能Bug（Gemini的Agent挂起，Pi的Compaction失败）以及稳定性回归（DeepSeek TUI的CPU退化）均有涉及，表明它们仍处于功能快速交付与问题修复并行的阶段。

- **中等活跃度**：**OpenCode** 和 **GitHub Copilot CLI**。OpenCode社区对内存问题（OOM/数据库膨胀）的长期追踪表明其用户基数稳固且专业，但核心稳定性问题尚未解决。GitHub Copilot CLI社区反应集中，但PR数较少，可能处于一次功能迭代后的稳定期。

- **观察期**：**Kimi Code CLI** 今日无活动，可能是周期性更新或开发重点转移，需要后续观察。

#### 6. 值得关注的趋势信号

1.  **“安全是增长的代价”**：社区对**安全分类器误报**的普遍抱怨（Claude Code, OpenAI Codex）是重要信号。AI工具的智能化必然带来更严格的安全审查，但“宁错杀”的策略会严重侵占开发者的信任和效率。**未来，可解释性和用户自定义的安全策略将是关键差异化要素。**

2.  **平台化竞赛已经开始**：**Claude Code的Mods** 和 **Qwen Code的Managed Agent** 代表了两种平台化路径。前者是通过**开放插件生态**吸引开发者，后者是通过**提供托管、可控的Agent运行时**服务企业。谁的模式更能解决开发者的实际痛点（如封装、安全、成本），谁就能占据下一个阶段的制高点。

3.  **Agent自治与状态管理是核心痛点**：多个工具出现Agent“挂起”、“误报成功”、“执行后状态未同步”等问题。这表明当前Agent模型的**可靠性**和**状态一致性**远未达到生产级要求。对于开发者而言，**短期应避免让Agent执行高度关键或不可逆的操作**，并关注工具在会话管理和任务回滚等方面的改进。

4.  **多模型兼容性是双刃剑**：支持多种模型（如GPT-6.1, Gemini, DeepSeek, Claude）已成为主流，但这给工具本身带来了巨大的**适配成本**。Pi、Gemini CLI、Qwen Code均出现了与特定模型行为不兼容的Bug。**这为专注于单一模型深度优化（如Claude Code）的方案留下了空间，也预示着“模型无关”的抽象层（如MCP协议）将成为生态基石。**

5.  **Token经济是下一个战场**：Qwen Code的“Non-conversation context token governance” Issue是一个明确的信号。随着Agent执行更长、更复杂的任务，上下文窗口管理与成本控制将不再是“优化项”，而是“必选项”。**能够提供更智能、更低成本的上下文压缩和优先级排序方案的工具，将在长期竞争中胜出。**

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

# Claude Code Skills 社区热点报告（数据截止 2026-09-30）

## 1. 热门 Skills 排行

以下 7 个 Pull Request 在社区中关注度最高，按评论活跃度（排名）排序。

| 排名 | 技能（PR） | 功能说明 | 讨论热点 | 状态 |
|------|------------|----------|----------|------|
| 1 | [fix(skill-creator): isolate trigger evals and handle Windows and runtime failures](https://github.com/anthropics/skills/pull/1298) | 修复 skill-creator 的触发评估模块，解决 Windows 子进程管道问题、运行时失败导致的假阴性、以及多 worker 竞争问题。 | Windows 兼容性、评估结果可靠性、CI 稳定性是核心焦点。社区关注如何避免“无效分数”误导优化。 | Open |
| 2 | [fix(mcp-builder): support mcp>=2 streamable_http_client import and custom headers](https://github.com/anthropics/skills/pull/1742) | 适配 MCP v2 中 `streamable_http_client` 的命名变更，并支持通过 `create_mcp_http_client` 配置自定义 HTTP 头。 | 依赖升级的 breaking change 处理、向后兼容性、用户自定义 header 场景（如认证、代理）。 | Open |
| 3 | [feat(skills): add proofcore-contract-auditor for smart contract notarization](https://github.com/anthropics/skills/pull/1771) | 新增 Web3 智能合约审计技能，支持 Solidity 和 Rust 静态分析，并将审计证明锚定到 TON 区块链。 | 区块链集成、零知识证明、自动化审计安全风险、社区对“去中心化信任”的热情。 | Open |
| 4 | [Add md2video-audio skill](https://github.com/anthropics/skills/pull/1703) | 将 Markdown 文档通过 Marp 转换成演示文稿幻灯片，再合成带真人语音的 MP4 视频，零成本。 | 内容生成工作流、语音质量、与现有文档工具的集成、潜在版权问题（语音模型）。 | Open |
| 5 | [Add pyxel skill for retro game development](https://github.com/anthropics/skills/pull/525) | 基于 Pyxel 框架的复古游戏开发技能，支持 headless 运行、帧检查、状态验证。 | 游戏开发自动化、测试手段（无头输入驱动、帧检测）、与 Claude 协作的边界。 | Open |
| 6 | [Add document-typography skill: typographic quality control for generated documents](https://github.com/anthropics/skills/pull/514) | 防止 AI 生成文档中的排版问题：孤行（orphan）、页首段落（widow）、编号错位。 | 排版质量标准、AI 文档的可读性、该技能适用于所有文档生成场景，实用性强。 | Open |
| 7 | [feat: add AWT (AI Watch Tester) — AI-powered E2E testing skill](https://github.com/anthropics/skills/pull/822) | 基于视觉和浏览器控制的零代码 E2E 测试工具，Claude 可自动生成测试用例并执行。 | 测试自动化、视觉定位的稳定性、与现有测试框架的对比、安全沙箱要求。 | Open |

## 2. 社区需求趋势

从 15 个最活跃的 Issues 中可以提炼以下主要需求方向：

| 需求主题 | 代表性 Issue | 说明 |
|----------|--------------|------|
| **安全与信任** | [#492 安全：社区技能冒充官方](https://github.com/anthropics/skills/issues/492)（43 评论，2 👍） | 社区技能在 `anthropic/` 命名空间下分发，导致用户混淆官方与第三方技能，形成信任边界漏洞。 |
| **组织级技能共享** | [#228 启用组织内技能共享](https://github.com/anthropics/skills/issues/228)（16 评论，8 👍） | 当前手动下载 + 上传模式效率低，社区强烈要求直接分享链接或共享技能库。 |
| **技能评估质量** | [#556 run_eval.py 触发率 0%](https://github.com/anthropics/skills/issues/556)（12 评论，7 👍） | 内置评估工具 `run_eval.py` 无法正确触发技能，导致所有测试零触发，影响技能开发和迭代。 |
| **技能自身稳定性** | [#62 技能消失且报错](https://github.com/anthropics/skills/issues/62)（10 评论）、[#189 插件重复安装](https://github.com/anthropics/skills/issues/189)（6 评论，9 👍） | 技能文件意外丢失、插件重复安装导致上下文膨胀，社区对基础可靠性不满。 |
| **特定领域技能** | [#1329 compact-memory（紧凑记忆）](https://github.com/anthropics/skills/issues/1329)（9 评论）、[#412 agent-governance（Agent治理）](https://github.com/anthropics/skills/issues/412)（6 评论） | 长上下文场景下需要符号化记忆表示；AI 代理系统需要安全治理模式。 |
| **上下文窗口管理** | [#1487 claude-api 技能注入 156k tokens](https://github.com/anthropics/skills/issues/1487)（4 评论） | 技能过度注入内容导致上下文窗口瞬间耗尽，影响正常对话。 |
| **跨平台兼容** |（隐含在多个 PR 和 Issue 中） | 如 skill-creator 的 Windows 支持、MCP builder 版本适配等。 |

**总结趋势**：社区最期望的是**技能生态的规范化**（命名空间、共享机制、评估工具）、**技能自身的稳定性**（避免冲突、内存泄漏、平台差异）以及**垂直场景技能**（智能合约审计、游戏开发、排版质量控制等）。

## 3. 高潜力待合并 Skills

以下 PR 评论活跃、功能明确且尚未合并，近期落地的可能性较高：

| 技能 | 链接 | 亮点 | 预计影响力 |
|------|------|------|------------|
| proofcore-contract-auditor | [PR #1771](https://github.com/anthropics/skills/pull/1771) | 首个 Web3 智能合约审计技能，结合区块链零存储 Merkle 协议。 | 拓展技能边界至区块链安全领域，吸引开发者社区。 |
| md2video-audio | [PR #1703](https://github.com/anthropics/skills/pull/1703) | 零成本将 Markdown 转为视频，适合教育、演示。若合并将极大降低视频制作门槛。 | 内容创作者的福音，可能成为最常用文档输出技能之一。 |
| notion-spec-to-implementation + quantitative-resume-auditor | [PR #1245](https://github.com/anthropics/skills/pull/1245) | 双技能：一个将产品规格转换为 Notion 执行任务，一个量化简历审计。 | 填补项目管理和招聘领域的空白。 |
| document-typography | [PR #514](https://github.com/anthropics/skills/pull/514) | 专注排版质量控制，解决 AI 文档的普遍痛点。 | 可嵌入任何文档生成流程，实用性强。 |
| AWT (AI Watch Tester) | [PR #822](https://github.com/anthropics/skills/pull/822) | 零代码 E2E 测试，Claude 直接操控浏览器。 | 可能改变前端测试范式，但安全审查需谨慎。 |

这些 PR 的合并时间受测试验证、安全审查和社区反馈影响，预计 1-2 个月内可能落地。

## 4. Skills 生态洞察

**当前社区最集中的诉求是：构建一个安全、可靠、可共享的技能生态，同时快速补充高价值的垂直场景技能，解决技能本身的稳定性问题（评估工具失效、平台兼容性、上下文失控）。**

---

好的，这是为您生成的 2026-09-30 Claude Code 社区动态日报。

---

# Claude Code 社区动态日报 | 2026-09-30

## 今日速览

社区讨论热度持续高涨，**Mods（插件）扩展性**与**多账户管理**两大功能请求持续霸榜。安全与权限控制成为今日绝对焦点：围绕“安全默认值”（Security Default）的多项PR合并，强化了组织的管控能力；同时，多个Bug报告揭露了安全分类器（Safety Classifier）误伤合法操作（如杀毒软件开发、网络安全研究）的问题，引发开发者广泛讨论。v2.1.285 版本也已发布，新增了桌面应用快捷启动和环境变量。

---

## 版本发布

### v2.1.285 发布
- **WebFetch 开关**：新增 `CLAUDE_CODE_DISABLE_WEB_FETCH` 环境变量，允许用户关闭 WebFetch 工具。
- **桌面应用集成**：新增 `claude --desktop` 命令，可在当前目录快速打开 Claude 桌面应用；支持通过 `--continue` / `--resume <id>` 参数直接恢复会话。
- **插件配置**：新增 `claude plugin configure <plugin>` 命令，用于展示插件配置。

---

## 社区热点 Issues

1.  **[#91870] Mods - make Claude 10x more extensible**
    - **热度**: 评论 225 | 👍 128
    - **摘要**: 社区翘首以盼的“Mods”功能（即函数钩子`function hooks`）核心issue。作者发布了社区更新，确认该功能将在数周内发布，并感谢社区的反馈设计。这是当前最受关注的功能，讨论持续火热。
    - **链接**: [Issue #91870](https://github.com/anthropics/claude-code/issues/91870)

2.  **[#18435] Add the ability to manage multiple Claude accounts**
    - **热度**: 评论 198 | 👍 841
    - **摘要**: 支持在桌面应用内管理多个Claude账户并轻松切换，是获赞数最高的功能请求。对于拥有多个工作或私人账户的开发者来说，这是核心痛点。
    - **链接**: [Issue #18435](https://github.com/anthropics/claude-code/issues/18435)

3.  **[#3301] Environment Contributions warning continuously reappears**
    - **热度**: 评论 50 | 👍 73
    - **摘要**: 一个持续了近一年半的BUG，在Cursor或VSCode中每次打开终端都会弹出“Claude Code想要重载终端”的警告。社区对这个问题积怨已久，亟需解决。
    - **链接**: [Issue #3301](https://github.com/anthropics/claude-code/issues/3301)

4.  **[#97854] Auto mode: server-side safety classifier intermittently returns no verdict**
    - **热度**: 评论 25 | 👍 33
    - **摘要**: **严重Bug**。在Auto模式下，服务器端安全分类器间歇性“罢工”，导致 `Bash` 和 `ScheduleWakeup` 等核心工具完全失效（即使是执行`echo ok`）。虽然似乎是偶发，但影响极大。
    - **链接**: [Issue #97854](https://github.com/anthropics/claude-code/issues/97854)

5.  **[#98145] 指定한 응답 언어(한국어)를 도구 호출 사이 중간 안내에서 반복적으로 지키지 않음**
    - **热度**: 评论 17 | 👍 0
    - **摘要**: 多语言支持问题。即使用户明确设置并使用韩语，模型在工具调用间的中间步骤仍会“忘记”规则，切换回英语。这反映了模型在严格遵循用户设定的语言指令上存在缺陷。
    - **链接**: [Issue #98145](https://github.com/anthropics/claude-code/issues/98145)

6.  **[#89599] [BUG] Claude Code desktop app (Windows MSIX): idle stealth update quits app...**
    - **热度**: 评论 13 | 👍 1
    - **摘要**: Windows平台的严重更新Bug。静默自动更新会导致应用退出后无法启动，错误代码 `0x80073D02`，除非手动杀掉后台残留进程。这严重影响了Windows用户的更新体验。
    - **链接**: [Issue #89599](https://github.com/anthropics/claude-code/issues/89599)

7.  **[#95566] Native binary hangs silently at 100% CPU on VMs with the kvm64 CPU model**
    - **热度**: 评论 7 | 👍 1
    - **摘要**: 兼容性Bug。在采用较老CPU模型（如kvm64）的虚拟机上，原生二进制文件会静默挂起并占满CPU。这说明工具对CPU指令集（如SSE4/POPCNT）有依赖，但缺少前置检查。
    - **链接**: [Issue #95566](https://github.com/anthropics/claude-code/issues/95566)

8.  **[#95050] [BUG] Claude Desktop 2.110.0 (Windows/MSIX): after a quit, every launch fails...**
    - **热度**: 评论 6 | 👍 0
    - **摘要**: Windows平台另一个启动故障Bug。退出后，下次启动会因 `renderer "launch-failed"` 错误而失败，需重启 `CoworkVMService` 才能恢复。与#89599类似，都与Windows应用打包和进程管理有关。
    - **链接**: [Issue #95050](https://github.com/anthropics/claude-code/issues/95050)

9.  **[#98169] Desktop app: auto mode classifier keeps blocking user-approved Claude in Chrome actions**
    - **热度**: 评论 2 | 👍 0
    - **摘要**: 权限Bug的典型案例。用户退出Auto模式后，安全分类器依然“残留记忆”，持续阻止用户在Chrome中的授权操作。会话状态与权限状态不同步。
    - **链接**: [Issue #98169](https://github.com/anthropics/claude-code/issues/98169)

10. **[#98289] [Bug] Anthropic API Error: Request blocked by safety guidelines for legitimate antivirus development**
    - **热度**: 评论 0 | 👍 0
    - **摘要**: 安全过滤器的**误报**问题。开发者在进行合法的杀毒软件开发时，被安全准则误伤，导致请求被拦截。这突显了在安全性与开发者自由之间的平衡挑战。
    - **链接**: [Issue #98289](https://github.com/anthropics/claude-code/issues/98289)

---

## 重要 PR 进展

1.  **[#98080] sec-default: a settings deny rule holds over an allow or ask from a plugin**
    - **状态**: 已合并
    - **摘要**: **安全增强**。此PR确保，在启用“安全默认值”的组织中，管理员设置的拒绝（Deny）规则的优先级高于用户安装插件赋予的允许（Allow）或询问（Ask）权限。强化了组织的安全基线。
    - **链接**: [PR #98080](https://github.com/anthropics/claude-code/pull/98080)

2.  **[#98083] sec-default: a managed option, allowManagedModsOnly, keeps the mods a person installs from loading**
    - **状态**: 已合并
    - **摘要**: **组织管控**。新增 `allowManagedModsOnly` 配置，允许组织只加载官方或受管的Mods，而拒绝用户自行安装的Mods，这对于企业级安全合规至关重要。
    - **链接**: [PR #98083](https://github.com/anthropics/claude-code/pull/98083)

3.  **[#97241] sec-default: the system prompt's sections continue past the user tier**
    - **状态**: 已合并
    - **摘要**: **安全增强**。此PR确保，在启用“安全默认值”后，用户的插件将无法再影响组织级的系统提示（System Prompt）构成，进一步防止了权限逃逸。
    - **链接**: [PR #97241](https://github.com/anthropics/claude-code/pull/97241)

4.  **[#98275] agents-md: send the AGENTS.md loaded line to the debug log**
    - **状态**: 已合并
    - **摘要**: **开发者体验**。当项目有 `AGENTS.md` 但无 `CLAUDE.md` 时，将加载信息从终端输出移至调试日志，避免了信息冗余，使界面更清爽。
    - **链接**: [PR #98275](https://github.com/anthropics/claude-code/pull/98275)

5.  **[#96434] security-guidance: keep denied and secret files out of the reviewer's reach**
    - **状态**: 开放中
    - **摘要**: **安全修复**。修复了一个安全审查流程中的漏洞：原先通过 `git diff` 等方式，审查者可以“看到”会话本身权限规则禁止读取的敏感文件（如 `secret.yaml`），现在将阻止此行为。
    - **链接**: [PR #96434](https://github.com/anthropics/claude-code/pull/96434)

6.  **[#97952] ci: security hardening for GitHub Actions workflows that call Claude**
    - **状态**: 开放中
    - **摘要**: **CI/CD安全**。对仓库中调用Claude的GitHub Actions工作流进行安全加固，包括添加出口防火墙等，防止凭证泄露，是开源项目安全的最佳实践。
    - **链接**: [PR #97952](https://github.com/anthropics/claude-code/pull/97952)

7.  **[#97334] sec-default: the rows a conversation keeps continue past the user tier**
    - **状态**: 开放中
    - **摘要**: 与#97241相辅相成，确保在安全默认值下，会话的某些关键信息流（rows）也能绕过用户层级，保障安全策略的完整性。
    - **链接**: [PR #97334](https://github.com/anthropics/claude-code/pull/97334)

8.  **[#97293] mods: the declarations carry process.run's truncation flags and list entries' mtimeMs**
    - **状态**: 开放中
    - **摘要**: **Mods API增强**。为Mods的 `process.run` 和 `fs.list` 等API添加了新的声明字段（如截断标志、文件修改时间），增强了Mods获取系统信息的能力，为更复杂的Mods开发铺路。
    - **链接**: [PR #97293](https://github.com/anthropics/claude-code/pull/97293)

9.  **[#94847] diff: the first edit opens the pane only when it has a file to list**
    - **状态**: 开放中
    - **摘要**: **UI/UX优化**。修复了一个行为：当首次编辑写入的文件在仓库之外或被 `.gitignore` 忽略时，不会打开空的“Diff”面板，避免了无意义的UI闪动。
    - **链接**: [PR #94847](https://github.com/anthropics/claude-code/pull/94847)

10. **[#98275] agents-md: send the AGENTS.md loaded line to the debug log**
    - **状态**: 已合并
    - **摘要**: 与上述#98275内容一致，因其是今日最重要的已合并PR之一，再次提及以强调其在改善开发者体验方面的作用。
    - **链接**: [PR #98275](https://github.com/anthropics/claude-code/pull/98275)

---

## 功能需求趋势

- **Mods / 插件系统 (Hooks & Plugins)**：以 `#91870` 为代表，社区对通过Mods扩展Claude Code功能的需求空前高涨，核心诉求是函数钩子和更高的可扩展性。
- **安全与权限精细化管理**：大量Issue围绕权限控制展开，包括对Auto模式分类器的限制、基于安全默认值的组织级管控（`#98080`, `#98083`）、以及更细粒度的工具权限白名单（`#92554`）。这表明随着Claude Code能力增强，企业和个人开发者对安全边界提出了更高要求。
- **成本控制与Token优化**：社区对“隐性Token消耗”非常敏感。多个Issue报告了工具（如Artifact `#91395`, Workflow `#79504`）在未使用时仍会加载其Schema，从而增加上下文开销和成本。开发者普遍呼吁提供禁用不必要的“Beta”工具的开关（`#94907`），以精确控制成本。
- **多账户管理**：`#18435` 表明，开发者希望在桌面应用中无缝切换多个Claude账号，以满足工作与个人使用的分离需求。
- **跨平台稳定性与体验一致性**：Windows平台的更新Bug（`#89599`, `#95050`）和Linux arm64架构的兼容性问题（`#98291`）表明，社区期望在桌面端获得更稳定、一致的体验。

## 开发者关注点

- **安全分类器误报**：开发者对安全分类器“宁可错杀一千”的策略感到沮丧。合法操作如网络安全研究（`#98211`）、杀毒软件开发（`#98289`）甚至用户授权的浏览器操作（`#98169`）都被误判，这严重影响了开发效率和信任感。
- **“自动模式”下的不可预测行为**：Auto模式下的问题频发，如分类器间歇性罢工导致核心工具失效（`#97854`），或退出模式后权限状态不清（`#98169`），这表明“Auto模式”的稳定性与状态管理是当前的一大技术短板。
- **Windows平台稳定性**：`#89599` 和 `#95050` 直指Windows MSIX打包应用更新和启动流程的严重缺陷，这已成为Windows用户的头号痛点。静默更新导致应用无法启动是极其糟糕的体验。
- **模型指令遵循性**：`#98145` 等Issue表明，即使通过设置和记忆明确指示，模型在执行任务时仍可能“遗忘”用户的根本性要求（如语言），这动摇了用户对模型可靠性的信心。
- **隐性Token浪费**：`#91395` 和 `#91775`（Usage统计翻倍）揭示了开发者对Token消耗的“锱铢必较”。他们不仅关心最终的成本，更关心成本构成的透明度和合理性，并对工具Schema的“预加载”行为表示不满。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报 - 2026-09-30

## 今日速览
Windows 用户终于等来了期待已久的控制台闪烁修复（v0.159.2），同时 GPT-6.1 Sol 成为默认模型。社区对随机欢迎消息的反感导致了两份重复提案，开发团队已合并 PR 予以移除。Windows 平台 bug 依然是社区反馈最集中的领域。

## 版本发布
过去 24 小时共发布 7 个版本（含 alpha 与稳定版），以下为重点更新：

- **rust‑v0.159.2**（稳定版）：修复 Windows 下 Codex 启动后台进程和沙箱命令时控制台窗口闪烁的问题（[#49385](https://github.com/openai/codex/pull/49385)）。
- **rust‑v0.159.1**（稳定版）：新增 GPT‑6.1 Sol 作为默认模型（捆绑目录及 Amazon Bedrock Mantle/Runtime 目录）；详情见 [Changelog](https://github.com/openai/codex/compare/rust-v0.159.0...rust-v0.159.1)。
- **rust‑v0.159.0**（稳定版）：引入可选 `instant_interrupt` 功能，允许新输入在模型响应或长时代码模式调用期间实时打断；新会话获得紧凑欢迎屏与统一头部，并附带随机问候语（后续被移除）。
- 另有多个 alpha 版本（v0.161.0‑alpha.1/2、v0.160.0‑alpha.6/6.1）持续开发中。

## 社区热点 Issues（10 条精选）

1. [#48074](https://github.com/openai/codex/issues/48074) **[Bug, Windows]** 安装 Codex 守护进程后，请求期间终端窗口反复闪烁  
   **重要性：** 117 条评论、139 👍，Windows 用户核心痛点。v0.159.2 已修复该问题，但社区持续关注是否彻底解决。

2. [#48043](https://github.com/openai/codex/issues/48043) **[Bug, Windows]** CLI v0.157.0 因守护进程权限错误无法启动（v0.156.1 正常）  
   **重要性：** 37 评论、36 👍，升级中断工作流，需紧急定位。

3. [#44768](https://github.com/openai/codex/issues/44768) **[Bug, Windows]** app‑server 守护进程为每个 hook 和 shell 命令弹出可见控制台窗口  
   **重要性：** 24 评论，与 #48074 部分重叠，影响开发体验。

4. [#48324](https://github.com/openai/codex/issues/48324) **[Bug, Windows]** ChatGPT 桌面版中 Codex 显示“无法加载组织设置”，Web/CLI 正常  
   **重要性：** 24 评论，阻止桌面用户正常使用 Codex 会话。

5. [#42243](https://github.com/openai/codex/issues/42243) **[Bug, App]** Codex Pet 浮动覆盖层在“收起”后再次出现  
   **重要性：** 23 评论、31 👍，macOS 用户普遍反馈的 UI 问题。

6. [#45835](https://github.com/openai/codex/issues/45835) **[Bug, 速率限制]** 频繁显示“所选模型已满载”，网络正常  
   **重要性：** 21 评论，影响 Pro Lite 订阅者，疑似配额计算异常。

7. [#25799](https://github.com/openai/codex/issues/25799) **[Bug, Windows / WSL]** 无法启动沙箱命令（WSL2 项目）  
   **重要性：** 19 评论，Windows + WSL 用户关键阻断。

8. [#41779](https://github.com/openai/codex/issues/41779) **[Bug, Windows]** 本地 API 启动被“policy blocked”拒绝  
   **重要性：** 15 评论，影响使用 exec_command 的开发者。

9. [#49322](https://github.com/openai/codex/issues/49322) **[Bug, Web]** 用量报告双倍计数（新旧视图不一致）  
   **重要性：** 最新上报（Sep 29），可能影响费用透明度。

10. [#48913](https://github.com/openai/codex/issues/48913) / [#48991](https://github.com/openai/codex/issues/48991) **[Enhancement]** 要求添加禁用随机欢迎消息的选项  
    **重要性：** 两份重复提案共 12 评论、27 👍，社区对“不必要噪音”的反感强烈。

## 重要 PR 进展（10 条精选）

1. [#49424](https://github.com/openai/codex/pull/49424) **[已合并]** 推断 Windows UNC 路径时支持正斜杠和混合斜杠  
   修复 `LegacyAppPathString` 将 `//server/share/project` 误判为 POSIX 路径的问题。

2. [#49416](https://github.com/openai/codex/pull/49416) **[已合并]** 省略多行 ANSI 警告中的载荷内容  
   防止大 payload 膨胀警告日志，改用结构化字段 `input_bytes` + `line_count`。

3. [#49415](https://github.com/openai/codex/pull/49415) **[已合并]** 截断协议调试输出中的输入文本  
   `ContentItem::InputText` 和 `UserInput::Text` 调试输出限制为前 512 字节，提升日志可读性。

4. [#49414](https://github.com/openai/codex/pull/49414) **[已合并]** 过滤 SQLite 日志中优雅关闭守卫与触发器的 TRACE 事件  
   默认日志级别设为 DEBUG，减少不必要噪声。

5. [#49407](https://github.com/openai/codex/pull/49407) **[已合并]** 在环境信息超时后恢复 exec‑server 会话  
   解决传输阻塞导致 `environment/info` 请求悬挂问题，增加 30 秒发送超时。

6. [#49406](https://github.com/openai/codex/pull/49406) **[已合并]** 支持通过 OpenAI API 密钥显式指定网络访问计划  
   新增 `api_key_cyber_access_programs` 与 `api_key_model_discovery` 选项，默认关闭。

7. [#49401](https://github.com/openai/codex/pull/49401) **[已合并]** 跨请求窗口保留实时工具调用元数据  
   防止持久化与聚合预算遗漏当前请求仍需的工具调用信息。

8. [#49395](https://github.com/openai/codex/pull/49395) **[已合并]** 移除 TUI 会话头部的随机欢迎消息  
   响应社区呼声（#48913/#48991），使会话头部仅显示 `model:` 和 `directory:`。

9. [#49389](https://github.com/openai/codex/pull/49389) **[已合并]** 序列化共享 Windows 沙箱账户的测试  
   避免并发测试导致密码轮换冲突，提升 CI 稳定性。

10. [#49385](https://github.com/openai/codex/pull/49385) **[已合并]** 回溯 Windows 控制台闪烁修复到 v0.159.2  
    基于 #49164 + #49308，仅包含关键补丁。

## 功能需求趋势
从最新 Issues 看，社区关注的三大方向：
- **Windows 平台体验**：控制台闪烁、权限错误、WSL 集成、白屏加载、策略阻止等占据多数议题。
- **会话 UI 与可定制性**：随机欢迎消息引发强烈反对（#48913/#48991），用户希望获得简洁、可配置的启动体验。
- **速率限制与配额可视化**：双倍计数（#49322）和“模型满载”误报（#45835）表明用户对用量透明度高度敏感。

## 开发者关注点
- 🚨 **Windows 痛点**：超过 50% 的热点 Issue 与 Windows 相关，尤其是守护进程引发的控制台窗口和权限问题，虽然 v0.159.2 已修补，但社区仍在观察稳定性。
- 😤 **欢迎消息争议**：v0.159.0 引入的随机问候语被批评为“无意义噪音”，团队快速移除（PR #49395），但短期内仍有用户遇到。
- 🔧 **配置与诊断**：多项 Issue 指向配置项（如组织设置加载失败、忽略策略）以及缺乏清晰的错误信息，开发者希望获得更详细的错误上下文。
- 🔄 **会话持久化**：项目/会话在更新后消失（#48875）、Android 端无法访问桌面 Sections（#49090）等问题影响工作流连续性。

*数据截止：2026-09-30 24:00 UTC，来源：github.com/openai/codex*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

## Gemini CLI 社区动态日报 — 2026-09-30

---

### 1. 今日速览

今日发布 **v0.63.0-preview.0** 和 **v0.62.0** 两个版本，主要修复连接重试进度显示及 A2A 服务器不支持的存储类型处理。社区讨论热点集中在**子代理恢复误报**、**通用代理挂起**以及**浏览器代理兼容性**等关键缺陷。PR 侧则围绕 **ChatRecordingService 增量补丁**、**Windows IME 光标**及**状态原子化持久化**等多项基础设施优化展开。

---

### 2. 版本发布

#### **v0.63.0-preview.0**  
- **亮点**: 修复 CLI 在连接恢复期间显示重试进度指示器（#28340）  
- **链接**: [Release v0.63.0-preview.0](https://github.com/google-gemini/gemini-cli/releases/tag/v0.63.0-preview.0)

#### **v0.62.0**  
- **亮点**: A2A 服务器在任务元数据端点中对不支持的存储类型进行早期返回（#29334）  
- **链接**: [Release v0.62.0](https://github.com/google-gemini/gemini-cli/releases/tag/v0.62.0)

---

### 3. 社区热点 Issues（10 条精选）

| 编号 | 标题 | 热度 | 重要性说明 |
|------|------|------|------------|
| [#22323](https://github.com/google-gemini/gemini-cli/issues/22323) | Subagent recovery after MAX_TURNS 被报告为 GOAL success | 💬 13 👍 2 | **严重逻辑缺陷**：子代理达到最大轮次后误报成功，导致用户认为任务已完成，实际未做任何分析。 |
| [#19873](https://github.com/google-gemini/gemini-cli/issues/19873) | Leverage model’s bash affinity via Zero-Dependency OS Sandboxing | 💬 9 👍 1 | **长期增强**：利用 Gemini 3 的原生 bash 能力，通过零依赖沙箱在保证安全的同时释放模型本地工具效率。 |
| [#21409](https://github.com/google-gemini/gemini-cli/issues/21409) | Generalist agent hangs | 💬 8 👍 8 | **高频痛点**：简单操作（如创建文件夹）就会导致通用代理无限挂起，社区已提交多个复现报告。 |
| [#22745](https://github.com/google-gemini/gemini-cli/issues/22745) | Assess the impact of AST-aware file reads, search, and mapping | 💬 7 👍 1 | **前沿探索**：评估 AST 感知工具对减少 token 消耗和提升代码读取精度的影响，集合多个子议题。 |
| [#21968](https://github.com/google-gemini/gemini-cli/issues/21968) | Gemini does not use skills and sub-agents enough | 💬 6 | **模型行为**：即使定义了技能和子代理，Gemini 也极少主动调用，需要用户显式指示，影响自动化水平。 |
| [#22267](https://github.com/google-gemini/gemini-cli/issues/22267) | Browser Agent ignores settings.json overrides | 💬 4 | **配置缺陷**：浏览器代理完全忽略全局/项目级 settings.json 中的 maxTurns 等覆盖设置，导致用户无法调整行为。 |
| [#22232](https://github.com/google-gemini/gemini-cli/issues/22232) | Enhance browser_agent resilience: Automatic session takeover and lock recovery | 💬 4 | **可靠性需求**：浏览器代理在遇到永久模式锁定（持久会话）时直接报错，而非自动接管或恢复。 |
| [#21983](https://github.com/google-gemini/gemini-cli/issues/21983) | browser subagent fails in wayland | 💬 4 👍 1 | **环境兼容**：在 Wayland 显示服务器下浏览器子代理直接退出，影响 Linux 用户使用。 |
| [#21000](https://github.com/google-gemini/gemini-cli/issues/21000) | Experiment with using native file tools for creating and maintaining the task tracker | 💬 4 | **任务机制**：探索用原生文件工具替代内存中的任务追踪，避免 token 浪费和会话间丢失。 |
| [#20079](https://github.com/google-gemini/gemini-cli/issues/20079) | ~/.gemini/agents/filename.md is not recognized if symlink | 💬 4 | **用户体验**：用户将 agent 定义文件符号链接到 agents 目录后不会被识别，降低配置灵活性。 |

---

### 4. 重要 PR 进展（10 条精选）

| 编号 | 标题 | 类型 | 要点 |
|------|------|------|------|
| [#26844](https://github.com/google-gemini/gemini-cli/pull/26844) | fix(cli): add missing CustomTheme properties to validation schema | 🐛 修复 | 补充 `ui.active` 等三个运行时属性到 Zod 验证 schema，消除启动时的“Unrecognized key”错误。 |
| [#29568](https://github.com/google-gemini/gemini-cli/pull/29568) | fix(core): implement append-only delta patching and bounded history windowing | 🐛 修复 | ChatRecordingService 改用增量追加（而非全量重写），并限制内存中保留的消息窗口，大幅降低 token 开销。 |
| [#29573](https://github.com/google-gemini/gemini-cli/pull/29573) | fix(cli): handle a registry port in sandbox image name parsing | 🐛 修复 | 修正镜像名解析时因端口号导致的标签丢失和 `/` 进入容器名的问题，支持带端口的 registry。 |
| [#29557](https://github.com/google-gemini/gemini-cli/pull/29557) | fix(cli): prevent CPU hang and quote swallowing on @ within code | 🐛 修复 | 修复在非交互模式下（`-p` + 管道输入）遇到 `@scope/pkg` 后引号吞没导致 100% CPU 锁死的问题。 |
| [#29560](https://github.com/google-gemini/gemini-cli/pull/29560) | fix(ui): ensure Windows ConPTY forwards IME cursor position | 🐛 修复 | 修复 Windows 上 CJK 输入法候选窗口锚定到右下角 footer 而非实际输入提示的问题。 |
| [#29564](https://github.com/google-gemini/gemini-cli/pull/29564) | fix(cli): preserve env placeholders during settings migration | 🐛 修复 | 设置迁移时保留 `${VAR}` 环境占位符，防止未触碰的配置项被展开为运行时值。 |
| [#29563](https://github.com/google-gemini/gemini-cli/pull/29563) | fix(core): keep line terminators when truncating | 🐛 修复 | `truncateString()` 现在保留换行符并将其计入长度限制，而不是静默删除。 |
| [#29558](https://github.com/google-gemini/gemini-cli/pull/29558) | fix(cli): persist state atomically and recover from backup on corruption | 🐛 修复 | 使用临时文件 + `fsync` + 原子重命名实现 state.json 安全写入，并提供 .bak 自动恢复和 .corrupt 保留。 |
| [#29457](https://github.com/google-gemini/gemini-cli/pull/29457) | fix(core): replace fuzzy requestedExplicitly logic with glob matching | 🐛 修复 | 修复 `read-many-files` 中二进制文件被误判为“显式请求”导致上下文膨胀的问题，改用 glob 严格匹配。 |
| [#29549](https://github.com/google-gemini/gemini-cli/pull/29549) | fix(acp): bridge PromptResponse.usage and emit usage_update notifications | 🐛 修复 | 在 ACP 模式（`--acp`）下填充标准协议字段并发送 `usage_update` 通知，解决 billing 高估约 3 倍的问题。 |

---

### 5. 功能需求趋势

从近期 Issue 和 PR 中可提炼出社区最关注的 **四个功能方向**：

| 方向 | 典型议题 | 说明 |
|------|----------|------|
| **AST 感知工具链** | #22745, #22746, #22747 | 使用抽象语法树驱动代码搜索、读取和映射，以减少 token 消耗和提高单次操作精度。 |
| **子代理/浏览器代理弹性** | #22232, #21432, #22741 | 自动接管锁定会话、支持后台运行（Ctrl+B）、报告子代理完整轨迹，提升长期任务可靠性。 |
| **持久化任务追踪** | #18836, #21000 | 替换内存中的 `WriteToDo` 为基于文件（CRUD）的任务管理，避免上下文腐烂和跨会话丢失。 |
| **零依赖沙箱与安全** | #19873 | 利用模型原生 bash 能力，通过轻量级 OS 沙箱执行命令，替代厚重容器方案，平衡安全与效率。 |

此外，**技能自动调用**（#21968）和**并行子代理协作**（#18287）也是用户高频呼吁的方向。

---

### 6. 开发者关注点

根据 Issue 评论和 PR 反馈，当前用户痛点和高频请求包括：

- **子代理状态混淆**：最大轮次后误报成功（#22323），且 `/bug` 报告不包含子代理上下文（#21763）。
- **通用代理稳定性**：简单操作（如创建目录）导致无限挂起，需强制禁用子代理才能工作（#21409）。
- **浏览器代理兼容性**：Wayland 下失败（#21983），忽略 `settings.json` 配置（#22267），持久会话锁定无法自动恢复（#22232）。
- **模型行为不佳**：不主动使用自定义技能/子代理（#21968），在随机位置创建临时脚本（#23571），执行破坏性 git 操作（#22672）。
- **配置与扩展限制**：symlink agent 不被识别（#20079），超过 128 个工具时返回 400 错误（#24246），自定义主题属性缺失验证（#26844）。
- **交互与输出问题**：`get-shit-done` 输出钩子导致崩溃（#22186），创建 Vite 应用时卡在交互提示（#22465），Windows IME 光标错位（#29560）。
- **数据一致性**：状态文件因断电或并发写入损坏（#29558），`truncateString` 静默删除换行符（#29563），设置迁移吞没环境变量（#29564）。

---

**结语**：今日动态显示出 Gemini CLI 团队在**稳定性修复**和**基础设施优化**上投入了大量精力，同时社区对**代理智能行为**、**跨平台兼容**和**工具链精确性**提出了更高期待。开发者可重点关注 v0.63.0-preview.0 中的连接重试改进及多项原子化持久化修复，以避免日常使用中的数据丢失和卡顿问题。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区日报 — 2026-09-30

## 今日速览
今日发布密集，一天内连续推送 v1.0.90-1 至 v1.0.90-5 五个补丁版本，集中修复了 MCP OAuth 令牌复用、模型提供商启动错误、文件监视风暴等问题。社区方面，CLI 持续返回 400 错误的 Issue（#1274）热度最高（31 条评论），Figma MCP 服务器集成故障（#4870）也引发广泛关注。同时，一项关于从 GitHub Release 自动发布 npm 包的 PR（#5000）正式提出，意味着 CLI 的发布流程将进一步规范化。

---

## 版本发布
过去 24 小时内共发布 5 个版本，全部为修复性更新：

- **v1.0.90-5**  
  - 修复：配置的提供商已提供模型时，不再在启动或模型选择器中显示“No supported model available”  
  - 修复：MCP 工具调用在服务器不断发送进度更新后仍能正常完成

- **v1.0.90-4**  
  - 修复：全新启动时不再打印登录过程中的“Failed to read model provider attribution”错误

- **v1.0.90-3**  
  - 新增：`--mcp-github-auth` 参数，将 GitHub 账户认证范围限定于已批准的 MCP 服务器来源  
  - 新增：路径访问提示中加入会话作用域的只读目录审批

- **v1.0.90-2**  
  - 其他修复和变更

- **v1.0.90-1**  
  - 修复：MCP OAuth 登录（如 Datadog）可复用仍在有效期内的缓存令牌  
  - 修复：已撤回的继续提示在会话恢复后不再保留

---

## 社区热点 Issues
以下 10 个 Issues 反映了当前社区最关注的问题与讨论：

1. **[#1274] [OPEN] CLI 持续返回 400 错误**  
   👤 unusualbob | 评论 31 | 👍 13  
   近几小时约 95% 的 code review 请求均返回 400 错误，用户怀疑问题可能在客户端或服务端。社区大量开发者跟进。  
   [链接](https://github.com/github/copilot-cli/issues/1274)

2. **[#1285] [OPEN] 组织级 Agent 不显示**  
   👤 SAhmeti | 评论 11 | 👍 14  
   在组织仓库下创建 Agent 后，CLI 和 VS Code 都看不到。涉及企业级集成与模板识别，对批量部署用户影响大。  
   [链接](https://github.com/github/copilot-cli/issues/1285)

3. **[#4870] [CLOSED] Figma MCP 远程服务器加载失败**  
   👤 Just-Jan | 评论 8 | 👍 12  
   `server/discover` 返回 `-32601` 被 CLI 视为致命错误，而 VS Code 工作正常。该问题已修复并在 v1.0.90-5 中体现。  
   [链接](https://github.com/github/copilot-cli/issues/4870)

4. **[#2861] [CLOSED] 会话压缩：三次重试后仍返回空响应**  
   👤 ronkeele | 评论 7 | 👍 5  
   对 Claude Opus 4.6 手动执行 `/compact` 连续失败，暴露模型在某些情况下无法返回有效压缩结果。  
   [链接](https://github.com/github/copilot-cli/issues/2861)

5. **[#4982] [OPEN] AI 模型在 Read Search View/Rg 工具调用时无限卡住**  
   👤 npechett-wtg | 评论 1 | 👍 0  
   并行文件读取/搜索调用中，部分调用永久无响应，只能手动中断。影响日常代码搜索类工作流。  
   [链接](https://github.com/github/copilot-cli/issues/4982)

6. **[#4805] [OPEN] 会话无法恢复：`inuse.<pid>.lock` 文件成为“僵尸”锁**  
   👤 daveroama | 评论 2 | 👍 0  
   宿主机崩溃后残留的锁文件导致会话永远无法重新打开，即使数据未损坏。需要运行时层面的锁回收机制。  
   [链接](https://github.com/github/copilot-cli/issues/4805)

7. **[#4515] [OPEN] MCP 工具结果同时暴露 `content` 和 `structuredContent`**  
   👤 rroesch1 | 评论 2 | 👍 0  
   当 MCP 工具同时返回两种格式时，CLI 未按规范仅使用 `structuredContent`，可能导致上下文混乱。  
   [链接](https://github.com/github/copilot-cli/issues/4515)

8. **[#4985] [OPEN] MCP 服务器环境变量 `secret` 占位符未传递到子进程**  
   👤 nathbooth | 评论 1 | 👍 0  
   macOS 下使用 `${secret:...}` 配置的密钥无法被 stdio MCP 服务器读取，导致认证失败。  
   [链接](https://github.com/github/copilot-cli/issues/4985)

9. **[#4894] [OPEN] 恢复长会话时滚动位置异常**  
   👤 zachbryant | 评论 1 | 👍 0  
   恢复长时间会话后，滚动条自动跳转到历史位置较前处，且用户难以拖动回到最新内容，影响浏览体验。  
   [链接](https://github.com/github/copilot-cli/issues/4894)

10. **[#3281] [CLOSED] 升级至 v1.0.46 后 CLI 无法启动**  
    👤 softwarezhen | 评论 7 | 👍 0  
    报错 `Cannot find native binding`，与 npm 可选依赖的已知 bug 相关。该场景虽已关闭但在社区中引发广泛讨论。  
    [链接](https://github.com/github/copilot-cli/issues/3281)

---

## 重要 PR 进展
当前仅有一条 PR 处于活跃状态：

- **[#5000] [OPEN] 从已发布的 Copilot CLI Release 自动发布 npm tarball**  
  👤 devm33 | 创建 2026-09-29  
  目的：npm 发布由 GitHub Release 触发，使用 OIDC 信任发布（trusted publishing），不再依赖 npm token。同时保留手动恢复路径。该 PR 将统一发布流程，降低运维风险。  
  [链接](https://github.com/github/copilot-cli/pull/5000)

---

## 功能需求趋势
从近期 Issue 与社区讨论中，用户最关注以下方向：

- **MCP 生态兼容性**：服务器发现、OAuth 授权、密钥传递、工具名含点号等问题反复出现，用户希望 CLI 能更严格遵循 MCP 规范，并提升对第三方 MCP 服务器的容错能力。
- **模型选择与稳定性**：多模型支持（BYOK、auto 模型）仍存在配置、压缩失败、400 错误等痛点，社区期望更可靠的模型切换和错误提示。
- **会话管理与 UI 优化**：会话恢复卡顿、滚动异常、锁文件残留等问题严重影响日常使用；请求/回答可折叠、快捷搜索等改进呼声渐高。
- **认证与权限简化**：OAuth 流程、组织级 Agent 可见性、锁屏/键盘输入冲突等反映出企业在批量部署时的认证痛点。
- **平台兼容性**：Windows ARM64 原生支持、macOS 键盘输入问题等提醒开发者仍需覆盖更多操作系统细节。

---

## 开发者关注点
综合近期反馈，开发者最直接的痛点和需求包括：

- **400 错误频发**：尤其是 code review 类请求，几乎无法正常使用，严重影响生产效率。
- **MCP 工具名中的点号被拒绝**：不符合 MCP 规范，导致某些第三方服务器无法正常工作。
- **Ctrl+Z 误触发退出**：终端中的撤销操作被 CLI 解释为退出信号，与开发习惯冲突。
- **文件监视事件风暴**：闲置时 CPU 飙升、日志暴增至 33GB，资源消耗失控。
- **会话锁文件无法自动回收**：意外崩溃后会话丢失，缺乏优雅的恢复机制。
- **“No supported model available” 误报**：虽已在 v1.0.90-5 中修复，但用户对此类初始错误提示敏感性极高。
- **希望 MCP 切换如技能一样简便**：目前需要输入命令，而技能可通过空格/回车切换，开发者期待统一交互。

> 以上为本日社区动态汇总，欢迎通过各 Issue/PR 链接参与讨论。

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 — 2026-09-30

## 今日速览

过去 24 小时内，OpenCode 社区修复了多个核心 Bug，包括 Copilot 推理努力值传递、OpenRouter 缓存策略遗漏以及 Zen API CORS 预检失败等问题。内存泄漏和数据库无节制膨胀仍是社区最关注的痛点，同时有多项针对 TUI 稳定性和模型兼容性的 PR 正在推进。

## 版本发布

过去 24 小时内无新版本发布。

## 社区热点 Issues

### 1. Memory Megathread — 内存问题集中追踪
- **链接**: [Issue #20695](https://github.com/anomalyco/opencode/issues/20695)
- **状态**: CLOSED | 评论: 147 | 👍: 112
- **为什么重要**: 社区内存问题的长期讨论帖，收集了大量堆快照。开发者呼吁不要猜测原因，只需提供堆转储。虽然已关闭，但仍是后续内存修复的参考源头。

### 2. 事件表无限制增长导致数据库膨胀至 13 GB+
- **链接**: [Issue #33356](https://github.com/anomalyco/opencode/issues/33356)
- **状态**: OPEN | 评论: 37 | 👍: 12
- **为什么重要**: 本地 SQLite 的 `event` 表从未被清理或压缩，长期运行实例中数据库体积膨胀至约 13 GB，占据磁盘 97–99%。无保留策略和压缩机制，是 2.0 版本最严重的性能隐患之一。

### 3. Zen 网关流式响应缺失 finish_reason
- **链接**: [Issue #43379](https://github.com/anomalyco/opencode/issues/43379)
- **状态**: OPEN | 评论: 9 | 👍: 1
- **为什么重要**: 使用 muse 系列模型通过 Zen 网关时，流式结束前不发送含 `finish_reason` 的 chunk，导致严格遵守 OpenAI 协议客户端进入重试循环。影响高级模型的高可靠性使用场景。

### 4. 自定义提供商图像输入拒绝后会话无法恢复
- **链接**: [Issue #52042](https://github.com/anomalyco/opencode/issues/52042)
- **状态**: OPEN | 评论: 8 | 👍: 0
- **为什么重要**: 当自定义 OpenAI 兼容模型拒绝图像输入后，粘贴的图像会一直保留在会话历史中，每次后续请求都触发同样的 400 错误，没有恢复路径。属于破坏会话可用性的严重 Bug。

### 5. TUI 间歇性内存耗尽 (OOM) — 24-28 GB
- **链接**: [Issue #51761](https://github.com/anomalyco/opencode/issues/51761)
- **状态**: OPEN | 评论: 6 | 👍: 1
- **为什么重要**: TUI 进程内存以 500MB–1GB/s 线性增长，不到一分钟即被 OOM 杀掉，无触发条件和 GC 锯齿。严重影响 v2 TUI 的日常可用性。

### 6. OAuth 预算被错误视为端点限制
- **链接**: [Issue #44821](https://github.com/anomalyco/opencode/issues/44821)
- **状态**: OPEN | 评论: 5 | 👍: 5
- **为什么重要**: 针对 ChatGPT OAuth 的转换逻辑将 Codex 产品预算（元数据）错误解释为实际端点限制，导致自动截断提前几十万 token。影响付费用户的 token 利用率。

### 7. OpenCode Go 订阅用户遭遇“账户资金不足”
- **链接**: [Issue #51424](https://github.com/anomalyco/opencode/issues/51424)
- **状态**: OPEN | 评论: 5 | 👍: 2
- **为什么重要**: 购买了 Go 订阅且使用率为 0% 的用户，仍然提示“Insufficient account funds”，无法使用 Kimi 等模型。暴露了计费系统状态计算或显示逻辑的 Bug。

### 8. GitHub Copilot GPT-6 模型未传递推理努力值
- **链接**: [Issue #51850](https://github.com/anomalyco/opencode/issues/51850)
- **状态**: CLOSED | 评论: 4 | 👍: 0
- **为什么重要**: 使用 Copilot 提供商调用 GPT-6 系列时，用户选择的 reasoning_effort 未被包含在请求中。已通过 PR #52182 修复，但暴露了适配器分类错误。

### 9. SIGILL 崩溃：AMD Zen 3 不支持 AVX-512
- **链接**: [Issue #38986](https://github.com/anomalyco/opencode/issues/38986)
- **状态**: OPEN | 评论: 3 | 👍: 0
- **为什么重要**: 打包的二进制包含 AVX-512 指令，AMD Ryzen 5 5600H (Zen 3) 因缺乏 AVX-512 支持而崩溃。影响大量中端 AMD CPU 用户。

### 10. Zen API CORS 头部仅返回给模型列表路由
- **链接**: [Issue #52178](https://github.com/anomalyco/opencode/issues/52178)
- **状态**: OPEN | 评论: 3 | 👍: 0
- **为什么重要**: 所有推理端点的预检请求返回 404，第三方浏览器客户端无法调用任何 Zen 模型。限制了 OpenCode 的浏览器集成能力。

## 重要 PR 进展

### 1. 新增模型门控自动批准模式
- **链接**: [PR #39015](https://github.com/anomalyco/opencode/pull/39015)
- **状态**: OPEN | 作者: mayanksingh09
- **摘要**: 为 TUI 添加可选的模型门控模式：小模型先审查每个重要操作，安全操作自动通过，危险操作弹窗确认。提升自动操作的信任度。

### 2. 修复命令加载时因模型字段误写而被丢弃
- **链接**: [PR #52195](https://github.com/anomalyco/opencode/pull/52195)
- **状态**: OPEN | 作者: simonether
- **摘要**: `.md` 命令文件的 frontmatter 中若 `model` 不是 `provider/model` 格式（如 `model: opus`），之前会被静默丢弃。现在正确解析并保留这些命令。

### 3. 识别 agent 创建请求并传递会话 ID
- **链接**: [PR #52193](https://github.com/anomalyco/opencode/pull/52193)
- **状态**: OPEN | 作者: Dante-dan
- **摘要**: `opencode agent create` 调用时缺少 `x-opencode-session` 头部，导致 OpenCode 平台无法识别会话。修复后正确标记该类请求。

### 4. 跳过插件系统转换用于标题生成
- **链接**: [PR #50490](https://github.com/anomalyco/opencode/pull/50490)
- **状态**: OPEN | 作者: monody0007
- **摘要**: 会话标题生成时若触发 `experimental.chat.system.transform` 插件转换，可能会追加上下文内容，破坏输出。现在标题生成跳过插件系统转换。

### 5. 容忍 Copilot 返回多个 reasoning_opaque 值
- **链接**: [PR #52190](https://github.com/anomalyco/opencode/pull/52190)
- **状态**: OPEN | 作者: param087
- **摘要**: 解决 Copilot 模型中 Claude Opus 5/5.5 和 Fable 5.1 每个工具调用前都发送一个新的 reasoning_opaque 导致解析错误的问题。现在允许合法地出现多个值。

### 6. 修复 Windows 默认服务端口冲突
- **链接**: [PR #49909](https://github.com/anomalyco/opencode/pull/49909)
- **状态**: OPEN | 作者: Hona
- **摘要**: 当端口被 WSL 转发或系统保留端口占用时，Windows 托管服务无法启动。该 PR 将默认端口移至安全区域，避免常见冲突。

### 7. 保留主题颜色的 Alpha 通道
- **链接**: [PR #51625](https://github.com/anomalyco/opencode/pull/51625)
- **状态**: OPEN | 作者: ericcurtin
- **摘要**: `tint()` 函数混合 RGB 时丢弃了 Alpha 通道，导致透明主题失效。修复后正确保留 Alpha 值。

### 8. 修复 Zen 网关 CORS 预检
- **链接**: [PR #52185](https://github.com/anomalyco/opencode/pull/52185)
- **状态**: OPEN | 作者: argszero
- **摘要**: 为所有 Zen API 路由（不仅是模型列表）添加 CORS 预检响应，解决 Issue #52178 中第三方浏览器无法调用任何模型的问题。

### 9. 为 OpenRouter 上的 Anthropic 和 Qwen 请求放置缓存断点
- **链接**: [PR #52110](https://github.com/anomalyco/opencode/pull/52110)
- **状态**: CLOSED | 作者: rekram1-node
- **摘要**: 修复 `applyCachePolicy` 跳过 OpenRouter 的 Bug，确保 Anthropic 和 Qwen 模型请求正确使用缓存断点，降低 API 费用。

### 10. 传递 Copilot 的推理努力值设置
- **链接**: [PR #52182](https://github.com/anomalyco/opencode/pull/52182)
- **状态**: CLOSED | 作者: rekram1-node
- **摘要**: Copilot Responses 适配器将 GPT-6 错误归类为非推理模型，忽略了用户选择的推理努力值。修复后正确传递该设置。

## 功能需求趋势

- **内存管理与数据库压缩**：多个 Issue（#20695、#33356、#51761）直接指向内存泄漏和数据库无节制膨胀，社区迫切需要持久化存储的保留/压缩策略。
- **简单聊天模式**：用户希望 OpenCode 能支持纯对话模式，不发送自动 prompt（#39399），反映部分用户对 IDE 代码辅助之外的基础聊天需求。
- **新模型/提供商集成**：请求包含 Nous Research 公开推理 API（#47515）、OpenRouter 缓存优化（#39009、#51726）、Bedrock 思维块兼容（#51481）等，表明社区对多模型生态的强依赖。
- **隐藏/自定义上下文控制**：用户希望控制模型上下文窗口的利用，如 OAuth 预算误判（#44821）、session ID 破坏跨会话缓存（#51007）等，暴露了上下文管理的精细需求。
- **平台无关性与兼容性**：AMD SIGILL（#38986）、Windows 服务端口冲突（#48640 相关）、macOS 签名问题（#46313）持续出现，跨平台兼容性仍是痛点。

## 开发者关注点

- **OOM 与稳定性**：TUI 和数据库的无限增长是最高频的崩溃诱因，开发者期望团队优先处理垃圾回收和压缩机制。
- **计费与订阅混乱**：Go 订阅用户显示资金不足、自动续费支付引导不清晰（#25170、#52191、#51424），计费系统的透明度和交互改进需求强烈。
- **自定义提供商可用性**：自定义 OpenAI 兼容提供商在桌面 GUI 中无法保存（#51330），且遇到图像输入后会话不可恢复（#52042），严重阻碍自建模型用户。
- **CORS 与浏览器集成**：Zen API 缺乏 CORS 支持使得浏览器应用无法利用 OpenCode 模型，限制了生态扩展。
- **模型请求细节传递**：推理努力值（#51850）、缓存控制（#51726）、finish_reason（#43379）等协议细节遗漏，暴露了适配器层的测试覆盖面不足。

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 | 2026-09-30

## 今日速览

Pi 今日发布 **v0.99.1**，默认启用 GPT-6.1 Sol 模型；同时 v0.99.0 引入了 **Codemode 和 MCP 服务器连接**能力，工具调用范式迎来重大升级。社区围绕 **Windows 生态适配**、**自动压缩（Compaction）与推理模型兼容性**、以及 **中文渲染** 等议题展开密集讨论，Issue 当日更新量达 50 条，PR 活跃度也显著提升。

## 版本发布

### [v0.99.1](https://github.com/earendil-works/pi/releases/tag/v0.99.1)（2026-09-30）

- **新模型：GPT-6.1 Sol** — 已上线 OpenAI、Azure OpenAI 及 OpenAI Codex，现为 OpenAI Codex 默认模型。
- 相关文档：`packages/coding-agent/docs/models.md#select-a-model`

### [v0.99.0](https://github.com/earendil-works/pi/releases/tag/v0.99.0)（近期）

- **Codemode 与 MCP 集成**：可连接 MCP 服务器，让模型并行执行 JavaScript 调用工具。
- 新增文档：`docs/mcp.md` 与 `docs/codemode.md`。

---

## 社区热点 Issues（精选 10 条）

### 1. [#7547 Windows 适配大讨论](https://github.com/earendil-works/pi/issues/7547)
- **状态**：开放 | **评论** 69 | 👍 2  
- **摘要**：Windows 上运行 Pi 的多种方式碎片化严重，社区呼吁官方聚焦核心场景（修复 Bug、完善文档、开箱即用）。这是当前最活跃的 Issue，反映了 Windows 开发者规模与当前支持力度之间的落差。

### 2. [#10033 Compaction 与推理模型冲突](https://github.com/earendil-works/pi/issues/10033)
- **状态**：已关闭 | **评论** 8 | 👍 1  
- **摘要**：DeepSeek V4.1 等推理模型返回完整思考文本后，`serializeConversation()` 将所有思考块塞入摘要提示，导致自动压缩永远失败。直接影响长会话稳定性，已合修复。

### 3. [#10074 Anthropic 工具调用非 ASCII 参数损坏](https://github.com/earendil-works/pi/issues/10074)
- **状态**：开放 | **评论** 5 | 👍 0  
- **摘要**：Claude 模型编辑含韩文的文件时，`edit` 调用中非 ASCII 转义序列被静默破坏（如 `\uXXXX` 丢失 `u` 导致控制字符）。已追踪三周，严重影响多语言文件处理。

### 4. [#10184 ChatGPT 登录：`invalid_client`](https://github.com/earendil-works/pi/issues/10184)
- **状态**：已关闭 | **评论** 3 | 👍 6  
- **摘要**：`/login openai` 跳转至 ChatGPT 授权时显示“App unavailable”，错误码 `invalid_client`。社区高赞反馈，表明 OAuth 配置存在问题。

### 5. [#10182 0.99.0 包缺失导致 ChatGPT 登录失败](https://github.com/earendil-works/pi/issues/10182)
- **状态**：已关闭 | **评论** 3 | 👍 4  
- **摘要**：发布包中缺少 `openai-chatgpt.js`，导致登录模块无法加载。影响 v0.99.0 用户，已紧急修复。

### 6. [#10154 中文 `**bold**` 渲染失败](https://github.com/earendil-works/pi/issues/10154)
- **状态**：开放 | **评论** 4 | 👍 0  
- **摘要**：中文场景下，加粗标记 `**` 在 CJK 标点与字符间渲染为字面量。这是回归问题（#3353 未完全修复），影响大量中文用户阅读体验。

### 7. [#10198 提示提交延迟随会话长度增长](https://github.com/earendil-works/pi/issues/10198)
- **状态**：已关闭 | **评论** 2 | 👍 0  
- **摘要**：v0.99.0 中 `getBranchSelection` 为每条助手消息重新合并模型目录，导致延迟线性增长。已引入记忆化优化。

### 8. [#10045 Bedrock 上 Opus 5.5 自动压缩被 Anthropic 策略阻止](https://github.com/earendil-works/pi/issues/10045)
- **状态**：开放 | **评论** 4 | 👍 0  
- **摘要**：通过 Bedrock 使用 Opus 5.5 时，自动压缩因违反 Anthropic 逆向工程限制被阻止。影响企业用户。

### 9. [#10144 队列提示未批量发送](https://github.com/earendil-works/pi/issues/10144)
- **状态**：开放 | **评论** 4 | 👍 0  
- **摘要**：`run sleep 20` 执行期间连续发送多个提示，实际仅发送第一个。用户反映此前 Issue #10046 被关闭，重新提交。

### 10. [#10157 Gemini 工具调用思考签名被丢弃](https://github.com/earendil-works/pi/issues/10157)
- **状态**：开放 | **评论** 2 | 👍 0  
- **摘要**：Google AI Studio OpenAI 兼容端点返回的 `thought_signature` 在 Pi 重放时丢失，导致后续请求不正确。影响 Gemini 工具调用路由。

---

## 重要 PR 进展（精选 10 条）

### 1. [#10194 Anthropic OAuth 增加“复制代码”登录方式](https://github.com/earendil-works/pi/pull/10194)
- **状态**：开放  
- **摘要**：新增基于 HTTP 代码的登录流，解决远程服务器上本地重定向无法使用的问题。作者在生产环境验证。

### 2. [#10190 原生 Provider 注册时更新认证快照](https://github.com/earendil-works/pi/pull/10190)
- **状态**：已合并  
- **摘要**：修复 `registerNativeProvider()` 不更新 auth 快照导致初始模型选择认为 Provider 未配置的问题。

### 3. [#10176 OpenAI 新增替代登录方式](https://github.com/earendil-works/pi/pull/10176)
- **状态**：已合并  
- **摘要**：为 OpenAI Provider 增加除重定向外的登录备选方案。

### 4. [#10174 内置扩展被替换时显示警告](https://github.com/earendil-works/pi/pull/10174)
- **状态**：已合并  
- **摘要**：当用户自定义 `/mcp` 扩展覆盖内置扩展时，加载时弹出警告，提升透明性。

### 5. [#10122 托管 llama.cpp 服务器模式](https://github.com/earendil-works/pi/pull/10122)
- **状态**：开放  
- **摘要**：`/login llama.cpp` 可让 Pi 自动启动 `llama-server`，通过独立守护进程管理，在最后一个 Pi 进程断开后停止。极大降低本地部署门槛。

### 6. [#10165 追踪丢弃的用户 Bash 输出](https://github.com/earendil-works/pi/pull/10165)
- **状态**：开放  
- **摘要**：用户 `!` 命令可能丢弃早期输出但报告 `truncated: false`，导致模型无截断通知。此 PR 跟踪丢弃内容并在结果中传递。

### 7. [#10159 内置扩展可通过 `pi config` 禁用](https://github.com/earendil-works/pi/pull/10159)
- **状态**：已合并  
- **摘要**：`mcp`、`llama.cpp`、`codemode`、`tool-search` 等内置扩展现在可以全局或项目级别禁用，使用 `builtin:<name>` 路径命名。

### 8. [#10158 修复 Llama 缓存上下文重载](https://github.com/earendil-works/pi/pull/10158)
- **状态**：已合并  
- **摘要**：修复卸载后重建模型目录时丢失 `meta.n_ctx`，导致缓存运行时上下文窗口被覆盖的问题。

### 9. [#10156 可配置鼠标滚轮滚动](https://github.com/earendil-works/pi/pull/10156)
- **状态**：已合并  
- **摘要**：在全屏模式下支持配置普通滚轮和 Alt 滚轮行为，可通过 `/settings` 或 `settings.json` 设置，修复 #9758。

### 10. [#10100 增加推理摘要分离的回归测试](https://github.com/earendil-works/pi/pull/10200)
- **状态**：已合并  
- **摘要**：为推理模型添加测试，确保推理事件以 `thinking_*` 发出，最终输出保持 `text_*`。

---

## 功能需求趋势

从近期 Issue 和 PR 中，社区重点关注以下方向：

1. **多模型与推理模型兼容性**：DeepSeek V4.1、Claude Opus 5.5、Gemini、GPT-6.1 Sol 等模型对 Compaction、工具调用、思考签名的支持需要针对性适配。
2. **Windows 生态扩展**：#7547 揭示大量 Windows 开发者希望得到官方支持的场景优先级指南，包括 WSL、原生启动、Docker 等。
3. **登录与认证体验**：ChatGPT/OpenAI 登录失败、Anthropic 代码登录、MCP OAuth 链接可点击等问题突出，用户期望更流畅的认证流程。
4. **渲染与国际化**：中文加粗、CJK 标点、多行语法高亮丢失等 bug 影响非英文用户的日常使用。
5. **性能与长会话**：提示提交延迟线性增长、自动压缩失败、Idle 缓存刷新机制缺陷等，表明社区对长时间运行 agent 的稳定性有高要求。
6. **扩展系统自省**：内置扩展可禁用、包验证统一、Nix flake 支持等，体现向更可预测的依赖管理和分发演进。

---

## 开发者关注点

- **痛点集中**：Windows 支持碎片化（#7547）是呼声最高的议题；非 ASCII 文件编辑损坏（#10074）对国际用户影响严重；中文渲染回归（#10154）使得日常体验不佳。
- **高频请求**：对 MCP 集成后工具调用稳定性的担忧（#10192 隐藏工具仍被广告）、登录流故障（#10184、#10182）急需修复；自动压缩与推理模型的不兼容（#10033）让长 session 用户苦恼。
- **性能优化**：提示提交延迟（#10198）、空闲时 CPU 占用（#10191）、GC 开销等细节被社区深挖，表明高级用户已进入微观性能调优阶段。
- **安全与合规**：Bedrock 违反 Anthropic 策略（#10045）提示跨云合规边界；`Illegal invocation` 在 Cloudflare Workers 环境（#10188）限制了边缘部署能力。
- **打包与安装**：`npm install` 拉取全部 26 平台 esbuild 二进制（#9979）导致体积膨胀，影响 CI/CD 环境；`pnpm uninstall` 重写 lockfile（#10202）带来意外副作用。

---

*数据来源：GitHub [earendil-works/pi](https://github.com/earendil-works/pi)（data sourced via badlogic/pi-mono）*  
*日报生成时间：2026-09-30 23:59 UTC*

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 | 2026-09-30

---

## 📌 今日速览

Qwen Code 团队于今日正式发布 **v0.24.7 稳定版** 及同名桌面客户端，同步推出 **TypeScript SDK v0.1.17**。社区热议焦点集中在 **Managed Agent 双路径架构设计（#12380）** 和 **非对话上下文 Token 治理（#12028）** 两大长期规划上，两者均处于密集讨论阶段。此外，多项针对 Runtime Broker、工具调用桥接及性能的内存相关 PR 正在积极合入。

---

## 🚀 版本发布

### 1. Qwen Code v0.24.7 (正式版)
- **发布链接**: [v0.24.7](https://github.com/QwenLM/qwen-code/releases/tag/v0.24.7)
- **更新内容**:
  - 新增 `feat(managed-agent): admit workspace-bound sessions without execution`（在托管代理中支持无执行的工作区会话绑定）。
  - 修复：`fix(core): align Code Mode text with lazy tool discovery`、`fix(permissions): honor approved` 等。
  - 无 Breaking Changes。

### 2. Qwen Code Desktop v0.24.7
- **发布链接**: [desktop-v0.24.7](https://github.com/QwenLM/qwen-code/releases/tag/desktop-v0.24.7)
- **更新内容**:
  - 修复：`fix(serve): preserve session creation failure diagnostics`。
  - 新增：`feat(sdk-java): Add managed runtime`。

### 3. SDK TypeScript v0.1.17
- **发布链接**: [sdk-typescript-v0.1.17](https://github.com/QwenLM/qwen-code/releases/tag/sdk-typescript-v0.1.17)
- **更新内容**: 捆绑 CLI 版本 0.24.7，内部构建时序相同。

---

## 🔥 社区热点 Issues（10 条精选）

| # | Issue | 重要性 | 社区反应 | 链接 |
|---|-------|--------|----------|------|
| 1 | **proposal(serve): Define Managed Agent dual-path architecture and staged delivery** (#12380) | 核心架构提案，规划托管代理的双路径设计与分阶段交付，影响未来 Session 管理、Workspace 绑定等多方面。 | 37 条评论，标记 `need-discussion`，多人参与设计讨论。 | [链接](https://github.com/QwenLM/qwen-code/issues/12380) |
| 2 | **tracking(core): non-conversation context token governance** (#12028) | 长期跟踪 Issue，针对系统提示、工具 Schema、上下文文件等非对话 Token 的开销进行治理。 | 15 条评论，多个子 Issue（#12326、#12333、#13004 等）从中衍生。 | [链接](https://github.com/QwenLM/qwen-code/issues/12028) |
| 3 | **feat(managed-agent): Admit read-only search tools in a new Hosted Workspace profile** (#13030) | 提议为托管工作区添加只读搜索工具（list_directory、glob、grep_search），扩展代理能力。 | 7 条评论，优先级 P2。 | [链接](https://github.com/QwenLM/qwen-code/issues/13030) |
| 4 | **feat(managed-agent): Stage D follow-ups for durable lifecycle, Turns, Actions, ...** (#12867) | 承接 #12380 的 D 阶段后续，涉及持久化生命周期、Turns/Actions 定义、AgentDefinition 等。 | 5 条评论，多角色参与。 | [链接](https://github.com/QwenLM/qwen-code/issues/12867) |
| 5 | **SDK abort or close leaves the relaunched CLI worker running** (#13016) | 严重 Bug（P1）：SDK 中止或关闭后，重新启动的 CLI 工作进程未终止，导致资源泄漏。 | 5 条评论，需紧急修复。 | [链接](https://github.com/QwenLM/qwen-code/issues/13016) |
| 6 | **Deferred `tool_call` schema allows empty arguments for tools with required fields** (#12889) | 延迟工具调用桥接允许工具必需字段为空，导致运行时错误。 | 5 条评论，已标记为 `ready-for-human`。 | [链接](https://github.com/QwenLM/qwen-code/issues/12889) |
| 7 | **perf(memory): add a bounded cooldown after no-op extraction** (#13004) | 内存提取优化：无操作后增加冷却期，避免频繁无用的提取任务。 | 5 条评论，社区关注性能。 | [链接](https://github.com/QwenLM/qwen-code/issues/13004) |
| 8 | **Ctrl + arrow key sends raw C0 byte to pty** (#13068) | Shell 模式下 Ctrl+方向键等组合键被错误发送为原始控制字节，导致终端混乱。 | 4 条评论，用户体验影响大。 | [链接](https://github.com/QwenLM/qwen-code/issues/13068) |
| 9 | **fix(runtime-broker): a provider start refused answers `200 prepared`, client waits forever** (#13059) | Broker 在提供者被拒绝时错误返回 200，导致客户端永久等待。 | 4 条评论，中等优先级。 | [链接](https://github.com/QwenLM/qwen-code/issues/13059) |
| 10 | **tool_call bridge refuses intermittently: "params must NOT have additional properties"** (#13070) | 延迟工具桥接间歇性拒绝合法参数，影响工具调用稳定性。 | 3 条评论，需更多复现信息。 | [链接](https://github.com/QwenLM/qwen-code/issues/13070) |

---

## 🔧 重要 PR 进展（10 条精选）

| # | PR | 说明 | 状态 | 链接 |
|---|-----|------|------|------|
| 1 | **fix(managed-agent): Settle task event and cancel semantics** (#12998) | 稳定托管代理的任务事件与取消语义，定义持久化保留策略与游标标识。 | OPEN，作者 wenshao | [链接](https://github.com/QwenLM/qwen-code/pull/12998) |
| 2 | **fix(core): stop MCP server rules from authorizing a colliding server** (#12531) | 修复 MCP 服务器授权匹配中的名称冲突问题，消除 `sanitizeToolNameForProvider()` 的丢失比较。 | OPEN，更新至 9/30 | [链接](https://github.com/QwenLM/qwen-code/pull/12531) |
| 3 | **fix(core): pre-validate bridged tool_call arguments against the target schema** (#12901) | 在桥接工具调用前预校验参数 Schema，提前报告必需字段/类型错误，而非无标签错误。 | OPEN，更新至 9/30 | [链接](https://github.com/QwenLM/qwen-code/pull/12901) |
| 4 | **feat(managed-agent): ask for Hosted tool approvals (D6a)** (#13071) | 托管代理现在需要审批窗口，在未预批准的调用前等待确认，扩展了 D 阶段功能。 | OPEN，更新至 9/30 | [链接](https://github.com/QwenLM/qwen-code/pull/13071) |
| 5 | **fix(core): keep delivered notification turns out of ACP rewind ordinals** (#13029) | 修复 ACP 回退时错误计数通知轮次的问题，避免影响回退语义。 | OPEN | [链接](https://github.com/QwenLM/qwen-code/pull/13029) |
| 6 | **fix(runtime-broker): answer a refused provider start as unknown instead of prepared** (#13064) | Broker 在提供者拒绝后返回 409 未知状态而非 200 prepared，避免客户端死等。 | OPEN，自述已审阅 | [链接](https://github.com/QwenLM/qwen-code/pull/13064) |
| 7 | **fix(core): stop misdiagnosing malformed tool-call args as max_tokens truncation** (#12982) | 修复流式解析器将格式错误的工具调用参数误判为 max_tokens 截断的问题。 | OPEN | [链接](https://github.com/QwenLM/qwen-code/pull/12982) |
| 8 | **feat(memory): bundle Mem0 with the main CLI** (#12891) | 将 Mem0 内存后端集成到主 CLI，支持配置 endpoint 和 envKey，自动注册 MCP 服务器。 | OPEN，待 review | [链接](https://github.com/QwenLM/qwen-code/pull/12891) |
| 9 | **feat(managed-agent): Implement private Hosted MCP runtime (H1)** (#12946) | 实现私有托管 MCP 运行时 Profile，涵盖 Hosted→Broker→Runtime 连接、标准 I/O 与 SSE 支持。 | OPEN | [链接](https://github.com/QwenLM/qwen-code/pull/12946) |
| 10 | **fix(ci): fall back to pinned yamllint when runner image copy is stale** (#12650) | CI 加固：当自托管 runner 镜像的 yamllint 过期时自动回退到固定版本。 | OPEN，自述已审阅 | [链接](https://github.com/QwenLM/qwen-code/pull/12650) |

---

## 📈 功能需求趋势

从近期 Issues 与 PR 中提炼出社区最关注的 **五个方向**：

1. **Managed Agent 架构深化**  
   - 双路径设计（#12380）、持久化生命周期（#12867）、托管工作区工具权限（#13030）、私有 MCP 运行时（#12946）等持续迭代。  
   - 社区希望代理能安全、稳定地执行远程工具，并支持审批流程。

2. **Token 与上下文性能优化**  
   - 非对话 Token 治理（#12028）驱动了多个子 Issue：eager 工具表面选择、CI 基准对比、内存提取冷却（#13004）等。  
   - 目标是降低大型上下文模型的 Token 消耗，同时不牺牲工具召回率。

3. **内存与持久化能力增强**  
   - Mem0 集成（#12891）表明社区希望支持外部记忆系统；结构化内存的快速召回（#13003）、事件驱动内存召回（#13063）等提案活跃。

4. **工具调用稳定性与桥接改进**  
   - 延迟工具调用桥接的 Schema 校验（#12901、#12982）、空参数拒绝（#12889）、间歇性拒绝（#13070）等问题被反复提及。  
   - 开发者要求工具调用具备可预测的失败反馈。

5. **SDK 与运行时生态**  
   - TypeScript/Java SDK 的发布与纠错（#13016、#13017）、Runtime Broker 的容错与边界条件修复（#13059、#13060、#13064）成为近期高频修改区域。

---

## 👨‍💻 开发者关注点（痛点和反馈）

- **SDK 资源泄漏**：`SDK abort 后 CLI worker 残留`（#13016）被标记为 P1，需要立即修复。类似地，`per-Session 索引不释放`（#13042）也引起注意。
- **终端交互 bug**：`Ctrl+方向键`等组合键在 Shell 模式下发送原始控制字节（#13068），影响日常使用，反馈强烈。
- **测试稳定性**：`ManagedAgentServerIntegrationTest 与 recovery scanner 竞争`（#13031）、`fault gate 测试 flaky`（#13017）多次出现，社区建议增加隔离与超时控制。
- **工具调用健壮性**：`Deferred tool_call 空参数`、`间歇性拒绝` 问题导致需要多次重试，开发者期望提供更明确的错误码和自动重试机制。
- **文档与配置帮助**：`Hosted Runtime Broker 选项帮助不清晰`（#13044）是细小但影响体验的问题；Flyway 迁移版本重复防护（#12965）则是内部 CI 改进。

---

*数据来源：QwenLM/qwen-code GitHub 仓库（统计时间截止 2026-09-30 12:00 UTC）*

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

# 🐋 DeepSeek TUI 社区动态日报 | 2026-09-30

---

## 📌 今日速览

昨日 **Codewhale**（即 DeepSeek TUI 上游）提交强度极高：**0.10.1 集成分支**（#6782）正式启动，多名贡献者提交了 MCP 握手、TUI 渲染、配置可调性等关键修复。社区焦点集中在 **EPIC-005 架构分解**（#5316）即将完成、**`/retry` 仅回滚 UI 而模型上下文未同步**（#6788）以及 **CPU 使用率从 v0.9.12 到 v0.10.0 持续退化**（#6728）三大问题上。Windows 多行粘贴回归（#6427）已在 0.10.0 中确认，修复正在集成中。

---

## 🐛 社区热点 Issues（10 个）

1. **[#5316] EPIC-005: CodeWhale TUI Crate 分解（全景）**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/5316)  
   **30 评论** | **更新 2026-09-29**  
   **为什么重要**：FEAT-030 及整个 debug 命令组已合并入 `main`（PR #6707），这是整个架构从单体到插件化 crate 分拆的里程碑。分解完成后将直接影响 TUI 的扩展性和稳定性。

2. **[#6427] 0.10.0 回归：Windows Terminal 多行粘贴会逐行自动提交**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6427)  
   **4 评论** | **更新 2026-09-29**  
   **为什么重要**：0.10.0 重新破坏了 #5981 的修复，Windows 用户每粘贴多行内容就会触发多条消息自动发出，严重影响工作流。社区已反馈复现步骤。

3. **[#6651] TUI 界面无法实时刷新（终端失焦时）**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6651)  
   **2 评论** | **更新 2026-09-29**  
   **为什么重要**：当终端窗口被其他窗口遮盖时，TUI 不再刷新内容，影响用户监控 Agent 状态。基础体验 bug。

4. **[#6699] SSE 请求未收到响应头时 turn 直接失败且无重试**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6699)  
   **2 评论** | **更新 2026-09-29**  
   **为什么重要**：网络瞬断导致整个交互回合直接终止，而同一路径其他失败模式有重试预算。该问题已催生配置化提案（#6700）。

5. **[#6721] 紧急压缩（compaction）对“保存会话”任务的影响**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6721)  
   **1 评论** | **更新 2026-09-30**  
   **为什么重要**：Agent 在执行保存会话时被 compaction 截断，导致上下文丢失。用户报告了潜在的数据可靠性风险。

6. **[#6573] 多个 TUI 会话在子 agent 存储上争用 → CPU 自旋**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6573)  
   **1 评论** | **更新 2026-09-29**  
   **为什么重要**：同时运行多个独立 TUI 实例会因共享存储的锁争用导致 CPU 100% 空循环，影响多开场景。FreeBSD 上复现，推测跨平台。

7. **[#6704] TUI 文本背景显示异常**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6704)  
   **1 评论** | **更新 2026-09-29**  
   **为什么重要**：运行约半小时后文本背景变黑，退出重进后恢复。可能是渲染缓存或色彩资源泄漏。

8. **[#6788] 0.10.0 中 `/retry`（及 `/undo`）只回滚 UI 层：模型上下文与持久化会话仍保留被撤销的消息**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6788)  
   **0 评论** | **更新 2026-09-30**  
   **为什么重要**：昨日新建且最严重语义 bug。`/retry` 仅擦除了 UI 转录，实际发给模型的历史消息仍在累积，导致 AI 看到重复上下文，且退出后重载会话时所有被撤销消息恢复。这违背了用户对 Undo 的基本预期。

9. **[#6728] CPU 使用率回归：v0.9.12（空闲）→ v0.9.13（中等）→ v0.10.0（高）**  
   [🔗](https://github.com/Hmbown/Codewhale/issues/6728)  
   **0 评论** | **更新 2026-09-29**  
   **为什么重要**：从 v0.9.12 到 v0.10.0 的二进制对比显示二进制体积增大（82→90MB），空闲 CPU 占用持续上升。FreeBSD 用户报告，需要定位渲染循环或任务调度回归。

10. **[#6787] Linux: Full Access 权限无法到达 Agent（0.10.0）**  
    [🔗](https://github.com/Hmbown/Codewhale/issues/6787)  
    **0 评论** | **更新 2026-09-30**  
    **为什么重要**：将权限设为 Full Access 后，子 Agent 仍被 Auto-Review 监护人拒绝（90 秒后失败关闭），用户被迫降级至 0.9.13。对新权限模型的安全验证机制构成质疑。

---

## 🔧 重要 PR 进展（10 个）

1. **[#6789] fix(mcp): 握手卫生——空 client capabilities、接受 2025-11-25、30s 连接、AWS 登录恢复**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6789)  
   **更新 2026-09-30**  
   **内容**：修复了 `aws` MCP 服务器因 `initialize` 返回 `-32602` 而失败的问题；`uvx`/`npx` 冷启动超时改为 30s；客户端能力字段置空以兼容严格服务器。

2. **[#6782] v0.10.1 集成分支：wave/0.10.1-next**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6782)  
   **更新 2026-09-30**  
   **内容**：作者直接合流大量改进，避免逐个 PR 审批。包含了配置化重试、渲染修复、安全扫描等。0.10.1 的基建主闸。

3. **[#6777] fix: 分页器空白与换行宽度、迭代 `/tree` 渲染、macOS 休眠抑制期**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6777)  
   **更新 2026-09-30**  
   **内容**：四合一 bug 狩猎发现：pager 末尾多余空白、/tree 渲染迭代稳定性、macOS 休眠时进程存活不足。涉及 `pager.rs`、`session_tree.rs` 和 `sleep_inhibitor.rs`。

4. **[#6786] fix(web): 404 未注册单段路径**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6786)  
   **更新 2026-09-30**  
   **内容**：`/foo.txt` 等未被路由的单段路径会返回 200 及首页，而不是 404。修复后正确识别静态文件和无效路径。

5. **[#6770] fix(tools): apply_patch 创建/删除/插入安全、search glob/截断/不可读目录、参数修复**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6770)  
   **更新 2026-09-29**  
   **内容**：修补 `apply_patch` 工具的多项检查（防止删除越界、搜索时忽略不可读目录、参数修复），提升代码编辑工具的安全性和准确性。

6. **[#6784] fix(config): 读取 [retry] jitter/Retry-After 键及 [tui].force_http1**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6784)  
   **更新 2026-09-29**  
   **内容**：实现 #6700 的配置化提案，让用户可调整重试 jitter、`Retry-After` 尊重开关和 HTTP/1.1 强制。提升网络不稳定环境下的可用性。

7. **[#6744] feat(engine): 在 TurnStarted 上回显主机提交 ID**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6744)  
   **更新 2026-09-29**  
   **内容**：允许外部嵌入者将提交的 turn 与 engine 实际启动的 turn 关联起来，解决后台续接可能抢占队列时 ID 失配问题。

8. **[#6741] fix(mcp): 给 tools/call 独立请求预算，避免长期执行被欠超时**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6741)  
   **更新 2026-09-29**  
   **内容**：MCP 工具调用之前被两层短超时堆叠（MCP 120s + TUI 60s），长时间构建/测试会被杀死。该 PR 为 `tools/call` 独立分配预算，并提高默认上限。

9. **[#6740] fix(tasks): 当工具调用进行中时，空闲看门狗保持耐心**  
   [🔗](https://github.com/Hmbown/Codewhale/pull/6740)  
   **更新 2026-09-29**  
   **内容**：后台任务空闲看门狗（默认 120s）在静默工具调用期间会误杀 turn，因为日志只在开始和完成时记录。修复后看门狗会忽略工具执行中的静默间隔。

10. **[#6408] feat(providers): 添加 Yolo-Auto 兼容的主机描述**  
    [🔗](https://github.com/Hmbown/Codewhale/pull/6408)  
    **更新 2026-09-29**  
    **内容**：在现有自定义提供者路径上新增 Yolo-Auto 预设，支持 `YOLO_AUTO_API_KEY` 和 `qwen3.8-flash` 引导模型。降低用户接入新模型的门槛。

---

## 📊 功能需求趋势

从近两日的 Issues 和 PRs 中，社区最关注的功能方向包括：

- **配置可调性**：网络重试预算、超时、jitter 等原本硬编码的参数现在通过 `[retry]` 和 `[tui]` 配置公开（#6700、#6784），用户可根据代理/防火墙环境调整。
- **多 Agent 会话与 UI 管理**：多个 TUI 会话争用 CPU（#6573）、Agent 存在芯片与侧边栏分离（#6322）、To-do 列表管理（#6546）表明用户对复杂工作流和并发场景的需求增强。
- **IDE/插件集成**：可复用 PR review action（#6486、#6780）、MCP 服务器互通改进（#6789）、Shell 工具钩子增强（#6689、#6582）显示社区希望将 Codewhale 嵌入更多开发流程。
- **新模型提供者**：Tsubasa（#6695）、Yolo-Auto（#6408）表明用户期望更丰富的

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*