# AI CLI 工具社区动态日报 2026-09-22

> 生成时间: 2026-09-22 01:08 UTC | 覆盖工具: 9 个

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

好的，作为专注于 AI 开发工具生态的资深技术分析师，我将基于您提供的 2026-09-22 社区动态摘要，为您生成一份横向对比分析报告。

---

## AI CLI 工具横向对比分析报告 | 2026-09-22

### 1. 生态全景

当前 AI CLI 工具市场正处于 **“能力扩张”与“成熟度阵痛”并存** 的高速发展期。一方面，所有主流工具都在积极构建 Agent 自主执行、多会话管理和插件生态等高级能力；另一方面，Windows 平台兼容性、成本控制透明度、以及 Agent 在长时间或复杂任务下的稳定性，成为社区普遍抱怨的“阿喀琉斯之踵”。整体来看，市场已经跨越了“演示可用”阶段，正进入一个考验产品 **健壮性、可负担性和跨平台体验** 的关键竞争周期。

### 2. 各工具活跃度对比

| 工具名称 | 热点 Issues (Top 10) | 重要 PRs (Top 10) | 版本发布 (24h) | 社区热度 (赞/评论综合) | 定性评价 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 10 | 2 | 0 | 高 (59赞领衔) | 社区成熟，但项目管理和Windows体验是剧痛。 |
| **OpenAI Codex** | 10 | 10 | 7 | 高 (67赞方向) | 迭代极快，但计费/速率限制和Windows问题频发。 |
| **Gemini CLI** | 10 | 10 | 1 (nightly) | 中高 | Agent 稳定性是核心焦点，正在努力打磨底层。 |
| **GitHub Copilot CLI** | 10 | 2 | 2 (补丁) | 中高 (16赞模型池) | 企业级特性与稳定性并重，OOM是最大隐患。 |
| **Kimi Code CLI** | 2 (迁移通知) | 3 | 1 (最终版) | 低 (已归档) | **生命周期终结**，社区关注度已迁移至新项目。 |
| **OpenCode** | 10 | 10 | 1 (紧急修复) | 高 (47赞Bug回归) | 社区活跃且反应迅速，但版本回归和计费问题是短板。 |
| **Pi** | 10 | 10 | 1 (v0.87.0) | 中 | 功能性强，但版本回归、性能问题及文档不一致是痛点。 |
| **Qwen Code** | 10 | 10 | 3 (多项目) | 中 | 功能发展均衡，但macOS终端和Remote-SSH问题是拦路虎。 |
| **DeepSeek TUI** | 10 | 10 | 0 | 中 | 激进创新，但CI极不稳定，开发状态偏早期。 |

**分析**：OpenAI Codex 的发布频率最高，显示出最激进的迭代节奏。Claude Code 和 OpenCode 社区反馈最激烈，Bug 和特性需求的 “点赞数”极高。Gemini CLI、Pi 和 Qwen Code 的 PR 数量多，说明开发团队在积极解决社区反馈的问题。Kimi Code CLI 则是一个独特的“终点”信号。

### 3. 共同关注的功能方向

以下是多个工具社区都在强烈关注的需求，表明了行业共性痛点：

1.  **成本控制与透明度**：
    - **涉及工具**: **Claude Code** (#95313, #94013), **OpenAI Codex** (#42987, #40880), **OpenCode** (#50093, #50452)。
    - **具体诉求**: 用户普遍要求对 Agent 的 Token 消耗、调用次数进行限制和预警，并希望看到更清晰的成本使用报告。

2.  **Agent 稳定性与行为可控性**：
    - **涉及工具**: **Gemini CLI** (#21409, #22323), **Claude Code** (#94013), **DeepSeek TUI** (#6184), **OpenCode** (#48811)。
    - **具体诉求**: 子 Agent 误报状态（成功/失败）、主 Agent 执行中途无响应（挂起）、或在无用户确认下执行高消耗操作，是普遍痛点。

3.  **跨平台兼容性**：
    - **涉及工具**: **Claude Code** (#45297, #93071), **OpenAI Codex** (#42739, #46613), **Qwen Code** (#11872, #12414), **Gemini CLI** (#21983)。
    - **具体诉求**: Windows 上的路径问题（UNC）、沙箱兼容性、应用稳定性；Linux 上的特定显示协议（如 Wayland）支持是主要短板。

4.  **用户界面与交互体验**：
    - **涉及工具**: **Claude Code** (#79305), **OpenCode** (#50387, #42264), **Qwen Code** (#12406), **GitHub Copilot CLI** (#3704)。
    - **具体诉求**: 支持自定义主题、改善国际化（如RTL语言、多语言摘要）、优化终端渲染性能、修复流式输出时的文本错误。

### 4. 差异化定位分析

| 分析维度 | Claude Code / GitHub Copilot | OpenAI Codex | Gemini CLI | Qwen Code / DeepSeek TUI | Pi | OpenCode | Kimi Code CLI |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **核心优势** | **生态深度**：背靠母公司强大的模型和开发者工具生态。 | **迭代速度**：功能更新极快，追求前沿能力。 | **Agent框架创新**：强调模型“原生”能力（如bash），追求零依赖。 | **开源与定制化**：满足特定模型、特定场景需求。 | **扩展性与可编程性**：强大的Hook系统和RPC接口。 | **开源社区驱动**：社区参与度高，修复迅速。 | **产品转型**：从失败的Python版转型至原生二进制。 |
| **目标用户** | 重度使用母公司生态的企业和开发者。 | 追求最新模型和功能的尝鲜者、高频用户。 | 技术栈偏好Google、Linux的底层开发者。 | 深度使用者、特定模型（如Qwen）爱好者、二次开发者。 | 插件开发者、对可控性要求极高的高级用户。 | 成本敏感、偏好开源、社区参与度高的开发者。 | 原Kimi CLI用户，关注下一代产品。 |
| **技术路线** | **托管服务与强身份绑定**。 | **强客户端，快速迭代**。 | **Agent优先，原生能力**。 | **功能均衡，社区驱动**。 | **可扩展的模块化架构**。 | **社区驱动，快速修复**。 | **彻底重写，技术升级**。 |
| **主要短板** | 成本失控风险、Windows体验差、项目管理透明度。 | 计费系统不稳定、Windows稳定性差、速率限制不清晰。 | Agent稳定性不足、子Agent成为黑盒、功能开发生态弱。 | 跨平台兼容性问题（macOS终端、Windows构建）。 | 版本回归频发、学习曲线陡峭、文档一致性。 | 计费系统混乱、回归Bug、跨端同步差。 | 旧版本停止维护，迁移路径不完备。 |

### 5. 社区热度与成熟度

- **最成熟 & 社区影响力最大**: **Claude Code** 和 **GitHub Copilot CLI**。它们的社区反馈体现了其庞大的用户基础，问题也更具代表性（如企业级的策略管理和成本控制）。Bug #87647 (6000+ issue被自动关闭) 揭示了项目管理上的挑战，但这本身就是规模庞大的体现。
- **快速迭代 & 社区活跃**: **OpenAI Codex** 和 **Gemini CLI**。发布频率高，社区反馈热烈，但问题也集中在核心稳定性上，表明产品处于从“能用”到“好用”的冲刺阶段。
- **特定场景深耕**: **Pi** 和 **OpenCode**。在可扩展性和社区驱动方面展现出独特优势，但社区规模较小，且问题集中在“高级用户”才会遇到的场景（如RPC集成、扩展开发）。
- **早期成长 & 挑战**: **Qwen Code** 和 **DeepSeek TUI**。社区热情高，功能探索积极，但CI/稳定性基础设施相对薄弱（如DeepSeek 81.5%的CI失败率），表明产品成熟度有待提升。
- **生命周期终结**: **Kimi Code CLI**。这是一个重要的行业信号，表明在激烈竞争中，产品架构可能成为被淘汰的决定性因素。

### 6. 值得关注的趋势信号

1.  **Agent 与成本的“新博弈”**：开发者对于Agent自主性的迷恋正在被“失控成本”的恐惧所平衡。Claude Code和OpenAI Codex社区对成本透明度的强烈呼声，预示着未来 **“成本可控”将成为AI CLI工具的核心竞争力**，甚至比功能多少更重要。
2.  **“胖客户端”的隐患**：多起OOM崩溃（如Copilot CLI #4699）和长会话性能下降，揭示了当前以本地桌面应用为主的架构在处理大规模上下文时的瓶颈。未来可能会出现更多 **“云端推理+本地轻量端”** 的混合架构，或将上下文状态持久化到云端以释放本地内存。
3.  **平台适配决定用户选择**：Windows和Linux（特别是Wayland）的兼容性问题，不再是“小问题”，而是成为用户 **选型时的否决项**。那些能提供稳定、一致跨平台体验的工具（如通过强大的Web终端或原生沙箱）将获得巨大优势。
4.  **记忆系统将成为下一个战场**：Gemini CLI和DeepSeek TUI等社区对“Agent记忆”功能的讨论，表明行业正从“单次会话助手”向“长期工作伙伴”演进。谁先能提供 **安全、高效、可检索** 的跨会话记忆功能，谁就能在用户体验上建立壁垒。
5.  **“企业级”需求已下沉**：对策略管理（Copilot CLI）、OAuth授权（Kimi Code/Pi）、持久化凭证和MITM代理（OpenAI Codex）的需求，已从大企业渗透到独立开发者和小团队。这表明AI CLI工具正成为 **日常开发基础设施**，必须补齐安全和合规的短板。

---

**总结建议**：对于技术决策者，如果您追求稳定和企业级体验，可优先关注 **GitHub Copilot CLI** 的演进；若团队对成本敏感且喜欢快速迭代，**OpenCode** 社区驱动模式值得关注；如果您是重度Google/Android开发者，**Gemini CLI** 的潜力不可忽视，但需评估其当前稳定性。对于普通开发者，短期内需警惕 **Agent 的成本黑洞**，并确保所选工具在您的主力开发平台上能稳定运行。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，作为专注于 Claude Code 生态的技术分析师，我已审阅截至 **2026-09-22** 的 `anthropics/skills` 仓库数据。以下是为您生成的社区热点报告。

---

### Claude Code Skills 社区热点报告（数据截止：2026-09-22）

#### 1. 热门 Skills 排行

基于评论活跃度、讨论深度及社区影响力，以下是当前最受关注的 Skills（PR）：

*   **#1298: `skill-creator` 修复：隔离触发评估、处理 Windows 兼容性与运行时故障**
    *   **功能**：核心元技能，修复 `skill-creator` 在评估技能触发条件时的关键缺陷，包括跨进程竞争、Windows 管道兼容性及运行时错误导致的误报问题。
    *   **社区热点**：讨论集中在技能创建的**可靠性**上。社区高度关注如何使技能触发评估更加精准，避免因环境差异或执行错误导致技能无效，这是整个技能生态健壮性的基石。
    *   **状态**: **Open**（讨论度极高，长期关注）
    *   **链接**: `github.com/anthropics/skills/pull/1298`

*   **#1771: `proofcore-contract-auditor`：智能合约公证审计技能**
    *   **功能**：面向 Web3 开发者，提供针对 Solidity 和 Rust 智能合约的自动化静态分析，并将审计证明锚定到 TON 区块链。
    *   **社区热点**：这是 Web3 与 AI 结合的典型案例。社区讨论聚焦于**去中心化安全审计**的可行性，以及将 AI 分析结果与区块链不可篡改特性结合的创新模式。
    *   **状态**: **Open**（新晋热门，领域创新度高）
    *   **链接**: `github.com/anthropics/skills/pull/1771`

*   **#525: `pyxel`：复古游戏开发技能**
    *   **功能**：为使用 Pyxel 引擎进行复古风格 Python 游戏开发提供全流程支持，包括创建、调试、无头运行和状态验证。
    *   **社区热点**：聚集了大量**游戏开发者**和创意编程爱好者。讨论重点在于如何通过 Skill 实现更流畅的游戏 AI 开发体验，以及对非业务场景的探索价值。
    *   **状态**: **Open**（长期活跃，受众广泛）
    *   **链接**: `github.com/anthropics/skills/pull/525`

*   **#822: `AWT (AI Watch Tester)`：AI 驱动的端到端测试技能**
    *   **功能**：引入开源工具 AWT，赋予 Claude 浏览器视觉和控制能力，实现零代码、AI 驱动的 E2E 测试。
    *   **社区热点**：代表了**AI 自动化测试**的前沿方向。讨论围绕“AI 代理+视觉理解”的测试模式展开，被视为传统自动化测试框架的潜在颠覆者。
    *   **状态**: **Open**（技术方向激进，讨论热烈）
    *   **链接**: `github.com/anthropics/skills/pull/822`

*   **#83: `skill-quality-analyzer` 与 `skill-security-analyzer`：元技能分析器**
    *   **功能**：添加两个元技能，从结构、文档、安全等多个维度对 Claude Skills 本身进行质量评估和安全审查。
    *   **社区热点**：这体现了社区的**“吃自己的狗粮”**趋势。开发者开始思考如何系统化地保证技能本身的质量、安全性和合规性，这对于建立成熟的技能市场至关重要。
    *   **状态**: **Open**（理念先进，具有生态价值）
    *   **链接**: `github.com/anthropics/skills/pull/83`

*   **#514: `document-typography`：文档排版质量控制技能**
    *   **功能**：专门解决 AI 生成文档中的常见排版问题，如孤行、寡段、编号错位等。
    *   **社区热点**：直击**AI 生成内容的“最后一公里”**痛点。用户普遍反映虽然内容生成得好，但格式细节欠佳，该技能精准满足了高质量文档输出的迫切需求。
    *   **状态**: **Open**（需求明确，实用性强）
    *   **链接**: `github.com/anthropics/skills/pull/514`

#### 2. 社区需求趋势

从 Issues 反馈中，可以清晰地看到社区对以下方向抱有强烈期待：

*   **安全与信任（最高优先级）**：Issue #492 关于社区技能被分发在 `anthropic/` 官方命名空间下的安全讨论获得了最多评论（43条）。这反映了社区对 **信任边界** 问题的深刻担忧，用户迫切需要清晰的官方/社区技能划分、审核机制和权限管控。
*   **组织级协作与共享**：Issue #228 要求实现组织级的技能库或直接分享链接。这表明 Skills 正从个人工具向 **企业级协作资产** 演进，用户不再满足于本地文件传输的低效模式。
*   **技能工具链优化**：Issue #556 报告 `run_eval.py` 评估脚本存在 0% 触发率的严重问题，这与 PR #1298 的修复目标一致。这揭示了社区对 **技能开发和测试工具链** 稳定性的强烈需求，这是技能生态健康发展的基础设施。
*   **效率与资源节约**：Issue #1329 提出的 `compact-memory` 技能想法，体现了用户对 **上下文窗口优化** 的关注。社区期望有更高效的机制来管理 Agent 的长时记忆和状态，以降低 Token 消耗并提升性能。
*   **特定领域深化**：除了泛化需求，社区也积极贡献特定领域的专业技能，如智能合约审计（#1771）、HPC 集群操作（#1615）等，显示出社区正朝着 **垂直场景精细化** 的方向发展。

#### 3. 高潜力待合并 Skills

以下 PR 评论活跃，尚未合并，具有较高落地价值，值得关注：

*   **#1771: `proofcore-contract-auditor`**：如之前介绍，Web3 安全方向热度高，创新性强，有较大的潜在用户群。
*   **#525: `pyxel` 游戏开发**：作为创意和技术结合的代表，需求持续存在，PR 历史悠久，社区维护良好，合并可能性高。
*   **#822: `AWT` 端到端测试**：代表了 AI 代理自动化测试的前沿，如果能解决稳定性和集成问题，将极具颠覆性。
*   **#1703: `md2video-audio`**：将 Markdown 一键转化为带配音的视频，精准满足了内容创作者和教育工作者对**内容多格式分发**的需求，市场需求明确。
*   **#723: `testing-patterns`**：作为技能生态中的“最佳实践”类技能，覆盖全栈测试，具有很高的教育意义和实用价值，合并后能迅速提升开发者编写高质量测试的能力。

#### 4. Skills 生态洞察

**一句话总结**：当前社区最集中的诉求是**构建一个安全可信、易于分享且开发工具链可靠的高质量 Skills 生态系统**，而非单纯追求技能数量的增长。用户正从尝鲜期进入精耕期，对技能的**“信任”、“效率”和“品质”**提出了更高要求。

---

好的，这是为您生成的 2026 年 9 月 22 日 Claude Code 社区动态日报。

---

# Claude Code 社区动态日报 | 2026-09-22

## 今日速览

Claude Code 社区今日热度集中在 **Windows 平台兼容性**与**成本控制**两个方向。几个高关注度的 Bug 揭示了 Cowork 功能在 Windows 上存在严重的文件路径与沙箱问题，同时社区对背景子代理（Subagent）无限制消耗 Token 的担忧日益增长。此外，一个关于**自动关闭 Issue** 的讨论引发了社区对项目维护规范的质疑。

## 社区热点 Issues

1.  **[BUG] Cowork: Folder does not support UNC under Windows** (#45297)
    - **重要性**: 该 Issue 是 Windows 用户使用 Cowork（协作）功能的核心障碍。UNC 路径是 Windows 网络中共享文件夹的常用方式，该问题导致大量企业用户在协作场景下无法正常工作。
    - **社区反应**: 29 条评论，30 个赞。评论数高企，说明此问题已影响众多用户，且长期未解决。用户 mrsilva 提交后多次被更新，显示了用户对其修复的持续关注。
    - **链接**: [Issue #45297](https://github.com/anthropics/claude-code/issues/45297)

2.  **[BUG] macOS sandbox unusable: Seatbelt profile... exceeds ARG_MAX** (#73468)
    - **重要性**: 这是 macOS 平台的一个严重 Bug。当用户项目包含大量 Git 工作树时，沙箱会因参数列表过长完全崩溃，导致 `/bin/zsh` 等基础命令都无法运行。这对于依赖沙箱进行安全隔离的开发者是致命缺陷。
    - **社区反应**: 虽已标记为 CLOSED，但获得了 11 条评论和 6 个赞，表明该问题在修复前已对许多 macOS 用户造成了困扰。
    - **链接**: [Issue #73468](https://github.com/anthropics/claude-code/issues/73468)

3.  **[BUG] Over 6k issues labeled with "has repro" have been auto-closed** (#87647)
    - **重要性**: 该 Issue 揭示了项目管理层面的潜在问题。大量（超过 6000 个）标记了“有复现方法”的 Bug 被自动关闭，可能意味着社区的 Bug 反馈并未被有效处理和追踪，这严重影响了开发者对项目的信任。
    - **社区反应**: 8 条评论，但获得了惊人的 **59 个赞**，是本期点赞数最高的 Issue。这强烈反映了社区对此现象的不满和担忧。
    - **链接**: [Issue #87647](https://github.com/anthropics/claude-code/issues/87647)

4.  **[FEATURE] Request: Require user confirmation before spawning expensive agents** (#95313)
    - **重要性**: 成本控制是用户的核心痛点之一。此 Issue 建议在启动可能产生高成本的“代理”任务前强制用户确认，以防止意外消费。这直接关系到用户的财务安全。
    - **社区反应**: 新 Issue，6 条评论。虽然点赞数不高，但 2026 年 9 月 18 日刚提出，讨论热度正在上升。
    - **链接**: [Issue #95313](https://github.com/anthropics/claude-code/issues/95313)

5.  **[BUG] Cowork Windows 10... no Plan9 drive shares mounted** (#93071)
    - **重要性**: 这是 Windows 10 上 Cowork 功能的另一个严重问题。`device_bash` 功能完全失效，导致 Cowork 的远程执行能力瘫痪。用户表明问题持久存在，更新重启均无法解决。
    - **社区反应**: 7 条评论。反映出 Windows 用户在协作体验上持续受挫。
    - **链接**: [Issue #93071](https://github.com/anthropics/claude-code/issues/93071)

6.  **[ENHANCEMENT] Desktop app: support custom themes / accent colors** (#79305)
    - **重要性**: 用户界面个性化需求。该 Issue 提出，当用户在多台显示器上同时使用多个现代暗色应用时，难以区分哪个窗口是 Claude Desktop。
    - **社区反应**: 9 条评论，19 个赞。赞数很高，说明大量用户渴望拥有自定义主题或强调色来提高窗口识别度和使用体验。
    - **链接**: [Issue #79305](https://github.com/anthropics/claude-code/issues/79305)

7.  **[ENHANCEMENT] statusline: expose per-model weekly rate limits** (#73770)
    - **重要性**: 开发者希望实时查看不同模型（Opus/Sonnet/Fable）的周速率限制，以更好地规划使用和避免中断。
    - **社区反应**: 6 条评论，18 个赞。赞数说明这是一个普遍需求，开发者希望在状态行直接获取细粒度的额度信息。
    - **链接**: [Issue #73770](https://github.com/anthropics/claude-code/issues/73770)

8.  **[BUG] Background subagents have no token, turn or time cap** (#94013)
    - **重要性**: 与 #95313 类似，是成本控制的重磅炸弹。此报告指出后台启动的研究型子代理在无任何费用限制和用户确认的情况下，消耗了 170 万 Token，这击中了开发者对成本失控的恐惧。
    - **社区反应**: 3 条评论。作为一个近期报告，其内容直指 Agent 架构的潜在危险。
    - **链接**: [Issue #94013](https://github.com/anthropics/claude-code/issues/94013)

9.  **[BUG] Desktop built-in browser can't grant standing permissions for .local hosts** (#94830)
    - **重要性**: 对于使用本地开发环境（如 WordPress Studio）的用户是阻碍性问题。每次浏览器操作都需要手动授权，严重破坏了工作流。
    - **社区反应**: 5 条评论，5 个赞。痛点明确，影响本地 Web 开发者的效率。
    - **链接**: [Issue #94830](https://github.com/anthropics/claude-code/issues/94830)

10. **[BUG] VS Code extension: @-mention file picker only searches the first folder of a multi-root workspace** (#87827)
    - **重要性**: 这是一个开发者体验问题。在 VS Code 多根工作区环境下，`@`提及文件选择器只能搜索第一个文件夹，导致无法快速引用其他项目文件。
    - **社区反应**: 已关闭，2 条评论。虽然已关闭，但对于使用多仓库工作区的 VS Code 用户来说，这是个影响较大的问题。
    - **链接**: [Issue #87827](https://github.com/anthropics/claude-code/issues/87827)

## 重要 PR 进展

1.  **Add issue template for GitHub connection problems** (#95932)
    - **功能**: 为 `claude.ai` 的 GitHub 连接问题新增了一个 Issue 表单模板，便于用户提交结构化的问题报告。
    - **链接**: [PR #95932](https://github.com/anthropics/claude-code/pull/95932)

2.  **diff: a shell command the tool held read-only fetches nothing** (#95423)
    - **功能**: 优化 `diff` 工具的刷新逻辑。之前，任何 Bash 或 PowerShell 工具调用后，`diff` 都会重新获取差异。此 PR 使其仅在可能修改文件的命令执行后才刷新，对于 `ls`、`cat` 等只读命令则跳过，从而提升性能。
    - **链接**: [PR #95423](https://github.com/anthropics/claude-code/pull/95423)

## 功能需求趋势

1.  **成本透明与管控**: 社区强烈要求更好地控制和了解 AI 成本。具体表现为：
    - 在状态行显示**每个模型的速率限制** (#73770)。
    - 在启动高成本 Agent 前**强制用户确认** (#95313)。
    - 为后台子代理设置**Token/时间/轮次上限** (#94013)。
2.  **桌面应用 UI/UX 增强**:
    - 支持**自定义主题/强调色**以避免窗口混淆 (#79305)。
    - 支持**拼写检查的多种语言** (#88502)。
    - 提供**讨论模式**，即只读会话，支持导出文件 (#85848)。
3.  **Windows 与跨平台支持**:
    - 全面解决 Windows 上 Cowork 功能的 **UNC 路径 (#45297)** 和 **Plan9 挂载 (#93071)** 问题。
    - 改进 WSL 环境下 Git 工作树与沙箱的兼容性 (#78818)。
4.  **权限与安全**: 除了成本，用户还关注对 Agent 行为的控制，例如要求对本地 `.local` 域名进行**持久授权** (#94830)，以及在**非交互式环境**（如 CI）中实现设计系统的授权 (#91063)。

## 开发者关注点

- **Windows 用户体验是重灾区**: 多个高热度 Issue 指向 Windows 平台，特别是 Cowork 和沙箱功能存在严重 Bug，影响了大量 Windows 开发者的正常使用。
- **对“运行成本”的焦虑蔓延**: 从 `background subagents` 到 `expensive agents`，开发者越来越担心 AI 使用过程中的不可控开销，社区正积极寻找成本可视化和控制的手段。
- **社区-项目管理信任度**: Issue #87647 揭示了大量 Bug 被自动关闭的现象，这可能会削弱开发者提交有效 Bug 报告的积极性，并引发对项目维护透明度和严谨性的质疑。
- **细节体验亟待打磨**: 从 “CJK 复制乱码” (#66269) 到 “快速双 Esc 清空输入” (#87631)，再到 “Agent 回复中的有序列表自动重编号” (#87790)，这些细节问题虽然不致命，但持续磨损着用户的使用体验。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报  
**2026-09-22** | 数据来源：github.com/openai/codex

---

## 今日速览

- **一天之内密集发布了 7 个 Rust 版本**（v0.155~v0.157），代码库进入快速迭代周期。
- **GPT-6 Astra 配额消耗异常** 成为社区最热议题，多位 Plus 用户反馈 5 小时限额在几分钟内耗尽，引发对计费与速率限制机制的广泛讨论。
- **Windows 桌面端稳定性告急**：登录卡死、项目丢失、应用崩溃等问题密集出现，共涉及超过 10 个 Windows 专属 issue。

---

## 版本发布

过去 24 小时共发布 7 个 Rust 预发布版本：

| 版本 | 链接 |
|------|------|
| v0.157.0-alpha.2 | [Release](https://github.com/openai/codex/releases/tag/rust-v0.157.0-alpha.2) |
| v0.157.0-alpha.1 | [Release](https://github.com/openai/codex/releases/tag/rust-v0.157.0-alpha.1) |
| v0.156.0-alpha.17 | [Release](https://github.com/openai/codex/releases/tag/rust-v0.156.0-alpha.17) |
| v0.156.0-alpha.16 | [Release](https://github.com/openai/codex/releases/tag/rust-v0.156.0-alpha.16) |
| v0.156.0-alpha.14 | [Release](https://github.com/openai/codex/releases/tag/rust-v0.156.0-alpha.14) |
| v0.156.0-alpha.13 | [Release](https://github.com/openai/codex/releases/tag/rust-v0.156.0-alpha.13) |
| v0.155.0-alpha.16.1 | [Release](https://github.com/openai/codex/releases/tag/rust-v0.155.0-alpha.16.1) |

版本变更日志未随数据提供，但从 PR 看近期涉及工具定义、代理配置、UI 行为修复等，可推测 v0.157 侧重稳定性与终端体验改进。

---

## 社区热点 Issues（10 条）

1. **#42987：GPT-6 Astra 耗尽全部 5 小时配额**  
   👤 GustavoMartins123 | 👍15 | 💬 26  
   核心问题：在 Codex 中使用 GPT-6 Astra（Medium 推理量）仅进行两次简短的交互，就消耗了 Plus 账户全部的 5 小时配额。社区反响强烈，怀疑新模型的计算单位换算或循环次数控制存在 bug。  
   [Issue](https://github.com/openai/codex/issues/42987)

2. **#40880：重新引入后 5 小时消耗速度显著加快**  
   👤 Damien-zeze | 👍3 | 💬 11  
   同样指向速率限制问题：用户报告在 v0.149.1 中使用 gpt-5.6-sol 时，额度消耗速度比之前明显更快，可能与后端计费参数变更有关。  
   [Issue](https://github.com/openai/codex/issues/40880)

3. **#42739：Windows 更新后本地项目从侧边栏消失**  
   👤 rizal281065 | 💬 22  
   用户更新 Codex/ChatGPT 桌面应用后，“Projects”列表显示为空，但本地文件和聊天记录仍在。Windows 专属 bug，影响开发流程。  
   [Issue](https://github.com/openai/codex/issues/42739)

4. **#39178：隐藏的 avatarOverlay 导致线程卡在“Thinking”**  
   👤 zgl-gits | 💬 11  
   Windows 端 UI 渲染 bug：当线程实际已完成时，由于隐藏的 avatar overlay 占据了会话所有权，主界面始终显示“Thinking”，无法展示结果。  
   [Issue](https://github.com/openai/codex/issues/39178)

5. **#46613：Windows 桌面端卡在“无法加载登录需求”**  
   👤 Cyril6666 | 👍1 | 💬 9  
   从 Microsoft Store 重新安装后，应用无法跳过登录需求检测，完全不可用。认证流程 bug。  
   [Issue](https://github.com/openai/codex/issues/46613)

6. **#31864：所有 GPT-5.6 Sol 会话因保留工具名失败**  
   👤 spadaval | 👍18 | 💬 8  
   调用 `collaboration.spawn_agent` 时，MultiAgentV2 使用该保留函数名导致每次请求都报错。影响多代理工作流，社区关注度高。  
   [Issue](https://github.com/openai/codex/issues/31864)

7. **#44363：上下文压缩永久破坏对话记录**  
   👤 noclascio | 💬 7  
   Pro 用户发现，Codex 的上下文压缩功能会原地重写存储的 rollout，导致原始对话记录完全丢失。数据安全严重隐患。  
   [Issue](https://github.com/openai/codex/issues/44363)

8. **#47138：Windows 应用因 `net::ERR_BLOCKED_BY_CLIENT` 无法启动**  
   👤 amanannn | 💬 2  
   最新版本 26.915.4065.0 在启动更新检查时被客户端网络拦截，应用直接退出。影响所有 Plus 用户。  
   [Issue](https://github.com/openai/codex/issues/47138)

9. **#47133：Windows 上 Codex 选择器不可点击**  
   👤 efratgez | 💬 2  
   顶部 Codex 选择区域被当作标题栏处理，双击还会最大化窗口。UI 交互 bug。  
   [Issue](https://github.com/openai/codex/issues/47133)

10. **#18115：仓库级插件与市场配置**  
    👤 yshrsmz | 👍67 | 💬 16  
    社区呼声最高的增强请求：要求 Codex 支持在项目配置文件（`.codex/config.toml`）中定义本地插件市场，实现团队共享插件配置，目前仍全用户范围。  
    [Issue](https://github.com/openai/codex/issues/18115)

---

## 重要 PR 进展（10 条）

1. **#47143：提取 exec-server CLI 启动至独立模块**  
   🚀 重构 `codex exec-server` 启动逻辑，将参数解析、传输验证、配置加载等从 `main.rs` 移至 `exec_server_command.rs`，提升可维护性。  
   [PR](https://github.com/openai/codex/pull/47143)

2. **#47142：独立 Web 搜索支持系统代理设置**  
   🔧 修复独立 Web 搜索功能始终绕过系统代理的问题，现在会使用配置的 `HttpClientFactory` 创建客户端。  
   [PR](https://github.com/openai/codex/pull/47142)

3. **#47137：阻止水平选择触发自动滚动**  
   🐛 修复横向拖动选择文本时导致自动滚动的 bug，现在要求垂直移动才触发滚动。提升选择体验。  
   [PR](https://github.com/openai/codex/pull/47137)

4. **#47132：网络代理支持调用方提供的 MITM CA**  
   🔐 新增可选配置 `network.mitm_ca`，允许用户指定证书文件和私钥，用于受信任代理场景。  
   [PR](https://github.com/openai/codex/pull/47132)

5. **#47130：移除 gpt-5.6-sol 的 `ultrafast` 服务等级**  
   🧹 从模型服务等级中删除 `ultrafast`，仅保留 `priority`（Fast）。可能统一计费标准或优化调度。  
   [PR](https://github.com/openai/codex/pull/47130)

6. **#47129：保留扩展工具环境中的外部工作目录**  
   🛠 修复扩展调用时，若工作目录无法转为宿主路径则被丢弃的问题。现在存储为 `PathUri` 保持完整传递。  
   [PR](https://github.com/openai/codex/pull/47129)

7. **#47125：为 Guardian 审核添加额外策略配置**  
   📋 新增 `auto_review.extra_policy` 字段，允许用户提供额外策略文本，与租户策略叠加生效。  
   [PR](https://github.com/openai/codex/pull/47125)

8. **#47122：将 OpenAPI 文件 blob 上传超时从 60 秒提升至 5 分钟**  
   ⏱ 解决大文件上传频繁超时问题，特别影响附件和媒体内容。  
   [PR](https://github.com/openai/codex/pull/47122)

9. **#47121：向附件上传传递线程 ID**  
   🔗 在 `UploadRequest` 中新增 `thread_id`，支持基于线程的附件放置逻辑。  
   [PR](https://github.com/openai/codex/pull/47121)

10. **#47118：Code Mode 工具消息支持模型目录覆盖**  
    🧠 允许通过模型目录（model catalog）覆盖 Code Mode 中 `exec`、`wait` 等工具的系统提示消息，增强模型行为可定制性。  
    [PR](https://github.com/openai/codex/pull/47118)

---

## 功能需求趋势

从过去 24 小时更新的 Issues 中，社区关注的功能方向集中在：

- **可扩展性与团队协作**：仓库级插件/市场配置（#18115，👍67）、本地密钥管理（#22029）是呼声最高的增强请求。
- **配额与任务连续性**：自动在 5 小时限额重置后恢复任务（#28931，👍35）成为高频诉求。
- **UI/UX 改进**：默认展开工具调用摘要（#23868，👍15）、TUI 提示常驻（#47096 等相关 PR）。
- **平台覆盖均衡**：Linux 桌面端缺少 /compact 等命令（#39343）、键盘输入失效（#45098），反映多平台功能不对称。
- **安全与代理**：MITM CA 支持（#47132）、MCP OAuth 凭据持久化（#28201）表明企业级安全配置需求上升。

---

## 开发者关注点

**高频痛点汇总：**
- **速率限制与计费**：GPT-6 Astra 和 GPT-5.6 Sol 均出现额度消耗异常，社区怀疑后端存在超额计费或循环计算 bug，涉及 #42987、#40880。
- **Windows 桌面端稳定性**：更新后项目丢失、登录卡死、标题栏误判、浏览器崩溃等 bug 大量出现（#42739、#46613、#47133、#46767），影响日常使用。
- **数据安全**：上下文压缩破坏对话记录（#44363）、远程编译超大数据导致 session 不可恢复（#24191、#30932），丢失工作成果的风险高。
- **多代理兼容性问题**：保留工具名冲突（#31864）使 GPT-5.6 Sol 的 multi-agent 功能彻底失效，影响高级工作流。
- **Linux 下 MCP 文件描述符泄露**（#46960）：生产环境下的潜在资源攻击面。

**开发者建议：**  
近期关注 Windows 应用更新节奏，建议在生产环境等待修复版本；对于大任务，注意手动备份会话 JSONL；如使用多代理功能，暂时回退到非 Sol 模型。

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，我根据您提供的 GitHub 数据，为您生成 2026 年 9 月 22 日的 Gemini CLI 社区动态日报。

---

## Gemini CLI 社区动态日报 | 2026-09-22

### 📈 今日速览

- **版本迭代**：昨日发布了 `v0.62.0-nightly.20260921` 夜间构建版本，持续滚动更新。
- **核心焦点**：社区热度集中在 **Agent 自主性与稳定性** 上，多个高优先级问题正在处理，包括子 Agent 中断报告错误、通用 Agent 无响应、以及 Agent 在特定环境下的功能失灵。
- **开发动态**：大量 PR 正在解决多个关键稳定性问题，例如文件写入原子性、代理配置兼容性、终端交互卡死等，显示出团队正在积极打磨 CLI 的底层健壮性。

---

### 🚀 版本发布

- **[v0.62.0-nightly.20260921.gcfbcaa8df](https://github.com/google-gemini/gemini-cli/releases/tag/v0.62.0-nightly.20260921.gcfbcaa8df)**
  发布了最新的夜间构建版本，包含最新的代码变更和潜在的 bug 修复。详细变更可查看[完整更新日志](https://github.com/google-gemini/gemini-cli/compare/v0.62.0-nightly.20260920.gcfbcaa8df...v0.62.0-nightly.20260921.gcfbcaa8df)。

---

### 🔥 社区热点 Issues

1. **[#22323] [BUG] 子 Agent 在达到最大轮次后误报为“成功”** [🔒]
   - **重要性**：高优先级、涉及核心逻辑错误。子 Agent `codebase_investigator` 在因达到最大运行轮次而被中断时，却向上级报告 `status: "success"`，可能导致用户基于错误的成功信号做出决策。
   - **社区反应**：有 13 条评论，社区和开发者正在深入讨论。
   - **链接**：[Issue #22323](https://github.com/google-gemini/gemini-cli/issues/22323)

2. **[#21409] [BUG] 通用 Agent 在任务执行时“挂起”** [🔒]
   - **重要性**：高优先级、严重影响用户体验。用户报告 `gemini-cli` 在将任务交给通用 Agent 时会无限期挂起，即使是最简单的建文件夹操作也会失败。
   - **社区反应**：获得 8 个 👍，8 条评论，多位用户确认遇到此问题。一个已知的临时解决方案是手动指示模型不要使用子 Agent。
   - **链接**：[Issue #21409](https://github.com/google-gemini/gemini-cli/issues/21409)

3. **[#21968] [BUG] Gemini 未能充分利用自定义技能和子 Agent** [🔒]
   - **重要性**：揭示了 Agent 框架的一个核心缺陷：模型无法主动、智能地选择和调用已配置的技能和子 Agent，即使任务与技能描述高度相关。
   - **社区反应**：6 条评论，开发者正在探讨如何改进模型的自我意识和工具调度能力。
   - **链接**：[Issue #21968](https://github.com/google-gemini/gemini-cli/issues/21968)

4. **[#19873] [ENHANCEMENT] 利用模型的原生 bash 能力，实现零依赖操作系统沙箱** [🔒]
   - **重要性**：工作量大的增强提案，旨在从根本上发挥 Gemini 3 模型作为“原生 bash 用户”的优势，通过安全沙箱化执行来提升代码库探索和编辑的效率。
   - **社区反应**：9 条评论，讨论涉及安全性与功能性的平衡。
   - **链接**：[Issue #19873](https://github.com/google-gemini/gemini-cli/issues/19873)

5. **[#21983] [BUG] 浏览器子 Agent 在 Wayland 环境下失败** [🔒]
   - **重要性**：高优先级，限制了对 Linux Wayland 显示服务器用户的可用性。
   - **社区反应**：有 4 条评论，社区成员已定位到 Wayland 环境兼容性问题。
   - **链接**：[Issue #21983](https://github.com/google-gemini/gemini-cli/issues/21983)

6. **[#24246] [BUG] 当可用工具超过 128 个时，Gemini CLI 返回 400 错误** [🔒]
   - **重要性**：限制了 CLI 的可扩展性。随着自定义技能的增多，模型无法有效管理和筛选大量工具，导致 API 调用失败。
   - **社区反应**：3 条评论，开发者正在寻找让 Agent 更智能地限定工具范围的方法。
   - **链接**：[Issue #24246](https://github.com/google-gemini/gemini-cli/issues/24246)

7. **[#26525] [BUG] 自动记忆功能的安全性：需增加确定性内容和减少日志记录** [🔒]
   - **重要性**：涉及数据隐私和安全。Auto Memory 读取本地记录时，敏感信息在内容被送入模型上下文后才进行脱敏，存在潜在的信息泄露风险。
   - **社区反应**：5 条评论，社区对隐私问题表达了关注。
   - **链接**：[Issue #26525](https://github.com/google-gemini/gemini-cli/issues/26525)

8. **[#22465] [BUG] Gemini CLI 在创建 Vite 应用时卡在交互式提示符** [🔒]
   - **重要性**：暴露了 Agent 在执行需要交互式输入的命令（如 `vite` 脚手架）时的能力缺陷。模型无法自动完成这类交互。
   - **社区反应**：2 条评论。
   - **链接**：[Issue #22465](https://github.com/google-gemini/gemini-cli/issues/22465)

9. **[#21763] [BUG] `/bug` 报告未能提供子 Agent 上下文** [🔒]
   - **重要性**：高优先级，直接影响了 Bug 报告的效率和准确性。当问题发生在子 Agent 内部时，主报告的上下文无法帮助开发者定位问题。
   - **社区反应**：2 条评论，开发者已确认这是一个需要修复的缺失功能。
   - **链接**：[Issue #21763](https://github.com/google-gemini/gemini-cli/issues/21763)

10. **[#26522] [BUG] Auto Memory 过度重试处理低价值会话** [🔒]
    - **重要性**：功能设计缺陷，导致 Auto Memory 会对不重要的会话进行无限重试，浪费 token 和资源。
    - **社区反应**：4 条评论，讨论如何优化 Session 处理流程。
    - **链接**：[Issue #26522](https://github.com/google-gemini/gemini-cli/issues/26522)

---

### 🛠️ 重要 PR 进展

1. **[#29440] fix(core): 修复 web-fetch 对 UTF-8 编码标题引用的偏移量问题** [OPEN]
   - **功能/修复**：修复了 `web-fetch` 工具在处理非 ASCII 文本（如 emoji、多字节字符）时，无法正确定位引用来源的问题，对齐了 `web-search` 的逻辑。
   - **链接**：[PR #29440](https://github.com/google-gemini/gemini-cli/pull/29440)

2. **[#29244] fix(core): 使工具文件写入具有原子性，并序列化对同一路径的写入** [OPEN]
   - **功能/修复**：解决了并行工具执行导致同一文件多次写入时，可能丢失编辑内容的问题。通过序列化写入操作，保证了数据一致性。
   - **链接**：[PR #29244](https://github.com/google-gemini/gemini-cli/pull/29244)

3. **[#29432] fix(core): 在调度器释放时，清除已排队的工具调用** [OPEN]
   - **功能/修复**：修复了 Agent 调度器在停止或销毁后，仍有工具任务在后台执行或“悬挂”的问题，提高了资源释放的彻底性。
   - **链接**：[PR #29432](https://github.com/google-gemini/gemini-cli/pull/29432)

4. **[#29401] fix(core): 标准化代理配置的 esbuild 互操作性** [CLOSED]
   - **功能/修复**：修复了在构建环境中，`https-proxy-agent` 等库因 CJS/ESM 模块处理不一致而导致的代理解析失败问题。
   - **链接**：[PR #29401](https://github.com/google-gemini/gemini-cli/pull/29401)

5. **[#29437] fix(core): 后台 Shell 执行退出时清理临时目录** [OPEN]
   - **功能/修复**：确保后台运行的 Shell 命令在结束后，其创建的临时文件（如进程 ID 文件）能被正确清理，避免产生垃圾文件。
   - **链接**：[PR #29437](https://github.com/google-gemini/gemini-cli/pull/29437)

6. **[#29436] fix(cli): 修复标准输入中包含引号内 `@` 字符导致的 100% CPU 死循环** [OPEN]
   - **功能/修复**：修复了一个严重的问题：当通过管道或粘贴输入包含 `@scope/pkg` 这类代码时，CLI 会陷入无限循环，导致 CPU 100% 占用和崩溃。
   - **链接**：[PR #29436](https://github.com/google-gemini/gemini-cli/pull/29436)

7. **[#29435] fix(cli,core): 防止会话退出时进程挂起** [OPEN]
   - **功能/修复**：解决了 CLI 退出时，因标准输入流未正确关闭或 MCP 传输未清理导致 Node.js 进程无法结束的问题。
   - **链接**：[PR #29435](https://github.com/google-gemini/gemini-cli/pull/29435)

8. **[#29343] fix(cli): 阻止请求取消时未捕获的 AbortError 日志** [CLOSED]
   - **功能/修复**：修复了用户主动取消流式请求时，CLI 会因未捕获的 `AbortError` 而崩溃的问题，提升了用户体验。
   - **链接**：[PR #29343](https://github.com/google-gemini/gemini-cli/pull/29343)

9. **[#29231] docs: 修复过时的 JSDoc 参数名** [CLOSED]
   - **功能/修复**：虽然是小改动，但反映了社区对代码质量和文档规范性的重视。修复了多个文件中 JSDoc 描述与实际参数不匹配的问题。
   - **链接**：[PR #29231](https://github.com/google-gemini/gemini-cli/pull/29231)

10. **[#29320] fix(a2a-server): 注册 A2A 路由前解析 JSON 请求体** [OPEN]
    - **功能/修复**：修复了 Agent-to-Agent (A2A) 服务器无法解析 JSON-RPC 请求体的问题，确保了 Agent 间通信的 `express.json()` 中间件能正确发挥作用。
    - **链接**：[PR #29320](https://github.com/google-gemini/gemini-cli/pull/29320)

---

### 📊 功能需求趋势

1. **Agent 行为控制与可靠性**：社区最强烈的呼声是希望 Agent 更“听话”、更稳定。这包括对子 Agent 进行更好的调度、防止其无故挂起或误报状态、以及让模型能主动、聪明地选择和使用用户配置的技能。
2. **性能与资源优化**：对 Token 和上下文窗口的优化需求持续存在，例如通过“基于 AST 的文件读取”、“Tactful Extraction”等方式减少不必要的信息加载，并改进 Auto Memory 功能以避免资源浪费。
3. **安全与合规**：随着 Auto Memory 等功能的引入，对敏感信息（如密钥）的处理和脱敏、以及在沙箱环境中持久化信任决策等功能，成为社区关注的安全焦点。

---

### 👨‍💻 开发者关注点

1. **Agent 能力不足或失灵**：开发者频繁反馈 Agent 无法完成任务（如创建 Vite 项目时卡住）、无法处理交互式命令行、以及在特定环境下（如 Wayland）直接故障。这提示 Agent 的鲁棒性和环境适配能力亟需加强。
2. **配置与自定义的痛点**：开发者指出，`settings.json` 中的配置（如 `maxTurns`）对某些 Agent（如 Browser Agent）无效，以及自定义技能和子 Agent 难以被模型自动调用。这表明配置系统和模型推理之间存在脱节。
3. **内存系统的不稳定性**：Auto Memory 是社区关注的新功能，但出现了无限重试、无效补丁处理不当等问题，影响了用户对其的信任度。
4. **子 Agent 的黑盒问题**：用户无法轻易查看或导出子 Agent 的执行轨迹，导致调试和评估 Agent 行为变得困难。`/bug` 报告不包含子 Agent 上下文，也让问题定位过程受阻。
5. **版本迭代与用户预期落差**：从频繁的夜间构建和大量 PR 来看，`gemini-cli` 正处于快速迭代期。但部分关键 BUG 的持续存在，反映了开发速度与版本稳定性之间的平衡挑战。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

好的，以下是为您生成的 **GitHub Copilot CLI 社区动态日报**（2026-09-22），基于 `github/copilot-cli` 仓库的公开数据。

---

# GitHub Copilot CLI 社区动态日报｜2026-09-22

## 今日速览

昨日发布了 **v1.0.88-0 / v1.0.88-1** 两个补丁版本，主要修复了托管策略刷新时的权限保留问题，并新增了对 Ghostty/WezTerm 的 OSC 777 终端通知支持。社区中 **OOM 崩溃（#4699）** 和 **Auto 模式模型池不可配置（#4218）** 成为最受关注的两个开放 Issue，分别反映了长会话场景下的稳定性缺陷和用户对模型选择权的迫切需求。

## 版本发布

### v1.0.88-1（昨日发布）
- **Fixed**：托管设置刷新失败时保留 `/allow-all` 状态；精确记住缺失路径的会话授权，不再隐式授予父目录；精确授权可在 `/list-dirs` 中查看，并通过 `/reset-allowed-tools` 清除。
- **Fixed**：沙箱网络因代理隧道故障导致的拒绝问题。

### v1.0.88-0（昨日发布）
- **Added**：为 Ghostty、WezTerm 原生终端会话添加可选的 OSC 777 终端通知。
- **Improved**：技能发现支持命名空间自定义技能及可忽略的技能目录。
- **Improved**：MCP 与插件视图现在显示服务器显示名和插件说明，状态更清晰。
- **Improved**：恢复（`--resume`）功能增强。

### v1.0.87（2026-09-21 发布）
- **Added**：为 Auto 路由层级添加用户和托管启动默认值，包括严格和用户可覆盖的组织策略。
- **Improved**：连续的同模式提示合并为一条待处理消息；在空输入时按 `↑` 键可回退编辑已粘贴的文本。

## 社区热点 Issues（10 条）

1. **#4699 [OPEN] OOM 崩溃：长 `--resume` 会话导致 V8 堆内存溢出**  
   - 6 条评论，6 👍  
   - 用户在 14 小时的长会话中崩溃 3 次，均触及 4 GiB 堆上限，且诊断报告会写入当前工作目录，可能泄露敏感路径。  
   - [链接](https://github.com/github/copilot-cli/issues/4699)

2. **#4218 [OPEN] 允许用户配置 Auto 模式使用的模型池**  
   - 2 条评论，16 👍（本日最高赞）  
   - 用户希望限定 Auto 模式可调用的模型范围，以控制成本和预测行为。当前 Auto 会使用所有可用模型，导致不可预测。  
   - [链接](https://github.com/github/copilot-cli/issues/4218)

3. **#4892 [OPEN] 扩展宿主与所有 MCP 服务器每小时重新枚举一次**  
   - 2 条评论  
   - 会话内每小时触发一次全量重加载，导致不必要的开销，可能影响长时间运行的 agent 任务。  
   - [链接](https://github.com/github/copilot-cli/issues/4892)

4. **#4844 [OPEN] `--yolo` 启动标志在预授权阶段被错误吞掉，政策解决后不会重试**  
   - 2 条评论  
   - 由于托管设置的 fail-closed 策略，`--yolo` 在认证前被禁用且后续不再重新应用，导致用户无法按预期绕过权限。  
   - [链接](https://github.com/github/copilot-cli/issues/4844)

5. **#4837 [OPEN] 策略驱动的 `enabledPlugins` 安装插件后始终标记为 `"enabled": false`**  
   - 2 条评论，1 👍  
   - 仅通过配置启用插件不会真正激活它，需手动修改 config.json，严重影响企业策略自动部署。  
   - [链接](https://github.com/github/copilot-cli/issues/4837)

6. **#4888 [OPEN] MCP 客户端在成功完成 `2026-07-28` 发现后，仍发送旧版 `2025-11-25` 初始化请求**  
   - 1 条评论  
   - 双协议版本的 MCP SDK 会锁定连接，导致后续初始化被拒绝，破坏与现代 MCP 服务器的兼容性。  
   - [链接](https://github.com/github/copilot-cli/issues/4888)

7. **#4924 [OPEN] 桌面 App：新工作树会话中自定义 agent 缺失**  
   - 1 条评论  
   - 从桌面端启动新工作树时，`.github/agents/*.agent.md` 中的自定义 agent 不会出现，因为配置发现发生在延迟检出之前且不会重新扫描。  
   - [链接](https://github.com/github/copilot-cli/issues/4924)

8. **#3704 [OPEN] 希伯来语文本应 RTL 却显示为 LTR**  
   - 1 条评论  
   - 终端渲染器不支持 RTL（从右到左）语言，影响希伯来语和阿拉伯语用户。  
   - [链接](https://github.com/github/copilot-cli/issues/3704)

9. **#4705 [OPEN] 队列中的提示在会话空闲后仍卡住**  
   - 1 条评论，1 👍  
   - 按 Ctrl+Q 入队的提示有时不会在空闲后自动出队，用户需要通过队列管理手动触发，影响连续工作流。  
   - [链接](https://github.com/github/copilot-cli/issues/4705)

10. **#3264 [OPEN] 文档化 `.copilot` 文件夹中符号链接的行为**  
    - 3 条评论，1 👍  
    - 用户希望知晓在 Windows/macOS/Linux 上使用符号链接共享配置（如 instructions、skills）是否受支持，目前缺乏官方说明。  
    - [链接](https://github.com/github/copilot-cli/issues/3264)

## 重要 PR 进展

昨日仅有 2 个公开 PR，均为文档改进，暂无代码合并。以下是详细内容：

- **#4739 [OPEN] 文档提案：终端拥有的 macOS 通知**  
  - 作者：anujb-msft | 更新于 2026-09-21  
  - 示 Mac 终端通知点击问题的解决方案，并附带 MIT 许可的示例代码与可移植回归测试。**未合并**，属于参考方案。  
  - [链接](https://github.com/github/copilot-cli/pull/4739)

- **#4770 [OPEN] 文档：WebSocket 响应退出机制**  
  - 作者：1fanwang | 更新于 2026-09-21  
  - 当模型默认使用 WebSocket 传输但网络阻塞或出现 `400 input item ID does not belong to this connection` 错误时，提供文档说明如何通过环境变量退出 WebSocket 模式。  
  - [链接](https://github.com/github/copilot-cli/pull/4770)

## 功能需求趋势

综合昨日所有活跃 Issue，社区最关注的几个功能方向为：

1. **MCP 生态稳定性**：多起 Issue 涉及 MCP 协议兼容性（#4888、#4211）和重载频率（#4892），表明社区对 MCP 集成和长时间运行的可靠性要求很高。  
2. **模型可配置性**：用户强烈要求能自定义 Auto 模式可用的模型池（#4218 获 16 👍），以及 BYOK 场景下的自定义 HTTP 头（#3399 获 14 👍）。  
3. **会话与内存管理**：长会话 OOM（#4699）和队列卡顿（#4705）暴露出会话状态管理的不足，尤其是 `--resume` 场景下的资源控制。  
4. **策略与配置灵活性**：企业用户需要更细粒度的工具权限（#1971）和可靠的策略驱动的插件激活（#4837），以及 `--yolo` 在预授权阶段的正确行为（#4844）。  
5. **终端渲染与国际化**：端输流输出乱码（#3749）和 RTL 语言支持缺失（#3704）反映了多语言环境下的可用性差距。

## 开发者关注点

- **性能与稳定性**：OOM 崩溃是当前最严重的 bug，开发者期待尽快修复或提供内存限制选项；每小时 MCP 重枚举也被质疑为过度设计。  
- **策略与权限**：托管策略与本地配置的交互存在多处不一致（`allowed-tools` 授权、插件启用、`--yolo` 失效），导致企业部署后实际行为与预期不符。  
- **MCP 兼容性**：大整数序列化失败（#4211）、协议版本错配（#4888）、OAuth 端口绑定（#4926）等细节问题频发，表明 MCP 客户端的健壮性有待提升。  
- **桌面集成**：桌面端新工作树自定义 agent 缺失（#4924）影响了已采用 GitHub 组织级 agent 的工作流，且缺少自动重新扫描机制。  
- **日常体验**：文件 `@` 提及在大型仓库中延迟过高（#3469）、`/ask` 有时无响应（#4253）、长提示回退编辑（v1.0.87 已部分修复但仍有待观察）等细节影响日常效率。  
- **文档缺失**：符号链接行为、WebSocket 退出机制、BYOK 自定义头等关键配置缺乏官方说明，开发者被迫通过 Issue 提问或自行试验。

---

*数据来源：GitHub 仓库 `github/copilot-cli`，截至 2026-09-22 00:00 UTC。*

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

## Kimi Code CLI 社区动态日报 | 2026-09-22

### 今日速览

Kimi CLI（Python 版）于昨日发布 **1.51.0 最终版本**，并正式宣布归档停止维护，所有用户被引导迁移至全新重写的 **Kimi Code CLI**（[MoonshotAI/kimi-code](https://github.com/MoonshotAI/kimi-code)）。社区关注重心迅速转移，遗留的 MCP 授权改进 PR 仍在等待合并，但主仓库已进入“冻结”状态。

---

### 版本发布

#### v1.51.0 – 最终归档版本
- **发布时间**：2026-09-21  
- **核心变更**：
  - 仓库正式归档，README、文档、PyPI 元数据将不再更新。
  - 新增 `packages/kimi-code` 存根包（stub），版本同步至 1.51.0，用于引导用户安装新的 Kimi Code CLI。
  - 所有 CHANGELOG、文档变更日志及破坏性变更说明均已同步至 1.51.0 版本下。

> **注意**：v1.51.0 是 Kimi CLI 的最后一个版本，后续功能迭代与问题修复将仅在 Kimi Code CLI 中进行。  
> 🔗 [Release v1.51.0](https://github.com/MoonshotAI/kimi-cli/releases/tag/1.51.0)  
> 🔗 [完整 Changelog](https://github.com/MoonshotAI/kimi-cli/compare/1.50.0...1.51.0)

---

### 社区热点 Issues

由于仓库即将归档，过去 24 小时内仅新增/更新 2 条 Issue，但意义重大：

| Issue | 状态 | 摘要 | 重要性说明 |
|-------|------|------|------------|
| [#2661 📢 Kimi CLI 停止维护，请迁移至 Kimi Code CLI](https://github.com/MoonshotAI/kimi-cli/issues/2661) | **OPEN** | 官方正式通知：Kimi CLI（Python 版）已停止维护，用户需迁移至 [Kimi Code CLI](https://github.com/MoonshotAI/kimi-code)（原生二进制，下一代终端 AI Agent）。 | **最关键 Issue**，所有用户都应阅读并迁移。目前无评论，预计社区讨论将转向 Kimi Code CLI 仓库。 |
| [#1534 CLI 终端界面乱序且自动重复](https://github.com/MoonshotAI/kimi-cli/issues/1534) | **CLOSED** | 用户报告启动后手动调整终端导致界面混乱、自动重复输出。 | 该 Issue 在归档前夕被关闭，但修复方案未公开，建议迁移至 Kimi Code CLI 查看是否已解决。 |

> **说明**：受限于归档冻结，Kimi CLI 仓库不再接受新的 Issue 提交。社区热点已迁移至 `MoonshotAI/kimi-code` 仓库，请关注该仓库的 Issue 区。

---

### 重要 PR 进展

| PR | 状态 | 摘要 | 技术价值 |
|----|------|------|----------|
| [#2660 chore: bump kimi-cli to 1.51.0](https://github.com/MoonshotAI/kimi-cli/pull/2660) | **已合并** | 发布最终版本，同步所有文档和元数据，移除对 `kimi-cli` 的依赖。 | **归档前最后操作**，确保用户能通过 PyPI 获取迁移指引。 |
| [#2659 chore: archive kimi-cli 并转向 Kimi Code CLI](https://github.com/MoonshotAI/kimi-cli/pull/2659) | **已合并** | 准备归档：更新 README、文档站点、安全/贡献政策，所有链接指向新仓库。 | 告知社区迁移路径，避免碎片化。 |
| [#1625 feat(mcp): 添加 --scope 选项支持 OAuth 作用域](https://github.com/MoonshotAI/kimi-cli/pull/1625) | **OPEN** | 为 MCP 服务器配置添加可重复的 OAuth scope 参数，修复上游认证流问题。基于 FastMCP 3.2.4 / MCP SDK 1.27.1。 | **遗留的最后一个功能 PR**，但因仓库冻结未合并。开发者可关注 Kimi Code CLI 是否已包含类似改动。 |

> **提示**：PR #1625 由于仓库归档将不会合并。若需要 MCP OAuth scope 支持，建议在 [Kimi Code CLI](https://github.com/MoonshotAI/kimi-code) 中提 feature request。

---

### 功能需求趋势

从近期 Issues 及 PR #1625 可提炼出社区最关注的技术方向：

1. **迁移适配**（当前 100%）  
   - 用户核心需求是平滑地从 Kimi CLI 迁移到 Kimi Code CLI，包括配置迁移、插件兼容性、工作流延续等。
2. **MCP 协议增强**（PR #1625）  
   - OAuth 授权流程的精细化控制（scope 可配置）是社区等待较久的功能，反映了企业级使用中对安全认证灵活性的要求。
3. **终端交互稳定性**（Issue #1534）  
   - 终端重绘、输出乱序等底层 TUI 问题仍有改进空间，新版本若能解决将提升用户体验。

---

### 开发者关注点

- **迁移成本**：Kimi CLI 用户需要安装新的原生二进制版本（Kimi Code CLI），配置路径、API Key 等可能需重新设置。社区对迁移文档的清晰度有较高期待。
- **遗留功能可用性**：部分高级功能（如自定义 MCP OAuth scope）在 Kimi CLI 中开发受阻，开发者希望 Kimi Code CLI 能尽快补齐。
- **封闭性风险**：Kimi Code CLI 重写为原生二进制后，开源透明度是否保持不变？部分开发者关注新仓库的许可协议和贡献流程。

> **建议**：立即查看 [Kimi Code CLI 仓库](https://github.com/MoonshotAI/kimi-code) 的 README 和迁移指南，并 Star 该仓库以接收后续更新。如遇到迁移问题，请直接在新仓库提交 Issue。

---

*日报数据截至 2026-09-22 09:00 UTC，基于 MoonshotAI/kimi-cli 仓库动态整理。*

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 | 2026-09-22

---

## 🔥 今日速览
- **v1.18.32 紧急发布**：修复了 v1.18.30 中导致所有提示崩溃的 `SystemPrompt.environment` 类型错误（`a.name` 未定义），同时修正了 Bedrock 图片附件与 Together AI 流式使用报告的问题。
- **社区热议**：超过 5 个独立 Issue 指向同一回归 bug，最高获赞 47；免费额度计算混乱、Web/TUI 会话不同步等问题持续困扰用户。
- **重要 PR 合并**：聊天模型按轮次动态选择（`chat.model` hook）已合入；TUI 自动标签模式、CLI 非交互模式输出丢失等问题得到修复。

---

## 🚀 版本发布

### v1.18.32
**核心修复**
- **Bedrock 图片附件**：仅对 Claude、Nova、Llama 4 模型提升图片附件，避免其他模型错误。
- **Together AI 流式使用报告**：修正流式响应后使用量统计不准确的问题。

**社区贡献**
- @dc85：
  - 文档：在 Zen 中添加 DeepSeek V4.1 Flash 支持 (#49897)
  - 功能：在 Zen 中添加 Grok 4.7 支持

> 注：此版本已包含 v1.18.30 回归 bug 的修复（见下方 Issue 说明）。

---

## 🐛 社区热点 Issues（10 个）

### 1. `SystemPrompt.environment` 崩溃轰炸（多个 Issue 合并）
- **#48811** (macOS，👍47) `undefined is not an object (evaluating 'a.name')`  
- **#48372** (通用，👍27) 同样错误，`opencode run` 和 TUI 均崩溃  
- **#49158** (通用，👍35) 同上  
- **#48965** (通用，👍22) 同上  

**重要性**：v1.18.30 的严重回归，几乎影响所有用户，每个提示立即失败。社区通过多个 Issue 快速反馈，官方已确认并在 v1.18.32 中修复。

### 2. #48973 🔥 Mus e Spark 1.3 报错 `encrypted_content` 未授权
**作者**：wayback09 | **评论**：12 | **👍**：8  
**摘要**：使用 Muse Spark 1.3 时出现上游请求失败，提示 `reasoning encrypted_content was not issued to this caller`。涉及 OpenCode Zen 特定模型的身份验证问题。

### 3. #50093 免费额度耗尽后重试计时器不断增长
**作者**：Raj-Khadka | **评论**：8 | **👍**：5  
**摘要**：免费模型额度用完后显示“重试还需 6 小时”，等待 6 小时后切换另一免费模型，计时器反而更长。免费模型之间的额度计算逻辑不透明，用户体验极差。

### 4. #50452 💸 充值 $20 后余额无故清零，无日志
**作者**：locustSpawning | **评论**：5 | **👍**：0  
**摘要**：充值后使用两天，账户余额突然归零，没有任何使用记录或日志。发票存在但活动为空，疑似计费系统 bug。

### 5. #2773 🔒 [CLOSED] 远程 SSH 终端无法复制文本
**作者**：magic-thomas | **评论**：28 | **👍**：3  
**摘要**：在远程 SSH 控制台中使用 OpenCode 时，无法像 Claude Code 那样复制选中文本。尽管已关闭，但社区讨论热烈，表明远程场景下基础交互缺失。

### 6. #42264 🖥️ TUI 流式输出时文本消失，TreeSitter 栈溢出
**作者**：birdhackor | **评论**：5 | **👍**：4  
**摘要**：LLM 流式生成时，语法高亮 Worker 因 WASM 栈溢出崩溃，导致已显示文本冻结。核心问题在于流式更新和高亮渲染的同步缺陷。

### 7. #45011 🌐 Web 首页无法显示 CLI 创建的会话
**作者**：tak2-08 | **评论**：8 | **👍**：2  
**摘要**：通过 TUI、`opencode run` 或 Agent 创建的会话在 Web 首页永远不可见，必须手动在浏览器中添加项目。跨端数据同步缺失。

### 8. #48645 📉 v1.18.30 回归，1.18.18 正常工作
**作者**：Syntaxri | **评论**：10 | **👍**：18  
**摘要**：从 pacman 更新到 1.18.30 后每个提示立即失败，降级到 1.18.18 恢复正常。确认是此版本引入的回归。

### 9. #50387 🗺️ 新界面布局糟糕，功能入口丢失
**作者**：wordgao | **评论**：2 | **👍**：4  
**摘要**：新版标签切换和显示模式不友好，找不到 OpenCode 切换按钮，看不到其他服务器的版本信息，且无法找到 ACP/MCP/Plugs 入口。中文用户强烈反馈 UI 可用性退化。

### 10. #50458 🧪 Bash 工具 stdout/stderr 管道损坏多字节输出
**作者**：Jiansorge | **评论**：2 | **👍**：0  
**摘要**：在 PowerShell 上运行长输出或多字节文本时，Bash 工具的管道处理出现数据完整性错误。影响中文、日文等多字节输出场景。

---

## 🔧 重要 PR 进展（10 个）

### 1. #50456 ✅ [CLOSED] feat(tui): 自动标签模式
**作者**：opencode-agent[bot]  
**摘要**：将原来的布尔值 `tabs.enabled` 替换为 `tabs.mode`（`auto` / `on` / `off`），默认 `auto` 在 `HERDR_ENV=1` 环境下自动禁用标签，同时向后兼容。提升多会话场景的体验。

### 2. #50448 ✅ [CLOSED] feat: `chat.model` hook — 按轮次动态选模型
**作者**：dmouse  
**摘要**：新增 `chat.model` 插件钩子，允许插件在每个 Provider 轮次前动态选择模型，而非固定整个任务使用同一模型。为复杂任务链提供了灵活调度能力。

### 3. #50462 🔄 [OPEN] fix(client): 保留服务启动失败信息
**作者**：abpai  
**摘要**：当多个进程争夺端口导致绑定失败时，保留首次启动的错误信息并展示给用户，避免无提示静默失败。关闭 #50461。

### 4. #50453 ✅ [CLOSED] fix(cli): 非交互模式输出丢失
**作者**：BoYanZh  
**摘要**：修复 `opencode run --format json` 偶尔返回空 stdout 的问题。在 run 进入空闲状态时刷新未发送的消息部分，确保完整输出。

### 5. #50455 ✅ [CLOSED] feat(codemode): 未知工具错误时提示最接近的工具名
**作者**：rekram1-node  
**摘要**：当调用不存在的工具时，自动匹配最接近的现有工具名。例如输入 `github.get-me` 会提示 `Did you mean tools.github.get_me?`。提升开发者体验。

### 6. #50450 ✅ [CLOSED] fix(codemode): 多项 JS 一致性修复
**作者**：rekram1-node  
**摘要**：修复 Map/Set forEach 实时遍历、生成器原型、重复函数声明、非引用值 delete 等问题。确保 codemode 行为与标准 JS 一致。

### 7. #50422 🔄 [OPEN] feat(core): 恢复 GitLab 工作流发现并添加 OAuth 登录
**作者**：vglafirov  
**摘要**：修复内置 GitLab Duo 提供商的 workflow 发现功能，并新增 OAuth 登录支持。关闭 #50421。

### 8. #50267 🔄 [OPEN] feat(app): 通过浏览器登录 OpenCode Go / Console
**作者**：Hona  
**摘要**：桌面端新用户可直接跳转到浏览器进行 OAuth 登录，API Key 方式作为底部小链接。简化企业级用户的登录流程。

### 9. #50454 ✅ [CLOSED] test: 稳定 Windows CI
**作者**：rekram1-node  
**摘要**：通过限制单元测试并发数、取消服务冒烟超时定时器、重新编译插件监视器等方式，解决 Windows CI 运行不稳定问题。

### 10. #49815 🔄 [OPEN] fix(app): 在快捷键弹窗中保持搜索框焦点
**作者**：fschrhunt  
**摘要**：设置 → 快捷键页面中，输入第一个字符后焦点丢失的问题。现在输入时保持焦点在过滤器上，提升可用性。

---

## 📈 功能需求趋势

从近期 Issues 和 PR 分析，社区最关注以下功能方向：

1. **跨端会话/项目同步**  
   - Web UI 与 TUI/CLI 会话不可见（#45011, #46444, #37096）  
   - 远程 SSH 基础交互（复制、标签切换）缺失（#2773）

2. **流式渲染与性能**  
   - TUI 流式文本消失因 TreeSitter 栈溢出（#42264）  
   - 流式事件未正确发布（#50285）

3. **模型与 API 兼容性**  
   - 新模型（Muse Spark 1.3, DeepSeek V4）的加密内容错误（#48973）  
   - 免费模型额度计算混乱（#50093, #50457）

4. **计费与账号透明度**  
   - 余额无故清零无日志（#50452）  
   - 免费额度和付费额度计算方式不透明

5. **UI/UX 改进**  
   - 标签快捷键（Ctrl+T/W/Tab）（#37077）  
   - 新布局功能入口丢失（#50387）  
   - MCP 侧边栏状态持久化（#50447）

6. **插件与扩展生态**  
   - 动态模型选择 hook（#50448）  
   - GitLab 集成刷新（#50422）  
   - 插件列表社区贡献（opencode-mesh, kowork 等）

---

## 👷 开发者关注点（痛点和高频需求）

- **回归灾难**：v1.18.30 的 `SystemPrompt.environment` 崩溃被多个用户独立报告，最高 47 赞，反映出版本发布前缺乏回归测试覆盖。开发者应优先建立关键路径的自动化测试。
- **免费额度体验差**：重试计时器累积、额度计算不清晰、无详细用量记录，导致轻度用户困惑甚至流失。
- **Web 与 CLI 数据鸿沟**：TUI/CLI 创建的会话在 Web 端不可见，以及反向情况，严重削弱混合工作流的使用意愿。
- **远程场景支持薄弱**：SSH 终端无法复制、移动端 Firefox 缺少组件选择器，表明跨环境适配仍是短板。
- **多字节编码问题**：Bash 工具管道损坏 UTF-8 输出，影响非英文用户，且反馈较少（👍 0），但有潜在广泛影响。
- **Windows 平台稳定性**：CI 不稳定、Web UI 在 Windows 下会话列表刷新丢失、PowerShell 管道问题，表明 Windows 端的 QA 仍需加强。

---

*数据来源：GitHub `anomalyco/opencode`，截至 2026-09-22 14:00 UTC。部分 Issue/PR 仍在开放中。*

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 | 2026-09-22

## 📌 今日速览

1. **核心版本 v0.87.0 发布**，引入规范化会话上下文与扩展边界，编辑模型上下文无需重写历史，并新增生命周期钩子。
2. **社区高度关注多个回归性 bug**，包括 0.86.x 版本中 RPC steer 与 extension 交互混乱、Codex 工具调用泄漏为原始文本，以及 `PI_OFFLINE` 环境变量静默禁用模型发现等。
3. **多起性能优化合并**，修复全屏模式下的渲染风暴和跳转标签偏移，同时新增 Grok 4.7 模型支持与 Google 429 重试策略。

---

## 📦 版本发布

### v0.87.0 — 2026-09-22

**核心新增：规范化会话上下文与扩展边界**
- 引入 **`ContextEditEntry`** 机制，允许在不重写历史的情况下编辑模型上下文。
- 添加**可操作的扩展生命周期钩子**（`before_provider_request`、`onPayload` 等），扩展可更精准地拦截或修改请求。
- 详见 [v0.87.0 Release Note](https://github.com/earendil-works/pi/releases/tag/v0.87.0)

> 该版本还包含了多个来自主干的 bug 修复（见下方 PR 列表），建议所有用户尽快升级。

---

## 🔥 社区热点 Issues（Top 10）

| # | 标题 | 状态 | 评论 | 重要性 |
|---|------|------|------|--------|
| **#7730** | [bug] Mac OS 长会话导致高 CPU (100%) | OPEN | 17 | **影响 macOS 重度用户**，与上下文大小相关，社区持续讨论中 👉 [链接](https://github.com/earendil-works/pi/issues/7730) |
| **#8684** | `PI_OFFLINE` 静默禁用所有 provider 模型发现，与文档矛盾 | OPEN | 12 | **严重误导**，本应只禁启动检查组网，却影响整个会话的模型发现，亟待文档纠正 👉 [链接](https://github.com/earendil-works/pi/issues/8684) |
| **#9803** | 0.86.0 回归：RPC steer 成功无法与 extension 处理的输入关联 | OPEN | 9 | **阻碍 RPC 客户端实现**，extension 可能消耗输入并排队，但响应无法追踪原始输入 👉 [链接](https://github.com/earendil-works/pi/issues/9803) |
| **#9822** | 0.86.x: Codex 工具调用在 compaction 后泄漏为原始 harmony 文本 | CLOSED | 5 | **导致工具链断裂**，已被 #9846 修复，但影响范围大，值得关注 👉 [链接](https://github.com/earendil-works/pi/issues/9822) |
| **#9549** | 大 transcript 下全屏渲染风暴（满核） | OPEN | 6 | **性能关键**，每次 resize 重绘整个 transcript，Windows 2 核用户卡顿严重 👉 [链接](https://github.com/earendil-works/pi/issues/9549) |
| **#9602** | Compaction 因包含被省略的 thinking 消息导致溢出 | OPEN | 6 | **影响本地模型用户**，Qwen3.8 等小模型超限，需优化 compaction 逻辑 👉 [链接](https://github.com/earendil-works/pi/issues/9602) |
| **#9773** | `before_provider_request` 未对 compaction/summarization 触发 | OPEN | 5 | **扩展开发者痛点**，文档说明应触发但实际未执行，extension 无法拦截这些请求 👉 [链接](https://github.com/earendil-works/pi/issues/9773) |
| **#9843** | 0.86.x 回归：通过 LiteLLM 代理的长请求出现 `APIConnectionError` | CLOSED | 4 | **影响 OpenAI 兼容代理用户**，回归后频繁断开，已定位但需验证全局修复 👉 [链接](https://github.com/earendil-works/pi/issues/9843) |
| **#8667** | 旧 compaction entry 在 later compaction 范围内永久破坏会话 | CLOSED | 4 | **严重固件**，Anthropic 模型遇到 `unexpected tool_use_id` 400 错误，社区给出规避方案 👉 [链接](https://github.com/earendil-works/pi/issues/8667) |
| **#9678** | mistral-conversations: 托管 GLM 推理丢失请求的 effort level | OPEN | 3 | **影响 Mistral 用户**，GLM 5.x 模型无法正确设置 reasoning_effort，社区请求新增模型 ID 👉 [链接](https://github.com/earendil-works/pi/issues/9678) |

---

## 🚀 重要 PR 进展（Top 10）

| # | 标题 | 状态 | 亮点 |
|---|------|------|------|
| **#9866** | fix(agent): 回放前验证持久化工具参数 | **CLOSED** | **安全修复**：当工具 schema 变更后，旧持久化参数可能导致意外执行，增加运行时校验 👉 [链接](https://github.com/earendil-works/pi/pull/9866) |
| **#9861** | fix(ai,coding-agent): 遵循 Google 429 速率限制的重试延迟 | CLOSED | **稳定性**：Google per-minute 限流返回明确重试延迟，之前立即失败，现已正确等待 👉 [链接](https://github.com/earendil-works/pi/pull/9861) |
| **#9859** | feat(ai,coding-agent): 增加 Grok 4.7 支持 | CLOSED | **新模型**：加载 `grok-4.7`，500k 上下文，支持图像输入与多级推理，定价翻倍但需注意 cache 策略 👉 [链接](https://github.com/earendil-works/pi/pull/9859) |
| **#9832** | 关联 RPC 输入处置与队列消息 | CLOSED | **解决 #9803**：为 RPC 输入添加明确的 `handled`、`queued`、`accepted` 处置状态，客户端可精准匹配 👉 [链接](https://github.com/earendil-works/pi/pull/9832) |
| **#9846** | fix(coding-agent): 跨 context handlers 保持 prompt 和工具状态 | CLOSED | **修复 #9822**：确保 context handler 过滤消息时不丢失内置工具声明，Codex 正确识别 tool call 👉 [链接](https://github.com/earendil-works/pi/pull/9846) |
| **#9842** | fix(tui): 防止跳转标签在滚动条隐藏时偏移 | CLOSED | **UI 改进**：解决 #9136 中标签跳动问题，居中绘制，不依赖滚动条可见性 👉 [链接](https://github.com/earendil-works/pi/pull/9842) |
| **#9830** | fix(coding-agent): 报告无效 prompt 前端模板 | CLOSED | **用户体验**：原来无效 YAML frontmatter 静默丢弃，现在通过诊断路径报告错误，与 skills 行为一致 👉 [链接](https://github.com/earendil-works/pi/pull/9830) |
| **#9438/9483** | fix(coding-agent): 工具 cwd 解析改为 opt-in 模式 | CLOSED | **向后兼容**：将之前的 `cwd` 重命名为 `customCwd`，保留 `ctx.cwd` 回退，避免破坏现有工具配置 👉 [链接](https://github.com/earendil-works/pi/pull/9483) |
| **#9841** | fix(coding-agent): 允许离线导出 bug 报告 | CLOSED | **可用性**：`PI_OFFLINE` 时不再阻止本地导出 zip，仅阻止上传，方便无网络用户收集诊断 👉 [链接](https://github.com/earendil-works/pi/pull/9841) |
| **#9714** | feat(ai): 支持 Azure Foundry Chat Completions 部署 | OPEN | **新平台**：扩展 Azure 适配器以支持 Chat Completions 端点，DeepSeek V4 Pro 等模型可通过 Azure 使用 👉 [链接](https://github.com/earendil-works/pi/pull/9714) |

---

## 📊 功能需求趋势

从过去 24 小时活跃的 Issues 和 PR 中，社区关注方向可归纳为：

1. **开源模型/多平台支持**  
   - 请求新增 `zai-glm` 模型（#9678）、Grok 4.7（#9859）、Ollama 原生支持（#9850，WIP）、Azure Foundry Chat Completions（#9714）。
   - 社区对本地模型（如 Qwen、GLM）的 compaction 和 retry 问题格外敏感。

2. **扩展 API 能力**  
   - 扩展无法观测 per‑attempt 重试（#9829）、无法访问提供商特定响应字段（#9784）、`before_provider_request` 未覆盖 compaction 请求（#9773）——开发者要求更完整的 hook 系统。
   - 同时，v0.87.0 的规范化会话上下文机制（`ContextEditEntry`）直接回应了这一诉求。

3. **性能与渲染优化**  
   - 大 transcript 下的全屏渲染风暴（#9549）和跳转标签偏移（#9136）已由 PR #9842 修复，但 Windows 10 下的 UI 遗留问题（#9833）仍需进一步解决。
   - macOS 高 CPU（#7730）依然开放，社区期待官方介入。

4. **RPC 与客户端集成**  
   - RPC steer 与 extension 处理的输入关联丢失（#9803、#9832）是近期的痛点，PR #9832 已提供解决方案。
   - `SessionManager.create()` 未及时写入磁盘（#9792）影响编程化使用。

5. **配置与文档一致性**  
   - `PI_OFFLINE` 行为与文档矛盾（#8684）引发广泛讨论，提示社区对“文档即契约”的强烈期待。

---

## 🔧 开发者关注点

- **回归频发**：0.86.x 系列引入多个问题（RPC steer、Codex 工具泄漏、LiteLLM 连接错误），开发者在升级时需谨慎，建议关注后续 patch 版本。
- **扩展开发门槛**：缺乏对 provider 重试、供应商特定字段的访问，导致社区提议创建 “meta‑issue” #9784 集中关注。v0.87.0 的扩展边界钩子有望缓解部分痛点。
- **Windows 平台体验**：除 UI 渲染问题外，Chrod 包边界测试在 Windows 上因路径反斜杠错误拒绝包内导入（#9835），已经修复。Windows 10 conhost 仍有残留内容问题（#9833）。
- **模型权限与限流**：Anthropic 开始通过 Pi 系统提示词检测并限制订阅使用（#9838），开发者可能需要考虑更隐蔽的 provider 配置或替换。

> 日报由 AI 技术分析师基于 GitHub 数据自动生成，仅供参考。  
> 数据截止：2026-09-22 01:00 UTC

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

好的，作为一名专注于 AI 开发工具的技术分析师，我为您整理了基于 QwenLM/qwen-code 仓库数据生成的 **2026年9月22日社区动态日报**。

---

# Qwen Code 社区动态日报 | 2026-09-22

## 今日速览

Qwen Code 今日发布 v0.24.3 正式版，重点增强了 Web Shell 的结构化输出和主机控制能力。社区方面，用户反馈的 **macOS 终端 PTY 不可用** 及 **Remote-SSH 会话创建失败** 问题成为讨论焦点，同时关于跨会话管理和多代理架构的功能需求讨论活跃。

## 版本发布

### v0.24.3 正式版发布
**核心更新：聚焦 Web Shell 与 CLI 体验**

*   **Web Shell 增强**：Web Shell 现在支持结构化 shell 执行结果展示、可选的轨迹指标，并新增了主机设置白名单功能。此外，移动端导航体验也得到了修复。
*   **功能优化**：
    *   `core`：新增监控工具（monitor tool）提示，用于指导系统行为。
    *   `daemon`：新增批量工作区操作支持。
*   **问题修复**：
    *   `cli`：修复了 ACP（自主代码流程）权限队列作用域问题，确保只对当前会话生效。
    *   `channels`：新增了共享输出模式功能。

> **相关链接**：
> - [Release v0.24.3](https://github.com/QwenLM/qwen-code/releases/tag/v0.24.3)
> - [Desktop v0.24.3](https://github.com/QwenLM/qwen-code/releases/tag/desktop-v0.24.3)
> - [SDK TypeScript v0.1.14](https://github.com/QwenLM/qwen-code/releases/tag/sdk-typescript-v0.1.14)

---

## 社区热点 Issues

1.  **[[P1] macOS 终端 PTY 完全不可用 (Issue #11872)](https://github.com/QwenLM/qwen-code/issues/11872)**
    *   **重要性**：最高优先级Bug。macOS 用户在 Web Shell 中无法使用终端，核心原因是 `@lydell/node-pty` 库的预构建版本因代码签名问题被系统拦截，而模块本身也未正确打包。
    *   **社区反应**：13条评论，是当前最受关注的问题，开发者正在积极排查。

2.  **[[P1] Remote-SSH 会话创建失败：`write EPIPE` (Issue #12416)](https://github.com/QwenLM/qwen-code/issues/12416)**
    *   **重要性**：影响 Remote-SSH 场景。使用 Companion 0.24.2 时，所有会话创建请求均因 `write EPIPE` / `BridgeChannelClosedError` 失败，但独立的 CLI 可以正常工作。
    *   **社区反应**：7条评论，用户反馈强烈，表明 0.24.2 版本在该场景下存在回归问题。

3.  **[[P1] Windows 桌面版构建失败，未发布 Windows 安装包 (Issue #12414)](https://github.com/QwenLM/qwen-code/issues/12414)**
    *   **重要性**：构建故障导致 v0.24.2 的Windows用户无法获取更新。根因是 CI 脚本在 PowerShell 下执行了 bash 命令。
    *   **社区反应**：6条评论，虽然已关闭，但对Windows用户影响重大。

4.  **[[P2] 跨会话门控：在多会话主机中管理、限制和命名会话 (Issue #12303)](https://github.com/QwenLM/qwen-code/issues/12303)**
    *   **重要性**：功能需求，是多代理（multi-agent）路线图中的关键一环。讨论了如何在一个包含多个会话的主机上，优雅地处理消息路由、会话上限和命名等核心问题。
    *   **社区反应**：8条评论，开发者正探讨潜在的技术方案和UI/UX设计。

5.  **[[P2] 托管代理双路径架构提案 (Issue #12380)](https://github.com/QwenLM/qwen-code/issues/12380)**
    *   **重要性**：高层次架构提案，定义了未来“托管代理（Managed Agent）”的演进路径，包括独立的推理环境、持久的会话所有权和可恢复的工具执行。
    *   **社区反应**：5条评论，标记为“需要讨论”，表明这是一个尚未有定论但社区和开发者都高度关注的方向。

6.  **[[P2] 功能请求：支持桌面端 UI 字体大小调整 (Issue #12406)](https://github.com/QwenLM/qwen-code/issues/12406)**
    *   **重要性**：体验优化。macOS 用户反馈桌面应用的 Web UI 字体过小，且设置中缺乏调整选项。
    *   **社区反应**：3条评论，是一个真实且影响日常使用的细节痛点。

7.  **[[P2] `review` 工具需要结构化启动属性标识 (Issue #12372)**
    *   **重要性**：代码审查功能的核心改进。旨在为每个代码块提供更精准的分类和覆盖率信息，但因其复杂性被拆分，目前仍处于待评审状态。
    *   **社区反应**：4条评论，反映了高级功能在迭代过程中的精细化打磨。

8.  **[[P3] 会话回顾摘要始终为英文 (Issue #11847)](https://github.com/QwenLM/qwen-code/issues/11847)**
    *   **重要性**：国际化问题。当用户回到闲置会话时，显示的摘要（recap）总是英文，无法与对话所用语言匹配，影响非英语用户的使用体验。
    *   **社区反应**：8条评论，显示出社区对多语言支持的期待。

9.  **[[P3] `splitCompoundCommandSegments` 错误解析注释中的运算符 (Issue #11815)](https://github.com/QwenLM/qwen-code/issues/11815)**
    *   **重要性**：shell命令解析Bug。脚本注释中的运算符（如`|`, `&`）被错误解析，导致权限确认逻辑出现异常。
    *   **社区反应**：6条评论，属于边界情况Bug，但可能影响自动化脚本执行的正确性。

10. **[[P3] 生态系统：ClawMetry 阅读器现已开源 (Issue #12428)](https://github.com/QwenLM/qwen-code/issues/12428)**
    *   **重要性**：生态拓展。第三方工具 ClawMetry 成为开源项目，用户可以直接在 Qwen Code 中使用。此前因明确的技术障碍被关闭，现障碍已解决。
    *   **社区反应**：3条评论，社区成员跟进积极，项目维护者回应良好。

---

## 重要 PR 进展

1.  **[[WIP] feat(web-shell): 为主机添加模型管理控制 (PR #12345)](https://github.com/QwenLM/qwen-code/pull/12345)**
    *   **内容**：为嵌入式的 Web Shell 实例添加可选的主机模型管理功能，允许部署者控制用户是否可以添加或删除模型。

2.  **[[WIP] feat(web-shell): 将会话计划固定在对话上方 (PR #12134)](https://github.com/QwenLM/qwen-code/pull/12134)**
    *   **内容**：在 Web Shell 的对话区顶部新增一个可折叠的计划面板，用于展示当前执行步骤，提升用户对Agent工作进度的掌控感。

3.  **[[WIP] feat(web-shell): 支持 SSH 工作区而无须远程守护进程 (PR #12255)](https://github.com/QwenLM/qwen-code/pull/12255)**
    *   **内容**：允许用户通过 `ssh://` 协议直接添加远程文件夹作为工作区，所有操作通过本地守护进程经 SSH 通道执行，无需在远程安装 Qwen Code 服务。

4.  **[[WIP] fix(core): 修复 `CodeModeOnly` 模式下桥接工具的显示问题 (PR #12429)](https://github.com/QwenLM/qwen-code/pull/12429)**
    *   **内容**：修复了 Issue #12425 中 `CodeModeOnly` 模式下，工作流关键词仍会错误引用隐藏桥接工具（`tool_search`）的问题。

5.  **[[WIP] fix(mcp): 支持更大 App、限定工具调用和隔离源 (PR #12258)](https://github.com/QwenLM/qwen-code/pull/12258)**
    *   **内容**：修复了 MCP 集成的三个独立故障，包括按服务器限制资源加载、允许由 App 触发的工具调用，以及处理不透明的 iframe 源。

6.  **[[WIP] feat(core,cli): 为严格 OpenAI 兼容服务器增加可选参数强制模式 (PR #12222)](https://github.com/QwenLM/qwen-code/pull/12222)**
    *   **内容**：新增 `toolParametersMandatory` 选项。当模型调用的工具无参数时，强制发送空参数对象，以满足某些严格遵循 OpenAI 规范的服务器要求。

7.  **[[WIP] feat(web-shell): 启用非 loopback 监听器上的过期二维码配对 (PR #12322)](https://github.com/QwenLM/qwen-code/pull/12322)**
    *   **内容**：为 Web Shell 的非本机网络监听器增加了带过期机制的二维码配对功能，提升了在局域网或远程场景下配对的安全性和易用性。

8.  **[[WIP] feat(extensions): 从目录加载部署管理的扩展 (PR #12183)](https://github.com/QwenLM/qwen-code/pull/12183)**
    *   **内容**：新增 `--managed-extensions` 参数，允许运维人员将预定义的扩展放置在特定目录中，供所有用户共享，适用于企业级部署。

9.  **[[WIP] feat(web-shell): 管理仓库的 Worktrees (PR #12154)](https://github.com/QwenLM/qwen-code/pull/12154)**
    *   **内容**：在 Web Shell 的 Git 对话框中新增第四页“Worktrees”，提供可视化的 Git Worktree 管理界面，方便并行开发。

10. **[[WIP] fix(web-shell): 跨页面刷新保留引用标签 (PR #12404)](https://github.com/QwenLM/qwen-code/pull/12404)**
    *   **内容**：修复了用户发送的文件、MCP 或扩展引用标签在刷新页面后丢失的问题，改进了会话体验的持久性。

---

## 功能需求趋势

综合近期的 Issues 动态，社区关注的三大功能方向为：

1.  **会话管理与多代理架构**：在单个主机内高效管理多个会话，并构建具备独立环境、持久状态和可恢复能力的“托管代理”体系，是社区最关注的前沿方向。相关讨论(P1/P2级别)频繁出现。
2.  **集成与生态扩展**：除了基础的 MCP 集成（支持更大App、共享输出），社区对**SSH工作区**、**Feishu/Lark等第三方通道的富媒体支持**，以及**CI/CD和容器(Dev Containers)集成**的需求日益增长。
3.  **用户界面与交互体验**：桌面端**字体调整**、会话概览页对**无工作区会话的支持**、以及**国际化**（如会话摘要语言）等基础但影响广泛的体验优化，是持续存在且高频的需求。

---

## 开发者关注点

1.  **macOS 兼容性痛点**：终端 PTY 完全不可用是当前最大的单一痛点，阻塞了 macOS 用户在 Web Shell 中使用终端的能力。
2.  **Remote-SSH 功能回归**：Companion 0.24.2 版本在 Remote-SSH 模式下会话创建失败，影响了使用该连接方式的开发者的核心工作流。
3.  **Windows 平台构建问题**：CI 脚本的跨平台兼容性不足，导致 Windows 安装包发布失败，影响了 Windows 用户对新功能的获取。
4.  **安全与权限**：社区开发者对 shell 命令窗口（如 PowerShell 在 Windows daemon 中被拒绝）的权限判定逻辑提出了质疑，并关注沙箱环境（bubblewrap）的强化。
5.  **版本发布质量**：频繁的夜间构建失败（如 #12382, #12401）和未发布的 Windows 包，表明发布流水线的健壮性和自动化测试需要加强。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

# DeepSeek TUI 社区动态日报 ｜ 2026-09-22

## 📰 今日速览

项目 `Codewhale`（即 DeepSeek TUI 的 Rust 实现）昨日迎来一轮密集修复：8 项 dogfooding 发现的 Bug 一次性合入，Anthropic 并行工具调用的数据重复问题已解决，遗留的根级 `base_url` 配置导致的路由错误被彻底清理。同时，社区提出了可插拔 Agent 记忆、计算机使用插件等前瞻性功能需求。CI 健康度在上周 130 次运行中 106 次为红色，当前维护者正全力冲刺 0.10.0 稳定性。

---

## 🚀 版本发布

过去 24 小时无新 Releases。

---

## 🔥 社区热点 Issues（10 条）

### 1. [#6184] Engine 中途静默冻结——用户消息被持久化但无响应
- **状态**：OPEN｜作者：bevis-wong｜更新：2026-09-21｜评论：8
- **重要性**：**核心稳定性问题**。长时间、工具密集的会话中引擎停止生成输出，无错误日志、无崩溃。用户输入被保存但从不回复。严重影响生产使用。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6184

### 2. [#6050] 可插拔 Agent 记忆：通用后端 seam + causal-memory/mem0 参考实现
- **状态**：OPEN｜作者：idling11｜更新：2026-09-21｜评论：5
- **重要性**：社区强烈希望引入第三方记忆后端（如 mem0 或因果记忆）。当前仅内置 `Native`/`Off` 两种，缺乏扩展性。这一特性将允许用户对接外部存储或知识图谱。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6050

### 3. [#5856] 计算机使用插件：live-install receipt + first look-act loop
- **状态**：OPEN｜作者：Hmbown｜更新：2026-09-21｜评论：6
- **重要性**：内置计算机使用（Computer Use）能力的构建。当前讨论聚焦于如何在不额外安装插件的情况下发现并启用内置 bundle，是 Agent 自动化能力的重大增强。
- **链接**：https://github.com/Hmbown/Codewhale/issues/5856

### 4. [#6378] Anthropic 提供者：并行工具调用产生虚假的 "tool call was not executed" 结果
- **状态**：CLOSED（已修复）｜作者：bronze1man｜更新：2026-09-21｜评论：2
- **重要性**：当模型返回多个并行 `tool_use` 时，第二及之后的工具调用会被重复发送一个失败占位符，导致模型收到矛盾信息。该 Bug 已被 PR #6387 修复。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6378

### 5. [#6374] 上下文预算守卫：1.5× 膨胀估算导致 131k 路由在 ~65k 真实输入时被拒绝
- **状态**：CLOSED｜作者：7jrxt42BxFZo4iAnN4CX｜更新：2026-09-21｜评论：2
- **重要性**：三个缺陷叠加：估算膨胀、提示的解决不可用、守卫触发的消息误导。属于静默破坏性 Bug，已修复。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6374

### 6. [#6296] 子代理继承计算机使用：验证者子代理在受限 shell 中通过宿主终端绕过限制
- **状态**：CLOSED｜作者：Hmbown｜更新：2026-09-21｜评论：1
- **重要性**：安全漏洞——`test` 角色的子代理通过继承的计算机使用能力，在宿主终端中输入命令绕过受限 shell。修复后需确保子代理不继承宿主能力。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6296

### 7. [#6394] 删除遗留根级 `base_url`，迁移至 `[providers.<name>] base_url`
- **状态**：OPEN｜作者：Hmbown｜更新：2026-09-21｜评论：0
- **重要性**：遗留配置 `base_url` 是 DeepSeek 字段，会被其他路由继承，导致使用小米 MiMo 等非 DeepSeek 提供者时 401 错误。**配置清理** 有助于减少隐式继承问题。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6394

### 8. [#6227] Pet 一致性测试：Rust 核心与规范 TypeScript 在 8 个通道中 6 个偏离（portable 红色）
- **状态**：CLOSED｜作者：Hmbown｜更新：2026-09-21｜评论：1
- **重要性**：Rust 实现的 Pet（宠物？）状态机与 TypeScript 参考实现存在字段级差异，导致一致性测试 red。修复后 CI 应恢复。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6227

### 9. [#6224] Windows: pet_watch 测试 `output_failures_do_not_stop_the_world` 断言失败
- **状态**：CLOSED｜作者：Hmbown｜更新：2026-09-21｜评论：2
- **重要性**：Windows 平台特定测试失败，因音频路径记录前就断言 `sink.failed()`。属于平台兼容性问题，已修复。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6224

### 10. [#6385] 健康摘要 2026-09-21 —— 上周 CI 130 次运行中 106 次红色
- **状态**：OPEN（自动化）｜作者：devin-ai-integration[bot]｜更新：2026-09-21｜评论：1
- **重要性**：自动化健康检查指出 `main` 分支 CI 极不稳定（81.5% 红色）。建议优先修复 CI。
- **链接**：https://github.com/Hmbown/Codewhale/issues/6385

---

## 🔧 重要 PR 进展（10 条）

### 1. [#6395] fix(config): 阻止遗留根级 base_url 成为路由端点
- **作者**：Hmbown｜状态：OPEN｜更新：2026-09-21
- **内容**：输入合法的小米 MiMo token 时因继承了 `base_url="https://api.deepseek.com"` 导致 401。此 PR 清除根级继承，改为按 provider 配置。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6395

### 2. [#6392] 8 项 dogfooding 修复——未生效的门控和一个从未上线的特性
- **作者**：Hmbown｜状态：OPEN｜更新：2026-09-21
- **内容**：包含 Shift+Tab 在 Plan 中无法修改权限、多步骤审批中助手视图未提交等真实使用中发现的问题。每个修复都附带回归测试。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6392

### 3. [#6387] fix(anthropic): 在 dangling-use 修复前，将拆分工具结果折叠为一个用户轮次
- **作者**：Hmbown｜状态：CLOSED｜更新：2026-09-21
- **内容**：修复 #6378：并行工具调用时第二个调用被发送两个 `tool_result`（一个虚假失败 + 真实结果）。此 PR 确保每个工具调用只发送一个结果。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6387

### 4. [#6386] feat(tasks): 声明任务线程启动时的审批姿态
- **作者**：gaord｜状态：CLOSED｜更新：2026-09-21
- **内容**：任务线程从未拥有明确的审批姿态，导致 `POST /v1/tasks` 可能启动一个无审批控制的任务。此 PR 引入 `permission_posture` 声明。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6386

### 5. [#6388] fix(tasks): 在任务准入时拒绝线程会拒绝的姿态
- **作者**：Hmbown｜状态：CLOSED｜更新：2026-09-21
- **内容**：#6386 的后续——`add_task_with_id` 未验证姿态，将其推迟到工作线程运行。此 PR 在存入前进行验证，避免无效姿态导致静默失败。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6388

### 6. [#6390] chore(tui): 命名 `windows::core::BOOL` 并移除直接依赖
- **作者**：Hmbown｜状态：CLOSED｜更新：2026-09-21
- **内容**：移除不必要的 `windows-core` 直接依赖（0.62→0.100 升级被 supersede）。简化依赖树。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6390

### 7. [#6393] Draft: echolocation, token diet, and fork-prefix cache inheritance
- **作者**：AdityaVG13｜状态：OPEN｜更新：2026-09-21
- **内容**：设计讨论稿，涉及回声定位、Token 精简及分叉前缀缓存继承。尚未准备合并，但方向已获维护者初步认可。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6393

### 8. [#6384] fix(review): 在“请求失败”下方打印提供商失败，并在 review 工作流中分类
- **作者**：Hmbown｜状态：CLOSED｜更新：2026-09-21
- **内容**：Codewhale 审查机器人自某个提交后持续失败，仅显示一行错误。此 PR 输出具体提供商错误（如 HTTP 401）并分类，便于调试。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6384

### 9. [#6383] 0.10.0 follow-up 4: 输入账单的端点标识，预览扫描的后扫描回退
- **作者**：Hmbown｜状态：CLOSED｜更新：2026-09-21
- **内容**：两个后合并审查发现：1) 输入账单的 carry-over 应以整个解析的端点为键，而非仅路由；2) 预览扫描失败时提供 fallback。每个修复都附带证据。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6383

### 10. [#6389] fix(tui): 在 resume 选择器预览中隐藏内部运行时流量
- **作者**：Hmbown｜状态：CLOSED｜更新：2026-09-21
- **内容**：`/resume` 会话历史预览渲染了所有持久化的消息，包括运行时控制流量（以 `role="user"` 存储）。此 PR 过滤这些内部消息，提升预览可读性。
- **链接**：https://github.com/Hmbown/Codewhale/pull/6389

---

## 📊 功能需求趋势

从近一周的 Issues 和 PR 中可看出社区最关注以下方向：

- **Agent 可扩展性**：可插拔记忆后端（#6050）、计算机使用插件（#5856）、子代理权限控制（#6296）。
- **稳定性与健壮性**：引擎静默冻结（#6184）、上下文预算膨胀估算（#6374）、并行工具调用数据重复（#6378）。
- **配置与兼容性**：遗留 `base_url` 迁移（#6394）、Windows 平台测试修复（#6224）、Pet 一致性测试对齐（#6227）。
- **性能优化**：Token 精简（#6393 draft）、fork-prefix 缓存继承（#6393）。
- **安全与审计**：子代理继承宿主能力漏洞修复（#6296）、CI 健康度监控（#6385）。

---

## 💡 开发者关注点

- **引擎非预期静默**：大量用户反馈引擎在长时间运行后停止输出且无任何日志，这是当前最严重的痛点。
- **配置继承陷阱**：根级 `base_url` 隐性继承导致非 DeepSeek 提供者无法使用，开发者需手动排查。
- **CI 不稳定**：主分支 CI 红色率高达 81.5%，影响开发者贡献信心，维护者需优先修复 CI 管道。
- **Anthropic 并行调用缺陷**：虽然昨日已修复，但此前用户可能因不完整的结果而误判模型能力，值得关注。
- **计算机使用安全**：子代理继承宿主能力可能引发越权行为，未来需更严格的权限隔离机制。
- **记忆系统单一**：当前仅内置记忆存储，社区期待支持外部知识库/记忆服务以构建持久化 Agent。

> 日报仅基于公开 GitHub 数据生成，不包含未公开的内部讨论。所有链接指向原始 Issue/PR。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*