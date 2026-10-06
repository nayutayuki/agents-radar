# AI CLI 工具社区动态日报 2026-10-06

> 生成时间: 2026-10-06 02:29 UTC | 覆盖工具: 9 个

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

# AI CLI 工具生态横向对比分析报告（2026-10-06）

本报告基于 Claude Code、OpenAI Codex、Gemini CLI、GitHub Copilot CLI、OpenCode、Pi、Qwen Code、DeepSeek TUI 八款主流 AI CLI 工具的当日社区动态，提炼行业态势与差异化特征，为技术决策者提供参考。

---

## 1. 生态全景

AI CLI 工具已从“单点代码生成”进入“全流程智能体”阶段，各工具普遍集成了多步骤任务规划、文件编辑、Shell 执行、MCP 协议扩展等能力。然而，快速迭代中暴露出的**稳定性问题**（自动更新导致会话中断、Agent 无限循环、平台兼容性缺陷）成为社区核心痛点，**用户对数据主权、权限透明度和静默操作的反感度急剧上升**。与此同时，**MCP 生态、跨设备协作、企业级安全管理**成为差异化竞争的关键战场，各厂商均在大幅投入代理框架深度与运行时健壮性。

---

## 2. 各工具活跃度对比

| 工具 | 今日版本发布 | 热点 Issues 数（Top 10） | 活跃 PR 数 | 社区情绪关键词 |
|------|-------------|-------------------------|-----------|----------------|
| **Claude Code** | 1（v2.1.290） | 10（含高赞、高评论） | 0 | 数据主权抗议、自动更新抱怨 |
| **OpenAI Codex** | 3（rust-v0.160.1 + 2 alpha） | 10 | 10 | Windows 挫折、Dots 期待 |
| **Gemini CLI** | 1（nightly v0.64.0） | 10 | 10 | Agent 可靠性焦虑 |
| **GitHub Copilot CLI** | 2（v1.0.93-0/1） | 10 | 1 | MCP 兼容性困扰、企业需求 |
| **OpenCode** | 0 | 10 | 10 | 隐私争议、循环崩溃 |
| **Pi** | 2（v1.0.4, v1.0.3） | 10 | 10 | 卡死、成本偏差 |
| **Qwen Code** | 1（v0.25.0） | 10 | 10 | 架构讨论热烈、回归 Bug |
| **DeepSeek TUI** | 0 | 10 | 10 | 安全审计冲刷、贡献者活跃 |

> 注：“热点 Issues 数”取自各日报列出的 Top 10；真实总量高于此数。Kimi Code 当日无活动，未纳入对比。

---

## 3. 共同关注的功能方向

以下需求在至少 4 个工具社区中同时出现，反映行业共性痛点与机遇：

| 共性方向 | 涉及工具 | 具体诉求 |
|----------|----------|----------|
| **Windows 平台一等公民** | Claude Code、Codex、Copilot CLI、OpenCode、Pi、DeepSeek TUI | 进程残留、沙箱兼容、Shell 路径、Computer Use 不可用、LaTeX 失败 |
| **会话状态与数据主权** | Claude Code、Gemini CLI、Copilot CLI、OpenCode、Pi | 自动压缩/更新时静默丢弃上下文、会话恢复丢失工具、30 天自动删除无告知 |
| **MCP 生态稳定性** | Claude Code、Codex、Copilot CLI、Pi | 工具响应解析错误、服务端类型检测错误、OAuth 凭据续期、cowork 模式兼容 |
| **权限管理与安全透明** | Claude Code、Codex、Gemini CLI、OpenCode、DeepSeek TUI | 自动模式误判、bypassPermissions 异常、沙箱逃逸、空 resources 列表导致越权 |
| **Agent 智能与可靠性** | Claude Code、Gemini CLI、Copilot CLI、OpenCode、Qwen Code | 子代理误报成功/无限循环、协作间隙、决策门性能优化、重播取消输入 |
| **模型成本与定价清晰** | Codex、Gemini CLI、Copilot CLI、Pi、Qwen Code | 实际 vs 估算偏差、重复计费、配置项不生效导致 Token 浪费 |

---

## 4. 差异化定位分析

| 工具 | 核心定位 | 目标用户 | 技术路线特点 |
|------|----------|----------|-------------|
| **Claude Code** | 深度插件生态 + 企业权限治理 | 大型团队、合规敏感者 | Mod Hook 系统、自动分类器权限控制、Fable 模型独有 |
| **OpenAI Codex** | 多设备（Dots）无缝协作 | 远程/混合团队、iOS 用户 | 跨设备配对、Remote Control、Browser Use、Rust 引擎 |
| **Gemini CLI** | 高级代理框架研究与定制 | AI 研究员、高级开发者 | 子代理变量、AST 感知、共享内存协作、Licensing 多层级 |
| **GitHub Copilot CLI** | 企业级 MCP 集成 + GitHub 生态 | 企业 DevOps、GitHub 重度用户 | Entra 认证、BYOK、Mission Control 仪表盘、Fit-for-Purpose 稳定性 |
| **OpenCode** | 开源中立、轻量级桌面体验 | 独立开发者、隐私优先者 | Tauri 桌面端、内置 Office 预览、WASM 扩展、私有模型支持 |
| **Pi** | 灵活工具编排 + 成本控制 | 个人开发者、多模型用户 | MCP 通配符过滤、Azure Foundry、durable 长会话、Nix 打包 |
| **Qwen Code** | 中文生态 + 大规模工作空间管理 | 中国企业、移动端用户 | 微信集成、Managed Agent 双路径、Android 客户端、Kubernetes 运行时 |
| **DeepSeek TUI** | 极简终端体验 + Rust 性能 | 终端爱好者、安全研究人员 | 单 crate 百万行重构、静态安全审计、OrcaRouter 集成、contribution-gate 社区机制 |

---

## 5. 社区热度与成熟度

- **最活跃（新 Issue + PR 高频）**：**DeepSeek TUI**（50 个 Issue、42 个 PR 更新）、**OpenCode**（多个高赞争议帖）、**Pi**（持续发布 + 10 个活跃 PR）
- **最成熟但社区压力大**：**Claude Code** 用户基数最大，但自动更新、静默压缩引发的抗议量级最高（单 Issue 超 70 赞）；**Codex** 在 Windows 上问题集中但 PR 修复速度快
- **快速迭代期**：**Gemini CLI** 正在大力重构 Agent 框架（子代理、AST 感知），高频 Nightly 但仍有 P1 Bug 挂起；**Qwen Code** 刚发布 v0.25.0，Managed Agent 双路径成了最热讨论
- **相对温和**：**GitHub Copilot CLI** 社区专注 MCP 与企业集成，情绪以“希望尽快修复”为主，尚未出现大规模抗议

**社区成熟度分布**（基于 PR 审核速度、Issue 回应率、版本发布节奏）：
- 高成熟度：Claude Code、Codex、GitHub Copilot CLI
- 中高：Gemini CLI、Pi、OpenCode
- 成长中：Qwen Code、DeepSeek TUI

---

## 6. 值得关注的趋势信号

1. **“静默”已成公敌**：多个工具因自动更新、闲置压缩、数据删除无通知引发用户强烈反弹。**开发者期望所有破坏性操作主动征得同意**，这将成为 CLI 工具设计的必要原则。
2. **MCP 从概念走向“痛苦”**：MCP 的协议兼容性、OAuth 版本协商、资源原语缺失等问题浮出水面。**MCP 的成熟度将决定 AI CLI 能否真正成为“超级终端”**。
3. **Agent 可信度危机**：子代理误报成功、无限循环、取消输入重播等 Bug 破坏了用户信任。**“可解释性”和“可中断性” 将成为代理框架的核心竞争力**。
4. **企业级安全需求加速**：Claude Code 的权限误判、Copilot CLI 的 Entra 认证、Codex 的沙箱逃逸审计表明，**安全治理正在从“可选”转为“必须”**。
5. **Rust 成为新利器**：Codex（Rust 引擎）、DeepSeek TUI（Rust 重写）、Pi（Rust/WASM）均在安全/性能上进行 Rust 化，**而 Node.js 阵营（Gemini、Copilot）开始面临性能和内存泄漏压力**。
6. **跨平台不再是口号**：Windows 用户的不满在 Claude Code、Codex、Pi 中集中爆发，**能够提供稳定 Windows 体验的工具将获得巨大竞争优势**。
7. **成本透明度受瞩目**：Pi 的 OpenRouter 成本估算偏差、Gemini 的 licensing 层级误判、Qwen 的重复计费——**开发者开始要求“每笔调用可追溯、可预测”**。

---

**总结**：当前 AI CLI 工具生态正处于从“能用”到“好用”的冲刺期。**领先者（Claude Code、Codex）在压测中暴露成熟度短板，追赶者（Pi、DeepSeek TUI、Qwen）则在细分领域快速建立差异化**。对技术决策者而言，关注工具的“静默行为策略”、“Windows 测试覆盖”、“Agent 可中断性” 和 “MCP 原生度” 将比评测功能列表更关键。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

# Claude Code Skills 社区热点报告（数据截止 2026-10-06）

## 1. 热门 Skills 排行

基于 Pull Request 活跃度（评论数、跨 PR/Issue 关联度）与社区关注度，以下为当前最受瞩目的 8 个 Skills（均为 Open 状态）：

| 排名 | PR | 功能描述 | 社区讨论热点 | 当前状态 |
|------|-----|----------|-------------|---------|
| 1 | [#1771 - proofcore-contract-auditor](https://github.com/anthropics/skills/pull/1771) | 智能合约静态分析与 TON 区块链审计证明锚定 | Web3 安全、Solana/Rust 审计、去中心化验证 | Open |
| 2 | [#1703 - md2video-audio](https://github.com/anthropics/skills/pull/1703) | 将 Markdown 文档编译为带真人语音的 MP4 视频 | 零成本专业视频生成、Marp 集成、语音合成质量 | Open |
| 3 | [#822 - AWT (AI Watch Tester)](https://github.com/anthropics/skills/pull/822) | 零代码 AI 驱动端到端测试，结合视觉与浏览器控制 | E2E 自动测试、视觉断言、降低测试门槛 | Open |
| 4 | [#1245 - notion-spec-to-implementation](https://github.com/anthropics/skills/pull/1245) | 将 Notion 产品/技术规格拆解为可执行的实现计划 | 需求分解、任务追踪、验收标准自动化 | Open |
| 5 | [#723 - testing-patterns](https://github.com/anthropics/skills/pull/723) | 覆盖测试哲学、单元测试、React 组件测试、E2E 的全面测试模式 | 测试 Trophy 模型、AAA 模式、最佳实践传递 | Open |
| 6 | [#525 - pyxel](https://github.com/anthropics/skills/pull/525) | 使用 Pyxel 框架进行复古游戏开发（创建、调试、验证） | 头戴运行、帧检查、身体任务测试 | Open |
| 7 | [#1776 - blast-radius](https://github.com/anthropics/skills/pull/1776) | 破坏性/批量操作前检查清单（删除用户、回收权限、批量发信） | 操作风险分类、数据安全、回滚预检 | Open |
| 8 | [#486 - ODT](https://github.com/anthropics/skills/pull/486) | OpenDocument 格式文本创建、模板填充、ODT→HTML 转换 | ISO 标准支持、LibreOffice 兼容、跨平台文档 | Open |

## 2. 社区需求趋势

从 Issues 中提炼社区最关注的新 Skill 方向及关键需求：

- **🔒 安全与信任**（Issues #492 - 43 条评论）：社区技能冒用官方命名空间引发信任边界担忧，**急需命名空间审核机制**。
- **🏢 组织协作**（Issue #228 - 16 条评论）：**组织级技能共享** 需求强烈，当前需手动下载/上传，期望直接分享链接或共享库。
- **🧪 评估可靠性**（Issues #556, #1383, #1390）：**skill-creator 的自动评估系统存在严重缺陷**（0% 触发率、Windows 失败、基准测试布局错误），影响技能质量验证。
- **📏 上下文窗口管理**（Issue #1487）：claude-api 技能注入 ~156k tokens 耗尽上下文，**需要技能裁剪或按需加载**。
- **🛠 特定领域技能提案**：社区积极提案新领域技能，如 **compact-memory 符号表示法**（#1329）、**agent-governance 安全模式**（#412）、**推理质量门控流水线**（#1385），反映对高阶推理与治理的渴望。
- **📄 文档处理增强**：除已有 PR 外，Issues 提及 SharePoint 集成安全（#1175）、文档排版优化（#514 已提案）等，**文档处理仍是核心场景**。

## 3. 高潜力待合并 Skills

以下 PR 社区讨论活跃、实现完整度较高，可能近期落地：

| PR | 理由 | 风险提示 |
|----|------|---------|
| [#1771 proofcore-contract-auditor](https://github.com/anthropics/skills/pull/1771) | 功能描述详尽，依赖外部协议（ProofCore），Web3 领域热度高 | 需审计外部依赖安全性 |
| [#1703 md2video-audio](https://github.com/anthropics/skills/pull/1703) | 零成本、直接利用 Marp 和开源 TTS，实用性极强 | 可能需解决音频生成资源消耗 |
| [#822 AWT](https://github.com/anthropics/skills/pull/822) | 成熟开源工具集成，降低 E2E 测试门槛 | 浏览器控制稳定性需验证 |
| [#1245 notion-spec-to-implementation](https://github.com/anthropics/skills/pull/1245) | 打破需求到实现鸿沟，Notion 生态用户基础大 | 依赖 Notion API 和权限 |
| [#723 testing-patterns](https://github.com/anthropics/skills/pull/723) | 覆盖全面测试栈，社区对测试方法论普遍认同 | 需要与现有测试技能协调 |
| [#1298 skill-creator 修复](https://github.com/anthropics/skills/pull/1298) | 修复核心工具链问题（Windows 兼容、运行时失败），影响所有技能开发者 | 修改涉及多个模块，合并需仔细回测 |
| [#1742 mcp-builder 兼容 MCP 2.0](https://github.com/anthropics/skills/pull/1742) | MCP 协议升级迫使适配，影响所有 MCP 相关技能 | 需确保向后兼容 |

## 4. Skills 生态洞察

> **当前社区最集中的诉求是：在确保技能供应链安全与评估工具可靠性的前提下，加速将文档处理、智能测试、Web3 等实用领域技能整合进官方生态，同时推动组织级技能共享能力的落地。**

开发者不再满足于基础文档生成，而是期待 Claude 能直接操作真实世界的软件系统（Notion、SharePoint、MCP 服务器、智能合约），并主动提供质量门控与安全审计能力。skill-creator 的评估缺陷已成为阻碍社区贡献的瓶颈，亟需官方修复以释放社区创新能量。

---

好的，各位开发者，以下是 2026 年 10 月 6 日的 Claude Code 社区动态日报。

---

# 2026-10-06 Claude Code 社区日报

## 📰 今日速览

1.  **新版本 v2.1.290 发布**：主要更新了插件 (Mod) 的 Hook 功能，为开发者提供了更深度的工具调用追踪能力。
2.  **社区焦点：核心稳定性与权限控制**：今日 Issues 数量激增，社区讨论高度集中在**自动更新导致的数据丢失/会话中断**、**权限系统的误判与行为异常**以及 **Windows 平台兼容性** 三大痛点上。
3.  **Fable 5 模型问题持续发酵**：关于 Fable 5 模型输出异常的问题 (#74558) 持续获得大量关注，社区用户正积极提供复现细节。

## 📦 版本发布

- **v2.1.290**: [查看完整发布说明](https://github.com/anthropics/claude-code/releases/tag/v2.1.290)
  - **主要更新**: 为 Mod 开发者增强了 Hook 功能。
    - `mod` 的 `turn.step` hook 现在会在结果中包含 `serverToolUses` 字段，可获取 Advisor 等 API 自行发起的工具调用信息（ID、名称、输入、起止时间等）。
    - 在 `tool.check` 事件中新增了 `agentId` 字段，使插件 Hook 能够区分并处理子代理 (sub-agent) 的权限检查。

## 🔥 社区热点 Issues (Top 10)

1.  **#15148 - LSP 插件配置不生效** | 💬 24 评论 | 👍 73
    - **摘要**: 从 `marketplace.json` 加载的 LSP 插件（如 typescript-lsp, pyright-lsp）配置被忽略，导致插件虽已安装但无法正常工作。
    - **重要性**: 社区最关注的问题之一，直接影响开发者的日常编码体验。
    - [GitHub Issue #15148](https://github.com/anthropics/claude-code/issues/15148)

2.  **#74558 - Fable 5 间歇性输出异常** | 💬 19 评论 | 👍 16
    - **摘要**: 使用 `claude-fable-5` 模型时，助手生成的文本块会间歇性地被错误替换为“总结思考”块，导致对话看似静默无响应。
    - **重要性**: 影响高级模型用户的信任度和体验。
    - [GitHub Issue #74558](https://github.com/anthropics/claude-code/issues/74558)

3.  **#91763 - Windows MSIX 更新后进程阻塞** | 💬 18 评论 | 👍 1
    - **摘要**: 在 Windows 上，由 Claude Code 启动的 `git fsmonitor--daemon` 进程会继承 AppX 容器作业，并在更新强制关闭后无法被新版本清理，导致重启报错 (0x80070020)。
    - **重要性**: 严重的 Windows 平台 BUG，会完全阻止用户升级后启动应用。
    - [GitHub Issue #91763](https://github.com/anthropics/claude-code/issues/91763)

4.  **#98747 - 闲置压缩静默丢弃上下文** | 💬 14 评论 | 👍 11
    - **摘要**: v2.1.286 版本开始，在提示缓存过期前，闲置会话会被自动压缩，且**无关闭选项和警告**。这对于长期工作会话来说，会丢弃已建立的上下文基础。
    - **重要性**: 社区对用户数据控制权的关切，批评其“静默破坏工作流”。
    - [GitHub Issue #98747](https://github.com/anthropics/claude-code/issues/98747)

5.  **#89690 - Opus Plan Mode 模式行被跳过** | 💬 12 评论 | 👍 0
    - **摘要**: 模型选择器在处理一个 `opusplan` 模式行时，误判其已被内置选项覆盖，导致用户无法在普通会话中选择 Opus Plan Mode。
    - **重要性**: 暴露了模型选择逻辑的缺陷，导致部分模式不可用。
    - [GitHub Issue #89690](https://github.com/anthropics/claude-code/issues/89690)

6.  **#87633 - Windows Cowork 会话中 MCP 文件系统不可用** | 💬 6 评论 | 👍 0
    - **摘要**: 在 MSIX 版本中，本地 `filesystem` MCP 服务器在 Cowork 模式下无法使用，原因是输出 Schema 校验失败。
    - **重要性**: 影响了 Windows 用户在协作场景下的核心文件操作功能。
    - [GitHub Issue #87633](https://github.com/anthropics/claude-code/issues/87633)

7.  **#79944 - MCP 工具响应中文本块被丢弃** | 💬 5 评论 | 👍 4
    - **摘要**: 当 MCP 工具返回既有 `structuredContent`（元数据）又有 `content`（文本正文）时，Claude Code 似乎只处理了结构化块，而静默丢弃了文本块。
    - **重要性**: 这是 MCP 协议交互中的严重 BUG，会错误消费数据。
    - [GitHub Issue #79944](https://github.com/anthropics/claude-code/issues/79944)

8.  **#95364 - 桌面自动更新中断远程控制** | 💬 5 评论 | 👍 3
    - **摘要**: 桌面应用的“静默更新”会在用户离开时自动退出并重启应用，导致所有远程控制 (Remote Control) 会话中断。
    - **重要性**: 与 #99585 等类似，是用户对自动更新机制的集中投诉。
    - [GitHub Issue #95364](https://github.com/anthropics/claude-code/issues/95364)

9.  **#96683 - VS Code 扩展 PreToolUse 回调挂起** | 💬 3 评论 | 👍 0
    - **摘要**: 在 VS Code 扩展的长时 session 中，`saveFileIfNeeded` 回调永远无法 resolve，导致每个读/写操作等待 600 秒后失败。
    - **重要性**: 严重影响 VS Code 用户的使用流。
    - [GitHub Issue #96683](https://github.com/anthropics/claude-code/issues/96683)

10. **#97044 - VS Code 扩展 Webview 导致 OOM 崩溃** | 💬 1 评论 | 👍 1
    - **摘要**: 在 VS Code 扩展中，大型智能体工具调用回合后，聊天 Webview 会触发渲染器进程 OOM 崩溃 (`code: 5`)。
    - **重要性**: 指明扩展的 Webview 存在严重的内存泄漏问题。
    - [GitHub Issue #97044](https://github.com/anthropics/claude-code/issues/97044)

## 📋 重要 PR 进展

无新的 Pull Request 更新。

## 📈 功能需求趋势

从今日的海量 Issues 中，社区最关注的功能方向呈现以下趋势：

1.  **用户控制权与数据主权**：对“静默”行为（静默更新、静默压缩、静默数据删除 #99817）的零容忍，要求明确的 opt-out 选项和用户警告。
2.  **权限与安全治理**：围绕着 `auto-mode` 的分类器错误（误判用户已授权操作 #99834、#99813）和 `bypassPermissions` 模式下的异常行为成为高频需求，社区渴望更可靠、更透明的权限管理。
3.  **MCP 生态稳定性**：MCP 工具响应解析错误 (#79944)、Cowork 模式下兼容性问题、以及浏览器连接等配套工具的稳定性是开发者关注的焦点。
4.  **Windows 平台一等公民化**：大量 Windows 相关 BUG (#91763、#87633、#95009、#99529) 表明，社区对 Claude Code 在 Windows 上获得与 macOS 同等稳定性和功能完整性的需求强烈。
5.  **命令行工具 (CLI) 与 Headless 模式完善**：用户期待 `headless` 模式 (`claude -p`) 性能优化，以及对典型 Git 操作场景的更好支持，例如 `git push`、`merge` 等操作不应被过度拦截。

## 🧑‍💻 开发者关注点

根据社区反馈，以下是开发者认为最亟需解决的问题和高频痛点：

- **自动更新机制**：自动更新在后台终止所有运行中的会话和远程控制，这是目前最让开发者反感的痛点之一。急需一个“不打扰/延迟更新”的选项。
- **权限系统过于“智能”**：`auto mode` 下的分类器过于敏感，频繁阻止开发者明确要求执行的操作（如合并、部署），破坏了信任和效率。
- **LSP 插件不可用**：核心编辑器功能（如 TypeScript 的 IntelliSense）因配置未被加载而失效，这是开发工作中断的首要原因。
- **数据丢失与静默清理**：`idle compaction` 和 30 天自动删除 session 记录的行为，缺乏透明度与用户控制权，引发了强烈的抗议。
- **Windows 平台稳定性**：从进程残留、更新阻塞到 Git Bash 兼容性，Windows 用户的体验问题突出，是社区不满情绪的重要来源。

以上就是本期日报的全部内容。祝各位开发者编码愉快！

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

好的，这是为您生成的 2026-10-06 OpenAI Codex 社区动态日报。

---

# OpenAI Codex 社区动态日报 | 2026-10-06

## 今日速览

今日社区焦点集中在 **Dots** 和 **Windows** 平台的体验改进与问题修复上。最新的 `rust-v0.160.1` 版本修复了远程 MCP 服务器启动时环境变量丢失的问题。此外，多个关于“Dots”会话恢复、跨平台配对以及 Windows 端 Computer Use 的 Bug 报告尤为突出，开发者们正积极反馈和修复。

## 版本发布

- **[rust-v0.160.1]** 发布补丁版本。
  - **Bug 修复:** 修复了在启动配置了远程环境变量的远程 `stdio` MCP 服务器时，未能保留 `SYSTEMROOT`、`TEMP` 和 `TMP` 等关键 Windows 环境变量的问题。现在，Unix 主机也能正确继承 Windows 执行器的启动环境。
  - [查看详情](https://github.com/openai/codex/releases/tag/rust-v0.160.1)

- **[rust-v0.162.0-alpha.16]** 发布内部测试 alpha 版本。
  - [查看详情](https://github.com/openai/codex/releases/tag/rust-v0.162.0-alpha.16)

- **[rust-v0.162.0-alpha.15]** 发布内部测试 alpha 版本。
  - [查看详情](https://github.com/openai/codex/releases/tag/rust-v0.162.0-alpha.15)

## 社区热点 Issues

1.  **[#36040] [Bug] iOS 远程控制只列出近期聊过天的项目**
    - **重要性:** 严重影响 iOS 用户通过远程控制访问所有项目的能力，是回归性问题。拥有 69 条评论，社区关注度极高。
    - [查看详情](https://github.com/openai/codex/issues/36040)

2.  **[#49458] [Bug] Windows 上通过 Dots 启动的本地任务缺少 Computer Use 工具**
    - **重要性:** 核心功能（Computer Use）在 Windows Dots 工作流中失效，直接影响依赖此功能的用户。获 24 个 👍，反馈强烈。
    - [查看详情](https://github.com/openai/codex/issues/49458)

3.  **[#25271] [Bug] Windows 上 Computer Use 无法识别 Chrome 的 URL**
    - **重要性:** 一个持续已久的 Windows 平台问题，导致自动化浏览器操作无法正确获取当前网页地址，影响网页导航和交互。拥有 50 条评论。
    - [查看详情](https://github.com/openai/codex/issues/25271)

4.  **[#49618] [Bug] Windows 与 Android 之间的 Codex Remote 配对陷入循环**
    - **重要性:** 跨平台配对功能完全失败，用户无法在移动设备上控制桌面端。获 16 个 👍，显示该问题影响面广。
    - [查看详情](https://github.com/openai/codex/issues/49618)

5.  **[#40060] [Bug] Windows CLI 中 `Start-Process` 与 URL 共存时触发错误的执行策略检查**
    - **重要性:** CLI 工具的安全策略（execpolicy）存在误报，阻碍了正常的 PowerShell 脚本执行。开发者确认问题在多个版本中仍然存在。
    - [查看详情](https://github.com/openai/codex/issues/40060)

6.  **[#48311] [Bug] Windows 桌面 App 内置 LaTeX 编译器无法找到标准目录**
    - **重要性:** 一个特定但专业的功能（LaTeX 编译）完全失效，影响了特定用户群体的生产。
    - [查看详情](https://github.com/openai/codex/issues/48311)

7.  **[#50800] [Bug] macOS 上 Dots 任务会话恢复后本地线程工具消失**
    - **重要性:** 核心 Dots 功能（本地线程工具）在会话恢复后丢失，破坏了工作流的连续性，严重影响使用体验。
    - [查看详情](https://github.com/openai/codex/issues/50800)

8.  **[#45021] [Bug] Codex CLI 在任务间消息传输中有时会丢失空格**
    - **重要性:** 模型行为上的 Bug，导致生成的文本格式错误。获 5 个 👍，表明这是一个清晰可复现的模型层问题。
    - [查看详情](https://github.com/openai/codex/issues/45021)

9.  **[#49917] [Bug] IDE 扩展聊天频繁重挂载，中断中文输入法**
    - **重要性:** 影响了开发者的核心 IDE 集成体验，特别是对使用中文输入法的用户造成直接干扰。
    - [查看详情](https://github.com/openai/codex/issues/49917)

10. **[#47506] [Bug] macOS 桌面版 Browser Use 误报权限被阻止**
    - **重要性:** 尽管网站访问权限已授权，但功能仍报告错误，干扰了正常的浏览器自动化任务。
    - [查看详情](https://github.com/openai/codex/issues/47506)

## 重要 PR 进展

1.  **[#51230] 稳定会话分页并报告列表失败**
    - **内容:** 修复了因会话活动导致分页游标不稳定，从而无法正确查找重复标签的问题，提升了会话管理的可靠性。
    - [查看详情](https://github.com/openai/codex/pull/51230)

2.  **[#51211] 拒绝 PATH 中可被 Sandbox 写入的 Bubblewrap 可执行文件**
    - **内容:** 安全性增强。阻止了在沙箱外运行位于可写路径下的可执行文件的可能性，防止潜在的安全逃逸。
    - [查看详情](https://github.com/openai/codex/pull/51211)

3.  **[#51221] 分离环境请求与运行时选择**
    - **内容:** 架构优化。引入 `TurnEnvironmentRequest` 和 `TurnEnvironmentSelection`，理清了用户提供的环境输入和系统最终运行时选择的职责。
    - [查看详情](https://github.com/openai/codex/pull/51221)

4.  **[#51203] `apply_patch` 无条件保留原始文件的行尾格式**
    - **内容:** 修复了 `apply_patch` 工具会更改 CRLF 文件行尾的问题，现在它会无条件保留文件的原始行尾格式。
    - [查看详情](https://github.com/openai/codex/pull/51203)

5.  **[#51217] 保留代码审查目标和范围偏差的连续元数据**
    - **内容:** 优化了代码审查流程，现在可以携带 `review_target`（审查目标）通过错误状态，为后续重试或调整提供上下文。
    - [查看详情](https://github.com/openai/codex/pull/51217)

6.  **[#51209] 为 JavaScript 代码模式添加排序工具发现功能**
    - **内容:** 新增 `code_mode_tool_search` 功能，允许在代码模式中使用 BM25 算法搜索和排序可用的工具，提升了工具查找效率。
    - [查看详情](https://github.com/openai/codex/pull/51209)

7.  **[#51207] 将 CLI 的 Daybreak 控制选项置于可选功能开关之后**
    - **内容:** 将 Daybreak 功能（可能涉及高级安全特性）设置为默认关闭的 `features.cli_daybreak` 特性开关，预防未经启用就使用带来的问题。
    - [查看详情](https://github.com/openai/codex/pull/51207)

8.  **[#51206] 记录恢复的子代理的初始化分析数据**
    - **内容:** 修复了恢复 resume 的子代理时，初始化事件未记录分析数据的问题。
    - [查看详情](https://github.com/openai/codex/pull/51206)

9.  **[#51200] 升级 Bazel 至 9.2.0 并刷新模块锁文件**
    - **内容:** 基础设施更新，升级了构建工具 Bazel 版本，并更新了依赖锁文件以确保构建一致性。
    - [查看详情](https://github.com/openai/codex/pull/51200)

10. **[#51186] 防止稳定版本发布指针回退**
    - **内容:** 流程增强。防止将一个较旧的稳定版本发布为“最新”，确保用户始终下载到最新的稳定版本。
    - [查看详情](https://github.com/openai/codex/pull/51186)

## 功能需求趋势

- **Windows 平台兼容性提升:** 大量的 Bug 报告集中在 Windows 系统上，包括 Computer Use 不兼容、LaTeX 编译失败、执行策略误报等。社区强烈期望 Codex 能提供更稳定、更完善的 Windows 桌面端体验。
- **Dots 功能稳定与增强:** “Dots” 功能（跨设备、跨会话工作流）处于高关注度，开发者们正积极寻求解决会话恢复后工具丢失、任务创建失败、以及各种授权/发现过程中的错误，说明该功能虽受期待但尚不够成熟。
- **IDE 扩展集成深度优化:** 开发者对 IDE 扩展的稳定性提出了更高要求，包括解决聊天窗口闪断、与输入法冲突、以及提升其与 Codex 主程序通信的可靠性。
- **安全与沙箱模型改进:** 涉及沙箱逃逸、子代理授权、Daybreak 安全认证等议题的讨论热度不减。社区希望在提供强大功能的同时，有清晰、可配置且不易误报的安全策略。

## 开发者关注点

- **痛点：** Windows 平台的“二等公民”体验最为突出，大量功能（Computer Use， Desktop App）在该平台上存在显著缺陷。跨平台（iOS ↔ Windows/Android ↔ Windows）的配对和远程控制成功率亟待提高。
- **高频需求：** 希望 **Dots 功能更加稳定可靠**，尤其是在会话恢复（resume）后能保留所有上下文和工具。同时，**代码审查（Code Review）流程**（如 PR #51217 所优化）的改进也受到关注。
- **流程抱怨：** 部分用户对 **Daybreak 模式要求物理硬件安全密钥**（Issue #50489）感到困扰，认为应该支持软件密码管理器（Passkeys）作为替代方案，这造成了使用门槛。

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，各位开发者，大家好！今天是 2026 年 10 月 6 日。作为一名专注于 AI 开发工具的技术分析师，我将为大家带来今日的 Gemini CLI 社区动态日报。通过深入分析 GitHub 上的最新数据，我为您梳理了社区中最值得关注的动态、技术讨论和开发趋势。

---

## **2026-10-06 Gemini CLI 社区动态日报**

### **1. 今日速览**

今日社区动态主要集中在代理（Agent）子系统的稳定性上。一方面，新版夜版发布，持续迭代；另一方面，多个高优先级 Bug 得到修复，特别是解决了会话退出时进程挂起和 CPU 占用率 100% 的严重问题。社区在持续关注并推动代理的可靠性、安全性和自主能力，尤其是关于“子代理在达到最大轮次后误报成功”的核心 Bug 正在引发广泛讨论。

---

### **2. 版本发布**

*   **Nightly v0.64.0**：发布了 **`v0.64.0-nightly.20261006.gfb972b2f8`** 版本。该版本为自动化发布的 nightly 构建，包含了一系列来自 `main` 分支的最新代码改动。开发者可通过查看其 [完整 Changelog](https://github.com/google-gemini/gemini-cli/compare/v0.64.0-nightly.20261005.gfb972b2f8...v0.64.0-nightly.20261006.gfb972b2f8) 了解具体更新了哪些提交。

---

### **3. 社区热点 Issues (Top 10)**

1.  **#22323: 子代理达成最大轮次后被误报为“GOAL”成功**
    *   **重要性**: 🔴 P1 Bug。这是当前社区最关注的 Bug 之一。它指出当子代理（如`codebase_investigator`）因达到执行轮次上限（MAX_TURNS）而中断时，系统却将其状态报告为“success”（成功），原因记录为“GOAL”（目标达成）。这掩盖了真实的执行中断，具有高度误导性，直接影响了代理系统的可信度。
    *   **社区反应**: 13 条评论，社区正在热烈讨论如何区分“成功完成”和“因限流而强制中断”的情况。
    *   **链接**: [Issue #22323](https://github.com/google-gemini/gemini-cli/issues/22323)

2.  **#19873: 利用零依赖操作系统沙箱执行模型的原生 Bash 能力**
    *   **重要性**: 🟠 P2 Enhancement。这是一个极具前瞻性的功能提议。其核心思想是利用模型自带的 Bash 操作能力，在一个零依赖的 OS 沙箱中执行命令，从而在不牺牲用户安全的情况下，最大化模型处理复杂任务的能力（如代码探索和文件编辑）。
    *   **社区反应**: 9 条评论，社区对此类“安全+能力”并重的解决方案表现出浓厚兴趣。
    *   **链接**: [Issue #19873](https://github.com/google-gemini/gemini-cli/issues/19873)

3.  **#21409: 通用代理 (Generalist Agent) 在处理任务时永久挂起**
    *   **重要性**: 🔴 P1 Bug。这是一个非常影响用户体验的 Bug。当 CLI 将任务委托给通用代理时，代理会无限期挂起，甚至在执行简单的文件创建等任务时也会发生。用户发现通过指示模型不使用子代理可以临时绕过该问题。
    *   **社区反应**: 8 条评论，社区普遍反馈此问题，且拥有 8 个 👍，说明受此问题影响的用户较多。
    *   **链接**: [Issue #21409](https://github.com/google-gemini/gemini-cli/issues/21409)

4.  **#22745: 评估 AST 感知的文件读取、搜索和映射的影响**
    *   **重要性**: 🟠 P2 EPIC。这是一个关键的研究课题，旨在探索如何利用抽象语法树（AST）来提升代理与代码交互的精度。通过使用 AST 感知的工具，代理可以减少 token 消耗，更精确地读取代码块，从而提升效率。
    *   **社区反应**: 7 条评论，社区对此方向持谨慎乐观态度，期待它能带来质的飞跃。
    *   **链接**: [Issue #22745](https://github.com/google-gemini/gemini-cli/issues/22745)

5.  **#21968: Gemini 不充分使用自定义技能和子代理**
    *   **重要性**: 🟠 P2 Bug。此问题反映了代理系统的“主动性”不足。用户创建了特定的技能（如 Gradle、Git 工具链）和子代理，但 Gemini 在自主决策时很少调用它们，除非用户明确要求。这削弱了自定义技能的价值。
    *   **社区反应**: 7 条评论，社区希望代理能更智能地理解任务与技能间的关联，并主动调用。
    *   **链接**: [Issue #21968](https://github.com/google-gemini/gemini-cli/issues/21968)

6.  **#22267: 浏览器代理 (Browser Agent) 忽略 settings.json 配置**
    *   **重要性**: 🟠 P2 Bug。该 Bug 表明通过 `settings.json` 对浏览器代理进行的配置（如 `maxTurns`）并未生效。尽管 `AgentRegistry` 正确读取了配置，但浏览器代理并未应用，导致用户无法通过配置文件细粒度地控制其行为。
    *   **社区反应**: 4 条评论，表明这是一个明确的配置生效性问题。
    *   **链接**: [Issue #22267](https://github.com/google-gemini/gemini-cli/issues/22267)

7.  **#21983: 浏览器子代理在 Wayland 环境下运行失败**
    *   **重要性**: 🔴 P1 Bug。一个特定于 Linux 发行版的兼容性问题。在使用 Wayland 显示服务器的系统上，浏览器子代理无法正常启动或工作，这对 Linux 用户社区是一个痛点。
    *   **社区反应**: 4 条评论，Wayland 用户正在关注此问题的修复进展。
    *   **链接**: [Issue #21983](https://github.com/google-gemini/gemini-cli/issues/21983)

8.  **#24246: 工具数量超过 128 个时，Gemini CLI 遭遇 400 错误**
    *   **重要性**: 🟠 P2 Bug。这是一个可扩展性问题。当用户启用的工具（包括子代理和技能提供的工具）数量过多（超过 128 个）时，API 请求会失败并返回 400 Bad Request 错误。这表明工具注册或管理机制可能存在上限或性能瓶颈。
    *   **社区反应**: 3 条评论，高级用户和插件开发者对此高度关注。
    *   **链接**: [Issue #24246](https://github.com/google-gemini/gemini-cli/issues/24246)

9.  **#20195: [Agents] - 本地子代理 (Local Subagent) - Sprint 1**
    *   **重要性**: 🟢 P3 Enhancement。这是一个跟踪本地子代理开发第一期任务的 Epic Issue。它标志着社区在持续推动“在用户本地环境运行子代理”这一核心功能的方向。
    *   **社区反应**: 3 条评论，这是该功能规划的聚合点。
    *   **链接**: [Issue #20195](https://github.com/google-gemini/gemini-cli/issues/20195)

10. **#18287: 探索共享内存或并行子代理协作**
    *   **重要性**: 🟢 P3 EPIC。这是一个极具想象力的未来方向，探讨如何实现多个子代理之间的并行协作和共享状态（通过共享内存）。这将显著提升处理复杂、多步骤任务的能力。
    *   **社区反应**: 2 条评论，尽管讨论较少，但其前瞻性对社区愿景有指导意义。
    *   **链接**: [Issue #18287](https://github.com/google-gemini/gemini-cli/issues/18287)

---

### **4. 重要 PR 进展 (Top 10)**

1.  **#29435: [已关闭] 修复 CLI 核心进程在会话退出时挂起的问题**
    *   **内容**: 此 PR 解决了因标准输入（stdin）清理不当导致的进程无法退出的问题。通过正确暂停和取消引用 stdin，确保了程序能干净退出。
    *   **重要性**: 修复了一个严重的进程管理 Bug，属于日常使用中的核心稳定性修复。
    *   **链接**: [PR #29435](https://github.com/google-gemini/gemini-cli/pull/29435)

2.  **#29436: [已关闭] 修复 CLI 因引号内的 `@` 字符导致 CPU 占用率 100% 的问题**
    *   **内容**: 当粘贴或管道内容包含 `@` 符号（如 `import { x } from "@scope/pkg"`）时，CLI 的正则表达式会陷入无限匹配，导致 CPU 占用率飙升。此 PR 通过修复正则表达式来终止这个错误。
    *   **重要性**: 修复了一个严重影响开发的“系统级” Bug。
    *   **链接**: [PR #29436](https://github.com/google-gemini/gemini-cli/issues/29436)

3.  **#29440: [已关闭] 修复 `web-fetch` 工具对非 ASCII 响应内容引用位置错误的问题**
    *   **内容**: 此 PR 修复了 `web-fetch` 工具在解析包含中文、Emoji 等多字节字符的网页时，无法正确标注引用来源的问题。
    *   **重要性**: 提升了 `web-fetch` 在处理国际化内容时的准确性和可靠性。
    *   **链接**: [PR #29440](https://github.com/google-gemini/gemini-cli/pull/29440)

4.  **#29536: [开放] 防御 `grep` 工具的命令行参数注入**
    *   **内容**: 通过在 `grep` 命令中使用 `-e` 分隔符明确分隔搜索模式，防止了恶意构造的搜索词被解释为命令选项（CWE-88），增强了安全性。
    *   **重要性**: 一项重要的安全加固措施，防范潜在的注入攻击风险。
    *   **链接**: [PR #29536](https://github.com/google-gemini/gemini-cli/pull/29536)

5.  **#29532: [开放] 修复 `RetryInfo` 延迟为 0 时，导致配额错误被错误分类的问题**
    *   **内容**: 此 PR 修复了当服务器指示可以立即重试某个限流请求时（延迟为 0），客户端错误地将此判定为“终端配额错误”，从而放弃重试并触发降级流程的问题。
    *   **重要性**: 修复了一个关键的限流重试逻辑，能有效减少因高频调用或正常限流而导致的非必要功能降级。
    *   **链接**: [PR #29532](https://github.com/google-gemini/gemini-cli/pull/29532)

6.  **#29535: [开放] 修复身份验证流程中，未能正确识别非默认的许可层级问题**
    *   **内容**: 当 API 返回多个可用的许可层级但未明确标记默认层级时，CLI 会错误地使用旧有的层级，可能导致有效的个人/免费账户被误认为无有效许可。
    *   **重要性**: 为企业级和多许可场景下的用户解决了登录时的鉴权失败问题。
    *   **链接**: [PR #29535](https://github.com/google-gemini/gemini-cli/pull/29535)

7.  **#29641: [开放] 支持在遥测配置中自定义 OTLP 标头 (Headers)**
    *   **内容**: 此 PR 增强了 Telemetry 模块，允许用户配置自定义的 HTTP 和 gRPC 头部信息，方便与需要认证或自定义元数据的后端（如 Grafana Cloud）集成。
    *   **重要性**: 提升了 CLI 的可观测性集成能力，对 DevOps 和平台团队很有价值。
    *   **链接**: [PR #29641](https://github.com/google-gemini/gemini-cli/pull/29641)

8.  **#29644: [开放] 恢复终端窗口大小变化时 UI 的防抖刷新**
    *   **内容**: 此 PR 恢复了当用户水平调整终端窗口大小时，对 UI 进行防抖（100ms）刷新的功能，以防止在高频调整时出现性能问题或 UI 闪烁。
    *   **重要性**: 优化了用户交互体验，让终端自适应更平滑。
    *   **链接**: [PR #29644](https://github.com/google-gemini/gemini-cli/pull/29644)

9.  **#29612: [开放] 强制用户信息轮次 (User Turn) 的协议不变性**
    *   **内容**: 此 PR 确保发送给 Gemini API 的对话历史记录始终以有效的用户轮次结束，以符合协议要求。它修复了使用 `/rewind` 或中断流等操作后可能出现的上下文不完整问题。
    *   **重要性**: 提升了与 Gemini API 交互的健壮性，避免由于客户端状态管理不当导致的 API 错误。
    *   **链接**: [PR #29612](https://github.com/google-gemini/gemini-cli/pull/29612)

10. **#29490: [开放] 修复使用 `-r` (resume) 参数恢复会话时，工具响应被重复处理的问题**
    *   **内容**: 此 PR 修复了在通过 `-r` 参数恢复一个之前中断的会话时，工具的执行结果被客户端重复记录两次，导致后续上下文混乱的 Bug。
    *   **重要性**: 直接关系到“会话恢复”这一重要功能的正确性，对长时间运行的任务至关重要。
    *   **链接**: [PR #29490](https://github.com/google-gemini/gemini-cli/pull/29490)

---

### **5. 功能需求趋势**

从今日的 Issues 和 PRs 来看，社区最关注的功能方向可以总结为以下几点：

*   **代理框架的深度优化 (Agent Framework Deep Dive)**：
    *   **Smart & Adaptive Agent**: 社区强烈希望代理系统能更智能，例如自动判断何时调用子代理（#21968），并能区分“成功完成”与“达到上限被迫中断”（#22323）。
    *   **Advanced Collaboration**: 探索并行子代理的模式（#18287）和通过共享内存进行协作，以处理更复杂的任务。
    *   **Tooling Precision**: 引入 AST 感知 (

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# 🤖 GitHub Copilot CLI 社区动态日报｜2026-10-06

## 📌 今日速览

昨日发布两个补丁版本（v1.0.93-0 / v1.0.93-1），重点修复了 MCP 服务器凭据静默续期、非沙箱模式下的语言服务器保活等问题。社区方面，macOS 安全更新后 MCP 绑定文件持久化导致 CLI 不可用的问题（#4998）获得最多关注，配合 `/effort` 快速切换推理级别的呼声持续高涨（#3074）。此外，多项 MCP 兼容性及企业配置相关 Issue 活跃度上升。

---

## 🚀 版本发布

### v1.0.93-1（最新）
- **修复与改进**：综合 Bug 修复及稳定性改进。

### v1.0.93-0
- **修复**：
  - 非沙箱模式下，预热语言服务器在 LSP 请求间保持运行
  - 点击截断的紧凑 shell 命令可展开查看完整内容

### v1.0.92（2026-10-05）
- **新增**：
  - 添加 `copilot config` 子命令（列表、读取、设置、删除配置项）
  - 对话前增加 **Ctrl+E** 环境选择器，支持在本地/云端运行间切换
  - Entra 保护的 MCP 服务器可静默续期仅含访问令牌的凭据
  - 旧版 HTTP+SSE 的 MCP 连接停止支持（已移除）

### v1.0.92-5
- **改进**：
  - 支持在选择 Microsoft Entra 账户后明确指定使用哪个账户；`/logout` 命令可登出这些 OAuth 会话
- **修复**：
  - Entra 保护的 MCP 服务器凭据静默续期

---

## 🔥 社区热点 Issues（Top 10）

### 1️⃣ #4998 — macOS 安全更新后 MCP 绑定文件持久化导致 CLI 不可用 ⭐9 💬9
- **摘要**：安装 macOS 安全更新并重启后，所有 Copilot CLI 会话（新开或恢复）均无法处理提示，报错指向 `.mcp-writer.binding` 存留了过期设备 ID。
- **影响**：严重影响 macOS 用户，社区积极讨论临时 Workaround，期望尽快修复。
- **链接**：https://github.com/github/copilot-cli/issues/4998

### 2️⃣ #4775 — Mission Control 仪表盘链接 404：会话路径错误 ⭐2 💬7
- **摘要**：GitHub Mission Control 中“由我创建”的远程会话链接指向 `/copilot/tasks/<uuid>` 导致 404，实际路径为 `/agents/tasks/<uuid>`。
- **影响**：阻断用户通过网页管理 CLI 会话，管理员需手动拼接链接。
- **链接**：https://github.com/github/copilot-cli/issues/4775

### 3️⃣ #3399 — 允许为 BYOK 设置自定义 HTTP(s) 头部 ⭐14 💬7（已关闭）
- **摘要**：请求支持在 `copilot config` 中为自定义 LLM 服务器添加 `X-Tenant-ID` 等自定义请求头，已被官方接受并合并。
- **影响**：满足企业内部多租户、网关认证等场景，14 个 👍 表明广泛需求。
- **链接**：https://github.com/github/copilot-cli/issues/3399

### 4️⃣ #4505 — 恢复会话后残留过期连接 ID 导致所有请求失败 ⭐3 💬6（已关闭）
- **摘要**：恢复已中断的会话后，每个提示都返回“input item ID does not belong to this connection”，`/fork` 也无法恢复。
- **影响**：影响长时间工作流恢复的可靠性，6 条讨论涉及复现步骤。
- **链接**：https://github.com/github/copilot-cli/issues/4505

### 5️⃣ #3074 — 添加 `/effort` 命令快速切换推理级别 ⭐12 💬4（已关闭）
- **摘要**：请求在模型内快速调整推理努力程度（Low / Medium / High），避免多步 `/model` 操作。
- **影响**：12 个点赞反映高频使用场景，已被实现并合入。
- **链接**：https://github.com/github/copilot-cli/issues/3074

### 6️⃣ #4991 — Cloudflare MCP 连接：OAuth 成功后提示“订阅限制” ⭐0 💬3
- **摘要**：Cloudflare 远程 MCP 服务器在完成 OAuth 认证后报错 `Subscription limit reached`，随后 UI 显示需要重新认证。
- **影响**：影响使用 Cloudflare MCP 的用户，疑似服务端配额问题。
- **链接**：https://github.com/github/copilot-cli/issues/4991

### 7️⃣ #3595 — AutoPilot 模式应在需用户确认时暂停等待输入 ⭐2 💬3
- **摘要**：代码审查场景中，AutoPilot 自动选择修复方案，用户希望它能暂停等待手动确认。
- **影响**：增强半自动化工作流的可控性，社区呼吁制定暂停策略。
- **链接**：https://github.com/github/copilot-cli/issues/3595

### 8️⃣ #2790 — Figma Desktop MCP (HTTP) 被错误识别为 SSE 导致连接失败 ⭐2 💬2
- **摘要**：将 Figma MCP 配置为 HTTP 类型，但 CLI 显示为“SSE”，连接时报 `SSE error: Non-200 status code (400)`，相同配置在 Codex CLI 正常。
- **影响**：暴露 MCP 类型检测 bug，阻塞 Figma 集成用户。
- **链接**：https://github.com/github/copilot-cli/issues/2790

### 9️⃣ #1803 — 支持 MCP 的 `resources/read` 原语 ⭐13 💬2
- **摘要**：目前 Copilot CLI 仅支持 MCP Tools，请求支持 `resources/list` 和 `resources/read` 以获取结构化数据。
- **影响**：13 个 👍 显示社区对 MCP 完整能力调用的迫切需求。
- **链接**：https://github.com/github/copilot-cli/issues/1803

### 🔟 #4960 — 企业自定义模型在 `/model` 列表中可见但无法选中 ⭐0 💬2
- **摘要**：企业通过 OpenAI 兼容提供商配置的自定义模型显示在交互式模型选择器中，但无法选中（回车无效）。
- **影响**：阻碍企业使用自有模型，需紧急修复选择逻辑。
- **链接**：https://github.com/github/copilot-cli/issues/4960

---

## 🔧 重要 PR 进展

### #5046 — Initial commit（工作进展中）
- **说明**：该 PR 为初始提交，无具体功能或修复描述。由于当前仅此一个活跃 PR，暂无其他实质性合入更新。
- **链接**：https://github.com/github/copilot-cli/pull/5046

> 提醒：过去 24 小时内 PR 活动稀少，社区关注点集中在 Issue 讨论与版本修复上。

---

## 📊 功能需求趋势

从近期高频 Issue 中提炼出社区最关注的 **5 个功能方向**：

1. **MCP 完整能力支持**
   - 核心诉求：增加 `resources/read` 原语支持（#1803，13👍）；修复 MCP 类型检测（#2790）；支持 OAuth 版本协商（#5039）。
2. **企业级模型与配置管理**
   - 核心诉求：自定义模型可选（#4960）、企业托管 setting 生效（#4959）、BYOK 自定义 HTTP 头部（#3399）。
3. **会话恢复与可靠性增强**
   - 核心诉求：恢复会话时清除过期 ID（#4505）；macOS 更新后绑定文件持久化问题（#4998）；Agent 子模型覆盖（#4462）。
4. **非交互模式与 telemetry 增强**
   - 核心诉求：`copilot -p` 模式下 OTEL 数据缺失（#4169）；OpenTelemetry span 增加交付上下文（#4967）。
5. **交互体验优化**
   - 核心诉求：`/effort` 命令快速切换推理级别（#3074）；AutoPilot 手动确认暂停（#3595）；Windows 主题跟随终端背景而非 OS 主题（#4961）。

---

## 🧑‍💻 开发者关注点

| 痛点/高频需求 | 示例 Issue | 社区情绪 |
|--------------|-----------|----------|
| **MCP 兼容性问题频发** | OAuth 版本被拒、Cloudflare 订阅限制、Figma 类型错误 | 🔴 阻塞，影响多服务集成 |
| **企业模型策略不生效** | 自定义模型无法选择、托管 setting 未应用 | 🟠 导致企业迁移受阻 |
| **macOS 更新后 CLI 异常** | `.mcp-writer.binding` 持久化设备 ID | 🔴 影响大量 Mac 用户 |
| **恢复会话后请求失败** | 残留连接 ID 导致 400 错误 | 🟠 破坏工作流连续性 |
| **双 Esc 快捷键误触发回滚** | 无意图的 Rewind 影响操作效率 | 🟡 希望提供禁用选项 |
| **非交互模式下 telemetry 缺失** | `-p` 模式不发送 OTEL 数据 | 🟡 无法监控自动化任务 |

---

*数据来源：GitHub `github/copilot-cli` 仓库，更新截止 2026-10-06 09:00 UTC。*

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 — 2026-10-06

---

## 今日速览

今日社区焦点集中在**自动压缩无限循环**（#15533，26 条评论）和**隐私政策争议**（#39875，49 👍）两个议题上，前者暴露了核心会话机制的严重缺陷，后者则凸显用户对透明度的高度敏感。此外，多个桌面端崩溃和 Agent 无限循环问题（#49414）集中出现，开发者反馈倾向于修复兼容性与运行时稳定性。

---

## 社区热点 Issues（10 条）

### 1. #15533 — Auto-compaction infinite loop  
- **重要性**：自动压缩在助手自然结束时（`finish === "stop"`）无条件注入伪消息“Continue...”，引发无限循环。社区已展开深度讨论，26 条评论指出现象和可能的修复方向。  
- **社区反应**：👍 12，持续活跃。  
- [查看详情](https://github.com/anomalyco/opencode/issues/15533)

### 2. #39829 — [FEATURE] 支持 DeepSeek V4 Flash 的 Responses API  
- **重要性**：DeepSeek 正式发布 `deepseek-v4-flash-0731` 原生支持 OpenAI Responses API，社区强烈希望集成（30 👍），该 Issue 已被关闭（可能已实现或待合并）。  
- **社区反应**：评论 13，投票积极。  
- [查看详情](https://github.com/anomalyco/opencode/issues/39829)

### 3. #39875 — 恢复隐私措辞并添加遥测说明（Go 订阅用户）  
- **重要性**：近期提交悄然移除了 Go 版本的隐私相关文字和服务归属信息，用户要求透明化并补充遥测保留政策。49 个赞为今日最高，社区反响强烈。  
- **社区反应**：评论 7，情绪偏向不满。  
- [查看详情](https://github.com/anomalyco/opencode/issues/39875)

### 4. #49414 — Agent 循环因“未知” finish reason 永不结束  
- **重要性**：当 Provider 返回未识别的 `FinishReason`（如 `unknown`）时，Agent 步骤循环不断发起新请求，造成无休止的请求风暴。核心运行时缺陷。  
- **社区反应**：评论 4，尚未修复（OPEN）。  
- [查看详情](https://github.com/anomalyco/opencode/issues/49414)

### 5. #40502 — Web 界面不实时刷新对话  
- **重要性**：新消息需手动刷新才能显示，严重影响协作体验。评论 8，用户已给出明确复现步骤。  
- **社区反应**：👍 3，已关闭（可能已修复）。  
- [查看详情](https://github.com/anomalyco/opencode/issues/40502)

### 6. #39991 — Desktop 打开项目文件夹时致命渲染器错误  
- **重要性**：Electron 渲染器崩溃日志显示 `Stale read from <Show>`，macOS 用户反馈频繁闪退。  
- **社区反应**：评论 4，已关闭。  
- [查看详情](https://github.com/anomalyco/opencode/issues/39991)

### 7. #40373 — Desktop 启动时因已删除会话导致崩溃循环  
- **重要性**：持久化标签引用已删除 session → `TypeError: reading 'directory'` → 应用彻底不可用。  
- **社区反应**：评论 4，已关闭。  
- [查看详情](https://github.com/anomalyco/opencode/issues/40373)

### 8. #40653 — `build` 模式下错误地升级了 Flutter  
- **重要性**：用户在 `plan` 模式下要求检查 Flutter 版本，但 Agent 却直接执行了升级操作，反馈误操作风险。  
- **社区反应**：评论 4，中文用户提交。  
- [查看详情](https://github.com/anomalyco/opencode/issues/40653)

### 9. #25689 — Windows Edge 鼠标指针在输入区不可见  
- **重要性**：Windows 11 + Edge 下鼠标光标在提示输入和终端区域消失，影响基本操作。  
- **社区反应**：评论 4，已关闭。  
- [查看详情](https://github.com/anomalyco/opencode/issues/25689)

### 10. #52953 — Snapshot 在 Git <2.45 下失败  
- **重要性**：`git add --all --sparse` 需要 Git 2.45+，旧版本用户无法使用检查点/回滚功能。兼容性问题影响范围广。  
- **社区反应**：评论 3，仍 OPEN。  
- [查看详情](https://github.com/anomalyco/opencode/issues/52953)

---

## 重要 PR 进展（10 条）

### 1. #53305 — 预览 Word、Excel、PPT 文件  
- **功能**：新增 `microsoft-office` 内置扩展，使用 BetterOffice + Rust/WASM 实现只读预览，文件不离机。  
- **状态**：OPEN。  
- [查看详情](https://github.com/anomalyco/opencode/pull/53305)

### 2. #49500 — 添加作曲者工作区底部栏  
- **功能**：在 composer 下方显示当前工作区和 Git 分支，支持快速切换会话目录。  
- **状态**：已关闭（合并）。  
- [查看详情](https://github.com/anomalyco/opencode/pull/49500)

### 3. #49700 — 配对功能移至服务器设置  
- **功能**：将配对配置从客户端迁移到各服务器设置页，支持 HTTP/WSL 服务器的 Tailscale Serve 管理。  
- **状态**：已关闭（合并）。  
- [查看详情](https://github.com/anomalyco/opencode/pull/49700)

### 4. #53267 — 移动端会话导航和抽屉优化  
- **功能**：窄屏幕下增加 `Session`、`Changes`、`More...` 标签，`More...` 展开底部抽屉（文件、终端、使用统计等）。  
- **状态**：OPEN。  
- [查看详情](https://github.com/anomalyco/opencode/pull/53267)

### 5. #51082 — 修复 GitLab Duo 模型的推理变体解析  
- **功能**：将 `gitlab-ai-provider` 加入 `PROTOCOLS`，使其模型的 reasoning 变体能被正确解析。  
- **状态**：已关闭（合并）。  
- [查看详情](https://github.com/anomalyco/opencode/pull/51082)

### 6. #53466 — 暂时停止通过 /models API 同步 ChatGPT 登录  
- **原因**：OpenAI 侧的 bug 导致模型列表不完整，改用硬编码 fallback 列表（含 gpt-6-luna 等新模型）。  
- **状态**：已关闭（合并）。  
- [查看详情](https://github.com/anomalyco/opencode/pull/53466)

### 7. #53467 — 重命名遗留 OpenAI OAuth 方法为 Codex  
- **功能**：清理代码历史，将旧 OAuth 方法更名为 `Codex browser (legacy)` 和 `Codex device code (legacy)`。  
- **状态**：已关闭（合并）。  
- [查看详情](https://github.com/anomalyco/opencode/pull/53467)

### 8. #53464 — 未知模型返回 404 而不是 500  
- **功能**：`SessionPrompt.getModel` 遇到未知模型时返回 404 错误，而非 500 内部错误，改善 API 一致性。  
- **状态**：OPEN。  
- [查看详情](https://github.com/anomalyco/opencode/pull/53464)

### 9. #53422 — 给插件提供宿主 Effect 实例  
- **修复**：避免插件及其依赖解析到独立 `effect` 副本，导致符号与 fiber 实例不共享，解决“找不到模块私有符号”问题。  
- **状态**：OPEN。  
- [查看详情](https://github.com/anomalyco/opencode/pull/53422)

### 10. #51664 — 空 resources 列表不再解析为 allow  
- **修复**：`permission.ts` 中空 `resources` 列表被映射为无效果，导致权限检查意外通过。现在拒绝空列表。  
- **状态**：OPEN。  
- [查看详情](https://github.com/anomalyco/opencode/pull/51664)

---

## 功能需求趋势

- **新模型 / API 适配**：DeepSeek V4 Flash Responses API、Claude Opus 5 extended thinking、DeepSeek 原生搜索。  
- **透明与隐私**：恢复已删除的隐私措辞、添加遥测说明、保留服务归属信息。  
- **搜索与导航**：会话内容全文搜索、会话统计信息。  
- **UI/UX 增强**：语音输入、实时刷新、鼠标光标修复、权限对话框按钮可访问性。  
- **兼容性**：Git 2.45 以下支持、WSL 下 CPU 优化、Windows 11 交互修复。  
- **稳定性**：自动压缩循环防护、Agent finish reason 兜底、桌面启动崩溃恢复。

---

## 

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 — 2026-10-06

## 今日速览
Pi 在昨日发布了 **v1.0.4**，聚焦工具模式匹配与 MCP 开关控制，同时 **v1.0.3** 正式添加 Azure Foundry Chat Completions 支持（已合入主线）。社区高度关注一个长期存在的“Working...”卡死 Bug（#10031），以及 OpenRouter 计费偏差（#9980）和 Windows 下 shell 路径异常（#9361）。MCP 内建集成和 Nix 打包也迎来多项修复。

---

## 版本发布

### v1.0.4  [查看](https://github.com/earendil-works/pi/releases/tag/v1.0.4)
**New Features**
- **工具模式匹配**：`--tools` 和 `--exclude-tools` 支持通配符 `*`，例如 `--tools read,codemode,'mcp__radius__*'` 仅保留指定 MCP 服务器的工具。`--tools` 默认保留 MCP 工具，除非条目以 `mcp__` 开头。
- **`--no-mcp` 标志**：允许在一轮对话中彻底关闭 MCP 集成，避免加载非必需工具。

### v1.0.3 [查看](https://github.com/earendil-works/pi/releases/tag/v1.0.3)
**New Features**
- **Azure Foundry Chat Completions**：将原来的 `azure-openai-responses` 重命名为 `azure` 提供商，并拓展支持 Foundry 的 Chat Completions 部署（如 `azure/deepseek-v4-pro`）。需使用新的配置字段，详见[文档](https://github.com/earendil-works/pi/blob/v1.0.3/packages/coding-agent/…)。

---

## 社区热点 Issues（Top 10）

### 1. #10031 — Pi 在按 ESC 停止思考后卡死在“Working...”  
- **链接**：https://github.com/earendil-works/pi/issues/10031  
- **热度**：20 评论 | 3 👍  
- **重要性**：自 v0.84.0 起反复出现，影响日常使用，唯一退出方法是 Ctrl+C 后 `pi -c` 恢复。多台机器复现，社区广泛反馈，急需修复。

### 2. #9361 — Windows：加载扩展后 settings.shellPath 被忽略，PATH 中意外调用 WSL bash  
- **链接**：https://github.com/earendil-works/pi/issues/9361  
- **热度**：12 评论  
- **重要性**：非确定性问题，当扩展启用时，用户配置的 `shellPath` 失效，转而从 PATH 寻找 bash（可能调用 WSL 的 System32 bash.exe）。Windows 用户体验严重受损。

### 3. #9075 — 自适应模型下压缩摘要（compaction）在 high effort 时总是触发输出上限  
- **链接**：https://github.com/earendil-works/pi/issues/9075  
- **热度**：8 评论 | 4 👍  
- **重要性**：使用 Anthropic 自适应思考模型时，compaction 继承会话的 thinking level，而 thinking tokens 计入 `max_tokens`，导致 high effort 下输出被截断。高级用户频繁遇到。

### 4. #9335 — [已关闭] openai-responses：支持 configuration_update 以保持缓存的推理精度调整  
- **链接**：https://github.com/earendil-works/pi/issues/9335  
- **热度**：7 评论 | 8 👍  
- **重要性**：GPT-6 支持通过 `configuration_update` 修改 reasoning effort 而不失效 prompt cache。社区高度期待该功能，可直接降低高模型使用成本。

### 5. #10074 — Anthropic 工具调用：非 ASCII 编辑参数被静默截断，导致文件损坏  
- **链接**：https://github.com/earendil-works/pi/issues/10074  
- **热度**：7 评论  
- **重要性**：编辑含韩文等非 ASCII 文本时，`\uXXXX` 转义符被错误解析为控制字符，频繁导致文件损坏。严重影响多语言用户。

### 6. #10267 — before_agent_start 贡献的提示文本在无用户提示运行时被丢弃，重复计费  
- **链接**：https://github.com/earendil-works/pi/issues/10267  
- **热度**：6 评论 | 2 👍  
- **重要性**：后台任务、plan 模式继续、重试等场景下，扩展贡献的 system prompt 丢失，导致模型重新生成全部上下文，浪费 token 和费用。

### 7. #9980 — OpenRouter 热门开源模型的计算成本与实际偏差 2–3 倍  
- **链接**：https://github.com/earendil-works/pi/issues/9980  
- **热度**：5 评论 | 1 👍  
- **重要性**：Pi 当前采用最便宜提供商定价计算成本，而 OpenRouter 实际路由常选择更贵的提供商，导致成本估算失真。用户体验和预算管理受影响。

### 8. #10519 — Nix 包将自身 Node 22 置于 PATH 首位，覆盖用户 node  
- **链接**：https://github.com/earendil-works/pi/issues/10519  
- **热度**：2 评论  
- **重要性**：Nix 打包后，bash 工具启动的任何 shell 中 `node` 等命令都指向 Pi 的 Node 22，而非用户预期版本。影响依赖特定 Node 版本的项目。

### 9. #10357 — pi-durable：进度提交通知间隔不可配置  
- **链接**：https://github.com/earendil-works/pi/issues/10357  
- **热度**：2 评论  
- **重要性**：当前硬编码 100ms 间隔提交进度，用户在低频场景下希望增大间隔以减少写入开销，或在高频场景下减小间隔以获得更细粒度更新。

### 10. #10489 — forceSystemPrompt 的投影导致 tool_search 后 prompt cache 未命中  
- **链接**：https://github.com/earendil-works/pi/issues/10489  
- **热度**：2 评论  
- **重要性**：当扩展返回 `systemPrompt` 时，AgentSession 会替换所有系统消息，但投影逻辑将之后添加的工具列表提前注入，破坏 prompt cache。影响缓存效率和速度。

---

## 重要 PR 进展（Top 10）

### 1. #10533 — [进行中] fix(durable): 拒绝形成循环的等待（wait）  
- **链接**：https://github.com/earendil-works/pi/pull/10533  
- **简述**：修复任务等待自身的循环导致挂死的问题。循环等待现在在形成循环的 wait 处立即失败，而非陷入永久阻塞。

### 2. #10530 — [已关闭] 在 system prompt 中为工具搜索函数添加 await  
- **链接**：https://github.com/earendil-works/pi/pull/10530  
- **简述**：codemode 的 tool search 在系统提示中未标记为 async，导致 LLM 经常输出不带 `await` 的调用，返回空结果。添加后显著减少 token 浪费和搜索失败。

### 3. #10410 — [进行中] feat(durable): 暴露 thinking budget 与 WebSocket 超时选项  
- **链接**：https://github.com/earendil-works/pi/pull/10410  
- **简述**：为 durable 的 `ConversationStreamOptions` 添加 `thinkingBudgets` 和 `websocketConnectTimeoutMs`，允许用户精细化控制推理预算和连接超时。

### 4. #10286 — [进行中] fix(ai): 使用 OpenRouter 报告的实际总成本替代目录估算  
- **链接**：https://github.com/earendil-works/pi/pull/10286  
- **简述**：直接从 OpenRouter 返回的 usage 字段读取 `total_cost`，解决当前估算与实际偏差 2-3 倍的问题。社区呼声高。

### 5. #10521 — [进行中] fix(ai): 为 NVIDIA NIM 模型内联 `$ref` 工具 schema  
- **链接**：https://github.com/earendil-works/pi/pull/10521  
- **简述**：NVIDIA NIM 模型返回的 tool schema 包含 `$ref` 引用，Pi 的 `validateToolArguments` 无法解析，导致调用失败。该 PR 在发送前内联所有 `$ref`。

### 6. #10528 — [已关闭] refactor nix package  
- **链接**：https://github.com/earendil-works/pi/pull/10528  
- **简述**：重构 Nix 打包流程，采用 `bun` 构建，对齐发布包结构，并允许覆写插件安装提供商，同时移除 clipboard 透传，提升一致性。

### 7. #10197 — [进行中] feat: 统一包件验证流程  
- **链接**：https://github.com/earendil-works/pi/pull/10197  
- **简述**：通过生成清单支持的、内容寻址的产物集，使本地验证更接近发布产物，消除因工作区解析隐藏的运行时依赖问题。

### 8. #10511 — [进行中] 清理受管安装：仅保留最新版本与正在更新的版本  
- **链接**：https://github.com/earendil-works/pi/pull/10511  
- **简述**：自动删除过时的受管安装，只保留最新发行版和当前正在执行更新的版本，避免磁盘占用膨胀（对应 #10392）。

### 9. #10513 — [进行中] feat(durable): 支持对话上下文中的条目截断（cutoffs）  
- **链接**：https://github.com/earendil-works/pi/pull/10513  
- **简述**：为 durable 的对话上下文增加设置条目的早期截止点功能，避免无限增长，提升长会话稳定性。

### 10. #9714 — [已关闭] feat(ai): 支持 Azure Foundry Chat Completions 部署  
- **链接**：https://github.com/earendil-works/pi/pull/9714  
- **简述**：扩展 Azure 提供商以支持 Chat Completions API，已在 v1.0.3 中发布。内置目录包含 `deepseek-v4-pro` 等模型。

（其他亮点：  
- #10503 — 修复跨块 ANSI 序列分割导致的文本污染  
- #8383 — 修复 gemini-3.7-flash 禁用 thinking 时参数错误  
- #10356 — 修复多行 token 的语法颜色丢失）

---

## 功能需求趋势

从近期 Issues 和 PR 中可以提炼出社区最关注的几个方向：

1. **MCP 集成深化**  
   - 支持 Unix Socket（#10247）、延迟连接（#10253）、工具模式匹配（v1.0.4）等。社区希望 MCP 更灵活、启动更快、资源占用更低。

2. **计费与成本透明度**  
   - 要求使用实际开销（#10286）、修正 OpenRouter 估算（#9980）、修复重复计费（#10267）。用户对成本敏感，期望准确。

3. **扩展与定制能力**  
   - 要求配置 `progress` 提交间隔（#10357）、支持 `thinkingBudgets` 可调（#10410）、无用户提示时保留扩展贡献的 prompt（#10267）。体现出用户希望更精细控制行为。

4. **跨平台稳定性**  
   - Windows shell 路径问题（#9361）、Nix 包 PATH 污染（#10519）、驱动器字母大小写导致的 skill 冲突（#10488）。平台兼容性仍是痛点。

5. **模型兼容性**  
   - 持续跟进各厂商 API 变化：Anthropic 的 OAuth 和 effort level（#10063）、NVIDIA NIM 的 `$ref` schema（#10521）、Gemini 3.7 Flash thinking 配置（#8383）、GPT-6 的 `configuration_update`（#9335）。

---

## 开发者关注点

- **核心 Bug 反复出现**：`Working...` 卡死（#10031）和文件损坏（#10074）持续数周未修复，影响日常开发效率，社区期待尽快热修复。  
- **扩展 API 行为不一致**：`before_agent_start` 贡献的 prompt 在多种场景下被丢弃（#10267），且 `forceSystemPrompt` 导致缓存失效（#10489），新增扩展功能可能需要更严格的测试。  
- **构建与打包改进**：Nix 打包重构（#10528）和统一验证（#10197）获得正面反馈，但 `Managed installs` 清理（#10511）需注意回滚风险。  
- **性能关注**：`emitBoundary` 在长会话中重复构建上下文（#10515）、Codename 的 `__proto__` 键丢失（#10510）等细节问题，均为社区贡献者自行排查并提交修复，体现了测试覆盖的不足。  
- **文档与配置**：Azure Foundry 新配置、tool schema 内联、MCP 模式匹配等新特性均需配套文档更新，部分 PR 已注明文档同步。

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 | 2026-10-06

## 今日速览
- **v0.25.0 正式发布**：包含本地工作空间/智能体协作、TypeScript/Java SDK 更新及桌面端多项修复。  
- **Managed Agent 双路径架构提案 (#12380) 引发热烈讨论**（46 条评论），社区围绕长期会话归属、工具环境解耦等设计方向持续辩论。  
- **多个关键 Bug 被快速修复**：模糊编辑吃掉空行、内存代理配置忽略用户设置、JSONL 读取越界等问题均已提交 PR。

---

## 版本发布

### v0.25.0 三合一发布
- **核心引擎**：新增 `feat(agents): add local workspace-agent collaboration`（PR #11206），实现本地工作空间与智能体的协作能力。  
- **TypeScript SDK v0.1.18**：内嵌 CLI v0.25.0 版本。  
- **Qwen Code Desktop v0.25.0**：修复服务端会话创建失败时的诊断信息保留问题（PR #12331）；Java SDK 新增托管运行时支持。

> 📎 [Release 详情](https://github.com/QwenLM/qwen-code/releases/tag/v0.25.0)

---

## 社区热点 Issues（10 个）

### 1. Managed Agent 双路径架构提案（#12380）
- **标签**：`priority/P2`, `type/feature-request`, `need-discussion`  
- **摘要**：定义分阶段托管智能体架构——保留现有 TypeScript 智能体循环，独立运行模型推理与工具环境供给，赋予会话持久的归属权、工作空间绑定、可恢复的工具执行及稳定的 WebSocket 连接。  
- **社区反应**：46 条评论，讨论热烈；多人对“会话与工作空间生命周期解耦”提出细化建议。  
- [🔗 Issue #12380](https://github.com/QwenLM/qwen-code/issues/12380)

### 2. Kubernetes 工具运行时进度追踪（#13395）
- **标签**：`priority/P2`, `type/feature-request`, `need-discussion`, `daemon`  
- **摘要**：跟踪提案 #12380 下的 Kubernetes 工具运行时实现剩余工作、可移植性及验收门禁。当前实现和审查修复在 PR #13289 中。  
- **社区反应**：14 条评论，开发者关注跨平台部署标准化。  
- [🔗 Issue #13395](https://github.com/QwenLM/qwen-code/issues/13395)

### 3. 后台智能体协作间隙：重复工作、过早完成与不可交互的 send_message（#8097）
- **标签**：`priority/P2`, `type/bug`, `roadmap/multi-agent`  
- **摘要**：当同时运行多个后台探索子智能体并使用 `send_message` 中途通信时，出现三种协调失败：父智能体重复子工作、过早完成、消息未被处理。  
- **社区反应**：10 条评论，用户报告了具体复现步骤，开发团队已确认。  
- [🔗 Issue #8097](https://github.com/QwenLM/qwen-code/issues/8097)

### 4. Android 第二阶段回归测试与导出 UX 跟进（#13111）
- **标签**：`priority/P3`, `scope/web-shell`, `type/enhancement`  
- **摘要**：跟踪 Android 第二阶段审查中留下的非阻塞建议：麦克风、无障碍、下载功能。  
- **社区反应**：7 条评论，移动端用户期待稳定版本。  
- [🔗 Issue #13111](https://github.com/QwenLM/qwen-code/issues/13111)

### 5. `memory.agentMaxTurns` 被用户作用域内存梦忽略（#13458）
- **标签**：`priority/P2`, `type/bug`, `status/ready-for-agent`  
- **摘要**：文档中 `memory.agentMaxTurns` 应用于后台内存智能体的预算，但 `planUserAutoMemoryDreamByAgent` 传入了硬编码常量 8 而非配置值。  
- **社区反应**：5 条评论，用户发现并提交 PR #13462 修复。  
- [🔗 Issue #13458](https://github.com/QwenLM/qwen-code/issues/13458)

### 6. Web Shell 计划批准：将计划渲染为 Markdown 并强制待办结构（#13340）
- **标签**：`priority/P2`, `type/feature-request`, `scope/web-shell`  
- **摘要**：两个改进：退出计划模式时的批准对话框将计划渲染为 Markdown；Plan & Review 强制要求“用户下一步”待办结构。  
- **社区反应**：5 条评论，用户界面体验优化需求较高。  
- [🔗 Issue #13340](https://github.com/QwenLM/qwen-code/issues/13340)

### 7. 已取消的智能体输入可被重播到随后的 Host 运行中（#13463）
- **标签**：`priority/P2`, `type/bug`, `scope/session-management`, `roadmap/multi-agent`  
- **摘要**：Web Shell 验收测试发现：取消托管智能体输入后，其内容可能被错误地注入后续的 Host 模型上下文。  
- **社区反应**：4 条评论，该问题已导致 CI 失败，紧急追踪。  
- [🔗 Issue #13463](https://github.com/QwenLM/qwen-code/issues/13463)

### 8. 加载需要鉴权的插件仓库时卡住（#13447）
- **标签**：`priority/P1`, `type/bug`, `scope/git`, `scope/extensions`  
- **摘要**：当加载需要 HTTP 鉴权的扩展仓库时，弹出 Git 用户名输入框但无法输入且无法跳过，导致每次启动卡死。  
- **社区反应**：4 条评论（含中文），用户强烈要求修复。PR #13459 已通过设置 `GIT_TERMINAL_PROMPT=0` 解决。  
- [🔗 Issue #13447](https://github.com/QwenLM/qwen-code/issues/13447)

### 9. 压缩时服务端上报的上下文天花板被解析后丢弃（#13432）
- **标签**：`priority/P2`, `type/bug`, `scope/token-management`  
- **摘要**：当服务端拒绝请求并返回真实上下文上限时，响应压缩仍按推断窗口计算大小，且缓存共享分支将未压缩的完整历史重新发送给刚拒绝的服务端。  
- **社区反应**：4 条评论，社区对 token 管理精度提出改进建议。  
- [🔗 Issue #13432](https://github.com/QwenLM/qwen-code/issues/13432)

### 10. 微信集成在 v0.25.0 中损坏（#13480）
- **标签**：`priority/P1`, `type/bug`, `category/integration`  
- **摘要**：扫描二维码配置微信时，iOS 微信客户端拒绝连接，提示“请升级 OpenClaw 中的微信接口版本”。此前 #2882 已在 v0.14.1 修复，现回归。  
- **社区反应**：4 条评论，用户升级后遇到阻塞性障碍。  
- [🔗 Issue #13480](https://github.com/QwenLM/qwen-code/issues/13480)

---

## 重要 PR 进展（10 个）

### 1. feat(managed-agent): 连接器和代理健壮性修复（#13330）
- **状态**：OPEN | `autofix/takeover`  
- **摘要**：修复 PR #12692 中 R2 审查的 9 个跟进项（Suggestions + 相邻健壮性问题），包括内存只读存档/删除防护、`computeIfAbsent` 内阻塞 HTTP、CLI 配置重复等。  
- [🔗 PR #13330](https://github.com/QwenLM/qwen-code/pull/13330)

### 2. fix(web-shell): 删除前离开当前独立会话（#12738）
- **状态**：OPEN  
- **摘要**：允许从侧边栏删除空闲的、无工作空间的当前会话。删除前先离开标签页、等待附属释放，再删除原会话。确认弹窗在操作完成前不可关闭。  
- [🔗 PR #12738](https://github.com/QwenLM/qwen-code/pull/12738)

### 3. fix(core): 模糊编辑后保留空白行（#13484）
- **状态**：OPEN | `review/self-reported`  
- **摘要**：确保模糊编辑在请求文本以换行结尾时，保留其后的空白行。边界处理避免错误删除。  
- [🔗 PR #13484](https://github.com/QwenLM/qwen-code/pull/13484)

### 4. fix(core): 用户作用域内存梦尊重 `memory.agentMaxTurns`（#13462）
- **状态**：OPEN  
- **摘要**：将 `memory.agentMaxTurns` 配置传递到用户作用域内存梦中，不再使用硬编码的 `MAX_TURNS`（8）。此修复对应 Issue #13458。  
- [🔗 PR #13462](https://github.com/QwenLM/qwen-code/pull/13462)

### 5. feat(managed-agent): H3 后台 Shell 和 Monitor 运行时（#13265）
- **状态**：OPEN  
- **摘要**：实现 Managed 路径的 H3 切片——后台 Shell 和 Monitor。包含中英双语设计文档，代码部分实现运行时框架。  
- [🔗 PR #13265](https://github.com/QwenLM/qwen-code/pull/13265)

### 6. fix(release): 回收 Docker 磁盘并在沙箱镜像构建前门控数据根目录（#13481）
- **状态**：OPEN  
- **摘要**：强化夜间发布的 Docker 集成管道，防止运行磁盘耗尽：构建沙箱镜像前清理 BuildKit 缓存，并检查数据根目录剩余空间（24h 阈值）。  
- [🔗 PR #13481](https://github.com/QwenLM/qwen-code/pull/13481)

### 7. feat(managed-agent): 使本地 Runtime 工具结果持久化（M5b）（#13291）
- **状态**：OPEN | `autofix/takeover`  
- **摘要**：实现 Managed 引擎的 M5b 切片——本地托管会话的每个 Runtime 工具结果在记录会话的同一权威中持久化。调用离开主机前发布最终参数和工具定义。  
- [🔗 PR #13291](https://github.com/QwenLM/qwen-code/pull/13291)

### 8. feat(managed-agent): 添加 W1c 离线工作空间迁移（#13260）
- **状态**：OPEN  
- **摘要**：为受信任的单台 Linux 主机添加私有离线工作空间搬迁能力。操作员退役所有旧放置、验证 W1b 捕获、有条件地在更高挂载版本上提升目标。  
- [🔗 PR #13260](https://github.com/QwenLM/qwen-code/pull/13260)

### 9. feat(web-shell): 在二级工作空间中支持侧边任务（#13468）
- **状态**：OPEN  
- **摘要**：Web Shell 的 `/btw side` 现在可以在父工作空间的信任二级工作空间中创建独立的侧边任务对话——包括父级正在响应时。创建遵循会话运行时，保留现有独立会话排除和生命周期清理。  
- [🔗 PR #13468](https://github.com/QwenLM/qwen-code/pull/13468)

### 10. fix(ci): 在运行 linter 前验证二进制文件存在（#13489）
- **状态**：CLOSED（已合并）  
- **摘要**：在 `scripts/lint.js` 中显式检查 `yamllint`、`shellcheck`、`actionlint` 是否在 PATH 上，未找到时失败关闭。优先合并以确保 CI 稳定性。  
- [🔗 PR #13489](https://github.com/QwenLM/qwen-code/pull/13489)

---

## 功能需求趋势

从本期 Issues 和 PRs 中可提炼出以下最受关注的社区功能方向：

| 趋势 | 说明 | 代表性 Issue/PR |
|------|------|------------------|
| **Managed Agent 架构** | 双路径（TypeScript 引擎 + 独立运行环境）、持久化会话、Kubernetes 运行时、工具结果持久化 | #12380, #13395, #13291 |
| **工作空间管理** | 多工作空间支持、离线迁移、侧边任务 | #13260, #13468, #12738 |
| **多智能体协调** | 后台智能体协作修复、通信机制、取消重播防护 | #8097, #13463 |
| **桌面/Web Shell 体验** | 计划渲染为 Markdown、取消回退到编辑器、二级工作空间侧边任务 | #13340, #13488, #13468 |
| **内存与 Token 管理** | 硬编码配置问题、Token 格式化显示、上限解析修复 | #13458, #13432, #13473 |
| **平台集成** | Android 第二阶段、微信接口回归 | #13111, #13480 |
| **CI/基础设施健壮性** | Docker 磁盘回收、linter 检查、构建门禁 | #13481, #13489 |
| **安全与权限** | 扩展仓库鉴权卡死、重复注册凭证 | #13447, #13122 |

---

## 开发者关注点

- **配置不生效**：`memory.agentMaxTurns` 硬编码问题引发广泛讨论，表明用户期待配置项能被严格执行。  
- **后台智能体状态混乱**：取消的输入可被重播、协作存在重复工作，这些 Bug 影响了自动化工作流的可靠性。  
- **扩展仓库鉴权阻塞**：Git 用户名输入框无法操作导致启动卡死，属于阻塞性障碍，已通过设置 `GIT_TERMINAL_PROMPT=0` 快速修复。  
- **Token/上下文压缩逻辑**：服务端上报的上下文上限被忽略，导致反复发送超长历史，性能浪费明显。  
- **新版回归问题**：v0.25.0 的微信集成损坏、模糊编辑吃掉空白行等，说明发布前需要更全面的集成测试。  
- **跨平台稳定性**：Windows 下 Vim 模式剪贴板损坏（#13197）、Android 第二阶段待办项不断累积，开发者期待平台一致性。  

> 以上日报基于 GitHub QwenLM/qwen-code 仓库 2026-10-06 前 24 小时数据生成，涵盖 Releaes、Issues 与 PRs。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

# DeepSeek TUI（Codewhale）社区动态日报 | 2026-10-06

## 今日速览

项目 `Codewhale`（DeepSeek TUI 核心底座）昨日无版本发布，但社区活跃度极高：共计50个 Issue 和42个 PR 在过去24小时内有更新。开发者集中关注 **Windows 平台稳定性修复**（#6846、#6871）、**静态安全审计批量提交**（#6553-#6561 共9个审计类 Issue）以及 **OrcaRouter OAuth 2.0 集成**（#6867）。同时，两款来自贡献者的 `contribution-gate` PR 正在完善工具超时与取消传播逻辑（#6849、#6850），值得跟进。

---

## 社区热点 Issues（10个）

### 1. 🔥 EPIC-005: CodeWhale TUI Crate 分解（总纲）
- **链接**: [#5316](https://github.com/Hmbown/Codewhale/issues/5316)
- **评论**: 31 | **状态**: OPEN
- **为什么重要**: 这是整个 TUI 模块解构的史诗级议题，涵盖了超过12个子任务（FEAT-027、FEAT-020 等），直接影响单 crate 大小（近百万行）的维护性。社区持续关注分解进展，昨天有 draft PR #6832 提出通过共享 `Shapes` 重构命令路由。
- **社区反应**: 虽然原作者 aboimpinto 开启了该议题，但近两日更新主要来自 Hmbown 本人的提交和评论。

---

### 2. 🐛 Windows 下 `node.exe` 被杀导致进程无清理（#6827）
- **链接**: [#6827](https://github.com/Hmbown/Codewhale/issues/6827)
- **评论**: 2 | **状态**: CLOSED
- **为什么重要**: 用户在 Windows 上通过 npm 启动时，`node.exe` 被杀死会导致 `codewhale.exe` 异常终止，且无法触发任何清理流程。已关闭但引发了关联 Issue #6871（见下方）。
- **社区反应**: 报告人 jayanthvee 详细描述了复现步骤，开发者迅速响应关闭。

---

### 3. 🐛 Windows 安全门拒绝 `Stop-Process` 变量形式（#6871）
- **链接**: [#6871](https://github.com/Hmbown/Codewhale/issues/6871)
- **评论**: 0 | **状态**: OPEN
- **为什么重要**: 修复 #6827 时添加的安全门过于严格，导致用户无法用 `$pid` 变量停止进程，只能强制使用管道形式。这是 Windows 用户体验的关键细节。
- **社区反应**: 新提交的 bug，暂无评论，但属于高优先级修复。

---

### 4. 🚨 静态安全审计：同步/阻塞工作运行在异步 Tokio 运行时上（#6553）
- **链接**: [#6553](https://github.com/Hmbown/Codewhale/issues/6553)
- **评论**: 0 | **状态**: OPEN
- **为什么重要**: 审计发现文件系统、子进程、git 等操作未使用 `tokio::task::spawn_blocking`，会在异步运行时上阻塞线程，可能导致整体性能下降甚至死锁。这是系统性风险。
- **社区反应**: 作者 7jrxt42BxFZo4iAnN4CX 一次性提交了9个审计类 Issue（#6553-#6561），开发者需要逐个评估修复优先级。

---

### 5. 🚨 审计：无上限读取/响应缓冲区（#6554）
- **链接**: [#6554](https://github.com/Hmbown/Codewhale/issues/6554)
- **评论**: 0 | **状态**: OPEN
- **为什么重要**: 网络响应、子进程管道等未设置字节上限，攻击者可能通过超大数据包耗尽内存。
- **社区反应**: 同属审计批次，社区期望维护方尽快将这些标记为 `bug` 并给出修复时间线。

---

### 6. 🚨 审计：崩溃不原子化写入（#6555）
- **链接**: [#6555](https://github.com/Hmbown/Codewhale/issues/6555)
- **评论**: 0 | **状态**: OPEN
- **为什么重要**: 状态文件、会话记录等写入时没有使用 `fsync` 和临时文件重命名，系统崩溃可能导致数据损坏。
- **社区反应**: 目前无讨论，但数据完整性是核心要求。

---

### 7. 🔍 审计：副作用重复执行无幂等键（#6556）
- **链接**: [#6556](https://github.com/Hmbown/Codewhale/issues/6556)
- **评论**: 0 | **状态**: OPEN
- **为什么重要**: 工具调用、MCP 调用、HTTP 请求等重试时可能重复执行，缺乏 idempotency key，可能导致重复付费或数据重复。
- **社区反应**: 这是 agent 系统的典型风险，社区期待引入 `Idempotency-Key` 头。

---

### 8. 🔍 TUI 分解阻塞：`crate::config` 单个模块 72.7 万行（#6034）
- **链接**: [#6034](https://github.com/Hmbown/Codewhale/issues/6034)
- **评论**: 2 | **状态**: OPEN
- **为什么重要**: 尽管已经移除了 localization、palette 等模块，但 `config.rs` 仍占 118/128 个模块，占 72.7 万行。这是 TUI 分解的最大阻碍。
- **社区反应**: Hmbown 澄清了实际进度，表示下一步将拆解 config 模块。

---

### 9. 📌 决策门：为常规 Agent 决策增加可选快速通道（#6603）
- **链接**: [#6603](https://github.com/Hmbown/Codewhale/issues/6603)
- **评论**: 1 | **状态**: OPEN
- **为什么重要**: 每次用户消息都唤醒大模型判断意图，对于简单消息浪费时间和费用。提案增加一个“决策门”快速过滤。
- **社区反应**: 评论者 Andrea-Bruno 是提出者，社区认为这是一个有价值的性能优化方向。

---

### 10. 📌 指令预算可配置与可见性（#6526）
- **链接**: [#6526](https://github.com/Hmbown/Codewhale/issues/6526)
- **评论**: 0 | **状态**: OPEN
- **为什么重要**: 当前项目指令（standing instruction）有硬编码上限（48KB），且无法告知用户指令被截断。提案增加可配置 knob 和可见通知。
- **社区反应**: 由 7jrxt42BxFZo4iAnN4CX 提出，属于用户可见性的改进。

---

## 重要 PR 进展（10个）

### 1. 🚀 0.10.1 跟进：Windows LPAC、图片拖放、Shell 交接、错误标签等（#6846）
- **链接**: [#6846](https://github.com/Hmbown/Codewhale/pull/6846)
- **状态**: OPEN | **作者**: Hmbown
- **摘要**: 此 PR 是 0.10.1 的补丁跟进，包含 Windows LPAC 路径验证、截图/图片拖放路径处理、Shell 安全交接、错误标签优化以及插件诊断工具。昨日已合并了上游 #6815 但 Windows 测试仍有失败，此分支正在逐个验证。
- **社区关注**: 核心维护者亲自推进，是近期最活跃的 PR。

---

### 2. 🛠️ 修复：解决快照模型 ID 与自定义提供商探测（#6870）
- **链接**: [#6870](https://github.com/Hmbown/Codewhale/pull/6870)
- **状态**: CLOSED（已合并） | **作者**: SparkofSpike
- **摘要**: 修复了自定义 OpenAI 兼容网关下 DeepSeek V4 快照模型 ID 误判为 128K unknown 形状的问题，同时改进了自定义提供商榜单探测。
- **社区关注**: 已合并，对使用私有网关的用户有直接帮助。

---

### 3. 📃 文档：公开 Agent 等待超时边界（#6850）
- **链接**: [#6850](https://github.com/Hmbown/Codewhale/pull/6850)
- **状态**: OPEN（contribution-gate） | **作者**: asto18089
- **摘要**: `agent(action="wait")` 的 schema 和描述未提及默认30秒、最大120秒的超时限制。贡献者补全了文档并添加了 `timed_out` 字段说明。
- **社区关注**: 贡献者 asto18089 正在通过贡献门，此 PR 是工具文档正确性的重要修补。

---

### 4. 🐛 修复：通过 SSE 兼容流传递工具结果取消事件（#6849）
- **链接**: [#6849](https://github.com/Hmbown/Codewhale/pull/6849)
- **状态**: OPEN（contribution-gate） | **作者**: asto18089
- **摘要**: 当外部审批被中断时，`approval.decided` 事件现在正确携带 `decision: "deny"` 和 `cancelled: true`，区分“无人应答”和“主动拒绝”。此前 SSE 兼容流只传递了 `timeout` 而丢弃了取消信息。
- **社区关注**: 对依赖 SSE 的第三方集成非常关键。

---

### 5. 🌍 修复：搜索函数使用配置的区域设置（#6860）
- **链接**: [#6860](https://github.com/Hmbown/Codewhale/pull/6860)
- **状态**: OPEN（contribution-gate） | **作者**: asto18089
- **摘要**: 无密钥的 Bing 和 DuckDuckGo 搜索之前忽略了 `locale` 配置，导致区域相关性错误。现添加 `mkt`、`setlang` 参数，Firecrawl/Serply/SearXNG 则早已支持。
- **社区关注**: 对多语言用户是重要修复。

---

### 6. 🔑 功能：OrcaRouter OAuth 2.0 + PKCE 连接与实时聊天目录（#6867）
- **链接**: [#6867](https://github.com/Hmbown/Codewhale/pull/6867)
- **状态**: OPEN（contribution-gate） | **作者**: hodeswildsmith455-boop
- **摘要**: 为 OrcaRouter 提供商增加 OAuth 2.0 + PKCE 登录入口，支持浏览器登录获取令牌，同时暴露实时聊天目录，与已有的 API Key 方式互补。
- **社区关注**: OrcaRouter 是新兴的模型路由提供商，此 PR 使 Codewhale 用户无需手动获取 API Key 即可接入。

---

### 7. 🚀 0.10.1 集成：引擎收敛、TypeScript 模块审查与 Ratatui UX（#6815）
- **链接**: [#6815](https://github.com/Hmbown/Codewhale/pull/6815)
- **状态**: CLOSED（已合并） | **作者**: Hmbown
- **摘要**: 将 Rust 引擎（执行、身份、权限、事件、会话、存储、计费）与 ACP、子 Agent、递归 RLM 统一到同一 turn 路径，并审查了 TypeScript 模块与 Ratatui 交互。作为 0.10.1 的基础，昨天已合并。
- **社区关注**: 主干合并，影响后续所有开发。

---

### 8. 📡 功能：提供技能体接口便于客户端激活（#6869）
- **链接**: [#6869](https://github.com/Hmbown/Codewhale/pull/6869)
- **状态**: OPEN | **作者**: gaord
- **摘要**: 新增 `GET /v1/skills/{name}` 端点，返回 `SKILL.md` 内容以及路由元数据（源、调用方式、别名、层级、启用状态）。此前 TUI 中已支持直接运行，但 REST API 无法获取技能内容。
- **社区关注**: 对构建外部 UI 或自动化的开发者是必要功能。

---

### 9. 🐛 修复：保护 app-server 代理请求超时（#6855）
- **链接**: [#6855](https://github.com/Hmbown/Codewhale/pull/6855)
- **状态**: CLOSED（已合并） | **作者**: asto18089
- **摘要**: `/v1/chat/completions` 代理未设置超时，提供者若连接后持续无响应或慢速流会卡死处理线程。现通过共享 builder 添加超时限制。
- **社区关注**: 属于安全/稳定性修复，已合并。

---

### 10. 🐛 修复：限制 Pandoc 转换子进程并清理 orphan（#6854）
- **链接**: [#6854](https://github.com/Hmbown/Codewhale/pull/6854)
- **状态**: CLOSED（已合并） | **作者**: asto18089
- **摘要**: `pandoc_convert` 工具原先在异步路径中同步阻塞调用 `Command::output()`，不仅占用 executor 线程，且取消后进程悬空。现改为 spawn_blocking 并设置超时，取消时自动 kill。
- **社区关注**: 贡献者 asto18089 昨日完成了多个同类修复（#6855、#6856、#6863 等），显示了强劲的贡献能力。

---

## 功能需求趋势

从最近24小时的 Issue 和 PR 中，社区最关注以下功能方向：

1. **Windows 平台稳定性**：多个 Issue 和 PR 聚焦 Windows 下的进程管理、安全门、路径处理等（#6846、#6871、#6827），表明 Windows 用户群体正在扩大且体验需提升。
2. **安全与可靠性审计**：9个审计类 Issue 集体出现（#6553-#6561），覆盖阻塞、无上限输入、原子写入、幂等性、竞态、子进程清理、错误黑洞、DoS 控制等。说明社区安全意识增强，项目需要系统性加固。
3. **Agent 决策效率优化**：决策门提案（#6603）和指令预算配置（#6526）体现了开发者对降低成本、提高响应速度的需求。
4. **更多 Provider 支持**：OrcaRouter 的 OAuth 集成（#6867）和模型 ID 修复（#6870）显示社区希望 Codewhale 对接更多源头。
5. **API 能力扩展**：技能体端点（#6869）和 SSE 取消传播（#6849）表明外部集成需求强烈，REST API 的完整性需要跟上 TUI 的功能。

## 开发者关注点

- **Windows 下进程生命周期管理**：多个问题指出 `node.exe` 被杀、`Stop-Process` 安全门误拦、子进程 orphan 清理不全，Windows 用户期望更安全的进程管理机制。
- **大代码库可维护性**：TUI crate 高达百万行，分解进度缓慢（#6034、#5316）。社区期待更激进的重构，但维护者需要平衡功能交付与代码健康。
- **超时与取消机制的缺失**：多个 PR 都在弥补超时和取消的漏洞（#6849、#6854、#6855、#6863），开发者希望这些基础能力能纳入体系化设计，而非逐个补丁。
- **高频依赖更新**：dependabot 提交了超过6个依赖更新 PR（#6809-#6813、#6821-#6823），部分涉及安全修复。项目应制定依赖更新策略，避免积压过多 bot PR。

---

> 以上日报基于 GitHub 仓库 `Hmbown/Codewhale` 的公开数据整理，部分链接指向偶数字符路径（如 `codewhale-hq/Codewhale`），实际同属于该项目。建议关注下一次版本发布（预计 0.10.1 近期推出）以获取以上修复。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*