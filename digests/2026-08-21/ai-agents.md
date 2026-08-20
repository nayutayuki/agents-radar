# OpenClaw 生态日报 2026-08-21

> Issues: 500 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-08-20 23:00 UTC

- [OpenClaw](https://github.com/openclaw/openclaw)
- [NanoBot](https://github.com/HKUDS/nanobot)
- [Hermes Agent](https://github.com/nousresearch/hermes-agent)
- [PicoClaw](https://github.com/sipeed/picoclaw)
- [NanoClaw](https://github.com/qwibitai/nanoclaw)
- [NullClaw](https://github.com/nullclaw/nullclaw)
- [IronClaw](https://github.com/nearai/ironclaw)
- [LobsterAI](https://github.com/netease-youdao/LobsterAI)
- [TinyClaw](https://github.com/TinyAGI/tinyagi)
- [Moltis](https://github.com/moltis-org/moltis)
- [CoPaw](https://github.com/agentscope-ai/CoPaw)
- [ZeptoClaw](https://github.com/qhkm/zeptoclaw)
- [ZeroClaw](https://github.com/zeroclaw-labs/zeroclaw)

---

## OpenClaw 项目深度报告

## OpenClaw 项目动态日报 — 2026-08-21

### 1. 今日速览

过去 24 小时项目活跃度极高，共产生 500 条 Issue 更新和 500 条 PR 更新。其中 **458 条 Issue 为新开或活跃**，仅 42 条被关闭；PR 方面 **336 条仍处于待合并状态**，164 条已合并或关闭。合并率约 33%，表明代码审查和合并吞吐量接近极限，积压压力持续存在。无新版本发布。社区讨论集中在 **网关级成本控制、跨编码文件名处理、SQLite 性能瓶颈** 以及 **多个 P0 级崩溃回归** 上，维护团队需要重点关注高优先级 bug 的修复进展。

### 2. 版本发布

无新版本发布。

### 3. 项目进展

今日合并/关闭的 PR 主要来自维护者 **steipete** 的快速修复批次，覆盖以下关键领域：

- **会话订阅恢复**：`#126760` 修复了 Control UI 会话订阅停止响应后聊天无法更新的问题。
- **沙箱后端所有权**：`#126828` 重构了 OpenShell 和 Codex 的沙箱适配器，消除重复后端句柄对象。
- **自定义端口查询**：`#126832` 修复了 `gateway usage-cost` 等命令在自定义端口下默默连接默认端口的问题。
- **UI 工具/技能状态**：`#126826` 修复了重新连接后工具和技能列表显示陈旧数据的问题。
- **插件提取器**：`#126829` 修复了插件元数据重载时可能丢弃健康提取器的问题。
- **TUI 消息路由**：`#126820` 修复了终端用户在选择代理变更后发送消息到错误代理的问题。
- **安装脚本**：`#126871` 修复了安装成功但后续验证失败时仍显示成功的问题。
- **安全策略确认**：`#116489` 新增了 `security.installPolicy` 支持 `warn` 级别，要求操作员在安装可疑插件时明确确认。

此外，还有一批新提交的 PR 正在等待审核或作者更新。

### 4. 社区热点

今日讨论最活跃的 Issues 反映了社区对 **成本控制**、**文件编码** 和 **版本验证** 的高度关注：

- **#42475** [Feature]: Per-agent cost budget enforcement at the gateway level（23 条评论）  
  用户强烈要求网关层面支持按代理设置每日/每月预算上限，以自动阻止因模型调用失控导致的费用飙升。该功能目前无关联 PR，维护者已标记为“needs-product-decision”。
- **#48788** feat: centralized filename encoding utility for multi-encoding Content-Disposition handling（20 条评论）  
  社区希望为所有渠道适配器提供统一的文件名编码工具，以处理 Shift-JIS、EUC-KR、GB18030 等多编码场景。当前仅通过 PR #48578 修复了 UTF-8 常见情况，但架构性解决方案仍在讨论中。
- **#125626** Release validation: v2026.8.1-beta.2（17 条评论）  
  版本验证流程涉及多名测试者，讨论集中在验证步骤、已知问题以及如何确保 beta 版本质量。

### 5. Bug 与稳定性

今日报告了大量 Bug，按严重程度排列如下（P0 为最高）：

| 严重级别 | Issue | 摘要 | 状态 |
|---------|-------|------|------|
| **P0** | [#108435](https://github.com/openclaw/openclaw/issues/108435) | 升级到 2026.7.1 后网关无法启动（systemd/ollama/手动启动均失败） | 开放，无关联 fix PR |
| **P0** | [#124788](https://github.com/openclaw/openclaw/issues/124788) | beta.2 网关事件循环每 ~10.9 分钟阻塞 ~100-120 秒，导致 WebSocket 断开、HTTP 无响应 | 开放，无 fix PR |
| **P0** | [#119270](https://github.com/openclaw/openclaw/issues/119270) | 文件工具（write/edit/apply_patch）会剥离目标路径开头的 `@`，导致写入/删除错误文件 | 开放，有 linked PR（待确认） |
| **P0** | [#125333](https://github.com/openclaw/openclaw/issues/125333) | totalTokens 膨胀问题仍未完全修复，`#123065` 的修复仅覆盖 `api === "cli"` 路径 | 开放，无 fix PR |
| **P1** | [#112423](https://github.com/openclaw/openclaw/issues/112423) | 大型 SQLite 转录清理阻塞网关事件循环 | 开放，无关联 PR |
| **P1** | [#113306](https://github.com/openclaw/openclaw/issues/113306) | SQLite 快照恢复缺少端到端崩溃和身份保证 | 开放，无 fix PR |
| **P1** | [#119087](https://github.com/openclaw/openclaw/issues/119087) | 网关冷启动时间从 2026.7.1-beta.1 到 2026.7.2-beta.7 退化约 2.5 倍 | 开放，有 linked PR |
| **P1** | [#123073](https://github.com/openclaw/openclaw/issues/123073) | dev 频道更新失败：`EUNSUPPORTEDPROTOCOL` 因为仓库使用 pnpm 而更新器使用 npm | 开放，有 linked PR |
| **P1** | [#125431](https://github.com/openclaw/openclaw/issues/125431) | Codex 受限工具策略静默禁用 workspace AGENTS.md | 开放，需安全审查 |
| **P1** | [#126246](https://github.com/openclaw/openclaw/issues/126246) | Telegram 持久化外发消息卡在 `send_attempt_started`，重启后丢失 | 开放，无 fix PR |

**值得注意的是**，多个 P0/P1 回归问题自 2026 年 7 月甚至 3 月就已报告，至今仍未修复，对项目稳定性构成严重威胁。

### 6. 功能请求与路线图信号

用户提出的新功能需求中，以下几条可能被纳入下一版本：

- **#42475** 网关级代理成本预算（P2，已标记为需要产品决策，但高评论数表明需求强烈）
- **#48788** 集中式文件名编码工具（P3，已有 PR #48578 部分修复，架构方案仍在讨论）
- **#45564** 为 `/new` 和 `/reset` 添加确认步骤（P2，已有 6 条评论，社区普遍支持）
- **#45501** 可配置会话启动消息 `session.resetPrompt`（P3，只有 6 条评论，但实现简单，可能被采纳）
- **#71142** 可配置 Control UI 上传大小限制（P2，已有 8 条评论，当前硬编码 5MB 限制影响用户体验）

此外，`#50798`（代理间可见消息传递）和 `#68920`（HTTP 端点 TTFB 优化）也反映了对实时性和多代理协作的长期需求。

### 7. 用户反馈摘要

从 Issues 评论中提炼的真实用户痛点：

- **升级/回滚问题**：多个用户反映升级后出现严重回归（如 `#108435` 网关无法启动，`#38327` 谷歌 Vertex 模型报错 "Cannot convert undefined or null to object"），且回滚后仍遗留模块路径问题（`#92241`）。用户期盼更稳定的升级测试和兼容性保证。
- **配置迁移透明性**：`#90378` 中用户抱怨从 5.28 升级到 6.1 时 cron 存储静默迁移到 SQLite，且新作业默认使用 `delivery.mode=announce` 导致频道错误，缺乏迁移通知和配置保留。
- **文档与版本不一致**：`#48920` 指出 Live Docs 中已包含 `IsolatedSessions` 配置，但最新发布版 2026.3.13 中尚不支持，用户按文档操作后失败。
- **性能退化**：`#119087` 报告冷启动时间增加 2.5 倍，`#124788` 报告事件循环周期性阻塞，严重影响生产环境可用性。
- **Windows 兼容性**：`#119796` 和 `#86612` 分别报告 Windows 下测试拆卸失败和 Docker 容器重启循环，表明 Windows 支持仍有待加强。

### 8. 待处理积压

以下 Issue 长期未获响应或修复，需维护者关注：

- **#38327**（2026-03-06 创建，P1，回归）：“Cannot convert undefined or null to object” 在 2026.3.2 中因 Google Vertex 模型触发，已有 14 条评论，但无任何进展。
- **#48920**（2026-03-17 创建，P0，回归）：Live Docs 超前于发布版，导致用户配置失败，10 条评论，但维护者标记为“needs-maintainer-review”后无动作。
- **#53628**（2026-03-24 创建，P3，行为 bug）：`$XDG_CONFIG_HOME` 在安装 skill 时未被解析，13 条评论，无 fix PR。
- **#72015**（2026-04-26 创建，P1，可靠性）：`active-memory` 插件阻塞回复，多代理网关过载，11 条评论，无实质进展。
- **#74378**（2026-04-29 创建，P2，回归）：Windows 上 CLI 命令执行后 `node.exe` 进程残留，6 条评论，标签为 `maturity:stable` 但未修复。

这些长期未解决的 Issue 可能影响用户信任和项目声誉，建议维护团队优先分配资源进行排查和修复。

---

*数据来源：OpenClaw GitHub 仓库 (github.com/openclaw/openclaw) 截至 2026-08-21 的公开 Issues 和 Pull Requests。*

---

## 横向生态对比

好的，作为您的资深技术分析师，我已根据您提供的各项目日报，生成了以下横向对比分析报告。

---

### **个人 AI 助手/自主智能体开源生态横向对比分析报告 (2026-08-21)**

#### **1. 生态全景**

当前，个人 AI 助手与自主智能体开源生态呈现出 **“高活跃度与高风险并存”** 的态势。一方面，以 OpenClaw 为代表的核心项目社区规模庞大，功能迭代迅速，推动着网关级成本控制、多智能体协作等前沿方向。另一方面，大量项目均面临 **稳定性问题积压** 的挑战，P0/P1 级别的 Bug（如网关崩溃、事件循环阻塞、更新破坏性）修复周期长，严重影响了用户体验和项目声誉。与此同时，社区对 **安全加固**（如 IronClaw、Moltis）、**平台兼容性**（Windows、macOS）和 **开箱即用体验** 的呼声日益高涨，生态正从“功能创新”驱动，转向“功能创新与质量巩固并重”的阶段。

#### **2. 各项目活跃度对比**

| 项目名称 | 今日 Issues 活跃量 | 今日 PR 活跃量 | 版本发布 | 健康度评估 |
| :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | 极高 (500) | 极高 (500) | 无 | **亚健康**：活跃度最高，但 PR 合并率低 (33%)，P0 级 Bug 积压严重，维护者压力巨大。 |
| **NanoBot** | 低 (5) | 中 (29) | 无 | **健康**：响应积极，Bug 修复效率高，但 PR 积压需关注。 |
| **Hermes Agent** | 极高 (50) | 极高 (50) | 无 | **亚健康**：更新流程破坏性 Bug 是核心痛点，P0/P1 Bug 多，高活跃度伴随高风险。 |
| **PicoClaw** | 低 (0) | 低 (8) | 无 | **稳定**：活跃度低，主要进行依赖更新和长期功能收尾，需关注 Web UI 性能问题。 |
| **NanoClaw** | 低 (3) | 极高 (50) | 无 | **健康**：核心团队主导大规模审计修复，响应迅速，PR 活跃度高但合并窗口期较集中。 |
| **IronClaw** | 高 (10+) | 高 (17) | **有 (v1.3.0)** | **健康**：版本发布稳定，功能开发与基础架构并重，社区讨论深入，响应及时。 |
| **Moltis** | 低 (1) | 中 (8) | **有 (20260820.01)** | **健康**：安全响应迅速，持续修复具体问题，但长期 PR 积压。 |
| **CoPaw** | 高 (27) | 极高 (50) | **有 (v2.1.1-beta.1)** | **健康**：功能开发与稳定性修复并行，部分严重 Bug 缺乏修复方案。 |
| **ZeroClaw** | 极高 (50) | 极高 (50) | 无 | **亚健康**：聚焦代码质量清理，但 PR 合并率为 0，决策和合并流程可能成为瓶颈。 |

*注：活跃度定义基于日报中提及的Issue/PR更新数量，健康度综合了Bug严重程度、响应速度、版本发布节奏等因素。*

#### **3. OpenClaw 在生态中的定位**

OpenClaw 是生态中 **社区规模最大、功能最全面的通用型 AI 助手框架**，常被视为行业参照标准。

*   **优势**：在 **网关级成本控制**（`#42475`）、**跨编码文件名处理**（`#48788`）等前沿问题上拥有最深入的社区讨论，功能提案丰富，覆盖了从安全策略到 UI 体验的方方面面。
*   **技术路线差异**：相对于 IronClaw 强调的“安全沙箱”和“Agent 生命周期钩子”，或 NanoClaw 的“跨平台集成”，OpenClaw 更侧重于 **网关代理层的统一管理** 和底层核心协议的稳定性（如 SQLite 性能、事件循环）。
*   **社区规模对比**：从每日 Issue/PR 更新量（500+）看，其社区活跃度远超其他项目（多数在 50 左右），但高活跃度也带来了 **维护响应瓶颈**，合并率低、Bug 积压问题突出。

#### **4. 共同关注的技术方向**

多个项目不约而同地涌现出相似需求，标志着行业共识正在形成：

*   **成本控制与预算管理**：
    *   **OpenClaw** (Issue #42475): 网关级代理成本预算。
    *   **Hermes Agent** (PR #90286): 为 `/goal` 命令添加 Token 预算。
    *   **NanoClaw** (PR #3270): Token 用量追踪功能。
    *   **趋势信号**：开发者对 AI 服务运行成本的精细化控制需求已从“可选”变为“必需”。

*   **多智能体协作与调度**：
    *   **PicoClaw** (PR #423, 已关闭): 多智能体协作框架探索。
    *   **IronClaw** (Epic #7770): Agent 生命周期钩子（`AfterTurn`）。
    *   **ZeroClaw** (Issue #10025): 零配置 Agent Swarm。
    *   **趋势信号**：从“单个 Agent 完成任务”到“多个 Agent 协同工作”是明确的发展方向，`hook` 机制和 `swarm` 模式是两种主流实现路径。

*   **本地化部署与平台兼容性**：
    *   **IronClaw** (Issue #5998): 本地 MCP 服务器连接问题。
    *   **Hermes Agent** (Issue #87093, #86443): Debian 安装失败，Windows 更新破坏。
    *   **Moltis** (PR #468, 长期未合并): Windows Shell 钩子兼容性。
    *   **趋势信号**：开发者社区（尤其是企业用户）对在本地、Win/Mac/Linux 等异构环境下稳定运行 Agent 的需求极为迫切，这是项目从“玩具”走向“工具”的关键。

*   **代码质量与安全**：
    *   **ZeroClaw** (Issue #10118): Rust 反模式清理计划。
    *   **IronClaw** (PR #7777, #7778): 快速修复 Rust 编译器新 Lint 规则导致的 CI 阻塞。
    *   **Moltis** (PR #1216, #1222): 修复 Vault 认证漏洞，验证沙箱镜像。
    *   **趋势信号**：随着项目成熟，社区对代码可维护性和安全性的重视程度显著提升，系统性的“技术债务清理”成为常态。

#### **5. 差异化定位分析**

| 项目 | 功能侧重 | 目标用户 | 技术架构关键差异 |
| :--- | :--- | :--- | :--- |
| **OpenClaw** | **通用型、网关层** | 需要统一管理多种模型和渠道的高级开发者、团队 | 强调网关代理的集中管理和成本控制，社区最大，但架构复杂度高。 |
| **NanoBot** | **轻量、TUI** | 偏好命令行、追求轻量级体验的个人开发者 | 架构简洁，依赖少，更新迭代快，对 Docker 和通道兼容性有持续优化。 |
| **Hermes Agent** | **记忆、工具** | 注重 Agent 长期记忆和工具扩展能力的用户 | 以“全息记忆”和“Agent 协作”为特色，但更新流程和平台兼容性是短板。 |
| **PicoClaw** | **模型兼容性** | 嵌入式或资源受限场景，希望接入多种模型 | 项目体量较小，行动灵活，但社区活跃度低，功能开发节奏慢。 |
| **NanoClaw** | **平台集成** | 希望将 Agent 嵌入 Slack、WhatsApp、IDE 等平台的开发者 | 专注于渠道适配（“技能”体系），核心团队推动力强，修复效率高。 |
| **IronClaw** | **安全沙箱、企业级** | 对安全、隔离、可靠性有高要求的企业用户 | 核心优势在于安全沙箱（`Landlock`）、Agent 生命周期管理和严谨的 CI/CD。 |
| **Moltis** | **安全、渠道坚固** | 需要安全可靠消息通道的用户 | 对安全事故响应快，WhatsApp 等渠道的修复能力强，但功能更新节奏较慢。 |
| **CoPaw** | **性能、稳定性** | 需要长时间稳定运行、处理复杂任务的用户 | 侧重于性能优化（冷启动、长会话响应）和文件处理鲁棒性，版本发布稳定。 |
| **ZeroClaw** | **代码质量、架构设计** | 注重代码规范、参与前沿架构讨论的贡献者 | 极度重视技术规范和 RFC 流程，Rust 代码质量要求高，但合并效率低。 |

#### **6. 社区热度与成熟度**

*   **快速迭代期（高活跃，高风险）**：**OpenClaw**、**NanoClaw**、**ZeroClaw**。这些项目 PR 和 Issue 数量庞大，社区讨论热烈，但同时也面临 Bug 积压、合并效率低等“成长烦恼”。其中 **ZeroClaw** 处于“高活跃，零产出”的特殊状态，值得警惕。
*   **质量巩固期（稳定产出，聚焦修复）**：**IronClaw**、**Moltis**、**CoPaw**。这些项目实现了版本稳定发布，核心功能完善，当前工作重心在于修复具体 Bug、增强安全性和平台兼容性，是成熟度较高的表现。
*   **稳定维护期（低活跃，功能收尾）**：**PicoClaw**、**NanoBot**。这些项目活跃度较低，主要进行小范围修复和依赖更新，可能在等待下一个重大功能迭代。

#### **7. 值得关注的趋势信号**

1.  **“成本控制”成为标配**：从 OpenClaw 的网关预算到 NanoClaw 的 Token 追踪，AI 智能体的运营成本已成为开发者必须考虑的实际问题，未来项目的“成本控制”能力将直接影响其市场竞争力。
2.  **“多智能体协作”走向标准化**：IronClaw 的 `Agent 生命周期钩子` 和 ZeroClaw 的 `零配置 Swarm` 代表了两种不同的标准化路径。前者强调可编程的细粒度控制，后者追求开箱即用的快速体验，两者都值得开发者深入研究。
3.  **“本地化”与“平台兼容性”是分水岭**：无法在 Windows 上稳定运行或无法连接本地 MCP Server 的项目，将被排除在大量企业级和桌面级用户之外。这已成为项目从“原型”走向“产品”的关键分水岭。
4.  **“代码质量”是长期竞争力的基石**：ZeroClaw 的“反模式清理”和 IronClaw 的“快速修复 Lint 问题”表明，优秀的项目已经开始系统性地审视和优化自身代码库。对于开发者而言，选择代码质量高、架构清晰的项目，意味着更低的二次开发和维护成本。

**对 AI 智能体开发者的参考价值**：如果您追求**功能全面和社区支持**，OpenClaw 是首选，但需做好应对其稳定性和复杂性的准备。若您重视**安全和企业级特性**，IronClaw 和 Moltis 是更稳妥的选择。若您需要**轻量级或特定平台集成**，NanoBot 和 NanoClaw 值得关注。而**关注技术前沿和架构设计**的开发者，则可以从 ZeroClaw 和 IronClaw 的 RFC 讨论中汲取灵感。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

# NanoBot 项目动态日报 (2026-08-21)

## 1. 今日速览

过去 24 小时内，NanoBot 项目保持高活跃度：共处理 **5 条 Issues**（新开 3 条，关闭 2 条）和 **29 条 Pull Requests**（待合并 17 条，已合并/关闭 12 条）。社区贡献集中在 **Bug 修复**（尤其是 Docker OAuth 登录、流式重试逻辑、代理兼容性）和 **功能增强**（WebUI 可观测性、Telegram 贴纸回复、新供应商 SenseNova 支持）。**无新版本发布**，但多项修复已进入主干，项目稳定性进一步提升。

## 2. 版本发布

无。

## 3. 项目进展

今日合并/关闭的重要 PR 及对应 Issue 推进了以下方向：

- **稳定性修复**  
  - [#1203](https://github.com/HKUDS/nanobot/pull/1203) — 修复 Linux 上 `Event loop is closed` 异常（关闭，关联 Issue #550）。  
  - [#5452](https://github.com/HKUDS/nanobot/pull/5452) — TUI 退出时打印恢复会话命令，提升用户操作便利性。  
  - [#5240](https://github.com/HKUDS/nanobot/pull/5240) — 重构 WebUI 浮动控件，统一浮动面板样式与语义。  

- **Bug 修复闭合**  
  - [#5425](https://github.com/HKUDS/nanobot/issues/5425) — 支持 legacy `socks://` 代理 URL（已关闭）。  

- **功能合并**  
  - 无新功能 PR 合并，但多个 open 功能 PR （如 [#5420](https://github.com/HKUDS/nanobot/pull/5420) WebUI 可观测性、[#5387](https://github.com/HKUDS/nanobot/pull/5387) Telegram 贴纸）持续更新，等待最终审核。

项目整体在 **Bug 修复** 和 **代码质量** 上迈出坚实一步，12 个 PR 合并表明维护者响应积极。

## 4. 社区热点

- **Issue [#5444](https://github.com/HKUDS/nanobot/issues/5444)**（Open，评论 1 条）  
  **Docker 环境下 OpenAI OAuth 登录失败**。用户报告在 Docker 容器中运行 NanoBot 时，OAuth 回调流程无法完成，反映容器化部署的常见痛点。该问题尚未有 fix PR，社区关注度较高。

- **PR 系列（KDB-Wind 贡献）**  
  - [#5414](https://github.com/HKUDS/nanobot/pull/5414) （Slack 文件下载重定向验证）  
  - [#5413](https://github.com/HKUDS/nanobot/pull/5413) （Provider 异常时应用 fallback 策略）  
  - [#5412](https://github.com/HKUDS/nanobot/pull/5412) （Gateway 后台子进程日志刷新）  
  - [#5339](https://github.com/HKUDS/nanobot/pull/5339) （WebUI 临时聊天消息丢弃保护）  
  - [#5338](https://github.com/HKUDS/nanobot/pull/5338) （MCP OAuth 凭证保留）  
  这些 PR 均处于 open 状态，但评论数和更新时间显示出社区对 **安全性与错误处理** 的强烈需求。

- **流式重试 Bug（#5454 / #5455）**  
  Issue [#5454](https://github.com/HKUDS/nanobot/issues/5454) 报告了流式中间 `server_error` 时重试跳过的问题，PR [#5455](https://github.com/HKUDS/nanobot/pull/5455) 立即提交了修复方案，体现了社区快速响应的生态活力。

## 5. Bug 与稳定性

| 严重程度 | Issue / PR | 描述 | 状态 |
|----------|------------|------|------|
| 高 | [#5444](https://github.com/HKUDS/nanobot/issues/5444) | Docker 中 OpenAI OAuth 登录失败，容器化用户可能受阻 | 无 fix PR |
| 中 | [#5454](https://github.com/HKUDS/nanobot/issues/5454) | 流式中间 `server_error` 不重试，导致部分请求被丢弃 | 已有 fix PR [#5455](https://github.com/HKUDS/nanobot/pull/5455) |
| 中 | [#5457](https://github.com/HKUDS/nanobot/pull/5457) | 通道调度器异常边界未包裹，可能导致消息停止发送 | 已有 fix PR |
| 低 | [#5425](https://github.com/HKUDS/nanobot/issues/5425) | 传统 `socks://` 代理别名不被识别 | 已关闭 |
| 低 | [#5412](https://github.com/HKUDS/nanobot/pull/5412) | 后台子进程输出缓冲，日志延迟 | 已有 fix PR |

此外，PR [#5413](https://github.com/HKUDS/nanobot/pull/5413)、[#5339](https://github.com/HKUDS/nanobot/pull/5339) 等也在修复稳定的边界情况。

## 6. 功能请求与路线图信号

- **新供应商需求**  
  - [#5459](https://github.com/HKUDS/nanobot/issues/5459) — 请求原生 Google Vertex AI 支持 Claude 模型。目前仅通过第三方网关兼容，用户希望直接集成。  
  - [#5453](https://github.com/HKUDS/nanobot/pull/5453) — 已提交 **SenseNova（商汤日日新）** 供应商实现，支持 `sensenova-6.8-flash-lite` 等多模态模型，极有可能纳入下一版本。

- **付费集成探索**  
  - [#5447](https://github.com/HKUDS/nanobot/issues/5447) — 用户提出将 NanoBot 与 Solana x402 微支付安全扫描服务（ScanPay）集成，虽已关闭，但反映了社区对 **MCP 付费能力** 的兴趣。

- **WebUI 与聊天体验增强**  
  - [#5420](https://github.com/HKUDS/nanobot/pull/5420) — 回合可观测性（turn observability）和 **安全恢复**（safe recovery），允许用户查看中断的工作流。  
  - [#5387](https://github.com/HKUDS/nanobot/pull/5387) — Telegram 贴纸回复支持，丰富消息交互。

这些功能请求与 PR 表明 **模型供应商扩展**、**可观测性**、**支付集成** 是当前社区关注的重点方向。

## 7. 用户反馈摘要

从 Issue 评论和 PR 讨论中提炼的主要用户声音：

- **Docker 部署痛点**：用户 `Bennett-Yang` 在 [#5444](https://github.com/HKUDS/nanobot/issues/5444) 中提供了完整的 Docker 下 OAuth 失败日志（回调 URL 处理异常），期望官方提供容器化环境下的兼容性修复。
- **代理兼容性**：`pxy0592` 在 [#5425](https://github.com/HKUDS/nanobot/issues/5425) 指出 `socks://` 别名不被识别，导致自定义 OpenAI 兼容供应商在代理环境下无法工作。该问题已关闭，用户反馈积极。
- **流式重试逻辑**：`akinolur` 在 [#5454](https://github.com/HKUDS/nanobot/issues/5454) 中详细描述了只有内容流式开始前失败才重试的问题，并提交了修复 PR，体现了社区贡献者主动解决问题的行为。
- **新供应商需求**：`xuayan-nokia` 请求 Google Vertex AI for Claude，强调目前缺少第一方支持，反映出企业用户对多种云平台部署的诉求。

## 8. 待处理积压

以下长期未合并或存在冲突的 PR 需要维护者关注决策：

| PR | 主题 | 状态 | 备注 |
|----|------|------|------|
| [#5180](https://github.com/HKUDS/nanobot/pull/5180) | MCP SDK v2 迁移评估（最小方案） | Open, 冲突 | 与 #5179 竞争，需选择合并方向 |
| [#5179](https://github.com/HKUDS/nanobot/pull/5179) | MCP SDK v2 迁移（完整方案） | Open, 冲突 | 优先级 p1，影响 MCP 兼容性 |
| [#5338](https://github.com/HKUDS/nanobot/pull/5338) | MCP OAuth 凭证保留 | Open, 冲突 | 潜在数据安全风险，需尽快评审 |
| [#5379](https://github.com/HKUDS/nanobot/pull/5379) | memory 压缩输入保护 | Open, 冲突 | 影响记忆持久化可靠性 |
| [#5387](https://github.com/HKUDS/nanobot/pull/5387) | Telegram 贴纸回复 | Open | 功能已完整，等待合并 |
| [#5420](https://github.com/HKUDS/nanobot/pull/5420) | WebUI 回合可观测性 | Open | 大幅提升用户体验，建议优先审核 |

这些积压 PR 多数涉及 **MCP 升级**、**内存管理**、**渠道交互** 等核心模块，长时间未解决可能影响后续版本发布节奏。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我根据您提供的 Hermes Agent GitHub 数据，为您生成 2026-08-21 的项目动态日报。

---

### **Hermes Agent 项目日报 | 2026-08-21**

---

#### **1. 今日速览**

今日 Hermes Agent 项目社区活跃度极高，Issues 和 PRs 更新量均达到 50 条。项目当前面临的主要挑战集中在**稳定性与兼容性**上，包括 Debian 安装流程阻塞、Windows 平台更新机制破坏桌面应用，以及 SQLite 数据库损坏等关键问题。尽管社区反馈积极，贡献者提交了大量修复与功能 PR，但高优先级（P0/P1）的 Bug 积压对用户体验造成了显著影响，项目健康度呈 **“高活跃，高风险”** 状态。

#### **2. 版本发布**

无新版本发布。

#### **3. 项目进展**

今日合并/关闭了 5 个 PR，标志着项目在以下方面取得了进展：

- **配置系统增强**：PR #87466 已合并，实现了命名配置文件的“可选”根主模型继承，允许用户更灵活地管理不同场景下的模型配置，提升了配置复用性。
- **新功能落地**：PR #91145 在新配置文件（如 Bot Mode 新 Agent）中默认集成了“全息记忆”激活，强化了长期记忆能力。PR #90287 实现了会话转向（`session.steer_peer` / `steer_broadcast`）功能，扩展了 Agent 间的协作模式。
- **UI/UX 改进**：PR #89687 为桌面端群聊功能添加了实时活动芯片，可显示当前回合 Bot 的“思考/写作/行动”状态，改善了用户等待体验。
- **功能提案与优化**：PR #90286 和 #90283 分别提出了 `/goal` 命令的 Token 预算和 `/refine` 命令的撤销功能，虽未合并，但标志着项目路线图的持续演进。

这些进展表明项目在功能丰富度和配置灵活性上正稳步向前迈进。

#### **4. 社区热点**

今日讨论最活跃的议题高度集中在 **“更新与安装”** 这一核心体验上。

- **🔥 [Issue #87093] Debian 安装失败**：以 14 条评论高居榜首。用户报告在 Debian 13.6 上通过官方脚本安装失败，问题卡在 `uv.lock` 和 `npm install` 步骤。这触及了项目入门体验的根本问题，引发了广泛关注。
    [链接: NousResearch/hermes-agent Issue #87093](https://github.com/NousResearch/hermes-agent/issues/87093)

- **🔥 [Issue #87697] 本地 LLM 流式传输被取消**：8 条评论揭示了更新后 Hermes 客户端在约 1.5 秒后主动取消本地 Ollama 后端的流式请求，导致 `<unused49>` 标记循环。这表明最近的更新可能引入了与本地推理服务的兼容性回归。
    [链接: NousResearch/hermes-agent Issue #87697](https://github.com/NousResearch/hermes-agent/issues/87697)

- **🔥 [Issue #86443] 更新后桌面应用消失**：6 条评论详细描述了 `hermes update` 在 Windows 上的破坏性行为：当 Electron 重建失败时，它会删除旧的 `Hermes.exe`，但重建失败后却返回成功状态码 (0)，使用户陷入无桌面应用可用的困境。
    [链接: NousResearch/hermes-agent Issue #86443](https://github.com/NousResearch/hermes-agent/issues/86443)

**诉求分析**：社区的核心诉求是**稳定、可靠的核心功能**，特别是**安装、更新与本地模型集成**。任何对基础流程的破坏都会立即引发大量用户不满。

#### **5. Bug 与稳定性**

今日报告的 Bug 数量多、影响面广，按严重程度排列如下：

- **P0 (严重)**:
    - **[Issue #90971] Anthropic 缓存控制非幂等**：`apply_anthropic_cache_control` 函数在已装饰的输入上重复调用会出错。**已有 fix PR #90972**。
        [链接: NousResearch/hermes-agent Issue #90971](https://github.com/NousResearch/hermes-agent/issues/90971)
        [链接: NousResearch/hermes-agent PR #90972](https://github.com/NousResearch/hermes-agent/pull/90972)

- **P1 (高)**:
    - **[Issue #87093] Debian 安装失败**：阻塞新用户入门。**目前无直接 fix PR**。
        [链接: NousResearch/hermes-agent Issue #87093](https://github.com/NousResearch/hermes-agent/issues/87093)
    - **[Issue #86443] Windows 更新后桌面应用丢失**：破坏性极强，用户无应用可用。**已有对应 fix PR #44234**，但尚未合并。
        [链接: NousResearch/hermes-agent Issue #86443](https://github.com/NousResearch/hermes-agent/issues/86443)
        [链接: NousResearch/hermes-agent PR #44234](https://github.com/NousResearch/hermes-agent/pull/44234)
    - **[Issue #90950] SQLite 数据库损坏**：`state.db` 在并发写入时损坏，影响会话持久化。**目前无直接 fix PR**。
        [链接: NousResearch/hermes-agent Issue #90950](https://github.com/NousResearch/hermes-agent/issues/90950)

- **P2 (中, 部分与 P1 重叠)**:
    - **[Issue #87697] 本地 LLM 流式传输取消**：影响本地模型使用体验。
    - **[Issue #90134] Windows 桌面构建失败**：`blockmap.js` 错误阻塞桌面应用构建。
        [链接: NousResearch/hermes-agent Issue #90134](https://github.com/NousResearch/hermes-agent/issues/90134)
    - **[Issue #90829] 桌面更新后重建失败**：指出根因是 `node_modules` 损坏导致的 `get-windows` 门控失败。**已有 fix PR #91063**。
        [链接: NousResearch/hermes-agent Issue #90829](https://github.com/NousResearch/hermes-agent/issues/90829)
        [链接: NousResearch/hermes-agent PR #91063](https://github.com/NousResearch/hermes-agent/pull/91063)

- **P3 (低)**:
    - 多个 P3 级别的 Bug，如 Discord 上下文丢失、Windows Snap 功能破坏、桌面端搜索显示错误等，虽然影响范围有限，但反映出在非核心功能上仍有不少细节问题。

#### **6. 功能请求与路线图信号**

今日涌现了多个功能请求，部分已有对应的 PR，反映出社区对项目扩展方向的期待：

- **会话协作与转向**：`session.steer_peer` / `steer_broadcast` 功能 (PR #90287) 已作为提案合并，将增强 Agent 间的指挥与协作能力。
- **Token 预算与成本控制**：社区提出了为 `/goal` 命令添加 Token 输入/输出预算的请求 (PR #90286)，表明用户对 Agent 运行成本的控制需求日益增长。
- **可撤销操作**：`/refine` 命令的撤销功能 (PR #90283) 被提出，旨在为用户提供更安全的“记忆/技能”编辑体验。
- **网络搜索集成**：PR #81393 提出添加 DeepSeek 网络搜索提供者插件，表明社区希望扩展 Agent 获取实时信息的能力。
- **安全与权限控制**：PR #91139 提出了限制 MCP 目录环境变量写入，是加强平台安全性的重要信号。

**路线图判断**：这些功能请求，特别是关于协作、成本控制和可撤销操作的提案，很可能被纳入项目下一阶段的开发计划中。

#### **7. 用户反馈摘要**

从今日的 Issues 评论中，可以提炼出以下用户反馈：

- **核心痛点**：**“更新”是最大的痛点**。Windows 用户 (Issue #86443, #44225, #90829) 和 Debian 用户 (Issue #87093) 都遭遇了更新流程的严重破坏。用户反馈情绪激烈，部分使用“destroy”、“spun down”等词，反映出对稳定性的强烈不满。
- **使用场景**：用户场景多样，包括个人桌面使用、本地开发、远程 WSL 后端、以及通过 Discord 等平台进行 Bot 模式交互。这表明用户基础广泛，但项目在不同平台和场景下的体验一致性有待加强。
- **满意度**：用户对项目的**功能丰富度**和**创新性** (如 Agent 协作、全息记忆) 持肯定态度，但对**基础稳定性**和**平台兼容性** (尤其是 Windows) 表示失望。高频的更新问题严重影响了用户满意度和信任度。

#### **8. 待处理积压**

以下为长期未响应的重要 Issue 或 PR，需提醒维护者重点关注意：

- **📌 [Issue #44225] (P2, 2026-06-11)**：Windows 桌面更新失败后 `Hermes.exe` 被删除。与今日 #86443 问题高度相关，其修复 PR #44234 已存在两个多月仍未合并，需优先处理。
    [链接: NousResearch/hermes-agent Issue #44225](https://github.com/NousResearch/hermes-agent/issues/44225)

- **📌 [Issue #46082] (P2, 2026-06-14)**：Hermes Dashboard 内存泄漏，可增长至 5.2GB 并被 OOM 杀死。这是一个存在两个多月的严重性能问题，目前无对应 PR，可能需重新评估优先级。
    [链接: NousResearch/hermes-agent Issue #46082](https://github.com/NousResearch/hermes-agent/issues/46082)

- **📌 [PR #44234] (P2, 2026-06-11)**：修复桌面更新失败后应用被删除的 PR，与今日多个更新 Bug 直接相关，合并此 PR 可解决一系列问题。
    [链接: NousResearch/hermes-agent PR #44234](https://github.com/NousResearch/hermes-agent/pull/44234)

- **📌 [PR #71486] (P2, 2026-07-25)**：修复会话压缩恢复的 PR，涉及会话状态管理，长期未合并可能影响部分用户的大会话体验。
    [链接: NousResearch/hermes-agent PR #71486](https://github.com/NousResearch/hermes-agent/pull/71486)

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我将根据您提供的 PicoClaw 项目数据，为您生成一份结构清晰、数据驱动的项目动态日报。

---

### PicoClaw 项目动态日报
**日期：** 2026-08-21

---

### 1. 今日速览

今日项目整体活跃度一般，主要活动集中在依赖项的自动化更新上，共产生了 8 个相关 PR 请求。核心功能开发方面，过去 24 小时无新版本发布，且无手动提交的代码合并或新功能 PR 推进。社区方面，用户反馈主要集中在长期存在的 Web UI 卡顿问题（#3281），以及两项新的功能请求。虽然项目维护者尚未直接介入，但来自社区贡献者的一项关于多智能体协作框架的长期 PR（#423）已于今日正式关闭，标志着该项目一个重要功能的开发周期告一段落。

### 2. 版本发布

**无。** 过去 24 小时内无新版本发布。

### 3. 项目进展

今日合并或关闭了 3 个 PR，其中 2 个为重要的功能或修复性合并，1 个为长期未完成的功能性 PR 关闭。

- **重要功能合并：** `feat: add anthropic-messages protocol for native Anthropic API format`（#1158）已被合并。此 PR 增加了对 Anthropic 原生 Messages API 格式的支持，解决了部分代理服务无法使用的问题（Fixes #269）。这是项目在模型兼容性上的重要一步，扩大了可接入的 LLM 服务范围。
- **稳定性修复合并：** `fix(web): repair unparseable pnpm-lock.yaml`（#3318）已被合并。该 PR 修复了 Web 前端 `pnpm-lock.yaml` 文件中的重复映射键错误，解决了 `pnpm` 包管理器无法解析该文件的问题，保障了前端开发环境的稳定。
- **长期 PR 关闭：** `WIP: feat: base multi-agent collaboration framework`（#423）已关闭。该 PR 自2026年2月开启，今日正式关闭，虽然未合并，但其提出的“黑板模式”、“代理交接”等概念可能为未来相关开发提供了参考和基础。

**项目整体向前迈进：** 通过合并 #1158 和 #3318，项目提升了模型兼容性和开发环境稳定性。今日 PR 流向显示，项目维护重心在于集成社区贡献的修复，并为后续功能（如多智能体）的完成画上了一个句号。

### 4. 社区热点

今日社区讨论的热点主要集中在一个长期存在的 Bug 报告上。

- **Issue #3281：** `[BUG] Web UI chat input is very laggy when history has a little bit long`
    - **链接：** [sipeed/picoclaw Issue #3281](https://github.com/sipeed/picoclaw/issues/3281)
    - **分析：** 该问题已存在一个月，获得了 6 条评论和 1 个 👍。用户（xpader）报告了在对话历史较长时，Web UI 输入框出现严重卡顿的问题。这是直接影响用户体验的痛点，尤其在长时间对话场景下。虽然目前没有直接的 fix PR，但该问题若持续被关注，可能成为下一个优化重点。

### 5. Bug 与稳定性

今日报告的 Bug 数量较少，但严重程度不容忽视。

| 严重程度 | 问题链接 | 描述 | 是否有 Fix PR | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| 中 | [Issue #3281](https://github.com/sipeed/picoclaw/issues/3281) | **Web UI 输入框在长对话历史时严重卡顿** | 暂无 | 影响核心用户体验，需要优化前端渲染或历史记录管理逻辑。 |
| 低 | [PR #3318](https://github.com/sipeed/picoclaw/pull/3318) | **pnpm-lock.yaml 文件解析错误** | 已合并 | 属于开发环境问题，已通过修复 PR 解决。 |

### 6. 功能请求与路线图信号

今日社区提出了两个新的功能请求，为项目未来的发展方向提供了信号。

- **通用音频转录支持：** [Issue #3331](https://github.com/sipeed/picoclaw/issues/3331) 用户 `stanislavvv` 提出，希望支持任何兼容 OpenAI `/audio/transcriptions` 端点的模型，而不仅仅局限于名字包含 `*-whisper-*` 的模型。这反映了用户对更灵活、更现代语音模型支持的需求。
- **动态模型覆盖支持：** [Issue #3330](https://github.com/sipeed/picoclaw/issues/3330) 用户 `v2up-32mb` 提出，希望 `delegate`、`spawn`、`subagent` 等工具能够在调用时动态指定模型。这显示了用户对更精细控制 AI Agent 行为的需求，尤其是在多智能体场景下。

**路线图信号分析：** 这两个功能请求，与今日合并的 Anthropic 协议支持（#1158）以及长期存在的多智能体框架（#423）方向一致，都指向了 **“模型灵活性”**和 **“多智能体编排能力”** 是项目当前社区呼声较高的方向。这些功能很可能被纳入后续版本规划。

### 7. 用户反馈摘要

从今日的 Issues 中，可以提炼出以下用户反馈：

- **核心痛点：** Web UI 前端性能是当前最突出的用户体验问题。用户在长时间对话后感到输入卡顿（来自 #3281），这可能是由前端渲染效率或历史消息管理机制不当导致的。
- **功能期望：** 用户对模型的兼容性和灵活性有更高期待，希望不再局限于特定的模型命名规则（如 `whisper`），并希望能在更细粒度的层面（如调用 `delegate` 工具时）控制所使用的模型（来自 #3330, #3331）。
- **使用场景：** 用户利用 PicoClaw 构建复杂的多 Agent 系统，并希望通过 Agent 间的协作（`delegate`, `spawn`）和调用外部语音识别服务来完成更复杂的任务。

### 8. 待处理积压

以下是一些长期未响应或未更新，可能需要注意的 Items：

- **依赖更新 PR（5 个）：** 由 `dependabot[bot]` 创建的 5 个依赖更新 PR（[#3332](https://github.com/sipeed/picoclaw/pull/3332), [#3333](https://github.com/sipeed/picoclaw/pull/3333), [#3334](https://github.com/sipeed/picoclaw/pull/3334), [#3335](https://github.com/sipeed/picoclaw/pull/3335), [#3336](https://github.com/sipeed/picoclaw/pull/3336)）均已存在一周且处于 `stale` 状态。这些更新涉及 AWS SDK、Anthropic SDK 和 Matrix 库，建议维护者尽快审视并合并，以避免依赖过时带来的安全风险或兼容性问题。
- **功能请求（2 个）：** [Issue #3330](https://github.com/sipeed/picoclaw/issues/3330) 和 [Issue #3331](https://github.com/sipeed/picoclaw/issues/3331) 均为社区提出的合理功能请求，目前仅有 1 条评论，建议维护者给予官方回复，明确是否接受、拒绝或纳入路线图，避免社区贡献者因得不到反馈而流失。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，根据您提供的 NanoClaw 项目数据，我为您生成了 2026-08-21 的项目动态日报。

---

## NanoClaw 项目动态日报 | 2026-08-21

### 1. 今日速览

今日项目活跃度极高，核心团队正在进行一项大规模的代码审计与修复战役，涉及多个官方技能（Skill）的稳定性、兼容性和文档完善。过去24小时内，共有 **50 条 PR** 被更新，其中 **16 条已合并或关闭**，**34 条待合并**，显示了密集的并行开发与审核工作。尽管社区提交的 Issue 数量不多（3条），但其中包含一个关于 WhatsApp 媒体附件的关键 Bug，已有对应的修复 PR。项目整体处于快速迭代和修复技术债务的活跃期，健康度良好。

### 2. 版本发布

无新版本发布。

### 3. 项目进展

今日合并/关闭的 PR 主要集中在社区贡献的长期功能以及核心团队大规模审计修复的结果。

- **长期功能 PR 合并**：一个长期开放的功能 PR **#1311 "Feature create new session"** 终于被合并，为项目增加了创建新会话的核心能力。
- **核心团队审计修复（“Stacked on #3408”系列）**：核心团队成员 `gavrielc` 主导了一系列密集的修复 PR（#3413 至 #3421），这批 PR 基于 `#3408` 进行堆叠，旨在修复一批官方技能中存在的配置不生效、文件路径错误、测试不完善、文档不准确等问题。涉及的技能包括 `add-vercel`、`add-clidash`、`add-atomic-chat-tool`、`add-ollama-tool`、`add-dashboard`、`add-tavily-tool`、`add-anydoc`、`add-macos-statusbar` 等。这些修复对提升项目的稳定性和开箱即用体验至关重要，标志着项目正积极清理历史遗留问题。
- **Slack 一键部署文档**：PR **#3421** 被合并，完善了 Slack 一键部署的文档和设置流程，降低了用户的上手门槛。

通过这些修复，项目在多个官方技能的可靠性、配置正确性和文档一致性上迈出了一大步。

### 4. 社区热点

今日讨论热度最高的议题集中在 **Slack 平台的路由 Bug** 和 **WhatsApp 集成问题**上。

- **Slack 线程误触发 Bug**：Issue **#3369** 报告了 `mention-sticky` 模式与 `accumulate` 策略结合时，Agent 会在未被提及的线程中回复的问题。该问题触及了会话管理和消息路由的核心逻辑，引发了社区和技术团队的关注。对应的修复 PR **#3422** 已经提交，标题为 “[fix(router): mention-sticky subscribes on a mention, not on a session…]”，直接回应了此 Issue。
- **WhatsApp 附件不可达 Bug**：Issue **#2715** 指出，通过 WhatsApp 发送的图片、文档等附件无法被 Agent 访问，因为文件被保存到了容器未挂载的目录。这直接影响核心功能，是用户反馈的一大痛点。对应的修复 PR **#3401** 也已提交，尝试解决兼容性问题。

这两个 Issue 都迅速获得了修复 PR，体现了项目对关键社区反馈的响应速度。

### 5. Bug 与稳定性

今日主要报告了 2 个新的 Bug，且均有对应的修复 PR 提交。

| 严重程度 | Issue / PR | 问题描述 | 状态 |
| :--- | :--- | :--- | :--- |
| **严重** | Issue #2715 | **WhatsApp 媒体附件无法访问**：文件被下载到容器外的目录，导致 Agent 无法处理用户发送的图片、文档和音频。 | 待修复，PR #3401 已提交 |
| **中等** | Issue #3369 | **Slack 线程误触发**：在 `mention-sticky` 模式下，Agent 错误地在未被提及的线程中开始回复。 | 待修复，PR #3422 已提交 |
| **已修复** | Issue #2606 | **`engage_mode='always'` 静默失效**：该模式未在路由器的 `evaluateEngage()` 函数中被处理，导致所有消息被静默丢弃。 | 已关闭，问题已在上一个迭代中修复 |

此外，`gavrielc` 提交的系列修复 PR（#3413-#3420）也修复了多个技能中存在的配置不生效、测试不完善等隐蔽性 Bug，大幅提升了稳定性。

### 6. 功能请求与路线图信号

今日无新的社区功能请求，但核心团队提交的 PR 揭示了项目未来的发展方向。

- **Cursor Agent SDK 集成**：PR **#3356** 和 **#3355** 正在推进对 **Cursor Agent SDK** 的支持，这标志着 NanoClaw 正从单一聊天平台 Agent 向更广泛的 IDE/开发环境 Agent 扩展。这是一个重要的路线图信号，表明项目旨在成为跨平台的 AI 助手层。
- **Token 用量追踪**：PR **#3270** 仍在开发中，该功能旨在为 Agent 增加 Token 消耗追踪能力，对于运营和成本控制有重要意义。
- **“为什么”技能**：PR **#3189** 提出的 `add-why` 技能，旨在向用户解释 Agent 对某条消息的处理逻辑，这对于提升 Agent 的可解释性和用户信任非常有价值。

这些 PR 表明，项目社区和核心团队正在积极探索 Agent 的跨平台部署、可观测性和可解释性，这些都可能成为未来版本的核心特性。

### 7. 用户反馈摘要

从今日的 Issue 和 PR 评论中，可以提炼出以下几个方面：

- **关键痛点**：
    - **WhatsApp 集成体验**：用户 `jon-ruth` 报告了 WhatsApp 附件无法使用的问题，这是在实际使用中遇到的严重阻碍，直接影响了消息多模态交互能力。
    - **Slack 配置困惑**：PR **#3423** 的提交者 `marcelomarra` 发现 `/add-slack` 命令的文档中遗漏了所需的 Bot Scope，这增加了用户配置的难度和出错概率。
    - **多实例部署问题**：在 PR #3419 的修复中，提到了 `ncl` 工具在多实例部署时可能读取错误的数据库，这反映了高级用户在生产环境中遇到的复杂性问题。
- **期望与诉求**：社区对功能的完善度和文档的准确性有较高期待。核心团队发布的大规模审计修复，正是对这一诉求的积极回应。

### 8. 待处理积压

目前无长期未响应且被标记为重要的 Issue 或 PR。今日的所有活跃 Issue 均已获得快速的修复 PR 回应。不过，以下 PR 虽然仍在积极迭代，但因其重要性，值得持续关注：

- **PR #3270**：`feat/ncl token usage`，这是一个重要的附加功能，自 8 月 16 日创建以来，仍在讨论和修改中，尚未合并。
- **PR #3189**：`feat(skill): add-why`，这是一个极具创新性的技能，自 8 月 5 日创建，至今仍在开放状态，可能需要更多社区讨论和功能验证。

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

好的，作为AI智能体与个人AI助手领域开源项目分析师，我将根据您提供的IronClaw GitHub数据，生成一份结构清晰、数据驱动的项目动态日报。

---

## IronClaw 项目动态日报 | 2026-08-21

### 1. 今日速览

项目今日活跃度极高，核心团队与社区贡献者共同推动多项关键功能与基础架构的进展。**过去24小时内，代码库合并/关闭了17个PR，并发布了新的稳定版v1.3.0**，修复了关键的升级问题。功能开发方面，**“永恒沙箱”** 和 **“Agent生命周期钩子”** 两大核心Epic均有实质性推进。同时，CI/CD流水线因Rust 1.98编译器更新出现短暂阻塞，但已通过社区协作在当天内修复，展现了项目良好的响应能力。总体来看，项目正处于功能密集开发与质量巩固并重的阶段，社区健康度良好。

### 2. 版本发布

- **ironclaw-v1.3.0 (1.3.0)**
  - **发布日期:** 2026-08-19
  - **发布说明:**
    - 这是一个从候选版本 `1.3.0-rc.2` 升级而来的稳定版。
    - 主要修复了从 `1.2` 版本升级时，因无法正确处理扩展的 `activation_state` 字段而导致 **启动崩溃循环** 的问题。
    - 包含了在 `rc.2` 中验证过的所有容器修复和升级改进。
  - **迁移注意事项:** 从1.2.x版本升级的用户直接使用此版本，即可解决升级后可能遇到的启动崩溃问题。

### 3. 项目进展

今日合并/关闭的重要PR显示了项目在代码质量、文档和关键功能上的稳步推进。

- **基础架构与稳定性:**
  - **[#7777](https://github.com/nearai/ironclaw/pull/7777) & [#7778](https://github.com/nearai/ironclaw/pull/7778):** 快速修复了因Rust 1.98稳定版编译器发布新Clippy lint规则导致的CI阻塞，确保所有分支的合并队列恢复畅通。
  - **[#7763](https://github.com/nearai/ironclaw/pull/7763):** 合并了子代理（subagent）设计文档，将7个分散、存在矛盾的设计文档合并为一份权威的README，净减少 **9,713行** 文档，极大降低了新贡献者的理解门槛。
- **功能与特性:**
  - **[#7729](https://github.com/nearai/ironclaw/pull/7729):** 实现了自动化（Automations）的“立即运行”功能，用户现在可以在WebUI或通过API手动触发一个自动化任务，无需等待其原有计划。
  - **[#7738](https://github.com/nearai/ironclaw/pull/7738):** 为Slack扩展的管理配置页面增加了字段级别的帮助提示文本，简化了运维人员的配置过程。
- **代码质量与重构:**
  - **[#7304](https://github.com/nearai/ironclaw/pull/7304):** 优化了WebChat的登录页面UI，将OAuth登录按钮置于更优先的位置，改善了用户体验。
  - **[#7755](https://github.com/nearai/ironclaw/pull/7755) (已关闭):** 清理了Turn/Subagent词汇表中的重复类型定义，减少了代码冗余。

### 4. 社区热点

过去24小时内，讨论最为活跃的议题集中在核心架构的设计与长期悬而未决的痛点。

- **#5998 [本地MCP服务器连接问题](https://github.com/nearai/ironclaw/issues/5998):** 该Issue存在已超过一个月，讨论仍在持续。核心诉求是用户无法在本地运行MCP（Model Context Protocol）服务器并与IronClaw交互，因为系统拒绝了`stdio`和`http://127.0.0.1`的通信方式。这表明社区对本地开发、测试及私有数据链结的需求非常迫切，是目前一个显著的痛点。
- **#7732 [永恒沙箱Epic](https://github.com/nearai/ironclaw/issues/7732):** 这个Epic下的讨论非常活跃，已有8条评论。核心是希望实现一个持久化的、基于用户的沙箱环境，替代当前每次执行shell命令都创建和销毁容器的模式。背后反映了社区对更稳定、更高效的开发环境和工作流的期待。
- **#7770 [Agent生命周期钩子Epic](https://github.com/nearai/ironclaw/issues/7770):** 作为一个新开的Epic，短时间内就获得了3条评论，说明社区对扩展Agent行为（如“在每次turn之后执行X”）的`hook`机制非常感兴趣，希望有更灵活的方式来定制Agent的行为，而不是修改核心引擎。

### 5. Bug 与稳定性

今日报告了多个Bug，涵盖从核心运行时到前端UI的多个层面。

- **严重**
  - **#7783 [LLM超时策略缺陷](https://github.com/nearai/ironclaw/issues/7783):** 结构化输出的最终化阶段无法测量首字节时间（TTFT），导致重试预算无法适配截止时间，一次传输卡顿即可导致整个运行失败。**此Bug风险高，目前尚无修复PR。**
  - **#7776 [内存写入并发问题](https://github.com/nearai/ironclaw/issues/7776):** `memory.write` 在全文档重写模式下，虽然使用了CAS（比较并交换）防止写入撕裂，但未能防止并发写入覆盖，存在数据丢失风险。**此Bug由PR #7765的代码审查发现，尚未修复。**
  - **#7775 [无界运行能力门控问题](https://github.com/nearai/ironclaw/issues/7775):** 当一个“无界运行”（Unbound run）遇到需要能力门控（gate）的情况时，会直接中止，而不是优雅地跳过该能力，导致后台任务失败。**此Bug是#7770 Epic中一个故意留下的开放决策，尚无修复PR。**
- **中等**
  - **#7308 [Attio MCP OAuth注册失败](https://github.com/nearai/ironclaw/issues/7308) (已关闭):** 修复了Attio扩展的OAuth注册问题，其根本原因是作用域（scope）无效。
- **较低**
  - **#7769 [扩展配置界面状态反馈缺失](https://github.com/nearai/ironclaw/issues/7769):** 扩展配置API会返回设置阶段和阻塞项，但WebUI的配置界面未能正确处理所有阻塞类型，可能导致用户误以为配置完成。**已有修复PR [#7772](https://github.com/nearai/ironclaw/pull/7772)。**
  - **#7767 [自动化测试时区依赖](https://github.com/nearai/ironclaw/issues/7767):** 自动化Presenter的日期测试假定使用UTC时区，导致在非UTC时区（如`Asia/Shanghai`）运行测试失败。**已有修复PR [#7774](https://github.com/nearai/ironclaw/pull/7774)。**

### 6. 功能请求与路线图信号

结合今日提交的PR和Issue，项目未来的功能方向十分清晰。

- **核心功能持续演进:**
  - **持久化沙箱 (#7732):** 对应的第二步PR **[#7779](https://github.com/nearai/ironclaw/pull/7779)** 已提交，旨在通过引入托管在每个用户下的代理（`iron-proxy sidecar`）来路由沙箱流量，实现网络隔离和持久化。
  - **Agent生命周期钩子 (#7770):** 第一阶段PR **[#7765](https://github.com/nearai/ironclaw/pull/7765)** 已提交，实现了`AfterTurn`钩子点，并首次在“记忆整理”场景中应用，表明此功能很可能进入v1.4.0版本。
- **WebUI设计系统巨幅更新:**
  - **设计系统Epic (#7038, #7781, #7782):** 多个相关PR和Issue进入活跃状态。`Storybook`集成 (PR [#7257](https://github.com/nearai/ironclaw/pull/7257), [#7750](https://github.com/nearai/ironclaw/pull/7750)) 和UI重构 (PR [#7773](https://github.com/nearai/ironclaw/pull/7773)) 正在推进，表明WebUI将迎来一次彻底的视觉和交互升级，并被标记为v1.4.0的重要部分。
- **通知中心与用户体验:**
  - **通知系统 (#7688, #7698, #7699):** 多个关于通用通知收件箱的PR和Issue正在合并或待合并，预示着未来将有一个统一的、带状态管理的通知中心，用于处理来自Agent、自动化任务和系统的各种消息。

### 7. 用户反馈摘要

从近期的Issues评论中可以提炼出以下用户反馈：

- **核心痛点：** 本地MCP服务器支持缺失（#5998）是讨论最久的痛点，严重影响了开发者和需要本地数据处理的用户。用户希望找到一个在本地开发、测试MCP连接的工作路径。
- **使用场景：** 用户强烈需要一个**持久化的、隔离的开发环境**（#7732），而不是每次执行命令都重新创建沙箱。这反映了从“试用”到“深度开发”的场景转变。
- **满意度：** 对于自动化任务，用户长期以来只能查看、暂停、恢复，而无法手动触发（#7193）。此次“立即运行”功能的实现，将直接提升用户对自动化功能的满意度。
- **对负面反馈的处理：** 一个关于Attio MCP的OAuth注册失败问题（#7308）已被修复和关闭，说明项目团队对用户报告的配置问题响应迅速。

### 8. 待处理积压

- **重要长期未响应Issue:**
  - **#5998 [本地MCP服务器连接问题](https://github.com/nearai/ironclaw/issues/5998):** 这是一个存在超过一个月的核心痛点，虽然讨论热烈，但至今没有明确的修复计划或PR。建议维护者尽快给出设计方案或临时解决方案，以安抚社区情绪。
- **待合并的长期PR:**
  - **#7491 [核心编码工具重构](https://github.com/nearai/ironclaw/pull/7491):** 这是一个大型PR，旨在统一和简化Agent的编码工具接口。它已开放超过9天，且标签为`size: XL`，风险`medium`。建议尽快安排审查，以避免产生大量代码冲突，并让社区能尽早基于新接口进行开发。

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

# LobsterAI 项目动态日报 (2026-08-21)

## 今日速览
- 过去24小时项目活跃度中等，共处理 **2 条 Issues** 和 **7 条 Pull Requests**，其中 **6 条 PR 已合并/关闭**，显示团队在持续推进修复与优化。
- 所有 Issues 和 PR 均为旧任务（创建于4月初）的重新激活或最终关闭，表明项目正集中清理历史积压。
- 核心进展集中在 **Agent 技能同步、定时任务通知 Bug、文件预览功能、设置面板搜索** 等用户体验改进，以及 **macOS 打包修复** 等平台兼容性工作。
- 无新版本发布，但多项修复已合并，预计将在下个版本中集成。

## 版本发布
**无**（过去24小时无新版本发布）

## 项目进展
今日合并/关闭的 **6 个 PR** 覆盖以下关键改进：

### 1. Agent 技能同步修复
- **PR #1545** (已合并)：修复 Agent 编辑技能后徽章不及时更新的问题，同步 `activeSkillIds` 状态。
- **PR #1560** (已合并)：修复在“我的Agent”界面编辑后点击原 Agent 无法切回聊天界面的问题。

### 2. 引擎启动交互增强
- **PR #1546** (已合并)：引擎启动超时（>30秒）后提供“取消启动”和“查看日志”按钮，避免用户长时间等待。

### 3. 定时任务通知 Bug 修复
- **PR #1547** (待合并)：修复通知渠道选择“不通知”后无法保存的问题，仅需 +2 行代码改动。

### 4. 文件预览 & 设置面板优化
- **PR #1553** (已合并)：为 Write 工具产物添加内联文件卡片及可拖拽预览面板，支持 Markdown、HTML、代码等格式。
- **PR #1557** (已合并)：设置面板侧栏增加搜索筛选功能，支持多关键词 AND 匹配，提升设置查找效率。

### 5. 打包兼容性修复
- **PR #1555** (已合并)：修复 macOS 上 `npm run dist:mac:x64` 打包失败，补充 `shasum` 兼容脚本。

> 项目整体向前迈出重要一步：**用户交互细节（技能切换、定时任务、设置查找）与文档预览能力**均得到实质性提升，同时修复了 macOS 打包阻塞问题。

## 社区热点
今日最活跃的 Issue 为 **#1556**（文档指南 404 问题），虽然仅 2 条评论，但属于用户直接反馈的“文档断链”问题，影响新用户上手体验。PR 方面 **#1553**（文件预览功能）对应了 Issue #1552 的长期需求，获得社区认可。

- [Issue #1556: IM机器人配置指南404](https://github.com/netease-youdao/LobsterAI/issues/1556)
- [PR #1553: Write工具文件卡片及分屏预览面板](https://github.com/netease-youdao/LobsterAI/pull/1553)

## Bug 与稳定性
以下 Bug 已全部在今日解决（PR 已合并或待合并）：

| 严重程度 | 问题描述 | 关联 Issue/PR | 状态 |
|----------|----------|---------------|------|
| 中 | 定时任务通知渠道选择“不通知”后无法保存（再次编辑仍显示旧渠道） | #1547 (PR) | 待合并 |
| 中 | 编辑 Agent 技能后 activeSkillIds 未同步，需手动切换 Agent 才生效 | #1545 (PR) | 已合并 |
| 中 | 在“我的Agent”编辑后点击原 Agent 无法切回聊天界面 | #1560 (PR) | 已合并 |
| 低 | macOS 打包因缺少 `sha256sum` 失败 | #1555 (PR) | 已合并 |
| 低 | 引擎启动卡住时无任何操作反馈 | #1546 (PR) | 已合并 |

## 功能请求与路线图信号
- **文件预览功能** (Issue #1552) 已由 PR #1553 实现，支持 Markdown/HTML/代码/图片预览，很可能会被纳入下一正式版本。
- **设置面板搜索** (PR #1557) 也属于用户明确提出的可用性需求，已被合并。
- 未发现新的重大功能请求，但 **文档404问题** (Issue #1556) 提示项目文档维护需加强。

## 用户反馈摘要
- 用户 `darkSheep404` 反馈 IM 配置指南链接返回 404，影响文档可用性（[Issue #1556](https://github.com/netease-youdao/LobsterAI/issues/1556)）。
- 用户 `noransu` 在 Issue #1552 中详细描述了 Write 工具产物无法预览的痛点，并提出了文件卡片与预览面板的具体需求，该需求已被 PR #1553 实现。
- 其他 Issues 评论较少，整体社区参与度偏低，但开发者对已报告问题响应及时。

## 待处理积压
- **Issue #1556** (IM配置指南404)：自2026-04-08创建，至今已有4个月，仍处于 OPEN 状态。虽被标记为 stale，但文档维护是项目健康度的重要指标，建议尽快修复链接或更新文档。
- **PR #1547** (定时任务通知 Bug)：已提交但未合并，仅 +2 行改动，建议尽快 Review 合并，避免后续版本遗漏。
- 此外，所有今日活跃的 Issues 和 PRs 均为历史积压，无全新报告的新问题，表明项目当前处于稳定期，但需警惕停滞风险。

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

# Moltis 项目日报 – 2026-08-21

---

## 1. 今日速览

- 过去24小时内，项目共处理了 **1 个 Issue**（已关闭）和 **8 个 Pull Request**（4 个待合并，4 个已合并/关闭），并发布了 **1 个新版本** `20260820.01`。
- 团队集中修复了 **Vault 解锁/恢复端点缺少认证** 的安全漏洞（CWE-306），对应 PR #1216 已合并，并关闭了该 Bug 报告（#1177）。
- 三个 WhatsApp 相关的 PR 同时被合并，显著提升了 WhatsApp 通道的消息处理能力（Markdown 转换、回复识别、推送名称修正）。
- 一个长期开放的 Windows 兼容性 PR（#468，已开放近5个月）仍在等待合并，项目整体活跃度较高，但某些积压项需关注。

---

## 2. 版本发布

### Release `20260820.01`

- **发布时间**：2026-08-20
- **变更内容**：未提供详细变更日志，但根据同期合并的 PR 推断，该版本应包含以下修复：
  - 修复 Vault 解锁/恢复端点未认证漏洞（CWE-306）
  - 修复 WhatsApp 硬编码推送名称问题
  - 修复 WhatsApp 群组中回复机器人消息未被识别为提及的问题
  - 为频道添加 `untrusted-turn` 工具上限可配置功能
- **破坏性变更**：无已知破坏性变更。
- **迁移注意事项**：若使用 Vault 功能，请确保升级后认证流程正常；WhatsApp 用户需注意推送名称将不再统一显示为“Moltis”，而是使用构建时配置的名称。

---

## 3. 项目进展（合并/关闭的重要 PR）

| PR | 标题 | 作者 | 合并时间 | 说明 |
|----|------|------|----------|------|
| [#1216](https://github.com/moltis-org/moltis/pull/1216) | fix(httpd): require authentication for vault unlock and recovery | penso | 2026-08-20 | **关键安全修复**：为 Vault 解锁/恢复端点添加 `AuthSession` 验证，修复 CWE-306 漏洞，防止未授权暴力破解。 |
| [#1217](https://github.com/moltis-org/moltis/pull/1217) | fix(whatsapp): treat a reply to the bot as addressing it | vikng-dev | 2026-08-20 | 修复 WhatsApp 群组中 `mention_mode = "mention"` 模式下，回复机器人消息被忽略的问题。 |
| [#1218](https://github.com/moltis-org/moltis/pull/1218) | fix(whatsapp): stop hardcoding the push name to "Moltis" | vikng-dev | 2026-08-20 | 不再硬编码推送名称为“Moltis”，使机器人配置的名称（如“Ada”）正确显示在群组中。 |
| [#1219](https://github.com/moltis-org/moltis/pull/1219) | fix(channels): make the untrusted-turn tool ceiling configurable | vikng-dev | 2026-08-20 | 允许为 `untrusted-turn` 设置可配置的工具上限，修复了之前硬编码导致公开受众工具不可用的问题。 |

> 以上4个 PR 已合并/关闭，项目在安全加固、WhatsApp 兼容性、频道配置灵活性方面均取得进展。

---

## 4. 社区热点

今日无高评论数的热点讨论，但以下 PR 因涉及安全核心问题而受到关注：

- **PR #1216**（Vault 认证修复）与 **Issue #1177**（Bug 报告）共同构成今日最受关注的安全事件。虽然无评论，但漏洞的严重性（CWE-306）使其成为社区焦点。
- **PR #1222**（验证沙箱镜像请求）和 **PR #1221**（锁定 Snyk Agent 扫描版本）均属于安全加固，反映了社区对供应链安全的持续关注。

**分析**：Moltis 团队近期在安全审计方面投入较多，用户反馈（Issue #1177）直接推动了修复，表明了项目对安全响应的及时性。

---

## 5. Bug 与稳定性

| 严重程度 | Bug 描述 | 对应 Issue | 修复状态 |
|----------|----------|------------|----------|
| **严重** | Vault 解锁/恢复端点缺少认证，允许未授权远程暴力破解密码（CWE-306） | [#1177](https://github.com/moltis-org/moltis/issues/1177)（已关闭） | 已通过 PR [#1216](https://github.com/moltis-org/moltis/pull/1216) 修复，随版本 `20260820.01` 发布 |
| 中等 | 沙箱镜像请求未验证镜像引用和包名，存在容器逃逸风险 | 未单独提 Issue，但 PR [#1222](https://github.com/moltis-org/moltis/pull/1222) 正在处理中 | 待合并（PR #1222 开放中） |
| 低 | WhatsApp 群组中回复模式未正确识别提及 | 无单独 Issue，PR [#1217](https://github.com/moltis-org/moltis/pull/1217) 已修复 | 已合并 |
| 低 | WhatsApp 推送名称硬编码 | 无单独 Issue，PR [#1218](https://github.com/moltis-org/moltis/pull/1218) 已修复 | 已合并 |

今日未报告新的崩溃或回归问题，稳定性良好。

---

## 6. 功能请求与路线图信号

- **WhatsApp Markdown 渲染**（PR [#1220](https://github.com/moltis-org/moltis/pull/1220)）：将模型生成的 Markdown 转换为 WhatsApp 原生标记，支持文本和媒体标题。该功能增强了 WhatsApp 通道的用户体验，与已合并的 WhatsApp 修复形成系列，很可能被纳入下一个版本。
- **沙箱镜像验证**（PR [#1222](https://github.com/moltis-org/moltis/pull/1222)）：限制镜像引用和包名验证，仅允许操作员管理员执行容器构建。这是安全加固的延续，符合近期路线图中的“安全沙箱”方向。
- **Snyk Agent 扫描锁定**（PR [#1221](https://github.com/moltis-org/moltis/pull/1221)）：固定技能安全扫描版本，防止供应链攻击，移除独立的 `mcp-scan` 回退，要求 `uv` 工具。这是一个运维改进，可能提升安全扫描的可靠性。

上述 PR 均处于开放待合并状态，预计将在未来1-2天内合并。

---

## 7. 用户反馈摘要

今日无新的用户评论或反馈（Issues 和 PR 评论数均为0）。但根据 Issue #1177 的提交内容，用户报告了**严重的安全漏洞**，并提供了详细的预检查清单，表明该用户是经验丰富的开发者，对项目安全有较高期望。修复后该 Issue 已关闭，未产生进一步讨论。

---

## 8. 待处理积压

| 项目 | 类型 | 创建时间 | 最后更新 | 状态说明 |
|------|------|----------|----------|----------|
| [#468](https://github.com/moltis-org/moltis/pull/416) | Pull Request | 2026-03-23 | 2026-08-20 | **Windows Shell 钩子兼容性**：使用 `cmd.exe` 替代 `sh -c`。已开放近5个月，作者已通过测试验证，但未获得合并。建议维护者评估并尽快处理，避免 Windows 用户长期受阻。 |
| 无其他长期未响应 Issue | – | – | – | 当前积压情况良好，除#468外无其他超过1个月未处理的公开问题。 |

---

**总结**：Moltis 项目今日在安全、WhatsApp 通道、频道配置方面取得显著进展，版本发布及时。需关注长期未合并的 Windows 兼容性 PR，以及待合并的安全加固 PR（#1221、#1222）。整体项目健康度较高，响应速度良好。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

# CoPaw 项目动态日报｜2026-08-21

## 今日速览

过去 24 小时项目保持高活跃度：共处理 27 条 Issue（14 条新开/活跃，13 条已关闭）和 50 条 PR（21 条待合并，29 条已合并/关闭），并发布了 v2.1.1-beta.1 版本。社区反馈集中在任务自动执行中断、长时间冻结、网络中断恢复、海量历史库膨胀等稳定性问题，同时涌现多项功能提案（如自动模型路由、跨会话回忆开关、QQ 定时消息等）。多项性能优化和安全修复（如 envs.json 原子写入、文件下载器超时回退、会话响应保持等）已合入主干，项目整体向更健壮、更可扩展的方向迈进。

## 版本发布

### v2.1.1-beta.1

- **发布链接**：[v2.1.1-beta.1 Release](https://github.com/agentscope-ai/QwenPaw/releases/tag/v2.1.1-beta.1)
- **主要变更**：
  - `feat(console): improve editor tab overflow navigation` – 优化编辑器标签页溢出的导航体验。
  - `fix(providers): lower rate limiter init log level` – 降低限流器初始化日志级别，减少日志噪音。
  - `chore: update release notes` – 更新版本发布说明。
- **破坏性变更**：无。
- **迁移注意事项**：无特殊要求，建议 Beta 用户升级测试。

## 项目进展

过去 24 小时内有 29 个 PR 被合并/关闭，以下为重要推进项：

| 关键 PR | 描述 | 状态 |
|--------|------|------|
| [#7161](https://github.com/agentscope-ai/QwenPaw/pull/7161) feat(console): add artifacts to assistant response card | 在助手回复卡片中增加产物（artifacts）展示 | 已合并 |
| [#7174](https://github.com/agentscope-ai/QwenPaw/pull/7174) perf(drivers): initialize persistent drivers concurrently | 并发初始化持久化驱动，减少工作区启动的冷启动时间 | 已合并 |
| [#6880](https://github.com/agentscope-ai/QwenPaw/pull/6880) feat(console): unify apps, plugins, and skills in the marketplace | 统一应用、插件、技能市场页面，提升导航一致性 | 已合并 |
| [#6371](https://github.com/agentscope-ai/QwenPaw/pull/6371) fix(file-handling): continue fallback after downloader timeout | 修复文件下载器超时后未正确回退到下一工具（wget→curl→urllib）的问题 | 已合并 |
| [#7166](https://github.com/agentscope-ai/QwenPaw/pull/7166) fix(release): bundle qwenpawmail MCP as a standalone sidecar | 将 qwenpawmail MCP 服务打包为独立 sidecar，避免依赖冲突 | 已合并 |
| [#7135](https://github.com/agentscope-ai/QwenPaw/pull/7135) fix(envs): preserve corrupt files and write envs atomically | 保留损坏的 envs.json 文件，并采用原子写入防止环境变量丢失 | 已合并 |
| [#7172](https://github.com/agentscope-ai/QwenPaw/pull/7172) chore(deps): patch vulnerable website and creator dependencies | 升级 vite、rollup、react-router-dom、js-yaml 等依赖，修复安全漏洞 | 已合并 |
| [#7176](https://github.com/agentscope-ai/QwenPaw/pull/7176) perf(console): keep long chat sessions responsive | 优化长会话下 Markdown 解析和流式更新的性能，提升响应速度 | 进行中 |

这些合并显著提升了控制台性能、文件处理鲁棒性、环境变量安全性，并统一了市场页面，为后续功能扩展奠定基础。

## 社区热点

过去 24 小时讨论最活跃的 Issue 和 PR 如下：

1. **[#6921 [Bug] 任务执行中经常无提示停止，需用户说“继续”才继续](https://github.com/agentscope-ai/QwenPaw/issues/6921)**
   - 评论数：10（最高）
   - 诉求：用户在执行多步骤任务时，模型输出类似“Now 2.1, 3.1, 3.2. Let me do all three.” 后自动停止，无任何提示，必须手动输入“继续”才能继续。该问题严重影响自动化体验，社区期望模型能够自动执行后续步骤，或至少提供明确的停止原因提示。

2. **[#7102 [Bug] 冻结超过 10 分钟](https://github.com/agentscope-ai/QwenPaw/issues/7102)**
   - 评论数：9
   - 诉求：用户使用 glm 5.3 模型时，QwenPaw 桌面端超过 10 分钟无任何响应，甚至思考过程也冻结。该问题导致用户不得不强制重启，严重影响工作流。社区期望增强对模型超时/冻结的检测和恢复机制。

3. **[#7110 [Bug] 对话上下文中包含无法下载的图片链接，整个会话不可用](https://github.com/agentscope-ai/QwenPaw/issues/7110)**
   - 评论数：3
   - 诉求：当消息记录中存在无法访问的图片链接（如网络限制或模型幻觉生成），会话会完全挂死，只有 `/clear` 才能恢复。用户期望对图片加载失败进行优雅降级，而非阻塞整个会话。

## Bug 与稳定性

以下按严重程度列出过去 24 小时报告的关键 Bug，并标注是否已有修复 PR：

| 严重程度 | Issue | 描述 | 是否已有 Fix PR |
|---------|-------|------|----------------|
| **严重** | [#6921](https://github.com/agentscope-ai/QwenPaw/issues/6921) | 任务执行中无提示停止，需用户手动干预 | 未发现关联 PR |
| **严重** | [#7102](https://github.com/agentscope-ai/QwenPaw/issues/7102) | 桌面端冻结超过 10 分钟，无任何响应 | 已关闭，但未见具体修复 PR |
| **严重** | [#6932](https://github.com/agentscope-ai/QwenPaw/issues/6932) | 网络短暂中断并恢复后，QwenPaw 无法自动恢复，所有 LLM 请求持续超时 | 无 PR |
| **严重** | [#7110](https://github.com/agentscope-ai/QwenPaw/issues/7110) | 无法下载的图片链接导致整个会话不可用 | 已关闭，但未见具体 PR（可能由其他 PR 间接修复） |
| **高** | [#7168](https://github.com/agentscope-ai/QwenPaw/issues/7168) | history.db 被 recall_history 的 expand 撑爆至 7.6GB，同一区间重复落库 | 无 PR |
| **高** | [#7162](https://github.com/agentscope-ai/QwenPaw/issues/7162) | 流式输出中途 httpx.ReadError 导致 UNKNOWN_AGENT_ERROR，且不重试 | 已关闭，可能已修复 |
| **高** | [#7156](https://github.com/agentscope-ai/QwenPaw/issues/7156) | embedding health check 超时硬编码（5s），预热后仍超时，导致降级为 BM25 | 关联 PR [#7133](https://github.com/agentscope-ai/QwenPaw/pull/7133)（WIP，增加可配置超时） |
| **中** | [#7118](https://github.com/agentscope-ai/QwenPaw/issues/7118) | 损坏的 envs.json 被静默吞掉并覆盖，导致所有环境变量丢失 | 已修复（PR [#7135](https://github.com/agentscope-ai/QwenPaw/pull/7135) 已合并） |
| **中** | [#6826](https://github.com/agentscope-ai/QwenPaw/issues/6826) | 助手消息结束时间显示异常（实际耗时 2min，页面仅显示几秒） | 已关闭，但无具体 PR |
| **低** | [#7060](https://github.com/agentscope-ai/QwenPaw/issues/7060) | view_video 内联媒体大小限制硬编码为 2MB，provider 配置无效 | 关联 PR [#7061](https://github.com/agentscope-ai/QwenPaw/pull/7061)（Open，修复 OpenAI Responses API 视频路径） |

**总结**：社区最迫切的稳定性问题集中在任务自动执行中断、长时间冻结、网络中断恢复及历史库膨胀。目前部分问题已有修复或进行中的 PR，但仍有多个关键 Bug 缺乏解决方案，需维护者优先关注。

## 功能请求与路线图信号

过去 24 小时提出了多项新功能需求，结合已有 PR 可推测以下方向可能被纳入下一版本：

- **自动模型路由（[#6436](https://github.com/agentscope-ai/QwenPaw/issues/6436)）**：根据请求类型自动选择小模型、视觉模型、大推理模型，无需固定绑定。该需求已获 1 个 👍，社区关注度较高，但暂无具体 PR。
- **跨会话回忆开关（[#7184](https://github.com/agentscope-ai/QwenPaw/issues/7184)）**：为 Agent 增加跨会话回忆的触发器级开关，平衡长上下文与隐私。已有 PR [#7183](https://github.com/agentscope-ai/QwenPaw/pull/7183) 实现 workspace 级别的“始终开启”技能加载，可能与此相关。
- **工作区级始终开启技能（[#7182](https://github.com/agentscope-ai/QwenPaw/issues/7182)）**：支持将特定技能自动加载到

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我将根据您提供的 ZeroClaw (zeroclaw-labs/zeroclaw) GitHub 数据，为您生成 2026 年 8 月 21 日的项目动态日报。

---

# ZeroClaw 项目动态日报 — 2026-08-21

## 1. 今日速览

今日 ZeroClaw 项目社区活跃度极高，24小时内产生了 **50 条 Issue 更新**和 **50 个 PR 提交**，但 **无新版本发布**，且 **PR 合并/关闭数为 0**。这表明项目正处于一个高强度的代码审查和技术债务清理阶段，尤其是针对 Rust 代码规范的“反模式”清理行动。虽然社区讨论和技术提案（RFC）非常热烈，但产出合并的节奏暂时放缓，维护者需要集中精力处理庞大的 PR 堆积和重要的架构决策。

## 2. 版本发布

无新版本发布。

## 3. 项目进展

尽管今日无 PR 被合并，但项目通过大量待审查的 PR 清晰地展示了其前进方向。特别是贡献者 **JordanTheJet** 提交了一系列旨在修复代码质量、增强稳定性的 PR，标志着项目正在系统性地解决存量技术债务。

- **核心代码质量与稳定性提升**：一系列 PR（如 `#10123`， `#10124`， `#10127`， `#10128`， `#10129`， `#10131`， `#10132`， `#10133`）致力于移除生产代码中的 `panic`、`unwrap` 和死代码。这些改动覆盖了 Gateway、Channels、Tools、Config、Runtime 等多个核心模块，旨在将错误处理从“崩溃”转向“优雅降级”，显著提升项目整体的健壮性。
- **安全基础设施加固**：
    - **PR #10100** 实现了 Landlock 沙箱对 `allowed_roots` 分层的支持，允许更细粒度的文件系统访问控制。
    - **PR #10107** 修复了 Google STT API 密钥可能通过 URL 泄露的安全问题，将其移至 HTTP Header。
    - **PR #10142** 是一个重量级 PR，旨在引入一个名为 `ZeroRelay` 的安全传输和浏览器注册前端，这可能是为未来的远程访问或协作功能奠定基础。
- **平台兼容性修复**：**PR #10080** 修复了 Windows 桌面端因缺少 `TaskDialogIndirect` 入口点而无法启动的问题，该问题直接关联到 Issue `#10111`。
- **渠道功能增强**：**PR #10084** 和 **PR #10085** 共同解决了 WhatsApp 渠道的 passkey 门禁问题，确保设备链接流程能够顺利完成。

## 4. 社区热点

今日社区讨论焦点集中在几个核心架构 RFC 和技术债务清理上，反映出社区对远期规划和技术规范的重视。

- **#9487 RFC: Runtime-owned conversation sessions** (22 评论) - [链接](https://github.com/zeroclaw-labs/zeroclaw/issues/9487)
    - **诉求分析**：这是当前最热门的讨论。该 RFC 提出了一个重大的架构变更，旨在将会话生命周期管理下放到 Runtime，并引入传输层适配器接口。社区讨论围绕所有权边界、`InboundAction` 的提交以及持久化准入语义展开，这表明社区正在为构建更灵活、更健壮的会话层进行深入的设计评审。
- **#10118 [Tracker]: Rust anti-slop policy debt remediation** (16 评论) - [链接](https://github.com/zeroclaw-labs/zeroclaw/issues/10118)
    - **诉求分析**：此跟踪器是今日大量代码质量 PR 的源头。社区对“anti-slop”政策的讨论非常热烈，该政策旨在清理 Rust 代码中不符合规范的“草率”模式（如未经检查的 panic、死代码等）。高达 307 个候选问题点被标记出来，表明社区对代码质量和长期可维护性有极高的追求。
- **#6850 RFC: Decouple memory lifecycle policy from storage backends** (14 评论) - [链接](https://github.com/zeroclaw-labs/zeroclaw/issues/6850)
    - **诉求分析**：该 RFC 提议将内存的生命周期策略与具体的存储后端解耦。持续的讨论表明，社区希望建立一个更清晰、层次分明的内存管理架构，以避免每个网关或渠道重复实现复杂的生命周期逻辑。
- **#8780 RFC: Realtime speech-to-speech channel for Gemini Live** (14 评论) - [链接](https://github.com/zeroclaw-labs/zeroclaw/issues/8780)
    - **诉求分析**：该提案在修订后转向了“代理合约”模式，表明社区对集成实时语音功能（特别是 Gemini Live）有强烈的兴趣。讨论焦点在于如何将这种复杂的实时交互模式抽象为一种通用的、可扩展的通道架构。

## 5. Bug 与稳定性

今日报告的 Bug 主要集中在配置兼容性、上下文限制和文档过时问题，严重程度多为 S2（功能降级）。

- **S2 - 严重**：
    - **#10068**：交互式 agent 会话的上下文长度被硬限制在 32,000 tokens，无视用户配置的 `max_context_tokens = 131072`。这是一个明显的功能降级，可能会影响大型任务的处理。**目前无关联的 fix PR。**
    - **#10106**：精确的代理选择器无法识别支持的转录服务（如 `transcription.groq`），导致代理配置错误。**目前无关联的 fix PR。**
    - **#10194 (已关闭)**：PR 审查机器人会在 PR 合并后仍发布审查结果，造成信息混乱。该问题已被标记为 Bug 并关闭，但根本的 CI 流程问题可能仍需关注。
- **S3 - 次要**：
    - **#10074**：`SECURITY.md` 文档引用的 CI 工作流已被删除，导致文档与事实不符。**目前无关联的 fix PR。**
    - **#10103**：ZeroCode 健康状态标签在法语和西班牙语本地化中因固定宽度截断导致显示错位。**目前无关联的 fix PR。**

## 6. 功能请求与路线图信号

今日用户提出的功能请求和 RFC 主要集中在提升默认体验、Agent 可移植性和平台扩展性上。

- **默认行为优化**：**#10168** 和 **#10166** 是两个非常务实的请求，建议将“stall 看门狗”和“流式模式”改为默认启用。这体现了社区对“开箱即用”体验的重视，很可能被纳入下一小版本迭代。
- **Agent 可移植性**：**#10069** 提出了一个“Agent 可移植性”RFC，允许用户将配置好的 Agent 导出为独立包，并在其他部署中导入。这指向了 Agent 市场或生态共享的远景，可能是一个长期路线图上的重要功能。
- **零配置 Swarm**：**#10025** 提出了一个“零配置 Agent Swarm”功能，允许用户通过一个命令快速启动一个临时性的、带有 TUI 界面的多 Agent 协作任务组。这反映了用户对多 Agent 协作场景的强烈需求，希望能降低实验门槛。
- **插件系统完善**：**#10162** 提出了一个具体的技术任务，要求使 `plugin install` 命令在配置写入失败时能够回滚，避免半安装状态。这直接关系到插件系统的健壮性，是通往成熟插件生态的关键一步。

## 7. 用户反馈摘要

从今日的 Issues 评论中，可以提炼出以下用户反馈：

- **配置与文档痛点**：用户对配置的复杂性和文档的过时性有所抱怨。例如，`max_context_tokens` 配置被忽略 (`#10068`)，代理选择器过於严格 (`#10106`)，以及安全文档引用了不存在的 CI 流程 (`#10074`)，这些都给用户带来了困惑。
- **对代码质量的“吹毛求疵”**：社区对代码质量有极高的要求。`#10118` 跟踪器下的大量评论和后续的系列 PR (`#10123` 等) 表明，不仅是核心维护者，包括贡献者群体也积极参与到代码规范和稳定性的提升中，这是一种高度健康的项目文化。
- **对“开箱即用”体验的期待**：`#10168` 和 `#10166` 等 Issue 的提出，清晰地表明用户希望 ZeroClaw 在默认配置下就能提供更稳定、更流畅的体验，而不是需要手动调整参数来避免卡死或等待全响应。

## 8. 待处理积压

以下是一些长期未响应或处于停滞状态的重要 Issue 和 PR，需要维护者关注：

- **长期未响应的 RFC**：
    - **#8132**：RFC 提议用 Rust→Wasm 框架替换 React/Vite 前端 UI。该提案具有颠覆性，但状态为 `needs-author-action`，作者未回应最新问题，导致讨论停滞。**提醒：** 如果此方向被否决，请及时关闭并给出理由。
    - **#6996**：细粒度沙箱策略 RFC，同样处于 `needs-author-action` 状态。这是实现高级安全隔离的关键，建议维护者主动介入推动。
    - **#8398**：插件权限、配置和密钥模型的开放问题 RFC。这是插件系统的核心设计，状态为 `needs-author-action`，长期无讨论，可能阻碍其他插件相关工作的进展。
- **待合并的长期 PR**：
    - **#9637**：一个大型的 CI 修复 PR，旨在临时处理 React Router 的安全问题。该 PR 打上了 `do-not-merge` 标签，需维护者评估其长期影响，并决定是合并还是寻找替代方案。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*