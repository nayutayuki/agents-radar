# AI CLI 工具社区动态日报 2026-09-02

> 生成时间: 2026-09-02 00:30 UTC | 覆盖工具: 9 个

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

好的，作为专注于 AI 开发工具生态的资深技术分析师，我已根据您提供的 2026-09-02 各工具社区动态摘要，为您生成一份横向对比分析报告。

---

### AI CLI 开发工具生态横向对比分析报告 (2026-09-02)

#### 1. 生态全景

当前 AI CLI 工具生态正处于 **“能力拓展 vs. 稳定性瓶颈”的激烈碰撞期**。一方面，各工具正密集引入新模型（如 Claude Fable 5.1）、新功能（如 Vim 模式增强、MCP 集成）和新的安全机制（如沙箱、权限分级），整体呈现向“全功能开发环境”演进的趋势。另一方面，**MCP 协议兼容性、Windows 平台稳定性、GPU 资源管理、以及数据持久化**成为普遍性痛点，暴露了社区在快速迭代中对基础架构和跨平台兼容性投入的不足。整体来看，工具间的功能同质化初现，差异化竞争正从“模型能力”转向“**生态集成深度**”和“**开发者体验精细化**”。

#### 2. 各工具活跃度对比

| 工具名称 | 今日 Issues 数 (Top 10) | 今日重要 PR 数 | 今日 Release 情况 | 社区热度 (评论/点赞) |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 10 | 1 | 1 个正式版 (v2.1.258) | 高 (多个 Issue 超 10 条评论) |
| **OpenAI Codex** | 10 | 10 | 1 个正式版 (v0.152.1) + 3 个 Alpha | 极高 (有 Issue 达 58 👍) |
| **Gemini CLI** | 10 | 10 | 1 个 Preview 版 (v0.59.0-preview.0) | 中高 (多个 P1 Bug 活跃) |
| **GitHub Copilot CLI** | 10 | 0 | 1 个正式版 (v1.0.83-1) | 高 (内存泄漏问题集中爆发) |
| **Kimi Code CLI** | 2 | 4 | 1 个正式版 (v1.50.0) | 低 (社区较为沉寂) |
| **OpenCode** | 10 | 10 | 1 个正式版 (v1.18.26) | 极高 (有 Issue 达 128 条评论) |
| **Pi** | 10 | 9 | 0 | 高 (多个 Bug 和 Feature 讨论深入) |
| **Qwen Code** | 10 | 10 | 1 个驱动更新 (cua-driver-rs v0.20.3) | 中高 (TUI 迁移和权限变更争议大) |
| **DeepSeek TUI** | 10 | 10 | 0 | 中 (集中在 Bug 修复和细节打磨) |

**分析**: **OpenCode** 和 **OpenAI Codex** 社区最为活跃，Issue 讨论热烈，PR 数量多，版本迭代快。**Kimi Code CLI** 社区动态相对冷清，与项目可能处于转型期有关。**GitHub Copilot CLI** 和 **Claude Code** 的社区热度高，但主要受重大 Bug（如内存泄漏、数据丢失）驱动，暴露了稳定性的隐忧。

#### 3. 共同关注的功能方向

多个工具的社区不约而同地聚焦于以下方向，表明这些是当前 AI CLI 工具的共性挑战：

- **模型兼容性与提供商支持**: **Claude Code**、**OpenAI Codex**、**Pi**、**Qwen Code** 等工具均出现与特定模型或提供商（如 Gemini、Grok、llama.cpp、OpenAI 兼容端点）的兼容性问题，包括 API 差异、参数错误、工具调用失败等。社区强烈要求**简化模型配置、提升自动发现能力**。
- **MCP 生态成熟度**: **Claude Code** (Schema 兼容性)、**OpenAI Codex** (进程泄漏、审批范围)、**Gemini CLI** (OAuth 认证)、**GitHub Copilot CLI** (协议版本不兼容) 均面临 MCP 集成带来的稳定性与协议兼容性问题。MCP 作为开放标准，其**标准化和互操作性**成为焦点。
- **终端 (TUI) 体验精细化**: **Claude Code** (Vim 光标形状)、**OpenAI Codex** (Vim 搜索/撤销/重做)、**Pi** (TUI 选择样式、动画)、**Qwen Code** (TUI 渲染层迁移)、**DeepSeek TUI** (焦点切换、工具状态可视化) 都在持续打磨 TUI 交互细节，**Vim 模式**和**视觉反馈**是高频需求。
- **安全与权限管理**: **Claude Code** (安全过滤器误报、权限旁路)、**Gemini CLI** (API Key 泄露、沙箱执行)、**OpenCode** (权限钩子未触发)、**Qwen Code** (权限语义变更) 都在探索更精细、更可靠的权限模型。**安全策略的精确性**和**沙箱隔离**是核心痛点。
- **Windows 平台稳定性**: **Claude Code** (数据丢失、协作连接失效)、**OpenAI Codex** (MCP 进程泄漏、远程控制重连循环)、**GitHub Copilot CLI** (权限问题) 在 Windows 上均出现严重稳定性问题，表明该平台是当前工具链中的**薄弱环节**。

#### 4. 差异化定位分析

尽管功能趋同，各工具在定位和路径上仍存在差异：

- **Claude Code / OpenAI Codex**: 作为**模型原厂 CLI**，深度绑定自家顶级模型，追求极致性能与体验，是技术标杆。其社区反馈直接反映了模型和新功能的落地效果。
- **GitHub Copilot CLI**: 背靠 **GitHub 生态**，与仓库、CI/CD 和代码审查深度集成，是“开发者工作流”的中心。其问题多与生态集成（如 BYOK、MCP 服务器）和环境兼容性（企业网络、PowerShell）相关。
- **Gemini CLI / Pi**: 强调**多模型兼容性**和**代理能力**。Gemini CLI 注重安全沙箱和子代理行为，Pi 则通过丰富的 PR 展现了强大的扩展性和 TUI 定制能力，社区贡献者活跃。两者目标用户均为对灵活性和底层控制有高要求的开发者。
- **OpenCode / Qwen Code**: 作为**开源社区驱动**的代表，迭代速度极快，社区参与度高。OpenCode 在剪贴板、模型发现等基础功能上社区反馈激烈，而 Qwen Code 则更侧重于本地化（如 DingTalk 集成）和底层架构（如 TUI 渲染层迁移、Agent协作）。
- **Kimi Code CLI / DeepSeek TUI**: 处于**转型或快速迭代期**。Kimi Code 正在向统一的 Kimi Code 品牌迁移，社区动态较少。DeepSeek TUI 则专注于打磨细节（如启动体验、国际化、编辑器状态）和修复 Bug，为下一版本冲刺做准备。

#### 5. 社区热度与成熟度

- **最活跃社区**: **OpenCode** 和 **OpenAI Codex**。前者 Issue 讨论量惊人，后者 PR 合并频繁，生态活力最强。
- **高热度但伴随阵痛**: **Claude Code** 和 **GitHub Copilot CLI**。社区规模大，但近期被重大 Bug（数据丢失、OOM 崩溃）所困扰，用户情绪波动较大，属于“增长中的烦恼”。
- **稳定迭代型**: **Pi** 和 **Gemini CLI**。社区讨论理性，PR 质量高，功能演进稳健，成熟度较高。
- **快速追赶型**: **Qwen Code** 和 **DeepSeek TUI**。版本迭代快，但社区规模相对较小，仍在解决基础架构和兼容性问题，处于爬坡阶段。

#### 6. 值得关注的趋势信号

- **MCP 标准化是“燃眉之急”**: 几乎所有工具都受到 MCP 集成问题的困扰，这已成为阻碍 AI 工具生态互联互通的最大障碍。**MCP 协议的标准化和兼容性测试将成为行业关键基础设施**。开发者应关注相关 RFC 和社区讨论，选择支持标准度高的工具。
- **“安全”从口号走向“代价”**: 安全过滤器误报、权限系统 Bug 频发，表明 AI 代理的安全策略正从“粗暴拦截”转向“精细化管理”。**开发者需要审查并参与构建更具弹性的安全模型**，否则将面临生产力与安全性的两难选择。
- **性能与资源消耗成为新瓶颈**: 多个工具报告了 CPU 占用过高、内存泄漏、GPU 进程崩溃等问题。**“无状态”的 API 调用模式正在被“有状态”的智能代理所取代，对计算资源的需求激增**。开发者在选用工具时，需关注其对本地资源的占用和优化情况。
- **“Vim 用户”是核心用户群**: 多个工具都在积极优化 Vim 模式体验，这表明**资深开发者是 AI CLI 工具的核心用户群**。他们不仅关注功能，更追求极致的“指尖效率”和终端控制感。任何提升终端体验的细节（如光标形状、搜索、宏）都值得投入。
- **平台之战：Windows 是“下一站”**: 几乎所有工具在 Windows 上均表现不佳，而 macOS 和 Linux 则相对稳定。这表明目前的 AI CLI 工具主要以类 Unix 生态为基础构建。**Windows 开发者工具链的兼容性优化，将是工具获取下一波主流用户的关键战场**。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

# Claude Code Skills 社区热点报告（截至 2026-09-02）

## 1. 热门 Skills 排行

以下按社区关注度（PR 评论数与讨论热度）排序，聚焦新增或重大改进的 Skills。

| 排名 | Skill / PR | 核心功能 | 社区讨论热点 | 状态 |
|------|-----------|---------|-------------|------|
| 1 | **document-typography** (#514) | 对 AI 生成文档进行排版质量控制：防止孤行、寡妇段落、编号错位等 | 用户普遍反映 AI 文档排版问题严重，该 Skill 直接解决痛点；讨论集中在如何覆盖更多排版规则 | 🔴 OPEN |
| 2 | **scnet-hpc** (#1615) | 通过 SSH + Slurm 工作流操作 SCNet HPC 集群，支持分区、内存、模块配置 | 社区对 HPC 场景需求强烈，但技能细节（如多集群兼容性）尚未完善 | 🔴 OPEN |
| 3 | **ODT 技能** (#486) | 创建、填充、读取、转换 OpenDocument 格式文件（.odt/.ods），支持模板填充 | 开源文档格式与 LibreOffice 生态的集成需求；讨论涉及 ODF 标准合规性 | 🔴 OPEN |
| 4 | **Hivemind 多智能体编排** (#1628) | 让 Claude Code 将机械化工作委托给免费模型（opencode）执行，保持规划/审查/合并角色 | 零成本多智能体协作的创意获得高关注，但安全性（代码执行管控）是讨论焦点 | 🔴 OPEN |
| 5 | **self-audit 推理质量门** (#1367) | 交付前自动进行机械文件验证 + 四维度推理审核（伤害严重性优先级） | 用户对 AI 输出质量缺乏信任，该 Skill 试图建立可审计的防错机制；讨论涉及“过度检查”对 token 的消耗 | 🔴 OPEN |
| 6 | **testing-patterns** (#723) | 完整测试技能，覆盖测试哲学、单元测试、React 组件测试、E2E 测试等 | 测试生成是开发者高频需求，社区希望扩展更多框架（如 Playwright、Cypress）支持 | 🔴 OPEN |
| 7 | **ServiceNow 平台技能** (#568) | 涵盖 ITSM、ITOM、SecOps、ITAM、FSM、CSDM 等 ServiceNow 全模块 | 企业级 IT 管理场景需求旺盛，但技能体量过大（可能影响上下文窗口），讨论优化方案 | 🔴 OPEN |
| 8 | **Pyxel 复古游戏开发** (#525) | 基于 Pyxel 引擎的像素风游戏开发，支持“写→运行→截图→迭代”循环 | 创意编程社区反响积极，但技能依赖外部 MCP 服务器，稳定性存疑 | 🔴 OPEN |

## 2. 社区需求趋势

从 Issues 排行榜（按评论数）可提炼出以下核心需求方向：

- **安全与信任边界**（#492，43 条评论）：社区技能被分发在 `anthropic/` 命名空间下，存在冒充官方技能的风险。用户要求更清晰的来源标识和权限隔离机制。
- **组织级技能共享**（#228，16 条评论）：企业用户迫切需要技能的组织内分享功能，而非手动下载/上传。需求指向“技能市场”或“团队库”。
- **技能评估工具链修复**（#556，12 条评论）：`run_eval.py` 在 Windows 上触发率始终为 0%，导致优化循环失效。该问题关联多个 PR 和 Issue，是当前技能创作体验的**最大障碍**。
- **技能重复安装**（#189，6 条评论）：`document-skills` 和 `example-skills` 插件内容重复，浪费上下文窗口。社区要求插件清理和去重策略。
- **上下文窗口效率**（#1487，4 条评论）：`claude-api` 技能单次注入 ~156K tokens，耗尽上下文。用户呼吁技能设计应更“轻量”，按需加载。
- **新技能提案**：`compact-memory`（符号化记忆表示，#1329）、`agent-governance`（AI 代理安全模式，#412）、`reasoning quality gate`（推理质量流水线，#1385）等，均反映出社区对**可审计、可控制、高效率**的 AI 代理行为的追求。

## 3. 高潜力待合并 Skills

以下 PR 评论活跃、功能完整，但尚未合并，有望近期落地：

| PR | 技能 | 亮点 | 合并障碍 |
|----|------|------|---------|
| [#1298](https://github.com/anthropics/skills/pull/1298) | skill-creator 修复 | 修复 `run_eval.py` 的 0% recall 问题，同时解决 Windows 流读取、触发器检测等 | 依赖多个底层模块，测试覆盖不足 |
| [#514](https://github.com/anthropics/skills/pull/514) | document-typography | 解决 AI 文档排版顽疾，代码简洁，效果立竿见影 | 需要与现有 PDF/DOCX 技能协调，避免冲突 |
| [#1615](https://github.com/anthropics/skills/pull/1615) | scnet-hpc | 面向 HPC 科研用户，填补技能空白 | 需提供更多集群配置示例和文档 |
| [#1628](https://github.com/anthropics/skills/pull/1628) | Hivemind | 零成本多智能体架构，创新性强 | 安全审查（代码执行委托）和权限模型需明确 |
| [#1367](https://github.com/anthropics/skills/pull/1367) | self-audit | 通用推理质量门，可集成到任何项目 | 可能增加额外 token 开销，需提供性能基准 |
| [#723](https://github.com/anthropics/skills/pull/723) | testing-patterns | 覆盖测试全栈，实用性强 | 需要补充更多框架支持和配置示例 |

## 4. Skills 生态洞察

**当前社区最集中的诉求是：提升技能创作与评估工具链的可靠性，同时建立安全、轻量、可共享的技能生态，使技能真正成为可信任的 AI 能力模块。** 具体表现为：技能评估工具（`run_eval.py`）在 Windows 上完全不可用（#556、#1298、#1099、#1050），命名空间安全漏洞（#492），以及上下文窗口爆炸（#1487）等“基础设施级”问题，正在阻碍社区从“尝鲜”走向“生产级”使用。

---

好的，各位开发者，以下是 **2026年9月2日** 的 Claude Code 社区动态日报。

---

### 📰 今日速览

今日最重磅的消息是 **Claude Code v2.1.257 发布，正式引入 Fable 5.1 模型**，并推出了全新的时间格式自定义设置。同时，v2.1.258 紧急修复了 macOS 12 的启动问题，确保了旧系统的兼容性。社区方面，关于 MCP 服务器输出 Schema 兼容性的问题引发了广泛讨论，用户对模型更新和终端体验优化的呼声依然很高。

---

### 🚀 版本发布

*   **v2.1.258 (紧急修复版)**
    *   **修复**: 解决了 macOS 12 (Monterey) 上无法启动的问题（v2.1.255 引入的回归 bug）。
    *   **修复**: 修复了远程和定时任务因权限批准消息重试导致“user messages must have non-empty content”错误而失败的问题。
    *   [查看发布详情](https://github.com/anthropics/claude-code/releases/tag/v2.1.258)

*   **v2.1.257 (功能更新)**
    *   **新模型**: 新增 **Claude Fable 5.1** (`claude-fable-5-1`) 模型，并设为默认模型。支持 100 万上下文，定价为每百万输入 Token $10 / 每百万输出 Token $50，缓存读取仅 $0.25/Mtok。
    *   **新设置**: 新增 `timeFormat` 和 `timeZone` 设置，支持 12 小时制、24 小时制、24小时 UTC 或自定义 strftime 格式，用于显示会话结束时间。
    *   [查看发布详情](https://github.com/anthropics/claude-code/releases/tag/v2.1.257)

---

### 🔥 社区热点 Issues

1.  **MCP 服务器兼容性问题 (Issue #86142)**
    *   **重要性**: ⭐⭐⭐⭐⭐ 这是一个**严重 Bug**。使用 `draft-07` 输出 Schema 的 MCP 服务器会完全无法使用，被客户端以“不支持的方言”为由拒绝。这是 MCP 功能的一个关键阻塞点，影响大量工具集成。
    *   **社区反应**: 41 条评论，13 个 👍。社区高度关注，急切等待 Anthropic 修复。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/86142)

2.  **GitHub Connector 在 Cowork 模式中失效 (Issue #61682)**
    *   **重要性**: ⭐⭐⭐⭐⭐ 一个持续了 3 个多月的 Bug。Windows 11 用户报告，GitHub 连接器显示为“已连接”，但在 Cowork 协作模式下不暴露任何工具，导致协作功能无法正常使用。
    *   **社区反应**: 31 条评论，24 个 👍。用户反馈强烈，表明该问题对 Windows 用户的工作流影响很大。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/61682)

3.  **Windows 自动更新后数据丢失 (Issue #53717)**
    *   **重要性**: ⭐⭐⭐⭐⭐ **数据丢失**是最高优先级的问题。Windows 版 Claude Code 桌面应用在自动更新后，会话历史消息内容全部丢失，但侧边栏仍显示会话列表。内容未持久化到 JSONL 文件。
    *   **社区反应**: 15 条评论，9 个 👍。用户对数据丢失表示担忧，此问题已被关闭，但影响深远。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/53717)

4.  **Vim 模式光标形状支持 (Issue #32469)**
    *   **重要性**: ⭐⭐⭐⭐ 一个**高赞功能请求**。用户希望在启用 Vim 模式时，光标能根据 Insert 和 Normal 模式自动切换形状（如竖线/方块），以提升终端编辑体验。
    *   **社区反应**: 5 条评论，但获得了高达 **42 个 👍**，表明这是许多 Vim 用户的强烈刚需。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/32469)

5.  **Fable 5.1 需要不稳定版本 (Issue #91345)**
    *   **重要性**: ⭐⭐⭐⭐ 与今日发布直接相关。用户报告称，使用最新发布的 Fable 5.1 模型需要切换到 Claude Code 的 unstable 发布通道，增加了使用门槛。
    *   **社区反应**: 3 条评论。来自早期采用者的反馈，提醒 Anthropic 应简化模型切换流程。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/91345)

6.  **Auto Mode 缓存块导致 API 400 错误 (Issue #84673)**
    *   **重要性**: ⭐⭐⭐⭐ 一个**回归 Bug**。自动模式分类器在构建请求时产生了 5 个 `cache_control` 块，导致 API 返回 400 错误，最终错误信息被掩盖为“模型暂时不可用”。
    *   **社区反应**: 3 条评论。此问题影响自动模式用户，错误信息不直观，增加了排查难度。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/84673)

7.  **Bedrock 上的 Token 计数问题导致高成本 (Issue #86628)**
    *   **重要性**: ⭐⭐⭐⭐ **成本问题**。在 Bedrock 应用推理配置文件上，Claude Code 的 Token 计数机制为每个上下文项发起一次计费推理调用，导致非预期的成本激增。
    *   **社区反应**: 3 条评论。此问题对使用 Bedrock 的企业用户影响较大，需要关注优化。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/86628)

8.  **权限旁路设置失效 (Issue #75235)**
    *   **重要性**: ⭐⭐⭐ 一个**回归 Bug**。Windows 桌面版中，`settings.json` 里的 `permissions.defaultMode=bypassPermissions` 设置不再生效，导致用户无法绕过权限提示。
    *   **社区反应**: 4 条评论。虽然讨论不多，但影响使用体验和工作流效率。
    *   [查看 Issue](https://github.com/anthropics/claude-code/issues/75235)

9.  **网络安全过滤器误报潮 (Issues #757XX, #755XX, #753XX)**
    *   **重要性**: ⭐⭐⭐⭐ 一组**系统性问题**。大量报告（超过 20 个）指出，Claude Code 的网络安全过滤器在对合法硬件调试、Android 逆向工程、网络抓包等场景中产生了大量误报，并直接中断会话。
    *   **社区反应**: 虽然这些 Issue 已被关闭（标记为重复），但问题集中爆发，表明模型的安全策略存在过于严格、误伤率过高的问题，严重影响开发者进行底层或安全研究。
    *   [查看相关 Issue 示例](https://github.com/anthropics/claude-code/issues/75792)

10. **Ralph-Wiggum 插件安全强化 (PR #78371)**
    *   **重要性**: ⭐⭐⭐ 虽然是 PR，但体现了社区对**安全操作**的重视。该 PR 旨在强化 `ralph-wiggum` 插件，防止无限循环、无授权发布等风险。
    *   **社区反应**: 1 条评论，0 个 👍。讨论较少，但反映了社区对插件安全性的关注和贡献。
    *   [查看 Pull Request](https://github.com/anthropics/claude-code/pull/78371)

---

### 💻 重要 PR 进展

*   **PR #78371: `ralph-wiggum` 插件安全强化**
    *   **功能**: 为 `ralph-wiggum` 插件增加了循环边界、推送/发布守卫和停止钩子修复，防止其在自动化循环中造成意外发布或无限迭代。
    *   [查看 Pull Request](https://github.com/anthropics/claude-code/pull/78371)

*(注：过去24小时内仅有一条 PR 更新，但该 PR 的议题——插件安全——是社区持续关注的方向。)*

---

### 📈 功能需求趋势

从近期 Issues 中可以提炼出以下社区最关注的几个方向：

1.  **Vim 体验优化**: 对光标形状、编辑模式切换等细节的追求，表明 Vim 用户在 Claude Code 用户群中占比较高，且对终端体验有极致要求。
2.  **模型兼容性与易用性**: 无论是 Fable 5.1 需要不稳定版本，还是 MCP 的 Schema 兼容性问题，社区都希望新模型、新功能上线时，能拥有更平滑、更兼容的体验。
3.  **MCP 生态成熟度**: MCP 服务器的兼容性问题是当前的最大痛点，尤其是 Schema 标准的支持。社区期待 Anthropic 能提供更稳定、更开放的 MCP 标准。
4.  **安全功能的精确性**: 网络安全过滤器的误报潮表明，现有的安全策略过于“一刀切”，社区希望 Anthropic 能提供更精细、可配置的安全策略，减少对合法开发工作的干扰。

---

### 🛠️ 开发者关注点

*   **痛点**:
    *   **数据丢失与持久化**: Windows 自动更新后的数据丢失问题，让开发者对数据安全性感到担忧。
    *   **协作功能稳定性**: 特别是 Windows 平台下 GitHub Connector 在 Cowork 模式中的失效，严重影响了团队协作效率。
    *   **成本控制**: 在 Bedrock 等自定义推理配置上，意外的 Token 计费行为引发了开发者对成本透明度的关注。
    *   **安全拦截的误报**: 网络安全过滤器在合法工作中的误报，让开发者感到沮丧，认为系统过于“神经质”。

*   **高频需求**:
    *   **更精细的权限控制**: 用户希望绕过权限提示的设置能稳定工作，并期待更灵活的安全策略。
    *   **更强的终端/TUI 体验**: 支持 Vim 模式下的光标形状变化，是来自资深用户群体的明确信号。
    *   **更稳定的模型切换**: 用户希望在不使用 unstable 版本的情况下，也能体验最新的模型。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报 | 2026-09-02

---

## 今日速览

过去 24 小时，Codex 发布了 **v0.152.1** 补丁修复及三个 **v0.153.0-alpha** 预发布版，重点改进了 Vim 模式搜索、限流提示及 Guardian 审批。社区讨论集中在 **Windows 平台稳定性**（MCP 进程反复启动、远程控制重连循环）和 **配额消耗异常** 两大热点，共有 10 余个相关 Issue 持续活跃。同时，一批针对 MCP 安全、性能预热的 PR 已合并，为后续版本铺平道路。

---

## 版本发布

### 正式版
- **[rust-v0.152.1](https://github.com/openai/codex/releases/tag/rust-v0.152.1)**  
  **Bug Fix**：Guardian 审批现在正确遵循通过模型元数据提供的 Node REPL 策略。

- **[rust-v0.152.0](https://github.com/openai/codex/releases/tag/rust-v0.152.0)**  
  **新功能**：
  - Vim 模式支持在草稿中使用 `/` 和 `?` 搜索，高亮匹配，并可通过 `n`/`N` 重复导航。
  - 限流横幅现在提供“检查用量”、“管理积分”、“重置限制”、“管理计划”等快捷操作。
  - 终端 UI 和 `codex exec` 相关改进（描述截断，详情见 Changelog）。

### 预发布版
- **rust-v0.153.0-alpha.4 / .2 / .1**  
  三个 Alpha 版本，主要供内部测试，未包含详细更新说明。

---

## 社区热点 Issues（10 个）

| # | Issue | 摘要 | 状态 | 热度 |
|---|-------|------|------|------|
| 1 | **[#14630](https://github.com/openai/codex/issues/14630) - TUI 语音转录** | 建议在 CLI 中集成 OpenAI 语音转录模型，替代当前低质量的听写模式。 | OPEN | 58 👍 / 22 评论 |
| 2 | **[#38754](https://github.com/openai/codex/issues/38754) - Windows 本地 MCP 服务器反复生成且未回收** | 每次对话轮次都会启动新的 stdio MCP 进程，旧进程不释放，导致资源泄漏。 | OPEN | 3 👍 / 19 评论 |
| 3 | **[#39954](https://github.com/openai/codex/issues/39954) - Windows + Android 远程控制进入重连循环** | 远程连接成功后立即断开并重连，无法正常使用。 | OPEN | 0 👍 / 18 评论 |
| 4 | **[#40782](https://github.com/openai/codex/issues/40782) - macOS 更新后 UI 文字变模糊** | 最新版桌面应用在 macOS 上全局 UI 文字变细且模糊，影响阅读。 | OPEN | 4 👍 / 12 评论 |
| 5 | **[#41433](https://github.com/openai/codex/issues/41433) - GitHub 连接器“标记就绪”操作失败** | 查询 `Repository.fullDatabaseId` 时字段不存在，导致 Draft PR 无法转为 Ready for review。 | OPEN | 7 👍 / 11 评论 |
| 6 | **[#41220](https://github.com/openai/codex/issues/41220) - 异常配额消耗和记账不一致** | 用户发现订阅配额或购买积分消耗速度远超往常，且无法从日志中对应。 | OPEN | 6 👍 / 11 评论 |
| 7 | **[#41088](https://github.com/openai/codex/issues/41088) - Windows 更新后本地执行无法启动** | 更新至 26.820.7780.0 后，所有本地 shell 执行均失败。 | OPEN | 0 👍 / 11 评论 |
| 8 | **[#38417](https://github.com/openai/codex/issues/38417) - Linux/WSL2 中 `codex-code-mode-host` 崩溃** | 0.147.0 版本在执行 shell 时触发 `SIGTRAP`，回退至 0.146.1 正常。 | OPEN | 0 👍 / 11 评论 |
| 9 | **[#39121](https://github.com/openai/codex/issues/39121) - Windows 桌面更新后历史项目消失** | 更新后仅显示新创建的项目，旧项目虽在磁盘但无法在 UI 中恢复。 | OPEN | 1 👍 / 11 评论 |
| 10 | **[#2379](https://github.com/openai/codex/issues/2379) - TUI 中撤销/重做输入** | 请求在提示词编辑器中支持 Cmd+Z / Shift+Cmd+Z 撤销/重做。 | OPEN | 32 👍 / 10 评论 |

---

## 重要 PR 进展（10 个）

所有以下 PR 均于 2026-09-01 合并，由 `copyberry[bot]` 提交。

| # | PR 标题 | 核心内容 | 链接 |
|---|---------|---------|------|
| 1 | **Expose model settings in app-server thread metadata** | 在 app-server 的 `Thread` 对象中暴露 `model` 和 `reasoningEffort` 字段，便于工具链感知当前模型配置。 | [PR #42151](https://github.com/openai/codex/pull/42151) |
| 2 | **Support remote marketplaces in the plugin CLI** | 允许 `codex plugin list` 显示远程插件目录条目，支持添加/删除远程插件。 | [PR #42150](https://github.com/openai/codex/pull/42150) |
| 3 | **Skip Guardian reviews in Full Access** | Full Access 模式下跳过 Guardian 审批，提升操作流畅性。 | [PR #42147](https://github.com/openai/codex/pull/42147) |
| 4 | **Add early rate-limit warnings for Plus and Team plans** | 当 Plus/Team 用户用量剩余不足 50% 时提前警告，其他计划维持原有阈值。 | [PR #42142](https://github.com/openai/codex/pull/42142) |
| 5 | **Add redo support to Vim composer history** | Vim 普通模式下 `Ctrl+R` 可重做上一次撤销的编辑，并新增 `vim_normal_redo` 配置。 | [PR #42140](https://github.com/openai/codex/pull/42140) |
| 6 | **Prewarm shell snapshots for eligible turns** | 在轮次开始后异步预捕获 shell 快照，减少后续命令的启动延迟。 | [PR #42137](https://github.com/openai/codex/pull/42137) |
| 7 | **Fix relative MCP server spawning on macOS** | 解决 macOS 上因 Rust `posix_spawnp` 历史问题导致相对路径 MCP 服务器启动失败。 | [PR #42117](https://github.com/openai/codex/pull/42117) |
| 8 | **Scope session MCP approvals to app account links** | MCP 工具审批键现在包含 `link_id`，避免不同账号下同一工具的审批被错误复用。 | [PR #42133](https://github.com/openai/codex/pull/42133) |
| 9 | **Bound Git root discovery for metadata enrichment** | 限制 Git 根目录发现的时间与资源，防止阻塞 Tokio 线程池及延迟关闭。 | [PR #42132](https://github.com/openai/codex/pull/42132) |
| 10 | **Refine hook activity rendering in the TUI** | 优化 TUI 中钩子活动状态的显示，将其移到底部活动区域，避免遮挡对话视图。 | [PR #42118](https://github.com/openai/codex/pull/42118) |

---

## 功能需求趋势

从近期 Issues 和 PR 中可以提炼出社区最关注的 **五大方向**：

1. **TUI/编辑器增强**  
   - 语音转录（#14630）、撤销/重做（#2379）、Vim 搜索增强（已在 v0.152.0 实现）。  
   - 社区对终端交互体验的优化需求持续高涨。

2. **远程控制与移动端**  
   - 文件上传支持（#37074）、移动端审批卡片显示（#39346）、远程控制重连稳定性（#39954）。  
   - 跨设备无缝协作是当前用户痛点。

3. **配额与订阅管理**  
   - 异常消耗（#41220）、限流警告提前（PR #42142）、订阅后限额未更新（#36246）。  
   - 用户对配额透明度和警告及时性要求强烈。

4. **插件与 MCP 生态**  
   - 远程市场插件支持（PR #42150）、MCP 审批范围细化（PR #42133）、OAuth 刷新协调（PR #42128）。  
   - 插件平台正在快速构建，安全与权限模型是核心。

5. **性能与稳定性**  
   - Windows 下 MCP 进程泄漏（#38754）、Git 根目录发现阻塞（PR #32132）、Shell 快照预热（PR #42137）。  
   - 尤其 Windows 平台问题成为当前重中之重。

---

## 开发者关注点

基于近期反馈，以下问题反复出现，需优先关注：

- **Windows 平台兼容性**：多个 Issue 报告 Windows 桌面应用更新后出现本地执行失败、历史项目消失、MCP 进程失控、UI 性能下降（如“Open in”菜单延迟）等。请开发者确保 Windows 环境下的全面回归测试。
- **配额与记账异常**：多位用户报告订阅额度消耗速度异常，且无法通过本地日志验证。建议 OpenAI 提供更细粒度的用量追踪机制，并修复可能的记账 Bug。
- **远程控制连接稳定性**：Windows + Android 组合出现重连循环，Mobile 端文件上传缺失，限制移动办公场景。建议尽快修复重连逻辑并补齐基础功能。
- **UI 与渲染问题**：macOS 更新后文字模糊、长回复滚动跳跃、元素缺失等影响日常使用，需关注跨平台渲染引擎的兼容性。
- **Guardian 审批策略**：Full Access 模式已跳过审批（PR #42147），但仍有用户反馈 Node REPL 策略未被正确应用（已修复于 v0.152.1）。建议持续完善策略执行引擎。

---

*以上数据截至 2026-09-02 08:00 UTC，基于 GitHub 仓库 [openai/codex](https://github.com/openai/codex) 公开信息整理。*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，这是为您生成的 2026-09-02 Gemini CLI 社区动态日报。

---

# Gemini CLI 社区动态日报 | 2026-09-02

## 今日速览

今日社区动态集中于安全加固与核心稳定性修复。`v0.59.0-preview.0` 发布，修复了一个核心崩溃问题。同时，多项 PR 正着力解决符号链接处理、API 密钥泄露和子代理行为异常等关键痛点，社区对代理可靠性和安全性的关注度持续上升。

## 版本发布

### v0.59.0-preview.0 发布
- **核心修复**: 修复了一个重要的核心崩溃问题 (`fix(core): prevent ...`)，具体细节正在更新中。
- **版本号更新**: 已发布 `v0.59.0-nightly.20260901.g0bd1d4397` 夜间构建版本。
- **发布地址**: [https://github.com/google-gemini/gemini-cli/releases/tag/v0.59.0-preview.0](https://github.com/google-gemini/gemini-cli/releases/tag/v0.59.0-preview.0)

## 社区热点 Issues

以下为今日最值得关注的 10 个 Issue，主要聚焦于代理行为、安全性和稳定性问题。

1.  **[#22323](https://github.com/google-gemini/gemini-cli/issues/22323) 子代理超时被误报为“目标达成”** (P1, Bug)
    - **重要性**: 核心逻辑错误。当子代理因达到最大轮次 (`MAX_TURNS`) 而被中断时，系统错误地报告为“成功”，这会误导用户以为任务完成，而实际并未执行分析。
    - **社区反应**: 13条评论，2个赞，讨论热烈，已标记为需要重新测试。

2.  **[#19873](https://github.com/google-gemini/gemini-cli/issues/19873) 利用模型的 Bash 亲和性：零依赖 OS 沙箱与意图路由** (P2, Enhancement)
    - **重要性**: 一个重要的功能增强提案。旨在利用模型原生能力操作 POSIX 工具，同时通过沙箱保证安全。这可能是未来安全执行策略的关键方向。
    - **社区反应**: 9条评论，1个赞，社区对此安全与性能平衡的设计思路讨论积极。

3.  **[#21409](https://github.com/google-gemini/gemini-cli/issues/21409) 通用代理 (Generalist agent) 无响应挂起** (P1, Bug)
    - **重要性**: 严重影响用户体验的核心问题。当 CLI 调用通用代理时，任何操作（如创建文件夹）都会导致无限期挂起，用户不得不手动取消。
    - **社区反应**: 8条评论，8个赞，是社区反馈最强烈的 Bug 之一，用户普遍遇到此问题。

4.  **[#25166](https://github.com/google-gemini/gemini-cli/issues/25166) Shell 命令执行完成后卡死在“等待输入”** (P1, Bug)
    - **重要性**: 严重阻碍工作流。一个简单的 CLI 命令完成后，代理仍显示为等待输入状态，导致无法继续后续操作。
    - **社区反应**: 4条评论，3个赞，复现率较高，开发者反馈强烈。

5.  **[#22745](https://github.com/google-gemini/gemini-cli/issues/22745) 评估 AST 感知文件读取的影响** (P2, Feature)
    - **重要性**: 探索性功能。通过 AST (抽象语法树) 感知技术精确读取代码，有望大幅减少 Token 消耗，提升代码理解和搜索效率。
    - **社区反应**: 7条评论，1个赞，是社区关注的性能优化方向。

6.  **[#26525](https://github.com/google-gemini/gemini-cli/issues/26525) 自动内存 (Auto Memory) 日志中增加确定性脱敏并减少日志量** (P2, Bug)
    - **重要性**: 安全与隐私问题。当前自动内存系统在将内容送入模型后才进行脱敏，存在潜在的数据泄露风险。
    - **社区反应**: 5条评论，社区对数据安全和隐私处理非常敏感。

7.  **[#21968](https://github.com/google-gemini/gemini-cli/issues/21968) Gemini 不会主动使用自定义技能和子代理** (P2, Bug)
    - **重要性**: 功能可用性问题。用户配置了 Git 和 Gradle 等技能，但 Gemini 除非被明确要求，否则不会主动调用，大大降低了技能扩展的价值。
    - **社区反应**: 6条评论，社区期望代理能更智能地自主决策使用工具。

8.  **[#21983](https://github.com/google-gemini/gemini-cli/issues/21983) 浏览器子代理在 Wayland 环境下失败** (P1, Bug)
    - **重要性**: 平台兼容性问题。在 Linux 的 Wayland 显示协议下，浏览器子代理无法正常工作，影响特定用户群体的使用。
    - **社区反应**: 4条评论，1个赞，对 Linux 用户影响较大。

9.  **[#20079](https://github.com/google-gemini/gemini-cli/issues/20079) 符号链接的 Agent 文件不被识别** (P2, Bug)
    - **重要性**: 配置管理问题。`~/.gemini/agents/` 目录下的符号链接文件无法被识别为 Agent，限制了用户灵活管理自定义 Agent 的能力。
    - **社区反应**: 4条评论，这是一个被忽视的配置管理痛点。

10. **[#24246](https://github.com/google-gemini/gemini-cli/issues/24246) 工具数量超过 128 个时触发 400 错误** (P2, Bug)
    - **重要性**: 扩展性瓶颈。当用户启用大量工具时，Gemini CLI 会因 API 限制而报错，限制了大规模工具集的使用场景。
    - **社区反应**: 3条评论，标记为需要更多信息，但已暴露出扩展性方面的问题。

## 重要 PR 进展

以下为今日 10 个重要的 PR，涵盖了安全、性能、平台兼容性等多个方面。

1.  **[#29115](https://github.com/google-gemini/gemini-cli/pull/29115) 强制配置文件路径的严格权限和所有权检查** (安全)
    - **内容**: 对 Windows 和 POSIX 系统的配置文件路径强制执行文件所有权和 ACL 验证，防止权限提升攻击。
    - **状态**: 开放中。

2.  **[#29158](https://github.com/google-gemini/gemini-cli/pull/29158) 清理 Chrome DevTools MCP 中硬编码的 API Key** (安全)
    - **内容**: 移除并清理了 `chrome-devtools-mcp` 组件中硬编码的 Google CrUX API 密钥，防止敏感凭证泄露。
    - **状态**: 开放中。

3.  **[#29163](https://github.com/google-gemini/gemini-cli/pull/29163) 修复在 Git 仓库中认证时的崩溃问题** (稳定性)
    - **内容**: 修复了在 macOS 等受限权限环境下，Gemini CLI 启动时因读取 Git 分支信息而崩溃的问题。
    - **状态**: 开放中。

4.  **[#28975](https://github.com/google-gemini/gemini-cli/pull/28975) 修复符号链接工作区根目录的 Glob 结果** (兼容性)
    - **内容**: 修复了当工作区根目录是符号链接（如 macOS 下的 `/tmp` 指向 `/private/tmp`）时，`glob` 查询返回空结果的问题。
    - **状态**: 开放中。

5.  **[#29116](https://github.com/google-gemini/gemini-cli/pull/29116) 缓解 NTFS 8.3 短文件名 (SFN) 路径问题** (兼容性)
    - **内容**: 改进了 Windows 下对 NTFS 8.3 短文件名（如 `git~1`）的路径处理，防止路径遍历和绕过安全检查。
    - **状态**: 开放中。

6.  **[#29117](https://github.com/google-gemini/gemini-cli/pull/29117) 强制 MCP OAuth 流程中的 Issuer 验证** (安全)
    - **内容**: 实现了 RFC 9207 标准，在 MCP 的 OAuth 流程中强制验证授权服务器身份，防止 Token 被路由到错误端点。
    - **状态**: 开放中。

7.  **[#29106](https://github.com/google-gemini/gemini-cli/pull/29106) 修复 SSE 流结束时不发送最后事件的问题** (稳定性)
    - **内容**: 修复了 SSE 解析器在流结束时丢失最后一个事件（如 `finishReason`）的问题，避免元数据丢失。
    - **状态**: 开放中。

8.  **[#29156](https://github.com/google-gemini/gemini-cli/pull/29156) 停止在 Shell 执行中清空用户 Git 配置** (Bug修复)
    - **内容**: 修复了近期引入的 Bug，该 Bug 导致所有 Shell 命令的 Git 配置被清空，使得 `user.name` 和 `user.email` 等信息丢失。
    - **状态**: 开放中。

9.  **[#29155](https://github.com/google-gemini/gemini-cli/pull/29155) 修复 BOM 编码文件的判空逻辑** (Bug修复)
    - **内容**: 修复了 `isEmpty()` 函数对 UTF-16/UTF-32 编码（带 BOM）的文件判空错误的问题，避免了错误的计划验证。
    - **状态**: 开放中。

10. **[#29151](https://github.com/google-gemini/gemini-cli/pull/29151) 修复技能优先级和激活状态的大小写敏感问题** (Bug修复)
    - **内容**: 修复了 `SkillManager` 在处理技能名称时的大小写不匹配问题，确保技能覆盖和激活能正确生效。
    - **状态**: 开放中。

## 功能需求趋势

从近期的社区动态来看，社区最关注的功能方向集中在以下三点：

1.  **代理行为与可靠性**: 社区强烈要求代理能更智能、更可靠。具体包括：子代理超时不应误报成功、通用代理不应挂起、代理应更积极地使用自定义技能和子代理。这反映了用户对“智能助手”的期望越来越高。
2.  **安全性与权限模型**: 安全问题是当前的重点。社区关注点包括：通过沙箱执行安全命令、对配置文件路径进行权限检查、防止 API Key 泄露、以及改进自动内存的脱敏机制。这体现了在 AI 自动化程度提高后，对安全边界的担忧。
3.  **性能与上下文管理**: 为了提升效率并控制 Token 消耗，社区对 AST 感知文件读取、精准的方法级代码提取等功能表现出浓厚兴趣。这旨在解决当前“暴力读取”带来的高 Token 消耗和低效问题。

## 开发者关注点

开发者反馈中的高频痛点主要集中在：

- **代理“假死”或“假成功”**: 无论是通用代理挂起，还是子代理超时被误报，都导致开发者对任务状态产生不信任，需要频繁人工干预。
- **Shell 执行体验不佳**: 命令执行完毕后卡住，以及 Git 配置被意外清空，都严重破坏了开发者的工作流，降低了 CLI 工具的实用性。
- **配置管理混乱**: 符号链接不被识别、工具数量过多导致报错，这些配置层面的问题增加了开发者的上手成本和使用障碍。
- **安全顾虑**: 硬编码 API key 泄露、自动内存脱敏时机不当等安全问题，让开发者对使用该工具进行敏感开发任务感到担忧。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区动态日报 | 2026-09-02

---

## 今日速览

- **v1.0.83-1 发布**：新增会话侧栏排序（最近/创建/名称/无），并支持企业管理员强制登录指定 GitHub 组织。同时 `/mcp config` 和 MCP 编辑体验得到改进。
- **内存泄漏问题集中爆发**：多个用户报告 Node.js 堆内存溢出（OOM）崩溃，分别发生在恢复长时间会话（#4664）和运行约 37 分钟后（#4686），涉及大量泄漏的 libuv 句柄，社区高度关注。
- **MCP 与 BYOK 集成问题频发**：MCP 初始化协议不兼容（#4525）、OAuth 后缺少 User-Agent 头（#4681）、BYOK 模型 ID 发送错误（#4680）以及本地 403 认证失败（#4414）等，显示 Copilot CLI 在自定义模型和服务接入方面仍需大量修复。

---

## 版本发布

### v1.0.83-1

**新增**
- 会话侧栏新增 **Recent**（最近）、**Created**（创建时间）、**Name**（名称）和经典的 **None**（无排序）四种排序方式，选择的排序会在重启后保持。
- 企业管理员可通过 `forceLoginOrgs` 托管设置，将登录限制在批准的 GitHub 组织内。

**改进**
- 优化了 `/mcp config` 命令以及 MCP 添加/编辑的交互流程。

---

## 社区热点 Issues（10 个最值得关注）

### 1. #4664 [OPEN] 恢复长时间会话时 JavaScript 堆内存溢出
**链接**：https://github.com/github/copilot-cli/issues/4664  
**标签**：`area:sessions`, `area:context-memory`  
**摘要**：当尝试恢复一个大型/长期存在的会话时，Copilot CLI 因 Node.js 堆内存耗尽而崩溃，发生在会话加载阶段，无法继续工作。  
**关注原因**：严重影响依赖长会话的高级用户，可能导致工作流完全中断。目前有 5 条评论，0 点赞。

### 2. #4525 [OPEN] v1.0.81-1 在成功发送 `server/discover` 后仍发送旧版 `initialize`，导致错误 -32022
**链接**：https://github.com/github/copilot-cli/issues/4525  
**标签**：`area:mcp`  
**摘要**：CLI 在连接 Python MCP SDK 2.0.0 的 stdio 服务器时，先发送现代 `server/discover` 探测，但随后又发送旧版 `initialize`，导致服务器返回 `-32022`。  
**关注原因**：MCP 协议版本兼容性问题，阻碍用户使用最新的 MCP 服务器。4 条评论。

### 3. #3688 [OPEN] 仓库级自定义代理的解析根目录不一致：代理基于 git root，技能和 .mcp.json 基于当前工作目录
**链接**：https://github.com/github/copilot-cli/issues/3688  
**标签**：`area:agents`, `area:configuration`  
**摘要**：三种仓库级自定义配置来源使用不同的基目录，导致配置发现混乱，例如自定义代理在 git 根目录下发现，而技能和 MCP 配置在工作目录下发现。  
**关注原因**：配置一致性是开发者的基本需求，该问题导致多仓库项目中的自定义行为不可预测。3 条评论，3 个 👍。

### 4. #4438 [OPEN] `disable-model-invocation: true` 使技能不可达，而非仅禁止模型调用
**链接**：https://github.com/github/copilot-cli/issues/4438  
**标签**：`area:agents`  
**摘要**：项目技能在 `SKILL.md` 中设置 `disable-model-invocation: true` 后，CLI 完全无法访问该技能——`copilot skill list` 能显示，但模型调用 `skill()` 工具返回 `Skill not found`。  
**关注原因**：设计意图是禁止模型自动调用，但仍应允许用户手动调用，但实际行为是错误的。3 条评论，6 个 👍。

### 5. #4681 [OPEN] MCP OAuth：成功登录后的 `initialize` 请求缺少 User-Agent 头，忽略自定义头部配置
**链接**：https://github.com/github/copilot-cli/issues/4681  
**标签**：`triage`  
**摘要**：当使用 HTTP/Streamable-HTTP 传输连接远程 MCP 服务器且需要 OAuth 时，底层 HTTP 客户端在 OAuth 令牌交换后的 `initialize` 请求中未发送 `User-Agent` 头，导致服务器可能拒绝请求。  
**关注原因**：影响企业级 MCP 服务器集成，可能导致 OAuth 流程完全失败。2 条评论。

### 6. #4680 [OPEN] CLI 向自定义 OpenAI 兼容端点发送错误的模型 ID，导致会话终止
**链接**：https://github.com/github/copilot-cli/issues/4680  
**标签**：`triage`  
**摘要**：使用自定义 OpenAI 兼容端点时（如模型名 `mimo-v2.5`），CLI 在 API 请求体中发送 `gpt-5.4-nano` 而非实际配置的模型名，导致请求失败，会话中断。  
**关注原因**：基本配置错误，严重破坏 BYOK 场景。2 条评论。

### 7. #4414 [CLOSED] BYOK 自定义提供商在请求到达提供商之前返回本地 403
**链接**：https://github.com/github/copilot-cli/issues/4414  
**标签**：`area:authentication`, `area:networking`, `area:models`  
**摘要**：自定义 OpenAI 和 Anthropic 兼容提供商的所有推理请求都失败，显示 `Authorization error, you may need to run /login`，但实际请求从未到达提供商。`/login` 也无济于事。  
**关注原因**：虽然已关闭，但反映了 BYOK 认证流程的深层问题，可能与其他开放问题相关。2 条评论，2 个 👍。

### 8. #4672 [OPEN] v1.0.82 回归：使用 BYOK 时 `/model` 命令报错 `Unknown command: /model`
**链接**：https://github.com/github/copilot-cli/issues/4672  
**标签**：`area:models`, `area:configuration`  
**摘要**：从 v1.0.81 开始，通过环境变量配置 BYOK 模型后，`/model` 命令失效，提示未知命令。用户无法在 Azure AI Foundry 等多模型环境中切换模型。  
**关注原因**：回归问题，影响所有 BYOK 用户。2 条评论，1 个 👍。

### 9. #4686 [OPEN] 运行约 37 分钟后 Node.js OOM 崩溃——31,965 个泄漏的异步 libuv 句柄（SEA 忽略 NODE_OPTIONS）
**链接**：https://github.com/github/copilot-cli/issues/4686  
**标签**：`triage`  
**摘要**：长期会话（约 37 分钟）后崩溃，报告 `FATAL ERROR: Reached heap limit`，泄漏了超过 3 万个 libuv 句柄。由于 SEA 单文件可执行模式，`NODE_OPTIONS` 被忽略，无法通过环境变量调整内存限制。  
**关注原因**：与 #4664 类似，但更严重——泄漏数量巨大，且平台限制使调节失效。1 条评论。

### 10. #4633 [OPEN] `view` 工具拒绝读取 8.6 KB 的文件，报告“文件太大无法一次性读取”
**链接**：https://github.com/github/copilot-cli/issues/4633  
**标签**：`triage`  
**摘要**：内置的 `view` 工具（VS Code 中显示为“Read”）在读取一个仅 8.6 KB 的多行 Markdown 文件时报错，提示文件太大。这显然是错误的阈值判断。  
**关注原因**：严重干扰日常文件查看，影响开发效率。0 条评论，但值得关注。

---

## 重要 PR 进展

**今日无合入或更新的 Pull Request。**

---

## 功能需求趋势

从近期 Issues 中提炼出社区最关注的功能方向：

- **会话管理与侧栏增强**：用户希望支持更多排序方式（已在新版本中部分实现）、文件树浏览器（#3971）、以及持久化的路径级写权限批准（#4682）。
- **MCP 服务器兼容性与稳定性**：包括协议版本协商（#4525）、OAuth 流程改进（#4681）、超时预算控制（#4678）等，表明社区正在积极将 Copilot 与各种 MCP 服务器集成。
- **BYOK 与自定义模型端点的可靠性**：模型 ID 错误、认证失败、/model 命令回归等问题集中爆发，说明 BYOK 功能仍处于早期阶段，需要更多测试和修复。
- **企业环境适应性**：PowerShell ConstrainedLanguage 模式（#4683）、sandbox 禁用后仍报错（#4679）等，反映出企业用户对安全策略和合规性有更高要求。
- **子代理并发控制**：#4688 提出静态限制无法感知机器负载，容易导致主机饱和和 UI 冻结，需要一个更智能的调度机制。

---

## 开发者关注点

- **内存泄漏与崩溃**：OOM 崩溃是当前最严重的痛点，多个用户报告，且涉及会话恢复和长期运行场景。尽管新版本已发布，但尚未看到针对此问题的修复。
- **MCP 初始化与版本兼容**：新旧协议混合使用导致连接失败，用户需要手动降级或等待修复，阻碍了 MCP 生态的采用。
- **配置分散与不一致**：仓库级自定义代理/技能/MCP 的基目录不统一，导致开发者难以预测行为，增加了调试成本。
- **技能可见性 bug**：`disable-model-invocation` 标志导致技能完全不可用，违背了“仅禁止模型调用”的设计意图，需要紧急修复。
- **企业限制下的兼容性**：Windows 约束语言模式、AppLocker 等环境下的错误提示污染了正常输出，影响了自动化脚本和 CI/CD 集成。

---

*数据来源：GitHub Copilot CLI 仓库（github.com/github/copilot-cli），统计时间截至 2026-09-02 02:00 UTC。*

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

# Kimi Code CLI 社区动态日报 | 2026-09-02

## 今日速览

Kimi Code CLI 今日发布 **v1.50.0**，主要包含 shell 的废弃感知更新流程以及 kosong 依赖的版本升级。社区方面，两个历史 Issue 被关闭，分别涉及任务执行时无法编写下一轮 Prompt 及子任务调用卡死问题，表明开发者对异步任务编排与稳定性有持续关注。此外，4 个 PR 中有两个涉及迁移引导（kimi-cli → Kimi Code）和插件文档，提示项目正在向更统一的品牌和生态演进。

---

## 版本发布

### v1.50.0

- **核心变更**：
  - `feat(shell): deprecation-aware update flow with one-key migration to Kimi Code` – 新增 shell 中的废弃感知更新流程，支持一键迁移至 Kimi Code。
  - `fix(kosong): omit empty anthropic-beta header when no beta features declared` – 修复 kosong 组件在未声明 beta 功能时发送空 anthropic-beta 头部的问题。
  - `chore(release): bump kosong to 0.56.0` – 将 kosong 子项目升级至 0.56.0 版本。
- 相关 PR： [MoonshotAI/kimi-cli #2632](https://github.com/MoonshotAI/kimi-cli/pull/2632)（发布 PR）、[MoonshotAI/kimi-cli #2630](https://github.com/MoonshotAI/kimi-cli/pull/2630)（迁移功能）、[MoonshotAI/kimi-cli #2580](https://github.com/MoonshotAI/kimi-cli/pull/2580)、[MoonshotAI/kimi-cli #2581](https://github.com/MoonshotAI/kimi-cli/pull/2581)

---

## 社区热点 Issues

（过去24小时内更新的 Issue 共2条，已全部列出）

### 1. #1287 – [CLOSED] 执行任务时无法编写下一任务的 Prompt

- **作者**: XiaoPengYouCode | 创建: 2026-02-28 | 更新: 2026-09-01 | 评论: 1 | 👍: 0
- **摘要**: 当前任务执行期间，下一任务的 Prompt 输入框被锁定，无法提前编辑，影响连续任务编排效率。
- **为什么重要**: 该需求直接关联多步骤工作流场景，如代码审查、批量修改等，限制用户并行思维。已关闭但未明确解决方案，社区仍需关注后续是否引入非阻塞输入。
- [GitHub Issue #1287](https://github.com/MoonshotAI/kimi-cli/issues/1287)

### 2. #1292 – [CLOSED] 调用 Task 时有时会卡住

- **作者**: Wolido | 创建: 2026-03-01 | 更新: 2026-09-01 | 评论: 0 | 👍: 0
- **摘要**: 使用 kimi v1.16.0 时，在调用多个子 Task 时，某个子任务可能卡住无响应，平台为 Kimi Code，模型未指定，系统 Darwin arm64。
- **为什么重要**: 子任务卡死严重影响自动化流程稳定性，虽已关闭，但未公布根因修复版本，开发者需自行升级至最新版（v1.50.0）测试是否复现。
- [GitHub Issue #1292](https://github.com/MoonshotAI/kimi-cli/issues/1292)

---

## 重要 PR 进展

（过去24小时内更新的 PR 共4条，全部列出）

### 1. #2614 – [OPEN] docs(plugins): 记录插件安全与持久化数据

- **作者**: QIANLING-0831 | 创建: 2026-08-20 | 更新: 2026-09-01 | 评论: 0 | 👍: 0
- **摘要**: 纯文档 PR，明确插件契约（`plugin.json`、命令工具、`inject` 及安装路径 `~/.kimi/plugins/`），不涉及功能变更。
- **为什么重要**: 随着插件生态扩展，标准化的安全与数据持久化文档是第三方开发者接入的必要前提。
- [GitHub PR #2614](https://github.com/MoonshotAI/kimi-cli/pull/2614)

### 2. #2632 – [CLOSED] chore(release): bump kimi-cli to 1.50.0

- **作者**: sailist | 创建: 2026-09-01 | 更新: 2026-09-01 | 评论: 0 | 👍: 0
- **摘要**: 版本发布 PR，将版本号提升至 v1.50.0，同步更新 release notes 以及 `kimi-code` 包装器依赖。
- [GitHub PR #2632](https://github.com/MoonshotAI/kimi-cli/pull/2632)

### 3. #742 – [CLOSED] 添加 `$ list skills` 类似 codex 的功能

- **作者**: ZacharyZhang-NY | 创建: 2026-01-28 | 更新: 2026-09-01 | 评论: 0 | 👍: 0
- **摘要**: 提议增加 `$ list skills` 命令以列出当前可用技能，类似 Codex 功能。已关闭，但未说明具体原因（可能因功能设计变更或迁移至 Kimi Code）。
- **为什么重要**: 技能清单是开发者快速了解 CLI 能力的关键入口，该 PR 的关闭可能暗示该功能已通过其他方式实现（如 `shell` 的迁移流程）。
- [GitHub PR #742](https://github.com/MoonshotAI/kimi-cli/pull/742)

### 4. #2630 – [CLOSED] feat(shell): 废弃感知更新流程 + 一键迁移至 Kimi Code

- **作者**: jackfish212 | 创建: 2026-08-31 | 更新: 2026-09-01 | 评论: 0 | 👍: 0
- **摘要**: 当 CDN 发布废弃/迁移通知时，CLI 将 Python 版本标记为废弃，并引导用户一键迁移至全新 Kimi Code 产品。这是产品统一化战略的关键步骤。
- **为什么重要**: 标志着 kimi-cli 可能逐步停止维护，所有用户需关注迁移路径，避免使用旧版本。
- [GitHub PR #2630](https://github.com/MoonshotAI/kimi-cli/pull/2630)

---

## 功能需求趋势

综合当前 Issue 和 PR 的反馈，社区最关注的功能方向如下：

| 方向 | 典型表现 | 说明 |
|------|----------|------|
| **任务编排与异步交互** | Issue #1287 要求提前编写下一任务 Prompt；Issue #1292 子任务卡死 | 用户希望 CLI 支持非阻塞并发输入，以及更稳定的多任务调度 |
| **产品迁移与品牌统一** | PR #2630 一键迁移至 Kimi Code；PR #742 技能列表功能关闭 | 项目正从 `kimi-cli` 向 `Kimi Code` 过渡，社区需适应新品牌和可能的 API 变更 |
| **插件生态标准化** | PR #2614 文档化插件安全与数据持久化 | 随着插件数量增加，开发者需要明确的契约和最佳实践 |
| **稳定性与兼容性** | Issue #1292 卡死问题；1.50.0 修复 anthropic-beta 头部 | 底层网络协议、模型调用兼容性仍是高频痛点 |

---

## 开发者关注点

- **迁移焦虑**：PR #2630 引入的一键迁移功能暗示 `kimi-cli` 可能被逐步取代，开发者需关注 `Kimi Code` 的兼容性与功能差异。
- **任务并发限制**：Issue #1287 表明当前 CLI 不支持异步编写 Prompt，连续工作流中用户效率受损，期待后续版本引入非阻塞输入或队列机制。
- **子任务稳定性**：Issue #1292 的卡死问题虽已关闭，但未在 release notes 中明确修复版本，建议用户升级至 v1.50.0 并主动测试，如仍有问题请重新提交 Issue。
- **技能可发现性**：PR #742 关闭后，获取当前可用技能的方式可能需要通过 `shell` 或 `Kimi Code` 的新命令实现，社区需等待官方文档更新。

---

> 数据截止：2026-09-02 08:00 UTC | 来源：[MoonshotAI/kimi-cli](https://github.com/MoonshotAI/kimi-cli)

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 | 2026-09-02

---

## 📌 今日速览

- **v1.18.26 发布**：修复了 Claude 5 会话中思维块过期、Bedrock GPT-5.6 推理参数、工具调用计时等核心 Bug。
- **社区热议**：剪贴板复制失效（#4283）以 128 条评论持续霸榜；模型自动发现功能（#6231）获 225 个 👍 成为最受期待的功能请求。
- **PR 活跃**：插件系统迎来多项重构，包括持久化状态迁移至 Effect Schema、插件与配置解耦、浏览器插件原型等，核心架构加速演进。

---

## 🚀 版本发布：v1.18.26

**核心 Bug 修复：**

- Claude 5 会话现在能够容忍过期的思维块，不再因提示或工具变更而失败。
- Bedrock 上的 GPT-5.6 模型现在支持 `none` 推理努力（reasoning effort）参数。
- Bedrock 的推理与重放处理更加可靠（感谢 @pengzh1）。
- 工具调用计时现在在变更后仍保持准确。

---

## 🔥 社区热点 Issues（10 个）

### 1. #4283 - 复制到剪贴板失效
- **评论/赞**：128 / 119
- **摘要**：用户选中响应文本后无法复制到剪贴板，影响所有操作系统。基础交互功能受阻，社区反应强烈。
- **链接**：[#4283](https://github.com/anomalyco/opencode/issues/4283)

### 2. #6231 - 自动发现 OpenAI 兼容提供商模型
- **评论/赞**：47 / 225
- **摘要**：用户需手动在 `opencode.json` 中列出所有模型，对于 LM Studio、Ollama 等本地提供商极为不便，请求自动从 `/v1/models` 端点发现模型。
- **链接**：[#6231](https://github.com/anomalyco/opencode/issues/6231)

### 3. #3688 - [已关闭] 系统主题在 v1.0.0 后失效
- **评论/赞**：38 / 20
- **摘要**：`System` 主题选项消失，手动配置亦无效。虽已关闭，但表明 UI 主题机制存在历史兼容问题。
- **链接**：[#3688](https://github.com/anomalyco/opencode/issues/3688)

### 4. #10490 - 请求配置项禁用“选中即复制”行为
- **评论/赞**：18 / 32
- **摘要**：OC 默认实现“XTerm/GPM”风格的选中即复制，用户希望添加 `opencode.json` 配置项来禁用此行为。
- **链接**：[#10490](https://github.com/anomalyco/opencode/issues/10490)

### 5. #19466 - 空闲时 CPU 占用过高
- **评论/赞**：16 / 16
- **摘要**：OpenCode 在等待 API 限速重试期间（无实际工作）消耗约 50% 的单核 CPU（i9-14900），性能问题突出。
- **链接**：[#19466](https://github.com/anomalyco/opencode/issues/19466)

### 6. #7006 - `permission.ask` 插件钩子未触发
- **评论/赞**：14 / 24
- **摘要**：新增的权限系统插件钩子 `permission.ask` 从未被调用，导致自动审批插件无法正常工作，影响自定义权限流程。
- **链接**：[#7006](https://github.com/anomalyco/opencode/issues/7006)

### 7. #1515 - [已关闭] CLI 自动补全（bash/fish/zsh）
- **评论/赞**：11 / 33
- **摘要**：请求为 CLI 添加 shell 补全脚本（如 `source <(opencode completions $SHELL)`），提升日常使用体验。已关闭但社区仍关注。
- **链接**：[#1515](https://github.com/anomalyco/opencode/issues/1515)

### 8. #38723 - `opencode run` 间歇性挂起（~56% 失败率）
- **评论/赞**：8 / 2
- **摘要**：`opencode run` 在初始化阶段随机挂起，无任何输出或错误，日志停留在 `message=init`，只有外部超时能退出。严重影响 CI/CD 集成。
- **链接**：[#38723](https://github.com/anomalyco/opencode/issues/38723)

### 9. #25570 - 请求支持单次提示中多个技能
- **评论/赞**：8 / 22
- **摘要**：当前无法在单个提示中同时指定多个技能，对于多框架工作流（如同时使用 React 和 Vue 技能）造成障碍，社区呼声较高。
- **链接**：[#25570](https://github.com/anomalyco/opencode/issues/25570)

### 10. #18011 - LM Studio 仅显示 3/9 个模型
- **评论/赞**：7 / 5
- **摘要**：OpenCode 自动发现 LM Studio 模型不完整，`/v1/models` 返回 9 个但只显示 3 个，即使使用 API 密钥也无效。
- **链接**：[#18011](https://github.com/anomalyco/opencode/issues/18011)

---

## 📦 重要 PR 进展（10 个）

### 1. #46558 - 重构持久化状态为 Effect Schema
- **状态**：OPEN
- **摘要**：将共享 Web/桌面持久化逻辑迁移到 Effect Schema，涉及 30 个消费者（设置、编辑器、布局、终端、服务器状态等），提升类型安全与可维护性。
- **链接**：[#46558](https://github.com/anomalyco/opencode/pull/46558)

### 2. #46689 - 插件暴露实验性指令源
- **状态**：OPEN
- **摘要**：为 Promise 和 Effect 插件添加 `ctx.experimental.instructions.transform()` 和 `reload()`，支持键值指令源注册、JSON 编解码、渲染回调。
- **链接**：[#46689](https://github.com/anomalyco/opencode/pull/46689)

### 3. #46639 - 插件与配置加载解耦
- **状态**：OPEN
- **摘要**：使 `Plugin` 独立于配置加载器，插件定义可自行管理上下文、激活、清理，为更灵活的插件部署铺路。
- **链接**：[#46639](https://github.com/anomalyco/opencode/pull/46639)

### 4. #46696 - 修复 Windows 沙箱访问权限
- **状态**：OPEN
- **摘要**：在 NSIS 安装后为 `$INSTDIR` 授予 `ALL RESTRICTED APPLICATION PACKAGES` 可继承读/执行权限，防止 Electron 启动失败（遵循 Electron 官方指南）。
- **链接**：[#46696](https://github.com/anomalyco/opencode/pull/46696)

### 5. #46695 - 修复同步失败时位置恢复问题
- **状态**：OPEN
- **摘要**：在连接和 workspace 同步失败时保持编辑器与草稿可见，重试失败读取；仅确认 `LocationNotFoundError` 后才显示目录恢复，提升网络不稳定时的体验。
- **链接**：[#46695](https://github.com/anomalyco/opencode/pull/46695)

### 6. #46694 - 保留工作树创建的标题和繁忙状态
- **状态**：OPEN
- **摘要**：在工作树创建期间保持会话标题可见，并在桌面标签、后台标签、移动标题栏等位置显示繁忙旋转器，优化创建过程中的界面反馈。
- **链接**：[#46694](https://github.com/anomalyco/opencode/pull/46694)

### 7. #46485 - 空闲时自动应用管理更新
- **状态**：OPEN
- **摘要**：跳过 TUI 启动更新检查，监听托管服务事件流，在无活跃会话时自动安装已发现的更新，实现无缝升级。
- **链接**：[#46485](https://github.com/anomalyco/opencode/pull/46485)

### 8. #46690 - 插件暴露会话表单、列表和全局事件流
- **状态**：OPEN
- **摘要**：为插件新增 `session.forms`、`session.list` 和全局事件流能力，支持构建 Telegram 等外部集成机器人。
- **链接**：[#46690](https://github.com/anomalyco/opencode/pull/46690)

### 9. #46687 - 添加异步会话 Webhook
- **状态**：OPEN
- **摘要**：为 v2 提示请求添加可选的 `callbackUrl`，支持移动通知和无法维持 SSE 连接的外部集成，扩展异步交互场景。
- **链接**：[#46687](https://github.com/anomalyco/opencode/pull/46687)

### 10. #46631 - 增量实现待处理状态
- **状态**：OPEN
- **摘要**：修复插件启动期间 OAuth 方法注册但不可读的问题，避免凭据刷新跳过导致的 Console 库存请求失败和模型缺失。
- **链接**：[#46631](https://github.com/anomalyco/opencode/pull/46631)

---

## 📊 功能需求趋势

1. **模型发现与兼容性**：自动发现 OpenAI 兼容提供商模型（#6231）、LM Studio 模型列表不完整（#18011）、Ollama 工具调用未执行（#46625）、Bedrock GPT-5.6 推理参数（#45405）——社区强烈要求减轻手动配置负担，并适配更多模型提供商。
2. **剪贴板与交互行为**：复制粘贴失效（#4283）、禁用选中即复制（#10490）表明用户对基础交互细节的稳定性要求极高。
3. **插件系统增强**：权限钩子触发器（#7006）、插件指令源（#46689）、会话表单/事件流（#46690）、异步 Webhook（#46687）——插件 API 正快速扩展，社区期待更强大的自定义能力。
4. **性能与资源占用**：空闲 CPU 过高（#19466）、GPU 进程崩溃（#36383）、`opencode run` 挂起（#38723）——稳定性与资源效率仍是核心痛点。
5. **多技能与多框架支持**：单次提示多个技能（#25570）、子代理事件透传（#46685）——复杂工作流场景下的需求日益增长。
6. **UI/UX 改进**：主题切换失效（#3688）、滚动条隐藏（#46680）、CLI 自动补全（#1515）——提升日常使用舒适度。
7. **安装与升级体验**：npm + scoop 升级失败（#46493）、Azure CLI 阻塞启动（#46658）——基础设施可靠性需加强。

---

## 🧑‍💻 开发者关注点

- **剪贴板功能严重退化**：Issue #4283 评论数 128，是当前最高热度的 Bug，涉及核心交互，需优先修复。
- **插件权限钩子异常**：Issue #7006 表明新权限系统存在未调用的钩子，阻碍自动审批插件开发，影响插件生态建立。
- **本地模型发现体验差**：LM Studio 和 Ollama 用户频繁遭遇模型列表不完整或工具调用失败，配置门槛高。
- **空闲 CPU 占用不合理**：Issue #19466 中 i9-14900 占用 50% 单核，在等待 API 限速时尤其明显，建议引入休眠或降频策略。
- **`opencode run` 稳定性堪忧**：Issue #38723 报告约 56% 的失败率，且无日志输出，对 CI/CD 场景毁灭性打击。
- **升级与安装问题**：Issue #46493 重复出现 npm + scoop 升级失败，Azure CLI 导致启动阻塞（#46658），影响用户初始体验。
- **GPU 进程崩溃**：Issue #36383 描述 Windows 桌面端首次启动即崩溃，GPU 子进程反复退出，阻止新用户入门。
- **子代理事件信息缺失**：Issue #46685 指出父会话状态在子代理运行时不可见，外部集成无法感知进度，需改进事件总线广播策略。

---

*数据来源：[GitHub - anomalyco/opencode](https://github.com/anomalyco/opencode) | 日报生成时间：2026-09-02*

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，我已根据您提供的 GitHub 数据，为您生成 2026 年 9 月 2 日的 Pi 社区动态日报。

---

# Pi 社区动态日报 | 2026-09-02

## 今日速览

今日 Pi 社区动态活跃，核心焦点集中在**扩展能力增强**与**模型兼容性修复**上。社区贡献者提交了允许子代理工具自定义模型的新功能，并修复了多个影响 Gemini、Grok 等新模型在实际使用中的关键性 Bug，包括工具调用循环和代理陷入“假死”状态的问题。此外，大量关于 TUI 体验优化、RPC 模式稳定性以及文档错误的报告也正在被积极处理。

## 社区热点 Issues

1.  **[Bug] 应用未遵循 XDG 基础目录规范 (#2870)**
    -   **重要性：** **高**。这是一个长期存在的代码质量与用户体验问题，涉及 54 个 👍 和 21 条评论，说明社区对此高度关注。该问题要求将 Linux 上的配置和状态文件从 `$HOME` 迁移到 `$XDG_CONFIG_HOME` 等标准目录，是提升项目成熟度的关键一步。
    -   **社区反应：** 讨论热烈，社区普遍支持，该问题已于近期关闭，预计相关改动即将合并。 [查看详情](https://github.com/earendil-works/pi/issues/2870)

2.  **[Bug] Agent 卡在“Working”状态但无任何进展 (#4338)**
    -   **重要性：** **高**。这是一个严重干扰核心工作流的问题。8 条评论表明多用户遇到此问题，代理在会话中频繁陷入循环，无法继续执行任务，严重影响开发效率。
    -   **社区反应：** 用户反馈强烈，期望核心团队能尽快定位并修复此“假死”问题。 [查看详情](https://github.com/earendil-works/pi/issues/4338)

3.  **[Bug] Gemini 3.x 模型在工具调用时因缺失 `thought_signature` 失败 (#6996)**
    -   **重要性：** **高**。这是一个与最新模型兼容性的关键问题。Gemini 3.x 系列模型在涉及工具调用后，会因为历史记录中缺少特定字段而报错，阻碍了用户使用最新的强大模型。
    -   **社区反应：** 开发者正积极讨论，寻找最佳解决方案，可能需要适配 Google 的新 API 规范。 [查看详情](https://github.com/earendil-works/pi/issues/6996)

4.  **[Bug] 通过正向代理使用 HTTP 提供商时，代理在首次工具调用后停止 (#8134)**
    -   **重要性：** **中**。此问题影响了使用本地或自托管模型（通常为 HTTP 协议）并通过代理连接网络的用户。自 0.84.0 版本引入，对部分用户的工作流造成了阻塞。
    -   **社区反应：** 6 条评论，用户正在积极提供复现环境和日志，帮助开发者定位代理相关的问题。 [查看详情](https://github.com/earendil-works/pi/issues/8134)

5.  **[Bug] Grok 4.6 模型无限重复工具调用 (#8973)**
    -   **重要性：** **高**。这是一个新报告的严重 Bug，影响使用 xAI Grok 模型的用户。代理会陷入无限循环，反复执行同一个工具调用，而忽略返回的结果，导致会话完全卡死。
    -   **社区反应：** 社区认为这是自 0.84.3 版本后的一个回归问题，开发者需要紧急修复。 [查看详情](https://github.com/earendil-works/pi/issues/8973)

6.  **[Feature] 允许扩展在现有会话中启动全新的上下文窗口 (#8972)**
    -   **重要性：** **中**。这是一个强大的扩展 API 需求。允许扩展在不创建新会话或不进行压缩的情况下，主动重置模型上下文，为编写更复杂、更智能的扩展提供了可能性（例如，实现“分支”对话或“聚焦”模式）。
    -   **社区反应：** 社区对此功能表示期待，认为它将极大提升扩展的灵活性和能力边界。 [查看详情](https://github.com/earendil-works/pi/issues/8972)

7.  **[Bug] 缺少 API Key 的供应商会从模型目录中消失 (#8968)**
    -   **重要性：** **中**。这是一个体验问题，当用户配置了多个模型供应商，但其中某些未设置 API Key 时，它们会从可用的 `/model` 列表中消失，导致用户误以为配置失败。
    -   **社区反应：** 该问题已被标记为“已修复”，社区对其快速响应表示满意。 [查看详情](https://github.com/earendil-works/pi/issues/8968)

8.  **[Bug] 编辑工具拒绝由 JSON 字符串组成的数组形式的编辑内容 (#8962)**
    -   **重要性：** **中**。这是一个模型兼容性问题。某些模型会以 JSON 字符串数组的形式发送编辑指令，但现有的编辑工具无法正确解析，导致编辑失败。
    -   **社区反应：** 开发者已提出修复方案，增强了工具的鲁棒性，以兼容更多模型的输出格式。 [查看详情](https://github.com/earendil-works/pi/issues/8962)

9.  **[Bug] RPC `abort` 报告成功但未取消正在进行的压缩操作 (#8920)**
    -   **重要性：** **中**。这是一个 RPC 模式下的状态管理问题。当用户尝试中止压缩时，系统返回成功，但压缩仍在后台运行，导致后续操作因冲突而失败。
    -   **社区反应：** 用户报告了清晰的复现步骤和错误日志，帮助开发团队定位问题。 [查看详情](https://github.com/earendil-works/pi/issues/8920)

10. **[Bug] 文档链接与页面标题锚点不匹配 (#8921)**
    -   **重要性：** **低（但影响广泛）**。这是一个影响所有用户文档浏览体验的问题。官方文档和发布说明中的内部链接因锚点不匹配而失效，无法跳转到指定章节。
    -   **社区反应：** 该问题已被标记为“处理中”，社区期望官方文档能尽快得到修复。 [查看详情](https://github.com/earendil-works/pi/issues/8921)

## 重要 PR 进展

1.  **feat(coding-agent): 为子代理工具添加模型和思考模式覆盖 (#8969)**
    -   **功能：** 允许用户在调用子代理工具时，动态指定不同的模型和思考模式，而无需依赖默认设置。这使得开发者可以灵活地分配任务：例如，使用一个快速廉价的模型进行初步探索，再使用一个更强大的模型进行深度规划。
    -   **状态：** **已合并**。 [查看详情](https://github.com/earendil-works/pi/pull/8969)

2.  **fix(coding-agent): `--provider` 参数现在能正确选择其默认模型 (#8966)**
    -   **修复：** 修复了当用户仅使用 `--provider` 参数而未指定 `--model` 时，该参数被忽略的 Bug。现在，`--provider` 会正确选择该供应商的默认模型，并改进了认证失败时的错误报告。
    -   **状态：** **已合并**。 [查看详情](https://github.com/earendil-works/pi/pull/8966)

3.  **fix(ai): 为 `openai-responses` 添加 `supportsMaxOutputTokens` 兼容性标志 (#8941)**
    -   **修复：** 解决了某些兼容 OpenAI Responses 协议的网关（如 Codex 代理）无法处理 `max_output_tokens` 参数的问题。通过引入一个可选的兼容性标志，允许用户关闭该参数的发送。
    -   **状态：** **已合并**。 [查看详情](https://github.com/earendil-works/pi/pull/8941)

4.  **feat(coding-agent): 默认在恢复会话选择器中隐藏无头会话 (#8951)**
    -   **功能：** 改善用户体验。由自动化工具（如 RPC 模式、子代理）创建的会话文件将不再默认显示在 `/resume` 列表中，避免干扰用户手动恢复其交互式会话。
    -   **状态：** **已合并**。 [查看详情](https://github.com/earendil-works/pi/pull/8951)

5.  **fix(ai): 修复 `NO_PROXY` 环境变量对子域名和根域名的匹配 (#8737)**
    -   **修复：** 完善了 `NO_PROXY` 的解析逻辑，使其能正确匹配通配符域名和裸域名，并修复了 IPv6 地址的解析问题。
    -   **状态：** **已合并**。 [查看详情](https://github.com/earendil-works/pi/pull/8737)

6.  **feat(coding-agent): 调整 TUI 中的选择样式 (#8900)**
    -   **功能：** 优化了 `/thinking`、`/model` 等命令下的 TUI 选择界面，采用“双列”布局（如 `→ ✓ xhigh`），更清晰地标示出当前激活的选项，提升了视觉清晰度。
    -   **状态：** **已合并**。 [查看详情](https://github.com/earendil-works/pi/pull/8900)

7.  **feat(tui): 美化“Working...”旋转动画 (#8799)**
    -   **功能：** 将“Working...”状态提示移至输入编辑器边框，并根据思考等级显示不同颜色，同时处理“重试中”的情况，使界面反馈更优雅、直观。
    -   **状态：** **开放中**，仍在开发。 [查看详情](https://github.com/earendil-works/pi/pull/8799)

8.  **fix(ai): 在延迟设置过程中保留中止的停止原因 (#8635)**
    -   **修复：** 修复了在工具执行后、进行下一步认证设置时，如果请求被中止，无法正确报告中止状态的 Bug。增加了对此场景的回归测试。
    -   **状态：** **开放中**，等待审查。 [查看详情](https://github.com/earendil-works/pi/pull/8635)

9.  **fix(agent): 在预检中止后停止已准备好的工具 (#8936)**
    -   **修复：** 修复了当并行工具调用在准备阶段后被中止时，部分工具仍会执行的问题。现在，中止

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 | 2026-09-02

---

## 🔍 今日速览

- **CUA Driver 发布 v0.20.3**，提供 macOS codesign、Linux/Windows 多架构预编译二进制，底层驱动能力持续增强。
- **TUI 渲染层迁移（ink → OpenTUI）** 成为社区焦点，跟踪 Issue #8662 已积累 16 条评论，暴露出 flicker、光标偏移等结构性难题。
- **多个 P1/P2 级 Bug 集中爆发**，尤以 `toolSearch.threshold > 0` 导致 `llama.cpp` 语法解析失败（#10520）、`permissions.allow` 语义变更（#10218）影响面最广，开发者反馈强烈。

---

## 📦 版本发布

### cua-driver-rs v0.20.3
- **描述**：CUA Driver 预构建二进制文件（位于 `packages/cua-driver` 下）。
- **平台支持**：
  - **macOS**：codesigned + notarized 通用二进制 + `QwenCuaDriver.app`
  - **Linux**：unsigned（x86_64 + arm64，glibc ≥ 2.31）
  - **Windows**：unsigned UIAccess worker + native SDK payload（x86_64 + arm64）
- **链接**：[Release 页面](https://github.com/QwenLM/qwen-code/releases/tag/cua-driver-rs-v0.20.3)

---

## 🔥 社区热点 Issues（Top 10）

### 1. #8662：TUI 渲染层从 ink 迁移至 OpenTUI（跟踪）
- **重要性**：当前 TUI 基于 ink 7 + React 19，严重 patch 导致 flicker、渲染错位等结构性缺陷。迁移是中长期 UX 改进的核心。社区评论 16 条，讨论深入。
- **链接**：[Issue #8662](https://github.com/QwenLM/qwen-code/issues/8662)

### 2. #10520：`toolSearch.threshold > 0` 导致 llama.cpp 400 语法解析错误
- **重要性**：P2 级 Bug，影响所有使用本地 llama.cpp 并开启 toolSearch 边界的用户。阈值设为 0 可绕过，说明内部 grammar 生成逻辑有缺陷。评论 7 条，复现清晰。
- **链接**：[Issue #10520](https://github.com/QwenLM/qwen-code/issues/10520)

### 3. #10530：0.22.3 版本 `Failed to initialize samplers` 错误
- **重要性**：与 #10520 类似但更泛化，使用 Qwen 3.8 27B/35B 时触发，前版本正常。怀疑与 grammar 采样器变更相关。评论 5 条，社区已定位到版本回归。
- **链接**：[Issue #10530](https://github.com/QwenLM/qwen-code/issues/10530)

### 4. #10218：`permissions.allow` 语义变更——未覆盖工具直接禁用（无询问）
- **重要性**：P1 级行为变更，0.22.1 起从“自动批准列表”变为“注册表白名单”，导致未覆盖工具被静默禁用且无文档说明。影响大量现有自动化配置。评论 5 条，用户要求回退或明确文档。
- **链接**：[Issue #10218](https://github.com/QwenLM/qwen-code/issues/10218)

### 5. #10162：`qwen serve` 队列饱和时应优雅降级而非直接关闭通道
- **重要性**：P2 增强，生产环境中 NDJSON 队列满导致通道被杀死，影响会话可靠性。已提出 follow-up 方案。评论 5 条。
- **链接**：[Issue #10162](https://github.com/QwenLM/qwen-code/issues/10162)

### 6. #2339：Telegram Bot 模式（`--telegram` 标志）
- **重要性**：持续受关注的需求（👍 3），允许通过 Telegram 远程交互。评论 4 条，社区期待官方实现。
- **链接**：[Issue #2339](https://github.com/QwenLM/qwen-code/issues/2339)

### 7. #10583：为 Linux 添加轻量级 Bubblewrap 沙箱后端
- **重要性**：P2 功能请求，无需 Docker 即可提供 OS 级隔离，对容器化环境不友好的场景极有价值。评论 4 条，讨论 bwrap 集成细节。
- **链接**：[Issue #10583](https://github.com/QwenLM/qwen-code/issues/10583)

### 8. #10710：`serve` 中会话重载隐藏已持久化的 assistant 消息
- **重要性**：P2 级 Bug，通道中断后重新加载会话会导致已保存的 assistant 回复丢失，影响可恢复性。评论 4 条，与 #10162 队列问题相关。
- **链接**：[Issue #10710](https://github.com/QwenLM/qwen-code/issues/10710)

### 9. #10400：`tools.eager` 条目命名与 `Object.prototype` 键冲突导致崩溃
- **重要性**：P1 级 Bug，若用户配置了名为 `toString`、`hasOwnProperty` 等 prototype 键的工具，`PermissionManager.initialize` 会 crash。评论 4 条，属高危配置缺陷。
- **链接**：[Issue #10400](https://github.com/QwenLM/qwen-code/issues/10400)

### 10. #10698：Node 20 下构建失败（ESM 错误）
- **重要性**：P3 支持问题，Node 20 用户无法通过 `npm ci` 构建。评论 4 条，要求提供 workaround 或修复。
- **链接**：[Issue #10698](https://github.com/QwenLM/qwen-code/issues/10698)

---

## 🚀 重要 PR 进展（Top 10）

### 1. #9402：Agent Board——独立启动的 agents 之间共享工作
- **内容**：实现可移植的 Board 层，为后续多 agent 协作奠定基础。不包含完整的 Qwen-to-Qwen 流程。评论较多，架构设计关键。
- **链接**：[PR #9402](https://github.com/QwenLM/qwen-code/pull/9402)

### 2. #10457：DingTalk 工具权限请求以原生交互卡片呈现
- **内容**：DingTalk 渠道的权限请求改为交互式卡片，支持“允许一次/拒绝/持久允许”。提升企业用户审批体验。
- **链接**：[PR #10457](https://github.com/QwenLM/qwen-code/pull/10457)

### 3. #10575：CI 秒级任务独立 ECS 通道
- **内容**：将 8 个耗时仅数秒的 jobs（如 force-push 提醒）迁移至独立的 `ecs-light` 通道，减少主队列阻塞。CI 优化关键 PR。
- **链接**：[PR #10575](https://github.com/QwenLM/qwen-code/pull/10575)

### 4. #9071：基于经验信号门控自动技能审查
- **内容**：将 AutoSkill 的仅计数触发改为确定性门控（重试弧、用户转向等），提升审查准确性。评论自报告。
- **链接**：[PR #9071](https://github.com/QwenLM/qwen-code/pull/9071)

### 5. #10704：修复 Web Shell 中跨客户端队列提示不一致
- **内容**：daemon 持有的队列提示按 prompt 身份协调，而非浏览器客户端，避免重复或丢失。修复多客户端交互问题。
- **链接**：[PR #10704](https://github.com/QwenLM/qwen-code/pull/10704)

### 6. #10421：在 probe tree 恢复前筛选内容过滤器
- **内容**：修复 `scratch-tree` 在本地配置 content filter 时拒绝创建/重置的问题，涉及 `filter.<name>.smudge` 检查。影响代码审查流程。
- **链接**：[PR #10421](https://github.com/QwenLM/qwen-code/pull/10421)

### 7. #10713：为频道对话添加 `/btw` 侧问题支持
- **内容**：在 Channel 中实现 `/btw` 侧问能力，验证输入、授权，返回带相关标识的响应。增强多任务场景。
- **链接**：[PR #10713](https://github.com/QwenLM/qwen-code/pull/10713)

### 8. #10719：Web Shell 为独立会话加载模型目录
- **内容**：在独立会话不存在时预先加载模型配置，通过能力门控的只读端点实现。改善 Web Shell 启动体验。
- **链接**：[PR #10719](https://github.com/QwenLM/qwen-code/pull/10719)

### 9. #10679：添加工作区范围的 MCP 管理
- **内容**：在工作区级别管理 MCP 配置和运行时，支持配置持久化、重载、重连、认证等。daemon 架构核心扩展。
- **链接**：[PR #10679](https://github.com/QwenLM/qwen-code/pull/10679)

### 10. #10751：添加会话轮次导航协议
- **内容**：Phase 1 实现 daemon 和 SDK 侧会话轮次导航，包括稀疏索引、签名快照、分页。为 Web Shell 会话导航功能铺路。
- **链接**：[PR #10751](https://github.com/QwenLM/qwen-code/pull/10751)

---

## 📈 功能需求趋势

从近期的 Issues 和 PR 中，社区最关注以下功能方向：

- **TUI/终端用户体验**：从 ink 迁移至 OpenTUI（#8662），解决 flicker、滚动、光标问题；会话导航（#10750）、斜杠命令附件保留（#10730）。
- **沙箱与安全**：轻量级 Bubblewrap 后端（#10583）、权限模型改进（#10218）、工具权限交互卡片（#10457）。
- **渠道集成扩展**：Telegram Bot 模式（#2339）、DingTalk 交互卡片（#10457）、频道内侧问（#10713）。
- **会话管理**：跨客户端队列协调（#10704）、会话轮次导航（#10751）、搜索内容匹配（#10261）。
- **CI/CD 与性能**：CI 秒级任务独立通道（#10575）、队列饱和优雅降级（#10162）、构建缓存优化（#10422）。
- **新运行时支持**：Node 20 ESM 兼容（#10698）、llama.cpp grammar 采样器修复（#10520/#10530）。

---

## 💡 开发者关注点

- **权限系统激进变更**：`permissions.allow` 从“白名单”变为“启用列表”，未覆盖工具直接禁用且无提示，用户被迫升级审查配置。建议尽快补充文档或提供迁移指南。
- **llama.cpp 兼容性回归**：0.22.3 中 `toolSearch.threshold` 与 grammar 采样器冲突，以及 Qwen 3.8 系列模型初始化失败，影响本地推理用户。需紧急修复或回退。
- **队列饱和导致会话中断**：`qwen serve` 中 NDJSON 队列满直接关闭通道，且重载后丢失部分消息，影响生产环境稳定性。社区期待优雅降级方案。
- **构建环境问题**：Node 20 下 ESM 报错、Windows 下扩展安装静默退出（#10742/#10741），开发环境适配仍需加强。
- **编辑器可用性检查缺失**：编辑确认对话框显示“使用外部编辑器”但实际编辑器未安装，导致流程失败（#10745）。期望增加前置验证。

---

*以上日报基于 GitHub 数据自动生成，数据截止 2026-09-02 08:00 UTC。*

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，这是为您生成的 2026-09-02 DeepSeek TUI 社区动态日报。

---

# DeepSeek TUI 社区动态日报 (2026-09-02)

**数据分析周期**: 2026-09-01 至 2026-09-02

---

## 1. 今日速览

今日社区活跃度较高，主要围绕 **CodeWhale v0.9.12 版本发布前的最后冲刺**。多项关键修复和功能被合并，包括修复了可能导致模型目录永远过时的严重 Bug、实现了原生 ChatGPT PKCE 登录以消除对 Codex CLI 的依赖，并优化了首次启动体验。此外，一个关于集成开源设计引擎 **OpenDesign** 的新功能请求 (Issue #5806) 引起了关注，预示着 AI 开发工具与设计工具融合的新趋势。

## 3. 社区热点 Issues

以下挑选了 10 个最值得关注的 Issue，涵盖 Bug 修复、功能增强和长期演进。

1.  **[#5806] [OPEN] feat: OpenDesign (nexu-io/open-design) 兼容性**  
    - **重要性**: 此 Issue 提出了集成开源设计引擎 OpenDesign（93k+ Stars）的宏伟计划，旨在将 TUI 转变为设计引擎，支持原型、演示文稿、设计系统导出等。这标志着 TUI 从纯代码开发工具向更广泛的设计-开发协作平台演进。
    - **社区反应**: 刚创建，暂无评论，但潜在影响巨大，值得长期关注。
    - **链接**: [Hmbown/CodeWhale Issue #5806](https://github.com/Hmbown/CodeWhale/issues/5806)

2.  **[#5778] [CLOSED] 无需安装 Codex CLI 即可原生登录 ChatGPT/Codex 订阅**  
    - **重要性**: 解决了用户反馈的一大痛点。此前连接 ChatGPT 订阅必须依赖外部 `codex` CLI 工具，此 Issue 推动实现了原生 PKCE 登录流程，极大降低了新用户的使用门槛。
    - **社区反应**: 已关闭，并由 PR #5784 实现，社区高度认可。
    - **链接**: [Hmbown/CodeWhale Issue #5778](https://github.com/Hmbown/CodeWhale/issues/5778)

3.  **[#5713] [CLOSED] fix(custom): 支持 `wire = "responses" | "anthropic"` 配置**  
    - **重要性**: 针对自定义 OpenAI 兼容提供商，新增了对 Responses API 和 Anthropic Messages API 格式的支持。这增强了工具的灵活性和对不同模型后端的兼容性。
    - **社区反应**: 由社区开发者 `whp233` 贡献，已合并，体现了社区对模型兼容性的强烈需求。
    - **链接**: [Hmbown/CodeWhale Issue #5713](https://github.com/Hmbown/CodeWhale/issues/5713)

4.  **[#5522] [CLOSED] v0.9.10: 让首次运行渐进式引导，而非前置全量配置**  
    - **重要性**: 直接来自非英语用户的反馈，指出首次启动时展示的大量配置选项和英文遥测披露造成了过高的心理成本。此 Issue 推动了更友好的“渐进式”首次运行体验。
    - **社区反应**: 已关闭，体现了项目对用户体验（尤其国际化）的重视。
    - **链接**: [Hmbown/CodeWhale Issue #5522](https://github.com/Hmbown/CodeWhale/issues/5522)

5.  **[#5605] & [#5735] [CLOSED] 并行测试下的 Flaky 测试问题**  
    - **重要性**: 两个 Issue 都是关于在完整测试套件并行负载下，某些测试用例（`remote_control` 和 `runtime_chat_relay`）会间歇性失败。这是影响 CI 稳定性的常见但棘手的问题。
    - **社区反应**: 两个 Issue 都已关闭，表明团队正在积极解决测试稳定性，但未提及具体根因，可能仍需持续关注。
    - **链接**: [Hmbown/CodeWhale Issue #5605](https://github.com/Hmbown/CodeWhale/issues/5605), [Hmbown/CodeWhale Issue #5735](https://github.com/Hmbown/CodeWhale/issues/5735)

6.  **[#5519] [CLOSED] Web: `isZh` 国际化迁移进度倒挂**  
    - **重要性**: 暴露了一个核心问题：尽管有迁移计划，但代码中直接使用 `locale === "zh"` 进行分支判断的文件数量在过去 90 天内反而增加了，表明国际化迁移工作失去了方向。
    - **社区反应**: 已由 PR #5805 解决，通过添加一个“单项上限”测试来强制收敛，确保迁移工作不会倒退。
    - **链接**: [Hmbown/CodeWhale Issue #5519](https://github.com/Hmbown/CodeWhale/issues/5519)

7.  **[#5757] & [#5754] [CLOSED] 用户界面 (TUI) 的视觉修复与对齐**  
    - **重要性**: 这两个 Issue 涉及 TUI 界面的细节打磨：#5757 修复了活动会话编辑器（Composer）的圆角边框渲染问题；#5754 将启动画面更新为官方认可的新 Logo（鲸鱼图案）。
    - **社区反应**: 均已关闭，表明团队在产品视觉一致性上投入了精力，追求更精致的用户体验。
    - **链接**: [Hmbown/CodeWhale Issue #5757](https://github.com/Hmbown/CodeWhale/issues/5757), [Hmbown/CodeWhale Issue #5754](https://github.com/Hmbown/CodeWhale/issues/5754)

8.  **[#5761] [CLOSED] 每次干净启动时显示 Tideline 启动画面**  
    - **重要性**: 修复了因历史设置导致干净启动时直接跳过启动画面，进入原始会话壳的问题，确保用户每次都能看到设计好的引导界面。
    - **社区反应**: 已关闭，是用户体验一致性修复的一部分。
    - **链接**: [Hmbown/CodeWhale Issue #5761](https://github.com/Hmbown/CodeWhale/issues/5761)

9.  **[#4394] [CLOSED] Compaction: 发布并强制执行结构化生存契约**  
    - **重要性**: 这是一个关于“Compaction”（上下文压缩/整理）功能的长期演进 Issue。它提出了一个更严格、结构化的契约来管理上下文，对于提升长会话的可靠性和性能至关重要。
    - **社区反应**: 已关闭，但摘要提到“已实现大部分”，说明此功能仍在持续完善中，是长期基础设施改进的一部分。
    - **链接**: [Hmbown/CodeWhale Issue #4394](https://github.com/Hmbown/CodeWhale/issues/4394)

10. **[#5807] [OPEN] fix(tui): 内置模型目录可能再次过时**  
    - **重要性**: 这是一个发布阻断（Release-blocker）级别的 Bug。修复了内置模型快照的 TTL（生存时间）被错误设置为十年，导致模型目录永远无法更新，严重影响用户使用最新模型。
    - **社区反应**: 刚创建，相关 PR 已提交，这是今天最关键的修复之一。
    - **链接**: [Hmbown/CodeWhale Issue #5807](https://github.com/Hmbown/CodeWhale/issues/5807)

## 4. 重要 PR 进展

以下挑选了 10 个重要的 PR，代表了过去 24 小时内的主要代码变更。

1.  **[\#5807] [OPEN] fix(tui): 修复内置模型目录过时 Bug**  
    - **功能/修复**: 紧急修复了发布阻断 Bug。将内置模型目录的 TTL 从 10 年改为 30 天，并修复了过期检查的逻辑，确保模型目录能及时更新。
    - **链接**: [Hmbown/CodeWhale PR #5807](https://github.com/Hmbown/CodeWhale/pull/5807)

2.  **[\#5784] [CLOSED] feat(tui): 原生 ChatGPT PKCE 登录**  
    - **功能/修复**: 实现了 Issue #5778 提出的功能。用户现在可以在 DeepSeek TUI 内直接通过浏览器进行 PKCE 流程登录 ChatGPT 账号，无需再安装 Codex CLI。
    - **链接**: [Hmbown/CodeWhale PR #5784](https://github.com/Hmbown/CodeWhale/pull/5784)

3.  **[\#5805] [CLOSED] web(i18n): 添加 `isZh` 分支的上限测试**  
    - **功能/修复**: 解决了 Issue #5519 的问题。通过在 CI 中添加一个测试，强制 `web/lib/i18n` 目录之外直接使用 `isZh` 判断的文件数量不得超过 28 个，以防止国际化迁移工作倒退。
    - **链接**: [Hmbown/CodeWhale PR #5805](https://github.com/Hmbown/CodeWhale/pull/5805)

4.  **[\#5798] [CLOSED] fix(tui): 修复 Tab 键焦点切换问题**  
    - **功能/修复**: 修复了一个微妙的焦点问题。此前由于缺少明确的焦点所有者，导致 Tab 键的焦点切换逻辑复杂且不可靠。此 PR 通过明确焦点所有者，使得 Tab/Shift+Tab 的切换行为变得可预测。
    - **链接**: [Hmbown/CodeWhale PR #5798](https://github.com/Hmbown/CodeWhale/pull/5798)

5.  **[\#5799] [CLOSED] tui: 工具调用 (Tool Cells) 现在携带自身状态**  
    - **功能/修复**: 提升了工具调用的视觉反馈。现在，运行中、失败或警告的工具会像其他输出块一样，在对话记录中通过边框颜色等方式显示其状态，大大增强了可读性。
    - **链接**: [Hmbown/CodeWhale PR #5799](https://github.com/Hmbown/CodeWhale/pull/5799)

6.  **[\#5795] [CLOSED] fix(providers): Ollama 默认模型从本地目录获取**  
    - **功能/修复**: 修复了一个严重的配置错误。当用户首次使用本地 Ollama 时，工具会错误地选择一个远程托管的模型名称（如 `deepseek-v4-flash`），导致所有请求失败。现在会正确地从本地 Ollama 的模型目录中获取默认模型。
    - **链接**: [Hmbown/CodeWhale PR #5795](https://github.com/Hmbown/CodeWhale/pull/5795)

7.  **[\#5796] [CLOSED] fix(tui): 底部栏权限状态优先级高于模式文字**  
    - **功能/修复**: 修复了“操作模式”下底部栏缺少“完全访问”权限状态标记的问题。现在权限状态标记的优先级更高，确保用户能清晰了解当前权限。
    - **链接**: [Hmbown/CodeWhale PR #5796](https://github.com/Hmbown/CodeWhale/pull/5796)

8.  **[\#5743] [CLOSED] web(tideline): 文档中心与帮助系统**  
    - **功能/修复**: 这是一个大型功能 PR，为 Web 端（Tideline）构建了完整的文档中心，包括任务搜索、版本更新日志、上下文帮助等，是提升用户自助服务能力的关键一步。
    - **链接**: [Hmbown/CodeWhale PR #5743](https://github.com/Hmbown/CodeWhale/pull/5743)

9.  **[\#5725] [CLOSED] feat(providers): 添加 Concentrate 作为一级 BYOK 提供商**  
    - **功能/修复**: 新增了一个名为 Concentrate 的 OpenAI Responses API 兼容网关提供商。这为用户提供了更多样化的模型后端选择，特别是那些需要 BYOK（自带密钥）的用户。
    - **链接**: [Hmbown/CodeWhale PR #5725](https://github.com/Hmbown/CodeWhale/pull/5725)

10. **[\#5712] [CLOSED] feat(cli): 云调度远程运行器**  
    - **功能/修复**: 完善了 `/dispatch` 命令的功能。现在，确认的调度任务会真正在云端沙箱中运行，并自动创建 Forge PR，实现了从本地到云端的完整 CI/CD 流程。
    - **链接**: [Hmbown/CodeWhale PR #5712](https://github.com/Hmbown/CodeWhale/pull/5712)

## 5. 功能需求趋势

从近期的 Issues 和 PR 中，可以提炼出社区最关注的几个功能方向：



</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*