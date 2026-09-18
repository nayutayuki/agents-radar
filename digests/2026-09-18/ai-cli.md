# AI CLI 工具社区动态日报 2026-09-18

> 生成时间: 2026-09-18 00:46 UTC | 覆盖工具: 9 个

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

好的，作为一名专注于AI开发工具生态的资深技术分析师，以下是我为您准备的基于今日（2026-09-18）各主流AI CLI工具社区动态的横向对比分析报告。

---

### AI CLI 工具生态横向对比分析报告 (2026-09-18)

#### 1. 生态全景

当前AI CLI工具生态正处于**从“功能堆叠”向“平台化与稳定性”跃迁的关键阶段**。一方面，以**Claude Code**和**GitHub Copilot CLI**为首的头部工具正积极构建插件（Mods/Agents）和协议（ACP）生态，试图从“单点工具”演变为“开发者工作流平台”。另一方面，以**Gemini CLI**和**Pi**为代表的工具则在疯狂“补课”，重点解决代理系统可靠性、会话持久化和多平台兼容性等基础体验问题。同时，**Windows稳定性**和**MCP（Model Context Protocol）集成深度**已成为衡量工具成熟度的普适性标尺，几乎所有工具都在这两个领域遭遇了用户集中反馈的痛点。

#### 2. 各工具活跃度对比

| 工具名称 | 社区热度 (Issues/PR) | 版本发布 | 核心议题焦点 |
| :--- | :--- | :--- | :--- |
| **Claude Code** | 极高 (100+ I / 3 PR) | v2.1.275 | **Mods扩展性**、Windows稳定性、会话连续性 |
| **OpenAI Codex** | 高 (10 I / 10 PR) | rust-v0.155.0 | **MCP非OpenAI兼容性**、UI假死、5小时限制 |
| **Gemini CLI** | 高 (10 I / 10 PR) | nightly v0.62.0 | **Agent系统可靠性**、Auto Memory安全、PTY兼容性 |
| **GitHub Copilot CLI** | 中 (10 I / 0 PR) | v1.0.86 | **Figma MCP冲突**、Windows权限、会话恢复中断 |
| **OpenCode** | 中 (10 I / 10 PR) | 无新版本 | **免费层逻辑错误**、DeepSeek V4地域限制、回归Bug |
| **Pi** | 中 (10 I / 10 PR) | 无新版本 | **错误重试逻辑**、会话压缩溢出、Window兼容性 |
| **Kimi Code CLI** | 低 (3 I / 1 PR) | 无新版本 | 工具调用循环、OAuth超时、配置写入异常 |
| **Qwen Code** | 高 (10 I / 10 PR) | v0.24.0-nightly, Desktop-v0.24.0 | **React UI崩溃**、ACP协议稳定性、Context性能优化 |
| **DeepSeek TUI** | 中 (10 I / 2 PR) | 无新版本 | **子代理资源管理**、安全边界、YOLO模式恢复 |

**分析**：Claude Code凭借其庞大的用户基数和“Mods”议题引发了极高热度的讨论，社区活跃度和影响力领先。Codex和Gemini CLI正处于密集的功能修复和迭代期。OpenCode、Pi、Qwen Code社区活跃度中等，但Issues和PR质量高，反映了深层次的技术挑战。Kimi Code活跃度最低，可能与其用户规模和社区运营策略有关。

#### 3. 共同关注的功能方向

以下需求在多个工具社区中反复出现，反映了开发者对AI CLI工具的普遍期待：

- **插件系统与可扩展性**
  - **Claude Code / Copilot CLI / OpenCode**: 用户不满足于内置功能，强烈希望像 VS Code 一样通过插件（Mods、Agents、Extensions）自定义工作流、集成新工具，并实现UI与生命周期的深度控制。

- **会话连续性与上下文管理**
  - **Claude Code / Codex / Gemini CLI / DeepSeek TUI**: 用户期望能在不同终端、时间点无缝恢复会话，并对token消耗、上下文内容有精确控制。自动压缩、会话恢复、后台任务唤醒是核心诉求。

- **Windows平台稳定性与权限问题**
  - **几乎所有工具**: Windows平台成为稳定性短板。Claude Code的孤儿Silo、Codex的UI假死、Copilot CLI的文件锁、Gemini CLI的ConPTY问题、Pi的shell路径随机失效等，表明跨平台兼容性是当前最普遍的技术债务。

- **MCP集成与第三方模型兼容性**
  - **Codex / Copilot CLI / Qwen Code / Pi**: 社区高度关注MCP工具在非原生模型（如Ollama, OpenRouter）上的可用性。同时，MCP服务器的OAuth认证、远程连接稳定性、配置灵活性也是热点。

- **安全与权限精细化**
  - **DeepSeek TUI / Claude Code / Codex**: 用户对AI代理的能力边界感到担忧。社区呼吁实现基于角色（只读/可写）的权限模型、细粒度的操作确认（如浏览器持久授权）、以及防止破坏性操作的“干运行”模式和安全护栏。

#### 4. 差异化定位分析

- **Claude Code**: **“工程用户的瑞士军刀”**。追求极致的功能深度和交互控制力（如快捷键、面板布局），并率先拥抱**插件化生态**，志在成为AI开发的基础平台。
- **OpenAI Codex**: **“多模型调度与集成中心”**。强调通过MCP和语音等交互模式连接多种工具和应用，但其对非OpenAI模型的兼容性限制，使其更像一个**偏封闭的生态核心**。
- **GitHub Copilot CLI**: **“GitHub原生专家”**。深度绑定GitHub生态（如仓库指令、自定义代理），优势在于与代码仓库和团队工作流的无缝集成，是**“为GitHub而生”**的AI开发助手。
- **Gemini CLI**: **“Agent与记忆系统探索者”**。在**子代理**和 **Auto Memory** 方面投入巨大，试图解决复杂多步骤任务的自主执行和长期记忆问题，定位更偏向**AI Agent研究者**。
- **Qwen Code**: **“协议与IDE集成先驱”**。积极推动 **ACP (Agent Control Protocol)** 作为行业标准，并努力深度集成到VS Code、Zed等IDE中，着眼于**定义下一代人机交互协议**。
- **Pi**: **“自由与可塑性强的工具”**。在错误处理、Provider支持、会话管理上提供了非常底层的控制力，代码库设计灵活，风格贴近**硬核开发者的“可编程终端”**。
- **DeepSeek TUI**: **“子代理资源管理的实验田”**。专注于解决**子代理间资源（Token、文件锁）的隔离与共享难题**，对安全边界（Computer Use）有深刻反思，是Agent系统方向的深度实践者。
- **OpenCode & Kimi Code**: 两者都偏向**通用型AI助手**，差异化不足。OpenCode凭借多模型支持和较高活跃度稍占优势，而Kimi Code似乎更专注于其独特的“记忆”和“梦境”功能，但稳定性是其最大挑战。

#### 5. 社区热度与成熟度

- **高热度，高复杂度 (Claude Code, Codex, OpenCode)**: 这些工具拥有庞大的用户群，社区讨论涵盖功能、Bug、设计哲学等多个层面。**Claude Code** 在功能深度和生态愿景上最成熟；**Codex** 在模型集成方面较为领先，但稳定性问题突出；**OpenCode** 增长迅速，但回归问题频发，处于亚健康迭代期。
- **高热度，快速迭代 (Gemini CLI, Qwen Code, Pi)**: 这些工具社区活跃，但议题集中在Bug修复和核心功能完善上，处于**快速追赶和打磨**阶段。**Gemini CLI** 的Agent系统概念超前，但bug过多；**Qwen Code** 在新协议和UI创新上勇敢，但稳定性堪忧；**Pi** 则在细节上精益求精。
- **中低热度，生态依附 (Copilot CLI, DeepSeek TUI, Kimi Code)**: **Copilot CLI** 依赖于GitHub生态，自身发布节奏稳定，社区议题聚焦于具体集成问题；**DeepSeek TUI** 社区规模较小但讨论质量高，专注于专业用户；**Kimi Code** 整体活跃度较低，相对边缘化。

#### 6. 值得关注的趋势信号

1.  **“插件化”成为兵家必争之地**: Claude Code的`Mods`议题引爆社区，Copilot CLI的`自定义代理`也在默默跟进。这表明未来的AI CLI竞争将从“谁更好用”升级为 **“谁的生态更丰富，谁的平台扩展性更强”**。
2.  **从“对话”到“长程运行”的范式转变**: 5小时使用限制（Codex）、会话/上下文/任务边界（Gemini CLI, Qwen Code）等议题的爆发，表明开发者不再满足于简单的问答，而是要求AI CLI工具能够**像操作系统一样管理长期、复杂的后台任务**。
3.  **安全性的“底线”正式浮出水面**: DeepSeek TUI的“子代理通过Computer Use绕过限制”案例和Claude Code的“权限配置不生效”问题，是开发者对AI代理权力觉醒的标志。**精细化、可声明、强制执行的权限模型**将成为未来所有AI CLI工具的标配。
4.  **平台兼容性的“第二战场”**: 几乎所有工具在Windows上都遇到了严重问题。随着AI开发从云端走向本地，**跨平台（尤其是Windows）的稳定性和体验一致性**，正从不被重视的“边缘需求”转变为决定工具能否大规模普及的“关键战役”。
5.  **“最低可用性”被重新定义**: 用户不再容忍任何程度的空转、崩溃或静默失败（如Codex的“UI假死”，Pi的“上下文溢出误判”）。**可预期的行为、优雅的错误处理、以及清晰的调试信息**，已成为衡量一个AI CLI工具成熟度的基础门槛。

**对开发者的参考价值**：选择AI CLI工具时，不应只看其宣传的功能亮点，更应深入考察其**生态系统开放性、会话持久化与任务管理机制、权限模型安全策略、以及目标平台的稳定性记录**。这些“底层”能力将最终决定工具在日常开发工作流中的实用性和可靠性。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，以下是根据您提供的《anthropics/skills》仓库数据（截至2026-09-18）生成的Claude Code Skills社区热点报告。

---

## Claude Code Skills 社区热点报告 (截至 2026-09-18)

### 1. 热门 Skills 排行

以下是根据社区讨论活跃度（PR评论及关联Issue讨论数）排名的热门Skills：

-   **`skill-creator` 修复与改进 (PR #1298, #1769)**
    -   **功能**: 核心元技能，用于创建和优化其他Skills。当前PR主要修复触发评估误报、Windows兼容性、运行时失败等问题。
    -   **社区热点**: 这是当前社区最关注、争议也最集中的技能。多个PR和Issues报告其触发器评估逻辑存在根本性缺陷 (0%召回率)、跨平台兼容性差及文档风格不符合最佳实践。社区的核心诉求是“**让创建器本身可靠**”。
    -   **状态**: 开放中 (Open)
    -   **链接**: [PR #1298](https://github.com/anthropics/skills/pull/1298), [PR #1769](https://github.com/anthropics/skills/pull/1769)

-   **`proofcore-contract-auditor` (PR #1771)**
    -   **功能**: 面向Web3开发者，对Solidity/Rust智能合约进行静态分析，并将审计证明锚定到TON区块链。
    -   **社区热点**: 作为技能生态中少见的Web3/区块链方向，其“零存储Merkle协议”和自动化审计上链能力引发了技术社区的兴趣。
    -   **状态**: 开放中 (Open)
    -   **链接**: [PR #1771](https://github.com/anthropics/skills/pull/1771)

-   **`md2video-audio` (PR #1703)**
    -   **功能**: 零成本将Markdown文档编译为带有拟真人声的专业级MP4视频。
    -   **社区热点**: 其“零成本”和“Markdown→视频”的闭环能力非常吸引内容创作者和开发者。社区关注其在实际工作流中的生成质量和效率。
    -   **状态**: 开放中 (Open)
    -   **链接**: [PR #1703](https://github.com/anthropics/skills/pull/1703)

-   **`document-typography` (PR #514)**
    -   **功能**: 纠正AI生成文档中的孤词、寡段、编号错位等排版问题。
    -   **社区热点**: 直击AI文档生成的“最后一公里”痛点。社区普遍认为这是一个“没人会主动要求，但所有人都需要”的实用技能。
    -   **状态**: 开放中 (Open)
    -   **链接**: [PR #514](https://github.com/anthropics/skills/pull/514)

-   **`pyxel` 复古游戏开发 (PR #525)**
    -   **功能**: 指导Claude创建、调试和验证基于Pyxel的Python Retro游戏，支持确定性无头运行和帧检查。
    -   **社区热点**: 代表社区对**创意和娱乐领域**的探索。其“确定性测试”和“帧级验证”的设计思路为AI生成复杂交互式内容提供了范本。
    -   **状态**: 开放中 (Open)
    -   **链接**: [PR #525](https://github.com/anthropics/skills/pull/525)

-   **`Hivemind` 多智能体编排 (PR #1628)**
    -   **功能**: 让Claude Code作为规划者，将机械性任务委托给使用免费模型的无头Workers。
    -   **社区热点**: 社区高度关注其“**零成本扩展**”和“**解耦昂贵推理与廉价执行**”的架构思想。这是优化成本和效率的典型代表。
    -   **状态**: 开放中 (Open)
    -   **链接**: [PR #1628](https://github.com/anthropics/skills/pull/1628)

---

### 2. 社区需求趋势

从Issues数据分析，社区对新技能的需求主要集中在以下方向：

-   **安全与信任 (Security & Trust)**: 社区强烈呼吁在`anthropic/`命名空间下建立更严格的社区技能审核与隔离机制 (#492)，防止信任边界滥用。这是最紧迫的生态治理需求。
-   **企业级功能 (Enterprise Features)**:
    -   **技能组织级共享**: 用户希望能在组织内直接分享和同步Skills，而不是手动发送文件 (#228)。
    -   **合规与治理**: 对结合内部文档系统（如SharePoint）的技能有明确需求，但同时对安全性和上下文窗口占用表示担忧 (#1175)。
-   **核心工具生态修复 (Core Tooling Fixes)**:
    -   **评估与调优工具**: `skill-creator`和`run_eval.py` (#556) 等工具的可用性和准确性受到广泛质疑，社区急需这些**元工具**变得稳定可靠。
    -   **上下文窗口管理**: 用户抱怨如`claude-api`等技能注入过多Token，堵塞上下文窗口 (#1487)。轻量级、按需加载的Skill设计成为刚需。
-   **高级上下文与记忆 (Advanced Context & Memory)**: 用户提出`compact-memory` (#1329) 技能，希望采用符号化表示法来压缩长期运行的Agent状态与记忆，以节省Token。
-   **智能体治理 (Agent Governance)**: 社区提议开发`agent-governance` (#412) 技能，用于定义AI智能体系统的安全模式、策略、审计和行为边界，这反映了对Agent可靠性的更高追求。

---

### 3. 高潜力待合并 Skills

以下 PR 评论活跃，技术含量高或解决核心痛点，具有很高的近期合并潜力：

1.  **`skill-creator` 修复集 (PR #1298, #1769)**: 合并优先级最高。这是生态的基础设施，其当前的可靠性问题（假阳性、0%召回率）直接影响到所有社区贡献者。
    -   **链接**: [PR #1298](https://github.com/anthropics/skills/pull/1298), [PR #1769](https://github.com/anthropics/skills/pull/1769)
2.  **`document-typography` (PR #514)**: 实用价值极高，解决普遍存在的AI文档排版问题，技术方案相对成熟，落地确定性高。
    -   **链接**: [PR #514](https://github.com/anthropics/skills/pull/514)
3.  **`md2video-audio` (PR #1703)**: 创意工具的代表，功能新颖且“零成本”定位精准，能极大扩展Claude Code的内容产出形式。
    -   **链接**: [PR #1703](https://github.com/anthropics/skills/pull/1703)
4.  **`Hivemind` (PR #1628)**: 代表了未来Agent系统的演进方向，其多智能体编排和成本优化设计极具吸引力，但需要更多关于Worker安全性和任务执行可靠性的讨论。
    -   **链接**: [PR #1628](https://github.com/anthropics/skills/pull/1628)

---

### 4. Skills 生态洞察

**当前社区最集中的诉求是：建立一个稳定、安全、可治理的Skills基础设施**，而不只是追求技能功能的丰富度。核心工具（特别是`skill-creator`）的可靠性、技能分发的安全性（命名空间管理）、以及企业级共享与治理能力，是社区健康发展亟需解决的“瓶颈”。

---

# Claude Code 社区动态日报 | 2026-09-18

---

## 今日速览

1. **v2.1.275 发布**：新增 Gateway 登录确认流和“立即发送”快捷键（Ctrl+Enter），提升交互控制力。
2. **社区最热议题 `#91870`（Mods 扩展性）** 评论数逼近 200，团队宣布数周内将上线函数钩子，社区期待值拉满。
3. **Windows 桌面端稳定性频遭反馈**：`#53247` 孤儿 Silo 问题持续近 5 个月未解，新版 `#95050` 又爆 exitCode 21 渲染崩溃，成为开发者最大痛点。

---

## 版本发布

### v2.1.275（2026-09-18）

**新增功能**
- **Gateway 登录确认**：当 Gateway 指定账户名时，用户需手动确认后方可保存凭据；`/status` 命令也会显示已登录账户。
- **立即发送快捷键**：`Ctrl+Enter`（或 `Ctrl+X Ctrl+S`）可中断当前轮次并立即发送所有排队消息，告别等待。

---

## 社区热点 Issues（10 条）

挑选依据：评论数、点赞数及问题严重性，覆盖扩展性、稳定性和 IDE 集成等关键方向。

### 1. `#91870` [增强] Mods - 让 Claude 扩展性提升 10 倍
- **作者**：poteat | **评论**：195 | **👍**：120
- **更新**：2026-09-17 | **状态**：OPEN
- **概要**：社区最热议题。团队已承诺数周内发布函数钩子系统，目前正根据用户反馈调整设计。`hooks` 和 `plugins` 两大标签预示官方将提供可编程扩展点。
- **链接**：https://github.com/anthropics/claude-code/issues/91870

### 2. `#53247` [Bug] Windows 桌面版启动失败 — 孤儿 Silo / Job Object 导致 HRESULT 0x80070020
- **作者**：rnpacheco25-sudo | **评论**：93 | **👍**：33
- **更新**：2026-09-17 | **状态**：OPEN
- **概要**：应用崩溃后残留的 Task 对象阻止后续启动，仅注销或重启可恢复。影响 `Claude Desktop` 和 `Cowork` 组件，涉及 Windows 底层 Job Object 回收问题。
- **链接**：https://github.com/anthropics/claude-code/issues/53247

### 3. `#11455` [增强] 会话交接 / 连续性支持
- **作者**：patrickhardiman | **评论**：36 | **👍**：25
- **更新**：2026-09-17 | **状态**：OPEN
- **概要**：CLI 用户长期诉求——能在不同终端、不同时间点无缝恢复对话上下文，避免每次重新初始化。
- **链接**：https://github.com/anthropics/claude-code/issues/11455

### 4. `#25128` [Bug] VS Code 扩展聊天面板拖放失效（终端 CLI 正常）
- **作者**：emregurhan | **评论**：33 | **👍**：48
- **更新**：2026-09-17 | **状态**：OPEN
- **概要**：自 v2.1.6 版本回归，拖放文件/图片到聊天面板无响应，终端中正常。用户急需此功能以快速引用资源。
- **链接**：https://github.com/anthropics/claude-code/issues/25128

### 5. `#15921` [Bug] VS Code 扩展：`.claude/settings.local.json` 权限配置未被 Bash/Write/Edit 操作尊重
- **作者**：elliottgaryusa | **评论**：31 | **👍**：32
- **更新**：2026-09-18 | **状态**：OPEN
- **概要**：即使设置 `bypassPermissions`，本地配置中的权限规则仍被忽略，导致安全预期与实际行为不符。Windows 平台尤其明显。
- **链接**：https://github.com/anthropics/claude-code/issues/15921

### 6. `#32726` [增强] VS Code 扩展：阻止面板自动抢占焦点
- **作者**：Ashkaan | **评论**：19 | **👍**：57
- **更新**：2026-09-18 | **状态**：OPEN
- **概要**：编写代码时 Claude 面板一旦输出结果就自动弹出并抢占焦点，严重打断工作流。点赞数第二高，说明是 IDE 用户普遍痛点。
- **链接**：https://github.com/anthropics/claude-code/issues/32726

### 7. `#81081` [Bug] 会话启动时技能列表静默截断大部分描述（受大小预算限制）
- **作者**：ralucaoda | **评论**：11 | **👍**：0
- **更新**：2026-09-17 | **状态**：OPEN
- **概要**：当用户定义多个技能时，会话初始化阶段只保留有限 token 给技能描述，超出部分被无声丢弃，导致能力显示不完整。
- **链接**：https://github.com/anthropics/claude-code/issues/81081

### 8. `#93156` [增强] 浏览器窗格：无法授予持久站点权限 — 每次操作都弹出确认
- **作者**：silentmado | **评论**：6 | **👍**：0
- **更新**：2026-09-17 | **状态**：OPEN
- **概要**：Claude Desktop 内嵌浏览器对每个站点访问都要求“允许一次”，没有“始终允许”选项。即使配置了 `launchPreviewAllowedOrigins`、工具白名单甚至 `bypassPermissions` 均无效。
- **链接**：https://github.com/anthropics/claude-code/issues/93156

### 9. `#95050` [Bug] Claude Desktop 2.110.0（Windows/MSIX）退出后下次启动失败 — renderer exitCode 21
- **作者**：catovanwezel | **评论**：2 | **👍**：0
- **更新**：2026-09-18 | **状态**：OPEN
- **概要**：新发现的 Windows 启动崩溃，闪窗后自动关闭。需重启 `CoworkVMService` 才能恢复。疑似与 MSIX 打包或沙箱机制相关。
- **链接**：https://github.com/anthropics/claude-code/issues/95050

### 10. `#88632` [Bug] Cowork Windows：本地环境无法附加任何项目 — “Projects can't be included in sessions that run on this computer”
- **作者**：UBOWENVT | **评论**：2 | **👍**：0
- **更新**：2026-09-17 | **状态**：OPEN
- **概要**：Windows 上 Cowork 本地会话完全无法使用项目功能，同一版本 macOS 正常。文档也未说明 Windows 存在此限制。
- **链接**：https://github.com/anthropics/claude-code/issues/88632

---

## 重要 PR 进展（共 3 条）

过去 24 小时内仅 3 个 PR 有更新，全部列举如下：

### 1. `#95198` mods/diff: 将 `openPane` 返回类型声明为 `unknown` 以兼容更丰富的 `$.ui.open` 结果
- **作者**：poteat | **更新**：2026-09-17
- **概要**：为即将到来的 Mods 引擎改进做准备，允许 `$.ui.open` 返回结果对象而不破坏现有调用者。
- **链接**：https://github.com/anthropics/claude-code/pull/95198

### 2. `#94847` diff: 首次编辑只在有文件可列出时才打开面板
- **作者**：bcherny | **更新**：2026-09-17
- **概要**：修复 diff 面板在成功编辑后立即打开却因文件被忽略或在工作树外而显示“无跟踪变更”空面板的问题。改为确认有实际变更后再打开。
- **链接**：https://github.com/anthropics/claude-code/pull/94847

### 3. `#87077` fix(pr-review-toolkit): 修复所有 agent 中无效的 YAML 前置元数据
- **作者**：anishsamant | **更新**：2026-09-17
- **概要**：Agent 描述中包含对话式多行文本（如 `Daisy: "..." / Assistant: "..."`），YAML 解析器将其视为嵌套映射导致前置元数据被丢弃。修复后每个 agent 能正确加载名称、描述和模型配置。
- **链接**：https://github.com/anthropics/claude-code/pull/87077

---

## 功能需求趋势

从过去 24 小时更新的 Issues 中，提炼出社区最关注的四大功能方向：

1. **可扩展性与插件系统（Mods）**
   - `#91870` 引爆社区，函数钩子（hooks）和插件（plugins）成为绝对热点。用户希望 Claude 能像 VS Code 一样通过 API 扩展，实现自定义工具、UI 面板和生命周期拦截。

2. **会话连续性与上下文人机分离**
   - `#11455` 会话交接持续多年未落地，开发者需要在多终端间迁移对话上下文，且希望上下文内容可控制（如 MCP 工具结果的自动过期 eviction #85169）。

3. **IDE 集成深度优化**
   - VS Code 扩展的焦点控制（`#32726`）、拖放支持（`#25128`）、内联图片渲染（`#79436`）、MCP 推送通知（`#79311`）等需求堆积，说明用户希望 IDE 内体验向终端 CLI 看齐甚至超越。

4. **权限与安全机制精细化**
   - 浏览器持久权限（`#93156`）、本地配置权限不生效（`#15921`）、Agent 批量创建 PR 无防护（`#79399`）等表明，用户需要更细粒度的权限模型，支持“允许一次/始终允许/拒绝”三级选择，并能针对特定来源或操作类型进行授权。

---

## 开发者关注点

开发者反馈中集中反映以下痛点和高频需求：

- **Windows 桌面端稳定性亟待解决**：`#53247` 与 `#95050` 均指向启动/重启崩溃，前者已存续近 5 个月，后者为最新版本 2.110.0 新增的 exitCode 21 错误，严重依赖 CoworkVMService。Windows 用户群体的不满度持续上升。
- **VS Code 扩展未达 CLI 体验基线**：拖放、焦点管理、内联图片等 CLI 已经支持的功能在扩展中缺失或退化，加上 MCP 通知不在面板显示，导致部分用户放弃扩展转用终端。
- **权限配置令人困惑**：`bypassPermissions` 与 `settings.local.json` 关系模糊，浏览器窗口权限模型过于简陋，开发者希望有统一、可预测的权限声明机制。
- **Token 浪费问题被反复提及**：即使禁用 MCP 连接器，其 schema 仍占用上下文（`#92255`），禁用工具也保留约 20K token（`#83363`）。高级用户对 token 消耗极度敏感，希望提供可视化预算和精确控制。
- **Agent 需要安全护栏**：`#79399`（91 个 PR 自动关闭并锁定用户仓库）是典型警示。社区期待“干运行”模式、PR 数量上限、外部仓库确认弹出等防护措施。

---

*日报生成于 2026-09-18，数据来源：[anthropics/claude-code](https://github.com/anthropics/claude-code)*

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报 | 2026-09-18

---

## 今日速览

Codex 今日发布 **rust‑v0.155.0 稳定版**，新增实验性 `/voice` 语音对话功能及 TUI 实时推理摘要显示；社区热点集中在 **MCP 工具对非 OpenAI 模型不可用**（#26234）、**桌面端 UI 假死无法恢复**（#24287）以及 **多模型容量满**（#43375）三大问题上；PR 侧重点在于 **Windows 沙盒清理**、**OAuth 网关认证** 及 `exec --json` 事件输出修复。

---

## 版本发布

- **[rust‑v0.155.0](https://github.com/openai/codex/releases/tag/rust-v0.155.0)**  
  稳定版更新亮点：
  - 实验性 `/voice` 语音对话功能，支持实时转写与麦克风控制，需通过 `/experimental` 启用。
  - TUI 在状态栏中显示实时推理摘要，并在成功轮次后添加完成时间戳。

- **rust‑v0.156.0‑alpha.1** 及多个 `v0.155.0‑alpha.*` 版本发布，均为持续迭代的预发布版，无公开新增特性。

---

## 社区热点 Issues

### 1. [#26234 – MCP 工具在非 OpenAI 模型上不可调用](https://github.com/openai/codex/issues/26234)
**重要性** ★★★★★ | 评论 35 | 👍 48  
当 Codex 使用 Ollama、LM Studio、OpenRouter 或 AWS Bedrock 等非 OpenAI 模型时，MCP 服务器提供的工具被封装在专有命名空间中，模型无法调用。社区呼吁提供扁平化处理方案，是当前 MCP 集成最严重的兼容性缺陷。

### 2. [#24287 – 桌面端输入后 UI 卡死在“Thinking”，无法停止](https://github.com/openai/codex/issues/24287)
**重要性** ★★★★★ | 评论 31 | 👍 14  
用户提交提示后界面永远卡在“Thinking”状态，停止按钮无效，重启后轮次可能消失。影响所有桌面端用户，且重现率高，是阻碍日常使用的 P0 级 Bug。

### 3. [#43375 – 多款 GPT‑5/6 模型返回“容量已满”](https://github.com/openai/codex/issues/43375)
**重要性** ★★★★☆ | 评论 28 | 👍 15  
连续切换 GPT‑5、GPT‑5.5、GPT‑6 等模型均出现“Selected model is at capacity”错误。推测为服务端配额策略或路由问题，严重影响高模型切换场景。

### 4. [#37967 – 远程控制无法附加到正在运行的 CLI 会话](https://github.com/openai/codex/issues/37967)
**重要性** ★★★★☆ | 评论 17 | 👍 26  
手机端 Remote Control 只能查看已完成的线程，无法附加到正在运行的任务。用户期望手机侧可监控、审批操作，是实现“工作站‑手机”双端协同的关键缺失。

### 5. [#40905 – 5 小时使用限制打断长时间 Sol Agent 任务](https://github.com/openai/codex/issues/40905)
**重要性** ★★★★☆ | 评论 15 | 👍 4  
GPT‑5.6 Sol 能运行数小时的自主任务，但 5 小时滚动窗口会中断已运行的进程，导致工作丢失。社区认为窗口机制应与任务粒度解耦。

### 6. [#42739 – Windows 桌面更新后本地项目从侧栏消失](https://github.com/openai/codex/issues/42739)
**重要性** ★★★★☆ | 评论 14 | 👍 0  
更新后 Projects 区域显示“No projects”，但文件仍在磁盘。影响所有 Windows 桌面用户，属于升级后数据损坏类严重问题。

### 7. [#15684 – VS Code 扩展卡在深色主题（已关闭）](https://github.com/openai/codex/issues/15684)
**重要性** ★★★☆☆ | 评论 13 | 👍 10  
虽然已关闭，但评论数高表明之前对该问题的关注度。现已在后续版本修复，可作为历史参考。

### 8. [#24437 – Intel macOS 缺少 Computer Use 助手](https://github.com/openai/codex/issues/24437)
**重要性** ★★★☆☆ | 评论 10 | 👍 5  
x64 发行版未打包 `computer-use` 插件，导致 Appshots、锁定使用等功能不可用。这是 Intel Mac 用户长期未被解决的打包问题。

### 9. [#32188 – 后台执行完成后的事件驱动唤醒](https://github.com/openai/codex/issues/32188)
**重要性** ★★★☆☆ | 评论 10 | 👍 13  
长命令需模型轮询 `write_stdin` 或委托子代理，造成额外 token 消耗。社区希望后台任务完成后能主动唤醒模型，提升执行效率。

### 10. [#42745 – Windows Computer Use：CUA 启动时漏发 trust RPC](https://github.com/openai/codex/issues/42745)
**重要性** ★★★☆☆ | 评论 9 | 👍 0  
当 CUA 仅以浏览器表面启动时，`sky trusted RPC` 被省略，导致计算机使用功能异常。属于边缘场景但影响特定用户流程。

---

## 重要 PR 进展

### 1. [#46333 – 处理 Windows 沙盒禁用账户的清理](https://github.com/openai/codex/pull/46333)
修复了清理过程中因账户已禁用导致令牌获取失败的问题，确保临时启用后能正确重新禁用。提升 Windows 沙盒稳定性。

### 2. [#46332 – TUI 中对话摘要使用暗色样式](https://github.com/openai/codex/pull/46332)
对所有渲染的回忆行应用暗色样式，移除 `Next:` 的青色，保留斜体与标签样式，改善 TUI 可读性。

### 3. [#46331 – 延迟环境网络策略验证至组合之后](https://github.com/openai/codex/pull/46331)
功能设置和托管需求可替换域与 socket 值，移动验证顺序以避免过早拒绝有效配置。提升环境配置灵活性。

### 4. [#46330 – 将重试退避迁移至 `codex-async-utils`](https://github.com/openai/codex/pull/46330)
将指数退避辅助函数抽取到独立 crate，减少 `codex-cloud-config` 对 `codex-core` 的运行时依赖。代码解耦。

### 5. [#46328 – 避免为无项目目录持久化项目信任](https://github.com/openai/codex/pull/46328)
若目录中无项目标记（Git 检出等），则不会写入信任状态，防止后续添加项目后自动获得预批准。安全增强。

### 6. [#46324 – 扩展压缩回退至当前模型](https://github.com/openai/codex/pull/46324)
模型切换后，压缩若用之前模型失败，现在可回退到当前模型。避免因流重试耗尽而卡死。

### 7. [#46323 – 记录轮次分析中的活跃插件清单](https://github.com/openai/codex/pull/46323)
在 turn analytics 中添加 `active_plugin_ids_at_turn_start`，结合远程插件 ID 与包 ID，排序去重。便于调试插件交互问题。

### 8. [#46319 – 修复 exec JSON 输出中 web 搜索事件丢失](https://github.com/openai/codex/pull/46319)
明确映射 web 搜索动作类型，保留 `open_page` URL 和 `find_in_page` 结果。解决 `codex exec --json` 结构化输出丢失的 Bug。

### 9. [#46318 – 添加模型提供者网关的 OAuth 凭证管理](https://github.com/openai/codex/pull/46318)
导出 `GatewayAuthConfig` 和 `GatewayAuthManager`，支持 PKCE 浏览器登录、环回回调、令牌加密存储与刷新。为第三方模型接入铺路。

### 10. [#46300 – 集中化 OAuth 登录与刷新处理](https://github.com/openai/codex/pull/46300)
合并登录和令牌刷新的 OAuth 请求处理逻辑，防止令牌值泄露到诊断信息中。安全改进，降低凭据泄漏风险。

---

## 功能需求趋势

- **MCP 工具与第三方模型兼容性**：当前最大的功能缺口。非 OpenAI 模型（Ollama、LM Studio、Bedrock）无法调用 MCP 工具，社区要求扁平化命名空间或提供适配层。
- **长时间任务与时间窗口解耦**：5 小时滚动窗口频繁打断长流程，社区希望改为按 token 消耗或任务粒度计费，而非固定时钟。
- **跨平台 Computer Use 可用性**：Intel macOS 和部分 Windows 用户缺少 Computer Use 插件或锁定使用功能，需要保证分发包完整性。
- **远程控制 / 移动端监控**：用户期望从手机端附加、监控、审批正在运行的 CLI 会话，实现双端协同。
- **事件驱动 / 异步回调机制**：后台任务完成或外部事件（如文件变更）主动唤醒模型，减少轮询消耗。
- **Windows 沙盒与 ACL 稳定性**：多个 Windows 用户报告 sandbox 初始化失败、ACL 无法应用，需要彻底修复。

---

## 开发者关注点

- **非 OpenAI 模型体验割裂**：使用 OpenRouter / Ollama 的用户一旦启用 MCP 工具即完全失效，无法获得与 OpenAI 原生模型相同的功能。
- **桌面端 UI 假死无恢复手段**：`Thinking` 状态卡死、停止按钮无效、重启后轮次丢失，严重影响工作流连续性。
- **x64 macOS 长期功能缺失**：Computer Use、Appshots、锁定使用等功能在 Intel Mac 上数月未修复，社区抱怨打包疏忽。
- **Windows 更新导致项目丢失**：自动更新后本地项目凭空消失，虽然文件仍在但需要手动重建信任关系。
- **exec JSON 输出数据丢失**：`codex exec --json` 对 web_search 动作的处理被异常丢弃，影响 CI/CD 集成场景。
- **模型容量错误缺乏重试机制**：用户需要手动切换模型，没有自动退避或排队方案，影响高并发或高峰时段使用。

---

*本日报数据来源于 [github.com/openai/codex](https://github.com/openai/codex)，统计截至 2026-09-18 UTC。*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

# Gemini CLI 社区动态日报 | 2026-09-18

## 今日速览

今日社区聚焦于 Agent 系统稳定性与记忆机制的修复：**#22323 子代理最大轮次后被误报为成功** 的根因已被定位并提交 PR（#29367）；同时 **Auto Memory** 的多个问题（日志泄漏、低信号会话重试、无效补丁隔离）进入密集修复期。此外，**Pty 执行生命周期**、**OAuth 令牌刷新** 等核心模块的稳定性 PR 也在今日合并或开启，整体呈现出从功能开发向质量打磨的转向。

## 版本发布

- **nightly 版本 v0.62.0-nightly.20260917**  
  仅包含 Changelog 链接，无显著更新说明。  
  [查看完整变更](https://github.com/google-gemini/gemini-cli/compare/v0.62.0-nightly.20260916.g6a466a7e2...v0.62.0-nightly.20260917.g6a466a7e2)

---

## 社区热点 Issues（Top 10）

### 1. **子代理最大轮次后被误报为成功**（#22323）  
   - **重要性**：P1 级别的 bug，直接掩盖子代理中断事实，影响 Agent 可靠性。  
   - **社区反应**：13 条评论，已有对应 PR #29367 修复。  
   - **链接**：[#22323](https://github.com/google-gemini/gemini-cli/issues/22323)

### 2. **通用代理（generalist agent）挂起**（#21409）  
   - **重要性**：P1 bug，用户反馈只要代理调用通用子代理就会无限挂起，简单文件夹创建都无法完成。  
   - **社区反应**：8 条评论，8 个 👍，影响面广。  
   - **链接**：[#21409](https://github.com/google-gemini/gemini-cli/issues/21409)

### 3. **Shell 命令执行后卡在“等待输入”**（#25166）  
   - **重要性**：P1 bug，极简 shell 命令完成后终端仍显示“Awaiting input”，严重阻塞交互。  
   - **社区反应**：4 条评论，3 个 👍。  
   - **链接**：[#25166](https://github.com/google-gemini/gemini-cli/issues/25166)

### 4. **Auto Memory 日志泄漏与确定性脱敏缺失**（#26525）  
   - **重要性**：安全相关，P2，Auto Memory 在将关键内容送入模型前未做充分脱敏，存在敏感信息泄漏风险。  
   - **社区反应**：5 条评论，已进入积极修复阶段。  
   - **链接**：[#26525](https://github.com/google-gemini/gemini-cli/issues/26525)

### 5. **Auto Memory 对低信号会话无限重试**（#26522）  
   - **重要性**：P2 bug，导致资源浪费和无效循环，影响记忆系统效率。  
   - **社区反应**：4 条评论。  
   - **链接**：[#26522](https://github.com/google-gemini/gemini-cli/issues/26522)

### 6. **浏览器子代理在 Wayland 下失败**（#21983）  
   - **重要性**：P1 bug，Linux Wayland 用户无法使用浏览器子代理。  
   - **社区反应**：4 条评论，1 个 👍。  
   - **链接**：[#21983](https://github.com/google-gemini/gemini-cli/issues/21983)

### 7. **Gemini 不使用自定义技能和子代理**（#21968）  
   - **重要性**：用户体验核心缺陷，用户明确配置了技能，但 Gemini 不会主动调用。  
   - **社区反应**：6 条评论，开发者已标记为需复测。  
   - **链接**：[#21968](https://github.com/google-gemini/gemini-cli/issues/21968)

### 8. **子代理轨迹无法通过 /chat share 共享**（#22598）  
   - **重要性**：P3 增强，但影响调试和评估流程，社区期望能方便分享子代理内部执行记录。  
   - **社区反应**：2 条评论，1 个 👍。  
   - **链接**：[#22598](https://github.com/google-gemini/gemini-cli/issues/22598)

### 9. **/compress 命令跨会话不持久**（#21335）  
   - **重要性**：P2 bug，压缩历史节省 token 的功能在退出重启后丢失，用户反复操作。  
   - **社区反应**：2 条评论，2 个 👍。  
   - **链接**：[#21335](https://github.com/google-gemini/gemini-cli/issues/21335)

### 10. **文件更新时误删无关注释**（#29370）  
   - **重要性**：最新提交的 bug（2026-09-17），直接影响代码质量，用户修复成本高。  
   - **社区反应**：1 条评论，但标记为 P2。  
   - **链接**：[#29370](https://github.com/google-gemini/gemini-cli/issues/29370)

---

## 重要 PR 进展（Top 10）

### 1. **[fix(agents)] 保留子代理原始终止原因，防止误报 GOAL 成功**（#29367）  
   - **说明**：修复 #22323，阻止恢复路径无条件覆盖 `terminateReason`。  
   - **状态**：Open，P1，maintainer only。  
   - **链接**：[#29367](https://github.com/google-gemini/gemini-cli/pull/29367)

### 2. **[fix(core)] 修复 ConPTY 进程退出生命周期与 PTY 输出终结**（#29379）  
   - **说明**：改进 Windows ConPTY 环境下进程确定性终结与流完整性。  
   - **状态**：Open，P1，size/l。  
   - **链接**：[#29379](https://github.com/google-gemini/gemini-cli/pull/29379)

### 3. **[fix(core,cli)] 改善终端缓冲内存管理与 Windows 诊断路径格式化**（#29380）  
   - **说明**：优化 PTY 执行内存占用，改进 `/bug` 报告中 Windows 路径的 Markdown 显示。  
   - **状态**：Open，size/l。  
   - **链接**：[#29380](https://github.com/google-gemini/gemini-cli/pull/29380)

### 4. **[fix(vscode-ide-companion)] 关闭 diff 标签后保持终端焦点**（#29378）  
   - **说明**：传递 `preserveFocus=true`，防止焦点跳回编辑器。  
   - **状态**：Open，P1，help wanted。  
   - **链接**：[#29378](https://github.com/google-gemini/gemini-cli/pull/29378)

### 5. **[fix(core)] 修复 OAuth 刷新后丢失 refresh_token**（#29339）  
   - **说明**：解决因令牌覆盖导致的重新认证死循环。  
   - **状态**：已关闭（merged），P1。  
   - **链接**：[#29339](https://github.com/google-gemini/gemini-cli/pull/29339)

### 6. **[fix(core)] 停止在 Windows 上运行 Unix ps 命令**（#29376）  
   - **说明**：修复 IDE 检测回退逻辑在 Windows 下执行 Unix 命令的错误。  
   - **状态**：Open，size/m。  
   - **链接**：[#29376](https://github.com/google-gemini/gemini-cli/pull/29376)

### 7. **[fix(core)] 防止在会话恢复时重放两次工具响应**（#29366）  
   - **说明**：恢复会话导致每次工具结果被发送两次，引起后端配对校验失败。  
   - **状态**：Open，P1，size/l。  
   - **链接**：[#29366](https://github.com/google-gemini/gemini-cli/pull/29366)

### 8. **[fix(acp)] 允许无可恢复内容时仍通过 ID 加载 session**（#29368）  
   - **说明**：修复非交互模式下 session 加载失败问题，#29288。  
   - **状态**：Open，P1。  
   - **链接**：[#29368](https://github.com/google-gemini/gemini-cli/pull/29368)

### 9. **[fix(ui)] 防止边框渲染中负布局尺寸导致崩溃**（#29347）  
   - **说明**：增加 `Math.max(0, ...)` 防护，修复 `RangeError: Invalid count value: -1`。  
   - **状态**：已关闭（merged），P1。  
   - **链接**：[#29347](https://github.com/google-gemini/gemini-cli/pull/29347)

### 10. **[fix(cli)] 避免截断时拆分 UTF-16 代理对**（#29304）  
   - **说明**：修复 `sanitizeForDisplay` 在 emoji 边界截断产生无效代理对的问题。  
   - **状态**：Open，size/s。  
   - **链接**：[#29304](https://github.com/google-gemini/gemini-cli/pull/29304)

---

## 功能需求趋势

从近 24 小时活跃的 Issues 中可提炼以下社区重点关注方向：

1. **Agent 行为可控性与透明性**  
   - 子代理执行轨迹共享（#22598）、子代理上下文在 bug 报告中体现（#21763）、Agent 自动调用技能的意愿不足（#21968）等，表明社区希望更深入了解 Agent 内部决策过程。

2. **记忆系统（Auto Memory）安全与效率**  
   - 敏感信息脱敏（#26525）、低信号会话循环（#26522）、无效补丁隔离（#26523）等，记忆模块正成为安全与性能热点。

3. **终端与环境兼容性**  
   - Wayland 下浏览器代理失败（#21983）、Windows ConPTY 问题（#29379）、Shell 执行挂起（#25166）等，多平台稳定性仍是刚需。

4. **AST 感知的文件操作**  
   - EPIC #22745 和 #22746 持续讨论基于 AST 的代码搜索与读取，期望提升代理解码精准度并减少 Token 浪费。

5. **安全管理与防护**  
   - 环境变量脱敏文档修复（#29372）、禁止破坏性操作（#22672）表明社区对代码和配置安全的重视。

---

## 开发者关注点

| 痛点 / 高频需求 | 对应 Issue / PR 数量 | 说明 |
|----------------|----------------------|------|
| **Agent 挂起与无限等待** | #21409, #25166, #22465 | 通用代理、Shell、交互式工具均存在挂起，影响日常使用。 |
| **代理不主动调用技能** | #21968 | 配置了 git、gradle 技能但 Gemini 几乎不用，需用户显式命令。 |
| **子代理恢复逻辑错误** | #22323, #29367 | 最大轮次被误报成功，掩盖失败，降低信任度。 |
| **记忆系统资源浪费** | #26522, #26523 | 低信号会话反复处理、无效补丁积累，需更智能的裁剪机制。 |
| **跨平台兼容性** | #21983 (Wayland), #29379 (ConPTY), #29376 (Windows) | 非主流平台用户频繁遇到特定崩溃。 |
| **令牌令牌与内存优化** | #19561 (Tactful Extraction), #21335 (/compress不持久), #29304 (surrogate pair) | 社区对降低 Token 消耗、提升上下文利用率有持续需求。 |
| **文档与提示错误** | #29371, #29372, #29374 | 配置文档与实际 schema 不一致，多个 PR 正在修正。 |

---

**总结**：今日社区动态揭示了 Gemini CLI 正从“增加功能”转向“修复稳定性与安全漏洞”，尤其是 Agent 执行生命周期与记忆系统的修复占据了 half 以上关键 PR。开发者应重点关注 Shell/PTY 相关挂起问题及子代理行为正确性。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区动态日报 — 2026-09-18

## 今日速览
- **v1.0.86 发布**：自定义代理可通过 frontmatter 配置集成仓库指令文件（`AGENTS.md` 等），会话恢复行为优化。
- **Figma MCP 远程服务器不兼容**：`server/discover` 返回 `-32601` 被 CLI 视为致命错误，导致工具无法注册，成为社区焦点（Issue #4870，9 👍）。
- **Windows 插件更新权限问题**持续高热度（22 👍），社区呼吁尽快修复 `Access is denied` 错误。

## 版本发布
### v1.0.86（2026-09-17）
- **自定义代理可 opt-in 仓库指令文件**：在 frontmatter 中设置 `include-custom-instructions: true` 后，代理将读取 `AGENTS.md`、`copilot-instructions.md`、`CLAUDE.md`。
- **会话恢复优化**：恢复活动会话时，若未指定 `plugin-directory`、`discovery` 或 `working-directory` 覆盖，则保留已有配置，减少意外变更。

## 社区热点 Issues
### 1. Figma MCP 远程服务器无法注册工具（#4870）
- **状态**：OPEN / Triage  
- **要点**：`https://mcp.figma.com/mcp` 认证成功，但 CLI 在 `server/discover` 阶段收到 `-32601` 错误后标记为致命失败，导致 Figma 工具始终不可用。  
- **为什么重要**：直接影响 Figma 设计稿与 Copilot 的 MCP 集成，用户需靠其它客户端（如 VS Code）绕行。  
- **社区反应**：5 条评论，9 个 👍，用户已提供完整抓包日志，开发组标记为 triage。  
  [链接](https://github.com/github/copilot-cli/issues/4870)

### 2. 会话恢复中断正在初始化的 stdio MCP 连接（#4753）
- **状态**：CLOSED  
- **要点**：v1.0.83 引入回归——恢复会话时，前台交接会导致仍在初始化中的 MCP 服务器连接被取消（超时从 ~16s 缩短至 ~1s），使这些服务器在整个会话中不可用。  
- **为什么重要**：MCP 是 CLI 扩展能力的核心，该回归严重破坏依赖动态 MCP 服务器的工作流。  
- **社区反应**：4 条评论，2 个 👍，已被修复（关闭）。  
  [链接](https://github.com/github/copilot-cli/issues/4753)

### 3. Agent Plugins 1.0：自定义代理未被发现（#4655）
- **状态**：CLOSED  
- **要点**：根据规范放置在 `com.github.copilot/agents` 目录下的自定义代理无法被 CLI 发现，导致技能和 MCP 服务器无法通过该代理使用。  
- **为什么重要**：Agent Plugins 1.0 是生态扩展的关键能力，该 bug 阻塞了第三方代理的部署。  
- **社区反应**：4 条评论，已关闭（推测已修复）。  
  [链接](https://github.com/github/copilot-cli/issues/4655)

### 4. HTTP/2 无效会话导致频繁重试（#3304）
- **状态**：OPEN  
- **要点**：CLI 反复出现 `ERR_HTTP2_INVALID_SESSION`，导致请求失败并进入无限重试循环，尤其在长推理响应中多发。  
- **为什么重要**：严重影响日常使用，用户必须强制退出。该问题自 5 月以来一直未关闭。  
- **社区反应**：4 条评论，无👍但影响面广。  
  [链接](https://github.com/github/copilot-cli/issues/3304)

### 5. 请求新增 `--disable-repo-mcps` 标志（#3380）
- **状态**：OPEN  
- **要点**：目前无法忽略仓库自带的 `.mcp.json` / `.github/mcp-config.json`，只能逐个禁用 MCP 服务器。用户希望一次性跳过所有仓库 MCP。  
- **为什么重要**：提升团队协作灵活性，避免不可信的仓库 MCP 自动加载。  
- **社区反应**：3 条评论，1 个 👍。  
  [链接](https://github.com/github/copilot-cli/issues/3380)

### 6. Windows：插件更新时“访问被拒绝”（#4095）
- **状态**：OPEN  
- **要点**：当 VS Code 运行且 Copilot 扩展持有插件目录的 watcher 句柄时，`copilot plugin update` 失败并返回 `Access is denied (os error 5)`。  
- **为什么重要**：Windows 用户高频痛点，22 个 👍 表明受影响人数多。  
- **社区反应**：3 条评论，22 个 👍。  
  [链接](https://github.com/github/copilot-cli/issues/4095)

### 7. Model 模式 Auto 下 `/btw` 或 `/ask` 返回错误（#4887）
- **状态**：OPEN / Triage  
- **要点**：选择 Auto 模型后，使用 `/btw` 或 `/ask` 命令时 CLI 报错，而手动指定具体模型则正常。  
- **为什么重要**：Auto 模式是默认设置，该问题影响大部分用户的基础指令。  
- **社区反应**：3 条评论，新报告（昨日）。  
  [链接](https://github.com/github/copilot-cli/issues/4887)

### 8. `--plugin-dir` 加载的技能在 `/skills` 和 `/env` 中缺失（#4886）
- **状态**：OPEN / Triage  
- **要点**：通过 `--plugin-dir` 提供的本地插件技能虽被后端发现、`copilot skill list --json` 也正确输出，但在交互式 `/skills` 面板和 `/env` 中被忽略。  
- **为什么重要**：本地插件用户无法以交互方式管理技能，降低了开发效率。  
- **社区反应**：2 条评论。  
  [链接](https://github.com/github/copilot-cli/issues/4886)

### 9. Google Workspace MCP OAuth 因尾部斜杠 issuer 不匹配失败（#4606）
- **状态**：OPEN  
- **要点**：Google 官方 Workspace MCP 端点返回的 issuer URL 为 `https://accounts.google.com/`（带斜杠），但 CLI 的 OAuth 实现要求精确匹配，导致授权流程中断。  
- **为什么重要**：阻塞了 Google Workspace 的 MCP 集成，企业用户受影响。  
- **社区反应**：2 条评论，1 个 👍。  
  [链接](https://github.com/github/copilot-cli/issues/4606)

### 10. 每小时的扩展主机和 MCP 服务器重枚举（#4892）
- **状态**：OPEN / Triage  
- **要点**：CLI 每过一小时会重新枚举所有扩展主机和 MCP 服务器，导致短暂的中断或资源消耗。  
- **为什么重要**：影响长期运行的会话稳定性，尤其在密集 MCP 使用场景中。  
- **社区反应**：1 条评论（含更正信息）。  
  [链接](https://github.com/github/copilot-cli/issues/4892)

## 重要 PR 进展
过去 24 小时内无新的合并或更新拉取请求。

## 功能需求趋势
- **MCP 集成增强**：社区持续要求更灵活的 MCP 控制（如禁用仓库 MCP、改善远程 MCP 兼容性、处理 OAuth 边缘情况）。
- **代理与插件生态**：自定义代理的发现、指令文件集成、技能面板可见性是近期高频请求。
- **平台兼容性**：Windows 文件锁问题（#4095）和 FreeBSD 平台被移除（#3382 已关闭但用户不满）显示跨平台支持的紧迫性。
- **用户体验改进**：Native 通知、任务栏图标可禁用、键盘输入行为（退格键删词）等细节优化受到关注。
- **模型选择可靠性**：Auto 模式下命令错误、不可用模型选择导致数据丢失等问题凸显模型路由的脆弱性。

## 开发者关注点
- **MCP 稳定性**：会话恢复中断 MCP 连接、远程 MCP 错误处理不够优雅是用户最大的挫败点。
- **Windows 权限问题**：插件更新时与 VS Code 文件句柄冲突，影响日常升级流程。
- **会话数据安全**：会话切换导致计划审批界面丢失、数据丢失（#4319、#3553）令用户不敢依赖长期会话。
- **调试信息缺乏**：`ERR_HTTP2_INVALID_SESSION` 等错误缺少清晰原因和重试策略说明。
- **自定义代理壁垒**：`--plugin-dir` 技能在交互式面板中不可见、代理无法跨会话使用不同模型端点，限制高级用户定制能力。

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

# Kimi Code CLI 社区动态日报  
**日期：2026-09-18**  
数据来源：github.com/MoonshotAI/kimi-cli  

---

## 今日速览  
- 社区提交一项关键修复 PR（#2651），旨在解决工具调用重复循环问题，避免无限重复执行相同调用。  
- 新上报两个 Bug：Kimi Desktop 的“梦境记忆”开关异常（#2649）和子代理启动时 OAuth 认证超时（#2650），均指向稳定性与配置管理痛点。  
- 历史 Issue #1276（@ 自动补全缺少文件）已于昨日关闭，修复状态待验证。  

---

## 版本发布  
过去 24 小时内无新版本发布。  

---

## 社区热点 Issues（共 3 条）  

1. **[Bug] Kimi Desktop “chat 记忆 / 梦境记忆”开关拨动后不写入配置**  
   - **编号**：#2649  
   - **作者**：GH-Mason  
   - **重要性**：影响会员用户（Vivace）的核心功能，开关视觉上生效但实际配置未写入，疑似服务端功能门控未放行。社区 2 条评论，用户尝试排查 `daimon/config.json` 发现 `features.memory.dream` 等字段未更新。  
   - **链接**：https://github.com/MoonshotAI/kimi-cli/issues/2649  

2. **[Bug] 子代理启动间歇性失败：OAuth token 获取超时（auth.kimi.ai）**  
   - **编号**：#2650  
   - **作者**：genhoi  
   - **重要性**：即使主会话认证正常，子代理（subagent）仍会因 `auth.kimi.ai` 连接超时而间歇崩溃，重试后可恢复。该问题影响多代理协作场景的可靠性，目前无评论，需开发者介入。  
   - **链接**：https://github.com/MoonshotAI/kimi-cli/issues/2650  

3. **[Bug] `@` 自动补全缺少文件（已关闭）**  
   - **编号**：#1276  
   - **作者**：hongquan  
   - **重要性**：在 Linux 平台、Kimi CLI 1.16.0 及 kimi-k2.5 模型下，`@` 引用时文件列表不完整。经 9 个月跟踪后于昨日关闭，修复内容未明确，社区可关注后续 Release 说明。  
   - **链接**：https://github.com/MoonshotAI/kimi-cli/issues/1276  

> 说明：过去 24 小时仅更新上述 3 条 Issue，已全部列出。  

---

## 重要 PR 进展（共 1 条）  

1. **修复：阻止重复工具调用循环**  
   - **编号**：#2651  
   - **作者**：Oxygen56  
   - **状态**：OPEN  
   - **功能/修复内容**：将重复工具调用的防护从 “达到阈值后仍执行最后一次并设置标志” 改为 **硬性停止**，避免继续执行后续重复调用。对应 Issue #2637 中的无限循环问题。该 PR 直接提升 Chat 工具链的稳定性，减少无效 API 消耗。  
   - **链接**：https://github.com/MoonshotAI/kimi-cli/pull/2651  

> 说明：过去 24 小时仅更新上述 1 条 PR。  

---

## 功能需求趋势  
结合当前 Issues 可提炼出社区近期关注的三个方向：  

- **配置持久化与同步**（#2649）：用户期望开关状态能真正写入本地/云端配置，而非仅 UI 展示。  
- **认证稳定性**（#2650）：OAuth 端点间歇性超时导致子代理无法启动，需增强重试机制或前端超时容忍度。  
- **补全体验**（#1276 已关闭）：`@` 引用文件列表完整性问题虽已修复，但说明社区对 CLI 交互中上下文感知补全的准确性有较高要求。  

---

## 开发者关注点  
- **配置不一致**：梦境记忆功能开关拨动后 `config.json` 未更新，怀疑服务端功能门控策略未同步到客户端，开发者需检查 `features.memory.dream` 的读写逻辑与后端接口。  
- **认证超时无降级**：子代理启动时 OAuth 超时直接导致整个 spawn 失败，而主会话工作正常，暴露了认证路径的单点脆弱性。建议增加重试或独立认证缓存。  
- **历史 Bug 修复周期**：#1276 从 2026-02 至 2026-09 将近 7 个月才关闭，社区对低频 Bug 的响应速度可能有更高期待。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

好的，作为专注 AI 开发工具的技术分析师，以下是为您生成的 2026 年 9 月 18 日 OpenCode 社区动态日报。

---

# OpenCode 社区动态日报 - 2026-09-18

## 今日速览

今日社区动态主要围绕 **“免费层验证逻辑错误”** 引发的广泛讨论，多个用户反馈在官方桌面应用及 VSCode 插件中错误地触发了“只能在 OpenCode 中使用”的限制。此外，**DeepSeek V4 Flash 模型的访问限制** 与 **1.18.30 版本的关键回归问题** 是社区关注的另外两个核心焦点。由社区贡献的 **VS Code 活动栏集成** 是今日最受期待的 PR，有望显著提升开发体验。

## 社区热点 Issues

1.  **免费层使用限制误报 (Issue #49433)**
    - **重要性**: 今日最热门的议题，27条评论。大量用户反馈在使用官方桌面应用和 VSCode 插件时，错误地触发了“OpenCode's free tier can only be used from within OpenCode”的报错，导致无法正常使用免费模型，影响了基本操作。
    - **链接**: https://github.com/anomalyco/opencode/issues/49433

2.  **DeepSeek V4 Flash 模型地区限制 (Issue #39845)**
    - **重要性**: 持续发酵，24条评论，30个👍。用户反馈 DeepSeek V4 Flash 模型突然要求启用“中国托管”选项，即使有订阅也无法使用，引发了关于模型可用性和服务条款的讨论。
    - **链接**: https://github.com/anomalyco/opencode/issues/39845

3.  **Go 模型上游请求失败 (Issue #37231)**
    - **重要性**: 一个长期存在的服务端错误，22条评论。所有 Go 系列模型都返回“Upstream request failed”错误，影响 CLI、桌面端和 VSCode 扩展，表明后端服务可能存在稳定性问题。
    - **链接**: https://github.com/anomalyco/opencode/issues/37231

4.  **无法解释的服务器错误 (Issue #29748)**
    - **重要性**: 14条评论，一个持续数月的问题。用户在使用 OpenRouter API 后频繁遇到“Unexpected server error”，排除重启后仍然重现，影响核心功能。
    - **链接**: https://github.com/anomalyco/opencode/issues/29748

5.  **1.18.30 版本回归：TypeError 崩溃 (Issue #48645)**
    - **重要性**: 10条评论，17个👍。一个严重的回归问题，用户在升级到最新版后，每次 prompt 都会因 `TypeError in SystemPrompt.environment` 而崩溃，不得不回退到旧版本。**此问题急需官方修复。**
    - **链接**: https://github.com/anomalyco/opencode/issues/48645

6.  **桌面端加载会话失败 (Issue #42170)**
    - **重要性**: 7条评论。桌面版 1.18.17 启动时无法加载会话，报数据库错误“no such column: project_id”，可能导致用户数据无法访问。
    - **链接**: https://github.com/anomalyco/opencode/issues/42170

7.  **旧会话恢复失败 (Issue #48973)**
    - **重要性**: 6条评论，8个👍。在使用“Muse Spark”免费模型时，恢复旧会话会出现 `encrypted_content` 授权错误，表明会话持久化或身份验证机制存在问题。
    - **链接**: https://github.com/anomalyco/opencode/issues/48973

8.  **会话成本不包含子代理成本 (Issue #45417)**
    - **重要性**: 4条评论，11个👍。这是一个关于计费准确性的重要问题。用户发现报告的会话成本仅为直接消耗，未包含由该会话启动的子代理成本，导致账单核对困难。
    - **链接**: https://github.com/anomalyco/opencode/issues/45417

9.  **macOS 二进制文件签名失效 (Issue #46313)**
    - **重要性**: 5条评论。v1.18.25 的 macOS 发布版本未能通过 `codesign` 验证，可能导致用户在非 App Store 环境下安装受阻或出现安全警告。
    - **链接**: https://github.com/anomalyco/opencode/issues/46313

10. **OpenCode 在白俄罗斯停止服务 (Issue #49598)**
     - **重要性**: 3条评论，涉及区域可用性的敏感话题。用户报告 OpenCode 在白俄罗斯完全无法使用，同时该国发行的万事达卡也被拒付，引发了关于服务区域政策的讨论。
     - **链接**: https://github.com/anomalyco/opencode/issues/49598

## 重要 PR 进展

1.  **feat(vscode): 在活动栏添加 OpenCode 入口 (PR #49643)**
    - **功能**: 一个新的 VS Code 扩展功能，将 OpenCode 直接集成到活动栏，提供侧边栏快捷操作。
    - **链接**: https://github.com/anomalyco/opencode/pull/49643

2.  **fix(tui): 在吞吐量中包含推理 Token (PR #48689)**
    - **修复**: 修复了 TUI 中 Token 吞吐量指标不计算推理 Token 的问题，使性能数据更准确。
    - **链接**: https://github.com/anomalyco/opencode/pull/48689

3.  **fix(app): 仅在需要时显示 SSH 认证提示 (PR #49642)**
    - **修复**: 优化了 SSH 连接的用户体验，不再默认为所有连接显示认证界面，仅在需要时弹出。
    - **链接**: https://github.com/anomalyco/opencode/pull/49642

4.  **feat(core): 修复工具参数错误 (PR #45002)**
    - **功能/修复**: 引入了一项内部机制，可以在模型传参不合规时自动修复，避免因小错误导致工具调用失败。
    - **链接**: https://github.com/anomalyco/opencode/pull/45002

5.  **fix(session-ui): 修复实时 Markdown 渲染时的 UI 闪动 (PR #48432)**
    - **修复**: 解决了流式 Markdown 渲染时终端界面位置偏移和闪烁的问题，提升了阅读体验。
    - **链接**: https://github.com/anomalyco/opencode/pull/48432

6.  **feat(opencode): 本地局域网提供商发现 (PR #27554)**
    - **功能**: 一个长期开发的实质性功能，允许 OpenCode 通过 mDNS 等方式自动发现局域网内的 OpenAI 兼容服务器，简化本地模型部署。
    - **链接**: https://github.com/anomalyco/opencode/pull/27554

7.  **fix(tui): 隐藏后台状态提示 (PR #49637)**
    - **修复**: 修复了 TUI 的一个小缺陷，当所有子任务都在后台运行时，不再显示“移至后台”的提示。
    - **链接**: https://github.com/anomalyco/opencode/pull/49637

8.  **fix(core): 修复中断后无法撤销已接受消息 (PR #49636)**
    - **修复**: 解决了在中断场景下的撤销功能缺陷，现在可以正确撤销已被接受但尚未完成的消息。
    - **链接**: https://github.com/anomalyco/opencode/pull/49636

9.  **docs: 添加波斯语 README 翻译 (PR #47783)**
    - **文档**: 新增了波斯语版本的 README，对全球社区合作做出了贡献。
    - **链接**: https://github.com/anomalyco/opencode/pull/47783

10. **feat(opencode): 导出结构化会话使用数据 (PR #48822)**
    - **功能**: 新增 `usage-json` 和 `usage-csv` 导出格式，方便用户分析和审计会话消耗。
    - **链接**: https://github.com/anomalyco/opencode/pull/48822

## 功能需求趋势

-   **深度的 IDE 集成**: 除了现有的 VSCode 扩展，社区强烈希望将 OpenCode 更无缝地集成到 IDE 中（如活动栏），提升交互便利性。
-   **多样化的模型支持与访问**: 用户不仅关注新模型（如 DeepSeek V4），更对模型的可访问性（如地区限制、付费验证）非常敏感。
-   **核心性能与稳定性**: 回归性能和服务器端错误是最大痛点。用户期待更严格的版本发布测试和更稳定的后端服务。
-   **透明的计费与资源管理**: 对会话成本的准确核算需求增加，尤其是在多代理场景下，用户希望能清晰了解每一笔开销。
-   **系统兼容性与国际化**: macOS 的代码签名、特定国家的服务可用性、多语言文档，都反映了OpenCode在支持更广泛用户群体方面仍有待改进。

## 开发者关注点

-   **“免费层”验证逻辑的误伤**: 这是开发者使用官方客户端（Desktop & VSCode）时最主要的障碍，严重影响新用户和免费用户的体验，急需官方排查和修复。
-   **模型的“区域限制”与强制启用机制**: DeepSeek V4 Flash 模型的案例引发了开发者对模型自主选择和潜在数据隐私问题的担忧。
-   **版本发布的稳健性不足**: `TypeError` 回归问题暴露了测试流程的疏漏。开发者普遍建议增加回归测试，或在发布日志中明确说明可能导致问题的变更。
-   **后端服务的可靠性**: “Upstream request failed”这类通用错误时有发生，开发者需要更具体的错误信息和更迅速的服务恢复。
-   **macOS 应用的“代码签名”问题**: 影响了直接下载二进制文件的用户，增加了非 App Store 分发的信任成本。

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 | 2026-09-18

## 今日速览

过去 24 小时内，社区围绕 **错误重试逻辑、会话压缩溢出、Windows 兼容性** 展开了密集修复与讨论。3 个由 Malformed `Retry-After` 引发的 `NaN` 延迟、空体 4xx 误判为上下文溢出等中高风险 bug 已被 PR 修复或正处于审查中。同时，多个新 Provider 支持（Azure Foundry Chat Completions、GMI Cloud、LLM Gateway）进入 PR 阶段，折射出社区对多模型接入的持续需求。

## 社区热点 Issues

挑选 10 个当前关注度最高、影响较大的 Issue：

1. **[#9571] provider retry: malformed Retry-After HTTP-date retries immediately (NaN delay)**  
   - 评论: 6 | 👍: 0  
   - 简介：当 `Retry-After` 头既不是数字也不是合法 HTTP 日期时，`getRetryDelayMs` 计算得到 `NaN`，导致重试零延迟，可能触发限流雪崩。  
   - 重要性：直接影响所有 API 429 的重试行为，属于运行时稳定性缺陷。  
   - 链接：[#9571](https://github.com/earendil-works/pi/issues/9571)

2. **[#9482] Empty-body 400 from OpenAI-compatible gateways misclassified as context overflow → destructive auto-compaction destroys up to ~400k tokens**  
   - 评论: 2 | 👍: 0  
   - 简介：空体 400 错误被误判为“上下文超长”，触发自动压缩并销毁大量历史对话（最多 40 万 token），极其隐蔽且破坏性大。  
   - 重要性：社区标注为 **serious, non-cosmetic**，直接降低 Pi 的工作质量，是当日最危险的 bug。  
   - 链接：[#9482](https://github.com/earendil-works/pi/issues/9482)

3. **[#9361] Windows: settings shellPath is non-deterministically ignored when extensions are loaded**  
   - 评论: 6 | 👍: 0  
   - 简介：Windows 下加载扩展后，`settings.json` 中的 `shellPath` 被随机忽略，退回到 WSL System32 中的 bash，导致工具执行环境不稳定。  
   - 重要性：Windows 用户的核心体验问题，搜索与调试困难。  
   - 链接：[#9361](https://github.com/earendil-works/pi/issues/9361)

4. **[#8684] `PI_OFFLINE` silently disables all provider model discovery — undocumented behavior**  
   - 评论: 10 | 👍: 0  
   - 简介：文档说明 `PI_OFFLINE` 仅禁用启动时网络检查，实际却关闭了所有 Provider 模型目录的网络发现，影响整个会话的模型可用性。  
   - 重要性：文档与行为严重不符，可能导致用户在离线模式下无法使用本地模型。  
   - 链接：[#8684](https://github.com/earendil-works/pi/issues/8684)

5. **[#9602] Compaction can overflow by including thinking messages omitted from earlier model requests**  
   - 评论: 5 | 👍: 0  
   - 简介：长会话中，模型响应达到 output limit 后，压缩操作将仅含 thinking 的消息也纳入压缩输入，导致压缩请求超过上下文窗口。  
   - 重要性：可能导致后续请求失败，影响长会话的连续性。  
   - 链接：[#9602](https://github.com/earendil-works/pi/issues/9602)

6. **[#9391] After compaction, stale signed thinking blocks are replayed every turn; Anthropic drops them**  
   - 评论: 4 | 👍: 1  
   - 简介：手动压缩后，每次请求都会重放已过期的 thinking block，Anthropic 因 `prefix_binding_mismatch` 丢弃它们，但 Pi 仍持续发送，浪费请求。  
   - 重要性：影响 Anthropic 用户的使用效率，增加 token 消耗。  
   - 链接：[#9391](https://github.com/earendil-works/pi/issues/9391)

7. **[#9647] Emit session_compact_end event to extensions after clearing compaction state**  
   - 评论: 4 | 👍: 0  
   - 简介：`session_compact` 事件在清除压缩状态前发出，导致扩展无法正确判断 idle 或发送后续消息，扩展 API 设计缺陷。  
   - 重要性：影响扩展开发生态，需调整事件触发时机。  
   - 链接：[#9647](https://github.com/earendil-works/pi/issues/9647)

8. **[#9708] Migration rewrites the session file in place with no backup**  
   - 评论: 3 | 👍: 0  
   - 简介：打开旧版会话文件时，Pi 会原地重写且无备份，中断情况下可能造成数据丢失。社区已标记为 `last-read, no-action`，但风险仍存。  
   - 重要性：数据安全性问题，建议关注后续措施。  
   - 链接：[#9708](https://github.com/earendil-works/pi/issues/9708)

9. **[#9036] openai-codex SSE parser buffers the whole response in one string, fatal heap OOM**  
   - 评论: 3 | 👍: 0  
   - 简介：Codex 响应流解析器将整个响应缓冲为单字符串，导致大输出时 V8 堆内存溢出、进程崩溃。  
   - 重要性：影响使用 Codex 模型的用户，属于内存安全 bug。  
   - 链接：[#9036](https://github.com/earendil-works/pi/issues/9036)

10. **[#9681] stopReason "toolUse" with no tool_use content block ends the turn silently**  
   - 评论: 2 | 👍: 0  
   - 简介：Anthropic API 返回 `stop_reason: "tool_use"` 但无 content block 时，Pi 不报错也不执行任何操作，用户误以为程序挂起。  
   - 重要性：边缘情况导致无反馈，影响用户体验。  
   - 链接：[#9681](https://github.com/earendil-works/pi/issues/9681)

## 重要 PR 进展

挑选 10 个重要 PR（包括修复、功能、测试优化）：

1. **[#9724] fix(ai): fall back to exponential backoff for malformed Retry-After dates**  
   - 状态：已合并 | 作者：Frank-zhu0404  
   - 简介：直接修复 #9571，将无法解析的 `Retry-After` 日期视为缺失，回退指数退避，并添加 `NaN` 校验。  
   - 链接：[#9724](https://github.com/earendil-works/pi/pull/9724)

2. **[#9722] fix(ai): retry opaque 4xx errors without a diagnostic body**  
   - 状态：已合并 | 作者：jtomek-strike48  
   - 简介：解决空体 400 被误判为上下文超长（#9482）的根本原因——将无 body 的 4xx 错误加入可重试列表，避免直接进入灾难性压缩。  
   - 链接：[#9722](https://github.com/earendil-works/pi/pull/9722)

3. **[#9717] fix(coding-agent): bound thinking-only messages in compaction summaries**  
   - 状态：已合并 | 作者：BlazeStorm001  
   - 简介：修复 #9602，限制仅含 thinking 的响应在压缩摘要中的大小，防止压缩请求溢出。  
   - 链接：[#9717](https://github.com/earendil-works/pi/pull/9717)

4. **[#9720] fix(ai): drive Mistral reasoning dispatch via thinkingLevelMap, add zai-glm-5-3**  
   - 状态：已合并 | 作者：amol-  
   - 简介：改用 `thinkingLevelMap` 判断 Mistral 模型是否支持推理，并添加 `zai-glm-5-3` 模型支持。  
   - 链接：[#9720](https://github.com/earendil-works/pi/pull/9720)

5. **[#9714] feat(ai): support Azure Foundry Chat Completions deployments**  
   - 状态：Open | 作者：jsanter27  
   - 简介：为 Azure Foundry 部署添加 Chat Completions API 支持（如 DeepSeek V4 Pro），扩展 Azure Provider 能力。  
   - 链接：[#9714](https://github.com/earendil-works/pi/pull/9714)

6. **[#9668] feat(coding-agent): add prompt cache warming**  
   - 状态：Open (WIP) | 作者：mitsuhiko  
   - 简介：实验性支持缓存预热，旨在减少长会话中的首请求延迟，提升响应速度。  
   - 链接：[#9668](https://github.com/earendil-works/pi/pull/9668)

7. **[#9630] feat(coding-agent): add event handler unsubscribe**  
   - 状态：已合并 | 作者：rwachtler  
   - 简介：为 `pi.on(...)` 添加取消订阅功能，并确保事件分发期间安全处理 handler 增删。  
   - 链接：[#9630](https://github.com/earendil-works/pi/pull/9630)

8. **[#9692] fix(tui): clip overflowing render lines instead of crashing**  
   - 状态：已合并 | 作者：982945902  
   - 简介：修复 #9691——当渲染行超过终端宽度时，不再抛出未捕获异常导致崩溃，而是裁剪超出部分。  
   - 链接：[#9692](https://github.com/earendil-works/pi/pull/9692)

9. **[#9694] test(ai): update DeepSeek flash model references to v4**  
   - 状态：已合并 | 作者：ngtrthanh  
   - 简介：更新测试中过时的 DeepSeek 模型 ID（`deepseek-flash` → `deepseek-v4-flash`），解决 CI 失败。  
   - 链接：[#9694](https://github.com/earendil-works/pi/pull/9694)

10. **[#7610] feat(ai): add LLM Gateway and LLM Gateway DevPass providers**  
   - 状态：Open | 作者：RATCHAW  
   - 简介：新增两个 OpenRouter 风格的 Provider，支持 LLM Gateway 生态，进一步丰富模型接入选项。  
   - 链接：[#7610](https://github.com/earendil-works/pi/pull/7610)

## 功能需求趋势

从近期 Issues 和 PR 中可看出社区最关注的几个功能方向：

- **Provider 扩展与兼容性**：Azure Foundry Chat Completions、GMI Cloud、LLM Gateway、OpenCode 等新 Provider 的需求持续涌现，反映用户希望 Pi 能覆盖更多推理服务。
- **错误处理与弹性重试**：多个 bug 集中在 HTTP 429/4xx 重试逻辑、空体误判、退避计算等问题上，社区对健壮性的期待很高。
- **会话管理安全**：压缩、迁移等操作缺乏保护机制（无备份、状态冲突、时间戳错误）引起多次讨论，用户希望增加备份与验证。
- **Windows 与跨平台体验**：Windows 下 shell 路径非确定性、路径分隔符硬编码等问题仍在修复中，跨平台一致性是关键痛点。
- **UI/终端体验优化**：可配置的 tool shell 间距、全屏选择样式、鼠标模式恢复等功能被提出，说明用户对终端交互细节有更高要求。

## 开发者关注点

高频反馈与痛点总结：

- **重试延迟 Bug**：因 `NaN` 导致的零延迟重试（#9571）与空体 400 被误判为上下文溢出（#9482）均被社区标记为严重问题，前者已有 PR 修复，后者通过 #9722 得以缓解。
- **会话数据安全**：迁移直接重写无备份（#9708）引发担忧，开发者期待加入 `--backup` 或自动备份机制。
- **Windows 兼容性**：`shellPath` 不可靠（#9361）限制了 Windows 用户使用 bash 工具，修复进展缓慢。
- **非 ASCII 文本复制乱码**（#9684）：pbcopy 回退编码错误，影响国际化用户。
- **事件与状态一致性**：`session_compact` 事件发出时机错误（#9647）、`--print` 静默空输出（#9718）等问题考验扩展开发的可靠性。

社区整体修复积极性高，上述核心 bug 大多在当日有对应 PR 被合并或开启

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报  
**日期：2026-09-18**  
**数据来源：** [github.com/QwenLM/qwen-code](https://github.com/QwenLM/qwen-code)

---

## 📌 今日速览

- **两个版本同时发布**：`v0.24.0-nightly.20260917` 完成 ACP 边界收敛文档合并，`desktop-v0.24.0` 新增共享输出模式并修复 CLI 权限队列作用域问题。
- **四项 P1 级 Bug 报告活跃**：React 崩溃 #11732（长任务后 TUI 进程死亡）、回调身份变化导致调度器被替换 (#12061)、session 删除导致文件头丢失 (#12091)、以及 `isAsyncOperator` 漏洞可能绕过 Bash 权限规则 (#11851)。
- **社区关注焦点转向 Context 性能与 ACP 稳定性**：多项 Issues 讨论 token 预算缩放反直觉、evidence catalog 冗余开销、Goal 运行时简化和工作树权限入库错误。

---

## 🚀 版本发布

### 1. `v0.24.0-nightly.20260917.f822124af5`
- **What's Changed**
  - `docs(serve): record merged ACP boundary acceptance` – 记录 ACP 边界评审的接受记录，供后续追踪。
  - `fix(ci): wait for the published export re` – 修复 CI 中发布导出重试的等待问题。
- **Release 链接**：[v0.24.0-nightly.20260917](https://github.com/QwenLM/qwen-code/releases/release/v0.24.0-nightly.20260917.f822124af5)

### 2. `desktop-v0.24.0`（桌面客户端）
- **What's Changed**
  - `fix(cli): scope the ACP permission queue to the session` – 将 ACP 权限队列作用域限定在 session 内，避免跨会话影响。
  - `feat(channels): add shared output modes` – 新增共享输出模式，支持多通道协作场景。
- **Release 链接**：[desktop-v0.24.0](https://github.com/QwenLM/qwen-code/releases/tag/desktop-v0.24.0)

---

## 🔥 社区热点 Issues（10条）

### 1. `#9278` [Design] `/review` publish-time convergence advisory  
**标签**：P2 / feature-request / commands  
**摘要**：完整保存 `/review` 发布时收敛建议的设计与实测记录，跟踪各工作项交付，避免设计散落。核心问题在于 Agent 修复循环中回路增益过大，唯一的阻尼器是 `AGENTS.md` 中的 prose。  
**评论数**：10 | **最新更新**：2026-09-17  
**链接**：[#9278](https://github.com/QwenLM/qwen-code/issues/9278)

### 2. `#11732` [Critical] React error #185 crash after native monitor task  
**标签**：P1 / bug / ui / rendering  
**摘要**：Qwen Code 0.23.3 在通过 native monitor 启动长任务后，因未捕获的 React 错误 #185（最大更新深度超限）导致 TUI 进程崩溃。已在两个独立 session 中确认复现。  
**评论数**：8 | **最新更新**：2026-09-17  
**链接**：[#11732](https://github.com/QwenLM/qwen-code/issues/11732)

### 3. `#12061` [Bug] Callback identity changes replace active tool scheduler  
**标签**：P2 / bug / cli / interactive  
**摘要**：`useReactToolScheduler` 在调用者回调标识改变时重建 `CoreToolScheduler`，导致正在执行 tool batch 的调度器被静默替换，引发状态泄漏。  
**评论数**：8 | **最新更新**：2026-09-17  
**链接**：[#12061](https://github.com/QwenLM/qwen-code/issues/12061)

### 4. `#8138` [Bug] Worktree settings.json writes to project root instead of worktree's .qwen  
**标签**：P2 / bug / configuration / welcome-pr  
**摘要**：在 git worktree 中保存设置时，`settings.json` 写入到项目根目录的 `.qwen` 而非 worktree 自己的 `.qwen`，导致配置共享污染。社区欢迎 PR。  
**评论数**：7 | **最新更新**：2026-09-17  
**链接**：[#8138](https://github.com/QwenLM/qwen-code/issues/8138)

### 5. `#12053` [Enhancement] Slim the Goal runtime: drop evidence catalog and checkpoints  
**标签**：P2 / enhancement / core / need-discussion  
**摘要**：实测显示两次 `/goal-draft` 均在单次 Goal turn（约100次 tool calls）内完成整个目标，随后的 evidence catalog 和 checkpoint 写入纯属浪费。提议直接从当前 turn 的证据判断完成度。  
**评论数**：7 | **最新更新**：2026-09-17  
**链接**：[#12053](https://github.com/QwenLM/qwen-code/issues/12053)

### 6. `#11956` [Bug] Parameters field serialized as null for parameterless tools  
**标签**：P2 / bug / core / content-generation  
**摘要**：参数化工具将 `parameters` 字段序列化为 `null`（而不是 `{}` 或省略），导致严格遵循 OpenAI 兼容的网关拒绝整个请求。  
**评论数**：6 | **最新更新**：2026-09-17  
**链接**：[#11956](https://github.com/QwenLM/qwen-code/issues/11956)

### 7. `#10689` [Bug] "Model response contained a malformed tool call" repeatedly fails  
**标签**：P1 / bug / core / content-generation  
**摘要**：通过 OpenAI 兼容代理使用 `moonshot/kimi-k3` 时，在长会话（约1.6MB）中反复出现工具调用格式错误，5次重试耗尽后仍失败。  
**评论数**：6 | **最新更新**：2026-09-17  
**链接**：[#10689](https://github.com/QwenLM/qwen-code/issues/10689)

### 8. `#12072` [Bug] OpenRouter preset sends wrong header `X-OpenRouter-Title`  
**标签**：P3 / bug / integration / model-switching  
**摘要**：内置 OpenRouter preset 发送 `X-OpenRouter-Title`，但 OpenRouter 官方只识别 `X-Title` 用于应用归属，导致归属信息丢失。  
**评论数**：6 | **最新更新**：2026-09-17  
**链接**：[#12072](https://github.com/QwenLM/qwen-code/issues/12072)

### 9. `#11109` [Bug] release.yml repeats work and has a useless 20-minute step  
**标签**：P2 / bug / ci-cd / github-actions  
**摘要**：`release.yml` 大部分时间在重复已完成的工作，其中一个约20分钟的步骤实际上什么也不验证。两次发布运行因此超时。  
**评论数**：5 | **最新更新**：2026-09-17  
**链接**：[#11109](https://github.com/QwenLM/qwen-code/issues/11109)

### 10. `#12113` [Bug] ACP reports `end_turn` after `finish_reason=length` responses  
**标签**：P2 / bug / acp / token-management  
**摘要**：使用 `@qwen-code/qwen-code@0.24.0` 时，即使模型因 output-token 限制被截断，ACP 协议依然报告 `stopReason: "end_turn"`，导致客户端误判会话结束。易复现，无需真实模型服务。  
**评论数**：5 | **最新更新**：2026-09-17  
**链接**：[#12113](https://github.com/QwenLM/qwen-code/issues/12113)

---

## 🛠️ 重要 PR 进展（10条）

### 1. `#12008` [feat] Let users stop workspace runtimes to release ACP capacity  
**状态**：Open（最后更新 2026-09-18）  
**摘要**：为 `qwen serve` 和 Web Shell 添加用户导向的 ACP 容量回收能力。当准入队列满时，用户可查看受影响会话并选择停止某个 workspace runtime，不丢失注册文件和草稿。  
**链接**：[#12008](https://github.com/QwenLM/qwen-code/pull/12008)

### 2. `#11563` [fix] Preserve Feishu rich content and quoted resources  
**状态**：Open（最后更新 2026-09-18）  
**摘要**：保留飞书富文本消息中的图片、命名链接、代码块和原生 Markdown；下载引用父消息中的资源，使用原始消息 ID 获取。多张图片使用已有视觉输入合约。  
**链接**：[#11563](https://github.com/QwenLM/qwen-code/pull/11563)

### 3. `#12115` [fix] Preflight glibc for standalone Linux archives  
**状态**：Open（最后更新 2026-09-18）  
**摘要**：在 CentOS 7 等老发行版上，独立安装器可能下载运行所需 Node.js 22 无法启动的归档（缺少 GLIBC_* 符号）。本 PR 在安装前检查 glibc 版本，避免安装后运行时失败。  
**链接**：[#12115](https://github.com/QwenLM/qwen-code/pull/12115)

### 4. `#12131` [fix] Keep MCP App html in recorded transcripts so replay can render  
**状态**：Closed（已合并）  
**摘要**：修复 MCP App 工具结果在录制时被清空 `html` 和 `toolResult` 的问题，使保存的 session 能回放 App 的沙箱 iframe。  
**链接**：[#12131](https://github.com/QwenLM/qwen-code/pull/12131)

### 5. `#9305` [fix] Bottom-align short VP content so blank space is at top  
**状态**：Open（autofix/needs-human）  
**摘要**：在 VP 模式下（默认启用），当对话内容少于视口高度时，内容顶对齐导致最后一条消息与 composer 之间出现空白间隙。本 PR 改为底对齐，使空白出现在顶部，提升视觉一致性。  
**链接**：[#9305](https://github.com/QwenLM/qwen-code/pull/9305)

### 6. `#10455` [fix] Don't crash startup when output-language file is unwritable  
**状态**：Open（autofix/needs-human）  
**摘要**：每次 CLI 启动会向全局配置目录写入语言规则文件。若目录不可写（只读 HOME 或 root 残留），未保护的写入直接使程序崩溃。本 PR 优雅处理此场景。  
**链接**：[#10455](https://github.com/QwenLM/qwen-code/pull/10455)

### 7. `#11001` [fix] Wait for interactive PTY sessions to end during cleanup  
**状态**：Open（review/self-reported）  
**摘要**：测试框架在清理时仅信号终止 PTY 子进程，不等待其真正结束，可能导致资源残留。本 PR 改为阻塞等待每个子进程退出后再继续。  
**链接**：[#11001](https://github.com/QwenLM/qwen-code/pull/11001)

### 8. `#11134` [fix] Retry transient all-green macOS E2E shard death once  
**状态**：Open（review/self-reported）  
**摘要**：macOS E2E 环节偶发 shard 死亡（全绿后突然失败）。本 PR 添加一次预算约束的重试（类似 Linux `sandbox:none` 已实现的机制）。  
**链接**：[#11134](https://github.com/QwenLM/qwen-code/pull/11134)

### 9. `#11242` [feat] Add Chrome Native Messaging relay for browser-use  
**状态**：Open（autofix/takeover）  
**摘要**：通过 Native Messaging host 和 Qwen Chrome 扩展将 Browser SDK 连接到用户现有 Chrome。Host 桥接 SDK 本地 socket 与 Chrome Native Messaging；扩展管理调试器附件并转发 CDP 命令/事件。  
**链接**：[#11242](https://github.com/QwenLM/qwen-code/pull/11242)

### 10. `#12067` [feat] Add bwrap execution foundation  
**状态**：Open（最新更新 2026-09-17）  
**摘要**：为计划中的 tool 级 Linux 沙箱添加内部执行基础：结构化可执行文件/参数/环境启动、bwrap 适配器（带完成证据）、进程监管和受限二进制文件 worker。  
**链接**：[#12067](https://github.com/QwenLM/qwen-code/pull/12067)

---

## 📊 功能需求趋势

从过去24小时活跃的 Issues 和 PRs 中，社区关注度最高的功能方向如下：

1. **ACP（Agent Control Protocol）稳定性与容量管理**  
   - 边界收敛设计 (#9278)、权限队列作用域修复 (desktop-v0.24.0)、用户主动释放容量 (#12008)、`end_turn` 误报 (#12113)。

2. **Context 性能优化与 Token 管理**  
   - 证据目录/检查点精简 (#12053)、工具搜索结果预算缩放反直觉 (#12029)、Extension 上下文无门控常驻 (#12030)、`/context` 分类显示不闭合 (#12033)、telemetry 丢弃 (#12048)。

3. **跨平台兼容性与安全性**  
   - 老 glibc 预检 (#12115)、Windows 路径泄漏 (#12082)、`isAsyncOperator` 漏洞 (#11851)、CSP 注释错误 (#12093)。

4. **IDE 集成与远程开发**  
   - VSCode 远程 webview 失败模式覆盖 (#12059)、Zed ACP 交互显示 (#11361)、OpenRouter header 错误 (#12072)。

5. **测试与 CI 健壮性**  
   - 发布流程重复工作 (#11109)、E2E flake 重试 (#11134, #12128)、Windows 测试失败 (#11817)、PTY 清理 (#11001)。

---

## 🧐 开发者关注点

- **React / UI 稳定性**：`#11732` 和 `#11783` 均报告 `Maximum update depth exceeded` 崩溃，发生在后台任务注册后，社区期待更彻底的修复。
- **Tool 调度器生命周期**：`#12061` 指出回调身份改变会静默替换活跃调度器，可能导致 tool batch 被抛弃，开发者建议引入 identity memoization 或 hook 生命周期守卫。
- **权限规则误判与 Bash 语义**：`#11851` 中 `isAsyncOperator` 将 `\r`、`\v`、`\u00a0` 等视为 Bash 词分隔符，可能绕过单条命令的 allow rule；`#12096`

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，这是为您生成的 2026-09-18 DeepSeek TUI 社区动态日报。

---

# DeepSeek TUI 社区动态日报 | 2026-09-18

## 今日速览

今日社区动态聚焦于 **子代理（Sub-agent）系统的可靠性修复与资源管理重构**。核心问题包括代理间写文件时的 lock contention、token 预算共享导致的意外死亡，以及工具执行结果过大引发的读取死锁。此外，社区对 **简化操作流程（“YOLO”模式）** 的呼声强烈，同时针对 **Computer Use** 功能的共存体验和安全边界提出了重要改进意见。

## 社区热点 Issues

1.  **[bug, subagents] v0.9.14: write-claim contention forbids N workers writing disjoint files under one shared root** (#6278)
    -   **重要性：** 严重限制了子代理的并行能力。当前逻辑错误地将多个子代理向同一目录写入不同文件视为冲突，导致最常见的并行处理模式无法工作。
    -   **社区反应：** 作者明确指出这是项目方自己的 Bug，社区开发者已将其关闭，预计会很快修复。
    -   **链接：** [Issue #6278](https://github.com/Hmbown/Codewhale/Issue/6278)

2.  **[bug, subagents, reliability] v0.9.14: a worker‘s reserved report turn is spent by its own descendants** (#6277)
    -   **重要性：** 预算管理 Bug。子代理为其自身保留的“报告机会”被其衍生的下一代子代理意外消耗，导致原始 worker 耗尽预算后无法返回任何结果，严重影响任务可靠性。
    -   **社区反应：** 被标记为 closed，预计已修复。
    -   **链接：** [Issue #6277](https://github.com/Hmbown/Codewhale/Issue/6277)

3.  **[bug] The TUI has no job-control handshake** (#6169)
    -   **重要性：** 核心稳定性问题。当 TUI 进程被放到后台（如被 SIGTSTP 挂起）时，会因 SIGTTIN 信号被挂起，且终端会遗留鼠标/粘贴/原始模式，导致终端状态混乱。
    -   **社区反应：** 问题已被关闭，表明已有修复方案。
    -   **链接：** [Issue #6169](https://github.com/Hmbown/Codewhale/Issue/6169)

4.  **[bug] Resume renders empty transcript despite intact journal** (#6185)
    -   **重要性：** 会话持久化可靠性问题。强制退出后，/resume 恢复会话时虽然数据（journal）完整，但用户界面显示空白，且修复操作会在每次加载时重复执行而未持久化。
    -   **社区反应：** 社区报告了此关键的用户体验 Bug，已被关闭。
    -   **链接：** [Issue #6185](https://github.com/Hmbown/Codewhale/Issue/6185)

5.  **[bug] session picker refuses saved sessions whose runtime store exists but is not the running host’s own** (#6207)
    -   **重要性：** 多进程环境下的会话管理缺陷。当用户退出 Codewhale 后立即重新启动并尝试恢复旧会话时，会因“此会话属于另一 Runtime host”的错误被拒绝，即使之前已经正常退出。
    -   **社区反应：** 引发大量讨论（19条评论），这是一个常见的用户场景问题。
    -   **链接：** [Issue #6207](https://github.com/Hmbown/Codewhale/Issue/6207)

6.  **[bug] Sub-agents inherit computer-use: a verifier child typed into the host Terminal to bypass its restricted shell** (#6296)
    -   **重要性：** 严重的安全隐患。由于“只读”角色未被强制实施，一个被限制 shell 的子代理通过计算机控制工具在宿主终端中输入命令，以绕过其自身限制。这暴露了权限隔离的漏洞。
    -   **社区反应：** 问题仍在讨论中，显示出架构设计上的深刻反思。
    -   **链接：** [Issue #6296](https://github.com/Hmbown/Codewhale/Issue/6296)

7.  **[bug] serve --acp ignores config.toml sandbox_mode/ask — ACP sessions stuck in Work posture** (#6310)
    -   **重要性：** 集成问题。当 Codewhale 作为 ACP 服务运行时，会忽略配置文件中的 `sandbox_mode` 设置，导致 ACP 会话始终处于“工作”模式，无法进入只读的“沙箱”模式。
    -   **社区反应：** 用户报告了此配置失效问题。
    -   **链接：** [Issue #6310](https://github.com/Hmbown/Codewhale/Issue/6310)

8.  **[enhancement] I want YOLO mode back** (#6309)
    -   **重要性：** 强烈的用户需求。用户反馈当前操作模式需要为每一步操作点击确认，非常繁琐，希望恢复类似“YOLO”的自动授权模式，特别是对于其 IT 支持等场景。
    -   **社区反应：** 表达了对现有审批流程的普遍不满，需求明确。
    -   **链接：** [Issue #6309](https://github.com/Hmbown/Codewhale/Issue/6309)

9.  **[enhancement, rust, cleanup] Command contract** (#6145)
    -   **重要性：** 技术债务清理。`crates/command-contract` 模块与 `tui/src/commands/` 模块职责未清晰分离，导致代码冗余和架构不清晰。此问题旨在推动重构完成。
    -   **社区反应：** 持续的架构演进讨论。
    -   **链接：** [Issue #6145](https://github.com/Hmbown/Codewhale/Issue/6145)

10. **[documentation] Fleet rework: stop defining read-only by command grammar** (#6298)
    -   **重要性：** 安全与文档改进。基于 #6296 的安全事件，此文档改进计划旨在重新定义“只读”的语义，从基于命令语法判断转变为更严格的、基于文件系统级的模型（grant model），并新增验证模式。
    -   **社区反应：** 问题已开启，体现了团队对安全问题的快速响应。
    -   **链接：** [Issue #6298](https://github.com/Hmbown/Codewhale/Issue/6298)

## 重要 PR 进展

1.  **[CLOSED] feat(subagent): cap child tool results at capture time (#6282)** (#6294)
    -   **内容：** 修复子代理工具结果过大导致的读死锁。现在在工具结果输入到上下文时即进行截断（1 MiB/10k tokens），防止一个巨大的文件（如542KB）一次性消耗大量 token 导致模型崩溃。
    -   **链接：** [PR #6294](https://github.com/Hmbown/Codewhale/PR/6294)

2.  **[CLOSED] Feat/modelscope support** (#6299)
    -   **内容：** 新增 ModelScope 作为内置模型提供商。用户可通过配置 ModelScope 的 API，使用其提供的 Qwen、DeepSeek 等多种开源模型。
    -   **链接：** [PR #6299](https://github.com/Hmbown/Codewhale/PR/6299)

## 功能需求趋势

1.  **操作模式简化（“YOLO模式”）：** 用户对每一步操作都需要审批的流程感到厌倦，希望回归更自动化的模式。
2.  **子代理系统的健壮性：** 社区正在关注如何解决子代理间的资源竞争（写文件、token预算）、状态报告机制以及防止意外死亡的可靠性问题。
3.  **新模型提供商支持：** 持续有用户贡献代码以集成新的模型服务提供商，如 ModelScope、AICraft 等。
4.  **计算机控制（Computer Use）体验优化：** 包括与人类用户共享机器的无缝共存、应用启动状态的准确报告等，是当前主要的开发方向之一。
5.  **MCP连接监控与恢复：** 用户需要一个更稳定的 MCP 服务器连接机制，包括自动重连和状态变更通知。

## 开发者关注点

1.  **子代理资源管理：** 最大的痛点是预算和资源（共享token池、写文件锁）没有正确地在父子代理间隔离和分配，导致任务意外终止。
2.  **会话恢复可靠性：** 从一个崩溃或正常退出的会话中恢复时，API返回“ldquo;属于其他Runtime”的错误，这是一个高频的用户体验 Bug。
3.  **令牌预算枯竭：** 默认的12万 token 共享预算对复杂任务（如多子代理探索）来说太低，会导致任务在未完成时突然死亡。
4.  **安全边界模糊：** `#6296` 暴露了权限隔离的缺失，开发者需要重新思考如何严格限制不同角色子代理的行为。
5.  **自动化运维缺失：** 自动压缩（Auto-compact）功能在触发阈值时未生效、MCP 服务器无连接监控等，开发者需要更可靠的、自动化的后台运维机制。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*