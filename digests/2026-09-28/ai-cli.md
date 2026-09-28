# AI CLI 工具社区动态日报 2026-09-28

> 生成时间: 2026-09-28 01:10 UTC | 覆盖工具: 9 个

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

好的，作为一名专注于 AI 开发工具生态的资深技术分析师，现根据您提供的 2026-09-28 各主流 AI CLI 工具的社区动态，为您呈现一份横向对比分析报告。

---

## AI CLI 工具生态横向对比分析报告 (2026-09-28)

### 1. 生态全景

当前 AI CLI 工具生态正处于从“能用”向“好用”跨越的关键阶段。**稳定性、安全性与 Agent 可靠性**成为全行业的共同攻坚方向，而不仅仅是功能堆叠。各工具在激烈竞争的同时，也展现出不同的技术路线和社区定位：**Claude Code** 与 **Gemini CLI** 在 Agent 架构和安全性上引领探索，**OpenAI Codex** 与 **Kimi Code CLI** 则饱受跨平台兼容性问题的困扰，**GitHub Copilot CLI** 作为老牌劲旅，侧重于精细化权限控制和工作流集成。社区反馈已从早期的“尝鲜”转向对 **数据一致性、进程管理和性能退化** 等生产环境核心痛点的严肃讨论，预示着整个赛道正在为大规模采用做准备。

### 2. 各工具活跃度对比

| 工具名称 | 今日新增/活跃 Issues | 今日活跃 PRs | 今日版本发布 | 核心活跃议题 |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 10 (社区精选) | 1 | 0 | Cowork 功能退化、Windows 路径 Bug、Session 资源泄漏 |
| **OpenAI Codex** | 10 (社区精选) | 10+ (密集合并) | 6 (Rust SDK alpha) | Windows 闪窗、Linux 桌面 26.924 卡死、子进程信号处理 |
| **Gemini CLI** | 10 (社区精选) | 10 (多个开放的) | 0 | 子 Agent 状态误报、Agent 挂起、安全检查加固 |
| **GitHub Copilot CLI** | 10 (社区精选) | 1 (疑似无效) | 1 (v1.0.89-5) | 工具白名单、模型切换、BYOK 配置问题、认证失效 |
| **Kimi Code CLI** | 0 | 0 | 0 | 无 |
| **OpenCode** | 10 (社区精选) | 10 (多个开放的) | 0 | MCP 进程泄漏、长期复制粘贴 Bug、SQLite WAL 膨胀、Go 订阅问题 |
| **Pi (earendil-works)** | 10 (社区精选) | 3 (1个已合并) | 0 | 上下文压缩功能崩溃、启动性能、扩展 API 改进 |
| **Qwen Code** | 10 (社区精选) | 10 (多个开放的) | 0 | Managed Agent 架构推进、凭证泄露修复、Ollama 兼容性 |
| **DeepSeek TUI** | 10 (社区精选) | 10 (多个开放的) | 0 | 长期运行性能退化、v0.10.1 版本集成冲刺、后台进程清理 |

**分析**:
*   **OpenAI Codex** 和 **Qwen Code** 是今日开发活动最密集的工具，前者在密集修复 Bug，后者在稳步推进重大架构变更。
*   **OpenCode**, **Qwen Code**, 和 **DeepSeek TUI** 的 PR 数量最多，表明这些项目处于快速迭代期。
*   **Kimi Code CLI** 连续 24 小时无活动，可能处于维护期或社区活跃度较低。
*   **GitHub Copilot CLI** 的 PR 活动异常，需警惕社区贡献热度下降。

### 3. 共同关注的功能方向

*   **跨平台（尤指 Windows）体验**：**Claude Code**（路径处理）、**OpenAI Codex**（闪窗、子进程）、**Gemini CLI**（无特别提及，但也是痛点）、**GitHub Copilot CLI**（Git 环境变量）、**OpenCode**（配置路径）均收到大量关于 Windows 平台兼容性、终端闪烁、路径转义和进程管理的投诉。**这是当前生态中最普遍的“水土不服”问题**。
*   **Agent 的可靠性与可观测性**：**Claude Code**（Cowork 数据泄漏）、**Gemini CLI**（子 Agent 状态误报）、**GitHub Copilot CLI**（计划模式竟能编辑）、**OpenCode**（Agent 配置转发错误）都暴露了 Agent 状态管理、意图理解和行为透明度的不足。社区不再满足于“能跑”，而是要求“可信赖”。
*   **安全性加固与权限控制**：**Gemini CLI**（路径遍历、环境变量泄漏）、**Claude Code**（MCP 协议漏洞）、**OpenCode**（重定向绕过权限）和 **GitHub Copilot CLI**（工具白名单需求）共同指向了对 **更精细化的权限模型** 和 **防止提示注入** 的强烈需求。
*   **上下文管理与压缩**：**Pi**（压缩后崩溃）和 **Claude Code**（压缩后丢失技能）的 Bug 表明，如何可靠、智能地管理 Agent 的上下文窗口，避免信息丢失或功能退化，是行业级的难题。
*   **MCP 协议兼容性**：**Claude Code** 和 **OpenCode** 都遇到了 MCP 协议实现的兼容性问题，这直接影响到外部工具生态的互联互通，是未来 Agent 能力扩展的关键瓶颈。

### 4. 差异化定位分析

| 工具名称 | 功能侧重 | 目标用户 | 技术路线与差异化 |
| :--- | :--- | :--- | :--- |
| **Claude Code** | **深度 Agent 协作 (Cowork)**，会话管理，技能系统 | 追求高效协作和复杂工作流的专业开发者 | 强调 AI 与 AI 的协作，在 Session 和 Agent 生命周期管理上探索最深，但功能复杂度也带来了稳定性的阵痛。 |
| **OpenAI Codex** | **IDE 级集成**，丰富的 SDK 生态 (Rust) | 希望在主流 IDE/终端中获得流畅 AI 体验的开发者 | 背靠 OpenAI，生态最广，但在 Windows 和 Linux 桌面端的稳定性是明显短板，正通过密集的 PR 修补。 |
| **Gemini CLI** | **内建安全与零配置沙箱**，多 Agent 框架 | 对安全合规和自动化可靠性要求极高的开发者 | 以 Google 的 AI 安全研究为背书，强调在 Agent 执行前、中、后都内建安全检查，这是其核心差异。 |
| **GitHub Copilot CLI** | 深度集成 **Git 工作流**，精细化权限 | 深度依赖 GitHub 生态的开发者，强调生产环境的可控性 | 功能演进最稳健，侧重在现有开发者工作流上“打补丁”，而非颠覆性创新。用户对权限、Token 开销等细节要求很高。 |
| **OpenCode** | 高度可扩展的 **TUI 与桌面应用**，MCP 生态 | 喜欢高度定制化和 TUI 体验的开发者 | 社区形态最接近开源 IDE，插件和 MCP 生态是其扩展性的核心，但“基础功能 BUG 长期不修”正在消耗社区耐心。 |
| **Pi (earendil-works)** | **本地模型 (llama.cpp) 优先**，多提供商支持 | 偏好自托管和本地模型的开发者和高级用户 | 独特的“本地模型”定位，但在压缩、扩展 API 等核心上存在系统性缺陷，性能退化问题突出。 |
| **Qwen Code** | **自有大模型 (Qwen) 驱动**，Managed Agent 架构 | 对中国模型生态和前沿 Agent 架构感兴趣的开发者 | 正在激进地进行架构重构（Managed Agent），并积极集成远程运行时，技术路线最前沿，但伴随较大风险。 |
| **DeepSeek TUI (Codewhale)** | **轻量 TUI 体验**，极致简洁 | 追求极简、资源占用低的开发者 | “小而美”的代表，定位明确，社区活动围绕稳定性（性能退化、进程管理）和国际化展开，适合入门和对性能敏感的用户。 |

### 5. 社区热度与成熟度

*   **社区热度最高（舆论场）**：**GitHub Copilot CLI** 和 **OpenCode** 的 Issue 讨论激烈，评论数和点赞数高，但舆情偏向负面（大量 Bug 和功能缺失投诉）。前者因其庞大的用户基数，后者因长期问题未解。
*   **快速迭代阶段**：**OpenAI Codex** (今日合并10+ PR)、**Qwen Code** (架构推进)、**DeepSeek TUI** (版本冲刺) 和 **OpenCode** (PR 活跃) 表现出最强的开发动能，处于快速解决 Bug 或构建新功能阶段。
*   **社区健康度**：**Gemini CLI** 的社区反馈质量较高，聚焦在深度技术问题 (Agent 状态、安全检查) 上；**DeepSeek TUI** 的贡献者活跃，有明确的版本发布计划。这些社区的“含金量”更高。
*   **成熟度观察**：**GitHub Copilot CLI** 和 **Claude Code** 的 Bug 报告更偏向于复杂场景下的细节问题，而非基础功能失效，这表明其核心功能相对成熟，正进入精细化打磨阶段。相反，**Pi** 和 **OpenCode** 存在一些长期未修复的基础交互 Bug，影响了用户对其成熟度的评价。

### 6. 值得关注的趋势信号

1.  **Agent 可靠性是“上车”的关键门槛**：无论是 **Gemini CLI** 的子代理状态错误，还是 **Claude Code** 的 Cowork 数据一致性，都说明当前的 Agent 系统远未达到值得信赖的程度。对于考虑引入 AI CLI 的团队，必须仔细评估 Agent 行为的可预测性和错误处理能力，否则自动化带来的风险可能大于收益。

2.  **安全与合规不再是“将来时”，而是“现在进行时”**：**多款不相关的工具不约而同地收到安全类 Issue 和修复 PR**（凭证泄露、路径遍历、环境变量固化），这强烈暗示 AI CLI 在使用中已经暴露了真实的安全风险。工具选择上，应优先考虑那些在内核层面就内建权限模型和安全沙箱的产品 (如 **Gemini CLI** 的路线)。

3.  **从“聊天”到“开发环境”的深度集成竞争**：社区对**工具白名单** (Copilot)、**IDE 深度加载** (OpenCode、Codex)、**非交互式模型列表查询** (Gemini CLI) 的需求，标志着 AI CLI 正在从单纯的“对话窗口”转变为用户“开发环境”的一部分。未来竞争的关键在于谁能更好地与 **Git、终端、IDE 和 CI/CD 流程** 无缝衔接。

4.  **国产工具进入多元化竞争**：**Kimi Code CLI** 和 **Qwen Code** 作为新生力量，展现了不同的路径。前者无活动，后者则展现出极强的工程野心 (Managed Agent 架构)。这预示着国产 AI 开发工具不再仅仅作为模型“壳”，而是开始探索自有的、更复杂的 Agent 架构，试图形成技术壁垒。

5.  **“跑得快”的代价往往是“站不稳”**：**OpenAI Codex** (桌面 26.924 版本大范围回退)、**Claude Code** (Cowork 合并后功能退化) 的案例表明，在 AI 工具领域，激进的功能堆叠或版本更新，很容易因测试不充分导致核心体验崩溃。这提醒开发者和团队，**为生产环境选择 AI 工具时，版本稳定性和社区修复速度比功能数量更重要**。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，作为专注于 Claude Code 生态的技术分析师，以下是对 `anthropics/skills` 仓库截止 2026-09-28 的数据分析报告。

---

### Claude Code Skills 社区热点报告 (截止 2026-09-28)

**核心洞察：社区正处于从“功能新增”向“生态成熟度”过渡的关键阶段。当前最集中的诉求并非创造更多新技能，而是解决现有核心技能（如 `skill-creator`、`mcp-builder`）的跨平台兼容性、可靠性及安全审计问题，并呼吁建立官方分发与治理机制。**

---

### 1. 热门 Skills 排行 (Pull Requests)

虽然列表中的 PR 以修复和改进为主，但以下项目代表了社区重点关注的 Skill 方向及其当前的技术痛点。

1. **`skill-creator` 修复 (PR #1298)**
   - **功能**: 帮助开发者创建新 Skill 的核心元技能。
   - **讨论热点**: 社区在“制造工具的工具”上投入了大量讨论。问题集中在 Windows 兼容性、子进程管理以及评测（eval）的假阳性/假阴性问题。这表明 Skill 创作本身的门槛和稳定性仍是主要挑战。
   - **状态**: 🟢 Open (自2026-06-10)
   - **链接**: https://github.com/anthropics/skills/pull/1298

2. **`mcp-builder` 修复 (PR #1742)**
   - **功能**: 自动化构建 MCP (Model Context Protocol) 服务器。
   - **讨论热点**: 随着 MCP 协议更新到 2.x 版本，社区的讨论聚焦于兼容性问题，尤其是 API 变更（如 `streamable_http_client` 重命名）和自定义 Header 配置方式的改变。这反映了一个活跃的基础设施生态正在快速演进。
   - **状态**: 🟢 Open (自2026-09-08)
   - **链接**: https://github.com/anthropics/skills/pull/1742

3. **`proofcore-contract-auditor` 智能合约审计 (PR #1771)**
   - **功能**: 对 Solidity 和 Rust 智能合约进行静态分析，并将审计证明锚定到 TON 区块链。
   - **讨论热点**: 作为 Web3 领域的新 Skill，它代表了社区对**垂直领域专业化**的兴趣。将 AI 分析与区块链存证结合，是一个新颖且高价值的方向。
   - **状态**: 🟢 Open (自2026-09-15)
   - **链接**: https://github.com/anthropics/skills/pull/1771

4. **`md2video-audio` 文档转视频 (PR #1703)**
   - **功能**: 将 Markdown 文档零成本地编译为带有拟人化配音的专业级 MP4 视频。
   - **讨论热点**: 这是一个极具创意和实用性的 Skill，代表了从“生成文档”到“生成多媒体内容”的进化。社区关注其通过 Marp + 语音合成的技术路线如何落地。
   - **状态**: 🟢 Open (自2026-09-01)
   - **链接**: https://github.com/anthropics/skills/pull/1703

5. **`pyxel` 复古游戏开发 (PR #525)**
   - **功能**: 使用 Python 的 Pyxel 库进行复古风格游戏的创建、调试和验证。
   - **讨论热点**: 这是一个长期存在的热门 PR，展示了社区对**创意和非工具类** AI 应用的强烈兴趣。讨论集中在如何通过无头输入驱动和帧检查等方式，让 AI 有效测试和验证游戏逻辑。
   - **状态**: 🟢 Open (自2026-03-05)
   - **链接**: https://github.com/anthropics/skills/pull/525

6. **`AWT (AI Watch Tester)` 端到端测试 (PR #822)**
   - **功能**: 为 Claude 赋予视觉和浏览器控制能力，实现零代码的端到端（E2E）测试。
   - **讨论热点**: 这是一个将 AI 能力与软件工程质量保障结合的典型代表。社区讨论聚焦于其“零代码”理念、视觉校验的可靠性，以及如何与现有测试框架集成。
   - **状态**: 🟢 Open (自2026-03-31)
   - **链接**: https://github.com/anthropics/skills/pull/822

7. **`blast-radius` 破坏性操作检查清单 (PR #1776)**
   - **功能**: 在执行批量或破坏性写入操作（如删除用户、清空数据）前，提供一个安全检查清单。
   - **讨论热点**: 这是一个安全导向的实用 Skill，直击 AI Agent 操作的“最后一公里”信任问题。它超越了数据查询的正确性，关注操作对“整个系统世界”的影响。
   - **状态**: 🟢 Open (自2026-09-17)
   - **链接**: https://github.com/anthropics/skills/pull/1776

---

### 2. 社区需求趋势 (Issues)

从 Issues 中可以看出，社区的需求正从“如何做”转向“如何安全、可靠、大规模地做”：

- **🔒 安全与信任 (Issue #492)**：社区最大的呼声之一。对在官方 `anthropic/` 命名空间下分发社区 Skill 可能导致权限滥用的风险表示高度担忧。这反映出社区对官方治理、签名和审计机制有强烈刚需。
  - **链接**: https://github.com/anthropics/skills/issues/492

- **🏢 组织级协作与分发 (Issue #228)**：用户不再满足于个人使用，而是需要一种官方、便捷的方式来在企业或团队内部共享和管理 Skills，避免通过 Slack/邮件手动拷贝的低效。
  - **链接**: https://github.com/anthropics/skills/issues/228

- **💡 新型 Skill 探索**：尽管热点是稳定性，但社区仍在积极提案新的 Skill 方向。
    - **紧凑型工作记忆** (Issue #1329)：为解决长对话中上下文窗口被 Agent 笔记占用的问题，提议使用符号化表示法来管理 Agent 状态。
    - **智能体治理 (Agent Governance)** (Issue #412)：将政策执行、威胁检测和审计追踪等安全模式系统化，作为一项独立 Skill。
    - **推理质量门禁 (Reasoning Gate Pipeline)** (Issue #1385)：一个覆盖任务前、中、后三个阶段的质量控制流水线，体现了对 AI 输出可靠性的极致追求。

- **⚙️ 核心技能稳定性与效率**：多个 Issues (#556, #1394, #1390, #1383) 专门反馈 `skill-creator` 和 `mcp-builder` 这些核心技能的 Bug。特别是 `skill-creator` 的 eval 系统在 Windows 上的失败率和隐含的 XSS 漏洞，是社区关注的焦点。同时，`claude-api` 技能一次性注入约 15.6 万 Token 耗尽上下文的问题 (Issue #1487) 也凸显了 Skill 资源管理的严峻挑战。

---

### 3. 高潜力待合并 Skills

以下是评论活跃、功能完整但尚未合并，预计未来可能落地的 PR：

1. **`md2video-audio`** (PR #1703): 功能新颖，直接解决了从技术文档到可传播视频的转换痛点，潜力巨大。
2. **`proofcore-contract-auditor`** (PR #1771): 切入 Web3 这一高价值垂直领域，技术方案独特，有望成为该领域的标杆 Skill。
3. **`pyxel`** (PR #525): 尽管 PR 存在时间长，但作为创意编程的典范，它展示了 AI 在非工具领域的潜力。一旦合并，将极大丰富生态的多样性。
4. **`AWT (AI Watch Tester)`** (PR #822): 将 AI 的视觉和多步推理能力直接应用于 E2E 测试，是对传统测试流程的颠覆性补充，落地价值高。
5. **`testing-patterns`** (PR #723): 一个综合性的测试技能，覆盖从单元测试到 React 组件测试等多个层面，是提升 AI 生成代码质量的关键基建。

---

### 4. Skills 生态洞察

**一句话总结：社区当前最集中的诉求是建立一个**可信、稳定且可治理的 Skill 分发与运行基础设施 **，而非单纯追求技能数量的增长；围绕 `skill-creator` 和 `mcp-builder` 等核心工具的可靠性修复与安全加固，是所有高级应用落地的先决条件。**

---

好的，这是根据您提供的 GitHub 数据生成的 2026-09-28 Claude Code 社区动态日报。

---

# Claude Code 社区动态日报 | 2026-09-28

## 今日速览

自上次发布以来，**无新版本发布**。社区焦点主要集中在 **Cowork 功能的遗留问题**（文件写入延迟、UX 退化）、**Windows 平台的斜杠命令与路径处理 Bug**，以及 **Session 会话管理中的资源泄漏与数据一致性问题**。此外，一条关于**安全审计日志** (sec-default) 的 PR 正在等待合并。

## 社区热点 Issues

以下挑选了 10 个最值得关注的 Issue，涵盖 Bug 反馈与功能请求。

1.  **[#76694] Cowork: 合并后新建项目丢失"选择文件夹"功能**
    -   **摘要**：自 Chat 与 Cowork 功能合并后，新建项目时原本的“选择文件夹”上下文菜单被替换为仅可上传文件的聊天式菜单。这严重破坏了 Cowork 原有的基于文件夹的工作流。
    -   **社区反应**：**35条评论，28个👍**。这是目前社区反响最强烈的 Bug，直接影响了核心功能的使用体验。
    -   **链接**: https://github.com/anthropics/claude-code/issues/76694

2.  **[#89398] Windows: 斜杠命令选择器仅在输入框开头输入 "/" 时才能打开**
    -   **摘要**：在 Windows 桌面版中，斜杠命令 (`/model`, `/help` 等) 的自动补全选择器只有在 "/" 是输入框第一个字符时才会弹出。但即便不在开头，命令也能运行，导致用户无法方便地发现和使用命令。
    -   **社区反应**：**15条评论，7个👍**。这是一个典型的 UI/UX 小问题，但影响日常使用的流畅性。
    -   **链接**: https://github.com/anthropics/claude-code/issues/89398

3.  **[#93482] Cowork: 文件写入报告成功，实际内容滞后一次提交**
    -   **摘要**：一个严重的**数据丢失**风险。在 Windows 平台上，`device_commit_files` 报告写入成功，但磁盘上的文件内容始终比预期落后一次更新（即写入的是前一次的数据）。这会导致用户以为代码已更新，实际使用的是旧版本。
    -   **社区反应**：**14条评论**。涉及数据一致性，需要高优先级修复。
    -   **链接**: https://github.com/anthropics/claude-code/issues/93482

4.  **[#92007] /model opusplan 命令失败: “Unsupported model”**
    -   **摘要**：`/model opusplan` 命令在使用了几个月后突然开始报错“不支持的模型”。这看起来是一个服务端或客户端配置的回归问题。
    -   **社区反应**：**7条评论，12个👍**。影响面广，很多用户依赖该命令切换模型。
    -   **链接**: https://github.com/anthropics/claude-code/issues/92007

5.  **[#94675] UserPromptSubmit 钩子无法区分用户输入与系统注入消息，存在提示注入风险**
    -   **摘要**：`UserPromptSubmit` 钩子在收到来自子代理、定时任务、心跳包等系统/代理自动注入的消息时，无法将这些消息与真正的用户打字输入区分开来。这为钩子处理逻辑带来了潜在的提示注入攻击面。
    -   **社区反应**：**3条评论，1个👍**。这是一个安全相关的重要问题，影响了自动化工作流的可靠性。
    -   **链接**: https://github.com/anthropics/claude-code/issues/94675

6.  **[#89938] SendMessage 报告成功但消息未送达；会话实例“失聪”**
    -   **摘要**：在 Linux 系统上，`SendMessage` API 返回 `{"success":true}`，但目标会话从未收到消息。同时，会话实例的双向通信都中断，导致主机的状态停留在“已连接”但实际无响应。
    -   **社区反应**：**3条评论，1个👍**。这是一个关键的 Agents 通信 Bug，严重影响协作和自动化流程的可靠性。
    -   **链接**: https://github.com/anthropics/claude-code/issues/89938

7.  **[#88128] MCP 协议：可选缓存提示缺失导致 tools/list 和 resources/list 被拒绝**
    -   **摘要**：MCP 协议中，如果 `tools/list` 或 `resources/list` 的响应里缺少了 `ttlMs` 或 `cacheScope` 这些可选缓存提示字段，请求就会被视为无效并拒绝。这不符合协议规范，导致不包含缓存的 MCP 服务端无法正常工作。
    -   **社区反应**：**1条评论**。协议兼容性问题，影响 MCP 生态的互通性。
    -   **链接**: https://github.com/anthropics/claude-code/issues/88128

8.  **[#82017] 会话压缩后丢失技能清单（skill_listing）**
    -   **摘要**：当长会话因 token 限制被自动压缩后，模型会丢失所有已注册技能的清单。后续只有新技能创建/变更的增量通知，但模型无法访问完整的技能列表，导致无法正确路由和调用已有技能。
    -   **社区反应**：**1条评论**。这是一个架构性问题，影响基于技能 (Skills) 的复杂工作流。
    -   **链接**: https://github.com/anthropics/claude-code/issues/82017

9.  **[#97409] Windows Bash 工具：双反斜杠被减半**
    -   **摘要**：在 Windows 上，通过 Bash 工具执行的命令中，**每一对连续的反斜杠 (`\\`)** 在到达 Bash 之前都会被减少为一个。这严重影响了需要转义符的脚本和路径操作（如正则表达式、PowerShell 命令）。
    -   **社区反应**：**1条评论**。一个具体的 Windows 平台 Bug，影响精度要求高的命令执行。
    -   **链接**: https://github.com/anthropics/claude-code/issues/97409

10. **[#97716] [新] 工作目录变更钩子未触发**
    -   **摘要**：`cwdChanged` 钩子（用于监听工作目录变化）在用户报告的环境中不工作。
    -   **社区反应**：**1条评论**。刚报告的 Bug，需要社区进一步验证。
    -   **链接**: https://github.com/anthropics/claude-code/issues/97716

## 重要 PR 进展

1.  **[#97688] [安全增强] sec-default: 收集器记录在用户层之后继续存在**
    -   **摘要**：此 PR 改进了安全默认设置 (sec-default)。当组织启用 sec-default 后，个人用户的插件将无法再删除或修改发送给其收集器的记录。这通过确保遥测日志流在用户层之后依然延续，增强了审计能力，确保了组织安全策略的强制执行。
    -   **状态**: OPEN
    -   **链接**: https://github.com/anthropics/claude-code/pull/97688

*(注：过去24小时内仅有1个活跃PR，其余为关闭的Issue状态更新。)*

## 功能需求趋势

从今日的 Issue 和 PR 中，可以提炼出社区最关注的几个方向：

1.  **Cowork 与协作工作流优化**：大量 Bug (#76694, #93482, #76233, #97058) 指向 Cowork 功能在合并后的种种问题，包括 UX 退化、数据丢失、资源泄漏等。社区迫切希望 Anthropic 能稳定和改善此功能。
2.  **MCP 协议兼容性与稳定性**：Issue #88128 和 #76239 反映了 MCP 协议实现中的兼容性问题（可选字段处理不当）和时序问题（服务器启动慢导致工具丢失）。这表明社区对 MCP 生态的可靠性有很高期望。
3.  **跨平台（特别是 Windows）的体验一致性**：多个 Bug (#89398, #93482, #97409, #93967) 专门针对 Windows 平台，涉及命令、文件路径、身份认证等核心功能。Windows 用户希望获得与 macOS 同样流畅的体验。
4.  **安全性与审计能力**：Issue #94675 关于提示注入风险，以及 PR #97688 关于增强安全默认设置，表明社区对 Agent 安全和组织合规性的关注度在提升。
5.  **会话管理与资源持久化**：Issue #82017（压缩后丢失技能）、#89938（通信失聪）、#76185（内存泄漏）和 #97058（进程上限耗尽）都指向了会话生命周期管理和资源状态的持久化问题，这在构建长时间运行的 Agent 任务时至关重要。

## 开发者关注点

综合来看，开发者们正面临以下痛点和高频需求：

-   **数据一致性与可靠性**：**Cowork 文件写入滞后** (#93482) 和 **SendMessage 状态虚假成功** (#89938) 是开发者最担心的两类问题，它们直接损害了对工具的信任。
-   **平台差异带来的挫败感**：**Windows 用户** 在命令、路径、认证等多个环节遇到“水土不服”的问题，这表明该平台的适配仍有较大提升空间。
-   **复杂工作流的“隐形”陷阱**：**会话压缩导致技能丢失** (#82017)、**Cowork 进程上限导致无法启动新会话** (#97058) 这类问题，只有在使用到高级功能（Skills、Cowork）时才会暴露，属于深度使用者的高频痛点。
-   **对基础功能的回归感到焦虑**：如 `/model opusplan` 不可用 (#92007)、斜杠命令菜单不工作 (#89398) 这类基础功能的突然失效，影响了正常的开发流程。开发者普遍希望新版更新能更稳定，避免引入此类回归 Bug。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报 | 2026-09-28

---

## 今日速览

今日 Codex 社区迎来 **6 个 Rust SDK alpha 版本** 的密集发布，但更受关注的是**Windows 桌面及 CLI 的多项严重 bug**——多起“闪窗”、启动卡死、会话卡住等问题的报告持续涌入。Linux 桌面在 26.924 版本也出现大量“无限加载”退步，开发者呼吁快速响应。社区反馈集中在 **桌面应用稳定性、子进程信号处理、Windows 终端兼容性** 上，同时也有不少 UI/UX 改进的 PR 正在合入。

---

## 版本发布

过去 24 小时内，OpenAI 发布了 **6 个 Rust SDK 的 alpha 版本**，均为渐进式迭代：

- [`rust-v0.159.0-alpha.11`](https://github.com/openai/codex/releases/tag/rust-v0.159.0-alpha.11)
- [`rust-v0.159.0-alpha.10`](https://github.com/openai/codex/releases/tag/rust-v0.159.0-alpha.10)
- [`rust-v0.159.0-alpha.9`](https://github.com/openai/codex/releases/tag/rust-v0.159.0-alpha.9)
- [`rust-v0.159.0-alpha.8`](https://github.com/openai/codex/releases/tag/rust-v0.159.0-alpha.8)
- [`rust-v0.159.0-alpha.7`](https://github.com/openai/codex/releases/tag/rust-v0.159.0-alpha.7)
- [`rust-v0.158.0-alpha.15.3`](https://github.com/openai/codex/releases/tag/rust-v0.158.0-alpha.15.3)

这些版本未附带详细 release notes，推测为内部 bug 修复与 API 调整，属于常规迭代。

---

## 社区热点 Issues

以下挑选 10 个关注度最高、影响范围最广的 Issue：

### 1. Windows: 安装 Codex daemon 后终端窗口反复闪烁 (Issue #48074)
- **链接**: [#48074](https://github.com/openai/codex/issues/48074)
- **热度**: 💬40 评论 | 👍74 点赞
- **摘要**: 安装 `codex daemon` 后，每次请求都弹出多个 Windows 终端窗口（闪烁），用户反馈强烈。涉及 CLI 和应用服务，是目前 Windows 用户的头号痛点。
- **社区反应**: 已有多个类似报告关联，开发者标记为 bug/windows-os/CLI/app-server。

### 2. Linux 桌面 26.924 无限卡死在“Starting your task” (Issue #48189)
- **链接**: [#48189](https://github.com/openai/codex/issues/48189)
- **热度**: 💬24 评论 | 👍42 点赞
- **摘要**: Linux Mint 上更新到 26.924.20706 后所有本地 Codex 任务均卡死，降级到 26.917.71314 可解。影响广，涉及 Plus 用户。
- **社区反应**: 多用户确认相同问题，已标记为 bug/app/app-server/Linux。

### 3. Electron 替换 libuv 的 SIGCHLD 处理函数导致子进程无法回收 (Issue #48554)
- **链接**: [#48554](https://github.com/openai/codex/issues/48554)
- **热度**: 💬22 评论 | 👍12 点赞
- **摘要**: Linux 桌面版使用 Electron 后，主进程安装了一个空的 SIGCHLD 处理函数，覆盖了 libuv 的处理，导致子进程无法回收、shell 环境超时、“Git 不可用”、线程加载失败。
- **社区反应**: 深度技术分析，被标记为 bug/app/Linux，开发团队需要紧急修复。

### 4. Windows 桌面更新后卡在加载界面 – app-server 进程需手动终止 (Issue #48333)
- **链接**: [#48333](https://github.com/openai/codex/issues/48333)
- **热度**: 💬22 评论 | 👍7 点赞
- **摘要**: 26.924.1866.0 版本，Windows 桌面打开后无限旋转，杀死后台 `codex.exe` 可恢复。用户需要通过任务管理器手动终止。
- **社区反应**: 多个 Windows 用户反馈类似问题，标记为 bug/windows-os/mcp/app/app-server。

### 5. Windows: 每次会话/回合都闪现可见的控制台窗口 (Issue #48422)
- **链接**: [#48422](https://github.com/openai/codex/issues/48422)
- **热度**: 💬16 评论 | 👍17 点赞
- **摘要**: 用户在 `codex-cli 0.157.1` 中发现每次与助手交互都会闪烁多个控制台窗，关联 Git 查询和 daemon 进程。
- **社区反应**: 关联 Issue #44768，社区认为这是 Windows 上最影响体验的 bug 之一。

### 6. Windows: 应用服务器 daemon 为每个 hook/shell 命令打开可见窗口 (Issue #44768)
- **链接**: [#44768](https://github.com/openai/codex/issues/44768)
- **热度**: 💬13 评论 | 👍4 点赞
- **摘要**: 共享 daemon 启动后，每个 hook 和 shell 命令都会弹出可见控制台窗口，严重影响开发体验。
- **社区反应**: 已存在多日，仍是高频问题，社区期待修复。

### 7. Windows 桌面更新后本地项目从侧边栏消失 (Issue #42739)
- **链接**: [#42739](https://github.com/openai/codex/issues/42739)
- **热度**: 💬32 评论 | 👍0 点赞
- **摘要**: 更新 Windows 桌面应用后项目列表消失，但本地文件夹仍在。影响面广，用户反映强烈。
- **社区反应**: 虽未获点赞，但评论数高，说明多人遇到相同问题。

### 8. Windows 桌面 26.903 版本：首次应答后无法发送后续消息 (Issue #44102)
- **链接**: [#44102](https://github.com/openai/codex/issues/44102)
- **热度**: 💬29 评论 | 👍2 点赞
- **摘要**: 第一个助手回复完成后，后续消息发送失败，阻塞对话。
- **社区反应**: 多个用户确认，影响连续性。

### 9. Linux 桌面 26.924 加载现有聊天记录挂起 (Issue #48345)
- **链接**: [#48345](https://github.com/openai/codex/issues/48345)
- **热度**: 💬11 评论 | 👍5 点赞
- **摘要**: 更新后打开历史或新建聊天均无限旋转，降级可解，再次确认 26.924 的退化。
- **社区反应**: 与 #48189 类似，但突出聊天列表加载问题。

### 10. Windows: `apply_patch` 报告虚假的重解析点错误 (Issue #46290)
- **链接**: [#46290](https://github.com/openai/codex/issues/46290)
- **热度**: 💬8 评论 | 👍1 点赞
- **摘要**: 在 Windows 10 上应用补丁时，由于重解析点（Junction/符号链接）导致错误，实际不影响功能但用户困惑。
- **社区反应**: 标记为 bug/windows-os/sandbox/tool-calls，属于边缘但影响开发工具可靠性。

---

## 重要 PR 进展

挑选 10 个合并或新创建的 PR：

### 1. 等待 Windows 沙箱配置服务启动 (PR #48829)
- **链接**: [#48829](https://github.com/openai/codex/pull/48829)
- **摘要**: 增加短暂等待，让沙箱配置服务有时间启动，避免桌面就绪检查过早超时。对 Windows 启动稳定性有帮助。
- **状态**: 已合并。

### 2. 允许归档尚未第一轮对话的线程 (PR #48828)
- **链接**: [#48828](https://github.com/openai/codex/pull/48828)
- **摘要**: 修复新创建的线程在第一次交互前无法归档的 bug。
- **状态**: 已合并。

### 3. 在 Ghostty 和 Kitty 终端中为转录链接显示手型光标 (PR #48827)
- **链接**: [#48827](https://github.com/openai/codex/pull/48827)
- **摘要**: 改善 TUI 交互体验，当鼠标捕获时在可点击链接上显示手型光标。
- **状态**: 已合并。

### 4. 保持语音 RTP 时间戳对齐 20ms 包 (PR #48824)
- **链接**: [#48824](https://github.com/openai/codex/pull/48824)
- **摘要**: 修复捕获抖动和静音切换导致 RTP 时间戳偏移的问题，确保接收端能够正常合帧。
- **状态**: 已合并。

### 5. 使用显式直方图桶统计工具和技能上下文指标 (PR #48819)
- **链接**: [#48819](https://github.com/openai/codex/pull/48819)
- **摘要**: 增加工具片段大小和命名空间数量的对数边界直方图，以及技能计数的整数边界直方图，提升可观测性。
- **状态**: 已合并。

### 6. 保留 Mermaid 标签中的标点符号和分号 (PR #48814)
- **链接**: [#48814](https://github.com/openai/codex/pull/48814)
- **摘要**: 修复在 Mermaid 标签中错误分割分号和过滤标点的问题，允许渲染复杂标签如 `A["Go []; &"]`。
- **状态**: 已合并。

### 7. 为空闲线程添加历史感知预预热 (PR #48812)
- **链接**: [#48812](https://github.com/openai/codex/pull/48812)
- **摘要**: 引入 `prewarm_with_history()` 方法，允许下一个回合复用已准备好的 WebSocket 响应，加速交互。
- **状态**: 已合并。

### 8. 在 TUI 完成页脚显示短回合持续时间 (PR #48807)
- **链接**: [#48807](https://github.com/openai/codex/pull/48807)
- **摘要**: 之前只显示超过 60 秒的时长，现在显示所有已知持续时间（包括亚秒级），提升透明度。
- **状态**: 已合并。

### 9. 修复 Windows 终端鼠标报告的 SGR 编码 (PR #48799)
- **链接**: [#48799](https://github.com/openai/codex/pull/48799)
- **摘要**: 解决某些 Windows 终端发送遗留鼠标报告的问题，通过独立写 SGR 编码请求来启用正确鼠标记录。
- **状态**: 已合并。

### 10. 修复 Unix 套接字通过长符号链接路径的连接问题 (PR #48772)
- **链接**: [#48772](https://github.com/openai/codex/pull/48772)
- **摘要**: 当控制套接字路径超过 Unix 套接字路径限制时，通过解析符号链接目标并重试来修复连接。
- **状态**: 已合并。

---

## 功能需求趋势

从近期 Issue 中可提炼出以下社区最关注的功能方向：

1. **IDE 与编辑器集成**：用户希望 Codex 能更好嵌入 IDE（如 VS Code、JetBrains），但目前仍以独立 CLI/TUI 为主。Issue #14044 提出动态对话重命名，#28977 建议桌面显示当前工作目录和 Git 分支，反映对开发上下文感知的需求。
2. **Windows 终端体验优化**：大量 Windows 用户在抱怨“闪窗”问题，但深层需求是希望 Codex CLI 在 Windows 上拥有与 Linux/macOS 同样静默的子进程管理能力。
3. **桌面应用稳定性**：Linux 和 Windows 桌面版 26.924 版本出现大范围卡死，社区急切要求快速回退或紧急修复补丁。
4. **MCP（模型控制协议）改进**：多个 PR 和 Issue 涉及 MCP 服务器状态发现、资源 URI 处理，说明社区正在推动更灵活的外部工具集成。
5. **语音与多媒体交互**：PR #48824 关于语音 RTP 时间戳对齐，以及 #46848 关于语音模式无法启动，显示用户对语音交互稳定性有需求。
6. **安全与权限管理**：浏览器 sandbox、网站权限缓存等问题反复出现（#36953、#43754、#41055），社区希望更清晰、可排错的权限管理界面。

---

## 开发者关注点

开发者反馈中的突出痛点与高频需求：

- **Windows 子进程管理**：daemon 启动后每个 hook 和 shell 命令都弹出可见控制台窗口，根本原因是 Windows 上缺乏类似 Unix 的 `SIGCHLD` 和 `setsid` 机制。建议使用 `CREATE_NO_WINDOW` 标志或 Windows 服务模式。
- **Linux 桌面信号处理退化**：Electron 替换 SIGCHLD 处理器是最新发现的深层问题，说明 Electron 集成需要更精细地处理原生信号。
- **版本升级后的兼容性**：26.924 版本在 Linux 和 Windows 上均有广泛退化，社区强烈建议 OpenAI 建立更严格的降级测试和回滚机制。
- **Git 集成与性能**：大量 Issue 提到 Git 查询导致闪窗（#48356），以及 Git 不可用（#48554），说明 Codex 对 Git 依赖敏感且实现不够稳健。
- **UI/UX 细节打磨**：TUI 中过长的消息隐藏、未读警告清除、模态框屏蔽滚轮等细节不断被用户提及，PR 中已有多种改进（#48775、#48761、#48805），说明团队正在积极回应。

---

**总结**：今日社区动态凸显了两大关键：**Windows 平台的终端兼容性问题** 和 **Linux 桌面 26.924 的稳定性回退**。好消息是开发团队正通过密集的 PR（今日至少 20+ 合并）逐一修复，尤其是在子进程、信号处理、TUI 交互方面。建议开发者保持更新到最新 alpha 版本，并在遇到严重 bug 时参考上述 Issue 报告。

*数据统计截止于 2026-09-28 23:59 UTC。*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，以下是根据您提供的 GitHub 数据，生成的 2026-09-28 Gemini CLI 社区动态日报。

---

# Gemini CLI 社区动态日报 | 2026-09-28

## 今日速览
今日社区动态集中在核心稳定性与安全性的修复上。**一个关键的 400 Bad Request 错误**（历史消息以模型回合结尾导致）已得到修复，同时一系列安全 PR 正在加固路径检查与外部执行环境。此外，**子代理中断误报为成功的 Bug** 引起社区热议，暴露了 Agent 状态管理中的深层问题。

## 社区热点 Issues

1.  **[#22323] 子代理达到最大轮数后被误报为成功**
    *   **热度**：评论 13 | 👍 2
    *   **原因**：这是一个高优先级 Bug。`codebase_investigator` 子代理在达到 `MAX_TURNS` 限制后，未被正确标记为中断，反而报告 `status: "success"` 和 `Termination Reason: "GOAL"`。这完全掩盖了任务被截断的事实，严重影响了用户对 Agent 行为的信任。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/22323

2.  **[#21409] 通用型 Agent 挂起**
    *   **热度**：评论 8 | 👍 8
    *   **原因**：社区反响强烈的高优先级 Bug。当 Gemini CLI 将任务委托给“通用型”子 Agent 时，会永久挂起，即便是简单的创建文件夹操作。用户唯一的解决方法是手动禁止使用子 Agent。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/21409

3.  **[#19873] 利用模型的 Bash 亲和性：零依赖 OS 沙箱与执行后意图路由**
    *   **热度**：评论 9 | 👍 1
    *   **原因**：这是一项大型功能请求，旨在利用 Gemini 模型原生擅长使用 `grep`、`sed` 等 Bash 工具的特点。提案建议通过创建一个零依赖的沙箱环境，在保证安全的前提下，让模型直接使用其最擅长的工具，而不是强制使用封装好的 API。这代表了 Agent 执行策略的一个潜在范式转变。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/19873

4.  **[#22745] 评估 AST 感知的文件读取、搜索与映射的价值**
    *   **热度**：评论 7 | 👍 1
    *   **原因**：一个功能探索性的 Epic。核心是评估是否应该引入能理解代码结构（AST）的工具，以实现更精确的方法体读取和代码库导航，从而减少 token 浪费和因对齐错误导致的额外交互轮数。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/22745

5.  **[#21968] Gemini 未能充分利用技能和子 Agent**
    *   **热度**：评论 6 | 👍 0
    *   **原因**：社区反馈表明，Gemini 模型很少主动使用用户自定义的技能（如 Gradle、Git 技能）和子 Agent，除非被明确指示。这直接影响了模型在特定领域任务上的效率和准确性。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/21968

6.  **[#26525] 自动内存功能：增加确定性机密脱敏并减少日志**
    *   **热度**：评论 5 | 👍 0
    *   **原因**：一个重要的安全问题。当前的“自动内存”功能在将对话历史发送给模型之前，依赖模型自身进行机密信息（如 API Key）脱敏，这存在风险。该 Issue 提议在发送前进行确定性脱敏。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/26525

7.  **[#26522] 阻止自动内存对低信号会话的无休止重试**
    *   **热度**：评论 4 | 👍 0
    *   **原因**：自动记忆 Agent 在遇到低价值的会话时，会进入无限重试循环，浪费资源和 token。此 Bug 直指 Auto Memory 功能的效率问题。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/26522

8.  **[#22267] 浏览器 Agent 忽略 settings.json 中的配置**
    *   **热度**：评论 4 | 👍 0
    *   **原因**：浏览器 Agent 无法读取并通过 `settings.json` 中的配置（如 `maxTurns`），这破坏了用户通过配置文件进行自定义和控制的预期，是一个明确的 Bug。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/22267

9.  **[#22232] 增强 Browser Agent 韧性：自动接管和锁恢复**
    *   **热度**：评论 4 | 👍 0
    *   **原因**：当浏览器 Profile 被锁定时（例如之前有未正常退出的进程），Browser Agent 的“快速失败”策略过于激进。此特性请求建议增加自动重试和会话接管机制，提高其稳定性和鲁棒性。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/22232

10. **[#21000] 实验：用原生文件工具创建和维护任务追踪器**
    *   **热度**：评论 4 | 👍 0
    *   **原因**：社区在探索更轻量、更持久的任务追踪方案。此 Issue 旨在替代现有的 `WriteToDo` 工具，该工具依赖“上下文内”的任务列表，存在上下文混乱和高 token 消耗的问题。
    *   **链接**：https://github.com/google-gemini/gemini-cli/issues/21000

## 重要 PR 进展

1.  **[#29527] 修复核心：确保请求内容不以模型回合结尾**
    *   **状态**：OPEN
    *   **摘要**：修复了在执行 `/rewind`、流中断等操作后，因历史记录以模型回合结尾而导致的 **400 Bad Request** 错误。这是一个关键的稳定性修复。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29527

2.  **[#29528] 修复 CLI：在无头模式下传播已解决的文件夹信任状态**
    *   **状态**：OPEN
    *   **摘要**：修复了在无头（Headless）模式下，即使工作区不被信任，也会错误地通知组件“已信任”的问题，解决了状态同步的分裂问题。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29528

3.  **[#29525] 修复 A2A 服务器：绝不从请求的 agentSettings 派生工作区信任**
    *   **状态**：OPEN
    *   **摘要**：安全性修复。防止 A2A 服务器在处理 `createTask` 时，直接信任由外部请求中 `agentSettings` 指定的工作区，消除了一个潜在的安全漏洞。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29525

4.  **[#29523] 安全性改进：为外部安全检查器提供最小化环境和输出上限**
    *   **状态**：OPEN
    *   **摘要**：安全性改进。限制了外部安全检查器进程的环境变量（防止泄露 API Key）和标准输出积累（防止无限输出），加固了沙箱。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29523

5.  **[#29522] 安全性改进：将 Glob 工具的匹配结果限制在已验证的搜索目录内**
    *   **状态**：OPEN
    *   **摘要**：安全性修复。Glob 工具在处理绝对路径模式（如 `/etc/*.conf`）时，可能绕过目录权限检查。此 PR 修复了路径验证逻辑，防止路径遍历攻击。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29522

6.  **[#29521] 安全性改进：将遗留检查点路径限制在检查点目录内**
    *   **状态**：OPEN
    *   **摘要**：安全性修复。修补了因 `path.join` 对 `../` 的归一化处理，导致检查点标签可以逃逸到目录之外的安全漏洞。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29521

7.  **[#29292] 修复检查点：在 loadCheckpoint 中验证 history 是否为数组**
    *   **状态**：CLOSED
    *   **摘要**：在加载检查点文件时，如果 `history` 属性为 JSON 格式有效但非数组（如 `null`），该 PR 会将其视为无效，防止了 `/resume` 等操作可能引发的崩溃。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29292

8.  **[#29294] 修复 CLI：防止因 stdout 争用和光标焦点导致的终端闪烁**
    *   **状态**：CLOSED
    *   **摘要**：解决了用户在命令执行或快速键入时，终端出现严重闪烁和撕裂的问题。这是对终端渲染性能的一个改进。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29294

9.  **[#29404] 功能添加：增加 'gemini models list' 带 JSON 输出的子命令**
    *   **状态**：OPEN
    *   **摘要**：为非交互式集成提供了编程发现可用模型的能力。外部工具现在可以通过 `gemini models list -o json` 获取模型列表，而无需解析交互式对话。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29404

10. **[#29411] 修复 CLI：将恢复最新会话解析为最近活跃的会话**
    *   **状态**：OPEN
    *   **摘要**：修复了 `--resume` 逻辑，使其根据“最近活动时间”而非“开始时间”来恢复会话。这避免了重新进入一个“较新”但已不活跃的短暂会话。
    *   **链接**：https://github.com/google-gemini/gemini-cli/pull/29411

## 功能需求趋势

*   **Agent 生态的智能化和可观测性**：社区强烈希望 Agent（特别是子 Agent 和浏览器 Agent）更智能。这包括：能够**自动识别并使用自定义技能**、**正确报告状态（如子 Agent 被中断）**、以及**暴露其执行轨迹**以便调试和共享。用户不再满足于黑盒化的 Agent 行为。
*   **安全与沙箱的深化**：随着 Agent 能力的增强，安全问题日益突出。大量 Issue 和 PR 集中在**零依赖沙箱**、**确定性机密脱敏**、**路径遍历防护**和**最小化外部环境变量**上。社区和开发者都在积极推动一个更安全、更可控的执行环境。
*   **文件读取与代码理解的效率优化**：针对大文件和复杂代码库，社区在探索更高效的方式。主要方向是**AST 感知的代码读取与搜索**，旨在减少上下文 Token 消耗，提高任务完成的准确率。
*   **终端体验的打磨**：尽管是细节，但**终端无闪烁行为和更好的交互提示**（如创建 Vite 项目时避免卡住）仍然是社区关注的重点，直接影响用户日常使用体验。
*   **非交互模式的支持**：通过 `gemini models list` 等命令的加入，体现了社区对**非交互式、可编程**使用 CLI 的需求。外部工具和自动化流程需要标准化的方式与 CLI 交互。

## 开发者关注点

*   **Agent 可靠性与状态不一致**：开发者最大的痛点集中在 Agent 的可靠性上。**Generalist Agent 挂起**、**Browser Agent 忽略配置**、**子 Agent 中断被误报为成功**等问题频繁出现，导致开发工作流被严重打断。Agent 的内部状态与最终报告状态之间的不一致让开发者感到困惑和不信任。
*   **安全问题与控制**：开发者对安全问题高度敏感。当前 Agent 在执行时可能会无意中**泄露环境变量（如 API Key）**，或者通过 **Glob 工具、检查点操作**等方式进行路径遍历。开发者希望 CLI 能提供更强的沙箱、路径认证和策略控制能力。
*   **用户体验的细微缺陷**：诸如 **终端闪烁**、**在 `vite create` 等交互式命令行前卡住**、**`\n` 转义处理不当**等问题，虽然单个看不大，但累积起来严重影响了开发者的使用流畅度和好感。
*   **自动内存系统的效率**：开发者对自动内存功能存在疑虑，主要体现在**低价值会话的无限重试**、**日志泄露风险**和**无效补丁的静默跳过**。这表明社区期望一个更稳健、可预测、低噪声的内存管理功能。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区动态日报 — 2026-09-28

## 📌 今日速览

今日发布小版本 v1.0.89-5，新增三个用户交互与自定义规则改进。社区最关注的热点 Issue 集中在“工具白名单”、“模型会话内切换”和“Git worktree 生命周期管理”三大功能需求上。此外，多个与认证令牌失效、MCP 连接噪音及 BYOK 采样参数相关的 bug 报告正在 triage 阶段。

---

## 🚀 版本发布

### v1.0.89-5
- **鼠标交互改进**：左键点击 `ask_user` 和表单输入区域可聚焦并将光标移至点击位置。
- **Claude Code 规则文件支持**：新增对 `.claude/rules` 中自定义指令的支持。
- **会话状态提示**：侧边栏中的会话在完成一个未读的 turn 后会显示蓝点。

---

## 🔥 社区热点 Issues（Top 10）

| # | Issue | 评论数 | 👍 | 重要性摘要 |
|---|-------|--------|----|------------|
| 1 | [#1973 交互模式工具白名单](https://github.com/github/copilot-cli/issues/1973) | 13 | 29 | 用户希望跳过只读工具的逐次审批，但 `/allow-all` 过于危险，需要可配置的白名单。 |
| 2 | [#1857 取消已排队消息](https://github.com/github/copilot-cli/issues/1857) | 12 | 29 | 当 agent 忙碌时，用户无法取消已排队的指令，急需消息队列管理功能。 |
| 3 | [#3709 允许 /model 切换 BYOK 等本地模型](https://github.com/github/copilot-cli/issues/3709) | 8 | 33 | BYOK 模式下无法通过 `/model` 选择本地托管的模型，限制了多模型工作流。 |
| 4 | [#4929 进程本地认证令牌停止刷新](https://github.com/github/copilot-cli/issues/4929) | 7 | 0 | 长时间运行的进程 auth 令牌失效后无法恢复，必须重启，严重影响生产使用。 |
| 5 | [#4905 桌面应用会话分钟级死亡](https://github.com/github/copilot-cli/issues/4905) | 6 | 4 | 桌面应用内置 CLI 会话因凭据注册失效导致 MCP 目录变 stale，阻碍工具发现。 |
| 6 | [#2627 可配置系统提示减少固定 token 开销](https://github.com/github/copilot-cli/issues/2627) | 6 | 21 | 系统提示占用约 20.5k token，用户希望裁剪不必要部分以释放上下文窗口。 |
| 7 | [#1613 内建 git worktree 生命周期管理](https://github.com/github/copilot-cli/issues/1613) | 4 | 38 | 希望 Copilot 自动创建/销毁 worktree，实现隔离任务工作。 |
| 8 | [#179 全局可配置允许工具](https://github.com/github/copilot-cli/issues/179) | 4 | 43 | 类似 Claude Code 的全局工具白名单，从 `config.json` 配置，呼声极高。 |
| 9 | [#1697 会话分叉](https://github.com/github/copilot-cli/issues/1697) | 4 | 25 | 支持将一条对话分支成多个并行会话并共享上下文，解决多任务切换痛点。 |
| 10 | [#4531 从 CLI 启动 VS Code 导致 Git 发现失败](https://github.com/github/copilot-cli/issues/4531) | 3 | 2 | 导出的空 `GIT_CONFIG_VALUE` 环境变量破坏 VS Code 的 Git 功能，Windows 平台突出。 |

---

## 🛠 重要 PR 进展

目前只有 **1 条 PR** 在过去 24 小时内更新，且内容异常（疑似测试或误创建）：

- [#3817 kCreate "#"](https://github.com/github/copilot-cli/pull/3817)  
  作者：edge500 | 创建于 2026-06-15 | 更新于 2026-09-27  
  摘要：`aquellos`（无实际描述）  
  **状态**：未合并，内容不明确，可能为测试提交。

> 说明：当前社区活跃 PR 较少，主要精力集中在 Issue 反馈与 bug 修复上。建议关注上述热点 Issue 的讨论与进展。

---

## 📈 功能需求趋势

从近期 Issue 中可以提炼出以下社区最关注的功能方向：

1. **精细化权限控制**  
   - 工具白名单（#1973、#179）：区分只读与危险操作，避免全盘允许。
   - 计划模式禁止编辑（#2075）等。

2. **多模型灵活切换**  
   - 支持 BYOK/本地模型在会话内动态切换（#3709），以及 `/model` 命令扩展。

3. **会话与上下文管理**  
   - 会话分叉（#1697）、可配置系统提示（#2627）、压缩不丢失上下文（#1571、#3703）。

4. **MCP 与外部服务稳定性**  
   - OAuth 远程 MCP 服务器支持（#1305）、MCP 连接通知不刷屏（#4907）、动态工具列表更新（#3125）。

5. **Git 与工作流集成**  
   - 内建 worktree 管理（#1613）、shell 工具执行计时（#3055）。

6. **认证与 token 生命周期**  
   - 长时间运行进程的 token 刷新（#4929）、桌面应用会话凭据过期问题（#4905）。

---

## 🧑‍💻 开发者关注点（痛点 & 高频需求）

- **认证令牌失效后无法恢复**：进程内无法自动刷新，必须重启，影响 CI 或长时间任务。  
- **BYOK 配置问题**：greedy 采样（temperature=0）导致小模型退化或挂起（#4950）；`reasoning` 字段没被识别（#3195）。  
- **MCP 连接噪音**：反复的“连接中/已连接”消息刷屏，且会话空闲时仍持续。  
- **工具超时**：grep 工具在大仓库中超时无结果（#2985），用户被迫使用 ripgrep。  
- **压缩丢失上下文**：`/compact` 后关键信息丢失，需要手动补回。  
- **复制命令包含不可见字符**：(#2285) 复制代码块后粘贴到其他终端执行失败。  
- **计划模式竟能执行编辑**：(#2075) 安全隐患，计划模式本该只读却可以写文件。  
- **Windows 平台 Git 环境变量污染**：(#4531) 启动 VS Code 后 Git 功能异常。

---

> 📊 数据截止：2026-09-28 00:00 UTC  
> 数据源：github.com/github/copilot-cli  
> 报告生成：AI 技术分析师

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 | 2026-09-28

## 今日速览
1. 社区持续关注 **CLI 复制粘贴**、**Tab 键切换 Agent** 等基础交互 bug，前者已累积 64 条评论但半年未修复。
2. 多项 **MCP 与 Session 相关**的 Bug 和 PR 活跃，涉及进程泄漏、权限绕过、数据库残留等关键问题。
3. **Go 订阅认证**、**LSP 支持降级**、**桌面端权限模型** 成为用户高频反馈痛点。

---

## 社区热点 Issues（10 条）

### 1. [#13984 can not copy and paste in opencode CLI](https://github.com/anomalyco/opencode/issues/13984) 🔥 64 评论 · 32 👍
**长期未修复的复制粘贴 Bug**。用户反馈 CLI 中 Ctrl+C 复制但粘贴无效，右下角显示“copied”却无实际内容。该 Issue 已开放超过 7 个月，社区多次催更，是当前最受关注的交互问题。

### 2. [#49133 TUI: tab key does not switch agents, shift+tab cycles instead](https://github.com/anomalyco/opencode/issues/49133) 🟢 已关闭 · 16 评论
v2.0.3 中 Tab 键无响应，Shift+Tab 反向循环。官方已修复并关闭，但用户对基础快捷键的稳定性仍有疑虑。

### 3. [#32157 [2.0] Configurable mid-run prompt delivery: queue vs steer](https://github.com/anomalyco/opencode/issues/32157) 🚩 9 评论 · 84 👍
**高票功能请求**：希望在用户提交提示时区分 `queue`（排队）、`steer`（转向）和 `break`（中断），并支持 compaction-aware 的 steer 语义。社区认为该特性可大幅度改善多 Agent 协作体验。

### 4. [#6156 Opencode doesn't know the location of its config file](https://github.com/anomalyco/opencode/issues/6156) 🟢 已关闭 · 9 评论
用户询问配置路径时得到不一致答案（根目录、`.config/opencode`、macOS 的 `~/Library/Application Support/`）。暴露了配置文件发现机制的混乱。

### 5. [#49027 Agent config extra fields forwarded verbatim causing invalid_request_error](https://github.com/anomalyco/opencode/issues/49027) 🟡 开放 · 5 评论
Windows 用户发现 Agent 配置中的自定义属性被原样转发给上游 Provider，导致 `invalid_request_error`。影响多个模型（kimi-k3, glm-5.3 等），需要配置净化机制。

### 6. [#37888 Feature: add OPENCODE_DISABLE_INSTALL env var](https://github.com/anomalyco/opencode/issues/37888) 🟡 开放 · 5 评论 · 3 👍
Docker/CI 场景下每次启动都会强制 npm install 插件，希望增加环境变量跳过安装。社区反馈强烈，尤其对自动化部署友好。

### 7. [#37495 SQLite WAL grows unbounded (10–15 GB) on Desktop](https://github.com/anomalyco/opencode/issues/37495) 🟡 开放 · 4 评论
桌面版因多个独立 SQLite 连接导致 WAL 永不被 checkpoint，最终磁盘满。用户必须完全退出才能恢复，属于 **严重资源泄漏**。

### 8. [#50885 NO API KEY — Go subscription unable to generate key](https://github.com/anomalyco/opencode/issues/50885) 🟡 开放 · 2 评论 · 9 👍
订阅了 OpenCode Go 但控制台未显示 API Key，`/connect` 强制要求 Key，而 Key 页面仅支持 Service Account。**认证流程断裂**，影响新用户付费体验。

### 9. [#50916 LSP support gutted from v2?](https://github.com/anomalyco/opencode/issues/50916) 🟡 开放 · 2 评论 · 3 👍
v2 官方文档明确“不再运行 Language Server / LSP diagnostics”，建议用 `v0` 模式代替。开发者担心 LSP 整合度大幅下降，影响代码错误预览。

### 10. [#49948 Shell: bare redirect bypasses the permission check](https://github.com/anomalyco/opencode/issues/49948) 🟡 开放 · 2 评论
`> file` 这种裸重定向被解析为 0 条命令，直接跳过权限检查执行文件截断。是 **安全漏洞**，涉及 `packages/core/src/tool/plugin/shell.ts`。

---

## 重要 PR 进展（10 条）

### 1. [#51743 fix(core): fail oversized MCP stdio frames without closing the transport](https://github.com/anomalyco/opencode/pull/51743) 🔄 开放
修复 MCP 本地 stdio 服务器返回 >~10 MiB 消息时导致整个连接断裂的问题。**避免了因单次超限消息丢失所有能力**，对使用大上下文模型的用户至关重要。

### 2. [#51741 fix(core): fail length finishes that return no content](https://github.com/anomalyco/opencode/pull/51741) 🔄 开放
部分 Provider 以 `finish_reason: "length"` 结束但不返回任何文本/推理/工具调用，导致下游空处理。PR 将其判定为错误而非成功结束。

### 3. [#46912 fix(opencode): wait for stdout writes before exit so piped JSON is not truncated](https://github.com/anomalyco/opencode/pull/46912) 🔄 开放
`export`、`session list --format json` 等命令在 `process.exit()` 前未等待 stdout 写入完成，导致管道输出截断。该修复保证了 JSON 完整输出。

### 4. [#51736 feat(opencode): add --no-open to `opencode web`](https://github.com/anomalyco/opencode/pull/51736) 🔄 开放
为 `opencode web` 增加 `--no-open` 选项，避免在 systemd/容器/无头环境中自动打开浏览器。对应需求 #43636。

### 5. [#51734 docs: add Bee by HEOSSI provider setup](https://github.com/anomalyco/opencode/pull/51734) 🔄 开放
文档贡献，新增 Bee by HEOSSI 作为 OpenAI 兼容 Provider 的配置指南。

### 6. [#50221 chore(nix): update nixpkgs for Bun 1.4](https://github.com/anomalyco/opencode/pull/50221) 🔄 开放
更新 Nix flake.lock 中的 nixpkgs 输入，使 Bun 版本提升至 1.4.2+，解决 node_modules 哈希计算问题。

### 7. [#45759 fix(core): recover Console models after startup failures](https://github.com/anomalyco/opencode/pull/45759) 🟢 已合并
如果启动时 Console DNS 或配置端点不可用，Console 插件会加载空模型列表且不再恢复。该 PR 在服务恢复后重新抓取模型列表，**避免永久性 ModelUnavailableError**。

### 8. [#45754 fix(tui): keep recent models in provider groups](https://github.com/anomalyco/opencode/pull/45754) 🟢 已合并
修复模型选择器中，“最近使用”的模型会从所属 Provider 分组中消失的问题，现在可以同时保留在分组和最近列表中。

### 9. [#45676 feat(CLI): add notification adaptor for termux environment](https://github.com/anomalyco/opencode/pull/45676) 🟢 已合并
为 Termux（Android 终端环境）添加通知适配器，使得通知功能在移动端可用。

### 10. [#45589 fix(merman): connect subgraph edges and preserve labeled paths](https://github.com/anomalyco/opencode/pull/45589) 🟢 已合并
修复 Mermaid 图表渲染中，子图边界连接错误和多行标签导致箭头脱落的问题，提升可视化准确性。

---

## 功能需求趋势

1. **MCP / 外部工具管理**  
   - 全局 stdio MCP 服务器每目录启动一份（#51003）→ 期待进程池化或去重  
   - MCP 超大帧不中断连接（#51743）→ 稳定性优先  
   - Location 关闭时未清理 MCP 进程（#51731）→ 期望完善的资源生命周期管理  

2. **桌面端交互与体验**  
   - 重新打开关闭的标签（#51717）、支持 Mermaid 预览（#51702）、内联代码斜杠误识别（#51723）  
   - 权限模型：Electron 多窗口覆盖 handler（#51748）→ 需要窗口级权限隔离  

3. **配置与环境变量**  
   - `OPENCODE_DISABLE_INSTALL`（#37888）、`OPENCODE_CONFIG_DIR` 行为不一致（#32825）  
   - 配置发现路径混乱（#6156）→ 统一 XDG 规范  

4. **AI 模型与 Provider 改进**  
   - Big Pickle 模型频繁中断（#44447）→ 需要更长推理稳定性  
   - Go 订阅认证流程断裂（#50885, #51388, #51689）→ 简化 Key 生成  
   - LSP 支持降级（#50916）→ 社区希望恢复内置 LSP 或提供替代方案  

5. **数据持久化与性能**  
   - SQLite WAL 无限增长（#37495）→ 需要连接池或 checkpoint 策略  
   - 删除 Session 遗留旧数据库行（#50260）→ 完整清理机制  

---

## 开发者关注点

1. **基础 CLI 交互的稳定性**  
   - 复制粘贴长期异常（#13984）导致日常使用受阻  
   - Tab 键切换 Agent 曾出错（#49133），用户对基础热键信心不足  
   - 未知子命令仅打印帮助无错误提示（#51696）  

2. **权限与安全漏洞**  
   - Shell 裸重定向绕过权限检查（#49948）可被恶意利用  
   - Desktop 多窗口权限覆盖（#51748）可能误拒合法请求  

3. **资源管理问题**  
   - MCP 全局 stdio 进程随目录数线性增长，耗尽内存（#51003）  
   - SQLite WAL 在桌面端涨至 10-15 GB（#37495）  
   - Session 压缩接受不完整摘要（#51747）可能造成历史丢失  

4. **认证与付费体验**  
   - OpenCode Go 订阅用户无法获取 API Key（#50885）  
   - “Insufficient account funds” / Go 徽标消失（#51689）  
   - 用户因策略违规被完全封禁且无申诉途径（#51508）  

5. **迁移适配**  
   - v2 移除 LSP 支持（#50916），现有工作流需调整  
   - Agent 配置额外字段被原样转发（#49027），需 Provider 兼容性校验  

---

> **数据源**：github.com/anomalyco/opencode  
> **统计截止**：2026-09-28 23:59 UTC

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，我已为您整理了基于 `badlogic/pi-mono`（实际数据为 `earendil-works/pi`）的 2026 年 9 月 28 日的 Pi 社区动态日报。

---

# Pi 社区动态日报 | 2026-09-28

## 今日速览

Pi 社区近期活动频繁，聚焦于解决一个关键的长期 Bug：**在长会话中使用推理模型时，上下文压缩（Compaction）功能因包含所有思考文本而持续失败**。同时，社区贡献者提交了一个重量级 PR，新增 **Codemode 和 MCP 支持**，这将是 Pi 在代码编辑与工具集成领域迈出的一大步。此外，关于启动性能、Session 创建延迟和扩展 API 的讨论热度不减。

## 社区热点 Issues

1.  **[#10033] [BUG] 上下文压缩提示包含所有思考文本，导致超出上下文窗口**
    -   **重要性**: 🔴 **高**。此 Bug 直接导致使用 DeepSeek V4.1 等推理模型时，长会话的自动压缩功能永远无法成功，严重影响了长时间编码或对话任务的可用性。社区对此问题反馈积极。
    -   **链接**: [Issue #10033](https://github.com/earendil-works/pi/issues/10033)

2.  **[#7739] [ENHANCEMENT] 设定启动时间预算，目标是与 Jcode 媲美的延迟和内存**
    -   **重要性**: 🔴 **高**。这是社区长期关注的性能核心议题。通过量化指标对标竞品 Jcode，旨在从根本上优化 Pi 的启动体验，反映了开发者对“即开即用”的强烈需求。
    -   **链接**: [Issue #7739](https://github.com/earendil-works/pi/issues/7739)

3.  **[#5581] [BUG] 自定义消息触发代理时绕过了 `before_agent_start` 事件**
    -   **重要性**: 🟡 **中**。此 Bug 破坏了扩展生态系统的核心钩子，导致依赖该事件进行自定义逻辑处理的扩展（如权限检查、日志记录）在特定场景下失效。评论中社区成员已详细分析了多种受影响场景。
    -   **链接**: [Issue #5581](https://github.com/earendil-works/pi/issues/5581)

4.  **[#8810] [BUG] 扩展注册的提供商：新 Session 间歇性忽略默认配置，启动其他提供商的模型**
    -   **重要性**: 🟡 **中**。这对使用多模型、多提供商配置的用户体验影响很大。用户配置的“默认模型”被神秘地忽略，导致工作流中断。
    -   **链接**: [Issue #8810](https://github.com/earendil-works/pi/issues/8810)

5.  **[#10031] [BUG] 使用 ESC 停止思考后，Pi 偶尔卡在“Working...”状态**
    -   **重要性**: 🟡 **中**。这是一个持续了一个多月的 Bug，影响多个机器版本。唯一的恢复方式是强制退出，说明这是一个严重阻塞操作流程的稳定性问题。
    -   **链接**: [Issue #10031](https://github.com/earendil-works/pi/issues/10031)

6.  **[#10105] [BUG] 创建新 Session 会重新加载所有扩展：启动时间从 4s 暴涨至 280s+**
    -   **重要性**: 🟡 **中**。对于拥有大量扩展插件的用户，这是一个灾难性的性能退化。报告者提供了详细的数据，证明问题严重性。
    -   **链接**: [Issue #10105](https://github.com/earendil-works/pi/issues/10105)

7.  **[#9905] [BUG] Anthropic: `thinking.display` 始终发送 "summarized"，CLI 无法更改**
    -   **重要性**: 🟢 **低**。虽然不严重影响功能，但限制了用户对模型思考过程的控制权，对于希望看到完整思考过程的开发者不够友好。
    -   **链接**: [Issue #9905](https://github.com/earendil-works/pi/issues/9905)

8.  **[#9010] [BUG] 上下文压缩导致本地 LLM 内存激增**
    -   **重要性**: 🟡 **中**。与 #10033 同属压缩模块的问题，但影响面是内存。对于在资源受限环境中运行本地模型的用户，这是个关键痛点。
    -   **链接**: [Issue #9010](https://github.com/earendil-works/pi/issues/9010)

9.  **[#9974] [BUG] Pi 错误处理来自 `llama.cpp` 的 Tool Calls，导致重复和损坏调用**
    -   **重要性**: 🟡 **中**。该 Bug 直接破坏了与最流行的本地推理后端之一 `llama.cpp` 的工具调用兼容性，影响大量自托管用户。
    -   **链接**: [Issue #9974](https://github.com/earendil-works/pi/issues/9974)

10. **[#10092] [BUG] 压缩功能的提供商使用数据若缺少 `cost` 字段，会导致恢复会话时 TUI 崩溃**
    -   **重要性**: 🟡 **中**。这是一个显著的稳定性 Bug，将导致用户无法恢复包含特定提供商数据的任何会话，需要紧急修复。
    -   **链接**: [Issue #10092](https://github.com/earendil-works/pi/issues/10092)

## 重要 PR 进展

1.  **[[#10040] feat(coding-agent): Codemode and MCP](https://github.com/earendil-works/pi/pull/10040)**
    -   **状态**: OPEN
    -   **要点**: 这是一个**里程碑式**的 PR，由知名开发者 @mitsuhiko 提交，为 Pi 引入了 **Codemode**（代码模式，可能是一种高度集成的代码交互模式）和 **MCP**（一个通用的协议或框架）支持。尽管未合并，但讨论热度极高，将是 Pi 扩展能力的一次重大飞跃。

2.  **[[#8572] feat(ai): amazon bedrock mantle](https://github.com/earendil-works/pi/pull/8572)**
    -   **状态**: OPEN
    -   **要点**: 该 PR 为 Amazon Bedrock 的新 API 面 “Mantle” 提供支持。由于当前路由错误，导致部分新模型（如 GPT-5）无法使用，此项 PR 将修复与 AWS 庞大模型库的兼容性问题。

3.  **[[#10100] fix(ai): preserve signature-only reasoning details deltas](https://github.com/earendil-works/pi/pull/10100)**
    -   **状态**: CLOSED (Merged)
    -   **要点**: **已合并**。这是一个重要的 Bug 修复。当 Claude 通过 OpenRouter 返回仅有 `signature` 而无 `text` 的推理细节 delta 时，Pi 会错误地将其丢弃。此修复确保了这些签名能被正确保留和处理。

4.  **[[#10099] 第一次Git实验作业：jiaqitang-1](https://github.com/earendil-works/pi/pull/10099)**
    -   **状态**: CLOSED
    -   **要点**: 一个教学相关的 PR。

## 功能需求趋势

-   **性能与冷启动优化**: 社区对 **启动时间**、**内存占用** 和 **Session 创建延迟**（议题 #7739, #10104, #10105）的抱怨日益增加。对标竞品（如 Jcode）并设定量化指标，反映了对“更轻、更快”的强烈渴望。
-   **可扩展性与集成**: 对 **Extension API** 的需求核心化，特别是 **持久化凭证**（#7658）、**运行时代码中调用 LLM 的可见性**（#10095）以及 **对通用协议（如 MCP）的支持**（PR #10040）。社区希望 Pi 能成为一个功能更强大、更能深度集成的平台。
-   **可靠性与稳定性**: **上下文压缩（Compaction）** 模块成为 Bug 重灾区（#10033, #9010, #10092），暴露出在处理长对话和特定提供商时的严重问题。这已成为影响高级用户满意度的关键瓶颈。
-   **提供商兼容性**: 对 **llama.cpp** (#9974) 和 **Amazon Bedrock** (#8572) 等流行商/开源后端的兼容性修复是高频需求。社区希望无论是在本地还是云上，都能有流畅一致的体验。

## 开发者关注点

-   **缓慢且不可预测的 Session 创建**: 多篇报告（#10104, #10105）指出，创建新 Session（或恢复旧 Session）的延迟随着扩展数量线性增加，甚至会在长时间运行的进程中累积内存/成本。这是 CICD 或需要频繁切换任务的开发者最直接的痛点。
-   **上下文压缩机制的信心危机**: 对于依赖推理模型进行长上下文任务的用户来说，压缩功能的 Bug（包含思考文本、内存溢出、导致崩溃）已经严重动摇了他们对这一核心功能的信任。
-   **默认设置的神秘变化**: `defaultProvider`/`defaultModel` 的间歇性失效（#8810）让用户感到困惑，降低了配置系统的可靠性。
-   **对扩展/插件作者的隐形测试**: 错误在扩展的工具渲染中被吞掉（#10073），以及部分 API 钩子被绕过（#5581），让扩展开发者难以调试和保证其插件质量。

---

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

好的，这是为您生成的 2026-09-28 Qwen Code 社区动态日报。

---

# Qwen Code 社区动态日报 | 2026-09-28

## 今日速览
1.  **Managed Agent 架构稳步推进**：围绕多阶段交付的提案，今天社区在会话持久化（Stage D4）、终端恢复栅栏（W0e）以及任务列表服务（Stage H0c）上均有代码合入或新 PR 提出，架构落地进入深水区。
2.  **安全与兼容性修复集中**：一个严重的凭证泄露 Bug（`baseUrl` 携带凭据）和一个由 `Ollama` 兼容性问题导致的功能失效（零参数工具）被提出，社区开发者积极响应。
3.  **CI 与测试基础设施持续加固**：针对死锁、超时和 Runner 环境差异的自动化测试和 CI 修复是另一大焦点，体现出社区对代码稳定性和可重复性的重视。

---

## 社区热点 Issues（10 个）

1.  **Managed Agent 双路径架构提案 ( #12380 )**
    - **重要性**：作为当前所有重大更新的蓝图，该提案定义了新旧 agent 引擎共存的分阶段交付路径，是社区未来发展的核心。
    - **链接**: [QwenLM/qwen-code Issue #12380](https://github.com/QwenLM/qwen-code/issues/12380)

2.  **Legacy 与 Managed 引擎配对集成 ( #12737 )**
    - **重要性**：作为前述架构的 Stage B 具体实现，将允许普通宿主同时运行新旧引擎，是实现平滑过渡的关键一步。
    - **链接**: [QwenLM/qwen-code Issue #12737](https://github.com/QwenLM/qwen-code/issues/12737)

3.  **Aux-model 选择器泄露凭证 ( #12856 )**
    - **重要性**：**严重安全漏洞**。`baseUrl` 中嵌入的用户信息（如 API Key）被明文暴露在所有公共接口，开发者需高度警惕并关注后续修复。
    - **元数据**: 5条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12856](https://github.com/QwenLM/qwen-code/issues/12856)

4.  **Ollama 因零参数工具导致 400 错误 ( #12878 )**
    - **重要性**：影响使用本地 Ollama 推理的用户。不合规的 JSON Schema 输出导致请求失败，是限制本地部署功能的明显痛点。
    - **元数据**: 3条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12878](https://github.com/QwenLM/qwen-code/issues/12878)

5.  **Web Shell 右面板无法关闭 ( #12874 )**
    - **重要性**：高优 UI Bug，直接影响 macOS 用户的操作体验。状态机缺陷导致面板展开后无法收起，可能影响正常的工作流。
    - **元数据**: 4条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12874](https://github.com/QwenLM/qwen-code/issues/12874)

6.  `qwen mcp reconnect` 违反隐私设置上报数据 ( #12844 )
    - **重要性**：**隐私合规 Bug**。即便用户明确禁用用量统计，该命令仍会上传 `session_start` 事件，违背了用户预期和数据隐私原则。
    - **元数据**: 4条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12844](https://github.com/QwenLM/qwen-code/issues/12844)

7.  **Skills 列表在禁用时仍被注入 ( #12835 )**
    - **重要性**：核心行为 Bug。使用 `--exclude-tools skill` 后虽然工具列表会更新，但发送给 LLM 的提示中仍包含技能列表，导致资源浪费和潜在干扰。
    - **元数据**: 5条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12835](https://github.com/QwenLM/qwen-code/issues/12835)

8.  **standalone-update 更新机制死锁 ( #12802 )**
    - **重要性**：影响桌面端用户更新的关键 Bug。旧的 `.deferred` 标记文件会永久性阻止后续更新，是一个隐蔽且影响面大的稳定性问题。
    - **元数据**: 5条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12802](https://github.com/QwenLM/qwen-code/issues/12802)

9.  **Runtime Broker 负精度 BigDecimal 序列化问题 ( #12859 )**
    - **重要性**：数据持久化 Bug。更新 JSON 库后，能写入但无法读回合法的负精度 `BigDecimal` 数据，可能导致数据库中出现无法处理的损坏数据。
    - **元数据**: 4条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12859](https://github.com/QwenLM/qwen-code/issues/12859)

10. **代理配置下 CUA SDK 下载超时 ( #12829 )**
    - **重要性**：企业级用户痛点。在必须使用 HTTP(S) 代理的网络环境中，CUA SDK 的原生依赖无法下载，阻塞了该功能的落地。
    - **元数据**: 4条评论 | P2/Bug
    - **链接**: [QwenLM/qwen-code Issue #12829](https://github.com/QwenLM/qwen-code/issues/12829)

---

## 重要 PR 进展（10 个）

1.  **feat(managed-agent): Session 持久化操作 (Stage D4) ( #12881 )**
    - **功能**：实现了会话的关闭、归档和删除的持久化操作，向 `Managed Agent` 架构的最终形态迈进。
    - **链接**: [QwenLM/qwen-code PR #12881](https://github.com/QwenLM/qwen-code/pull/12881)

2.  **feat(managed-agent): 添加终端恢复栅栏 (W0e) ( #12839 )**
    - **功能**：为 Managed Agent 引擎添加了终端状态 `ABANDONED`，用于处理日志丢失的执行，增强了状态机的健壮性。
    - **链接**: [QwenLM/qwen-code PR #12839](https://github.com/QwenLM/qwen-code/pull/12839)

3.  **feat(managed-agent): 提交任务记录并服务任务列表 (H0c) ( #12855 )**
    - **功能**：管理平面现在可以提交 Stage H 的记录并从中重建任务列表，是任务管理能力在 `Managed Agent` 上的落地。
    - **链接**: [QwenLM/qwen-code PR #12855](https://github.com/QwenLM/qwen-code/pull/12855)

4.  **fix(cli): 清除 aux-model 选择器中的凭证泄露 ( #12862 )**
    - **修复**：**关键安全修复**。清理了因 `baseUrl` 携带凭证而在多个公共表面泄露的安全问题，响应迅速。
    - **链接**: [QwenLM/qwen-code PR #12862](https://github.com/QwenLM/qwen-code/pull/12862)

5.  **fix(edit): 保留未修改行的行尾格式 ( #12799 )**
    - **修复**：解决了因编辑操作导致文件行尾格式不一致的问题，提升了代码编辑的健壮性和信噪比。
    - **链接**: [QwenLM/qwen-code PR #12799](https://github.com/QwenLM/qwen-code/pull/12799)

6.  **perf(core): 并行化扩展加载循环 ( #12107 )**
    - **增强**：通过有界并发来加载扩展，并具备错误传播和重试机制，有望显著提升 IDE 的启动速度。
    - **链接**: [QwenLM/qwen-code PR #12107](https://github.com/QwenLM/qwen-code/pull/12107)

7.  **fix(ci): 回退到固定版本的 yamllint ( #12650 )**
    - **修复**：通过固定工具版本，防止因 Runner 镜像中的工具过时或损坏导致 CI 失败，提升了 CI 的稳定性和可重复性。
    - **链接**: [QwenLM/qwen-code PR #12650](https://github.com/QwenLM/qwen-code/pull/12650)

8.  **fix(core): 清理仅包含符号链接或构建输出的陈旧工作区 ( #12785 )**
    - **修复**：优化了工作区的清理逻辑，避免意外删除仅包含符号链接或构建缓存的工作区，提升了用户体验。
    - **链接**: [QwenLM/qwen-code PR #12785](https://github.com/QwenLM/qwen-code/pull/12785)

9.  **feat(agents): 新增远程运行时支持 ( #12582 )**
    - **功能**：在 A2A 层之上，增加了对远程 Qwen、Codex 和 Claude 运行时的支持，扩展了 Agent 的能力边界。
    - **链接**: [QwenLM/qwen-code PR #12582](https://github.com/QwenLM/qwen-code/pull/12582)

10. **test(managed-agent): 新增 Hosted Broker 回复丢失栅栏测试 ( #12873 )**
    - **测试**：为 Hosted 工具调用场景中的网络故障（回复丢失）增加了精细化的集成测试，确保核心引擎在各种故障下的健壮性。
    - **链接**: [QwenLM/qwen-code PR #12873](https://github.com/QwenLM/qwen-code/pull/12873)

---

## 功能需求趋势

- **Managed Agent 架构落地**：目前社区最热门的方向，涉及会话管理、工具执行、持久化、远端 Agent 集成等多个子任务，标志着 Qwen Code 正在从单体工具向弹性的多Agent 系统演进。
- **多模型与运行时支持**：不仅支持本地模型（Ollama 兼容性修复表明其受欢迎程度），也积极集成云端和外部第三方运行时（如 Codex, Claude），显示出打通多种推理后端的强烈需求。
- **数据安全与隐私**：凭证泄露和隐私设置失效问题的活跃讨论，表明开发者对数据安全和企业级合规有极高的要求。

## 开发者关注点

- **IDE 体验与稳定性**：Webview 崩溃、面板 Toggle 失效等 UI Bug 直接影响了日常使用。增强 IDE 滚动加载、消息引用等功能的需求浮现。
- **隐私与安全威胁**：`baseUrl` 泄露 API Key 的 Bug 是最紧要的开发者痛点，其次是“禁用统计”未生效问题，这两点触及用户信任的底线。
- **代理与网络兼容性**：在复杂网络环境（如企业代理）下的依赖下载失败问题反复出现，是影响用户成功使用门槛的关键。
- **旧状态导致的死锁**：`standalone-update` 等历史遗留问题导致的更新死锁，表明对遗留状态的清理和兼容性处理需要投入更多关注。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，根据您提供的 GitHub 数据，我为您生成了 2026-09-28 的 DeepSeek TUI（Codewhale）社区动态日报。

---

## DeepSeek TUI 社区动态日报 | 2026-09-28

### 📢 今日速览

今日社区动态主要集中在 **v0.10.1 版本的集成冲刺** 上，大量修复性 PR 正在排队等待合并。同时，多个关于 TUI 长期运行后性能退化（如滚动卡顿、实时刷新异常）以及后台进程管理的 Bug 报告引起了开发者关注，反映出稳定性和健壮性是当前版本的重点攻坚方向。

### 🚀 版本发布

过去 24 小时内无新版本发布。

### 🔥 社区热点 Issues（Top 10）

1.  **[#6573] Bug: Multiple TUI Sessions Contend on Subagents Store → CPU Spin-loop**
    - **重要性**：严重。多会话并发导致 CPU 空转，直接影响到多窗口或协作场景的使用体验。
    - **社区反应**：已有 1 条评论，被标记为 `needs-triage`，说明开发者已关注到该问题。
    - **链接**: [Hmbown/Codewhale Issue #6573](https://github.com/Hmbown/Codewhale/Issues/6573)

2.  **[#6651] Bug: the TUI interface cannot refresh in real time**
    - **重要性**：核心体验问题。当终端窗口不在焦点时，TUI 界面无法刷新，这是一个典型的终端应用后台处理问题。
    - **社区反应**：已被标记并收到 1 条评论，表明用户和开发者都认为这是一个需要解决的功能缺失。
    - **链接**: [Hmbown/Codewhale Issue #6651](https://github.com/Hmbown/Codewhale/Issues/6651)

3.  **[#6652] Bug: After running for a long time, TUI scrolling becomes laggy, like jelly**
    - **重要性**：性能退化。应用长时间运行后出现滚动卡顿，是直接影响效率和用户体验的恶性 BUG。
    - **社区反应**：该问题被标记为 `bug`，用户已提供复现步骤（约3-5小时），开发者可能会将其列为高优修复项。
    - **链接**: [Hmbown/Codewhale Issue #6652](https://github.com/Hmbown/Codewhale/Issues/6652)

4.  **[#6650] Bug: The shortcut key for switching thinking intensity is abnormal**
    - **重要性**：交互逻辑 Bug。快捷键 Ctrl+T 在循环切换思考强度时出现响应异常，表明状态机或快捷键绑定逻辑存在缺陷。
    - **社区反应**：已收到反馈，并有一个关联的 PR #6667 试图修复此问题（虽然未能完全复现）。
    - **链接**: [Hmbown/Codewhale Issue #6650](https://github.com/Hmbown/Codewhale/Issues/6650)

5.  **[#6654] Bug: Background shells have no parent-death cleanup**
    - **重要性**：安全与稳定性。后台 shell 进程在 TUI 异常退出后无法被终止，会导致僵尸进程和资源泄漏，这是生产环境中的高危问题。
    - **社区反应**：被标记为 `needs-triage`，问题描述非常详细，提供了技术背景和影响分析。
    - **链接**: [Hmbown/Codewhale Issue #6654](https://github.com/Hmbown/Codewhale/Issues/6654)

6.  **[#6688] Bug: exec takes the prompt only as argv, so anything above ~128 KiB fails with E2BIG**
    - **重要性**：功能限制。`exec` 命令由于依赖命令行参数传递，导致长提示失败，限制了用户脚本的灵活性。
    - **社区反应**：Issue 分析深入，提供了精确的数据（131072字节限制），开发者需要一个更优雅的解决方案（如通过 stdin 传递）。
    - **链接**: [Hmbown/Codewhale Issue #6688](https://github.com/Hmbown/Codewhale/Issues/6688)

7.  **[#6546] Enhancement: To-do list is not manageable (at least not with known menu items)**
    - **重要性**：功能缺失。待办列表缺少清除/管理功能，是一个常见且影响工作流的功能性短板。
    - **社区反应**：用户已尝试多种方法但未找到解决方案，说明该功能的入口或交互设计不够直观。
    - **链接**: [Hmbown/Codewhale Issue #6546](https://github.com/Hmbown/Codewhale/Issues/6546)

8.  **[#6545] Bug: Terminal cursor is still visible though composer is not on Mac**
    - **重要性**：UI 体验。隐藏不活跃输入区域的终端光标，是一个不错的 UX 细节优化。
    - **社区反应**：问题在 Mac 平台上被发现，已被标记，是用户对交互细节有更高要求的体现。
    - **链接**: [Hmbown/Codewhale Issue #6545](https://github.com/Hmbown/Codewhale/Issues/6545)

9.  **[#6616] Enhancement: AICraft — docs_url, credential_url and guidance for the aicraft descriptor**
    - **重要性**：开发者体验。完善 AI 模型提供商描述文件，帮助开发者更好地接入和使用外部模型。
    - **社区反应**：Issue 提供了具体的字段补充建议，是社区对生态完善度有贡献的体现。
    - **链接**: [Hmbown/Codewhale Issue #6616](https://github.com/Hmbown/Codewhale/Issues/6616)

10. **[#6621] Enhancement: Bind fresh HTTP threads to their live snapshot session for file undo**
    - **重要性**：功能修复。HTTP 线程在创建文件快照后无法关联会话，导致撤销功能失效。这是一个高级功能的技术债问题，涉及多个模块的交互。
    - **社区反应**：由项目拥有者提出，说明是开发者自己的重构计划的一部分。
    - **链接**: [Hmbown/Codewhale Issue #6621](https://github.com/Hmbown/Codewhale/Issues/6621)

### 💻 重要 PR 进展（Top 10）

1.  **[#6672] v0.10.1 integration: land the ready PRs together**
    - **重要性**：里程碑。这是一个为 v0.10.1 版本准备的集成 PR，它汇总了多个已准备好的修复，并将一次性合入主分支。这是版本发布前最关键的一步。
    - **链接**: [Hmbown/Codewhale PR #6672](https://github.com/Hmbown/Codewhale/Pulls/6672)

2.  **[#6687] fix(tui): first launch keeps the configured provider instead of adopting local Ollama**
    - **重要性**：Bug 修复。修复了首次启动时 TUI 错误地自动接管本地 Ollama 服务的问题，确保用户的配置得到尊重。
    - **链接**: [Hmbown/Codewhale PR #6687](https://github.com/Hmbown/Codewhale/Pulls/6687)

3.  **[#6686] fix(tui): keep the thinking label in the footer at every effort tier**
    - **重要性**：UI 修复。修复了在窄终端下，思考强度标签被截断的显示问题，优化了不同终端宽度下的布局。
    - **链接**: [Hmbown/Codewhale PR #6686](https://github.com/Hmbown/Codewhale/Pulls/6686)

4.  **[#6667] fix(tui): Ctrl+T moves to a new effective thinking tier on fixed routes**
    - **重要性**：Bug 修复。专门针对 Issue #6650 的快捷键异常问题进行修复，确保固定路由下的快捷键逻辑正确。
    - **链接**: [Hmbown/Codewhale PR #6667](https://github.com/Hmbown/Codewhale/Pulls/6667)

5.  **[#6684] fix(rlm): bound an RLM turn by the child wall-clock budget**
    - **重要性**：稳定性修复。为 RLM 循环添加了超时机制，防止模型或外部进程卡死导致整个 TUI 无法响应。
    - **链接**: [Hmbown/Codewhale PR #6684](https://github.com/Hmbown/Codewhale/Pulls/6684)

6.  **[#6685] fix(tui): read anchors, notes and registry names through one confined open**
    - **重要性**：安全加固。统一了工作区文件的读取方式，增加安全检查（如防止符号链接攻击），提升了对不可信工作区的安全性。
    - **链接**: [Hmbown/Codewhale PR #6685](https://github.com/Hmbown/Codewhale/Pulls/6685)

7.  **[#6663] docs(i18n): complete the Tier-3 developer and internal docs for EPIC #5482**
    - **重要性**：国际化推进。完成了第三梯度的简体中文文档本地化，覆盖了开发者和内部运营文档，降低了非英语开发者的参与门槛。
    - **链接**: [Hmbown/Codewhale PR #6663](https://github.com/Hmbown/Codewhale/Pulls/6663)

8.  **[#6662] docs(i18n): complete the Tier-2 should-have docs for EPIC #5482**
    - **重要性**：国际化推进。完成了第二梯度的简体中文文档本地化，覆盖了大部分用户操作文档，显著改善了中文用户的使用体验。
    - **链接**: [Hmbown/Codewhale PR #6662](https://github.com/Hmbown/Codewhale/Pulls/6662)

9.  **[#6649] runtime_api: end every server-initiated thread stream with a typed stream.end**
    - **重要性**：协议规范。规范了 Runtime API 的流结束行为，用一个明确的事件信号替代了简单的连接关闭，提升了外部集成的可靠性和可编程性。
    - **链接**: [Hmbown/Codewhale PR #6649](https://github.com/Hmbown/Codewhale/Pulls/6649)

10. **[#6680] fix: keep undo, resume and requirements honest; bound stream lines**
    - **重要性**：全面 Bug 修复与健壮性提升。此 PR 包含六个小修复，涉及撤销、会话恢复和流处理等多个核心功能，是代码审计后的清理工作。
    - **链接**: [Hmbown/Codewhale PR #6680](https://github.com/Hmbown/Codewhale/Pulls/6680)

### 🧭 功能需求趋势

从今日的 Issues 中，可以提炼出社区最关注的几个功能方向：

1.  **TUI 性能与稳定性**：长期运行后的性能退化（#6652）、后台进程生命周期管理（#6654）、CPU 空转（#6573）是当前社区反馈的热点，表明用户对工具的健壮性有较高要求。
2.  **国际化与文档**：大量关于简体中文文档翻译的 PR（#6663, #6662）正在推进，表明开发团队正在积极拓展非英语市场，并且社区对此有正向反馈和贡献。
3.  **安全性与信任边界**：对文件读取、后台进程、凭证存储的安全性加固（#6685, #6601, #6681）是近期开发的重点，这也反映了开发者社区对 AI 编程工具安全性的普遍担忧。
4.  **TUI 交互与可用性**：快捷键异常（#6650）、界面刷新（#6651）、待办列表管理（#6546）等，表明在功能逐渐完善后，社区开始关注交互细节和极端场景下的可用性。

### 🧑‍💻 开发者关注点

1.  **痛点：性能退化**。多个 Issue（#6652, #6651）指向 TUI 在长时间运行后的卡顿和响应问题，这是当前最影响核心体验的痛点。
2.  **痛点：后台进程与资源泄漏**。后台 shell（#6654）和 CPU 空转（#6573）问题，暴露出项目在处理并发和后台任务时存在资源管理漏洞。
3.  **高频需求：文件操作与撤销的健壮性**。涉及文件撤销（#6621, #6682）、路径安全性（#6678）的讨论频繁出现，说明开发者对“安全地进行文件操作”有高度关注。
4.  **配置与互操作性**。无需配置时自动接管本地服务的行为（#6687）和 exec 命令的参数限制（#6688），反映出开发者希望工具能与现有工作流和配置习惯更好地兼容。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*