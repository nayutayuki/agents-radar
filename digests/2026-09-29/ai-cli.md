# AI CLI 工具社区动态日报 2026-09-29

> 生成时间: 2026-09-29 02:17 UTC | 覆盖工具: 9 个

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

好的，作为一名专注于AI开发工具生态的资深技术分析师，我将基于您提供的2026-09-29各主流AI CLI工具的社区动态，为您生成一份横向对比分析报告。

---

### AI CLI 工具生态横向对比分析报告 (2026-09-29)

#### 1. 生态全景

当前，AI CLI 工具生态正经历从“功能狂欢”向“精耕细作”的关键转型。一方面，工具在**Agent能力**（如多Agent协作、自主规划）和**生态集成**（如MCP协议、插件系统）上持续深化；另一方面，**稳定性、安全性和开发者体验**成为了社区最尖锐的痛点，几乎每个工具都面临因更新引入回归（Regression）而导致的用户反弹。模型提供商之间的竞争加剧（如OpenAI、Gemini、Qwen），正促使工具开发者调整策略，例如优先交付托管服务而非本地部署。总体而言，行业共识正在形成：**一个“能用”的AI代理工具容易构建，但一个“可靠、可预测、健壮”的工具才是真正的护城河。**

#### 2. 各工具活跃度对比

| 工具名称 | 今日Issues数(热点) | 今日PR/合并数 | 版本发布情况 | 社区活跃度评估 |
| :--- | :--- | :--- | :--- | :--- |
| **OpenAI Codex** | 10 (Top 10) | 10+ | **v0.158.0 正式版**，多个Alpha版 | **极高**，用户基数大，Bug反馈与功能需求并存 |
| **Gemini CLI** | 10 (Top 10) | 10 (Top 10) | **v0.63.0-nightly** | **很高**，聚焦Agent核心问题及安全修复 |
| **OpenCode** | 10 (Top 10) | 10+ | **v1.18.33 热修复版** | **很高**，功能迭代与稳定性修复并行 |
| **Pi** | 10 (Top 10) | 10 (Top 10) | 无新版本 | **高**，社区关注长期存在的死锁与性能退化问题 |
| **Qwen Code** | 10 (Top 10) | 10 (Top 10) | 无新版本 | **高**，深度讨论架构演进（Managed Agent）与核心议题 |
| **CodeWhale (关联DeepSeek TUI)** | 10 (Top 10) | 10 (Top 10) | **v0.10.1 补丁版** | **中高**，聚焦网络容错与UI渲染，模块化重构进行中 |
| **Claude Code** | (摘要失败) | (摘要失败) | 数据缺失 | 数据缺失 |
| **GitHub Copilot CLI** | (摘要失败) | (摘要失败) | 数据缺失 | 数据缺失，从历史趋势看通常较为稳定 |
| **Kimi Code CLI** | 0 | 0 | 无活动 | **低** |

**分析：** OpenAI Codex以庞大的用户基数带来了最高的问题反馈量。Gemini CLI、OpenCode、Pi和Qwen Code活跃度接近，均处于深度迭代与问题修复的关键阶段。CodeWhale作为初入视野的工具，表现出了不错的社区参与度。Kimi Code则处于相对静默期。

#### 3. 共同关注的功能方向

1.  **Agent行为的可控性与可预测性**
    - **具体诉求：**
        - **OpenAI Codex/ Qwen Code:** 要求能够**精细控制Agent的思考、确认和执行流程**。如Codex的自动对话摘要(Recap)开关、Qwen Code的AUTO模式用户审批Bug。
        - **Gemini CLI/ Pi:** 要求解决**Agent无限挂起（Hang）** 和**任务永久死锁**的问题，这是对“可预测性”最底层的需求。
        - **OpenCode:** 实现**Human-in-the-Loop (HITL)** 机制，通过不同级别来平衡自动化和安全控制。

2.  **网络与连接的健壮性 (Resilience)**
    - **具体诉求：**
        - **OpenAI Codex/ CodeWhale:** 焦点在 **SSE (Server-Sent Events) 连接** 的中断恢复与重试机制。CodeWhale甚至要求将重试预算和超时变为可配置项。
        - **OpenCode:** 要求对**网络错误提供“快速失败”** 而非长时间等待，并给出清晰错误提示。
        - **Qwen Code:** 聚焦于 **Remote-SSH场景下的会话稳定性**，EPIPE崩溃是P1级Bug。

3.  **跨平台稳定性与兼容性**
    - **具体诉求：**
        - **OpenAI Codex:** Windows平台成为重灾区，出现大量**白屏、终端窗口弹出、App-Server被意外杀死**等问题，是“回归Bug”的集中体现。
        - **OpenCode/ Pi:** macOS和Windows平台的**剪贴板/文件路径粘贴**行为不一致是普遍痛点。
        - **CodeWhale:** 报告了**特定终端（如iTerm2、Konsole）下的UI渲染异常**，包括背景色和光标显示问题。

#### 4. 差异化定位分析

- **OpenAI Codex (富操作系统):** 野心最大，将自己定位为AI时代的“操作系统”，深度集成Desktop、CLI、TUI等多种界面和MCP生态。但其臃肿的架构导致Windows平台稳定性危机四伏，社区反馈像是“在用爱发电测试Beta版操作系统”。
- **Gemini CLI (Agent内省探索者):** 高度聚焦于**Agent自身的推理与行为逻辑**，如子Agent协作（sub-agent）、自主规划（plan mode）。其安全问题也是“Agent权限”层面的问题，技术路线更偏向于深度探索Agent能力上限。
- **OpenCode (可扩展性平台):** 通过**插件系统、模块化路由（如opencode-zen）和强大的配置能力**，强调开发者可以自由“搭积木”。其“Human-in-the-Loop”理念也突显出对操作安全性的重视。更像一个AI开发者的“Workbench”。
- **Pi (推理模型先锋与性能守护者):** 社区明显更关注**推理模型（如DeepSeek）的上下文管理**和**性能退化（Session创建延迟）**。定位偏向于服务于高阶、长时间运行的复杂任务，但对系统稳定性要求极高。
- **Qwen Code (架构前瞻者):** 在**多智能体（Multi-Agent）和持久化记忆**架构上走得最远（如Managed Agent双路径架构、结构化Auto Memory）。社区讨论偏“设计层面”，有很强的前瞻性，但用户体量可能相对较小。
- **CodeWhale (轻量级优化者):** 聚焦于**TUI的“手感”和“净室”体验**。它解决的不是Agent能力问题，而是响应延迟、文件截断、UI渲染等最优级问题。定位像是开发者的“指尖伙伴”，追求极致的响应速度和可靠性。

#### 5. 社区热度与成熟度

- **极活跃/成熟 (Crowd-sourced QA):** **OpenAI Codex** 拥有最庞大的用户群和生态，但这也意味着它成为了最大的“问题曝光池”。其社区更像一个大规模Beta测试现场，用户反馈尖锐，团队修复响应迅速但Bug回滚频繁。
- **高活跃/快速迭代期:** **Gemini CLI、OpenCode、Qwen Code** 处于快速增加功能和打磨稳定性的并行期。社区讨论既有深度技术议题，也有高频的日常使用Bug。它们正在从“新锐工具”向“可靠工具”过渡。
- **中活跃/深度玩家俱乐部:** **Pi** 和 **CodeWhale** 的社区更倾向于由深度用户和贡献者驱动。讨论的问题技术含量高（如上下文死锁、WASM故障），但用户门槛高，属于“硬核玩家”聚集地。

#### 6. 值得关注的趋势信号

1.  **Agent “未成熟”已成共识:** 多个工具共同出现的**Agent无限挂起、死锁、错误报告“成功”** 等严重问题，揭示了当前Agent技术在复杂、开放环境下的脆弱性。这对开发者的警示是：**现阶段不应完全信任AI Agent的自主决策**，必须设计好“熔断、降级、人工确认”的防护机制。

2.  **“确定性”压倒一切:** 从社区反馈看，**复制粘贴失效**（Codex, Pi）、**UI白屏**（Codex, OpenCode）、**文件截断**（CodeWhale）等“低级”的可用性问题，其负面情绪远超Agent能力不足。这清晰地表明：**对于AI开发工具，90%的靠谱性比120%的智能更重要。** 开发者需要一个“确定能工作”的起点，而不是一个有潜力但随时会崩的“神奇工具”。

3.  **从“能做事”到“不出错”：**
    - **安全左移:** 从Qwen Code的MCP服务器规则绕过，到Gemini CLI的日志泄露凭证，再到OpenCode的调试信息脱敏，反映出安全正从运行时考虑前置到开发与配置阶段。
    - **Token/成本治理:** Qwen Code的“非对话上下文Token治理”和OpenCode的“提示词缓存不明确”，体现了社区开始精细化管控LLM的隐性成本。
    - **可观测性需求:** 开发者希望Agent能提供更清晰的内部状态（如思考过程、错误原因、资源使用）。Pi的会话创建延迟分析和CodeWhale的健康检查摘要反映了这种趋势。

**对技术决策者与开发者的建议：**

- **追求稳定者优先考虑OpenCode**，其热修复和HITL机制显示出对开发体验的优先保障。
- **探索前沿Agent能力可关注Qwen Code**，其架构设计具有前瞻性，但要做好应对不稳定性的准备。
- **使用Windows平台需谨慎选择OpenAI Codex**，其平台兼容性在当前阶段是重大风险。
- **所有人在生产环境中使用前，必须经过严格的压力测试和稳定性验证**，特别是要检查网络故障、长对话场景下的Agent挂起和资源泄漏问题。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，作为专注于 Claude Code 生态的技术分析师，以下是基于您提供的数据（截至 2026-09-29）生成的社区热点分析报告。

---

### Claude Code Skills 社区热点报告（截至 2026-09-29）

#### 1. 热门 Skills 排行

根据 PR 的评论活跃度、功能重要性及影响范围，以下是社区关注度最高的 5 个 Skills：

- **#1298 fix(skill-creator)**: 解决 `skill-creator` 核心评估引擎的断层问题。关键修复包括：隔离触发评估、处理 Windows 兼容性及运行时失败。这是社区开发者最关注的“技能制作技能”，其稳定性直接影响生态扩展。
    - **状态**: open
    - **链接**: [PR #1298](https://github.com/anthropics/skills/pull/1298)

- **#1742 fix(mcp-builder)**: 紧急适配 MCP 协议版本升级。修复了 `MCP >= 2.0.0` 带来的导入路径变更和自定义 Header 配置问题。这直接影响到所有依赖 MCP 服务的技能，是基础设施层面的关键补丁。
    - **状态**: open
    - **链接**: [PR #1742](https://github.com/anthropics/skills/pull/1742)

- **#1792 fix(docx)**: 提升 DOCX 技能处理 LibreOffice 转换时的健壮性。将超时从静默成功改为显式报错，并增加了对输出文件内容的校验，确保修订标记被正确清除。这体现了社区对技能输出质量的高要求。
    - **状态**: open
    - **链接**: [PR #1792](https://github.com/anthropics/skills/pull/1792)

- **#1771 feat(proofcore-contract-auditor)**: 一个面向 Web3 开发者的专业技能，通过对 Solidity/Rust 智能合约进行静态分析，并将审计证明锚定到 TON 区块链。代表了社区对新领域（加密资产、去中心化）的技能探索。
    - **状态**: open
    - **链接**: [PR #1771](https://github.com/anthropics/skills/pull/1771)

- **#1703 feat(md2video-audio)**: 一个极具创新性的“零成本”技能，将 Markdown 文档通过 Marp 转为幻灯片，并配上仿真人声旁白，最终输出为 MP4 视频。它探索了 AI 从文本生成多媒体内容的边界。
    - **状态**: open
    - **链接**: [PR #1703](https://github.com/anthropics/skills/pull/1703)

- **#1245 feat(notion-spec-to-implementation)**: 一个强大的工作流自动化技能。它能够读取 Notion 中的产品/技术规格文档，并将其自动分解为具体的、可执行的编码任务清单。它直击开发者从“需求”到“代码”的痛点。
    - **状态**: open
    - **链接**: [PR #1245](https://github.com/anthropics/skills/pull/1245)

#### 2. 社区需求趋势

从社区 Issues 反馈来看，当前用户的关注焦点已经从“有什么新技能”转向了“技能生态如何更健壮、更安全、更易用”：

- **安全与信任危机**：Issue #492 以 43 条评论高居榜首，核心矛盾在于社区技能通过官方命名空间分发，可能导致用户混淆信任边界，引发权限滥用风险。这说明社区对**安全审计和信任机制**有强烈需求。
- **工作流自动化与集成**：Issue #228（组织级分享）、#228（功能需求）和 #1329（紧凑记忆符号表示法）表明，用户渴望 Skills 能更好地融入现有工作流，实现**团队协作、状态管理和流程自动化**。
- **质量控制与可靠性**：Issue #556（评估工具触发率为0）和 #1383（技能创建器基准测试失败）反复强调了**工具链本身的可靠性**是当前的最大短板。用户要求核心工具（如 skill-creator）能稳定工作。
- **资源效率（Token 优化）**：Issue #1487 指出 `claude-api` 技能一次性注入 ~156k tokens，导致上下文窗口耗尽。这表明随着技能复杂度提升，**Token 预算管理**成为关键挑战，社区期待更轻量、更智能的技能设计。

#### 3. 高潜力待合并 Skills

以下 PR 社区讨论活跃、功能实用，有较大可能在近期被官方合并或吸收：

- **[#1771 ProofCore Contract Auditor](https://github.com/anthropics/skills/pull/1771)**：为 Web3 开发者提供了一个开箱即用的安全审计工具，概念新颖且填补了生态空白。
- **[#1245 Notion Spec to Implementation](https://github.com/anthropics/skills/pull/1245)**：实现“需求即代码”的自动化工作流，是提升开发效率的典型代表，用户期待度高。
- **[#525 Pyxel Skill](https://github.com/anthropics/skills/pull/525)**：一个完整的复古游戏开发技能，覆盖从创建到调试的全流程，对于教育和技术演示场景有巨大价值。
- **[#486 ODT Skill](https://github.com/anthropics/skills/pull/486)**：支持 OpenDocument 格式，是处理办公文档的重要补充，对于企业和政府用户至关重要。
- **[#822 AWT (AI Watch Tester)](https://github.com/anthropics/skills/pull/822)**：赋予 Claude 视觉和浏览器控制能力以执行端到端测试，代表了 AI 驱动的测试自动化方向。
- **[#723 Testing Patterns](https://github.com/anthropics/skills/pull/723)**：一个全面的测试策略指南，覆盖单元测试、组件测试到测试哲学，是提升代码质量的基础设施。

#### 4. Skills 生态洞察

一句话总结：当前社区最集中的诉求是提升核心基建（skill-creator, mcp-builder）的**稳定性和跨平台兼容性**，并解决由社区技能激增引发的**安全信任和资源效率**问题。

---

⚠️ 摘要生成失败。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报 — 2026-09-29

> 数据来源：GitHub [openai/codex](https://github.com/openai/codex)，筛选过去 24 小时（UTC 2026-09-28 ~ 2026-09-29）内的 Releases、Issues 与 Pull Requests。

---

## 1. 今日速览

- **正式版 v0.158.0 发布**：新增全屏 TUI 文本选择/粘贴控制、OAuth MCP 服务器支持，转录保留 Markdown 格式。
- **Windows 稳定性问题集中爆发**：数十个 Issue 报告更新后出现白屏、终端窗口反复弹出、第二条消息挂起等回归，社区反馈强烈。
- **复制粘贴功能回归成为焦点**：Linux TUI 下的右击/中键粘贴在 0.157.0 之后多处断裂，多个 Issue 累计获得 20+ 评论，团队已通过 X11 粘贴支持 PR 紧急修复。

---

## 2. 版本发布

### [rust-v0.158.0 (正式版)](https://github.com/openai/codex/releases/tag/rust-v0.158.0)
- **新增特性**：
  - 全屏 TUI 中可配置 **复制时选择 (copy-on-select)** 与 **右键粘贴**，转录内容保留 Markdown 格式。
  - 支持通过 `codex mcp add --oauth-client` 连接需要预注册 OAuth 客户端密钥的 MCP 服务器。
- **影响**：改善 TUI 用户交互体验，拓展 MCP 集成范围。

### Alpha 版本（无特性详情）
- `rust-v0.160.0-alpha.3`、`rust-v0.160.0-alpha.2`、`rust-v0.159.0-alpha.13`、`rust-v0.159.0-alpha.12` 陆续发布，均为内部迭代版本，未公开变更日志。

---

## 3. 社区热点 Issues（Top 10）

| # | Issue | 评论数 | 👍 | 要点 |
|---|-------|--------|----|------|
| 1 | [#48208](https://github.com/openai/codex/issues/48208) `[CLOSED]` Linux Desktop UI 更新后加载卡死 | 27 | 17 | Ubuntu 24.04 升级后 UI 停留在加载转圈，`thread_hydration` 超时，app-server 正常。**回归 bug，影响广泛。** |
| 2 | [#26984](https://github.com/openai/codex/issues/26984) `MCP stdio` 泄漏管道 fd 与孤儿进程 → EMFILE | 26 | 7 | 长期存在的严重资源泄漏，导致“Too many open files”。社区反复报告，需架构级修复。 |
| 3 | [#41622](https://github.com/openai/codex/issues/41622) **需求**：添加禁用自动对话摘要的设置 | 23 | 89 | 高赞功能请求。用户希望 `config.toml` 提供开关关闭自动 recap，提升清晰度。 |
| 4 | [#48059](https://github.com/openai/codex/issues/48059) Windows CLI 终端窗口频繁弹出 | 22 | 44 | 0.157.0 后，正常使用中反复弹出新终端窗口，**严重影响工作流**。 |
| 5 | [#47855](https://github.com/openai/codex/issues/47855) Windows Desktop 第二条消息无限挂起 | 16 | 0 | 首条消息正常，第二条永远处于 loading，app-server 无响应。**会话中断。** |
| 6 | [#40231](https://github.com/openai/codex/issues/40231) Windows app-server 因 `STATUS_CONTROL_C_EXIT` 被杀死 | 16 | 0 | 执行 shell 命令几分钟后被终止，回归在 26.818 版本后重现。 |
| 7 | [#47511](https://github.com/openai/codex/issues/47511) Git 提交/推送按钮消失 | 15 | 36 | Desktop 更新后版本控制按钮不可见，**影响 CI/CD 流程**。 |
| 8 | [#48313](https://github.com/openai/codex/issues/48313) Windows 更新后打开永久空白白屏 | 15 | 1 | `26.924.1866.0` 版本导致整个客户端区域白屏，无任何日志输出。 |
| 9 | [#48277](https://github.com/openai/codex/issues/48277) CLI 更新后约 20 个终端窗口持续弹出 | 15 | 3 | 用户手动关闭时仍有新窗口弹出，**疑似创建进程失控**。 |
| 10 | [#48125](https://github.com/openai/codex/issues/48125) Linux TUI 复制文本功能失效 | 15 | 17 | Ubuntu 24.04 通过 SSH 使用时无法复制，**情绪激动**，反映对开发者极不友好。 |

---

## 4. 重要 PR 进展（Top 10）

所有 PR 均由 `copyberry[bot]` 在 24 小时内合并关闭。

| # | PR | 功能 / 修复 |
|---|-----|-------------|
| 1 | [#49130](https://github.com/openai/codex/pull/49130) | **内容过滤指导迁移至共享重试处理器**：将 content-filter 指导逻辑从 sampling 循环移到 `handle_response_stream_error`，统一重试决策。 |
| 2 | [#49127](https://github.com/openai/codex/pull/49127) | **去重云与执行者技能清单**：避免重复占用技能描述空间，让模型能看到更多独特技能。 |
| 3 | [#49119](https://github.com/openai/codex/pull/49119) | **为内容过滤重试添加恢复指导**：当回复被 content_filter 阻断时，在重试请求中附带解释并提供允许的替代方案。 |
| 4 | [#49112](https://github.com/openai/codex/pull/49112) | **X11 主选择与中键粘贴支持**：修复 Linux TUI 复制粘贴回归，支持 `PRIMARY` 剪贴板及中键粘贴。 |
| 5 | [#49106](https://github.com/openai/codex/pull/49106) | **代理命令中心历史分页**：从仅显示最近 10 条变为可展开“显示更多”，支持加载/重试状态。 |
| 6 | [#49105](https://github.com/openai/codex/pull/49105) | **重连后恢复未发送的 TUI 输入**：断线重连时自动恢复排队但未确认的输入消息，减少用户重输。 |
| 7 | [#49100](https://github.com/openai/codex/pull/49100) | **复用 HTTP 连接池用于远程插件请求**：避免每次调用新建 client pool，提升性能。 |
| 8 | [#49099](https://github.com/openai/codex/pull/49099) | **缓存解析的插件清单**：通过 `PluginStore` 共享 manifest 缓存，减少重复解析和警告。 |
| 9 | [#49098](https://github.com/openai/codex/pull/49098) | **解决 Windows sandbox PowerShell 回退**：远程控制器无法解析沙箱兼容的 PowerShell 路径，在 exec-server 端自动回退。 |
| 10 | [#49097](https://github.com/openai/codex/pull/49097) | **通知生命周期扩展关于压缩用量限制**：手动或压缩时若达到 usage limit，触发 turn error 生命周期通知。 |

---

## 5. 功能需求趋势

从当日 Issue 与 PR 可提炼出社区最关注的功能方向：

- **TUI 复制/粘贴行为可配置**：多平台（Linux/Wayland/Konsole/mate-terminal）下快捷键和粘贴行为需统一且可定制（如 `copy-on-select`、中键粘贴、右键粘贴）。
- **Windows 稳定性与 UI 修复**：高频崩溃、白屏、终端窗口弹出、app-server 被意外杀死等回归问题亟待解决。
- **自动对话摘要（Recap）控制**：大量用户要求提供 `config.toml` 开关，避免干扰。
- **MCP 连接可靠性**：stdio 泄漏 fd、OAuth 支持、资源清理等是长期痛点。
- **Git 集成**：Desktop 中 git commit/push 按钮回归，以及版本控制可视化需求。
- **模型行为优化**：GPT-6 模型误报“Invalid prompt safety error”导致正常请求被拒，要求更精准的安全过滤。

---

## 6. 开发者关注点

- **升级后 UI 完全不可用**（#48208、#48313、#48602）：Linux & Windows Desktop 在更新后加载卡死或白屏，用户只能回退旧版本。
- **终端窗口泛滥**（#48059、#48277、#48945）：Windows CLI 更新后出现大量持久终端窗口，疑似进程 fork 失控，严重影响日常使用。
- **复制粘贴功能频繁回退**（#48125、#48127、#49092）：多个终端模拟器在 0.157.0 后无法使用标准粘贴方式，开发效率骤降。
- **认证与授权问题**：Android 端“Authorize this phone”无限循环（#36268、#48555），切换账号后绑定错误；Windows 下线程/归档因认证未签入而失败（#48367）。
- **资源泄漏**：MCP stdio 管道 fd 泄漏（#26984）仍未修复，长期运行导致 EMFILE 错误。
- **模型误拦截**（#48817）：GPT-6 系列模型对无害提示频繁返回“Invalid prompt safety error”，需要安全策略调整。

---*日报由 AI 自动生成，仅供技术参考。所有链接均为 GitHub 原始 Issue/PR。*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

# Gemini CLI 社区动态日报 | 2026-09-29

## 1. 今日速览

- 发布 **v0.63.0-nightly** 修复了认证循环问题，但社区依然聚焦多个严重的 Agent 挂起与错误报告问题。
- 安全领域出现多个高优先级补丁：`a2a-server` 日志忽略 `LOG_LEVEL` 并泄露请求体、策略目录权限检查缺失等问题已被修复。
- `sandbox_expansion_required` 无限递归和 `.gitignore` 锚定错误等核心 bug 在 PR 中已完成修复，等待合入。

## 2. 版本发布

**v0.63.0-nightly.20260929.gfe6350238**  
- **修复**：认证环路无限循环（由文件竞争、无头 keyring 及 supervisor 状态丢失引发）。  
[查看完整变更日志](https://github.com/google-gemini/gemini-cli/compare/v0.63.0-n...v0.63.0-nightly.20260929.gfe6350238)

## 3. 社区热点 Issues

| # | 标题 | 优先级 | 评论 | 点赞 | 摘要 |
|---|------|--------|------|------|------|
| [#21409](https://github.com/google-gemini/gemini-cli/issues/21409) | Generalist agent hangs | P1 | 8 | 8 | 通用 Agent 在委托子任务时永久挂起，用户反馈等待超过1小时。社区建议通过提示禁止委托可绕过。 |
| [#22323](https://github.com/google-gemini/gemini-cli/issues/22323) | Subagent recovery after MAX_TURNS reported as GOAL success | P1 | 13 | 2 | `codebase_investigator` 子代理达到最大轮次后仍报告“成功”，隐藏了真实的中断原因。影响调试可靠性。 |
| [#28584](https://github.com/google-gemini/gemini-cli/issues/28584) | Sandbox Dockerfile uses node:20-slim (EOL 2026-04-30) | P1 | 4 | 0 | 沙箱镜像仍基于已 EOL 的 Node 20，尽管过去曾升级到 Node 22，安全风险亟待解决。 |
| [#29317](https://github.com/google-gemini/gemini-cli/issues/29317) | a2a-server logger ignores LOG_LEVEL and logs request bodies without redaction | P1 | 4 | 0 | 日志系统硬编码 `info` 级别，且未脱敏请求体，可能泄漏敏感信息。已在 PR #29328 中修复。 |
| [#29309](https://github.com/google-gemini/gemini-cli/issues/29309) | unbounded _execute recursion on sandbox_expansion_required | P2 | 5 | 0 | `scheduler.ts` 中工具返回 `sandbox_expansion_required` 导致无限递归，最终堆溢出崩溃。PR #29332 已修复。 |
| [#29313](https://github.com/google-gemini/gemini-cli/issues/29313) | nested setState in useInputHistoryStore breaks StrictMode | P2 | 5 | 0 | React StrictMode 下因嵌套 setState 导致输入历史记录异常，影响开发体验。 |
| [#29290](https://github.com/google-gemini/gemini-cli/issues/29290) | Nested .gitignore: patterns with only trailing slash anchored incorrectly | P2 | 10 | 0 | 嵌套 `.gitignore` 中 `build/` 模式只忽略同级目录，不向下匹配。PR #29324 已提供最小修复。 |
| [#21968](https://github.com/google-gemini/gemini-cli/issues/21968) | Gemini does not use skills and sub-agents enough | P2 | 6 | 0 | 用户定义的自定义技能和子代理只有在显式指示时才被使用，Agent 缺乏主动调用能力。 |
| [#27668](https://github.com/google-gemini/gemini-cli/issues/27668) | Misrepresents Billing Model, resulting in catastrophic billing ($4,000 in 2 days) | P1 | 3 | 0 | Gemini CLI 错误告知用户使用内部配额，实际产生巨额 API 费用。事件已关闭但争议巨大。 |
| [#22267](https://github.com/google-gemini/gemini-cli/issues/22267) | Browser Agent ignores settings.json overrides (e.g., maxTurns) | P2 | 4 | 0 | 浏览器 Agent 完全忽略全局或项目级 `settings.json` 中的 `maxTurns` 等配置，导致行为不可控。 |

## 4. 重要 PR 进展

| # | 标题 | 状态 | 摘要 |
|---|------|------|------|
| [#29332](https://github.com/google-gemini/gemini-cli/pull/29332) | fix(core): bound how often one call may expand the sandbox | 已合并 | 为 `sandbox_expansion_required` 递归添加深度限制，防止进程因无限递归而堆溢出崩溃。 |
| [#29328](https://github.com/google-gemini/gemini-cli/pull/29328) | fix(a2a-server): honour LOG_LEVEL and keep credentials out of the log | 已合并 | 修复日志系统：使 `LOG_LEVEL` 环境变量生效，并对请求体进行脱敏处理，消除敏感信息泄漏风险。 |
| [#29336](https://github.com/google-gemini/gemini-cli/pull/29336) | fix(core): secure non-system policy directories against write permissions | 已合并 | 将权限检查从仅系统策略目录扩展到用户和工作区策略目录，支持 POSIX/Windows 的当前用户所有权验证。 |
| [#29330](https://github.com/google-gemini/gemini-cli/pull/29330) | fix(cli): keep input typed before the logger answers, and read it once | 已合并 | 修复输入历史记录中嵌套 setState 导致的数据污染问题，保证用户输入在日志输出后仍保留。 |
| [#29327](https://github.com/google-gemini/gemini-cli/pull/29327) | fix(sdk): honour AgentShellOptions env and timeoutSeconds | 已合并 | SDK 的 `AgentShell.exec` 之前忽略 `env` 和 `timeoutSeconds`，现在正确传递到子进程，避免命令无限制等待。 |
| [#29324](https://github.com/google-gemini/gemini-cli/pull/29324) | fix(core): don't anchor nested .gitignore patterns that only have a trailing slash | 已合并 | 针对 #29290 的最小修复：嵌套 `.gitignore` 中 `build/` 模式不再被错误锚定，改为向下递归匹配。 |
| [#29436](https://github.com/google-gemini/gemini-cli/pull/29436) | fix(cli): prevent 100% CPU hang from @ within quotes in stdin | 开放中 | 修复管道输入中带引号的 `@`（如 `import from "@scope/pkg"`）导致 CPU 100% 挂起的问题。 |
| [#29435](https://github.com/google-gemini/gemini-cli/pull/29435) | fix(cli,core): prevent process hang on session exit | 开放中 | 清理 stdin 监听器和 MCP 传输连接，确保会话退出时 Node 事件循环正确终止，避免进程残留。 |
| [#29539](https://github.com/google-gemini/gemini-cli/pull/29539) | fix(core): enable autonomous plan execution in non-interactive mode | 开放中 | 在非交互/无头模式下，Plan Mode 跳过用户确认步骤，自动合成策略并执行计划，面向 CI/CD 场景。 |
| [#29542](https://github.com/google-gemini/gemini-cli/pull/29542) | fix(core): disable truncation when maxChars <= 0 in formatTruncatedToolOutput | 开放中 | 当 `maxChars` 设为 0 或负数时禁用工具输出截断，避免因截断逻辑导致字符串意外扩展的边界问题。 |

## 5. 功能需求趋势

从近期 Issue 和 PR 中可以提炼出社区最关注的 **四大功能方向**：

1. **Agent 行为自主性与透明度**  
   - 要求子代理轨迹可通过 `/chat share` 分享、Bug Report 包含子代理上下文、Agent 应更主动使用自定义技能和子代理。  
   - 希望 Agent 能自我认知（了解自身命令行标志、热键、能力），避免破坏性操作（如 `git reset --force`）。

2. **安全与权限加固**  
   - 日志脱敏、环境变量生效、策略目录权限检查、沙箱基础镜像升级至 Node 22（已 EOL 的 Node 20 带来隐患）。  
   - 认证环路、密钥管理、无头模式下的安全性也成为修复重点。

3. **跨工作区与多根支持**  
   - 多根工作区（`includeDirectories`）导致 `GlobTool` 校验与执行目录不一致；请求增加跨工作区会话列表 `--list-all-sessions`。

4. **非交互/Headless 模式完善**  
   - 允许 Plan Mode 在无头环境下自动执行，支持 CI/CD 集成；同时修复 `ShellProcessor` 忽略中断信号、管道输入超时等问题，提升脚本化使用体验。

## 6. 开发者关注点

- **高频痛点**：Agent 挂起（#21409）和子代理错误反馈（#22323）是反馈最多的两类问题，严重影响日常使用可靠性。
- **

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

⚠️ 摘要生成失败。

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，以下是根据您提供的 GitHub 数据生成的 2026 年 9 月 29 日 OpenCode 社区动态日报。

---

# OpenCode 社区动态日报 | 2026-09-29

## 今日速览

OpenCode 今日发布了 v1.18.33 热修复版本，主要解决了 Cloudflare AI 网关超时和调试信息泄露等关键 Bug。社区方面，关于 GPT-5.6 Sol 模型的服务器过载错误成为最热议题，同时，社区对“Human-in-the-Loop”机制的实现讨论持续升温。

## 版本发布

### v1.18.33 发布

这是一个维护性版本，重点修复了核心功能中的几个关键问题，提升了稳定性和安全性。

- **Bug 修复：**
  - **Cloudflare AI 网关超时**：现在能正确遵守提供商响应和流的超时设置。（贡献者：@danlapid）
  - **MCP 浏览器启动**：修复了启动器立即退出时，未能正确报告失败的问题。
  - **调试安全性**：对调试配置的输出进行了脱敏处理，移除了凭据和敏感标头。
  - **Gemini 思考模型**：修复了 Gemini 模型思考过程中的若干问题。

## 社区热点 Issues

1.  **GPT-5.6 Sol 模型服务器过载**
    - **Issue #39653**：用户反馈在使用 Sol 模型时持续遭遇“服务器过载”错误，但使用 Pi 或 Codex 模型则无此问题。该问题获得了 11 个赞，引发广泛关注，表明 Sol 模型的服务端可能存在稳定性问题。
    - **链接**: [anomalyco/opencode Issue #39653](https://github.com/anomalyco/opencode/issues/39653)

2.  **Ollama 集成响应异常**
    - **Issue #37762**：用户报告在 Windows 上使用 Ollama 本地模型时响应异常，尽管 Cloud 模型工作正常。这反映了本地模型集成稳定性仍需改进。
    - **链接**: [anomalyco/opencode Issue #37762](https://github.com/anomalyco/opencode/issues/37762)

3.  **模式切换功能失效**
    - **Issue #38655**：最新更新后，用户无法在 “Plan” 和 “Build” 模式间切换，默认始终为 Build 模式。这是一个影响核心工作流程的严重 Bug。
    - **链接**: [anomalyco/opencode Issue #38655](https://github.com/anomalyco/opencode/issues/38655)

4.  **响应速度极其缓慢**
    - **Issue #39527**：用户反馈 OpenCode 响应变得极其缓慢，简单的问候也需要十分钟才能回复。这暗示可能存在未捕获的性能退化或网络问题。
    - **链接**: [anomalyco/opencode Issue #39527](https://github.com/anomalyco/opencode/issues/39527)

5.  **新功能：简易聊天模式**
    - **Issue #39399**：用户希望提供一个纯粹的“简单聊天”模式，避免 OpenCode 自动向模型发送系统提示词。这表明部分用户需要一个更轻量、无干扰的交互界面。
    - **链接**: [anomalyco/opencode Issue #39399](https://github.com/anomalyco/opencode/issues/39399)

6.  **功能请求：网络错误的快速失败与清晰的错误提示**
    - **Issue #39771**：用户提出在网络不稳时，工具应能快速失败而非等待 60-120 秒的超时，并提供更清晰的错误输出。这直接关系到开发者的使用体验和效率。
    - **链接**: [anomalyco/opencode Issue #39771](https://github.com/anomalyco/opencode/issues/39771)

7.  **Sidecar 启动失败**
    - **Issue #39494**：Windows 用户报告 OpenCode 桌面版启动时 Sidecar 进程无法在 60 秒内就绪。这是一个阻碍性错误，影响用户正常使用。
    - **链接**: [anomalyco/opencode Issue #39494](https://github.com/anomalyco/opencode/issues/39494)

8.  **提示词缓存与计费不明确**
    - **Issue #37598**：用户指出在使用某些模型时，缓存命中的行为不稳定且计费记录不明确，影响了使用的透明度和成本控制。
    - **链接**: [anomalyco/opencode Issue #37598](https://github.com/anomalyco/opencode/issues/37598)

9.  **WYSIWYG 文档预览与编辑**
    - **Issue #39611**：社区提议为生成的文档格式（docx, HTML, Markdown）提供所见即所得的预览与编辑功能，提升内容创作体验。
    - **链接**: [anomalyco/opencode Issue #39611](https://github.com/anomalyco/opencode/issues/39611)

10. **桌面版插件安装回归**
    - **Issue #39543**：用户报告在 Desktop v1.18.9 上，npm 插件安装功能再次失效（回归），这与之前修复的 #26085 问题相关。
    - **链接**: [anomalyco/opencode Issue #39543](https://github.com/anomalyco/opencode/issues/39543)

## 重要 PR 进展

1.  **[#51967] 新增 Human-in-the-Loop 确认级别**
    - **PR #51967 (已关闭)**：实现了“Human-in-the-Loop”功能，引入 `AUTO`、`SAFE`、`BALANCED` 等 5 个可配置的确认级别，作为现有权限系统的附加层。
    - **链接**: [anomalyco/opencode PR #51967](https://github.com/anomalyco/opencode/pull/51967)

2.  **[#51981] 为多个消息路由启用缓存**
    - **PR #51981 (开放中)**：为 Alibaba、Cloudflare 等 6 个供应商的消息路由启用默认缓存策略，以提升 API 调用效率并降低成本。
    - **链接**: [anomalyco/opencode PR #51981](https://github.com/anomalyco/opencode/pull/51981)

3.  **[#51986] 修复跨轮次的图片裁剪问题**
    - **PR #51986 (开放中)**：修复了在连续对话中，图片尺寸裁剪不稳定的 Bug，确保模型收到的图片数据一致。
    - **链接**: [anomalyco/opencode PR #51986](https://github.com/anomalyco/opencode/pull/51986)

4.  **[#51090] 修复推理期间的显示问题**
    - **PR #51090 (开放中)**：优化了 UI 显示，确保当模型只在后台进行“推理”时，UI 能正确保持“Working”状态，而非显示空白。
    - **链接**: [anomalyco/opencode PR #51090](https://github.com/anomalyco/opencode/pull/51090)

5.  **[#50283] 暴露模型的推理能力配置**
    - **PR #50283 (开放中)**：修复了模型配置中 `reasoning` 标志位丢失的问题，允许用户正确启用或禁用模型的推理能力。
    - **链接**: [anomalyco/opencode PR #50283](https://github.com/anomalyco/opencode/pull/50283)

6.  **[#51979] 优化 MCP OAuth 令牌刷新**
    - **PR #51979 (开放中)**：通过“single-flight”模式优化并发 MCP OAuth 刷新，防止出现令牌刷新冲突和网络请求风暴。
    - **链接**: [anomalyco/opencode PR #51979](https://github.com/anomalyco/opencode/pull/51979)

7.  **[#51975] 对齐 Shell 工具环境变量**
    - **PR #51975 (已关闭)**：为 Shell 工具添加环境变量标记（如 `OPENCODE_SESSION_ID`），帮助执行的脚本识别其所在会话和代理上下文。
    - **链接**: [anomalyco/opencode PR #51975](https://github.com/anomalyco/opencode/pull/51975)

8.  **[#51969] 修复 LLM Bash 工具的 WASM 加载错误**
    - **PR #51969 (开放中)**：修复了在 LLM 执行 Bash 工具时，因 WASM 模块加载失败而导致的 `loadWebAssemblyModule` 错误。
    - **链接**: [anomalyco/opencode PR #51969](https://github.com/anomalyco/opencode/pull/51969)

9.  **[#51973] 新增最近关闭标签页菜单**
    - **PR #51973 (开放中)**：在 UI 上增加了“最近关闭的标签页”菜单，方便用户通过右键点击恢复误关闭的会话。
    - **链接**: [anomalyco/opencode PR #51973](https://github.com/anomalyco/opencode/pull/51973)

10. **[#51974] 新增 `/loop` 命令**
    - **PR #51974 (开放中)**：新增 `/loop` 命令，支持定时循环执行任务，为自动化工作流提供了基础。
    - **链接**: [anomalyco/opencode PR #51974](https://github.com/anomalyco/opencode/pull/51974)

## 功能需求趋势

- **开发者体验优化**：社区强烈呼吁提升日常使用体验，包括**可配置的简易聊天模式**、**WYSIWYG 文档编辑**、**网络错误的快速失败机制**以及**UI 主题自动跟随**。
- **核心稳定性与问题修复**：大量 Issue 集中在**服务器过载**、**响应延迟**、**模式切换失效**和**Sidecar 启动失败**等阻碍性问题上。修复这些 Bug 是当前社区的第一要务。
- **增强模型与 API 支持**：社区希望**更透明地暴露模型能力**（如推理开关），并对接更多供应商（如 NVIDIA、Gemini 新版本），同时**优化提示词缓存机制**以提升效率和控制成本。
- **安全与权限管理**：**Human-in-the-Loop** 和**更细粒度的权限管理**是备受关注的功能发展方向，旨在提供更可控的 AI 协作体验。

## 开发者关注点

1.  **连接稳定性与错误信息**：网络不稳定时的长时间等待和无明确提示，是开发者最大的痛点之一。
2.  **npm 插件安装与本地模型集成**：插件生态的健壮性和本地模型（如 AI SDK V2 的集成稳定性）的易用性直接影响开发者的扩展和私有化部署。
3.  **快捷键与交互适配**：Windows 平台上的快捷键冲突（如 `Win+A`）和剪切板/选择行为不符合用户习惯，是影响日常使用效率的关键细节。
4.  **配置持久化与透明度**：部分 UI 操作（如 Desktop 上的“Connect”按钮）未能正确持久化配置，导致重启后丢失，且存在计费计费不透明的问题，降低了信任感。

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# 2026-09-29 Pi 社区动态日报

---

## 今日速览

Pi 社区今日主要围绕稳定性与兼容性展开：推理模型上下文死锁、终端卡死等长期 bug 持续得到关注；同时，Codemode / MCP 支持、托管 llama.cpp 以及虚拟模型等重量级 PR 进入审查阶段，标志着 Pi 正从单一代理想可扩展自动化平台演进。

---

## 社区热点 Issues

以下 10 个 Issue 反映了当前社区最关注的稳定性、兼容性和性能问题：

### 1. **[#10031] Pi 在按 ESC 停止思考后卡在 “Working…” 状态**  
  **作者**: kkovacs | 💬 17 评论 | ⭐ 2 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/issues/10031  
  **说明**: 该 bug 从 v0.84.0 开始持续约一个月，用户必须 `CTRL+C` 退出后用 `pi -c` 恢复。影响多台机器，是当前反馈最强烈的稳定性问题之一。

### 2. **[#9508] pi-ai 向兼容 OpenAI 的提供商发送非标准字段导致 400/422**  
  **作者**: srcKod | 💬 8 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/issues/9508  
  **说明**: 许多第三方提供商（如本地代理、LiteLLM）拒绝 OpenAI 特定字段，导致之前可用的模型突然失败。社区期待 Pi 能增加 “严格模式” 或自动过滤。

### 3. **[#9409] 推理模型永久卡在上下文上限，每次请求返回 `stopReason: "length"`**  
  **作者**: Sager611 | 💬 4 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/issues/9409  
  **说明**: 使用推理模型（如 gpt-o、DeepSeek 等）时，会话达到上下文上限后无法通过自动压缩恢复，导致永久死锁。社区多次回退，急需更智能的压缩策略。

### 4. **[#10074] Anthropic 工具调用：非 ASCII 编辑参数被静默破坏（`\uXXXX` 中丢失 `u`）**  
  **作者**: hoonysis | 💬 4 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/issues/10074  
  **说明**: 包含韩文等非 ASCII 字符的文件通过 `edit` 工具时频繁失败或造成文件损坏。问题持续三周仍复现，影响多语言用户的日常使用。

### 5. **[#10077] llama.cpp 模型 `contextWindow` 在 `models-store.json` 中被重置为 128000**  
  **作者**: sa-mendez | 💬 3 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/issues/10077  
  **说明**: 用户设置的 `ctx-size` 在 Pi 加载后有时会被覆盖，导致本地模型无法按预期使用更大的上下文。该问题影响所有本地 llama 用户。

### 6. **[#10072] `built-in-tool-renderer` 示例移除了模型系统提示中的工具定义**  
  **作者**: pandysp | 💬 2 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/issues/10072  
  **说明**: 官方示例扩展不当，在修改工具渲染时丢失了原始工具描述，导致模型无法正确调用工具。这对插件开发者有误导性。

### 7. **[#10137] 失败的阈值压缩未改变上下文，后续请求仍带完整上下文**  
  **作者**: dennisimoo | 💬 2 评论 | 状态: **CLOSED**（但核心问题未解决）  
  **链接**: https://github.com/earendil-works/pi/issues/10137  
  **说明**: 压缩失败后继续使用未压缩上下文，导致工具调用重复执行。虽然已关闭，但社区认为应建立更健壮的压缩失败回退机制。

### 8. **[#10105] 每次会话创建都重新加载所有扩展，导致 4s→>280s 延迟**  
  **作者**: wu546526 | 💬 2 评论 | 状态: **CLOSED**  
  **链接**: https://github.com/earendil-works/pi/issues/10105  
  **说明**: 大型扩展设置（70+扩展）下每次新聊天都要重新加载，且多进程累积成本。这是一个严重的性能退化问题。

### 9. **[#10104] 会话创建延迟：15.5s 基线，随时间退化至 >140s**  
  **作者**: wu546526 | 💬 2 评论 | 状态: **CLOSED**  
  **链接**: https://github.com/earendil-works/pi/issues/10104  
  **说明**: 在长时间运行的进程中，会话创建延迟逐渐增大，伴随 CPU 峰值。影响 Web UI 用户的重连接体验。

### 10. **[#10148] 包含未回答工具调用的 turn 可永久挂起**  
  **作者**: Ayo-Fam | 💬 1 评论 | 状态: **CLOSED**  
  **链接**: https://github.com/earendil-works/pi/issues/10148  
  **说明**: 如果模型输出工具调用后数据流静默消失，会话不仅不报错，还会永远等待。这是 0.87.0 的严重死锁场景。

---

## 重要 PR 进展

以下 10 个 PR 代表了 Pi 在功能扩展、修复和性能优化方面的最新努力：

### 1. **[#10040] feat(coding-agent): Codemode and MCP**  
  **作者**: mitsuhiko | 💬 0 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/pull/10040  
  **说明**: 核心特性：支持模型在 QuickJS WASM 虚拟机中运行 JavaScript，并调用 Pi 的工具（Codemode）；同时引入 MCP（Model Context Protocol），使 Pi 能作为 MCP 客户端与其他自动化工具互操作。

### 2. **[#10122] feat(coding-agent): add managed llama.cpp server mode**  
  **作者**: mitsuhiko | 💬 0 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/pull/10122  
  **说明**: Pi 现在可以自动启动/管理本地的 llama-server，通过独立 supervisor 进程处理端口分配和连接计数，简化本地模型使用。

### 3. **[#10035] feat(coding-agent): Virtual models**  
  **作者**: mitsuhiko | 💬 0 评论 | 状态: **CLOSED**  
  **链接**: https://github.com/earendil-works/pi/pull/10035  
  **说明**: 实验性功能：扩展可注册“虚拟模型”，在每次请求时动态选择底层物理模型和思考级别。为策略路由和负载均衡打下基础。

### 4. **[#9714] feat(ai): support Azure Foundry Chat Completions deployments**  
  **作者**: jsanter27 | 💬 0 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/pull/9714  
  **说明**: 为 Azure Foundry 添加 Chat Completions API 支持，使 DeepSeek V4 Pro 等模型能在 Azure 上正常工作。此前只支持 Responses API。

### 5. **[#10136] fix(coding-agent,tui): paste Finder file paths instead of icons**  
  **作者**: christianklotz | 💬 0 评论 | 状态: **CLOSED**  
  **链接**: https://github.com/earendil-works/pi/pull/10136  
  **说明**: 修复 macOS 上复制文件后粘贴得到 Finder 图标的问题，现在会粘贴实际文件路径，并保留图片/文本后备方案。

### 6. **[#10142] fix(ai): send reasoning effort to OpenAI models on Bedrock Converse**  
  **作者**: jsanter27 | 💬 0 评论 | 状态: **OPEN**  
  **链接**: https://github.com/earendil-works/pi/pull/10142  
  **说明**: Bedrock Converse 适配器此前仅向 Claude 发送思考字段，导致 OpenAI 模型在 Bedrock 上始终使用默认 `medium` 努力度。现在正确传递配置的思考级别。

### 7. **[#10135] fix(coding-agent): normalise compaction usage to prevent footer crash on resume**  
  **作者**: holny | 💬 0 评论 | 状态: **CLOSED**  
  **链接**: https://github.com/earendil-works/pi/pull/10135  
  **说明**: 修复压缩后 footer 显示崩溃问题，确保压缩后的用量统计正确归一化。

### 8. **[#10134] fix(coding-agent): preserve tool prompt fields in built-in-tool-renderer example**  
  **作者**: hol

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

好的，请看以下为您生成的2026-09-29 Qwen Code社区动态日报。

---

# Qwen Code 社区动态日报

**日期**: 2026-09-29
**数据来源**: [QwenLM/qwen-code](https://github.com/QwenLM/qwen-code)

---

### 今日速览

今日社区的核心议题围绕“Managed Agent”双路径架构的深度讨论和分阶段交付规划，以及针对上下文Token治理和多智能体（Multi-Agent）协作的持续打磨。值得注意的是，多个高优先级Issue和PR正在解决远程SSH环境下的会话崩溃、安全性漏洞以及性能瓶颈，显示出项目正从功能构建转向稳定性与安全性的精细化运营。无新版本发布，但大量涉及架构和核心模块的PR正在密集推进中。

### 社区热点 Issues

1.  **[#12380] proposal(serve): Define Managed Agent dual-path architecture and staged delivery** (评论: 37)
    - **重要性**: 社区最热议题。该提案定义了`Managed Agent`的双路径架构（Legacy vs. Managed），并规划了从A到H的阶段性交付计划，是Qwen Code未来的核心发展方向。多路评论深入讨论了持久化会话、工作区绑定等核心概念。
    - **链接**: [Issue #12380](https://github.com/QwenLM/qwen-code/issues/12380)

2.  **[#12416] Remote-SSH: every POST /session fails with `write EPIPE` / `BridgeChannelClosedError`** (评论: 17)
    - **重要性**: **P1优先级Bug**。Remote-SSH场景下，任何会话创建都会失败。此问题严重影响远程开发用户，社区反馈热烈，开发者（danyavaad）详细描述了环境、症状和日志，对修复至关重要。
    - **链接**: [Issue #12416](https://github.com/QwenLM/qwen-code/issues/12416)

3.  **[#12028] tracking(core): non-conversation context token governance** (评论: 11)
    - **重要性**: **P2核心议题**。跟踪非对话上下文（如系统提示、工具架构）导致的Token过度消耗问题。社区开始关注大模型场景下，容易被忽视的“固定开销”成本，对优化性能和API成本有重要指导意义。
    - **链接**: [Issue #12028](https://github.com/QwenLM/qwen-code/issues/12028)

4.  **[#12737] feat(acp-bridge): Stage B host integration for paired Legacy and Managed engines** (评论: 13)
    - **重要性**: 作为#12380 Stage B的跟踪议题，探讨Legacy和Managed双引擎的主机集成方案。社区的决策是优先交付Hosted Managed服务，本地执行优先级靠后，反映了产品策略的权衡。
    - **链接**: [Issue #12737](https://github.com/QwenLM/qwen-code/issues/12737)

5.  **[#12947] Track structured Auto Memory rollout readiness on main** (评论: 7)
    - **重要性**: 跟踪结构化自动记忆（Auto Memory）在主分支上线的就绪状态。这是#12028 (Token治理)的子任务，也是#10151 (改进Auto Memory)的收尾工作，标志着记忆模块即将迈入新的里程碑。
    - **链接**: [Issue #12947](https://github.com/QwenLM/qwen-code/issues/12947)

6.  **[#12856] Aux-model selectors persist a NUL-separated baseUrl that every public surface emits verbatim** (评论: 6)
    - **重要性**: **安全Bug**。辅助模型选择器持久化了包含空字符分隔符的baseURL，可能导致凭证泄露。这是一个潜在的安全漏洞，社区正积极讨论修复方案。
    - **链接**: [Issue #12856](https://github.com/QwenLM/qwen-code/issues/12856)

7.  **[#10151] Improve Auto Memory with structured recall and lossless migration** (评论: 6)
    - **重要性**: 社区长期关注的功能需求。旨在设计结构化、无损且按需召回的记忆路径。该议题的讨论结果将直接影响用户长期会话体验和智能体记忆力。
    - **链接**: [Issue #10151](https://github.com/QwenLM/qwen-code/issues/10151)

8.  **[#11019] AUTO mode: user approvals never reach the classifier** (评论: 4)
    - **重要性**: **严重Bug**。在AUTO模式下，用户对关键操作的批准无法被分类器接收，导致用户确认无效。这直接破坏了安全确认机制，对生产环境中的自动化操作构成风险。
    - **链接**: [Issue #11019](https://github.com/QwenLM/qwen-code/issues/11019)

9.  **[#8281] Add an Email channel with IMAP and SMTP support** (评论: 6)
    - **重要性**: 虽是P3优先级，但该功能请求持续引发讨论。社区希望Qwen Code Agent能通过邮件与用户交互，扩展了Agent的交互渠道，是未来工作流自动化的重要设想。
    - **链接**: [Issue #8281](https://github.com/QwenLM/qwen-code/issues/8281)

10. **[#11471] Auto-memory extract has no frequency gate** (评论: 4)
    - **重要性**: 社区开发者（GCGH159）对该功能进行了深度分析，指出记忆提取逻辑可能存在性能问题：缺乏频率限制且在无操作后仍会触发。这引发了关于背景自动化进程效率和设计意图的讨论。
    - **链接**: [Issue #11471](https://github.com/QwenLM/qwen-code/issues/11471)

### 重要 PR 进展

1.  **[#12894] feat(managed-agent): Add durable remote Shell result delivery**
    - **重要性**: 为Hosted Shell调用添加了持久化的远程结果交付路径，包括标准输出/错误输出、不可变目录存储等。这是构建可靠远程执行能力的关键模块。
    - **链接**: [PR #12894](https://github.com/QwenLM/qwen-code/pull/12894)

2.  **[#12891] feat(memory): bundle Mem0 with the main CLI**
    - **重要性**: 将第三方记忆服务Mem0作为可选功能集成到CLI中。此举为开发者提供了更灵活、强大的记忆后端选项，有望显著提升Agent的长期记忆能力。
    - **链接**: [PR #12891](https://github.com/QwenLM/qwen-code/pull/12891)

3.  **[#12946] feat(managed-agent): Implement private Hosted MCP runtime (H1)**
    - **重要性**: 实现私有的Hosted MCP Runtime，这是Managed Agent架构Stage H1的核心交付物。它负责管理MCP连接、凭证并为主机提供运行时环境。
    - **链接**: [PR #12946](https://github.com/QwenLM/qwen-code/pull/12946)

4.  **[#12920] docs(managed-agent): Defer local engine delivery behind Hosted**
    - **重要性**: 明确文档化产品策略：将本地Managed引擎交付推迟，优先交付Hosted服务。这对社区开发者了解未来版本路线图至关重要。
    - **链接**: [PR #12920](https://github.com/QwenLM/qwen-code/pull/12920)

5.  **[#12280] fix(core): keep Write deny rules when quoting hides the async operator**
    - **重要性**: 修复了一个安全绕过漏洞。攻击者可通过特定shell引用技巧绕过`deny`规则，修改受保护文件。这是重要的安全修复。
    - **链接**: [PR #12280](https://github.com/QwenLM/qwen-code/pull/12280)

6.  **[#12943] feat(web-shell): add adaptive navigation rail and unified Live settings**
    - **重要性**: 增强Web Shell用户体验，引入自适应导航栏和统一的实时设置面板。这显示了团队在持续优化UI/UX。
    - **链接**: [PR #12943](https://github.com/QwenLM/qwen-code/pull/12943)

7.  **[#12898] feat(core): lazy-load deferred tools in Code Mode**
    - **重要性**: 为Code Mode引入延迟工具加载机制。这可以优化启动速度和资源占用，对于提升开发者体验（特别是在大型项目中）有重要意义。
    - **链接**: [PR #12898](https://github.com/QwenLM/qwen-code/pull/12898)

8.  **[#12580] feat(prompt): answer from conversation history before investigating**
    - **重要性**: 改进系统提示词，引导Agent优先从对话历史中寻找答案，而不是立即触发外部搜索或工具调用。这能显著提升响应速度和效率。
    - **链接**: [PR #12580](https://github.com/QwenLM/qwen-code/pull/12580)

9.  **[#12531] fix(core): stop MCP server rules from authorizing a colliding server**
    - **重要性**: 修复了一个MCP服务器规则授权的逻辑缺陷，防止命名冲突导致错误授权。这是对MCP协议实现的一个关键补丁。
    - **链接**: [PR #12531](https://github.com/QwenLM/qwen-code/pull/12531)

10. **[#12773] fix(cli): pin fast model to the selected provider endpoint**
    - **重要性**: 修复了多Provider场景下“快速模型”选择器的问题，确保快速模型能锁定到用户指定的具体提供者端点上，解决了模型切换时的歧义问题。
    - **链接**: [PR #12773](https://github.com/QwenLM/qwen-code/pull/12773)

### 功能需求趋势

- **多智能体（Multi-Agent）与工作流编排**: 以`#12380`为代表，社区正积极探索和定义Managed Agent架构，包括Agent之间的协作、任务分配、持久化生命周期和会话管理等。
- **记忆与上下文治理**: `#12028`, `#10151`, `#12947`等Issue表明，社区对智能体记忆的管理需求日益旺盛，从简单的记忆存储转向结构化召回、无损迁移和Token成本控制。
- **安全性与权限管理**: `#12856` (凭证泄露) 和 `#11019` (用户审批绕过) 等议题反映出对Agent在自动执行任务时安全性和可控性的高度关注。`#12280` PR则直接修复了命令注入的绕过漏洞。
- **持久化与可靠性增强**: 大量Issue和PR（如`#12416` Remote-SSH崩溃，`#12894` 持久化Shell结果）专注于提升在远程、生产环境下的可靠性和稳定性。
- **IDE与交互渠道扩展**: 除了核心CLI和Web Shell，社区仍在推进功能扩展，例如`#8281`提出的Email通道集成，以及`#12943`对Web Shell UI的优化。

### 开发者关注点

- **Remote-SSH稳定性**: `#12416`是开发者反映最强烈的痛点，会话创建失败是阻塞性Bug，严重影响通过SSH进行远程开发的用户。
- **配置与安全陷阱**: `#12856` (空字符导致的凭证泄露) 和 `#11019` (用户审核被忽略) 等议题揭示了配置和安全机制中不易察觉但后果严重的问题。开发者对配置的透明性和验证性有更高期待。
- **性能与Token成本意识**: `#12028` (非对话Token治理) 和 `#11471` (记忆提取性能分析) 表明开发者开始关注系统内部开销，特别是大模型API调用背后的隐形成本，社区正推动更有意识的优化。
- **对复杂架构的透明度**: `#12380`提案及其多个子议题 (`#12737`, `#12867`等) 虽然讨论热烈，但也显示出架构演进过程中的复杂性。开发者希望看到更清晰、易于理解的演进路线图和文档。
- **“静默”行为和隐藏Bug**: 开发者对`#11408` (延迟审查发现) 和`#12835` (技能列表在排除后仍被注入) 这类不易被发现但影响预期的“静默”行为非常敏感，这些问题往往需要深度使用后才能察觉。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，这是为您生成的 DeepSeek TUI 社区动态日报，聚焦于当前活跃的关联项目 **CodeWhale**。

---

# CodeWhale 社区动态日报 | 2026-09-29

## 今日速览

昨日（2026-09-28）CodeWhale 社区活跃度极高，主要围绕 **v0.10.1 补丁版本发布**、**SSE 网络容错机制** 及 **UI 渲染异常修复** 展开。维护者关闭了多个关于会话与快照管理的长期 issue，并合并了多项关键修复。与此同时，社区对新模型提供者支持（如 Tsubasa）和网络配置可调性的需求浮出水面。

## 版本发布

- **[v0.10.1] 补丁版本发布**
  维护者 `Hmbown` 在昨日合并并发布了 v0.10.1 版本。该版本主要修复了因硬编码默认超时导致的长任务被意外中断问题，以及对多个排期到 0.10.1 版本的问题进行了修复。
  - **修复**: 移除了引擎中默认的每次对话回合硬性超时限制 (`PR #6703`)。
  - **修复**: 解决了首次启动时配置的提供者被本地运行的 Ollama 错误覆盖的问题 (`PR #6687`)。
  - **修复**: 优化了 `Ctrl+T` 快捷键在不同路由模式下的思维链层级切换逻辑 (`PR #6667`)。
  - **修复**: 修复了在 80 列终端宽度下，页脚无法完全显示推理等级的文本标签 (`PR #6686`)。
  - 链接：`https://github.com/Hmbown/Codewhale/pull/6708`

## 社区热点 Issues

1.  **[#6699] SSE 请求无响应头时对话回合直接失败且无重试机制**
    - **重要性**: **极高**。这是一个网络稳定性相关的Bug。在流式请求（SSE）建立连接的过程中，如果网络故障导致无法接收到任何响应头，整个对话回合会立即失败，而代码中其他位置的网络故障都配置了重试逻辑。这导致该环节成为不可靠网络上的单点故障。
    - **社区反应**: 由资深贡献者提出，已明确指出了引擎中两种恢复机制（用户层面/代理层面）均无法覆盖此场景。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6699`

2.  **[#6700] 请求将流式重试预算和传输超时暴露为可配置项**
    - **重要性**: **高**。此 issue 是 #6699 的延伸，社区希望将当前硬编码 (`const`) 的网络容错参数变为用户可配置的选项。这对于部署在代理或不稳定网络环境中的用户至关重要。
    - **社区反应**: 已创建，并详细列出了当前各类网络参数的配置现状。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6700`

3.  **[#6697] TUI 界面中“跳转到最新消息”按钮渲染异常**
    - **重要性**: **高**。这是直接影响用户体验的UI bug。按钮上出现了多条水平线，属于视觉渲染问题。
    - **社区反应**: 用户已提供截图，问题可复现。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6697`

4.  **[#6704] TUI 界面文本背景显示异常**
    - **重要性**: **高**。另一个影响核心阅读体验的 UI Bug。在连续运行约半小时后，TUI 的文本背景会变为黑色，导致阅读困难。
    - **社区反应**: 用户已提供运行前和运行后的截图对比，问题明确。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6704`

5.  **[#6705] `opencode-zen` 路由因预置的模型列表过时而拒绝 58 个模型**
    - **重要性**: **中**。该 issue 揭示了 CodeWhale 内部“支持”但实际无法使用的模型兼容性问题。由于内置的模型白名单未及时更新，导致超过一半的目录模型被标记为“未经证实的端点”而无法使用。
    - **社区反应**: 用户提出了对由 `catalog.rs` 控制的静态端点列表的批评，建议改为动态注册。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6705`

6.  **[#6695] [功能请求] 为 Tsubasa 添加提供者描述符**
    - **重要性**: **中**。这是一个来自社区的功能请求，希望 CodeWhale 能原生支持 Tsubasa 模型服务，避免用户需要手动定义自定义提供者。
    - **社区反应**: 请求者已提出具体方案（提供端点、密钥别名和公开模型），并等待维护者批准。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6695`

7.  **[#6706] 重构整个调试命令组以使其可移植 (FEAT-029)**
    - **重要性**: **高**。这是 CodeWhale 大规模架构重构（Crate 分解）的一部分。此 issue 旨在将 14 个调试斜杠命令从当前的 TUI 应用中解耦，使其成为可被其他前端（如 CLI、Web）复用的独立模块。
    - **社区反应**: 已有对应的 PR (#6707) 对此进行实现。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6706`

8.  **[#5316] [EPIC] CodeWhale TUI 模块分解 (Umbrella)**
    - **重要性**: **极高**。这是一个里程碑级别的史诗任务，追踪整个 CodeWhale 核心模块从单体 TUI 应用中拆分为独立 Rust Crate 的进度。这是提升代码可维护性、可测试性和构建速度的关键举措。
    - **社区反应**: 评论多达 29 条，显示了其高度的复杂性。维护者 `aboimpinto` 持续更新执行计划。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/5316`

9.  **[#6702] 自动化健康检查摘要 (2026-09-28)**
    - **重要性**: **高**。这是由 bot 自动生成的每周项目健康报告。报告指出 `main` 分支当前处于红色状态（`Windows` 平台测试失败），并给出了修复建议。这是项目状态的核心监控信号。
    - **社区反应**: 报告由自动化工具生成，内容经过结构化排序。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6702`

10. **[#6698] `main` 分支全量测试门禁失败**
    - **重要性**: **高**。明确指出了当前 `main` 分支的 CI 门禁存在问题。问题在于一个“共享进程”全量工作空间测试失败，这通常与集成测试环境或代码合并冲突有关。
    - **社区反应**: 问题已被创建，但尚无人认领。这很可能与 #6702 报告的红名问题为同一件事。
    - 链接：`https://github.com/Hmbown/Codewhale/issues/6698`

## 重要 PR 进展

1.  **[#6703] fix(engine): 移除默认的每轮对话硬超时限制**
    - **内容**: 一个长时间运行的对话回合在刚好满 1 小时时被强制终止，即使它仍在持续输出。此 PR 移除了这个默认的硬性限制。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6703`

2.  **[#6646] perf(tui): 优化线程列表加载性能**
    - **内容**: 修复了一个性能问题。当有大量对话（140个线程、6万多个文件）时，打开一个线程的界面会卡顿高达 **6.7 秒**。PR 通过引入索引文件，避免了遍历整个目录来查找线程信息。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6646`

3.  **[#6707] refactor(commands): 使整个调试命令组可移植**
    - **内容**: 完成了对 `/tokens`, `/cost`, `/undo` 等 14 个调试斜杠命令的重构，使其脱离 TUI 应用，为模块化拆分（FEAT-029）打下基础。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6707`

4.  **[#6645] fix(runtime): 修复线程快照所有权问题，支持文件级撤销**
    - **内容**: 修复了一个核心问题：运行时线程无法为其创建的快照建立持久身份。导致撤销操作 (`/undo`) 无法正确工作。PR 确保每个线程拥有自己的快照，使得文件级撤销成为可能。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6645`

5.  **[#6682] fix(tui): 将 `/undo` 的作用域限定为被撤销步骤更改的路径**
    - **内容**: 在 #6645 的基础上，进一步改进了 TUI 的 `undo` 命令。以前撤回会恢复整个工作树，现在只会恢复该轮对话实际修改的文件，更加精确高效。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6682`

6.  **[#6687] fix(tui): 首次启动时保留用户配置的提供者**
    - **内容**: 修复了一个新手引导 Bug：如果用户在配置文件中指定了 OpenAI 兼容端点，但本地恰好运行着 Ollama，TUI 会错误地自动切换到 Ollama 并运行其模型，导致用户困惑。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6687`

7.  **[#6667] fix(tui): 修复 Ctrl+T 快捷键在固定路由上无效的问题**
    - **内容**: 修复了在指定了特定模型（如 `deepseek-v4.1-flash`）后，按下 `Ctrl+T` 切换思维链层级无效的问题。原因是自动路由和固定路由使用了不同的内部层级列表。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6667`

8.  **[#6660] Runtime: 对话工单现在携带类型化的工件引用**
    - **内容**: 这是一个重要的增强功能。以前，一次对话生成了什么文件或大型输出是未知的。现在，对话记录会明确记录其产生的工件引用，使得预览功能可以直观展示对话的产出。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6660`

9.  **[#6640] fix(sessions): 修复会话文档与运行时线程的孤儿问题**
    - **内容**: 修复了数据一致性问题。某些场景下，会话的“文档”和“运行时线程”会相互丢失引用，导致会话丢失无法恢复。PR 重新梳理了所有权关系，并修复了历史遗留的孤儿问题。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6640`

10. **[#6619] fix(tools): 为工具输出设定统一的可恢复大小预算**
    - **内容**: 修复了一个令开发者非常困惑的 Bug：`cargo test` 等命令的输出被截断，而且丢掉的是末尾的**失败摘要和错误信息**。PR 引入了更智能的预算机制，优先保留关键的错误信息。
    - **链接**: `https://github.com/Hmbown/Codewhale/pull/6619`

## 功能需求趋势

- **网络稳定性与可配置性**: 社区对网络问题的容忍度正在降低。硬编码的超时和重试参数成为众矢之的，将容错参数暴露给用户进行配置是当前最迫切的需求之一。
- **性能优化**: 随着项目规模增长，启动和操作体验的性能问题开始凸显。对大型会话列表的优化（#6646）成为社区关注焦点。
- **模型支持扩展**: 用户不满足于仅支持头部模型，对长尾模型和替代服务商（如 Tsubasa）的兼容性需求开始出现。
- **UI/UX 精细化**: 在功能基本完备后，社区开始关注细节体验，如文本渲染、按钮样式、信息层级展示等，表明产品正在走向成熟期。
- **架构解耦**: 通过 `FEAT-029` 系列 issue 可以看出，将核心功能从 TUI 中分离出来，使其可以赋能 CLI、Web 等多种前端，是项目发展的明确长期趋势。

## 开发者关注点

- **`main` 分支 CI 门禁失效**: Windows 平台测试失败（#6698, #6702），这是一个需要立即解决的阻碍性问题，否则会阻塞所有开发工作。
- **网络故障容错性不足**: 核心开发者发现 SSE 请求在建立阶段遇到网络故障时完全没有重试能力（#6699），这是一个需要紧急修复的架构缺陷。
- **UI 渲染稳定性**: 多个 UI 渲染 Bug（#6697, #6704）被报告，虽然不影响核心功能，但严重影响了产品印象。这些 Bug 可能在特定终端或长时间运行后触发，需要仔细排查。
- **配置灵活性**: 开发者和运维人员抱怨缺乏对网络超时等底层参数的配置能力（#6700），这限制了产品在复杂网络环境下的布署能力。
- **跨平台与终端兼容性**: Mac 和 Linux 上均暴露出不同的 UI 问题（Mac 光标显示异常 #6545，Linux 背景颜色异常 #6704），表明跨终端模拟器的测试覆盖仍有不足。
- **后向兼容性**: `opencode-zen` 模型的兼容性失败（#6705）提醒维护者，硬编码的模型列表需要定期更新，或者切换为更动态的注册机制，以避免“支持”但不可用的尴尬局面。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*