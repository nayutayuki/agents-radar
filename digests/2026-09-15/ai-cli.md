# AI CLI 工具社区动态日报 2026-09-15

> 生成时间: 2026-09-15 00:53 UTC | 覆盖工具: 9 个

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

好的，以下是为您准备的 2026-09-15 AI CLI 工具横向对比分析报告。

---

# AI CLI 开发工具横向对比分析报告 (2026-09-15)

## 1. 生态全景

当前，AI CLI 工具已全面进入 **“Agent 化”与“平台化”的竞速阶段**。各工具不再局限于代码补全或简单问答，而是争相构建能执行复杂任务、调用外部工具、并支持多模型与团队协作的智能体平台。然而，急速的功能迭代也导致了 **“成熟度瓶颈”** 的集中爆发：社区反馈普遍指向 **稳定性不足（崩溃、挂起）、成本控制机制缺失、以及企业级安全与权限管理的粗糙**。与此同时，对 **插件化扩展（Mods/MCP）** 和 **多模型兼容性** 的呼声，已成为所有工具的共识，标志着行业正从单一“模型依赖”向开放“生态构建”转变。

## 2. 各工具活跃度对比

| AI CLI 工具 | 今日版本发布 | 今日活跃 Issues (Top 10) | 今日活跃 PRs (Top 10) | 社区核心关注点 |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 2 | 10 | 5 | 会话计费、Mods 扩展系统、沙箱稳定性 |
| **OpenAI Codex** | 3 (alpha) | 10 | 10 | Windows 桌面端崩溃、沙箱重构、AGENTS.md 模块化 |
| **Gemini CLI** | 1 (nightly) | 10 | 10 | Agent 决策质量、企业级安全加固、A2A 服务器 |
| **GitHub Copilot CLI** | 2 | 10 | 0* | 沙箱策略绕过、会话状态卡死、MCP 协议支持 |
| **Kimi Code CLI** | 0 | 3 | 0 | 多 Agent 并发限制、CJK 输入法 Bug、批注功能 |
| **OpenCode** | 1 | 10 | 10 | UI 布局强制变更、模型可用性故障、SSE 超时 |
| **Pi** | 0 | 10 | 10 | 缓存计费错误、长会话稳定性、会话初始化性能 |
| **Qwen Code** | 2 | 10 | 10 | TUI 崩溃、非千问模型兼容性、权限队列死锁 |
| **DeepSeek TUI (CodeWhale)** | 1 | 10 | 10 | Agent 工作流管理、Token 用量诊断、Fleet 模型管理 |

> *注：活跃 Issues 与 PRs 数量基于今日 Top 10 热点统计，非完整总数。Copilot CLI 今日无更新的活跃 PRs。

## 3. 共同关注的功能方向

以下是在多个工具的社区中反复出现的核心需求：

- **插件化与扩展性 (Mods/MCP/Agent Framework)**
  - **涉及工具**: **Claude Code** (#91870), **OpenAI Codex** (#17401), **Gemini CLI** (#21968), **GitHub Copilot CLI** (#4834), **OpenCode** (#49064), **Pi** (#9591), **Qwen Code** (#11711), **DeepSeek TUI** (#6050)。
  - **具体诉求**: 开发者不再满足于内置功能，强烈需求一套标准的、可编程的插件系统，用于集成自定义工具链、第三方模型和复杂工作流。这体现了从“使用工具”到“构建平台”的演进。

- **成本控制与用量透明**
  - **涉及工具**: **Claude Code** (#38335, #85422), **OpenAI Codex** (#41338), **Gemini CLI** (#21335), **Pi** (#8752, #9210), **OpenCode** (#26602), **DeepSeek TUI** (#6011)。
  - **具体诉求**: 用户付费意愿与成本焦虑并存。社区不仅要求精确的 Token/会话消耗报告，更期待**强制的消费上限断路器**、**按来源（Agent/插件）归因的成本明细**，以及防止因模型异常（如 Opus 5 异常思考）导致账单激增的防护机制。

- **安全与权限管理的精细化**
  - **涉及工具**: **Claude Code** (#86928), **OpenAI Codex** (#33356), **Gemini CLI** (#26525, #22672), **GitHub Copilot CLI** (#4846, #4837), **Qwen Code** (#11887), **DeepSeek TUI** (#6162)。
  - **具体诉求**: 随着 Agent 自主执行能力增强，沙箱逃逸、文件系统权限绕过、`yolo` 模式被滥用等安全问题开始凸显。社区希望获得更严格的沙箱策略、更透明的权限审批日志，以及对破坏性操作（如 `git reset --force`）的主动警告或拦截。

## 4. 差异化定位分析

| 工具名称 | 功能侧重 | 目标用户 | 技术路线 / 特点 |
| :--- | :--- | :--- | :--- |
| **Claude Code** | **团队协作与企业级安全** | 企业团队、安全敏感型开发者 | 强调 Remote Sessions、沙箱化 Bash、精细化的策略控制。Mods 系统是其生态扩展的核心。 |
| **OpenAI Codex** | **底层基础设施建设** | 重度用户、自动化平台开发者 | 持续重构沙箱与 daemon 架构，追求极致的隔离性和可编程性。Agent 能力（A2A）是其长期愿景。 |
| **Gemini CLI** | **Agent 智能化与多模型** | 前沿技术探索者、架构师 | 拥有最丰富的“子代理”和“技能”概念，但在决策质量和可靠性上存在挑战。A2A 服务器是其企业级卖点。 |
| **GitHub Copilot CLI** | **无缝集成 GitHub 生态** | GitHub 重度用户、企业 | 与 GitHub 策略、插件、Actions 深度绑定，强调企业级管理和组织级部署，但独立模型支持较弱。 |
| **Kimi Code CLI** | **亚洲市场与协作场景** | 中国开发者、团队协作 | 专注 Kimi Work 的协作审阅流程，对中国用户（如 CJK 输入）体验优化更敏感，但社区规模和活跃度目前最小。 |
| **OpenCode** | **社区驱动与极致可定制** | 极客、个人开发者 | 拥有高度活跃的社区和丰富的社区插件（如 Dashscope 图像生成），UI 设计（经典 vs 新版）是社区讨论焦点。 |
| **Pi** | **透明与精准的计费模型** | 成本敏感型、高级用户 | 对计费逻辑（如缓存写入）的细节暴露最多，社区反馈集中在成本计算准确性上，与 Provider 兼容性调试是其强项。 |
| **Qwen Code** | **多模型网关与本地化** | 中国开发者、模型切换者 | 强调对非千问模型（如 ZHIPU, DeepSeek）的兼容性，并有独立网关组件。在 IDE 集成和 Windows 兼容性上有较多问题。 |
| **DeepSeek TUI** | **创新性交互与多代理管理** | 体验驱动型、Agent 应用开发者 | 拥有最具特色的“宠物”功能和 Fleek（子代理管理）系统，UI 和交互设计大胆，但项目刚刚更名，稳定性和文档待加强。 |

## 5. 社区热度与成熟度

- **高热+高成熟度（社区庞大，讨论深入，问题专业）**: **Claude Code** 和 **OpenAI Codex** 代表了第一梯队。其 Issue 讨论动辄数百条，反馈的问题（如计费、沙箱）直接触及核心商业与技术瓶颈。频繁的版本发布（Claude Code 每日小版本，OpenAI Codex 多个 alpha）体现其迭代速度。

- **高热+快速迭代（社区活跃，但常有颠覆性变更）**: **OpenCode** 和 **DeepSeek TUI (CodeWhale)** 属于第二梯队。社区非常活跃，对新功能（如 UI、宠物、插件）反馈积极，但也更容易因激进的设计变更（如强制新UI）引发争议，处于快速探索与验证阶段。

- **

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，作为一名专注于 Claude Code 生态的技术分析师，以下是基于 `anthropics/skills` 仓库数据（截止 2026-09-15）的社区热点报告。

---

### Claude Code Skills 社区热点报告 (2026-09-15)

#### 1. 热门 Skills 排行 (Top 5-8)

以下列出社区关注度最高的 Skills 相关 Pull Requests，涵盖功能、讨论焦点及当前状态。

1.  **`fix(skill-creator): isolate trigger evals and handle Windows and runtime failures` (PR #1298)**
    *   **功能**: 修复 `skill-creator` 核心工具的触发器评估问题，解决 Windows 兼容性、运行时失败导致的误报问题。
    *   **社区热点**: 讨论集中在 **Skill 开发的可靠性** 和 **跨平台兼容性**，尤其是评估引擎的稳定性直接影响开发者体验。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #1298](https://github.com/anthropics/skills/pull/1298)

2.  **`fix(mcp-builder): support mcp>=2 streamable_http_client import and custom headers` (PR #1742)**
    *   **功能**: 修复 `mcp-builder` 对 MCP 最新版本的兼容性，支持新的客户端导入方式和自定义 HTTP 头。
    *   **社区热点**: 反映了社区对 **MCP 生态依赖的更新** 非常敏感，开发者希望 Skill 工具链能紧跟上游 MCP 协议的演进。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #1742](https://github.com/anthropics/skills/pull/1742)

3.  **`Add md2video-audio skill` (PR #1703)**
    *   **功能**: 新增一个“零成本”Skill，可将 Markdown 文档转换为带语音合成的专业 MP4 视频。
    *   **社区热点**: 显示出社区对 **“文档到多媒体”** 的创作自动化有强烈兴趣，旨在拓宽 Claude Code 的输出形式。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #1703](https://github.com/anthropics/skills/pull/1703)

4.  **`Add pyxel skill for retro game development` (PR #525)**
    *   **功能**: 集成 Pyxel 引擎，允许 Claude Code 直接进行复古（像素/8-bit）游戏的开发与迭代。
    *   **社区热点**: 展现了游戏开发者社区的参与度，讨论聚焦在 **将 AI 代理与特定创意引擎结合** 的可行性。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #525](https://github.com/anthropics/skills/pull/525)

5.  **`Add Hivemind: Zero-Cost Multi-Agent Orchestration Skill` (PR #1628)**
    *   **功能**: 引入“蜂群”模式，让 Claude Code 作为规划者，将机械任务委托给免费模型工作节点，以节约昂贵模型上下文。
    *   **社区热点**: 引发了关于 **多代理协作模式** 和 **成本优化策略** 的讨论，是社区探索高级 AI 工作流的一个标志。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #1628](https://github.com/anthropics/skills/pull/1628)

6.  **`feat: add buffer-api Agent Skill` (PR #1627)**
    *   **功能**: 新增一个通用的 Buffer (社交媒体管理平台) GraphQL API 的 Agent Skill，用于自动化发布和内容排期。
    *   **社区热点**: 代表了社区对 **外部业务 SaaS 集成** 的旺盛需求，希望将 Claude Code 作为统一的营销工具操作界面。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #1627](https://github.com/anthropics/skills/pull/1627)

7.  **`Add document-typography skill` (PR #514)**
    *   **功能**: 一个专门的`排版质量控制器`，防止 AI 生成文档中的孤词、寡行和编号错位等典型问题。
    *   **社区热点**: 讨论焦点在于 **AI 生成内容的细粒度质量控制**，特别是对专业文档的“最后一公里”打磨，体现了对产出质量的高要求。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #514](https://github.com/anthropics/skills/pull/514)

8.  **`Add scnet-hpc skill` (PR #1615)**
    *   **功能**: 用于操作 SCNet 高性能计算集群的 Skill，支持通过 SSH 和 Slurm 工作负载管理器进行任务调度。
    *   **社区热点**: 表明 **科研和算力密集型领域** 的开发者正在积极将 Claude Code 引入其复杂的工作流中。
    *   **状态**: 🟡 **Open**
    *   **链接**: [PR #1615](https://github.com/anthropics/skills/pull/1615)

---

#### 2. 社区需求趋势 (从 Issues 中提炼)

从社区 Issues 的讨论中，可以提炼出以下三大需求趋势：

1.  **安全与信任体系（Token of Trust）**: 核心诉求 Issue #492 (43条评论)。社区强烈关注 `anthropic/` 命名空间下混入社区技能的**信任边界滥用**问题。用户担忧误以为官方技能而授权，引发安全风险。这要求官方建立更清晰的认证、审核或签名机制。

2.  **组织级协作与管理**: Issue #228 (8个👍) 和 Issue #189 (9个👍) 是典型代表。企业和团队用户越来越不满足于个人下载、手动分享 `.skill` 文件的低效模式。他们迫切需要**组织内技能库、共享链接或目录服务**等协作功能。

3.  **开发工具链的可靠性与基线兼容性**: 多个高热度 Issues 指向了开发者和集成者的“工具链阵痛”。例如：
    *   评估工具失效 (Issue #556)
    *   技能体积膨胀消耗上下文 (Issue #1487)
    *   特定平台脚本失败 (Issue #1362)
    *   **核心诉求**: 社区需要一套**更稳定、文档更清晰、默认行为更合理**的开箱即用工具链，降低技能开发和集成的门槛。

---

#### 3. 高潜力待合并 Skills

以下 PR 讨论活跃、功能重要，且尚未合并，很可能在近期落地：

1.  **`md2video-audio` (PR #1703)**: 将文档直接转化为视频是一个非常有吸引力的功能，潜在用户面广，预计会快速推进。
2.  **`Hivemind` (PR #1628)**: 开创性的多代理成本优化方案，代表了行业前沿探索，可能成为高级用户的标准配置。
3.  **`buffer-api` (PR #1627)**: 作为标准化 SaaS 集成的代表，其模式和代码可能为未来官方提供“API 集成模板”铺平道路。
4.  **`Detect orphaned docx comments` (PR #1734)**: 虽然可能是一个相对小的修复，但它精准地解决了文档处理中的一个**烦人的痛点**，社区响应可能会很好。

---

#### 4. Skills 生态洞察

一句话总结当前社区的诉求：

**社区在 Skills 层面的核心诉求已从“如何创造新功能”，转向了“如何构建一个可信任、可协作且稳定可靠的生态基础设施”，以确保已有和未来的 Skills 能够安全、高效地在团队和个人工作中落地。**

---

好的，以下是 2026 年 9 月 15 日的 Claude Code 社区动态日报。

---

# Claude Code 社区动态日报 | 2026-09-15

## 今日速览

Claude Code 今日发布两个小版本更新，主要修复稳定性问题，并为 Remote Sessions 带来了“快速模式”和对 `/config` 面板的鼠标支持。社区方面，关于付费用户会话配额消耗异常的问题（Issue #38335）持续引发热议，已成为社区头号焦点，累计获得近 500 个点赞和 850+ 条评论。此外，社区对通过“Mods”系统实现更深度扩展的呼声极高，相关提案 (#91870) 已收到 170+ 条讨论，开发者承诺将在数周内交付相关功能。

---

## 版本发布

### v2.1.272
- **更新内容**：Bug 修复和可靠性提升。
- **链接**：[v2.1.272 Release](https://github.com/anthropics/claude-code/releases/tag/v2.1.272)

### v2.1.271
- **更新内容**：
    - **远程会话 (Remote Sessions) 快速模式**：为云端和自托管运行器中的 Remote Sessions 新增了“快速模式”。主机可设置快速模式，或与会话内输入 `/fast` 启用（需组织允许）。
    - **全屏模式鼠标支持**：`/config` 面板在全屏模式下支持鼠标滚轮滚动设置。
- **链接**：[v2.1.271 Release](https://github.com/anthropics/claude-code/releases/tag/v2.1.271)

---

## 社区热点 Issues

1.  **[[BUG] Claude Max 套餐 Session 限额异常快速消耗 (CLI 使用)](https://github.com/anthropics/claude-code/issues/38335)**
    - **为什么重要**：最受关注的 Issue，直接影响付费用户的成本和可用性。尽管已创建半年，社区对 Session 消耗计数器的准确性及 Anthropic 的响应速度表达了强烈不满。
    - **社区反应**：851 条评论，476 个赞。用户普遍反映问题未解决，并分享了大量的排查数据。

2.  **[[增强] Mods - 让 Claude 扩展性提升 10 倍](https://github.com/anthropics/claude-code/issues/91870)**
    - **为什么重要**：这是一项关于插件系统的重大提案，承诺将彻底改变 Claude Code 的扩展方式。开发者社区对此寄予厚望，认为这将是解锁自定义工作流的关键。
    - **社区反应**：173 条评论，105 个赞。项目维护者已确认并承诺在数周内发布功能钩子（function hooks），社区反应积极正面。

3.  **[[BUG] Windows: Windows 更新后所有 Plan9 共享失败](https://github.com/anthropics/claude-code/issues/92984)**
    - **为什么重要**：影响 Windows 用户的“协同工作”（Cowork）功能。安装特定 KB 更新后，Plan9 挂载失败，导致远程文件操作无法进行，已确认卸载更新可临时解决。
    - **社区反应**：113 条评论，58 个赞。用户提供了清晰的重现步骤和临时解决方案，等待官方修复。

4.  **[[BUG] VS Code 扩展中第一条用户消息固定在聊天面板顶部](https://github.com/anthropics/claude-code/issues/36146)**
    - **为什么重要**：一个长期存在的 UI 问题，严重影响 VS Code 用户的聊天体验，导致屏幕空间被占用。
    - **社区反应**：29 条评论，43 个赞。该问题自三月起存在，至今未修复，用户再次表达不满。

5.  **[[BUG] Linux: 沙盒化 Bash 间歇性失败](https://github.com/anthropics/claude-code/issues/86928)**
    - **为什么重要**：影响 Linux 用户的安全沙盒功能，约 1/10 的调用会因 `unshare(CLONE_NEWUSER)` 错误失败，导致任务中断。
    - **社区反应**：16 条评论，8 个赞。已提供详细日志和重现方法，目前为 Open 状态。

6.  **[[功能请求] 运行时 Token 消耗断路器](https://github.com/anthropics/claude-code/issues/85422)**
    - **为什么重要**：社区对 AI 使用成本控制的需求日益迫切。这项提案要求实现一个强制的、按来源（hook/plugin/subagent）归因的消费上限机制，而不仅仅是警告。
    - **社区反应**：15 条评论。虽然热度一般，但代表了高频、高成本用户的真实痛点。

7.  **[[BUG] Windows: 斜杠命令选择器打开逻辑异常](https://github.com/anthropics/claude-code/issues/89398)**
    - **为什么重要**：一个典型的 UI/UX 不一致问题。`/` 命令只有在输入框最开头才能触发选择器，但命令在其他位置也能执行，导致用户困惑。
    - **社区反应**：12 条评论，6 个赞。用户清晰报告了环境细节和问题表现。

8.  **[[BUG] Opus 5 模型在 xhigh 下出现异常思考行为](https://github.com/anthropics/claude-code/issues/93596)**
    - **为什么重要**：用户报告 Opus 5 模型在未更改设置的情况下突然对几乎所有请求产生思考块，且输出 Token 量激增 2-7 倍。这直接影响成本和响应速度。
    - **社区反应**：3 条评论。虽评论不多，但该问题可能导致严重的用户账单问题，需要官方紧急排查。

9.  **[[BUG] Windows 桌面版: 每个新的 PowerShell 调用等待约 154 秒](https://github.com/anthropics/claude-code/issues/94344)**
    - **为什么重要**：一个令人沮丧的性能问题，一旦使用 PowerShell，每次新调用都有超过 2 分钟的延迟，而 Bash 调用则无此问题。
    - **社区反应**：2 条评论。用户确认此问题在 v2.1.270 中依然存在，指向一个长期未解决的 Bug。

10. **[[BUG] 分支/恢复的 Session 导致 MCP 服务器泄漏](https://github.com/anthropics/claude-code/issues/83771)**
    - **为什么重要**：长期使用后性能下降的根源被定位。分支或恢复的会话会产生大量僵尸 MCP 服务器进程，导致内存和 CPU 资源泄漏，影响 `tsc` 和 Shell 等命令的执行。
    - **社区反应**：1 条评论。虽然讨论不多，但问题本身具有隐蔽性和破坏性，对重度用户影响巨大。

---

## 重要 PR 进展

1.  **[Create pylint.yml](https://github.com/anthropics/claude-code/pull/83890)**
    - **内容**：新增 pylint CI 工作流，旨在提升代码质量。

2.  **[mods/diff: 固定头部、仅滚动主体的全屏 Diff 视图](https://github.com/anthropics/claude-code/pull/94184)**
    - **内容**：为 Mods 系统的 Diff 视图贡献了更接近原生的交互逻辑：停靠面板现在匹配内置 `/diff` 的固定头部、文件列表和精确滚轮翻页行为。这是 Mods 系统 UI 体验的重要提升。

3.  **[docs(sandbox): 注明提示批准的域名是会话范围的](https://github.com/anthropics/claude-code/pull/71627)**
    - **内容**：更新了沙盒模式的文档，明确解释了用户在提示中批准的域名仅在当前会话有效，重新启动后需要再次批准。这对安全配置非常重要。

4.  **[mods: 将 Diff、Sec-default 和 Telemetry 测试移至 Mods 目录下](https://github.com/anthropics/claude-code/pull/93951)**
    - **内容**：将三个 Mods 的行为测试文件移至各自 Mods 的 `tests/` 目录下，实现了代码组织的清晰划分，并使用 `claude plugin test` 运行，增强了 Mods 的独立可测试性。

5.  **[fix(security-guidance): 使 `**` 通配符匹配零深度路径](https://github.com/anthropics/claude-code/pull/87079)**
    - **内容**：修复了一个安全相关的 bug。之前 `security-patterns.json` 中的 `**` 通配符无法匹配顶级文件，会导致安全规则失效。此 PR 修正了 glob 匹配逻辑，确保安全规则能覆盖所有层级的文件。

---

## 功能需求趋势

1.  **插件化与扩展性（Mods 系统）**：**#91870** 是社区最关注的增强功能，体现了开发者对自定义工作流的强烈渴望。这不仅仅是添加功能，而是要求平台具备可编程的、模块化的扩展能力。

2.  **成本控制机制**：**#85422** 提出的“Token 消耗断路器”是核心需求。用户不再满足于消费报告，而是希望拥有强制性的、基于使用量的预算控制，以防止意外高额账单，尤其是在使用子代理和复杂插件时。

3.  **只读/讨论模式**：**#91301** 和 **#85848** 都提到了“讨论模式”。这表明用户的需求已经从“让 AI 帮我写代码”扩展到“让 AI 帮我理解和分析代码”，需要一个不产生任何副作用、仅供阅读和对话的安全模式。

4.  **子代理的精细化控制**：**#77298** 请求为子代理添加 `effort` 参数，以便更精细地控制单个子任务的推理成本和深度。这表明用户希望更灵活地分配 AI 资源。

5.  **MCP 生态完善**：**#93175** 请求 MCP 工具渲染 API 的折叠状态控制能力。随着 MCP 服务器数量增多，用户对如何高效展示和管理这些工具的输出有了更高要求。

---

## 开发者关注点

1.  **Session/配额计费问题依然是首要痛点**：大量评论集中在 **#38335** 上，表明用户对付费 session 的消耗机制感到困惑和不满，这对用户信任度有极大影响。

2.  **Windows 平台兼容性问题集中爆发**：近期有多个 Windows 专属 Bug 被报告（**#92984, #94344, #93479**），涉及 Cowork、PowerShell 延迟等核心功能，严重影响了 Windows 用户的开发体验。

3.  **Session 状态的泄漏与污染**：多个 Bug（**#83771, #93482, #86198**）指向一个共同问题：Session 状态管理不善，导致资源泄漏、数据错乱或逻辑冲突，这通常是系统架构设计中需要警惕的信号。

4.  **模型行为的不可预测性**：**#93596** 报告的 Opus 5 异常输出行为引发担忧。开发者认为模型的行为应当稳定且可预期，任何无端的成本增加或行为变化都会严重破坏信任。

5.  **安全与权限控制的细节问题**：对沙盒、安全通配符、权限模型的改进提议（**#87079, #71627, #90004**）表明，用户在将 AI 集成到开发流程时，对其安全边界和正确性有非常严肃的考量。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报 — 2026-09-15

## 今日速览
- **Windows 桌面端问题集中爆发**：多个严重 Bug 被确认，包括截图功能完全失败、后续消息无法发送以及分页线程永久冻结，社区讨论激烈。
- **沙箱安全与注册机制重构**：团队提交了系列 PR，将 Windows 沙箱的守护进程管理、包注册和 Unix 套接字权限统一抽象，并开始支持注册包执行。
- **Alpha 版本密集迭代**：过去 24 小时内连续发布 3 个 Rust 0.155.0-alpha 版本，聚焦沙箱与 daemon 模块的底层重构。

---

## 版本发布
- **[rust-v0.155.0-alpha.5](https://github.com/openai/codex/releases/tag/rust-v0.155.0-alpha.5)** / **[alpha.4](https://github.com/openai/codex/releases/tag/rust-v0.155.0-alpha.4)** / **[alpha.2.4](https://github.com/openai/codex/releases/tag/rust-v0.155.0-alpha.2.4)**  
  Rust 核心组件连续发布三个小版本，均为 alpha 阶段，未附带详细变更说明。推测为今日大量 PR 合并后的打包产物，重点关注 Windows 沙箱注册与 daemon 分离的逻辑。

---

## 社区热点 Issues（10 条）

### 1. #25178 Windows Computer Use 截图功能彻底失败
**评论：59 | 👍：25**  
在 Windows 10 22H2 上，任何调用截图的操作均因 `SetIsBorderRequired` 接口不支持而失败。虽然列表窗口、激活窗口等均可正常使用，但截图这一核心能力缺失严重影响自动化流程。  
[查看详情](https://github.com/openai/codex/issues/25178)

### 2. #41566 分页滚动导致重复序号，永久冻结线程历史
**评论：32 | 👍：0**  
当分页 rollout 过程中遇到未完成的 turn，生成的 ordinal 可能出现重复，随后线程历史再也无法向前滚动。该问题已影响多位长期重度用户。  
[查看详情](https://github.com/openai/codex/issues/41566)

### 3. #44102 Windows Desktop 更新后无法发送后续消息
**评论：21 | 👍：1**  
版本 26.903.61454 下，完成第一次完整 turn 后，输入栏的后续消息无法提交。用户需重启应用才能继续对话，严重影响连续性。  
[查看详情](https://github.com/openai/codex/issues/44102)

### 4. #33356 Windows 沙箱 exec 每次调用泄漏 3-5 个 lsass 句柄
**评论：13 | 👍：1**  
`codex-cli 0.144.4` 中，sandboxed exec 每执行一次命令就会泄漏 lsass 进程句柄，长期运行后导致整个操作系统卡顿。已是第二次报告该问题，团队尚未修复。  
[查看详情](https://github.com/openai/codex/issues/33356)

### 5. #45119 macOS 14.2 沙箱启动因 `TIOCSTI` 未定义而失败
**评论：12 | 👍：0**  
最新桌面版（26.908.40834）在 macOS 14.2 上无法启动沙箱，终端报“unbound variable TIOCSTI”。经检查上游 main 分支亦存在相同问题。  
[查看详情](https://github.com/openai/codex/issues/45119)

### 6. #17401 社区强烈需求：为 AGENTS.md 增加 `@include` 指令
**评论：12 | 👍：21**  
要求实现 `@path/to/file.md` 语法，让 CLI 在组装指令时自动内联引用文件，从而实现模块化、可维护的上下文配置。该 issue 获 👍 数最高，是社区长期呼声。  
[查看详情](https://github.com/openai/codex/issues/17401)

### 7. #41338 内联图片输出 4.2MB 但对 Token 消耗仅 ~230，导致线程膨胀
**评论：10 | 👍：0**  
工具调用返回的 base64 图片体积巨大（4.2 MB），但基于 token 的上下文管理机制无法感知该 payload，最终线程因实际层乱码而卡死。  
[查看详情](https://github.com/openai/codex/issues/41338)

### 8. #30271 合法逆向工程被误判为“网络滥用”
**评论：10 | 👍：4**  
用户已通过 OpenAI 的网络安全验证，但合理使用逆向工程分析自有硬件时仍被触发政策限制。类似误报导致任务中断，社区呼吁改进 false positive 检测。  
[查看详情](https://github.com/openai/codex/issues/30271)

### 9. #41014 macOS 更新后 MCP 覆盖导致本地守护进程不可达
**评论：4 | 👍：4**  
环境变量 `CODEX_APP_SERVER_USE_LOCAL_DAEMON=1` 被忽略，Desktop 启动私有 stdio app-server 替代已存在的本地守护进程，导致自定义 MCP 服务无法连接。  
[查看详情](https://github.com/openai/codex/issues/41014)

### 10. #36473 GitHub 插件应显示组织安装链接
**评论：6 | 👍：4**  
当前插件成功连接后，菜单中不提供 GitHub App 的组织级安装入口，导致私有仓库和组织项目无法使用。用户需要手动寻找安装流程。  
[查看详情](https://github.com/openai/codex/issues/36473)

---

## 重要 PR 进展（10 条）

### 1. #45559 恢复 Windows 沙箱注册刷新（服务重启后）
服务重启导致已注册的沙箱账户运行时中断，该 PR 确保注册刷新机制能在服务重启后自动继续。  
[查看详情](https://github.com/openai/codex/pull/45559)

### 2. #45558 从完整 CLI 包中“播种”缺失的守护进程安装
之前 daemon 只能通过独立安装程序部署，此 PR 允许直接从完整的 CLI 包中提取并安装 daemon 二进制文件，减少安装步骤。  
[查看详情](https://github.com/openai/codex/pull/45558)

### 3. #45556 新增附件上传/解析 API
将原来的 `AttachmentStore::persist` 拆分为 `upload` 和 `resolve`，支持返回内联字节或文件 ID，并提供了可选的元数据与下载 URL。  
[查看详情](https://github.com/openai/codex/pull/45556)

### 4. #45550 Windows 沙箱支持注册包执行（opt-in）
通过环境变量 `CODEX_WINDOWS_REGISTERED_CORE=1` 启用，沙箱内可执行经过服务注册的运行时，支持所有权验证和资源沙箱化。  
[查看详情](https://github.com/openai/codex/pull/45550)

### 5. #45549 保留 turn 终止时的流式答案与计划
此前中断或失败的 turn 会丢弃已流式的答案和计划内容，导致数学推理等场景丢失关键信息。现在在 turn 结束时刷新并合并流。  
[查看详情](https://github.com/openai/codex/pull/45549)

### 6. #45548 使 Seatbelt 遵守预设的 Unix Socket 权限
修复了 `ManagedNetworkSandboxContext` 中忽视 `allow_unix_sockets` 和 `dangerously_allow_all_unix_sockets` 的问题，确保沙箱正确继承预设权限。  
[查看详情](https://github.com/openai/codex/pull/45548)

### 7. #45546 将 daemon 包从独立 CLI 安装中分离
daemon 更新不再与 CLI 版本耦合，支持独立发布与部署，用户可单独管理 daemon 版本而不影响 CLI 环境。  
[查看详情](https://github.com/openai/codex/pull/45546)

### 8. #45544 禁止记录完整图像生成结果
更新图像生成工具指南，避免用 `text()` 或 `notify()` 打印完整的 base64 图像数据或全量结果，仅输出必要元数据。  
[查看详情](https://github.com/openai/codex/pull/45544)

### 9. #45543 重构图像内容为共享 `ImageReference` 类型
将 `ContentItem` 和 `FunctionCallOutputContentItem` 中的图像表示统一为 `ImageReference::Inline`，同时保持原有 `image_url` 有线格式不变。  
[查看详情](https://github.com/openai/codex/pull/45543)

### 10. #45542 为 Windows 沙箱账户添加服务管理的包注册
新增 `registered_core` 预配模式，允许服务记录应用包及其运行别名，并对调用方进行包族认证，强化沙箱安全边界。  
[查看详情](https://github.com/openai/codex/pull/45542)

---

## 功能需求趋势
从过去 24 小时更新的 Issues 中，可提炼出社区最关注的方向：

- **Windows 桌面稳定性**：截图、消息发送、滚动行为、分页线程——多项基础功能出现回归或 Bug，用户要求紧急修复。
- **沙箱安全与资源管理**：句柄泄漏、权限继承、进程隔离、守护进程分离等底层问题正在被动回应，但用户仍希望更透明的沙箱配置。
- **上下文管理增强**：`AGENTS.md` 的模块化（`@include`）、大图片 payload 处理（非 token 维度的资源限制）成为高频讨论点。
- **速率限制与计费透明**：用户希望看到实时的 token 燃烧速率（如#45427 的“速度表”），并期望当前 turn 不应因额度耗尽而强制中断（#45444）。
- **GitHub 集成改进**：组织级安装、权限持久化（不重复弹出确认）是插件场景的核心诉求。
- **虚假政策标记**：逆向工程、安全分析等合法工作被误判，影响开发者信任。

---

## 开发者关注点
- **Windows 用户成为最大受害者**：上述 10 个热点中 7 个涉及 Windows，尤其是 Windows 10/11 上的基础操作（截图、发送消息、滚动）均存在问题，表明近期 Windows 桌面版回归严重。
- **沙箱性能泄漏累积**：`lsass` 句柄泄漏在 #33356 中已有多次反馈却未修复，导致长时间使用后必须重启系统，开发者对此容忍度很低。
- **配置管理混乱**：多个 issue 指向环境变量（如 `CODEX_APP_SERVER_USE_LOCAL_DAEMON`）被忽略，MCP 重写配置时丢失注释和未知字段（#45432），开发者抱怨“配置不可靠”。
- **分页与线程恢复脆弱**：#41566 和 #41512 均指向分页线程在恢复时出问题，且无自动恢复机制，导致数据永久丢失。
- **安全过滤器误报恶化**：gpt-6-astra 模型在无害的 Bug 分类任务中频繁触发 `cyber_policy` 限制（#45553），严重干扰开发者工作流。

> 数据截止时间：2026-09-15 23:59 UTC+8 | 统计口径：GitHub openai/codex 仓库公开 Issue 与 PR

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

# 🚀 Gemini CLI 社区动态日报 | 2026-09-15

## 📌 今日速览
过去 24 小时内，Gemini CLI 发布了 **v0.61.0-nightly** 版本升级；社区讨论热度集中在 **Agent 决策质量**（子代理误报成功、通用代理挂起）与 **企业级安全加固**（策略目录权限审查、A2A 服务器日志泄露防护）两大方向。另有多项针对 `sandbox` 递归崩溃、`.gitignore` 嵌套模式等核心修复的 PR 正在合并中。

---

## 📦 版本发布
### v0.61.0-nightly.20260914.g9c1b0a610
- **发布时间**：2026-09-14  
- **变更记录**：基于前一夜版的增量更新，主要包含 bug 修复与基础设施调整。  
  [完整变更日志](https://github.com/google-gemini/gemini-cli/compare/v0.61.0-nightly.20260913.g9c1b0a610...v0.61.0-nightly.20260914.g9c1b0a610)

---

## 🔥 社区热点 Issues（Top 10）

### 1. **#22323 – 子代理因 `MAX_TURNS` 中断却误报 “GOAL” 成功**
   - **标签**：P1 / bug / agent  
   - **核心问题**：`codebase_investigator` 子代理在达到最大轮次后报告 `success` 与 `GOAL`，实际并未完成任何分析，导致主流程被静默掩盖。  
   - **社区反应**：13 条讨论，用户关注此类“假成功”严重影响自动化任务的可信度。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/22323)

### 2. **#21409 – 通用代理挂起“无限等待”**
   - **标签**：P1 / bug / agent  
   - **核心问题**：当主任务委托给通用子代理时，CLI 永久挂起（已测试长达 1 小时）。用户反馈通过明确禁止“使用子代理”可临时绕过。  
   - **社区反应**：8 条讨论，8 个 👍，说明该问题高频且影响面大。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/21409)

### 3. **#19873 – 利用模型对 Bash 的亲和性实现零依赖 OS 沙箱**
   - **标签**：P2 / enhancement / agent  
   - **核心问题**：提议利用 Gemini 3 模型的原生 POSIX 工具链能力，结合无第三方依赖的沙箱执行策略，在安全前提下最大化模型操作效率。  
   - **社区反应**：9 条讨论，1 个 👍，属于长线功能探索。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/19873)

### 4. **#25166 – Shell 命令执行后在终端显示“Awaiting input”并卡死**
   - **标签**：P1 / bug / core  
   - **核心问题**：简单 CLI 命令（如 `ls`）执行完毕后，终端仍显示“Waiting input”，实际进程已结束。用户需手动中断。  
   - **社区反应**：4 条讨论，3 个 👍，与交互体验直接相关。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/25166)

### 5. **#21968 – Gemini 不使用自定义技能和子代理**
   - **标签**：P2 / bug / agent  
   - **核心问题**：用户创建了 gradle、git 等自定义技能，但 Gemini 在相关场景中几乎从不主动调用，必须显式指示。  
   - **社区反应**：6 条讨论，0 个 👍（但多人共鸣）。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/21968)

### 6. **#26525 – 自动内存功能存在确定性脱敏缺失与过度日志**
   - **标签**：P2 / bug / security  
   - **核心问题**：Auto Memory 在提取本地会话时，脱敏指令作用于模型上下文之后，且可能记录未清理的凭证。  
   - **社区反应**：5 条讨论，安全团队要求紧急修复。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/26525)

### 7. **#22232 – 增强浏览器代理弹性：自动会话接管与锁恢复**
   - **标签**：P3 / feature / agent  
   - **核心问题**：浏览器使用 `sessionMode: 'persistent'` 时，若旧进程残留，代理直接失败而非尝试接管或清理。  
   - **社区反应**：4 条讨论，涉及自动化测试场景。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/22232)

### 8. **#22672 – 代理应劝阻/阻止破坏性行为**
   - **标签**：P2 / agent  
   - **核心问题**：模型在 git 操作、数据库维护等场景下可能使用 `git reset --force` 等危险命令，缺少安全提醒机制。  
   - **社区反应**：3 条讨论，用户期望引入“安全确认”步骤。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/22672)

### 9. **#20079 – 符号链接文件不被识别为子代理**
   - **标签**：P2 / bug / agent  
   - **核心问题**：`~/.gemini/agents/` 下若放置符号链接（symlink），CLI 不会将其视为有效代理。用户期待支持链接以方便管理。  
   - **社区反应**：4 条讨论，属于低优先级但影响工作流配置。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/20079)

### 10. **#21335 – `/compress` 命令在会话恢复后不持久**
   - **标签**：P2 / bug / agent  
   - **核心问题**：`/compress` 在内存中替换聊天摘要，但未写回会话文件，导致恢复后原始长历史重新加载。  
   - **社区反应**：2 条讨论，2 个 👍，对 token 开销敏感的用户尤为困扰。  
   [查看详情](https://github.com/google-gemini/gemini-cli/issues/21335)

---

## 🔧 重要 PR 进展（Top 10）

### 1. **#29336 – 加固非系统策略目录权限检查**
   - **标签**：P2 / enterprise / size: L  
   - **内容**：将 `isDirectorySecure` 验证扩展到用户目录与工作区目录，并支持 POSIX/Windows 下的当前用户所有权检测。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29336)

### 2. **#29333 – 校验通过约定找到的策略目录权限**
   - **标签**：P2 / enterprise / size: M  
   - **内容**：修复 `filterSecurePolicyDirectories` 只检查系统目录的问题，确保用户/工作区目录的权限也被审计。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29333)

### 3. **#29328 – A2A 服务器：尊重 LOG_LEVEL 且不记录凭证**
   - **标签**：P1 / security / size: L  
   - **内容**：修复日志级别硬编码为 `info` 的问题，同时过滤可能出现在日志中的敏感凭据。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29328)

### 4. **#29335 – 修复 AgentLoopContext 属性在对象展开后丢失**
   - **标签**：P1 / core / size: M  
   - **内容**：`Config` 类中若干属性原为原型 getter，展开后丢失；改为普通实例属性以保证上下文完整传递。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29335)

### 5. **#29332 – 限制单次调用对 sandbox 展开的频率**
   - **标签**：P2 / core / size: M  
   - **内容**：防止始终返回 `sandbox_expansion_required` 的工具导致 `_execute` 无限递归引发堆溢出崩溃。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29332)

### 6. **#29329 – CLI：截断后暂停 stdin，并提示输入已终止**
   - **标签**：P2 / core / size: S  
   - **内容**：使用 `process.stdin.destroy()` 后无法恢复，改为 pause 并在放弃时输出清晰提示。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29329)

### 7. **#29330 – CLI：保持用户输入在日志响应前不被读取两次**
   - **标签**：P2 / core / size: M  
   - **内容**：修复 React 严格模式下 `setPastSessionMessages` 内调用 `setCurrentSessionMessages` 导致的输入重复消费问题。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29330)

### 8. **#29327 – 修复 SDK 代理 Shell 中 env 与 timeoutSeconds 被忽略**
   - **标签**：P2 / agent / size: M  
   - **内容**：`SdkAgentShell.exec` 接收的 `AgentShellOptions` 中 `env` 和 `timeoutSeconds` 此前未被真正应用，现修正。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29327)

### 9. **#29323 – 修复嵌套 .gitignore 中尾部斜杠模式匹配错误**
   - **标签**：P2 / core / size: L  
   - **内容**：对 `build/`、`node_modules/` 等模式，在嵌套 `.gitignore` 中错误锚定到文件所在目录；改为匹配任意深度。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29323)

### 10. **#29324 – 更简洁的修复：嵌套 .gitignore 中仅尾部斜杠的模式不锚定**
   - **标签**：P2 / core / size: S  
   - **内容**：针对相同问题的另一种最小化修复，仅统计末尾字符前的斜杠。  
   [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29324)

---

## 📊 功能需求趋势

从近期 Issues 中提炼三大核心方向：

| 方向 | 代表性 Issue | 社区热度 |
|------|-------------|----------|
| **Agent 决策智能化** | 子代理误报成功（#22323）、通用代理挂起（#21409）、不主动使用自定义技能（#21968） | 🔥🔥🔥🔥 |
| **企业级安全与权限** | 策略目录权限加固（#29336）、行级别脱敏（#26525）、阻止破坏性命令（#22672） | 🔥🔥🔥🔥 |
| **工具链与沙箱增强** | 零依赖 Bash 沙箱（#19873）、AST 感知文件操作（#22745）、浏览器代理锁恢复（#22232） | 🔥🔥🔥 |
| **持久化与状态管理** | `/compress` 不持久（#21335）、Auto Memory 重试低信号会话（#26522） | 🔥🔥 |

此外，**A2A 服务器**相关 PR 占比明显升高（日志、CORS、存储等），提示企业级集成需求上升。

---

## 🙋 开发者关注点

- **高频痛点**：  
  - 子代理行为不可控，在触及限制时返回假成功（#22323）。  
  - 通用子代理挂起、Shell 命令结束后终端卡住，严重影响日常开发流程（#21409、#25166）。  
- **配置与管理**：  
  - 符号链接不被识别（#20079）、自定义技能被闲置（#21968），用户期望更灵活的扩展机制。  
  - `/compress` 不是持久化，导致会话恢复后 token 浪费（#21335）。  
- **安全警示**：  
  - 自动内存功能存在凭证泄露风险（#26525）。  
  - 模型可能无意执行破坏性 git 操作，需要安全护栏（#22672）。  
- **社区情绪**：  
  - 用户对 nightly 版本的发布频率表示认可，但期待更稳定的代理行为；多个 “P1” 级 bug 已存在数周等待合并。  

---

📎 *数据来源：社区用户讨论及公开仓库活动。本日报由 AI 分析工具自动生成。*

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

好的，这是为您生成的 2026-09-15 GitHub Copilot CLI 社区动态日报。

---

# GitHub Copilot CLI 社区动态日报 — 2026-09-15

## 今日速览

今日发布了 `1.0.84-8` 版本，主要改进了对话体验和 Agent Factory 控制台，并修复了模型列表刷新问题。社区方面，大量新的 triage 状态 Issue 集中涌入，涉及沙箱策略绕过、会话状态卡死、MCP协议支持以及特定模型兼容性问题，预示着社区对稳定性、企业级策略和多模型支持的关注度正在上升。

## 版本发布

**最新版本: [v1.0.84-8](https://github.com/github/copilot-cli/releases/tag/v1.0.84-8)**
- **Added:** 新增 `transcriptView` 设置为 “concise”，可将工具活动分组为可展开的工作摘要，提升对话可读性。新增 `/config` 命令以在 CLI 中打开侧边栏配置界面。新增 `/sandbox` 网络主机允许/拒绝规则，同时不影响已配置的上游代理。
- **Improved:** 可从 `/factories` 对话框暂停和恢复 Agent Factory 运行。对原生 shell 重定向和 `sed` 操作应用了托管编辑和写入规则。
- **Fixed:** 修复了登录、切换账户或退出登录后模型列表不刷新问题。修复了 Claude 模型中思考形状（thinking shape）的适配问题。

**次要版本: [v1.0.84-7](https://github.com/github/copilot-cli/releases/tag/v1.0.84-7)**
- **Fixed:** 修复了 `sessionEnd` 钩子在 `/clear` 关闭会话时的触发问题。

## 社区热点 Issues

本期共涉及 21 个活跃 Issue，以下为 10 个最值得关注的问题：

1.  **[#4525] [已关闭] MCP 初始化故障 (1.0.81-1)** - **重要**：该 Issue 报告了一个严重的产品 bug，导致 Copilot CLI 在与使用 Python MCP SDK 2.0.0 的服务器握手时失败。虽然该 Issue 已关闭，但其揭示了 MCP 协议版本兼容性的核心问题，并可能已通过新版本修复。
    - 链接: [Issue #4525](https://github.com/github/copilot-cli/issues/4525)

2.  **[#4845] [新] 会话永久卡在“使用中”状态** - **高关注**：用户报告会话未被正确标记为空闲，导致无法自动恢复，每次都需要手动 `/resume`。这会严重影响工作流效率，是影响用户体验的核心痛点。
    - 链接: [Issue #4845](https://github.com/github/copilot-cli/issues/4845)

3.  **[#4846] [新] 沙箱用户文件系统策略被绕过** - **高关注**：当启用“允许开发工具访问”时，针对特定命令（如 `python`）的沙箱文件策略失效。这对企业环境下的安全合规构成直接威胁，预计会引起广泛讨论。
    - 链接: [Issue #4846](https://github.com/github/copilot-cli/issues/4846)

4.  **[#4843] [新] Warp 终端颜色不随主题变化** - **高关注**：颜色显示依赖于系统级明暗模式而非终端主题，导致在混合设置下文字难以阅读。这直接影响了终端模拟器的使用体验，尤其是像 Warp 这样的现代终端用户。
    - 链接: [Issue #4843](https://github.com/github/copilot-cli/issues/4843)

5.  **[#4844] [新] `--yolo` 标志在启动时被吞噬** - **高关注**：在从策略服务器获取配置前，启动时的预授权锁定会错误地禁用 bypass 模式，导致 `--yolo` 标志失效。这打破了高级用户对特定敏捷工作流的依赖。
    - 链接: [Issue #4844](https://github.com/github/copilot-cli/issues/4844)

6.  **[#4836] [新] Grok 4.5 模型工具数量超限导致 400 错误** - **模型兼容性**：CLI 在向 Grok-4.5 发送请求时，未遵守该模型 350 个工具的限制，导致全部失败。这表明模型兼容性测试需要覆盖更多边界情况。
    - 链接: [Issue #4836](https://github.com/github/copilot-cli/issues/4836)

7.  **[#4835] [新] Gemini Flash 因 MCP 数组枚举格式问题而失败** - **模型兼容性**：一个格式错误的 MCP 工具 schema（整数枚举直接作用于数组属性）会导致所有对 Gemini Flash 的请求失败。这凸显了 MCP schema 的严格验证和多模型适配的复杂性。
    - 链接: [Issue #4835](https://github.com/github/copilot-cli/issues/4835)

8.  **[#4837] [新] 策略驱动的插件安装后处于禁用状态** - **企业策略**：通过企业策略安装的插件被设置为 `enabled: false`，导致无法激活。这挫败了通过 MDM 进行统一插件管理的企业级用例。
    - 链接: [Issue #4837](https://github.com/github/copilot-cli/issues/4837)

9.  **[#4834] [新] 请求支持 MCP 2026-07-28 多轮请求协议** - **功能需求**：用户明确要求 CLI 支持新版 MCP 协议，以使用 MRTR（多轮请求）功能。这表明 MCP 生态在快速发展，CLI 需加快跟进。
    - 链接: [Issue #4834](https://github.com/github/copilot-cli/issues/4834)

10. **[#4725] [平台: Linux] 频繁的 JavaScript 堆内存不足崩溃** - **稳定性**：这是一个持续了近两周的严重 bug，影响 Linux 平台。CLI 每隔几分钟就会因内存不足而崩溃（内存占用接近 4GB），对日常开发工作造成严重干扰。社区讨论热烈，用户期待尽快修复。
    - 链接: [Issue #4725](https://github.com/github/copilot-cli/issues/4725)

## 重要 PR 进展

截至 2026-09-15，没有发现过去 24 小时内更新过的 Pull Request。

## 功能需求趋势

从近期的 Issues 中可以提炼出社区最关注的三个功能方向：
1.  **MCP 协议兼容性**：社区强烈要求支持 MCP 2026-07-28 及更高版本协议，特别是 MRTR（多轮请求）功能，以适应不断演进的 MCP 生态。
2.  **企业级管理与策略**：企业对 CLI 的集中管理需求显著增加，包括：为沙箱中的 yolo 模式设置独立策略、确保策略驱动的插件能正确启用、以及更严格的沙箱安全策略控制。
3.  **多模型支持与优化**：用户不仅希望支持更多模型（如 Grok, Gemini），更对 CLI 在处理这些模型时的兼容性、错误处理和边界情况测试提出了更高要求。同时，支持 BYOK（自带密钥）的稳定性也是用户痛点。

## 开发者关注点

从当前的社区反馈中，开发者普遍感到不满和关注的问题主要集中在：
- **稳定性与性能**：Linux 平台上频繁的内存溢出崩溃（#4725）和 Windows 上命令执行时控制台窗口闪烁（#4549）是影响日常使用最严重的稳定性问题。
- **会话状态管理**：会话卡死在“使用中”状态（#4845）和对中断响应后连接 ID. 残留（#4505）的问题，严重干扰了正常工作流。
- **配置与UI问题**：终端主题适配问题（#4843）和 `--yolo` 标志被意外覆盖（#4844）都反映了配置系统在某些场景下的鲁棒性不足。
- **安全与策略漏洞**：沙箱策略被绕过（#4846）和插件策略执行错误（#4837）是影响企业级用户信心的关键短板。

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

# Kimi Code CLI 社区动态日报 | 2026-09-15

**数据来源**: github.com/MoonshotAI/kimi-cli（截至2026-09-14 23:59 UTC）

---

## 1. 今日速览

过去24小时内，Kimi Code CLI 无新版本发布，共产生3个新 Issue（2个OPEN，1个已关闭）。社区焦点集中在：多Agent并发限制引发的会员权益争议（已关闭但仍有讨论）、CJK输入法下回车误触发送消息的Bug，以及一项针对Kimi Work交互式审阅的可视化批注功能需求。

---

## 2. 版本发布

无

---

## 3. 社区热点 Issues（共3条）

| ID | 状态 | 标题 | 作者 | 评论 | 链接 |
|----|------|------|------|------|------|
| #1383 | CLOSED | [bug] 为什么说的会员权益是支持多agent但是我两个小龙虾同时思考就会出现限制 | asecret | 6 | [查看](https://github.com/MoonshotAI/kimi-cli/issues/1383) |
| #2643 | OPEN | [kimi web] Enter pressed during IME composition is treated as 'send message' | wangjin1982 | 0 | [查看](https://github.com/MoonshotAI/kimi-cli/issues/2643) |
| #2642 | OPEN | 功能需求：Kimi Work 会话内支持对 Agent 回复的可视化批注与审阅反馈 | Zhywleo | 0 | [查看](https://github.com/MoonshotAI/kimi-cli/issues/2642) |

**Issue 分析**

- **#1383（已关闭）**：用户使用 OpenClaw API 运行两个 Agent（“小龙虾”）同时思考时遭遇 rate limit，质疑“多 Agent 支持”的会员权益名不副实。虽已关闭，但6条评论反映出社区对并发限制与宣传承诺之间落差的关注。该问题可能涉及 API 配额设计或资源调度策略，值得产品团队正面回应。

- **#2643（新提交）**：中文/日文/韩文用户在 `kimi web` 输入框中使用 IME 输入时，按回车确认拼音/字母上屏会被误触为“发送消息”，导致未完成的文本发出。该 Bug 直接影响全体 CJK 用户的核心输入体验，属于高优先级交互缺陷，目前零评论表明官方尚未介入。

- **#2642（新提交）**：用户建议在 Kimi Work 会话中对 Agent 的长回复（如计划、报告）提供**逐段可视化批注**能力，并支持将批注结构化地返回给 Agent 用于修订。这是对现有“纯文本修改意见”方式的升级，瞄准企业级协作审阅场景，契合工作流产品差异化方向。

---

## 4. 重要 PR 进展

无

---

## 5. 功能需求趋势

从过去24小时的 Issue 中可提炼两个主要需求方向：

1. **协作审阅结构化增强**（#2642）  
   社区期望 Kimi Work 引入类似文档协作软件的标注反馈机制（高亮、注释、修订建议），将用户对 Agent 输出的“感性与印象”转化为可执行的修改指令，降低沟通成本，提升人机协同效率。

2. **输入体验本地化修复**（#2643）  
   非拉丁字母输入法下的键盘事件处理问题表明，Kimi CLI 的用户群体已扩展至东亚地区，开发团队需要建立完整的输入法兼容性测试覆盖，避免“回车即发送”等基础交互失控。

---

## 6. 开发者关注点

- **多 Agent 并发限制的透明化**（#1383）：开发者反映实际使用中多 Agent 同时推理会触发 API 限制，与会员权益中“支持多 agent”的表述存在语义模糊。建议官方在文档或管理界面明确标注各套餐的**最大并发 Agent 数量**及**速率限制阈值**。

- **IME 输入法的死线问题**（#2643）：回车键误触发是典型的**P0级交互Bug**，在中文开发社区中极易引发负面口碑。建议团队优先复现并修复，或在发送前增加输入法状态检测（`isComposing` 属性）。

- **缺乏结构化反馈通道**（#2642）：当前用户只能通过输入框以自然语言描述修改意见，不仅效率低，且难以被 Agent 精确理解。开发者呼吁提供“点选-批注-提交”的闭环工具，提升长文本协作场景的用户留存率。

---

**编者注**：本日报基于24小时内的公开数据生成，如需查看完整历史记录请访问 [GitHub 仓库](https://github.com/MoonshotAI/kimi-cli)。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 | 2026-09-15

## 今日速览

**OpenCode v1.18.31 发布**，重点修复了 ACP 会话恢复时的模型/effort/mode 边界问题，并改进了 TUI 启动时的远程配置认证错误提示。社区方面，新版 UI/布局强制变更引发强烈反弹（至少 5 个高赞 issue 要求恢复经典布局），同时 v1.18.30 的系统提示词崩溃 Regression 已确认（#48803、#48372），官方快速在 v1.18.31 中修复。此外，多款模型（Muse Spark、DeepSeek V4.1 Flash）出现可用性故障，开发者需留意。

## 版本发布

### [v1.18.31](https://github.com/anomalyco/opencode/releases/tag/v1.18.31) (2026-09-15)

| 模块 | 变更内容 |
|------|----------|
| **Core** | 修复加载、恢复或 fork 会话时 ACP 会话模型、effort、mode 和推理 chunk 的边界恢复（@JacobNWolf） |
| **TUI** | 启动时显示远程配置认证错误，并在认证失败时以退出状态退出 |
| **Extensions** | 进行了改进（Improvement，详情未完整公布） |

> ⚠️ **重点跟进**：本次版本同时修复了 v1.18.30 中由于 `SystemPrompt.environment` 引发的 `TypeError: undefined is not an object` 崩溃（#48803、#48372、#48903），请受影响用户尽快升级。

---

## 社区热点 Issues（精选 10 条）

### 1. [#13984] CLI 中无法复制粘贴（59 条评论）
- **链接**：[Issue #13984](https://github.com/anomalco/opencode/issues/13984)
- **重要性**：自 2026-02 起累计 32 👍，至今未解决，严重影响终端用户体验
- **摘要**：用户按下“复制到剪贴板”后，Ctrl+V 无法粘贴，怀疑是 TUI 剪贴板绑定问题

### 2. [#17318] SSE read timed out 错误（48 条评论）
- **链接**：[Issue #17318](https://github.com/anomalco/opencode/issues/17318)
- **重要性**：高赞（37 👍），涉及文件写入时的超时中断，影响大文件生成场景
- **摘要**：使用“brainstorm + planning-with-files”技能时频繁触发 SSE 超时

### 3. [#48741] Muse Spark 系列模型工具调用崩溃（26 条评论）
- **链接**：[Issue #48741](https://github.com/anomalco/opencode/issues/48741)
- **重要性**：最新 beta 版本（0.0.0-beta-18050）中关键模型故障，已由 PR #48908 修复中
- **摘要**：模型接收图片或进行工具调用时返回 `encrypted_content` 错误，怀疑是 Zen 网关验证问题

### 4. [#48882] 要求恢复经典侧边栏布局（14 条评论 / 20 👍）
- **链接**：[Issue #48882](https://github.com/anomalco/opencode/issues/48882)
- **重要性**：用户强烈要求将旧版双栏布局（持久左栏+会话面板）作为可选项，评论中多人表示新 UI 降低多项目管理效率
- **摘要**：20242 号 PR 的侧边栏重设计移除了经典布局，社区呼吁增加选项

### 5. [#26602] 桌面版本地 Provider 5 分钟超时（13 条评论）
- **链接**：[Issue #26602](https://github.com/anomalco/opencode/issues/26602)
- **重要性**：即使配置 `timeout: false` 仍受 undici 默认 300s 超时限制，影响 Ollama/本地跑大模型的用户
- **摘要**：OpenCode Desktop 在 5 分钟时抛出 `Headers Timeout Error`

### 6. [#49041] DeepSeek V4.1 Flash 不可用（9 条评论）
- **链接**：[Issue #49041](https://github.com/anomalco/opencode/issues/49041)
- **重要性**：热门模型突然宕机，近期已出现多次类似问题（#40479），用户满意度下降
- **摘要**：模型无响应，界面无限旋转；其他 DeepSeek 模型正常

### 7. [#31137] Web UI “自动接受权限”按钮在新布局下被禁用（9 条评论 / 9 👍）
- **链接**：[Issue #31137](https://github.com/anomalco/opencode/issues/31137)
- **重要性**：新布局导致核心权限设置功能失效，影响自动化流程
- **摘要**：启用“New layout and design”后，权限自动接受开关变灰

### 8. [#48803] v1.18.30：每个 Prompt 都报 `TypeError: undefined layer node`（5 条评论 / 5 👍）
- **链接**：[Issue #48803](https://github.com/anomalco/opencode/issues/48803)
- **重要性**：严重的 Regression，回退至 v1.18.20 正常，已在 v1.18.31 修复
- **摘要**：系统提示组装时因 `Effect layer` 未定义而崩溃，相同配置在旧版正常

### 9. [#48837] 强制 V2 界面破坏多项目/多代理工作流（4 条评论 / 13 👍）
- **链接**：[Issue #48837](https://github.com/anomalco/opencode/issues/48837)
- **重要性**：用户明确指出新界面无法切换回旧版，且 20+ 会话场景下效率降低
- **摘要**：新版布局无法同时扁平化管理多个项目，要求恢复切换选项

### 10. [#48372] `SystemPrompt.environment` 崩溃（5 条评论 / 19 👍）
- **链接**：[Issue #48372](https://github.com/anomalco/opencode/issues/48372)
- **重要性**：与 #48803 同源，影响 `opencode run` 和 TUI，社区已积累大量 +1
- **摘要**：`SystemPrompt.environment` 抛出 `TypeError: undefined is not an object (evaluating 'a.name')`

---

## 重要 PR 进展（精选 10 条）

### 1. [#49081] 恢复编辑跟进消息时的附件队列
- **链接**：[PR #49081](https://github.com/anomalco/opencode/pull/49081)
- **状态**：已合并
- **内容**：编辑跟进消息时附件隐藏问题，现在编辑时附件会正确显示并可移除

### 2. [#49080] 移除附件标签前缀“Plus”
- **链接**：[PR #49080](https://github.com/anomalco/opencode/pull/49080)
- **状态**：已合并
- **内容**：纯附件消息不再显示“Plus 1 attachment”，改为“1 attachment”，更清晰

### 3. [#48908] 修复 Muse Spark 等模型因加密推理导致会话恢复失败
- **链接**：[PR #48908](https://github.com/anomalco/opencode/pull/48908)
- **状态**：待审查中
- **内容**：针对 #48741，当 Provider 拒绝旧加密推理内容时，自动降级恢复，避免崩溃

### 4. [#49064] 为代理 Markdown 提示文件添加 `{file:...}` 插值
- **链接**：[PR #49064](https://github.com/anomalco/opencode/pull/49064)
- **状态**：已合并
- **内容**：`CLAUDE.md`、`AGENTS.md` 等文件中可使用 `{file:./common/juggling.md}` 引用外部文件内容，极大提升提示复用性

### 5. [#49066] 新增代理集群标签页及 Token 迷你趋势图
- **链接**：[PR #49066](https://github.com/anomalco/opencode/pull/49066)
- **状态**：待合规性审查
- **内容**：跨项目的代理视图，包含代理状态、阶段、Token 速率、缓存命中率、TTFT 等，并配有 64 桶输出 Token 火花图

### 6. [#49078] TUI 添加 `/effort` 命令别名
- **链接**：[PR #49078](https://github.com/anomalco/opencode/pull/49078)
- **状态**：已合并
- **内容**：用户现可用 `/effort` 代替 `/variants` 或 `/thinking` 来切换模型 Effort 级别

### 7. [#49076] CodeMode 增加 `Uint8Array`、`TextEncoder`、`TextDecoder`
- **链接**：[PR #49076](https://github.com/anomalco/opencode/pull/49076)
- **状态**：待审查中
- **内容**：扩展的二进制类型支持，工具边界拒绝二进制并提示编码为文本，向完整 WASM 运行时迈进

### 8. [#49074] 文档：添加 `opencode-dashscope-imagegen` 插件
- **链接**：[PR #49074](https://github.com/anomalco/opencode/pull/49074)
- **状态**：已合并
- **内容**：社区插件，支持通过 DashScope API 生成图片，纳入生态系统列表

### 9. [#49065] 增强 CodeMode 工具边界传递：Set、RegExp、URLSearchParams
- **链接**：[PR #49065](https://github.com/anomalco/opencode/pull/49065)
- **状态**：已合并
- **内容**：之前 `Set` 传递为 `{}`，现在保留数据信息，减少数据丢失

### 10. [#49052] 修复 Azure Foundry 消息区分器
- **链接**：[PR #49052](https://github.com/anomalco/opencode/pull/49052)
- **状态**：已合并
- **内容**：为 Azure Foundry Responses 添加 `type: "message"` 区分器，避免与自定义网关冲突

---

## 功能需求趋势

从近 24 小时（特别是更新于 9月14-15日 的 Issues）来看，社区最关注的功能方向如下：

| 功能方向 | 代表 Issues | 热度 |
|----------|-------------|------|
| **恢复/可选经典 UI 布局** | #48882, #48837, #49021, #49031, #49043 | 🔥🔥🔥🔥🔥 至少 5 条高赞需求，总计 43+ 👍 |
| **模型稳定性与兼容性** | #48741, #49041, #40479, #49033 | 模型挂起、加密推理失败、路由无响应 |
| **超时控制可配置** | #26602, #49044 | undici 300s 硬限制无法覆盖，本地 Provider 5 分钟必挂 |
| **W3C Trace 传播** | #49038 | 向 LLM 请求添加 `traceparent` 以支持可观测性 |
| **Tab 快捷键支持** | #37077 | Ctrl+T/W/Tab 切换标签页 |
| **图片识别与多模型协作** | #49026, #49028 | 模型能看图但 OpenCode 传递失败，希望同一任务可调用不同模型 |
| **上下文压缩自动触发** | #46137 | 大上下文模型（如 hy3）永远不触发压缩，浪费 Token |
| **Windows Defender 误报** | #49047 | 执行文件被侦测为 Trojan，影响安装信任 |

## 开发者关注点（高频痛点）

1. **v1.18.30 的 SystemPrompt Regression**：所有 Prompt 报 `TypeError`，影响范围极广，虽已在 v1.18.31 修复，但暴露了核心测试覆盖不足问题。
2. **新 UI 强制使用**：多个用户反馈新版布局破坏多项目管理与垂直标签流，且旧版无法恢复，被认为是“倒退”。
3. **本地/慢速 Provider 超时**：undici 默认 300s headers 超时不可配置，导致 Ollama 等本地模型在长时间思考时连接中断。
4. **模型可用性波动**：DeepSeek V4.1 Flash、Muse Spark 等模型近期频繁出现故障，用户对 Zen 网关可靠性产生质疑。
5. **Session 会话数据丢失**：更新后侧边栏不显示旧项目（#49029），影响工作连续性。
6. **MCP 工具 Schema 不兼容**：Gemini 模型拒绝包含 `nullable array` 或 `anyOf` 的 MCP 工具定义，导致绑定失败（#48073）。

---

*数据来源：GitHub anomalyco/opencode 仓库 Issues & PRs，截止 2026-09-15 UTC。*

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 – 2026-09-15

## 今日速览
- **计费与缓存问题集中爆发**：多个 Open/High 级 Issue 指出 `bedrock-converse` 和 `vercel-ai-gateway` 对缓存写入的计费速率识别错误，导致用户被按 5 分钟费率收取 1 小时缓存写入费用，影响预算与成本控制。
- **会话初始化性能优化落地**：PR #9601 通过精确 session ID 查找替代全量 transcript 扫描，显著降低 `--session-id` 新会话的启动耗时（从 ~16s 降至 ~0.5s），解决大量用户反馈的卡顿问题。
- **TUI 严重崩溃修复进行中**：Issue #9606 暴露了 `wordWrapLine` 对 CJK 全宽字符的无限递归 Bug，导致 TUI 直接堆栈溢出崩溃，已在当天被标记为 Closed。

## 版本发布
（过去 24 小时内无新 Release）

---

## 社区热点 Issues（Top 10）

### 1. bedrock-converse: usage.input 未按模型族归一化 → 错误缓存未命中提示、输入成本翻倍
- **编号**：#8752 | **状态**：OPEN | **评论**：6 | 👍 5
- **链接**：https://github.com/earendil-works/pi/issues/8752
- **重要性**：直接影响所有使用 Bedrock 的用户的成本核算，Anthropic 与 OpenAI 系列对 `usage.input` 的定义（净 vs 毛）差异导致 `cacheRead` 和 `cacheWrite` 双倍计算，社区要求紧急修复。

### 2. Anthropic Messages via Gateway: cacheWrite1h 永远为 0，1h 写入按 5m 费率计费
- **编号**：#9210 | **状态**：OPEN | **评论**：5 | 👍 0
- **链接**：https://github.com/earendil-works/pi/issues/9210
- **重要性**：Vercel AI Gateway 用户即使设置 1 小时缓存保留期，`cacheWrite1h` 字段始终为零，导致所有缓存写入被按 5 分钟速率计费，大幅增加成本。

### 3. vercelGatewayRouting 配置在 Gateway provider 上无效
- **编号**：#9211 | **状态**：OPEN | **评论**：5 | 👍 0
- **链接**：https://github.com/earendil-works/pi/issues/9211
- **重要性**：文档中的路由配置（`only`/`order`）仅对 `openai-completions` 生效，而内置的 `vercel-ai-gateway` 目录全部使用 `anthropic-messages` 传输，导致该配置完全失效，用户无法控制 Provider 选择。

### 4. 压缩后，过时的签名思考块在每次对话中重播，Anthropic 返回 `prefix_binding_mismatch`
- **编号**：#9391 | **状态**：OPEN | **评论**：4 | 👍 1
- **链接**：https://github.com/earendil-works/pi/issues/9391
- **重要性**：长时间会话执行 context 压缩后，每次后续请求都会重播同一组 15 个已过期的 thinking block，被 Anthropic 以“前缀绑定不匹配”拒绝，导致请求失败或降级。严重影响长会话的稳定性。

### 5. 错误/中止的 turn 在上下文留下未匹配的 toolCall，后续 `runAgentLoopContinue` 被 Provider 拒绝
- **编号**：#9306 | **状态**：OPEN | **评论**：4 | 👍 0
- **链接**：https://github.com/earendil-works/pi/issues/9306
- **重要性**：Agent 调用工具过程中若发生错误或用户中止，流式输出的 `toolCall` blocks 会残留上下文，后续继续时 Provider 收到不完整的工具调用报错。影响所有工具密集型自动化场景。

### 6. bedrock-converse: 1h 缓存写入按 5m 速率计费
- **编号**：#9457 | **状态**：OPEN | **评论**：3 | 👍 4
- **链接**：https://github.com/earendil-works/pi/issues/9457
- **重要性**：与 #9210 类似，但针对 Bedrock `converse` 流式接口，`cacheWrite1h` 未被正确设置，导致 1h 缓存写入时的费用被低估（按 5m 计费）。高赞票数显示社区高度关注。

### 7. `--session-id` 使用新 ID 时会扫描所有 transcripts，启动缓慢
- **编号**：#9440 | **状态**：OPEN | **评论**：3 | 👍 0
- **链接**：https://github.com/earendil-works/pi/issues/9440
- **重要性**：扩展通过 `--session-id` 创建新会话时，Pi 会加载全部 4K+ transcripts 读取头部信息，导致启动延迟长达 16 秒，严重影响扩展使用体验。PR #9601 正尝试修复。

### 8. Prompt 模板无效 frontmatter 被静默丢弃，无任何警告
- **编号**：#9354 | **状态**：OPEN | **评论**：3 | 👍 0
- **链接**：https://github.com/earendil-works/pi/issues/9354
- **重要性**：与 skill 文件的警告行为不一致，模板 YAML 错误时用户完全不知情，`/` autocomplete 中也不显示。降低可用性，需统一错误处理。

### 9. openai-completions 丢弃 Gemini `thoughtSignature`，破坏多轮工具使用
- **编号**：#9444 | **状态**：OPEN | **评论**：2 | 👍 0
- **链接**：https://github.com/earendil-works/pi/issues/9444
- **重要性**：通过 OpenAI 兼容网关使用 Gemini 时，流式 `tool_calls` 中的 `thoughtSignature` 未被捕获，导致第二次工具调用请求缺少签名被拒（400）。阻止 Gemini 用户执行工具链任务。

### 10. TUI 崩溃: `wordWrapLine` 在单个宽于 maxWidth 的字素上无限递归（如 CJK 字符）
- **编号**：#9606 | **状态**：CLOSED | **评论**：1 | 👍 0
- **链接**：https://github.com/earendil-works/pi/issues/9606
- **重要性**：编辑器中的换行函数对全宽字符（中文、日文等）在布局宽度为 1 时陷入无限调用，导致 `Maximum call stack size exceeded`。虽然当天被关闭，但展示了 TUI 对 CJK 支持的薄弱环节。

---

## 重要 PR 进展（Top 10）

### 1. fix(coding-agent): apply provider hooks to summarization streams（#9607）
- **状态**：CLOSED | **作者**：lksgs0
- **链接**：https://github.com/earendil-works/pi/pull/9607
- **内容**：修复压缩/分支摘要等直接调用 session stream 时，扩展注册的 `before_provider_request` hooks 被跳过的问题。现在摘要流也能正确触发扩展拦截逻辑。

### 2. feat(ai): add GMI Cloud provider（#9605）
- **状态**：CLOSED | **作者**：isaachuangGMICLOUD
- **链接**：https://github.com/earendil-works/pi/pull/9605
- **内容**：新增 GMI Cloud 作为内置 Provider，复用 OpenAI Chat Completions 适配器，用户只需设置 `GMI_API_KEY` 即可接入。

### 3. feat(coding-agent): report the shell's pid to the caller（#9604）
- **状态**：CLOSED | **作者**：youssefsiam38
- **链接**：https://github.com/earendil-works/pi/pull/9604
- **内容**：在 `BashOperations` 的 exec 选项中增加 `onSpawn(pid)` 回调，允许调用者（如 headless 服务器）获取子进程 PID 以追踪进程树。

### 4. Mid conversation system messages（#9548）
- **状态**：OPEN | **作者**：mitsuhiko
- **链接**：https://github.com/earendil-works/pi/pull/9548
- **内容**：重大机制变更：将系统提示文本和工具变更记录到 transcript 中，而非静默改写会话初始条件。支持会话恢复、分支导航时还原状态，并保留缓存前缀。提案性 PR，社区讨论热烈。

### 5. fix(ai): preserve reasoning_content on cross-model replay into DeepSeek-family endpoints（#8732）
- **状态**：CLOSED | **作者**：ethanhe-036
- **链接**：https://github.com/earendil-works/pi/pull/8732
- **内容**：解决跨模型重放（切换到 DeepSeek 系列）时 assistant 消息携带的 `reasoning_content` 丢失问题，避免被 DeepSeek API 拒绝。已在多个终端验证。

### 6. fix(coding-agent): avoid transcript scans for exact session IDs（#9601）
- **状态**：OPEN | **作者**：metaist
- **链接**：https://github.com/earendil-works/pi/pull/9601
- **内容**：直接使用精确 session ID 查找 header，替代加载整个 transcript，将新会话启动时间从 16s 降至约 0.5s。解决 #9440 的性能瓶颈。

### 7. feat(ai): add Gemini-only Antigravity provider（#9594）
- **状态**：CLOSED | **作者**：a209m
- **链接**：https://github.com/earendil-works/pi/pull/9594
- **内容**：为 Google Antigravity 提供一级 OAuth Provider，恢复基于订阅的 Gemini 访问（之前实现被移除）。用户可直接通过 OAuth 流程使用 Gemini 模型。

### 8. fix(coding-agent): preserve indentation in rendered diffs（#9274）
- **状态**：OPEN | **作者**：dannote
- **链接**：https://github.com/earendil-works/pi/pull/9274
- **内容**：修复编辑工具在渲染 diff 时，插入文本后可能丢失删除行前导缩进的问题。改善 diff 可读性。

### 9. feat(coding-agent): export image bytes MIME detector（#9591）
- **状态**：CLOSED | **作者**：kaixuantan
- **链接**：https://github.com/earendil-works/pi/pull/9591
- **内容**：将 `detectSupportedImageMimeType` 工具函数导出，供读取 tool 扩展（如 sandbox 获取字节流）使用，提升扩展开发便利性。

### 10. feat(coding-agent): bundle Node runtime（#8474）
- **状态**：CLOSED | **作者**：mitsuhiko
- **链接**：https://github.com/earendil-works/pi/pull/8474
- **内容**：重构 `pi-coding-agent` 打包方式，大幅减少文件加载数，解决 Windows 上因 Windows Defender 导致的启动慢问题，以及 IO 瓶颈。

---

## 功能需求趋势

从近期 Issue 和 PR 中提炼出社区最关注的三大方向：

1. **计费与缓存机制标准化**  
   大量反馈聚焦于不同 Provider（Bedrock、Vercel Gateway、OpenAI）对缓存写入（`cacheWrite1h`、`cacheRead`）的费率计算不一致问题，尤其是 1h 缓存写入被按 5m 计费的 Bug。社区要求统一计费逻辑并在文档中清晰说明。

2. **长会话稳定性与可靠性**  
   包括压缩后历史块重播、未匹配 toolCall 残留、session ID 扫描性能、跨模型重放丢失 `reasoning_content` 或 `thoughtSignature` 等。用户希望 Pi 能更稳定地维护代理会话状态，避免 Provider 拒绝或数据错乱。

3. **扩展性与自定义能力**  
   多篇 Issue/PR 涉及扩展 API：支持在 `session_start` 追加系统提示（#9434）、提供原子中断与消息交付（#9578）、允许扩展控制工具执行结束/中断、导出工具函数（#9591）等。说明开发者希望 Pi 成为更强大的可编程 Agent 平台。

---

## 开发者关注点

- **痛点高频区**：  
  - **缓存计费 Bug** (#8752, #9210, #9457) 是当前最突出的成本相关痛点，用户发现多次请求后费用异常。  
  - **会话初始化性能** (#9440) 对使用自动化扩展的开发者影响很大，等待 16 秒无法接受。  
  - **TUI 崩溃** (#9606) 和 **diff 缩进丢失** (#9274) 影响日常编辑体验。  
  - **Provider 兼容性**：DeepSeek 跨模型重放、Gemini 多轮工具使用等因缺少字段被拒，需要适配器层补齐。

- **实用建议**：  
  - 关注 #9601 的合入，将显著改善 `--session-id` 用户的使用体验。  
  - 使用 Verc

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 (2026-09-15)

## 📌 今日速览

- **v0.23.4 正式发布**：移除了频道中的可配置消息前缀过滤，并同步更新了夜间版与 CUA Driver 预构建二进制。
- **社区焦点**：多个 P1 级 Bug 持续发酵 —— TUI 因 React #185 静默崩溃、非千问模型因 `metadata` 字段导致 400 错误、Windows 下扩展操作 EPERM 问题。开发团队已响应并提交多个修复 PR。
- **新功能与修复**：Web Shell 标签切换动画、容器执行子代理、`qwen batch` 批量命令等 PR 获得关注；同时多项安全与兼容性修复（shell 注释语义、NTFS 文件 ID 问题）正在审查中。

---

## 📦 版本发布

### 🆕 v0.23.4 (正式版)
- **主要变更**：
  - **Breaking Change**：移除通道中可配置的消息前缀过滤，符合条件的信息现在遵循正常的发送者、群组、@提及和配对策略，不再依赖前缀。
  - 详情见完整变更日志。
- **链接**: [Release v0.23.4](https://github.com/QwenLM/qwen-code/releases/tag/v0.23.4)

### 🌙 v0.23.4-nightly.20260914
- **变更亮点**：
  - 测试：记录 Windows inode 隐藏问题并跳过其中一个（@yiliang114）
  - 修复：保留 CUA 驱动相关逻辑（片段显示）
- **链接**: [Release v0.23.4-nightly](https://github.com/QwenLM/qwen-code/releases/tag/v0.23.4-nightly.20260914.f024b37689)

### 🔌 cua-driver-rs v0.20.8 与 v0.20.7
- 提供 macOS（已签名公证）、Linux（x86_64+arm64，glibc 2.31）、Windows（UIAccess +原生 SDK）的预构建二进制。
- 注意：v0.20.8 为最新版，需检查是否包含 v0.20.7 的累积修复。
- **链接**: [v0.20.8](https://github.com/QwenLM/qwen-code/releases/tag/cua-driver-rs-v0.20.8) | [v0.20.7](https://github.com/QwenLM/qwen-code/releases/tag/cua-driver-rs-v0.20.7)

---

## 🔥 社区热点 Issues（Top 10）

### 1️⃣ TUI 静默崩溃（React #185）— #11500
- **状态**: OPEN  
- **评论**: 13 | 👍 1  
- **摘要**: 多个后台代理同时完成时，终端 UI 因 Ink 布局监听器 `setState` 导致 React #185（更新深度超限）崩溃回到 Shell，无任何错误显示。  
- **影响**: 高优先级 P1，影响所有终端用户，与 #11849 类似。  
- **链接**: [Issue #11500](https://github.com/QwenLM/qwen-code/issues/11500)

### 2️⃣ 非千问模型因 `metadata` 字段 400 错误 — #11590
- **状态**: CLOSED  
- **评论**: 8 | 👍 0  
- **摘要**: 向 DashScope 网关发送请求时，Qwen Code 自动注入 `metadata` 对象，导致非 Qwen 模型（如 ZHIPU/GLM-5.3-Flash）反序列化失败并返回 400。删除该字段后恢复正常。  
- **影响**: 严重阻碍多模型集成，已关闭但修复需后续验证。  
- **链接**: [Issue #11590](https://github.com/QwenLM/qwen-code/issues/11590)

### 3️⃣ 函数参数为空导致 400 错误 — #11834
- **状态**: OPEN  
- **评论**: 6 | 👍 0  
- **摘要**: 用户遇到 `API Error: 400 invalid params, function parameters is empty (2013)`，即使是简单对话也会触发。涉及内容生成核心。  
- **链接**: [Issue #11834](https://github.com/QwenLM/qwen-code/issues/11834)

### 4️⃣ VSCode 插件在 Remote-SSH 下卡加载 — #11556
- **状态**: OPEN  
- **评论**: 6 | 👍 0  
- **摘要**: `vscode-ide-companion` 0.23.1 在 Remote-SSH 模式下 WebView 一直加载中无法使用，Linux ARM64 服务端。  
- **链接**: [Issue #11556](https://github.com/QwenLM/qwen-code/issues/11556)

### 5️⃣ 后台 Agent 完成时静默崩溃（#11500 类似）— #11849
- **状态**: OPEN  
- **评论**: 5 | 👍 0  
- **摘要**: 用户报告 0.23.3 间歇性崩溃回 Shell，无明显模式，长时间工作后更易触发。怀疑与 #11500 相关。  
- **链接**: [Issue #11849](https://github.com/QwenLM/qwen-code/issues/11849)

### 6️⃣ 权限队列死锁：空闲会话阻塞其他会话 — #11795
- **状态**: OPEN  
- **评论**: 5 | 👍 0  
- **摘要**: 权限队列基于 ACP 连接键，一个空闲会话的未回答提示会无限期阻塞守护进程上的所有其他会话。已提交部分修复 (#11802)。  
- **链接**: [Issue #11795](https://github.com/QwenLM/qwen-code/issues/11795)

### 7️⃣ `--acp` 忽略审批模式（安全风险） — #11887
- **状态**: OPEN  
- **评论**: 4 | 👍 0  
- **摘要**: `qwen --acp` 会话即使设置为限制模式，仍自动执行文件写入和 Shell 命令，不会向客户端发送 `session/request_permission`。  
- **影响**: P2 但属于严重安全漏洞。  
- **链接**: [Issue #11887](https://github.com/QwenLM/qwen-code/issues/11887)

### 8️⃣ macOS 下 PTY 不可用 — #11872
- **状态**: OPEN  
- **评论**: 3 | 👍 0  
- **摘要**: Web Terminal 面板显示 `[Error: PTY not available]`，因为 `@lydell/node-pty` 预构建未打包，且 macOS 代码签名阻止本地安装的预构建加载。  
- **链接**: [Issue #11872](https://github.com/QwenLM/qwen-code/issues/11872)

### 9️⃣ shell 注释中运算符被错误分割 — #11882
- **状态**: OPEN  
- **评论**: 2 | 👍 0  
- **摘要**: 两个复合命令分割器未统一处理 `#` 注释语义，导致权限判定错误。需要设计决策以对齐实现。  
- **链接**: [Issue #11882](https://github.com/QwenLM/qwen-code/issues/11882)

### 🔟 DeepSeek 模型 token 限制错误 — #11894
- **状态**: OPEN  
- **评论**: 2 | 👍 0  
- **摘要**: `deepseek-flash` 模型被错误解析为 128k/32k（实际应为 V4 1M/384k），导致长对话压缩失败而崩溃。  
- **链接**: [Issue #11894](https://github.com/QwenLM/qwen-code/issues/11894)

---

## 📬 重要 PR 进展（Top 10）

### 1️⃣ 修复 Hook 匹配器尾随空格 — #11871
- **状态**: OPEN  
- **作者**: yiliang114  
- **摘要**: 修复 hook 匹配器结尾转义空格时被 `trim()` 错误移除导致正则表达式无效的问题。  
- **链接**: [PR #11871](https://github.com/QwenLM/qwen-code/pull/11871)

### 2️⃣ 使 Ink useBoxMetrics 循环保护独立于机器速度 — #11835
- **状态**: OPEN  
- **作者**: yiliang114  
- **摘要**: 将循环保护从基于时间改为基于提交次数，确保在任何机器上都能正确检测振荡，不再只影响快速机器。  
- **链接**: [PR #11835](https://github.com/QwenLM/qwen-code/pull/11835)

### 3️⃣ Web Shell 标签滑动动画 — #11844
- **状态**: OPEN  
- **作者**: callmeYe  
- **摘要**: 添加 200ms 滑动效果，使激活的标签更醒目，提升 Web Shell 侧边栏切换体验。  
- **链接**: [PR #11844](https://github.com/QwenLM/qwen-code/pull/11844)

### 4️⃣ 捆绑 node-pty 预构建修复 Web 终端 — #11881
- **状态**: OPEN  
- **作者**: yiliang114  
- **摘要**: 将 `@lydell/node-pty` 的六个可选依赖预构建打包进独立归档，解决 macOS/Linux 下 PTY 不可用的问题（对应 #11872）。  
- **链接**: [PR #11881](https://github.com/QwenLM/qwen-code/pull/11881)

### 5️⃣ 新增 `qwen batch` 命令支持 DashScope Batch API — #11874
- **状态**: OPEN  
- **作者**: yiliang114  
- **摘要**: 提供 `submit`/`status`/`fetch`/`cancel` 子命令，可批量提交单轮聊天请求，享受半价计费和独立配额。  
- **链接**: [PR #11874](https://github.com/QwenLM/qwen-code/pull/11874)

### 6️⃣ 子代理容器执行支持 — #11711
- **状态**: OPEN  
- **作者**: wenshao  
- **摘要**: 允许通过 `QWEN_AGENT_EXECUTION_BACKEND=docker` 或 `podman` 将子代理运行在容器中，可配置强制要求，增强安全隔离。  
- **链接**: [PR #11711](https://github.com/QwenLM/qwen-code/pull/11711)

### 7️⃣ 修复 Windows 扩展更新/卸载 EPERM — #11889
- **状态**: OPEN  
- **作者**: niheaven  
- **摘要**: 当 Windows 锁定扩展目录时，改用复制+删除的方式代替重命名，避免 `EPERM` 错误。  
- **链接**: [PR #11889](https://github.com/QwenLM/qwen-code/pull/11889)

### 8️⃣ 关闭 OpenTUI 与 Ink 之间的 12 个兼容性缺口 — #11806
- **状态**: OPEN  
- **作者**: chiga0  
- **摘要**: 迁移 OpenTUI 渲染器后发现的 12 个差异，包括 8 个行为差异和 4 个代码审查缺口。  
- **链接**: [PR #11806](https://github.com/QwenLM/qwen-code/pull/11806)

### 9️⃣ CI：跳过未变更差异的重新审查 — #11857
- **状态**: OPEN  
- **作者**: yiliang114  
- **摘要**: 当推送的 diff 与已审查的 base 字节完全相同时（如合并 main），自动跳过 review 流程，节省资源。  
- **链接**: [PR #11857](https://github.com/QwenLM/qwen-code/pull/11857)

### 🔟 修复暂停的后台代理超时 — #11270
- **状态**: OPEN  
- **作者**: yiliang114  
- **摘要**: 新增固定进度监控：普通后台代理（包括新启动、恢复运行）15 分钟无进展则超时，每个工具执行 10 分钟时限。  
- **链接**: [PR #11270](https://github.com/QwenLM/qwen-code/pull/11270)

---

## 🧭 功能需求趋势

从近 24 小时的 Issues 和 PR 中，社区最关注的方向包括：

1. **IDE 集成与兼容性**：VS Code 插件在 Remote-SSH 下不可用、扩展管理 UI 反馈缺失等问题反复出现。
2. **多模型/网关支持**：非 Qwen 模型因 `metadata` 字段无法使用，用户强烈要求兼容更多第三方模型（如 GLM、DeepSeek）。
3. **终端与 UI 稳定性**：TUI 崩溃（React #185）、PTY 不可用在多平台（尤其是 macOS）上持续影响体验。
4. **权限与安全**：ACP 模式忽略审批、shell 注释分割错误、NTFS 文件 ID 安全漏洞（2^53 限制）等需要紧急修复。
5. **性能与可靠性**：后台代理超时机制、CI 随机失败、Windows 下扩展操作的 EPERM 问题，表明社区对生产环境稳定性的期待。

---

## 🛠️ 开发者关注点

- **痛点高频提及**：
  - **TUI 崩溃问题**：多个 Issue (#11500, #11849, #11873) 指向同一根因——`useBoxMetrics` 循环与 Ink 渲染器冲突，开发者已提交 #11835 尝试修复，但仍需社区验证。
  - **Windows 文件操作障碍**：扩展更新/卸载 `EPERM` (#11883)、NTFS 64-bit 文件 ID 比较失败 (#11848, #11877)，Windows 用户受影响严重。
  - **测试环境脆弱性**：CI 在 Windows 和负载下测试不稳定 (#11817, #11893)，多个 PR 试图修复 test 套件的机器依赖性。

- **开发者建议**：
  - 加快 `metadata` 多模型兼容性修复（已关闭但仍需注意后续回退）。
  - 关注 `qwen batch` 和容器执行子代理等新功能，有望降低 API 成本并提升安全隔离。
  - 建议团队统一 shell 注释分割器的实现逻辑，避免两个 splitter 不一致引发权限误判 (#11882)。

---

> 本日报数据源：GitHub [QwenLM/qwen-code](https://github.com/QwenLM/qwen-code) 仓库，统计时间截至 2026-09-15 08:00 UTC。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，各位开发者，早上好。欢迎阅读 **2026年9月15日 DeepSeek TUI 社区动态日报**。

以下是为您整理的最新社区动向：

---

### **今日速览**
项目已从 `deepseek-tui` 正式迁移至 **CodeWhale**，并发布了修复多个严重缺陷的 `v0.9.14` 版本。社区热度聚焦于 **Agent 工作流管理**、**Token 用量诊断**及 **Fleet（子代理）模型管理**等复杂功能，同时大量围绕着新版本 `v0.9.14` 的 **Bug 修复**和**文档补充**工作也在快速推进。

### **版本发布**
**v0.9.14** - `console-freeze, approval-death, compaction, and session-retention fixes`
- **核心修复**：此版本是一次紧急修补，主要解决了三个导致终端冻结或静默死亡的严重问题：
    1.  在对话进行中执行 `/mcp` 命令导致的控制台冻结。
    2.  无人值守的审批流程因空闲超时被取消，导致任务静默失败。
    3.  解决了 Token 压缩（compaction）过程中遗留的 `tool_result` 数据空洞问题。
- **其他修复**：改进了会话保留策略，并修复了部分已知问题。
- **（原 v0.9.13 版本已废弃）**：鉴于 v0.9.14 的发布，v0.9.13 版本已被标记为废弃。旧版 `deepseek-tui` npm 包也已停止更新。

### **社区热点 Issues**
本期挑选了 10 个最具讨论价值的 Issue（含已关闭），涵盖架构、新功能与Bug：

1.  **[EPIC-005] 核心架构重构：Crate 分解 (Umbrella)**
    - **链接**: [Issue #5316](https://github.com/Hmbown/CodeWhale/issues/5316)
    - **重要性**: 这是目前社区最关注的超级 Issue（27条评论），旨在将庞大的代码库（如`lib.rs`、`config.rs`等）进行模块化拆分。它是一切后续迭代的基石，代表了项目长期健康发展的方向。

2.  **[enhancement] Token 用量与工具诊断功能**
    - **链接**: [Issue #6011](https://github.com/Hmbown/CodeWhale/issues/6011)
    - **重要性**: 社区对 Token 消耗的可观测性需求强烈。此 Issue 提案详细记录了每个组件、模型、工具调用的 Token 开销、缓存命中率及压缩成本，是开发者进行成本优化和性能调优的关键。

3.  **[bug] Google Gemini 在新安装环境下的配置问题**
    - **链接**: [Issue #6018](https://github.com/Hmbown/CodeWhale/issues/6018)
    - **重要性**（已关闭）: 用户报告在“从头开始”安装时，Google Gemini 模型无法正常工作。该问题已被认定为 Bug 并快速解决，反映了社区对新模型支持稳定性的高要求。

4.  **[bug] /models 命令无法完整获取模型列表（缺少分页支持）**
    - **链接**: [Issue #6009](https://github.com/Hmbown/CodeWhale/issues/6009)
    - **重要性**（已关闭）: 当使用 OpenAI 兼容的 API 时，`/models`命令只返回第一页结果。此 Bug 导致拥有大量模型的供应商无法被完全发现，是模型管理功能的基础缺陷。

5.  **[bug] 自动化面板中，已取消的运行任务不生成记录**
    - **链接**: [Issue #6162](https://github.com/Hmbown/CodeWhale/issues/6162)
    - **重要性**（已关闭）: 当自动化任务状态变为“已取消”时，系统不会生成任何完结记录（transcript receipt），导致用户无法追踪被取消的任务，这是一个严重的信息缺失问题。

6.  **[enhancement, release-blocker] Computer-use 插件：实时安装与首次交互循环**
    - **链接**: [Issue #5856](https://github.com/Hmbown/CodeWhale/issues/5856)
    - **重要性**: “Computer-Use”功能作为 Agent 能力的延伸，是社区关注的焦点。此 Issue 作为发布阻断项，旨在完成插件的实时安装体验和首次“看-动”（Look-act）循环的验证。

7.  **[enhancement] 可插拔的 Agent 记忆后端**
    - **链接**: [Issue #6050](https://github.com/Hmbown/CodeWhale/issues/6050)
    - **重要性**: 社区希望 Agent 的记忆不再局限于默认方案，能够通过通用接口接入如 `mem0` 等第三方记忆服务。这表明社区对 Agent 个性化和记忆能力的扩展性有强烈需求。

8.  **[enhancement] Fleet 模型管理：从提供商到角色分配**
    - **链接**: [Issue #5915](https://github.com/Hmbown/CodeWhale/issues/5915)
    - **重要性**: 此 Issue 源自创始人，是 CodeWhale Agent 功能（Fleet）的核心。它定义了如何为用户创建模型候选列表，并为子代理（sub-agents）分配角色，是构建多代理协作系统的关键一步。

9.  **[enhancement] TUI 会话选择器交互优化**
    - **链接**: [Issue #6014](https://github.com/Hmbown/CodeWhale/issues/6014)
    - **重要性**: 社区反馈 Session Picker 存在四个可用性问题（如无法隐藏空会话、列表无法翻页等）。这些看似微小的 UX 问题，直接影响用户日常使用体验。

10. **[bug] 终端作业控制失效：后台运行导致 TUI 挂起**
    - **链接**: [Issue #6169](https://github.com/Hmbown/CodeWhale/issues/6169)
    - **重要性**: 这是一个严重的稳定性 Bug。当 CodeWhale 的进程组被置于后台时，无法处理 `SIGTTIN` 信号，导致 TUI 挂起且终端模式无法恢复，是新手用户容易遇到的致命问题。

### **重要 PR 进展**
本期筛选了 10 个重要的 Pull Request：

1.  **[[CLOSED] v0.9.14: console-freeze, approval-death, compaction 等修复]**
    - **链接**: [PR #6161](https://github.com/Hmbown/CodeWhale/pull/6161)
    - **核心内容**: 正如“版本发布”所述，此 PR 合并了 v0.9.14 的所有关键修复，是社区过去 24 小时内最重要的合并。

2.  **[[CLOSED] feat(pet): 增加持久化世界与工作驱动点阵形态]**
    - **链接**: [PR #6110](https://github.com/Hmbown/CodeWhale/pull/6110)
    - **核心内容**: 为 CodeWhale 宠物引入了持久化的、跨平台的视听世界。宠物的形态会随着工作负载动态变化（如代码线、文件系统分支等），增强了产品的趣味性和沉浸感。

3.  **[[CLOSED] feat(tui): /pet 模式 — 宠物接管终端]**
    - **链接**: [PR #6154](https://github.com/Hmbown/CodeWhale/pull/6154)
    - **核心内容**: 实现 `/pet` 命令，允许宠物占据整个终端视图，并在对话时实时展示助手的回答或错误，交互完成后可通过 Escape 返回。

4.  **[[OPEN] feat(providers): 添加 AICraft OpenAI 兼容提供商模板]**
    - **链接**: [PR #6171](https://github.com/Hmbown/CodeWhale/pull/6171)
    - **核心内容**: 新增对 `aicraftapi.com` 的支持，只需简单配置模板即可使用。这体现了社区对第三方模型提供商接入的持续热情。

5.  **[[OPEN] fix(weixin-bridge): 修复微信桥，简化快速入门]**
    - **链接**: [PR #6170](https://github.com/Hmbown/CodeWhale/pull/6170)
    - **核心内容**: 修复了微信集成桥接器无法运行的文档和运行时问题，并简化了启动步骤。这对于中文社区开发者来说是一个积极的信号。

6.  **[[CLOSED] feat(config): 添加 [reasoning_only] 配置节]**
    - **链接**: [PR #5867](https://github.com/Hmbown/CodeWhale/pull/5867)
    - **核心内容**: 将原先硬编码的“仅推理”模式的重试次数（2次）开放给用户配置，提高了模型，特别是推理类模型的灵活性和可控性。

7.  **[[OPEN] Feat(tui): 为交互式工具审批提示添加超时功能]**
    - **链接**: [Issue #6101](https://github.com/Hmbown/CodeWhale/pull/6101) *(作者注：用户提供的数据中将此列为Issue，但此类通常也对应PR，根据上下文判断为功能性更改)*
    - **核心内容**: 为工具调用批准窗口添加了可选的超时和拒绝机制，防止任务因等待用户审批而无限阻塞。

8.  **[[OPEN] Build: 统一 JSON 和 nextest 命令的 Cargo 警告处理策略]**
    - **链接**: [Issue #6132](https://github.com/Hmbown/CodeWhale/pull/6132) *(同上)*
    - **核心内容**: 解决了 Cargo 在不同输出格式下对 `deny` 警告策略的处理不一致问题，这对于 CI/CD 的稳定性和代码质量至关重要。

9.  **[[CLOSED] [bug] 已取消的运行在自动化面板中静默消失]**
    - **链接**: [Issue #6147](https://github.com/Hmbown/CodeWhale/pull/6147) *(同上)*
    - **核心内容**: 修复了引擎中两个无界通道可能导致的无限内存增长问题，提升了系统的健壮性和抗压能力。

10. **[[OPEN] [dependencies] chore(deps): 更新 rustls 依赖]**
    - **链接**: [PR #6105](https://github.com/Hmbown/CodeWhale/pull/6105)
    - **核心内容**: 由 Dependabot 发起，将 TLS 库 `rustls` 从 0.23.43 更新至 0.23.44，旨在例行维护安全性和稳定性。

### **功能需求趋势**
从本周的 Issues 和 PR 中，可以明显看出社区关注点正在从基础的对话体验，向 **更高级、更自主的 Agent 能力** 和 **内部运维的可观测性** 转变。

1.  **Agent 与多代理协作 (Fleet & Sub-agents)**: 这是当前最明确的方向。围绕 `Fleet` 的模型管理、子代理的状态监控、以及 `Computer-Use` 插件的完善，是社区最热门的话题。
2.  **内部状态的可观测性**: 开发者不满足于黑盒运行。Token 用量的精确诊断（#6011）、自动化工作流的可视化（#5528）以及内存/性能的监控，成为开发者提升开发效率的关键。
3.  **“宠物”功能 (Dev UI / Gamification)**: `/pet` 模式和持久化宠物世界的引入，表明项目团队在探索将开发者工具游戏化，通过非侵入的交互提升使用体验。
4.  **插件化与外部集成**: 无论是插件化记忆后端（#6050）、微信桥接（#6170），还是对 AICraft 等第三方提供商的快速支持，都反映出社区希望 CodeWhale 能成为一个开放的平台。
5.  **健壮性与错误处理**: 大量关于“静默失败”、“任务取消无记录”和“终端冻结”的 Bug 修复，表明社区对软件的健壮性和稳定性的要求正在不断提高。

### **开发者关注点**
1.  **安装与兼容性痛点**：
    -   **Google Gemini 的兼容问题 (#6018)** 在“全新安装”时依然存在，对非 OpenAI 模型的支持稳定性是开发者选择模型时的最大顾虑。
    -   **终端控制与信号处理 (#6169)**：开发者需要 TUI 在后台运行时能优雅处理，而不是挂死整个终端。

2.  **信息可见性不足**：
    -   **数据可见性差**：`/models` 命令不全（#6009）、运行失败无提示（#5528）、Token 用量不透明（#6011）等，都指向一个共同的需求：**让用户能“看到”系统内部发生了什么**。

3.  **操作与交互困惑**：
    -   **`/hooks edit` 命令 (#6165)**：进入编辑器前未暂停 TUI 输入，导致按键分流，这是一个明显且影响高效的交互设计问题。
    -   **MCP OAuth 登录 (#6040)**：退出登录无法切换工作空间，这是一个账号管理上的严重逻辑缺陷。

4.  **文档与上手体验**：
    -   **微信桥接器的文档 (#6170)**：README 中的路径和操作说明完全是错误的，导致功能无法按文档使用。这提醒我们，即使是好的功能，如果文档跟不上，也会让开发者感到沮丧。

---
以上就是今天的日报内容。感谢各位开发者的阅读，我们明天见！

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*