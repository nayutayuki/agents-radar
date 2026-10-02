# AI CLI 工具社区动态日报 2026-10-02

> 生成时间: 2026-10-02 01:48 UTC | 覆盖工具: 9 个

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

好的，作为专注于 AI 开发工具生态的资深技术分析师，我已审阅今日所有主流 AI CLI 工具的社区动态。现为您呈现一份横跨多个生态的深度对比分析报告。

---

# AI CLI 工具生态周报：横向对比分析 (2026-10-02)

## 1. 生态全景

当前 AI CLI 工具生态正经历一场“由外而内”的深刻变革。一方面，**插件/扩展系统 (Mods, Plugins)** 成为各大工具厂商争夺开发者生态的核心战场，标志着工具从“单体 Agent”向“Agent 平台”的范式转变。另一方面，社区关注的焦点从单一的功能实现，转向了更深层次的 **可靠性、可控性、安全性以及成本透明度**。各工具在快速迭代功能的同时，也暴露出 Agent 行为不可预测、核心回归 Bug 频发、平台兼容性不足等共性问题，这表明整个行业正从“能做什么”的兴奋期，步入“如何做好”的成熟期。

## 2. 各工具活跃度对比

| 工具 | 高热度 Issues | PR 进展 | 版本发布 | 社区活跃度 (基于数据) | 总体评估 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 10 (含 #91870 史诗级) | 5 | 2.1.287 | 极高，聚焦于 Mods 讨论和核心功能回归 | **创新驱动，但稳定性波动大** |
| **OpenAI Codex** | 10 | 10 | 0.160.0 及多个 Alpha | 极高，Pets 争议和 Windows 问题突出 | **功能激进，平台适配成短板** |
| **Gemini CLI** | 10 | 10 | Nightly | 高，集中于子代理 Bug 修复 | **稳健修复，向 Agent 可靠性发力** |
| **GitHub Copilot CLI** | 10 | 1 | 3 个补丁 (91, 91-1, 92-0) | 中等，企业级用户反馈量大 | **面向企业，稳定性仍是核心诉求** |
| **Kimi Code CLI** | - | - | - | **几乎无活动** | - |
| **OpenCode** | 10 | 10 | 无 | 高，计费问题和模型兼容性是热点 | **计费与模型兼容性是信任危机** |
| **Pi** | 10 | 10 | **1.0.0 正式版** | 高，围绕全屏模式适配问题多 | **正式版发布后，终端兼容性挑战升级** |
| **Qwen Code** | 10 | 10 | Nightly | 高，聚焦于 Managed Agent 架构演进 | **架构先行，向企业级平台演进** |
| **DeepSeek TUI** | 5 | 23 | 无 | 中等，集中于多贡献者 PR 合并 | **受限于贡献者活跃度，稳定性修复为主** |

*注：活跃度基于上述日报中筛选出的高热度 Issues 和重要 PR 数量。*

## 3. 共同关注的功能方向

多个工具的社区不约而同地聚焦于以下需求，这已成为行业级痛点：

- **Agent 行为的可靠性与可控性：** 这是今日报告中的核心议题，几乎所有工具都遇到了类似问题。
    - **虚假成功反馈：** **Gemini CLI (#22323)** 和 **OpenCode (#52378)** 的子代理（Subagent）在任务失败（如达到轮次上限或调用错误）时，仍向父代理报告“成功”，造成误导。
    - **无响应与挂起：** **Gemini CLI (#21409)** 的通用代理（Generalist Agent）会无限期挂起。**Claude Code (#83848)** 的后台子代理会间歇性停滞。
    - **自主性不足：** **Gemini CLI (#21968)** 的模型不会主动使用用户明确定义的自定义技能和子代理，需要强制指令。

- **插件/扩展生态系统的构建：**
    - **Claude Code** 发布的 **“Claude Mods”** 系统 (#91870) 是整个行业的风向标，它允许插件修改模型的深层行为。
    - **OpenCode** 的 **“You should know” Mod** 作为一个系统级“纠错员”，代表了插件从“功能增加”向“协作增强”的尝试。
    - **OpenCode (#49389)** 社区正在呼吁开放核心会话能力给插件 API，这反映了开发者不满足于表层插件，渴望更深度的集成。

- **模型行为的一致性与可预测性：**
    - **Claude Code (#98679)** 的 Opus 5.5 和 **OpenCode (#13768)** 的 Claude Opus 4.6 都出现了模型侧未公布的行为偏移，如思考时间变长、拒绝预填充等。这引发了社区对模型稳定性与透明度的担忧。

- **安全与权限的精细化控制：**
    - **GitHub Copilot CLI (#953, #4989)** 企业用户强烈要求限制 OAuth 权限范围和 MCP 白名单匹配。
    - **OpenCode (#22672)** 社区提议 Agent 应主动阻止破坏性 Git 操作。
    - **Gemini CLI (#19873)** 提出了零依赖 OS 沙箱的需求，旨在平衡安全性与模型能力。

- **数据驻留与合规：**
    - **GitHub Copilot CLI (#4938)** 报告 GHEC 数据驻留租户的认证仍然错误地路由到公共端点，这是企业采用的关键障碍。

## 4. 差异化定位分析

| 工具 | 核心定位 | 技术路线 / 特色 | 目标用户 / 场景 | 主要竞争力 |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | **Agent Platform** | **深度 Plugin 体系 (Mods)**，后设认知能力 | 高级开发者、内部工具构建者 | 模型智能与可扩展性的结合 |
| **OpenAI Codex** | **全能型 Agent** | 激进的功能迭代（Pets, MCP）与强大的云端集成 | 追求新体验、深度使用 OpenAI 生态的开发者 | 功能丰富度、模型先进性 |
| **Gemini CLI** | **Google 生态 Agent** | 强调子代理 (Agent) 架构，稳健修复 | **Google Cloud 用户、Android 开发者** | 与 Gemini 模型及 GCP 服务的深度整合 |
| **GitHub Copilot CLI** | **企业级安全 Agent** | **关注企业合规、数据驻留、策略管理** | 大型企业、受监管行业的开发者 | GitHub 生态整合、安全与合规能力 |
| **OpenCode** | **开源社区 Agent** | **模型兼容性与成本控制 (缓存、计费)** | 偏好开源、对成本敏感的技术用户 | 模型中立性、社区驱动的成本优化 |
| **Pi** | **终端体验优先** | **全屏 TUI 模式，丰富的 Provider 支持** | 重度终端用户、多模型切换者 | 纯终端交互的极致体验与稳定性 |
| **Qwen Code** | **下一代 Agent 架构** | **Managed Agent 架构，面向企业级** | 希望构建复杂、可伸缩 Agent 应用的开发者 | 架构前瞻性、高可用与安全隔离设计 |
| **DeepSeek TUI** | **社区驱动的基础 Agent** | 插件生态初步构建，社区贡献者活跃 | 中小型团队、个人开发者 | 简单易用，专注于社区反馈的快速修复 |

## 5. 社区热度与成熟度

- **成熟稳定型（企业级）：** **GitHub Copilot CLI** 和 **Gemini CLI** 社区反馈更聚焦于企业级痛点（如数据驻留、策略管理），功能迭代趋于稳健，Bug 修复占主流，表明产品已进入成熟期，核心功能稳定，正在打磨边缘场景。
- **高速成长型：** **Claude Code** 和 **OpenAI Codex** 社区热度最高，创新功能不断涌现，但伴随而来的是较多影响用户体验的 Bug 回归和平台兼容性问题。这表明它们在快速迭代功能的同时，稳定性和质量保障面临压力。
- **快速迭代型：** **Qwen Code** 社区虽活跃，但其核心议题围绕着宏大的架构变更（Managed Agent）展开，显示出其正从功能性项目向平台级产品快速演进，内部重构和架构升级是当前主旋律。
- **社区驱动型：** **OpenCode** 和 **DeepSeek TUI** 作为开源项目，社区反馈直接驱动了修复方向。OpenCode 的关注点在模型兼容性和成本，DeepSeek TUI 则依赖于个别核心贡献者的 Fix PR，整体受限于贡献者活跃度。

## 6. 值得关注的趋势信号

1.  **“Agent 可靠性” 成为行业生死线：** 所有工具都面临着 Agent 逻辑的“不诚实”（虚假成功）、“不作为”（挂起）和“乱作为”（自主性差）问题。这证明当前的 Agent 架构（特别是子代理/多Agent协作）仍未解决可靠性难题，是未来技术突破的关键方向。**开发者应警惕：依赖自动化的多 Agent 工作流可能比预想的要脆弱得多。**

2.  **插件生态决定长期护城河：** Claude Code 的 Mods 系统和 Copilot CLI 的 MCP 集成，标志着工具之争已升级为平台之争。谁能率先构建一个健康、强大且易于使用的插件生态，谁就能锁定更多开发者和使用场景。

3.  **安全与合规不再只是“附加项”，而是“必备项”：** 企业对 OAuth 精简化、数据驻留、沙箱隔离的需求日益强烈。没有强大企业级安全模型的工具，将在进入大型组织时面临壁垒。Gemini CLI 和 Qwen Code 的架构设计正在此方向上发力。

4.  **“成本可见性” 与 “模型行为预算” 成为新关注点：** OpenAI Codex (#9980) 中费用估算偏差和 OpenCode (#29363) 中输出 Token 被静默限制，表明用户对成本控制的需求已从“能用就行”转变为“精打细算”。未来工具必须提供更透明、更精细的 Token 消耗和预算控制能力。

5.  **平台兼容性是最大的“隐形门槛”：** **Windows 和 Linux 在 CLI 工具上的体验劣势正在集中爆发。** OpenAI Codex、Gemini CLI、Pi 都出现了严重的 Windows/macOS 安全更新或 Linux Wayland/tmux 兼容性问题。这提示开发者，跨平台一致性是当前 CLI 工具生态中一个被严重低估但极其重要的挑战。

**对技术决策者的建议：**
在选择 AI CLI 工具时，除了关注模型能力和功能，应优先考察**工具的 Agent 可靠性（有无虚假成功报告的前科）、企业级安全合规能力、以及社区的活跃度和对 Bug 的响应速度**。如果您的团队高度依赖自动化流程，那么一个更新稳健、Bug 较少的工具（如当前的 Gemini CLI）可能比一个功能激进但稳定性堪忧的工具（如 OpenAI Codex）更合适。如果您的目标是构建内部工具平台，那么 Claude Code 的 Mods 系统值得重点关注。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，作为一名专注于 Claude Code 生态的技术分析师，以下是我基于 `anthropics/skills` 仓库截至 2026-10-02 的数据生成的社区热点报告。

---

## Claude Code Skills 社区热点报告 (截止 2026-10-02)

### 1. 热门 Skills 排行

以下为当前社区讨论热度与关注度最高的 Skills，主要体现在 Pull Requests 的活跃讨论中。

| 排名 | Skill (PR) | 功能摘要 | 社区讨论焦点与状态 |
| :--- | :--- | :--- | :--- |
| 1 | **skill-creator (fix)** <br> [PR #1298](https://github.com/anthropics/skills/pull/1298) | 修复 skill-creator 工具链：隔离触发评估、处理 Windows 兼容性及运行时失败。 | **核心工具稳定性**。社区高度关注官方开发工具的可靠性，尤其是在多平台（Windows vs macOS/Linux）下的兼容性问题，以及评估系统（evaluation）的准确性。**状态：Open** |
| 2 | **mcp-builder (fix)** <br> [PR #1742](https://github.com/anthropics/skills/pull/1742) | 修复 MCP Builder 对 `mcp>=2` 新版本库的兼容性，支持自定义HTTP头。 | **依附系统升级**。社区紧跟上游依赖（MCP协议）的更新，确保技能生成工具能正常运行。这表明社区非常依赖于一个健康、更新的基础工具链。**状态：Open** |
| 3 | **notion-spec-to-implementation** <br> [PR #1245](https://github.com/anthropics/skills/pull/1245) | 将 Notion 中的规格文档转化为可执行的实现任务，并跟踪进度。 | **工作流自动化**。将项目管理工具（Notion）与代码实现深度绑定，是社区对“AI + 项目管理”整合的典型需求。讨论集中在如何精确转换复杂规格和任务拆解逻辑。**状态：Open** |
| 4 | **proofcore-contract-auditor** <br> [PR #1771](https://github.com/anthropics/skills/pull/1771) | 自动审计 Solidity 和 Rust 智能合约，并将审计证明锚定到 TON 区块链。 | **Web3 & 安全**。一个高度专业化的垂直领域技能，代表了社区在特定行业（区块链、安全审计）中的创新尝试。其零存储Merkle协议和链上锚定是亮点。**状态：Open** |
| 5 | **document-typography** <br> [PR #514](https://github.com/anthropics/skills/pull/514) | 防止AI生成文档中的排版问题，如孤行、寡段和编号错位。 | **文档质量提升**。看似细小的排版问题，却是所有AI生成文档的通用痛点。社区对提升“最终交付物”品质有强烈需求，追求从“能用”到“好看”的转变。**状态：Open** |
| 6 | **AWT (AI Watch Tester)** <br> [PR #822](https://github.com/anthropics/skills/pull/822) | 一个AI驱动的端到端测试工具，能零代码生成测试用例，并具备视觉测试能力。 | **自动化测试**。社区积极探索利用AI的视觉和浏览器控制能力来自动化 E2E 测试。讨论点在于如何保证零代码生成的测试用例的可靠性和覆盖率。**状态：Open** |
| 7 | **blast-radius** <br> [PR #1776](https://github.com/anthropics/skills/pull/1776) | 在大规模或破坏性写操作（如归档用户、删除数据行）前执行的风险检查清单。 | **安全与操作规范**。社区关注AI agent的“行为边界”，特别是在执行危险操作时增加防护机制，确保其行为是安全且符合预期的。**状态：Open** |

### 2. 社区需求趋势

从社区 Issues 的讨论中，可以提炼出以下几大核心需求方向：

1.  **安全与信任 (Security & Trust)**：社区最关心的问题是**技能的安全性**。Issue #492 对社区技能假借官方名义分发表示担忧，认为这可能造成信任边界的滥用。用户希望官方建立更清晰的技能来源审核和信任机制，尤其是在企业级应用场景下。
2.  **协作与共享 (Collaboration & Sharing)**：用户迫切希望能在**组织内高效共享 Skills**。Issue #228 的16条评论和8个👍表明，当前的“下载-发送-上传”流程过于繁琐，社区期待一个更直接的组织级技能库或分享链接功能。
3.  **工具链可靠性与可用性 (Toolchain Reliability)**：大量 Issue 指向了 `skill-creator` 和 `run_eval.py` 等核心工具链的问题。例如，评测工具 0% 触发率 (Issue #556) 导致技能无法被正确调用，以及安装插件重复 (Issue #189) 导致上下文窗口浪费。**开发者工具的可信度是社区贡献技能的前提。**
4.  **性能与效率 (Performance & Efficiency)**：社区开始对技能本身带来的性能开销提出要求。Issue #1487 指出 `claude-api` 技能会注入大量 Token 撑爆上下文窗口。这说明用户不仅关注技能功能，也开始关注其资源消耗和设计精良度。
5.  **特定领域深度应用 (Vertical Applications)**：社区不再满足于通用功能，而是探索更具深度的行业应用。`proofcore-contract-auditor` (Web3) 和 `scnet-hpc` (高性能计算) 这类高度专业化的技能提案，代表了社区从“广撒网”向“专业化深耕”的趋势。

### 3. 高潜力待合并 Skills

以下是讨论活跃、需求明确、具有较高实用价值，目前仍处于 Open 状态的 PR，预计近期有较大可能落地：

- **[PR #1245] notion-spec-to-implementation**：将项目管理的核心环节与代码开发打通，需求明确，潜力巨大。
- **[PR #822] AWT (AI Watch Tester)**：填补了 AI 驱动 E2E 测试的空白，技术方向新颖，与“AI Agent”的概念契合度高。
- **[PR #1776] blast-radius**：解决了“AI Agent 如何在危险操作前自我检查”的关键问题，对于提升 Agent 的行为安全至关重要。
- **[PR #514] document-typography**：虽然功能点小，但精准解决了所有文档类技能的“最后一公里”问题，适用面极广。
- **[PR #1771] proofcore-contract-auditor**：代表了社区在垂直行业的创新探索，若合并将吸引大量 Web3 开发者。

### 4. Skills 生态洞察

**一句话总结：当前社区在 Skills 层面最集中的诉求是：在确保核心开发工具链（skill-creator）稳定可靠和多平台兼容的基础上，追求更安全、可协作、更高效的工作流自动化与特定领域应用。**

---

好的，作为一个专注于AI开发工具的技术分析师，我将根据您提供的GitHub数据，为您生成一份结构清晰、内容专业的Claude Code社区动态日报。

---

# 云中日报：Claude Code 社区动态 | 2026-10-02

### 今日速览

1.  **重大更新：Mods 时代来临**：Claude Code 发布了 `v2.1.287`，正式引入 **Claude Mods（插件系统）**，允许插件修改更深层次行为。其中内置的 `You should know` Mod 作为“第二双眼睛”，旨在避免开发者与 Claude 遗漏关键问题。
2.  **社区热议：可扩展性与可用性问题并存**：关于 Mods 的史诗级 Issue [#91870] 是社区最热话题，讨论数超过230条。同时，GitHub 连接器功能出现严重回归 [#71542] 和 Auto 模式下的安全分类器问题 [#97854] 也引发了大量关注，成为开发者当务之急的痛点。
3.  **模型行为波动引担忧**：有用户报告 Claude Opus 5.5 模型在10月1日出现行为异常，包括思考时间变长、输出增多但判断力下降的情况 [#98679]，这引发了社区对模型稳定性的讨论。

---

### 版本发布

- **Claude Code v2.1.287**
    - **发布重点：**
        - **新增 “Claude Mods”（插件系统）**：这是本次更新的核心，标志着 Claude Code 在可扩展性上迈出巨大一步。Mods 不局限于简单的提示或技能，而是能够更深入地修改 Claude 的行为。
        - **内置 Mod：“You should know”**：一个非常实用的内置插件。它会启动一个“副手代理”在后台监控你的工作，标记你可能或 Claude 本身遗漏的关键信息。可以通过 `/plugin enable cc-plugin-you-should-know@builtin` 命令开启。

    - **详细分析：** `v2.1.287` 的发布明确了 Anthropic 在 Agent 可扩展性上的战略方向。通过 Mods，开发者可以构建更强大、更定制化的辅助工具，而 `You should know` 更像是系统级的“安全气囊”和“纠错员”，旨在提升协作质量。

---

### 社区热点 Issues

社区热度集中在 **Mods 的深度讨论** 与 **核心功能（GitHub集成、安全）的回归问题**。

1.  **[#91870] Mods - make Claude 10x more extensible**
    - **重要性：** ⭐⭐⭐⭐⭐
    - **说明：** 这是一个关于 Mods 功能的“史诗级”议题，社区反馈的核心阵地。讨论了 Mods 的愿景、设计思路和未来方向。拥有高达230条评论和130个点赞，是当前社区最关注的功能。
    - **链接：** [anthropics/claude-code Issue #91870](https://github.com/anthropics/claude-code/issues/91870)

2.  **[#71542] GitHub connector Regression**
    - **重要性：** ⭐⭐⭐⭐⭐
    - **说明：** 一个严重的回归问题，导致 GitHub 连接器虽然能成功链接仓库，但 Claude 无法读取**任何**仓库（公开或私有）的内容。这直接影响依赖 GitHub 代码库进行开发的用户，评论数高达68条，点赞64个。
    - **链接：** [anthropics/claude-code Issue #71542](https://github.com/anthropics/claude-code/issues/71542)

3.  **[#97854] Auto 模式下安全分类器故障**
    - **重要性：** ⭐⭐⭐⭐
    - **说明：** 在 Auto 模式下，服务器端的安全分类器偶发地不对 Bash 等工具的使用做出判决，导致 `Bash` 和 `ScheduleWakeup` 工具完全被阻塞。此问题影响了自动化工作流的可靠性。
    - **链接：** [anthropics/claude-code Issue #97854](https://github.com/anthropics/claude-code/issues/97854)

4.  **[#84862] 请求增加 Passkey (WebAuthn) 登录支持**
    - **重要性：** ⭐⭐⭐⭐
    - **说明：** 用户希望在所有界面上支持 Passkey 登录，这是对安全性和无密码体验的强烈呼声。虽然只有10条评论，但获得了84个点赞，表明这是一个广泛的用户需求。
    - **链接：** [anthropics/claude-code Issue #84862](https://github.com/anthropics/claude-code/issues/84862)

5.  **[#83848] 后台子代理间歇性停滞**
    - **重要性：** ⭐⭐⭐⭐
    - **说明：** 使用新建的子代理类型时，后台代理偶尔会不输出最终结果就结束任务，但框架却报告 `status: completed`。这严重影响了多代理任务的可靠性，是 Agent 系统的重要 bug。
    - **链接：** [anthropics/claude-code Issue #83848](https://github.com/anthropics/claude-code/issues/83848)

6.  **[#98184] 网络变化后请求挂起 184 秒**
    - **重要性：** ⭐⭐⭐
    - **说明：** 特定于 Linux 平台的bug。当网络发生变化（如Wi-Fi切换）后，下一次 API 请求会在一个已失效的连接上挂起长达184秒，严重影响开发效率和体验。
    - **链接：** [anthropics/claude-code Issue #98184](https://github.com/anthropics/claude-code/issues/98184)

7.  **[#81024] VS Code 扩展不支持 git-worktree 会话**
    - **重要性：** ⭐⭐⭐
    - **说明：** VS Code 扩展的会话列表硬编码了 `includeWorktrees: false`，导致用户的 `git-worktree` 会话无法显示在列表中。对于使用多 worktree 工作流的开发者，这是一个显著的效率障碍。
    - **链接：** [anthropics/claude-code Issue #81024](https://github.com/anthropics/claude-code/issues/81024)

8.  **[#98836] spawn_task 芯片通过“云”模式丢失提示**
    - **重要性：** ⭐⭐⭐
    - **说明：** 通过 `spawn_task` 工具创建的待办任务芯片，如果通过“cloud”模式（而非本地 worktree）启动，其生成的完整 `prompt` 会丢失。这影响了云优先的协作工作流。
    - **链接：** [anthropics/claude-code Issue #98836](https://github.com/anthropics/claude-code/issues/98836)

9.  **[#98679] Claude Opus 5.5 行为偏移**
    - **重要性：** ⭐⭐⭐
    - **说明：** 用户报告自10月1日起，Claude Opus 5.5 的行为发生统计上显著的变化：思考时间加倍、输出增长60%，但任务判断力却下降。这可能暗示模型侧发生了一个未公布的变化或问题。
    - **链接：** [anthropics/claude-code Issue #98679](https://github.com/anthropics/claude-code/issues/98679)

10. **[#89827] 日语输出中 Markdown 强调分隔符损坏**
    - **重要性：** ⭐⭐
    - **说明：** 一个影响非英语用户的本地化问题。Claude 在生成日语文本时，处理 CJK 标点与 Markdown 强调（`**`）的逻辑存在 bug，导致渲染格式错误。
    - **链接：** [anthropics/claude-code Issue #89827](https://github.com/anthropics/claude-code/issues/89827)

---

### 重要 PR 进展

1.  **[#16632] Fix: shell operators safety warning**
    - **概述：** 修复了特定 shell 命令会触发不必要安全警告的问题。
    - **链接：** [anthropics/claude-code PR #16632](https://github.com/anthropics/claude-code/pull/16632)

2.  **[#62592] Update security-guidance plugin**
    - **概述：** 对安全指导插件进行了文档更新。
    - **链接：** [anthropics/claude-code PR #62592](https://github.com/anthropics/claude-code/pull/62592)

3.  **[#94847] diff: auto-open pane only when have file**
    - **概述：** 修复了 `diff` 面板在无文件变更时仍会打开的问题。现在，只有在首次成功编辑文件后，`diff` 面板才会自动弹出。
    - **链接：** [anthropics/claude-code PR #94847](https://github.com/anthropics/claude-code/pull/94847)

4.  **[#98018] mods: revert two changes**
    - **概述：** 回滚了 Mods 中的两项变化，涉及 `agents-md` 和 `diff` 的强制颜色行为，使它们回归到之前更稳定的版本。
    - **链接：** [anthropics/claude-code PR #98018](https://github.com/anthropics/claude-code/pull/98018)

5.  **[#98555] diff: dialog opens every file**
    - **概述：** 修复了 `/diff` 对话框在打开时会自动展开所有文件的操作，以及关闭对话框后无信息输出的问题，改善了交互体验。
    - **链接：** [anthropics/claude-code PR #98555](https://github.com/anthropics/claude-code/pull/98555)

---

### 功能需求趋势

1.  **深度可扩展性 (Agents & Plugins)**
    - **趋势：** 社区对 Mods 系统的兴趣和反馈极其热烈。开发者不再满足于简单的提示词注入，而是希望创建能够深度集成、修改 Claude 底层行为的插件，以实现复杂任务自动化（如后台代理、安全监控代理等）。
    - **相关 Issue：** #91870, #83848, #82858

2.  **安全性与身份验证**
    - **趋势：** 除了对基础功能安全的修复（如 #97854），社区对强身份验证（如 Passkey）的需求日益增长，同时对 GitHub 集成等核心功能的可靠性有极高要求。
    - **相关 Issue：** #84862, #71542, #97854

3.  **IDE 深度集成**
    - **趋势：** 用户对 IDE（特别是 VS Code）的集成体验要求越来越高。需求不仅停留在基本功能，而是希望获得与 CLI 版本同等甚至更优的体验，如 `git-worktree` 支持。
    - **相关 Issue：** #81024

4.  **模型行为的一致性与可预测性**
    - **趋势：** 用户对模型的任何行为变化都高度敏感。Opus 5.5 的行为偏移问题表明，开发者需要更稳定的模型表现和透明的变更日志。
    - **相关 Issue：** #98679, #98848, #98847

5.  **本地化与国际化**
    - **趋势：** 随着用户群扩大，对非英语语言（如日语、西班牙语）的本地化支持问题开始凸显。这包括模型语言偏好遵守和 Markdown 格式的跨语言兼容性。
    - **相关 Issue：** #89827, #95399, #98848

---

### 开发者关注点

1.  **GitHub 连接器可靠性**：Issue [#71542] 是过去24小时内最受关注的 bug，严重影响依赖 GitHub 进行代码管理的开发者。这是一个**高优先级**的回归问题，正在被大量用户验证。
2.  **Auto 模式下的安全误报/漏报**：Issue [#97854] 指出了 Auto 模式下安全限制的不可预测性，导致 `Bash` 工具完全不可用。这表明自动化工作流的鲁棒性仍有待加强。
3.  **Agent 系统的稳定性**：后台代理的间歇性停滞 [#83848] 和网络重试的高延迟 [#98184] 是开发者在使用高级功能（多代理、远程工作）时遇到的主要痛点。
4.  **Windows 平台的更新死锁**：Issue [#96942] 报告了 Windows 桌面版在更新时的死锁问题，这直接影响了用户的升级体验和系统稳定性。
5.  **“语言偏好”被忽略**：多名用户反馈 Claude 不能正确遵循语言偏好指令（如西班牙语 [98848]），以及在特定语境中使用不恰当的语言风格 [95399]。这影响了非英语用户的核心体验。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报（2026-10-02）

## 今日速览
- **Codex CLI 0.160.0 正式发布**，新增键盘可访问的“显示更多”浏览旧任务、全屏模式下选中行并中键粘贴、在项目外使用工作区默认启动会话等实用功能。
- **Windows 平台高频 bug 集中爆发**：sandbox 设置失败、启动卡住、dot 混合路径、环境变量丢失等问题引发大量反馈。
- **“Pets”桌面宠物功能争议持续**：#34349 (👍81) 和 #44546 (👍20) 两则 feature request 要求彻底禁用/移除 Pets，社区情绪强烈。

## 版本发布
过去 24 小时内发布了多个版本，重点更新如下：

### rust-v0.160.0 稳定版
- **浏览旧任务**：在 agent command center 中可通过键盘操作的“Show more”按钮浏览更早的任务。  
- **全屏模式粘贴**：在支持的 Linux X11 本地终端上，可选中转录文本并中键粘贴。  
- **外部项目启动**：支持在项目外使用工作区默认值启动会话。

### Alpha 版本
发布了 `0.162.0-alpha.2`、`0.162.0-alpha.1`、`0.161.0-alpha.7~13` 等多个 alpha 版本，未附带独立变更日志。

## 社区热点 Issues（共 30 条高评论 Issue，以下为 10 条最值得关注）

### 1. [#34349] 请求允许用户完全禁用 Pets 并移除菜单项
- **标签**：enhancement, app, pets  
- **评论**：24  |  👍：81  
- **摘要**：用户要求提供选项彻底禁用 Pets 功能，隐藏侧栏菜单项及所有 UI 相关元素。  
- **链接**：https://github.com/openai/codex/issues/34349

### 2. [#40858] Native subagent 忽略显式的 model_provider 覆盖
- **标签**：bug, CLI, custom-model, subagent, config  
- **评论**：20  |  👍：16  
- **摘要**：在 Codex CLI 0.149.1 中，父模型为 gpt-5.6-luna 时，子代理设置 MiniMax-M3 但 subagent 仍使用父模型 provider，模型覆盖失效。  
- **链接**：https://github.com/openai/codex/issues/40858

### 3. [#49729] Dot 无法在已保存项目中创建或跟进本地 Codex 任务
- **标签**：bug, app, app-server  
- **评论**：17  |  👍：2  
- **摘要**：Dot 可创建本地任务却无法选择已保存的 Codex App 项目，导致任务线程无法被 dot 读取或回复，破坏工作流。  
- **链接**：https://github.com/openai/codex/issues/49729

### 4. [#49497] Codex Web 首次消息失败：“Unable to determine project root”
- **标签**：bug, codex-web  
- **评论**：15  |  👍：24  
- **摘要**：在已发布的云端环境中提交首条消息时，UI 报错“Error submitting message”和“Unable to determine project root”，页面卡住。  
- **链接**：https://github.com/openai/codex/issues/49497

### 5. [#23999] Codex Desktop 侧栏聊天历史消失，更新后无法恢复隐藏对话
- **标签**：bug, app, session  
- **评论**：12  |  👍：3  
- **摘要**：macOS 上 Codex Desktop 侧栏聊天历史无故消失，最新更新后仍无法恢复已隐藏的聊天。  
- **链接**：https://github.com/openai/codex/issues/23999

### 6. [#43776] Windows 上 `.agents` 所有权问题破坏 sandbox 和浏览器控制
- **标签**：bug, windows-os, sandbox, app, browser  
- **评论**：11  |  👍：2  
- **摘要**：Codex 创建的 `.agents` 目录所有权异常，导致 sandbox 设置失败、内置浏览器无法控制。  
- **链接**：https://github.com/openai/codex/issues/43776

### 7. [#49488] Windows dot/Work 任务缺乏浏览器/桌面工具：MCP 启动失败
- **标签**：bug, windows-os, mcp, app, app-server, computer-use, browser  
- **评论**：11  |  👍：4  
- **摘要**：Windows 上 dot 发起的计算机任务缺少浏览器和桌面工具，MCP 服务持久性启动失败，跟进路径报错。  
- **链接**：https://github.com/openai/codex/issues/49488

### 8. [#49718] Windows 应用启动卡在 Logo 画面，sandbox 设置始终失败
- **标签**：bug, windows-os, sandbox, app, app-server  
- **评论**：8  |  👍：1  
- **摘要**：Windows 版 Codex Desktop 启动时渲染器错过初始“connected”状态导致卡 Logo，sandbox 设置因“only managed permission profiles can be enforced”失败。  
- **链接**：https://github.com/openai/codex/issues/49718

### 9. [#44546] 要求完全移除桌面宠物功能：造成不必要的压力和干扰
- **标签**：enhancement, app, pets  
- **评论**：7  |  👍：20  
- **摘要**：用户请求彻底移除 Pets 功能（包括叠加层、菜单项、快捷键），认为其带来显著额外压力和焦虑。  
- **链接**：https://github.com/openai/codex/issues/44546

### 10. [#50127] DOT：UNKNOWN 任务创建、过时断连通知、模糊的任务读取与 Luna Schema 失败
- **标签**：bug, model-behavior, app, connectivity, app-server  
- **评论**：3  |  👍：0  
- **摘要**：DOT 工作流中任务创建结果未知、断连通知延迟、任务读取歧义、Luna schema 错误等多重问题。  
- **链接**：https://github.com/openai/codex/issues/50127

## 重要 PR 进展（共 20 条高评论 PR，以下为 10 条关键变更）

### 1. [#50140] 使用服务器权限目录优化 TUI 权限快捷方式
- **状态**：已合并  
- **功能**：权限快捷方式现在统一从已连接服务器的权限目录获取，而非本地配置，确保与 picker 行为一致，尤其是模型特定的自动审核要求。  
- **链接**：https://github.com/openai/codex/pull/50140

### 2. [#50131] 为 TCP 隧道添加可选的 JSON 诊断功能
- **状态**：已合并  
- **功能**：新增 `codex tcp-tunnel --diagnostics-json` 选项，输出版本化的换行符分隔 JSON 诊断信息，记录启动、CONNECT、传输及控制失败，不暴露凭据或原始错误。  
- **链接**：https://github.com/openai/codex/pull/50131

### 3. [#50129] 为远程 MCP 服务器保留 Windows 环境变量
- **状态**：已合并  
- **功能**：修复 Unix 启动 Windows 端 stdio MCP 服务器时，显式环境变量允许列表基于 Unix 默认值过滤掉 Windows 运行时变量的问题，现在会保留必要的 Windows 临时目录等变量。  
- **链接**：https://github.com/openai/codex/pull/50129

### 4. [#50128] 暴露正在运行的 turn 下一步所选模型
- **状态**：已合并  
- **功能**：新增 `CodexThread::current_turn_model` 方法，返回指定运行 turn 下一步的模型 slug，独立于未来 turn 的设置。  
- **链接**：https://github.com/openai/codex/pull/50128

### 5. [#50113] 为云端线程 resume 和 attach 添加原生 gRPC 客户端
- **状态**：已合并  
- **功能**：新增 `codex-cloud-client` Rust 库，通过 HTTP/2 复用 `ThreadService.Resume` 和 `ThreadService.Attach` 接口，提供 bearer token、账户 ID 等配置。  
- **链接**：https://github.com/openai/codex/pull/50113

### 6. [#50112] 集中化 TUI 加载动画与帧调度
- **状态**：已合并  
- **功能**：将语音连接 spinnder 等加载 glyph 集中到 `codex-rs/tui/src/motion.rs`，保持 100ms 动画节拍，并在减少动效模式下显示静态 glyph。  
- **链接**：https://github.com/openai/codex/pull/50112

### 7. [#50109] 限制全屏提示框高度并提供滚动
- **状态**：已合并  
- **功能**：全屏编辑器高度限制为可用高度的三分之二，支持滚动浏览长草稿，同时保留远程图片附件的编辑行可见。  
- **链接**：https://github.com/openai/codex/pull/50109

### 8. [#50105] 合并聊天 composer 底部逻辑到 `footer_state`
- **状态**：已合并  
- **功能**：将 footer 属性构建、模式解析、提示覆盖、退出快捷键提示等从 `chat_composer.rs` 迁移至 `chat_composer/footer_state.rs`，保留原有行为。  
- **链接**：https://github.com/openai/codex/pull/50105

### 9. [#50099] 为 Guardian V2 增加可选的 Decisions 比较功能
- **状态**：已合并  
- **功能**：新增默认关闭的 `guardianv2_decisions_comparison` 特性，允许在 Guardian V2 快照分类旁运行 Decisions 进行比较，使用相同策略和证据。  
- **链接**：https://github.com/openai/codex/pull/50099

### 10. [#50094] 在 app-server 中添加附件所有者查询
- **状态**：已合并  
- **功能**：新增 `thread/attachmentOwner/list` 端点，可根据附件标识返回所有关联的线程 ID 及归档状态，支持客户端查找某个附件属于哪些线程。  
- **链接**：https://github.com/openai/codex/pull/50094

## 功能需求趋势
从 Issue 的趋势标签和内容来看，社区当前最关注四个方向：
1. **桌面体验优化**：Pets 功能的禁用/移除（#34349、#44546）呼声极高；会话管理（删除归档任务 #46182、历史消失 #23999）需求紧迫。
2. **Windows 平台兼容性**：sandbox 设置、目录权限、启动卡死、路径混合、环境变量等问题几乎占据一半的 bug 报告。
3. **Dot/Agent 工作流可靠性**：任务创建失败、线程读取歧义、MCP 启动失败、断连通知混乱等问题凸显多智能体协作的稳定性仍是短板。
4. **IDE 扩展稳定性**：VS Code 扩展消息队列丢失、ResizeObserver 错误、输入被吞等问题（#49988、#50118、#26683、#50071）影响日常开发。

## 开发者关注点
- **Windows 用户痛点集中**：sandbox 设置失败（#49718、#48759）、路径混合 linux/windows（#49753）、full access 策略无弹窗（#47213）、CMD 窗口泛滥（#49352）等，表明 Windows 上的系统集成仍需大量打磨。
- **模型配置覆盖 Bug**：subagent 忽略显式 model_provider（#40858）导致自定义模型流控失败，影响高级用户对多模型工作管理的信任。
- **消息队列与状态同步**：多个 Issue 报告消息被吞、卡在“thinking”状态、thread 标记 `Streaming=true` 却不响应（#50118、#50142），以及 session 切换后历史丢失（#23999），表明核心会话状态机需要进一步加固。
- **安全审核误报**：用户明确授权的文件更新被 safety check 拦截（#48940），引发对审核策略透明度的讨论。

---

*数据来源：GitHub openai/codex 仓库，截止 2026-10-02 UTC。*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，作为一名专注于 AI 开发工具的技术分析师，我已根据您提供的 GitHub 数据，为您生成了 2026 年 10 月 2 日的 Gemini CLI 社区动态日报。

---

## Gemini CLI 社区动态日报 | 2026-10-02

### 今日速览

今日社区动态聚焦于**稳定性与数据安全**。最新的 Nightly 版本引入了两个关键修复：**增量式聊天记录补丁**和**原子化状态持久化**，旨在解决数据损坏和丢失的核心痛点。在社区讨论中，`子代理（Subagent）`在达到最大轮次限制时**错误地报告成功**的问题引发了关注，这是一个需要优先处理的误导性 Bug。

### 版本发布

*   **v0.64.0-nightly.20261002.gc9096a847**
    *   **核心修复：** 实现了基于 `append-only delta patching` 的聊天记录服务 (`ChatRecordingService`)，通过增量更新和有限的历史窗口来管理对话，减少不必要的全量重写开销。
    *   **CLI 修复：** 实现了状态的**原子化持久化** (`PersistentState`)，当发生写入崩溃或数据损坏时，能够自动从 `.bak` 备份文件中恢复，极大提升了文件系统操作的安全性。
    *   **链接**: [查看 Release](https://github.com/google-gemini/gemini-cli/releases/tag/v0.64.0-nightly.20261002.gc9096a847)

### 社区热点 Issues

1.  **#22323: [Bug] 子代理达到最大轮次后错误报告“成功”**
    *   **摘要**：`codebase_investigator` 子代理在因 `MAX_TURNS` 限制而中断后，仍向主代理报告 `status: "success"` 和 `Termination Reason: "GOAL"`，实际上它并未完成任何分析工作。这给用户和系统都造成了误导。
    *   **社区反应**：这是一个 P1 级别的严重 Bug，已获得 2 个点赞（👍），社区认为这掩盖了子代理的真实运行状态。
    *   **链接**: [Issue #22323](https://github.com/google-gemini/gemini-cli/issues/22323)

2.  **#21409: [Bug] 通用代理（Generalist agent）无限期挂起**
    *   **摘要**：当 CLI 将任务委托给通用代理时，会导致进程无限期挂起，即使是创建文件夹等简单操作也是如此。用户反馈，指示模型不委托子代理是当前唯一的临时解决办法。
    *   **社区反应**：这是一个热门 issue，获得了 8 个点赞（👍），表明这是一个普遍且严重影响使用体验的 Bug。
    *   **链接**: [Issue #21409](https://github.com/google-gemini/gemini-cli/issues/21409)

3.  **#19873: [增强] 利用模型 Bash 亲和性，通过零依赖 OS 沙箱执行命令**
    *   **摘要**：提议利用 Gemini 3 模型对原生 Bash 操作的亲和性，在零依赖的 OS 沙箱中执行命令，从而在不牺牲安全性和用户体验的前提下，充分发挥模型编写和执行 POSIX 工具链的能力。
    *   **社区反应**：这是一个 P2 级别的重大增强提案（Effort/Large），有 1 个点赞（👍），代表了社区对更安全、更强大的模型委派执行（Agentic Execution）的追求。
    *   **链接**: [Issue #19873](https://github.com/google-gemini/gemini-cli/issues/19873)

4.  **#22745: [功能] 评估 AST 感知文件读取、搜索和映射技术的影响**
    *   **摘要**：这是一个追踪（EPIC）Issue，旨在探索利用 AST（抽象语法树）感知工具来替代纯文本操作，以实现更精准的代码导航、减少 token 消耗并提高上下文补全效率。
    *   **社区反应**：获得了 1 个点赞（👍），被视为提升代理代码理解能力的一个潜在方向。
    *   **链接**: [Issue #22745](https://github.com/google-gemini/gemini-cli/issues/22745)

5.  **#21968: [Bug] Gemini 不主动使用自定义技能和子代理**
    *   **摘要**：社区成员反馈，即使用户定义了描述清晰的自定义技能和子代理（如 Gradle、Git 技能），Gemini 也不会在需要时主动使用它们，除非被明确指令要求。这表明模型的任务调度逻辑有待改进。
    *   **社区反应**：有 6 条评论，揭示了当前 Agent 系统在工具自主调用方面的短板。
    *   **链接**: [Issue #21968](https://github.com/google-gemini/gemini-cli/issues/21968)

6.  **#22267: [Bug] 浏览器代理（Browser Agent）忽略 settings.json 配置**
    *   **摘要**：用户发现浏览器代理完全忽略用户在 `settings.json` 中设定的 `maxTurns` 等配置覆盖项。虽然初始化时能正确读取，但运行时并未遵循。
    *   **社区反应**：这是一个典型的配置与运行时脱节的问题，有 4 条评论讨论其影响。
    *   **链接**: [Issue #22267](https://github.com/google-gemini/gemini-cli/issues/22267)

7.  **#21983: [Bug] 浏览器子代理在 Wayland 环境下失败**
    *   **摘要**：用户报告在 Linux 的 Wayland 显示服务器协议下，浏览器子代理无法正常启动或运行，最终导致失败。
    *   **社区反应**：P1 级别 Bug，是平台兼容性问题的一个典型代表，严重影响了部分 Linux 用户的使用。
    *   **链接**: [Issue #21983](https://github.com/google-gemini/gemini-cli/issues/21983)

8.  **#20079: [Bug] 子代理符号链接（Symlink）不被识别**
    *   **摘要**：当 `~/.gemini/agents/` 目录下的 `.md` 文件是符号链接时，它不会被系统识别为有效的子代理。这限制了用户管理代理定义文件时的灵活性。
    *   **社区反应**：一个直接且明确的功能 Bug，虽不严重但影响了部分用户的自定义工作流。
    *   **链接**: [Issue #20079](https://github.com/google-gemini/gemini-cli/issues/20079)

9.  **#24246: [Bug] 超过 128 个工具时 Gemini CLI 遇到 400 错误**
    *   **摘要**：当配置的工具数量超过 128 个（原文为>400，Issue 标题写 128）时，CLI 会返回 400 错误。用户期望工具选择机制能更智能地限制范围。
    *   **社区反应**：这触及了扩展性和 Agent 上下文窗口管理的核心问题。
    *   **链接**: [Issue #24246](https://github.com/google-gemini/gemini-cli/issues/24246)

10. **#22672: [增强] 代理应阻止或劝阻破坏性行为**
    *   **摘要**：提议为 Agent 增加安全机制，以防止在执行复杂 Git 操作或管理数据库时使用过于激进的命令（如 `git reset --force`），提醒用户使用更安全的替代方案。
    *   **社区反应**：获得了 1 个点赞（👍），社区对 Agent 的安全意识和防护能力提出了更高要求。
    *   **链接**: [Issue #22672](https://github.com/google-gemini/gemini-cli/issues/22672)

### 重要 PR 进展

1.  **#29597: [修复] 为 gVisor/runsc 沙箱启用 IPC Socket 回退**
    *   **摘要**：此 PR 解决了在 gVisor 沙箱环境中 IPC 通信失效的问题。通过启用 stdio IPC 回退机制，确保在受限网络环境下，CLI 仍能与后端进行可靠通信。
    *   **链接**: [PR #29597](https://github.com/google-gemini/gemini-cli/pull/29597)

2.  **#29457: [修复] 用 glob 匹配替换模糊的 `requestedExplicitly` 逻辑**
    *   **摘要**：这是一个解决上下文膨胀的关键修复。在 `read-many-files` 中，原先使用 `String.includes()` 进行模糊匹配，导致二进制文件（如图片、PDF）被错误地读入上下文。现改为更精确的 glob 匹配，杜绝了无意中的 token 浪费。
    *   **链接**: [PR #29457](https://github.com/google-gemini/gemini-cli/pull/29457)

3.  **#29582: [性能] 优化忽略过滤并启用子树剪枝**
    *   **摘要**：通过引入分层目录状态记忆、通配符目录模式剪枝和符号链接缓存，大幅优化了大型仓库（如包含大量 `node_modules`）的文件搜索和忽略过滤性能，解决了此前数秒的阻塞延迟。
    *   **链接**: [PR #29582](https://github.com/google-gemini/gemini-cli/pull/29582)

4.  **#29584: [修复] 防止快速退出时删除恢复的会话历史**
    *   **摘要**：修复了一个数据丢失的严重 Bug：在恢复一个已保存的会话后，如果快速退出（例如立即按 `Ctrl+C`或是输入 `/exit`），之前的会话历史文件会被永久删除。此 PR 从根本上解决了这个问题。
    *   **链接**: [PR #29584](https://github.com/google-gemini/gemini-cli/pull/29584)

5.  **#29502: [修复] 确保 Enter 和 Spacebar 可靠确认选择列表**
    *   **摘要**：修复了在不同终端（特别是 Windows IDE 终端）下，交互式选择列表（如 `RadioButtonSelect`）对 `Enter` 和 `Spacebar` 键响应不一致的问题，确保在所有环境下都有可靠的操作体验。
    *   **链接**: [PR #29502](https://github.com/google-gemini/gemini-cli/pull/29502)

6.  **#29520: [修复] 在流式输出时保持滚动位置**
    *   **摘要**：解决了在流式输出或工具确认提示时，用户在终端滚动浏览历史内容后，视图会被跳回至滚动位置的 Bug，极大提升了阅读长会话时的终端使用体验。
    *   **链接**: [PR #29520](https://github.com/google-gemini/gemini-cli/pull/29520)

7.  **#29540: [修复] 在 Windows 上重试目录删除以解决锁定错误**
    *   **摘要**：针对 Windows 平台在更新或卸载扩展时遇到的临时文件锁定错误（`EBUSY`、`EPERM`），引入了重试机制，避免了因进程未释放文件句柄而导致的扩展安装或卸载失败。
    *   **链接**: [PR #29540](https://github.com/google-gemini/gemini-cli/pull/29540)

8.  **#29586: [修复] 确保 Ctrl+C 紧急中止能到达取消处理器**
    *   **摘要**：修复了一个关键的输入处理缺陷，即当有活跃的 Agent 或流式输出运行时，用户按 `Ctrl+C` 紧急终止的信号可能被“吞掉”或损坏，导致无法中断操作。
    *   **链接**: [PR #29586](https://github.com/google-gemini/gemini-cli/pull/29586)

9.  **#29581: [修复] 解析 `@file:line` 引用并防止幽灵文本换行挂起**
    *   **摘要**：修复了两个 Bug：1) 无法正确解析 `@file:10` 或 `@file:line10-20` 这类引用；2) 在终端宽度较窄或包含宽字符时，输入提示框的幽灵文本（ghost text）可能导致无限循环挂起。
    *   **链接**: [PR #29581](https://github.com/google-gemini/gemini-cli/pull/29581)

10. **#29583: [修复] 在不受信任的文件夹中强制工作区设置只读**
    *   **摘要**：此 PR 确保了当 CLI 在未经验证的目录下运行时，针对 `.gemini/settings.json` 的写入操作（如 `gemini mcp add`）不会被执行，从而防止了对工作区设置的静默覆盖或破坏。
    *   **链接**: [PR #29583](https://github.com/google-gemini/gemini-cli/pull/29583)

### 功能需求趋势

从今日的 Issues 和 PRs 中，可以总结出以下几个主要的社区功能需求方向：

*   **代理（Agent）可靠性与可控性**：这是最核心的趋势。社区强烈要求修复代理（特别是子代理和通用代理）**无响应、挂起**以及**错误报告状态**的 Bug。同时，希望 Agent 能**更智能地主动使用工具**，而不是被动等待指令。
*   **AST 感知的代码导航**：社区开始寻求超越纯文本操作，探索利用 AST 进行更精确的代码**搜索、读取和映射**。这被视为降低 token 消耗、提升代理在大型项目中导航和理解代码能力的关键方向。
*   **扩展生态与平台兼容性**：对 **Chrome 扩展 / IDE 集成**的需求持续存在。同时，**MCP 插件管理**的稳定性和可靠性备受关注，包括修复扩展安装时的 Windows 文件锁定问题，以及在配置中暴露 MCP 服务端名称。
*   **状态持久化与数据安全**：对会话历史和配置文件的**原子化写入**和**灾难恢复**有极高呼声。社区不希望因意外退出或崩溃而丢失宝贵的上下文或损坏状态文件。
*   **Windows 体验优化**：针对 Windows 平台的特定问题修复数量显著增多，包括 IME 输入法、文件锁定、和终端交互，表明社区正积极推动 Windows 环境下的体验提升。

### 开发者关注点

开发者社区的反馈主要集中在以下几个痛点和高频需求：

*   **子代理（Subagent）管理混乱**：开发者频繁反映子代理的**行为不可预测**，如最大轮次限制后虚假成功、自行挂起、以及自主调用意愿低。这表明当前 Agent 的调度和执行机制亟待优化。
*   **一般性卡死（Hang）问题**：`Generalist agent` 的无限期挂起是最大痛点之一，严重影响了工具的正常使用，开发者只能通过“禁止使用子代理”这种变通方法来规避。
*   **扩展性与平台兼容性挑战**：当工具数量过多（超过128个）时出现 400 错误，以及浏览器代理在特定平台（如 Wayland）上不可用，都是开发者工作的实际阻碍。
*   **用户体验与 UI 问题**：在 Windows 上的 IME 输入问题、`Ctrl+C` 无法强制中止、以及终端滚动/输入框的卡顿，直接影响了工具的感知可靠性和日常使用流畅度。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区动态日报 (2026-10-02)

## 今日速览
- **版本集中发布**：过去24小时连续发布 v1.0.91、v1.0.91-1、v1.0.92-0，新增 `copilot sandbox ca` 命令体系并修复 MCP 工具在 OAuth 重认证后的稳定性。
- **macOS 系统更新引发大规模故障**：Issue #4998 报告 macOS 安全更新后 CLI 完全不可用，影响所有会话，社区高度关注，已有6条评论。
- **企业级用户痛点持续凸显**：多项 Issue 聚焦于 GHEC 数据驻留、企业托管模型设置未生效、MCP 服务器白名单匹配失败等问题，反映出企业场景下的适配缺口。

## 版本发布

### v1.0.92-0 (2026-10-02)
- **Fixed**: 修复当工具定义未变更时，MCP 工具在 OAuth 重新认证后仍能继续工作的问题。提升了 OAuth 流程的健壮性。

### v1.0.91 (2026-10-01)
- **Added**: 新增 `copilot sandbox ca` 命令组，支持 check、create、trust、rotate、remove 代理 CA 信任操作，包含无人值守 Windows 安装。原 `/sandbox ca install` 拆分为 `create` 和 `trust`。
- **Improved**: 会话时间线现在能在中断的 turn 结束后正确清除“忙碌”状态。
- **Fixed**: 沙箱命令在 Windows 上正常运行。

### v1.0.91-1 (2026-10-01)
- **Added**: 与 v1.0.91 相同的新增内容（`copilot sandbox ca`）。
- **Improved**: CLI 关闭时会在退出前刷新待发送的遥测数据，并在遥测发送时施加有限延迟（避免数据丢失）。

## 社区热点 Issues（Top 10）

### 1. [#4998] macOS 更新后 CLI 完全不可用 — `.mcp-writer.binding` 持久化失效
- **标签**: `area:mcp`, `bug`
- **摘要**: 安装 macOS 安全更新并重启后，所有新会话和已恢复会话均无法处理提示。原因是持久化的 `.mcp-writer.binding` 中存储了过期的文件系统设备 ID。
- **为什么重要**: 影响范围大（所有用户），且无临时绕过方案。已有6条评论，4个👍，社区期望立即修复。
- [🔗 Issue #4998](https://github.com/github/copilot-cli/issues/4998)

### 2. [#5008] 启动时反复弹出“未认证”错误（v1.0.89+）
- **标签**: `area:authentication`, `area:models`, `bug`
- **摘要**: 每次新交互会话启动后立即显示两次 `Failed to read model provider attribution: Error: Not authenticated`，约3秒后登录完成才能正常使用。疑似启动时竞态条件。
- **为什么重要**: 高频触发，影响用户体验；已有5个👍，6条评论，社区希望尽快修复启动时序。
- [🔗 Issue #5008](https://github.com/github/copilot-cli/issues/5008)

### 3. [#953] 权限请求过于宽泛（企业级痛点）
- **标签**: `area:authentication`, `area:permissions`, `area:enterprise`, `feature`
- **摘要**: 用户要求能精确控制 AI 可访问的仓库和 GitHub 范围，目前 OAuth 认证时请求全量读写权限，过于激进。
- **为什么重要**: 长期高优 feature（创建已9个月），企业安全合规刚需。8条评论，5个👍，持续关注。
- [🔗 Issue #953](https://github.com/github/copilot-cli/issues/953)

### 4. [#3282] 支持多个 BYOK 模型
- **标签**: `area:models`, `area:configuration`, `feature`（已关闭）
- **摘要**: 用户希望在 Copilot CLI 中同时配置多个 BYOK 模型，并在 TUI 内切换。当前只能通过环境变量设置单一模型，切换需重启会话。
- **为什么重要**: 社区31个👍，12条评论，需求强烈。已在2026-10-01关闭，可能已内部实现或规划中。
- [🔗 Issue #3282](https://github.com/github/copilot-cli/issues/3282)

### 5. [#4851] Azure MCP 服务器 HTTP 请求失败（BrokenPipe）
- **标签**: `triage`, `bug`
- **摘要**: 使用 Azure API Center MCP registry 数月后突然失败，CLI 1.0.83 的 Rust 运行时验证时出现 BrokenPipe 错误。
- **为什么重要**: 影响使用 Azure 企业 MCP 服务的团队，5条评论，8个👍。表明 MCP 生态稳定性仍需加强。
- [🔗 Issue #4851](https://github.com/github/copilot-cli/issues/4851)

### 6. [#4938] GHEC 数据驻留租户的认证仍路由到 api.github.com
- **标签**: `area:authentication`, `area:enterprise`, `area:networking`, `bug`
- **摘要**: GitHub Enterprise Cloud 数据驻留租户的 `SessionConfig.GitHubToken` 仍强制指向 `api.github.com`，而非租户专属端点。与旧 Issue #4527 同类缺陷。
- **为什么重要**: 严重影响 GHEC-DR 客户的数据主权合规。1条评论，1个👍，但属于高危 bug。
- [🔗 Issue #4938](https://github.com/github/copilot-cli/issues/4938)

### 7. [#4959] 企业托管 `model` 设置未生效
- **标签**: `triage`, `bug`
- **摘要**: 企业策略中配置了 `"model": "auto"`，日志显示已获取，但模型解析器仍使用用户级设置而非托管值。
- **为什么重要**: 企业管理员无法统一管控模型，可能引发合规问题。2条评论，3个👍。
- [🔗 Issue #4959](https://github.com/github/copilot-cli/issues/4959)

### 8. [#4989] MCP 服务器白名单 `serverName` 匹配失败
- **标签**: `area:enterprise`, `area:mcp`, `bug`
- **摘要**: 企业管理的 `allowedMcpServers` 中使用 `serverName` 字段时，命名服务器被错误地阻止为“未在白名单中”。
- **为什么重要**: 企业 MCP 管控失效，导致自定义 MCP 服务器无法使用。1条评论，但影响面大。
- [🔗 Issue #4989](https://github.com/github/copilot-cli/issues/4989)

### 9. [#5027] Linux 沙箱 DNS 在 systemd-resolved 下不可用
- **标签**: `triage`, `bug`
- **摘要**: 沙箱共享宿主机的 `/etc/resolv.conf` 指向 `127.0.0.53`，但沙箱内部无法访问该 loopback 地址，导致 DNS 完全不可用。
- **为什么重要**: 影响所有使用 systemd-resolved 的 Linux 发行版，沙箱功能形同虚设。新建 Issue，未获评论，但问题清晰。
- [🔗 Issue #5027](https://github.com/github/copilot-cli/issues/5027)

### 10. [#3675] 会话 worktrees 应可配置、自清理且命名一致
- **标签**: `area:sessions`, `area:configuration`, `area:tools`, `feature`
- **摘要**: 当前 worktree 路径魔、分支名、文件夹名三者不一致，且无自动清理机制，占用磁盘空间。
- **为什么重要**: 开发者工作流中常见痛点，8个👍，1条评论。长期 feature，期望改善。
- [🔗 Issue #3675](https://github.com/github/copilot-cli/issues/3675)

## 重要 PR 进展

由于过去24小时内仅出现1个 Pull Request，现重点分析：

### [#5036] 更新 README 中的默认模型版本
- **作者**: mjgard
- **状态**: OPEN（2026-10-01创建，当日更新）
- **摘要**: 将文档中的默认模型描述更新为与实际 Copilot CLI 使用的默认模型一致，并附截图说明。
- **为什么重要**: 文档与实现脱节会误导新用户，该 PR 虽小但有助于降低 onboarding 困惑。社区暂无评论。
- [🔗 PR #5036](https://github.com/github/copilot-cli/pull/5036)

> 注：过去24小时内无其他 PR 被创建或更新，社区主要精力集中在 Issue 反馈和版本修复上。

## 功能需求趋势

从近期 Issue 中可提炼出以下社区最关注的功能方向：

1. **多模型与模型切换**  
   - 多个 BYOK 模型支持 (#3282)、企业模型强制策略 (#4959)、运行时切换模型，反映用户对灵活性的追求。

2. **精细化权限与安全控制**  
   - OAuth 范围裁剪 (#953)、企业托管 MCP 白名单 (#4989)、代理 CA 管理（新版本已落地），强调企业安全合规。

3. **MCP 生态稳定性与可观测性**  
   - MCP 服务器失败后自动重试、状态通知可关闭 (#5034)、DNS 沙箱问题 (#5027)，用户希望 MCP 更健壮、更透明。

4. **会话与工作流管理**  
   - 会话 worktrees 可配置化 (#3675)、历史会话恢复可靠性 (#5023)、中断后状态清理（v1.0.91改进），提升日常使用体验。

5. **配额与用量透明化**  
   - 在状态栏暴露额度使用与账单周期信息 (#5029)，用户希望及时了解成本消耗。

## 开发者关注点

- **macOS 系统更新兼容性**：安全更新后 CLI 完全瘫痪，暴露出持久化状态与系统设备 ID 相关硬伤，需紧急修复。
- **Windows 体验问题**：MCP 启动时 CMD 窗口闪烁 (#3171，已关闭但仍有同类残留)、VS Code 代理 host 重复加载指令文件 (#5022)，Windows 用户期待更原生集成。
- **启动竞态与认证问题**：1.0.89 引入的模型提供商标识时序错误 (#5008) 导致每次启动弹错误，影响第一印象。
- **企业级路由与数据驻留**：GHEC-DR 路由错误 (#4938) 长时间未解决，企业用户持续担忧数据跨境。
- **沙箱功能受限**：Linux 下 systemd-resolved DNS 不可用 (#5027)、Windows 沙箱命令才修复，沙箱作为核心安全特性仍需打磨。
- **自动提交导致 co-author 格式错误**：`Copilot-Session` 字段出现在 `Co-authored-by` 后，被 GitHub 错误解释为作者 (#5032)，影响贡献归属。

> *数据来源：[github.com/github/copilot-cli](https://github.com/github/copilot-cli)，截止 2026-10-02 06:00 UTC。*

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 — 2026-10-02

## 今日速览
今日社区聚焦 **Claude Opus 4.6 预填充崩溃**（#13768，74 条评论）和 **输出 token 上限被静默限制**（#29363）两大遗留痛点；同时 **Go 订阅计费混乱**（#52595/#52592/#52596）与 **免费模型被付费上限误封**（#51682）引发信任危机。PR 方面，多个 **核心修复**（缓存、MCP 重试、超时）和 **文档修正** 正在推进，v2 版本稳定性持续改善。

## 版本发布
过去 24 小时内无新版本发布。

## 社区热点 Issues（10 条）

### 🔥 1. Claude Opus 4.6 不支持 assistant message prefill（#13768）
- **链接**：[Issue #13768](https://github.com/anomalyco/opencode/issues/13768)
- **社区反应**：74 条评论，35 👍；CLOSED 但仍在讨论。
- **要点**：使用 Opus 4.6 时频繁报错 “This model does not support assistant message prefill”，对话被中断。多个用户确认在 session 切换或工具调用后出现。

### 🔥 2. `limit.output` 被静默限制在 32K token（#29363）
- **链接**：[Issue #29363](https://github.com/anomalyco/opencode/issues/29363)
- **社区反应**：26 条评论，29 👍
- **要点**：即使 `opencode.json` 设置了更大的 `limit.output`（如 384K），实际 `maxOutputTokens` 仍被静默截断至 32K。环境变量 `OPENCODE_EXPERIMENTAL_OUTPUT_TOKEN_MAX` 为实验性方案且不便，用户呼吁官方修复。

### 🔥 3. 插件无法访问 5 种核心会话能力（#49389）
- **链接**：[Issue #49389](https://github.com/anomalyco/opencode/issues/49389)
- **社区反应**：16 条评论，4 👍；OPEN
- **要点**：核心存在 `read-only session enumeration`、`hidden/ephemeral sessions` 等能力，但插件 API 未暴露。限制插件生态发展。

### 🔥 4. 未使用模型 gpt-6-luna 被报告使用（#52367）
- **链接**：[Issue #52367](https://github.com/anomalyco/opencode/issues/52367)
- **社区反应**：6 条评论，OPEN
- **要点**：用户从未选用 `gpt-6-luna`，但控制台显示其被调用并通过 `openai-responses` 协议消耗。引发计费信任问题。

### 🔥 5. Go 免费模型在付费上限耗尽后被封锁（#51682）
- **链接**：[Issue #51682](https://github.com/anomalyco/opencode/issues/51682)
- **社区反应**：4 条评论，2 👍；OPEN
- **要点**：文档标注“Unlimited”的免费模型（如 Space Bunny Free）在达到 Go 月度/周使用上限后无法使用。违反预期，用户强烈不满。

### 🔥 6. LaTeX 数学公式渲染问题（#34407 / #39170 / #49486）
- **链接**：[#34407](https://github.com/anomalyco/opencode/issues/34407)、[#39170](https://github.com/anomalyco/opencode/issues/39170)、[#49486](https://github.com/anomalyco/opencode/issues/49486)
- **社区反应**：每个 3-6 条评论，3 👍；部分 CLOSED 但未完全修复
- **要点**：CLI 和 Desktop 中行内公式 `$...$` 被渲染为原始 LaTeX，块级 `$$...$$` 正常。跨版本复现，影响学术用户。

### 🔥 7. Go 订阅支付后未激活（#52595 / #52592 / #52596）
- **链接**：[#52595](https://github.com/anomalyco/opencode/issues/52595)、[#52592](https://github.com/anomalyco/opencode/issues/52592)、[#52596](https://github.com/anomalyco/opencode/issues/52596)
- **社区反应**：各 4-5 条评论，OPEN
- **要点**：多位用户报告付款后账户仍显示“Subscribe”，或出现 403 拒绝。支付记录存在但余额未到账，需要合规团队介入。

### 🔥 8. DeepSeek V4.1 Flash prompt 缓存退化为仅匹配第一张图片（#51993）
- **链接**：[Issue #51993](https://github.com/anomalyco/opencode/issues/51993)
- **社区反应**：5 条评论，OPEN
- **要点**：在多图片对话中，新加入图片后缓存仅命中第一张之前的内容，后续图片和文本被重新处理，导致成本增加和延迟。

### 🔥 9. Subagent 错误被报告为成功完成（#52378）
- **链接**：[Issue #52378](https://github.com/anomalyco/opencode/issues/52378)
- **社区反应**：4 条评论，OPEN
- **要点**：Subagent 因 `MALFORMED_FUNCTION_CALL` 失败（`finish:"error"`），但父进程将其视为成功，导致下游决策错误。严重 bug。

### 🔥 10. 60 分钟空闲驱逐导致工具失败信息丢失（#52597）
- **链接**：[Issue #52597](https://github.com/anomalyco/opencode/issues/52597)
- **社区反应**：2 条评论，OPEN（今日创建）
- **要点**：当运行因空闲 60 分钟被驱逐时，工具失败只返回通用信息“Tool execution interrupted”，丢失具体原因（如 `inactivity`）。同时待处理的表单被取消时也不携带内容（#52599）。

## 重要 PR 进展（10 条）

### 🚀 1. 修复扩展迁移导致的回归（#52620）
- **链接**：[PR #52620](https://github.com/anomalyco/opencode/pull/52620)
- **状态**：CLOSED
- **内容**：A/B 审计发现 #52369 引入约 30 项回归，本 PR 逐一修复，涉及 app 行为还原。

### 🚀 2. 改进 Anthropic 缓存命中率（#14743）
- **链接**：[PR #14743](https://github.com/anomalyco/opencode/pull/14743)
- **状态**：OPEN（长期 PR）
- **内容**：通过系统消息分割和工具稳定性修复跨 repo/跨 session 的缓存未命中问题。Closes #5416 等。

### 🚀 3. 启用阿里 Qwen 聊天缓存（#52612）
- **链接**：[PR #52612](https://github.com/anomalyco/opencode/pull/52612)
- **状态**：OPEN
- **内容**：为通义千问模型默认启用 system 和 conversation-tail 缓存检查点，提升响应速度。

### 🚀 4. MCP 连接失败自动重试（#52614）
- **链接**：[PR #52614](https://github.com/anomalyco/opencode/pull/52614)
- **状态**：OPEN
- **内容**：远程 MCP 服务器启动或临时 503 不再直接标记为失败，最多额外重试 3 次，增强稳定性。

### 🚀 5. 提供者请求超时默认 5 分钟（#49229）
- **链接**：[PR #49229](https://github.com/anomalyco/opencode/pull/49229)
- **状态**：OPEN
- **内容**：为服务端响应头和流式数据块分别设置 5 分钟超时（可复位的块超时），避免无限等待。

### 🚀 6. 禁用 Claude 4.6 的 assistant prefill（#14772）
- **链接**：[PR #14772](https://github.com/anomalyco/opencode/pull/14772)
- **状态**：OPEN
- **内容**：针对 #13768 的修复——当对话最后消息为 assistant 时，Opus 4.6 会拒绝；此 PR 在切换模型时清除不必要的 prefill 消息。

### 🚀 7. 修复 UI 中双波浪线误渲染为删除线（#52063）
- **链接**：[PR #52063](https://github.com/anomalyco/opencode/pull/52063)
- **状态**：OPEN
- **内容**：`marked` 库将单独的 `~` 对视为删除线（`strikethrough`），导致类似“~5 min”的文本错误显示。本 PR 限制只在双波浪线上应用删除线。

### 🚀 8. 命令文件无效 model 时给出警告（#52268）
- **链接**：[PR #52268](https://github.com/anomalyco/opencode/pull/52268)
- **状态**：OPEN
- **内容**：当 `.md` 命令文件的 `model` 字段无效时（如 `opus` 而非具体型号），此前静默丢弃；现改为日志警告，便于排查。

### 🚀 9. 退役遗留 S3 统计存储（#52515）
- **链接**：[PR #52515](https://github.com/anomalyco/opencode/pull/52515)
- **状态**：OPEN
- **内容**：移除旧版 S3 表、Athena 工作组及相关基础设施，所有统计迁移到新的 stats 模块，降低维护成本。

### 🚀 10. 时间戳 gutter 模式（#29398）
- **链接**：[PR #29398](https://github.com/anomalyco/opencode/pull/29398)
- **状态**：CLOSED（合并）
- **内容**：在消息左侧 gutter 显示时间戳，支持悬停弹出详情。回应了多个用户请求，提升对话可读性。

## 功能需求趋势
从今日 Issues 和 PR 中可以提炼出社区最关注的三个方向：

1. **大模型兼容性与缓存优化**：Claude 4.6 预填充、阿里/Anthropic 缓存、DeepSeek 图片缓存退化等，反映出用户对多模型稳定使用和成本控制的迫切需求。
2. **计费与订阅透明度**：Go 订阅的多起支付失败、免费模型被误封、未使用模型被计费，表明社区对**账单可见性**和**合规响应**高度敏感。
3. **插件与扩展能力**：#49389 暴露出核心会话能力与插件 API 之间的鸿沟，开发者希望插件能读写会话、创建隐藏会话等，以构建更复杂的自动化工作流。

## 开发者关注点
- **高频痛点**：`limit.output` 被静默截断（#29363）和 LaTeX 渲染残缺（#34407）是长期未解决的“老问题”，影响模型输出质量和学术场景。
- **稳定性召回**：Windows 控制台闪烁（#42440）、桌面 UI 冻结（#43355）、新会话无响应（#49561）等问题虽然已 CLOSED，但开发者期望在 v2 后续版本中彻底根除。
- **MCP 生态**：MCP 服务器重复启动（#42190）和连接失败处理优化（#52614）表明社区正在积极改善本地工具集成体验。
- **自动化与测试**：Subagent 错误静默传递（#52378）以及空闲驱逐丢失原因（#52597）暴露出错误传播和状态记录上的缺陷，对依赖 Agent 链的开发者尤为关键。

> 整理自 GitHub [anomalyco/opencode](https://github.com/anomalyco/opencode) 在过去 24 小时内的公开发布数据。

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 — 2026-10-02

## 今日速览

- **v1.0.0 正式发布**，默认启用全屏 TUI 模式，终端体验大幅升级；同时发布了多项针对新版本的快速修复。
- **Cloudflare Clef 分类模型**被快速合入 Workers AI 提供程序，社区对低成本新模型的兴趣持续升温。
- **多个关键 Bug 得到修复**：包括全屏模式下的图像滚动崩溃、`read` 工具参数类型错误、Anthropic SSE 空帧问题以及 `pi-coding-agent` 中的依赖漏洞。

---

## 版本发布

### v1.0.0

**发布日期：2026-10-01**

- **全屏模式成为默认**：TUI 现在默认以全屏方式运行，可通过设置 `tuiMode` 为 `"regular"` 恢复终端常规回滚行为。
- **更精简的代码**：包体积进一步缩小，启动速度优化。
- 更多细节请查看 [发布说明](https://github.com/earendil-works/pi/releases/tag/v1.0.0)。

---

## 社区热点 Issues（Top 10）

### 1. #5653 — 移除 Shrinkwrap 依赖锁定（Open，23 条评论）
**问题**：同时安装 `pi-ai` 和 `pi-coding-agent` 会导致磁盘上出现两份相同的 `pi-ai` 副本（一个被提升，一个嵌套在 `pi-coding-agent` 下），由于 API 提供者注册表是模块级的 `Map`，两个副本会隔离状态，造成功能异常。
**社区反应**：讨论激烈，开发者认为 `shrinkwrap` 机制破坏了依赖共享，希望改用更灵活的锁定策略。
🔗 [Issue #5653](https://github.com/earendil-works/pi/issues/5653)

### 2. #10031 — 按 ESC 停止思考后 Pi 卡在 “Working...” 状态（Open，19 条评论）
**问题**：从 v0.84.0 开始，频繁出现按 ESC 中断思考后 Pi 永久卡死，只能通过 Ctrl+C 退出并 `pi -c` 恢复。多台机器复现。
**社区反应**：多位用户确认复现，属于回归性 Bug，严重干扰日常使用。
🔗 [Issue #10031](https://github.com/earendil-works/pi/issues/10031)

### 3. #9255 — 长对话滚动时全屏重绘风暴（Open，9 条评论）
**问题**：当对话高度远大于终端高度时，实时流式组件（约 30 行思考尾）导致每帧都触发 `fullRender(true)`，造成文本跳跃、重复，滚动体验极差。
**社区反应**：开发团队已识别到渲染引擎优化瓶颈，正等待架构调整。
🔗 [Issue #9255](https://github.com/earendil-works/pi/issues/9255)

### 4. #9980 — OpenRouter 上热门开放模型的费用估算偏差 2-3 倍（Open，5 条评论）
**问题**：Pi 目前使用**最便宜**提供商的价格计算成本，对于多提供商支持的开放模型（如 `z-ai/glm-5.3-flash`），实际扣费往往高出 2-3 倍。
**社区反应**：用户反馈强烈，影响预算控制；PR #10286 已尝试用 OpenRouter 返回的实际账单替代估算。
🔗 [Issue #9980](https://github.com/earendil-works/pi/issues/9980)

### 5. #9887 — `read` 工具的行号渲染在参数为字符串时崩溃（Open，5 条评论）
**问题**：某些模型（如 `xiaomi/mimo-v2.6-flash`）将 `offset`/`limit` 作为字符串发送，TUI 在计算行范围时拼接字符串而非加法，导致显示错误。
**社区反应**：影响模型兼容性，已通过 PR #10290 修复。
🔗 [Issue #9887](https://github.com/earendil-works/pi/issues/9887)

### 6. #9793 — 模糊长度停止导致上下文意外压缩（Open，3 条评论）
**问题**：子代理在占用仅 11% 上下文窗口时被压缩，原因是流式响应缺少推理 token 导致长度计算偏差。
**社区反应**：对上下文管理机制提出改进需求，希望更智能地判断“实际使用长度”。
🔗 [Issue #9793](https://github.com/earendil-works/pi/issues/9793)

### 7. #10258 — ChatGPT OAuth 登录返回 400 错误（Open，3 条评论）
**问题**：添加 OpenAI 提供商时，授权后出现 `invalid_grant` 错误，而旧版 `open-codex (legacy)` 正常工作。
**社区反应**：用户尝试多种方式无果，怀疑是 OAuth 令牌刷新机制问题。
🔗 [Issue #10258](https://github.com/earendil-works/pi/issues/10258)

### 8. #10250 — TUI 在 tmux 中启动时输入框填满垃圾字符（Open，3 条评论）
**问题**：自 v0.99.0（默认 system 主题）起，在 tmux 3.6/3.6a 下启动时，输入框会被预填充一堆十六进制乱码，每次不同。
**社区反应**：与 tmux 的颜色处理兼容性问题，已确认 `pi -ne` 可绕过。
🔗 [Issue #10250](https://github.com/earendil-works/pi/issues/10250)

### 9. #10308 — 空闲 Pi 会话占用约 140 MiB 内存（Closed，2 条评论）
**问题**：空闲会话的内存占用量偏高，开发者希望从懒加载 highlight.js 语法库开始降低驻留内存。
**社区反应**：社区积极，开发者已准备好第一个优化分支，等待合并。
🔗 [Issue #10308](https://github.com/earendil-works/pi/issues/10308)

### 10. #10249 — 内置 MCP 关闭时未等待初始化完成（Open，2 条评论）
**问题**：关闭连接时若仍在初始化，可能残留传输层任务，导致 SDK 清理不彻底。
**社区反应**：属于并发安全问题，影响 MCP 集成的可靠性。
🔗 [Issue #10249](https://github.com/earendil-works/pi/issues/10249)

---

## 重要 PR 进展（Top 10）

### 1. #10322 — 添加 Cloudflare Clef 分类器到 Workers AI（已合并）
**内容**：新增 `@cf/cloudflare/clef`（27B，$0.24/百万输入 token）和 `@cf/cloudflare/clef-flash`（9B，$0.09/百万输入 token），与现有 `typesafe/jev` 使用相同接口。
**意义**：为 Pi 提供更多低成本、高质量的分类模型选项。
🔗 [PR #10322](https://github.com/earendil-works/pi/pull/10322)

### 2. #9880 — 发布 coding-agent 配置 JSON Schema（开发中）
**内容**：从规范的 TypeBox 合约自动生成 `models.json`、`settings.json`、`keybindings.json` 和主题的 JSON Schema，并添加回归测试。
**意义**：为 IDE 自动补全和配置校验提供基础，改善开发者体验。
🔗 [PR #9880](https://github.com/earendil-works/pi/pull/9880)

### 3. #10293 — 修复 system 主题下柔和调色板变得过于鲜艳（已合并）
**内容**：对调色板颜色应用钟形曲线衰减，并限制在原始色度内，保证 `Catppuccin Frappe` 等主题保持原有视觉风格。
**意义**：解决了 #10255 报告的回归问题，恢复正确色彩渲染。
🔗 [PR #10293](https://github.com/earendil-works/pi/pull/10293)

### 4. #10290 — 修复 `read` 工具字符串参数的行号显示（已合并）
**内容**：在显示行范围时将 `offset`/`limit` 强制转换为数字，避免字符串拼接导致的错误。
**意义**：直接修复 #9887，提高对非标准模型的兼容性。
🔗 [PR #10290](https://github.com/earendil-works/pi/pull/10290)

### 5. #10286 — 使用 OpenRouter 实际报告的总成本替代估算（开发中）
**内容**：从 OpenRouter 的响应中提取实际扣费金额，取代基于目录的估算价格。
**意义**：解决 #9980 中费用偏差问题，提供更准确的消费记录。
🔗 [PR #10286](https://github.com/earendil-works/pi/pull/10286)

### 6. #10275 — 添加 Kenari 作为 API Key 提供程序（已合并）
**内容**：支持 Kenari (`https://kenari.id/v1`)，通过 `/login` 输入 `kn-` 前缀密钥或环境变量 `KENARI_API_KEY`，模型列表自动从 `/v1/models` 拉取。
**意义**：增加亚太地区用户的接入选择。
🔗 [PR #10275](https://github.com/earendil-works/pi/pull/10275)

### 7. #10194 — Anthropic OAuth 支持代码登录方式（已合并）
**内容**：在远程服务器上使用 Pi 时，可通过复制登录页面代码进行授权，避免 localhost 重定向的失败。
**意义**：大幅改善远程/SSH 环境下登录 Anthropic 的体验。
🔗 [PR #10194](https://github.com/earendil-works/pi/pull/10194)

### 8. #7610 — 添加 LLM Gateway 和 LLM Gateway DevPass 提供程序（开发中）
**内容**：集成 OpenRouter 风格的路由服务 LLM Gateway，作为内置的 `openai-completions` 提供程序。
**意义**：丰富提供程序生态，为某些地区用户提供更低延迟的替代选择。
🔗 [PR #7610](https://github.com/earendil-works/pi/pull/7610)

### 9. #8383 — 修复 Gemini 3.7 Flash 禁用思考模式失败（开发中）
**内容**：将 `getDisabledThinkingConfig` 中 `gemini-3.7-flash` 的禁用思考级别从 `MINIMAL` 改为 `LOW`，避免 400 错误。
**意义**：保障 Gemini 模型正常使用，特别是需要关闭思考以节省成本时。
🔗 [PR #8383](https://github.com/earendil-works/pi/pull/8383)

### 10. #10295 — Coding Agent 中 Radius 登录动画与介绍（已合并）
**内容**：为 “Sign in with Radius” 按钮添加四色流光动画，并在登录页面增加 Radius 介绍文字。
**意义**：提升视觉体验和品牌辨识度。
🔗 [PR #10295](https://github.com/earendil-works/pi/pull/10295)

---

## 功能需求趋势

| 方向 | 具体表现 |
|------|----------|
| **新模型与提供者** | 社区持续要求支持更多低成本模型（Cloudflare Clef、Mistral、Kenari），以及更灵活的路由/网关（LLM Gateway）。 |
| **MCP 集成增强** | 多项议题要求支持 Unix Socket（#10247）、分离同一 URL 下的不同 OAuth 账户（#10252），以及优化初始化/关闭流程（#10249）。 |
| **性能与内存优化** | 长对话全屏重绘风暴（#9255）、空闲进程内存占用（#10308）成为重点优化领域。 |
| **主题与 UI 自定义** | 系统主题默认后的兼容性 Bug 集中涌现（tmux 乱码、调色板过艳），以及请求添加 `headeronly` 启动模式（#10296）。 |
| **开发者工具** | JSON Schema 发布（#9880）、统一的包验证（#10197）将降低配置门槛和发布风险。 |
| **安全性** | `brace-expansion` 漏洞（#10288）暴露了 shrinkwrap 带来的依赖更新延迟，社区提出移除 shrinkwrap 的呼声（#5653）。 |

---

## 开发者关注点

### 高频痛点
1. **稳定性回归**：如 #10031（ESC 卡死）、#9688（剪贴板复制失效）等回归 Bug 严重影响日常工作流，用户期望更严格的回归测试。
2. **成本准确性问题**：#9980 的费用估算偏差持续受到质疑，PR #10286 的合并将直接回应这一需求。
3. **终端兼容性**：#10250（tmux 垃圾字符）、#10323（tmux 切换窗格时光标不隐藏）表明全屏 TUI 在多终端环境下的适配仍需打磨。
4. **OAuth 体验**：#10258（ChatGPT 登录失败）和 #10219（Atlassian MCP “Invalid scope”）反映 OAuth 流程的边缘情况处理不足。

### 积极趋势
- 社区成员主动提交性能优化（#10308 的内存优化分支）和安全修复（#10288 的漏洞通报），显示项目健康度较高。
- 新模型提供者的 PR 快速合并（如 #10322、#10275），体现了团队对扩展生态的积极态度。
- 开发者工具链（Schema 生成、包验证）正在向工程化方向迈进，有助于降低贡献门槛。

> **本期编辑**：技术分析师 @PiBot  
> **数据来源**：GitHub earendil-works/pi  
> **生成时间**：2026-10-02

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，我已根据您提供的 GitHub 数据，为您生成了 2026-10-02 的 Qwen Code 社区动态日报。

---

### Qwen Code 社区动态日报 (2026-10-02)

**今日速览**

今日，Qwen Code 社区发布 `v0.24.7-nightly` 版本，主要修复了代码模式文本对齐和权限授权问题。社区开发焦点高度集中在 **Managed Agent** 架构的后续阶段交付，特别是其持久化生命周期、安全模型及热点 Bug 修复，展现出向企业级、高可靠性平台演进的明确趋势。

---

#### 版本发布

- **[v0.24.7-nightly.20261001.a7deb01bcb]**: 发布夜间构建版本，包含两项关键修复：
    - **fix(core)**: 对齐了代码模式文本与延迟工具发现的逻辑。
    - **fix(permissions)**: 修正了权限授权流程中的问题。
    - **链接**: [Release v0.24.7-nightly.20261001.a7deb01bcb](https://github.com/QwenLM/qwen-code/releases/tag/v0.24.7-nightly.20261001.a7deb01bcb)

---

#### 社区热点 Issues

1.  **[#12380] Managed Agent 双路径架构提案**: 该 Issue 是整个 Managed Agent 功能集的母议题，定义了从现有 TypeScript Agent 到全新架构的分阶段交付路径。社区讨论热烈（38条评论），是目前最核心的架构演进方向。
    - **链接**: [Issue #12380](https://github.com/QwenLM/qwen-code/issues/12380)

2.  **[#12028] 非对话上下文 Token 治理追踪**: 随着模型上下文窗口增大，系统提示词、工具定义等“非对话”内容的 Token 消耗日益显著，此议题旨在追踪对此部分的精细化治理（18条评论），体现了社区对成本和性能优化的深度关注。
    - **链接**: [Issue #12028](https://github.com/QwenLM/qwen-code/issues/12028)

3.  **[#12867] Managed Agent D 阶段后续工作**: 作为 #12380 的子议题，详细规划了 Managed Agent 在 D 阶段的剩余工作，包括持久化生命周期、Actions、Agent 定义等核心概念（17条评论），表明社区正在快速推进该架构的落地。
    - **链接**: [Issue #12867](https://github.com/QwenLM/qwen-code/issues/12867)

4.  **[#13030] 为 Hosted 工作区添加只读搜索工具**: 该提议旨在为 Hosted Workspace 添加 `list_directory`、`glob` 等只读搜索工具（9条评论），反映了在托管环境中，用户对文件操作安全性与灵活性的平衡需求。
    - **链接**: [Issue #13030](https://github.com/QwenLM/qwen-code/issues/13030)

5.  **[#12889] 延迟 `tool_call` 允许空参数**: 新发现的 Bug，即使用 `deferred` 工具时，模型可能会为需要必填字段的工具发送空参数（7条评论），这直接影响了工具调用的可靠性，已被标记为待处理。
    - **链接**: [Issue #12889](https://github.com/QwenLM/qwen-code/issues/12889)

6.  **[#13180] Managed Agent 代理认证**: 提议为 Managed Agent 运行时 Broker 设计认证/凭证层（4条评论），从信任安排转向基于身份的认证，是提升架构安全性的关键一步。
    - **链接**: [Issue #13180](https://github.com/QwenLM/qwen-code/issues/13180)

7.  **[#13157] Agent Host 权限流与沙箱隔离**: 报告了在 Agent Host 模式下，越权调用会因触发拒绝流程而导致整个 Host 运行结束的严重问题（5条评论），指出了当前权限检查与沙箱隔离机制的缺陷。
    - **链接**: [Issue #13157](https://github.com/QwenLM/qwen-code/issues/13157)

8.  **[#13003] 性能优化：强命中时跳过选择器**: 提出在确定性快速召回已提供唯一强匹配时，跳过模型选择器的性能优化方案（6条评论），体现了社区对长会话及记忆模块延迟问题的关注。
    - **链接**: [Issue #13003](https://github.com/QwenLM/qwen-code/issues/13003)

9.  **[#13193] Managed Hooks 重复释放所有者**: 新提交的性能 Bug，报告了 `releaseEarlierOwners` 函数在每次加载和分离时释放所有早期激活的问题（3条评论），可能导致不必要的性能开销。
    - **链接**: [Issue #13193](https://github.com/QwenLM/qwen-code/issues/13193)

10. **[#13187] 托管 Turn 接管后审查的 36 条建议**: 对已合并 PR 的后续审查结果，提出了36条建议（3条评论），体现了社区严谨的代码审查文化，对代码质量和健壮性要求极高。
    - **链接**: [Issue #13187](https://github.com/QwenLM/qwen-code/issues/13187)

---

#### 重要 PR 进展

1.  **[#13138] 添加离线 W1b 恢复包**: 为一个完整的离线恢复工作流添加了证据收集、导出和比对的入口（评论无），是提升系统灾难恢复能力的关键功能。
    - **链接**: [PR #13138](https://github.com/QwenLM/qwen-code/pull/13138)

2.  **[#13192] 修复 Managed Agent 写入器与发布截止时间**: 修复了因时区差异导致的管理代理写入器租约和工具发布授权周期计算错误（评论无），对系统正确性至关重要。
    - **链接**: [PR #13192](https://github.com/QwenLM/qwen-code/pull/13192)

3.  **[#13135] 可靠关闭工作区绑定会话**: 实现了通过公共和 WebShell 生命周期操作，可靠关闭空闲的工作区绑定会话（评论无），提升了系统的资源管理能力。
    - **链接**: [PR #13135](https://github.com/QwenLM/qwen-code/pull/13135)

4.  **[#13179] 加固 Managed Agent 提交重试与工作隔离**: 包含三项鲁棒性修复：拒绝越权文件路径、加固提交重试逻辑等（评论无），旨在提升系统稳定性。
    - **链接**: [PR #13179](https://github.com/QwenLM/qwen-code/pull/13179)

5.  **[#13146] 允许 WebShell 信任无终端的工作区**: 新增 API 路由和界面操作，允许用户在没有终端的情况下也能信任一个工作区（评论无），改善了 Web shell 的用户体验。
    - **链接**: [PR #13146](https://github.com/QwenLM/qwen-code/pull/13146)

6.  **[#13084] 保护会话拥有的工具输出**: 为 Session 管理的工具输出增加了永久性退休、固定预算数据库读取等保护机制（评论无），加强了数据的持久化和安全。
    - **链接**: [PR #13084](https://github.com/QwenLM/qwen-code/pull/13084)

7.  **[#13156] 修复 MEMORY.md 索引链接截断**: 修复了一个 Bug，该 Bug 导致 MEMORY.md 索引在截断时破坏了 Markdown 链接（评论无），直接影响了记忆模块的可用性。
    - **链接**: [PR #13156](https://github.com/QwenLM/qwen-code/pull/13156)

8.  **[#13033] 默认延迟 Agent 和目标声明**: 将 Agent 和 Goal 相关的协调工具改为按需发现（评论无），有助于减少非对话 Token 消耗，是优化上下文效率的一部分。
    - **链接**: [PR #13033](https://github.com/QwenLM/qwen-code/pull/13033)

9.  **[#12901] 修复延迟 `tool_call` 在 Responses 提供者上的参数传递**: 修复了在 Responses 请求中，延迟工具的空参数问题（评论无），直接对应热门 Issue #12889，是重要的工具调用修复。
    - **链接**: [PR #12901](https://github.com/QwenLM/qwen-code/pull/12901)

10. **[#13151] 允许代码模式下并发 Bash 调用**: 允许模型在代码模式下使用 `Promise.allSettled` 并发执行 Bash 命令（已关闭），这一特性将显著提升代码生成和执行效率，是开发者期待的功能。
    - **链接**: [PR #13151](https://github.com/QwenLM/qwen-code/pull/13151)

---

#### 功能需求趋势

1.  **Managed Agent 架构演进**: 这是目前绝对的核心趋势。社区正围绕 `#12380` 母议题，集中讨论如何构建一个具有持久化生命周期、强大安全模型和独立可伸缩性的新一代 Agent 运行时。这是一个从原型到企业级平台的重大飞跃。
2.  **长上下文性能优化**: 以 `#12028` 为代表，社区对 Token 消耗的精细化管理提出了强烈诉求。无论是减少非对话上下文的开销，还是优化记忆模块的召回性能，都指向了在长上下文场景下降低成本、提升效率的迫切需求。
3.  **安全与沙箱隔离**: 多个 Issue 和 PR 都涉及安全，包括 Managed Agent 的认证、Agent Host 的权限沙箱以及工作区的文件操作权限。这表明在 Agent 能力增强的同时，安全隔离和权限控制是社区高度关注的核心问题。
4.  **稳定性和可靠性**: 社区在持续修复 Bug（如工具调用空参数、索引链接截断）和提升系统鲁棒性（如提交重试、会话可靠关闭）。这表明项目正从功能快速迭代期，进入强调稳定性和可维护性的成熟期。

---

#### 开发者关注点

1.  **非对话上下文成本**: 开发者普遍关注系统提示词、工具定义等隐形 Token 消耗，认为其在大上下文模型中被放大，是导致成本膨胀的“隐形杀手”。
2.  **工具调用的错误处理**: `deferred` 工具允许空参数等 Bug 表明，当前工具调用的 schema 校验和错误处理逻辑存在薄弱环节，影响了 Agent 执行任务的成功率。
3.  **Agent Host 与沙箱的交互**: #13157 指出的问题揭示了在无交互模式下，错误的权限流可能导致整个执行环境崩溃，这是一个严重的生产环境风险，需要优先解决。
4.  **审查文化带来的开发压力**: #13187 和 #13133 等 Issue 展示了社区极其严格的代码审查流程，虽然保证了代码质量，但也可能导致 PR 合并速度变慢，对开发者而言是一种成本。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

# DeepSeek TUI 社区动态日报

**日期**: 2026-10-02  
**数据来源**: [Hmbown/Codewhale (原 DeepSeek TUI)](https://github.com/Hmbown/DeepSeek-TUI)

---

## 今日速览

社区今日没有新版本发布，但 `v0.10.1` 的集成工作进入第二阶段（PR #6815），多项由贡献者 `asto18089` 提交的关键修复已批量合并（PR #6799）。此外，一项关于成立汉化组的 Issue（#6804）获得了社区关注，反映出项目国际化文档的痛点。Issue 方面剩余 5 条均已关闭或处于讨论中，社区活跃度集中于 PR 的合并与测试。

---

## 社区热点 Issues

> 过去 24 小时更新共 5 条，以下全部列出。

### 1. #6309 [CLOSED] 希望恢复“YOLO 模式”（一键批准）
- **作者**: weifeng89  
- **摘要**: 用户喜欢 Codewhale 作为 IT 支持工具，但每次操作都要点击确认非常烦人，希望恢复之前的一键执行模式（YOLO）。  
- **社区反应**: 6 条评论，无赞——该 Issue 已关闭，但讨论热度较高，属于用户对操作效率的强烈需求。  
- **链接**: [Issue #6309](https://github.com/Hmbown/Codewhale/issue/6309)

### 2. #6804 [OPEN] 号召：成立汉化组
- **作者**: SparkofSpike  
- **摘要**: 因 CodeWhale 文档量大，AI 翻译质量仅“可读”但不流畅，作者希望成立 QQ 群进行人工汉化，并同步更新英文版本。  
- **社区反应**: 2 条评论，目前处于召集阶段，反映了非英语用户对高质量本地化的迫切需求。  
- **链接**: [Issue #6804](https://github.com/Hmbown/Codewhale/issue/6804)

### 3. #6814 [CLOSED] 完成 Codewhale-ratatui 组件目录和 README 画廊
- **作者**: Hmbown  
- **摘要**: 完成了组件目录及创始人扩展的设计，PR #3 已合并并通过全部 CI 检查。  
- **社区反应**: 无评论，属于基础设施完善，降低了新贡献者的上手门槛。  
- **链接**: [Issue #6814](https://github.com/Hmbown/Codewhale/issue/6814)

### 4. #6582 [CLOSED] hooks: 在 stdin 中为 shell tool_call_after 提供结构化执行收据
- **作者**: wuisabel-gif  
- **摘要**: 为 MemoryWhale 插件提供支持，记录 Codewhale 运行的 shell 命令（command、cwd、exit code、output），以便跨会话记忆。  
- **社区反应**: 无评论，已合并，属于插件生态扩展。  
- **链接**: [Issue #6582](https://github.com/Hmbown/Codewhale/issue/6582)

### 5. #6792 [CLOSED] FEAT-026: 完成 session 命令形状和提取边界
- **作者**: aboimpinto  
- **摘要**: EPIC-006 的最后一个 session-group 任务，解决 `/structcopy` 访问主 App 状态以及 session group 的依赖问题，为独立 crate 提取铺平道路。  
- **社区反应**: 无评论，代码架构优化。  
- **链接**: [Issue #6792](https://github.com/Hmbown/Codewhale/issue/6792)

---

## 重要 PR 进展

> 过去 24 小时更新共 23 条，以下选取 10 条对功能或稳定性影响最大的条目。

### 1. #6815 [OPEN] v0.10.1 集成，第二部分：wave/0.10.1-next 上的剩余修复
- **作者**: Hmbown  
- **摘要**: 继 #6782 合并后，继续将 0.10.1 的审计修复集成进来，包括空闲任务线程不再每 200ms 轮询磁盘、任务存储锁命名改进等。  
- **意义**: 版本集成关键步骤，影响性能和稳定性。  
- **链接**: [PR #6815](https://github.com/Hmbown/Codewhale/pull/6815)

### 2. #6805 [OPEN] feat(plugins): 支持审核过的 OAuth AI 提供商
- **作者**: LIghtJUNction  
- **摘要**: 插件包可声明 OpenAI 兼容的 AI 提供商及 OAuth 客户端，通过新的 extensions 字段实现，无需额外的代理处理。  
- **意义**: 插件系统重大扩展，允许第三方服务无缝集成。  
- **链接**: [PR #6805](https://github.com/Hmbown/Codewhale/pull/6805)

### 3. #6715 [OPEN] fix(auth): 选择、显示并切换 ChatGPT 和 xAI 账号
- **作者**: Hmbown  
- **摘要**: 创始人有两个 ChatGPT 账号，之前无法选择；该 PR 增加账号列表显示、切换功能，并改进用量限制错误提示。  
- **意义**: 解决多账号使用痛点，提升认证体验。  
- **链接**: [PR #6715](https://github.com/Hmbown/Codewhale/pull/6715)

### 4. #6782 [CLOSED] v0.10.1 集成：wave/0.10.1-next
- **作者**: Hmbown  
- **摘要**: 完成了 0.10.1 审计修复的合并，包含来自 #6793、#6799、#6802 的贡献者 PR，修复了撤销、Linux 权限等问题。  
- **意义**: 版本集成里程碑，为后续发布铺路。  
- **链接**: [PR #6782](https://github.com/Hmbown/Codewhale/pull/6782)

### 5. #6802 [CLOSED] 合并 #6741：MCP tools/call 预算，每次请求一个截止时间
- **作者**: Hmbown  
- **摘要**: 正式合并 @asto18089 的 #6741 修复：为 MCP `tools/call` 分配独立的请求预算，防止长时间运行的工具调用被过早 kill。  
- **意义**: MCP 工具调用稳定性修复，直接影响用户构建、测试等长时操作。  
- **链接**: [PR #6802](https://github.com/Hmbown/Codewhale/pull/6802)

### 6. #6799 [CLOSED] 合并 asto18089 的队列：七个 PR 作为原始提交
- **作者**: Hmbown  
- **摘要**: 批量合入 @asto18089 的 #6736~#6744（除 #6741 外），包括上下文路径相对化、JS 执行子进程超时杀死、视觉分析超时修复、空闲看门狗优化等。  
- **意义**: 一次性解决多个关键缺陷，贡献者质量很高。  
- **链接**: [PR #6799](https://github.com/Hmbown/Codewhale/pull/6799)

### 7. #6743 [CLOSED] fix(tools): 在超时时杀死 JS 执行子进程并提高上限
- **作者**: asto18089  
- **摘要**: `execute_js_execution_tool` 之前只用 `timeout(120s, ...)`，超时后不杀死子进程，Node 持续占用资源。现改为强制杀掉，并将 cap 从 120s 适当提高。  
- **意义**: 修复资源泄漏 bug，保证工具调用安全性。  
- **链接**: [PR #6743](https://github.com/Hmbown/Codewhale/pull/6743)

### 8. #6742 [CLOSED] fix(vision): 限制连接数并为每次请求包裹 30 分钟超时信封
- **作者**: asto18089  
- **摘要**: `image_analyze` 之前使用一个 120s 的客户端超时覆盖整个调用，导致大图片上传或生成失败。现改为独立超时（30 分钟）并限制连接数。  
- **意义**: 视觉分析稳定性提升，支持更大图片和慢速提供商。  
- **链接**: [PR #6742](https://github.com/Hmbown/Codewhale/pull/6742)

### 9. #6740 [CLOSED] fix(tasks): 保持空闲看门狗在工具调用飞行时不误杀
- **作者**: asto18089  
- **摘要**: 后台任务空闲看门狗（默认 120s）在静默工具调用（如长期构建）期间会错误触发杀死。修复后，工具调用开始和结束之间不统计空闲。  
- **意义**: 防止长时间后台任务被误杀，提高可靠性。  
- **链接**: [PR #6740](https://github.com/Hmbown/Codewhale/pull/6740)

### 10. #6737 [CLOSED] fix(context): 相对化项目指令和 constitution 源标签
- **作者**: asto18089  
- **摘要**: `<project_instructions source="...">` 之前携带绝对路径，导致迁移目录后产生虚假的 `<context_update>` 历史追加。现改为仓库相对路径。  
- **意义**: 修复上下文一致性 bug，减小历史膨胀。  
- **链接**: [PR #6737](https://github.com/Hmbown/Codewhale/pull/6737)

---

## 功能需求趋势

从近期 Issue 和 PR 分析，社区最关注的方向包括：

- **操作效率**（YOLO 模式、一键批准）——用户希望减少手动确认步骤，更流畅地使用 AI 支持。
- **插件生态扩展**（OAuth 提供商、MemoryWhale 集成）——社区正在构建丰富的插件体系，以支持第三方服务、记忆持久化等。
- **国际化与本地化**（汉化组）——非英语用户对文档和界面的母语支持需求强烈。
- **认证与账号管理**（多账号切换、账号状态提示）——随着 ChatGPT/xAI 等服务的普及，多账号管理成为刚需。
- **稳定性与超时处理**（MCP、JS、视觉长超时）——大量 PR 集中在消除隐藏的僵尸进程、看门狗误杀、网络超时等边界情况。

---

## 开发者关注点

根据 Issue 讨论和 PR 反馈，开发者反馈中的痛点与高频需求包括：

- **“点按审批” 烦恼**：每次操作都要手动确认，打断工作流，希望回到“YOLO mode”。
- **AI 翻译质量不足**：自动翻译的技术文档“能读但费力”，需要人工汉化组的介入。
- **长时工具调用被意外终止**：构建、测试、爬虫等操作因超时或看门狗机制被误杀，影响开发体验。
- **账号混淆与权限提示不清晰**：登录了多个账号但无法切换，用量限制错误未指明具体账号。
- **子进程资源泄漏**：`timeout` 后未杀死后台进程，导致 CPU 和文件 handle 持续占用。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*