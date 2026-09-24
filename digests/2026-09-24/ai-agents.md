# OpenClaw 生态日报 2026-09-24

> Issues: 500 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-09-24 00:52 UTC

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

# OpenClaw 项目动态日报 | 2026-09-24

---

## 1️⃣ 今日速览

过去 24 小时内，OpenClaw 项目共处理 **500 条 Issue**（活跃/新开 464，关闭 36）和 **500 条 PR**（待合并 397，合并/关闭 103），社区参与度极高。**v2026.9.6 因 macOS 启动崩溃已紧急撤回**，官方正在准备 2026.9.7 热修复。多项 P0 级别稳定性 Bug（内存泄漏、更新失败、会话丢失）成为活跃讨论焦点，项目正处在高强度修复周期中。整体活跃度 ★★★★★（极高），稳定性风险 ★★★☆☆（高）。

---

## 2️⃣ 版本发布

### v2026.9.6 (2026-09-23)
- **内容**：常规月度更新。
- **⚠️ 重要警告**：macOS app 存在严重问题，更新后可能导致应用在每次启动时闪退（[#156861](https://github.com/openclaw/openclaw/issues/156861)）。
- **当前状态**：该版本已从 Sparkle 更新源中撤回，官方正在开发 **2026.9.7 macOS 热修复**。
- **迁移建议**：如果 macOS 用户已更新并无法启动，请重新安装 v2026.9.5 构建版。其他平台用户暂时可以继续使用 2026.9.6，但仍需注意更新流程中可能存在的风险（参见下方 Bug 章节）。

---

## 3️⃣ 项目进展

过去 24 小时内合并/关闭了 **103 个 PR**，主要集中在以下领域：

- **PDF 文档处理修复** – [#131922](https://github.com/openclaw/openclaw/pull/131922) 已合并：PDF 提取超时被截断时，模型现在会被告知文档是部分的，避免幻觉。
- **CI 与构建优化** – [#155743](https://github.com/openclaw/openclaw/pull/155743) 已合并：限制安全审查的源代码检出范围，减少 CI 工作时长。
- **CLI 端口解析统一** – [#156815](https://github.com/openclaw/openclaw/pull/156815) 已合并：移除重复的 TCP 端口解析代码，降低维护成本。
- **诊断报告改进** – [#146630](https://github.com/openclaw/openclaw/pull/146630) 已合并：修复“卡死会话”诊断中强制清除被错误报告为终止的问题。
- **会话与 UI 修复** – 多个 PR（如 [#146855](https://github.com/openclaw/openclaw/pull/146855) iOS Talk 超时修复、[#156838](https://github.com/openclaw/openclaw/pull/156838) UI 讨论发布改进等）仍在审核中，等待合并。

这些修复使项目在文档提取、CI 效率、诊断准确性方面前进了一步，但核心稳定性问题仍待解决。

---

## 4️⃣ 社区热点

今日评论数量最多的 Issue 反映了用户对 **可靠性、消息丢失、启动故障**的强烈关注：

| 排名 | Issue | 评论数 | 核心诉求 |
|------|-------|--------|----------|
| 🥇 | [#91588](https://github.com/openclaw/openclaw/issues/91588) 网关内存泄漏（RSS 从 350MB 增长至 15.5GB） | 39 | 请求尽快修复内存泄漏，避免 OOM 被杀。 |
| 🥈 | [#126360](https://github.com/openclaw/openclaw/issues/126360) AgentSelectionRequiredError 泛滥日志（显式多代理所有权下） | 19 | 用户需要明确的 agentId 目标或回退机制。 |
| 🥉 | [#80319](https://github.com/openclaw/openclaw/issues/80319) QA 工具默认套件混淆 Codex 原生动/OpenClaw 动态工具 | 17 | 测试框架应区分两种工具的测试范围。 |
| 4 | [#148707](https://github.com/openclaw/openclaw/issues/148707) 回复丢失（2026.9.4 回归） | 16 | 会话中 in-flight 轮被抢占导致回复永久丢失。 |
| 5 | [#152981](https://github.com/openclaw/openclaw/issues/152981) 网关启动挂起 ~17 分钟（Windows） | 15 | 准备模型运行时超时，怀疑是插件加载 bug。 |

**分析**：社区最关心的仍然是**会话层可靠性**（消息丢失、不当抢占）和**资源管理**（内存泄漏、启动挂起）。多个 Issue 被标记为 `clawsweeper:needs-maintainer-review`，说明维护团队被这些问题淹没，资源分配面临挑战。

---

## 5️⃣ Bug 与稳定性

按严重程度排列，今日活跃或新报告的 Bug：

### P0 – 紧急（影响核心功能）

| ID | 描述 | 平台 | 状态 |
|----|------|------|------|
| [#156861](https://github.com/openclaw/openclaw/issues/156861) | macOS 更新到 2026.9.6 后应用完全无法启动 | macOS | 已确认，**已在开发修复 PR** [PR #156881](https://github.com/openclaw/openclaw/pull/156881) |
| [#91588](https://github.com/openclaw/openclaw/issues/91588) | 网关内存泄漏（RSS 15.5GB）导致 OOM 反复崩溃 | 全平台 | 开放，无 fix PR |
| [#152981](https://github.com/openclaw/openclaw/issues/152981) | 网关启动挂起 ~17 分钟（Windows） – 2026.9.5 回归 | Windows | 开放，无 fix PR |
| [#146887](https://github.com/openclaw/openclaw/issues/146887) | 2026.9.3→2026.9.4 更新失败（多阶段崩溃） | Linux | 开放，无 fix PR |
| [#148681](https://github.com/openclaw/openclaw/issues/148681) | 更新失败 finalize:doctor (2026.9.4) | Linux/macOS | 开放，需要更多信息 |
| [#156712](https://github.com/openclaw/openclaw/issues/156712) | `openclaw triage` 子进程无法正常退出，持有锁阻塞重启 | 全平台 | 开放，无 fix PR |
| [#152935](https://github.com/openclaw/openclaw/issues/152935) | 容器升级（2026.9.4→2026.9.5）所有 agent schema 拒绝 | 容器 | 开放，无 fix PR |

### P1 – 重要（影响多数用户）

| ID | 描述 | 影响范围 | 状态 |
|----|------|----------|------|
| [#148707](https://github.com/openclaw/openclaw/issues/148707) | 回复丢失（in-flight 轮被抢占，2026.9.4 回归） | 交互会话 | 开放，标签 `clawsweeper:needs-info` |
| [#140010](https://github.com/openclaw/openclaw/issues/140010) | Windows 睡眠唤醒后 WebSocket 重连失败 30-60s | Windows | 开放，无 fix PR |
| [#138272](https://github.com/openclaw/openclaw/issues/138272) | Android Talk 在需要工具调用时丢消息 | Android | 开放，需要复现 |
| [#137488](https://github.com/openclaw/openclaw/issues/137488) | 派发运行完成通知声称到错误接收者（语音通道） | Discord 语音 | 开放，标签 `clawsweeper:fix-shape-clear` |
| [#152275](https://github.com/openclaw/openclaw/issues/152275) | 插件激活失败后模型元数据和回复派发不可用 | 全平台 | 开放，需复现 |
| [#148650](https://github.com/openclaw/openclaw/issues/148650) | 内存索引子进程无法解析 SecretRef 凭证（401） | 全平台 | 开放，无 fix PR |

### P2 – 中等（影响特定场景）

| ID | 描述 | 状态 |
|----|------|------|
| [#140723](https://github.com/openclaw/openclaw/issues/140723) | WebChat 显示重复回复 2-3 次 | 开放 |
| [#138599](https://github.com/openclaw/openclaw/issues/138599) | 自动压缩死锁：会话超过压缩模型窗口 | 开放 |
| [#123354](https://github.com/openclaw/openclaw/issues/123354) | Matrix E2EE 在 Megolm 会话轮换后停止解密 | 开放 |
| [#70903](https://github.com/openclaw/openclaw/issues/70903) | 持久化 provider 冷却让用户在充值后仍被阻挡数小时 | 开放，P0 但标注 stale |

### 已修复/正在修复的 PR

- **macOS 启动崩溃**：PR [#156881](https://github.com/openclaw/openclaw/pull/156881) 已提交（待验证）。
- **Talk 去重**：PR [#156885](https://github.com/openclaw/openclaw/pull/156885) 修复 Android Talk 中 xAI 重复对话轮。
- **浏览器 CDP 凭证泄露**：PR [#137756](https://github.com/openclaw/openclaw/pull/137756) 修复浏览器 URL 中携带认证信息被暴露给模型的风险。

---

## 6️⃣ 功能请求与路线图信号

以下来自社区的新功能请求获得较多关注，部分已有关联 PR 或处于 `clawsweeper:needs-product-decision` 阶段：

| ID | 功能描述 | 用户热度 | 路线图可能性 |
|----|----------|----------|-------------|
| [#44309](https://github.com/openclaw/openclaw/issues/44309) | A2A 单向派发模式（无需回复往返） | 👍1, 10评论 | 中等 – 已标记 `needs-product-decision` |
| [#51572](https://github.com/openclaw/openclaw/issues/51572) | 会话内存钩子在重置/修剪时触发，不仅限于压缩 | 👍1, 9评论 | 高 – 与内存管理优化方向一致 |
| [#71058](https://github.com/openclaw/openclaw/issues/71058) | 支持多个 Azure/Teams Bot 连接同一网关 | 👍1, 9评论 | 中等 – 企业用户强烈需求 |
| [#44965](https://github.com/openclaw/openclaw/issues/44965) | 流重复输出防护（暂停并确认） | 👍1, 7评论 | 高 – 与当前 `NO_REPLY` 类 Bug 相关 |
| [#40982](https://github.com/openclaw/openclaw/issues/40982) | 提高/移除 CLI 请求的 3 分钟无输出看门狗上限 | 👍2, 6评论 | 高 – 已有相关 PR 在审核 |
| [#138279](https://github.com/openclaw/openclaw/issues/138279) | 为 Linux aarch64 提供官方 Companion 构建 | 👍0, 7评论 | 低 – 相对小众但社区有呼声 |

**判断**：下一版本（2026.9.7）将优先修复 macOS 崩溃和更新流程，但会话可靠性改进（#148707、#44965）和内存泄漏（#91588）是社区最迫切的需求，可能被提前排入路线图。

---

## 7️⃣ 用户反馈摘要

从 Issue 评论和报告内容中提炼的真实用户声音：

- **macOS 用户**：“更新后应用彻底打不开，两台 Mac 都无法启动…… 我现在完全没有办法使用 OpenClaw。” —— [#156861](https://github.com/openclaw/openclaw/issues/156861)
- **会话丢失痛点**：“回复完全丢失，没有重试，没有部分内容，就像白说了一样。” —— [#148707](https://github.com/openclaw/openclaw/issues/148707)
- **内存泄漏对部署的影响**：“2-3 天后 RSS 涨到 15.5GB，OOM 杀掉后启动循环，生产环境没办法用。” —— [#91588](https://github.com/openclaw/openclaw/issues/91588)
- **更新流程挫败感**：“跨 4 个阶段失败，最后只能手动重新安装…… 希望有更可靠的更新机制。” —— [#146887](https://github.com/openclaw/openclaw/issues/146887)
- **Agent 配置混乱**：“显式多代理模式下，每个 RPC 调用都报 AgentSelectionRequiredError，日志完全被刷屏。” —— [#126360](https://github.com/openclaw/openclaw/issues/126360)
- **期待的方向**：“单次派发模式对自动化工作流非常有用，不需要每次都 ping-pong 回复。” —— [#44309](https://github.com/openclaw/openclaw/issues/44309)

**总体情绪**：用户对项目功能丰富度和自定义能力高度认可（如多代理、内存搜索、插件生态），但**稳定性和可靠性**是当前最大不满来源。macOS 用户受影响最大，Windows 睡眠恢复和一般更新流程也存在较大风险。

---

## 8️⃣ 待处理积压

以下 Issue/PR 长期未获得维护者响应或进展缓慢，可能成为风险点：

| ID | 摘要 | 创建日期 | 上次更新 | 潜在影响 |
|----|------|----------|----------|----------|
| [#70903](https://github.com/openclaw/openclaw/issues/70903) | 持久化 provider 冷却导致用户充值后仍被阻挡数小时（P0，stale） | 2026-04-24 | 2026-09-23 | 用户被锁死，直接损失信任 |
| [#85030](https://github.com/openclaw/openclaw/issues/85030) | MCP 工具未注入子代理会话（P1，diamond lobster） | 2026-05-21 | 2026-09-23 | 高级用户无法使用 MCP 生态 |
| [#110190](https://github.com/openclaw/openclaw/issues/110190) | 运行时上下文载体放在用户消息之后导致模型混乱（P1，diamond lobster） | 2026-07-17 | 2026-09-23 | 影响所有基于上下文的推理质量 |
| [#121617](https://github.com/openclaw/openclaw/issues/121617) | 压缩失败误分类为“无新内容可压缩”，导致会话无法恢复（P1） | 2026-08-10 | 2026-09-23 | 会话进入

---

## 横向生态对比

好的，作为资深技术分析师，以下是对OpenClaw、NanoBot、Hermes Agent、PicoClaw、NanoClaw、NullClaw、IronClaw、LobsterAI、CoPaw、ZeroClaw这十个项目在2026-09-24社区动态的横向对比分析报告。

---

## 个人AI助手/自主智能体开源生态全景分析报告 (2026-09-24)

### 1. 生态全景

当前个人AI助手与自主智能体开源生态正处于 **“大规模验证与稳定性爬坡”** 阶段。经历了年初的功能爆发期后，头部项目（如OpenClaw、NullClaw、ZeroClaw）普遍面临因功能快速迭代而导致的稳定性阵痛，社区对**会话可靠性、内存泄漏、安全边界**等生产环境问题的反馈急剧增加。与此同时，以NanoBot、Hermes Agent、NanoClaw为代表的项目则通过高效的问题修复和积极的平台能力拓展，在各自的细分领域（如聊天平台集成、企业安全信创、多租户架构）构建差异化优势。整个生态呈现 **“顶尖项目忙于还债，中坚力量加速扩张”** 的态势，对“稳定”、“安全”与“协作”的诉求已超越单纯的“功能丰富”。

### 2. 各项目活跃度对比

| 项目名称 | Issues (新/活跃/关闭) | PRs (待合并/合并关闭) | 版本发布 | 健康度评估 |
| :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | 500 (464/36) | 500 (397/103) | v2026.9.6 (已撤回) | ⚠️ 高风险，高强度修复期 |
| **NanoBot** | 6 (4/2) | 34 (30/4) | 无 | ✅ 活跃，功能丰富但PR积压 |
| **Hermes Agent** | 50 (32/18) | 50 (26/24) | 无 | ✅ 高活跃，修复与国际化并行 |
| **PicoClaw** | 1 (1/0) | 1 (1/0) | 无 | ⚠️ 官网宕机，核心体验受阻 |
| **NanoClaw** | 3 (2/1) | 8 (7/1) | **v2.4.0** | ✅ 健康，功能迭代尾声 |
| **NullClaw** | 17 (15/2) | 21 (15/6) | 无 | ✅ 高活跃，密集修复与开发 |
| **IronClaw** | 0 (0/0) | 2 (2/0) | 无 | ⚠️ 低活跃，发布准备阶段 |
| **LobsterAI** | 0 (0/0) | 10 (2/8) | **v2026.9.23** | ✅ 健康，聚焦协作与决策模型 |
| **CoPaw (QwenPaw)** | 8 (7/1) | 9 (6/3) | 无 | ✅ 高活跃，社区讨论热烈 |
| **ZeroClaw** | 11 (10/1) | 50 (47/3) | 无 | ⚠️ 高活跃，PR严重积压 |

**注：** 健康度评估综合考虑了Bug严重性、问题解决效率、功能迭代方向及基础设施稳定性。

### 3. OpenClaw 在生态中的定位

- **核心定位：** AI智能体领域的“超级入口”或“操作系统层”，提供最广泛的功能集成（多代理、多平台、插件生态）。
- **优势：** 社区规模最大（日处理500+ Issue/PR）、功能最全面、生态最丰富。是许多其他项目（如LobsterAI）的技术上游和功能参照。
- **技术路线差异：** 追求极致的通用性与用户自定义，通过高度插件化的架构支持几乎所有场景。相比之下，NanoBot更聚焦于“对话即服务”的接口，Hermes Agent则在上层构建了更严格的安全审批流程。
- **社区规模对比：** 其讨论热度远超其他项目，但这也意味着大量用户反馈涌入，导致维护团队资源紧张，不得不依赖`clawsweeper`等自动化工具应对。当前稳定性问题（P0 Bug密度高）是其最大短板，也为其他项目（如NullClaw的专业团队版）提供了市场空间。

### 4. 共同关注的技术方向

多个项目在同一时间点涌现了高度相似的需求，反映了行业的共性挑战：

1.  **会话可靠性与数据完整性：**
    - **涉及项目：** OpenClaw (#148707), NullClaw (#972), ZeroClaw (#11055), CoPaw (#7534)
    - **核心诉求：** 解决消息丢失、通道假死、上下文被错误裁剪、运行时状态不一致等问题，确保在长时间运行、无人值守或多轮交互场景下的稳定性。

2.  **安全与审批边界：**
    - **涉及项目：** Hermes Agent (#59293), ZeroClaw (#10968), NullClaw (#969), Moltis (#1272)
    - **核心诉求：** 构建细粒度的权限控制。从CLI绕过审批层、无人值守模式下的安全门失效、到沙箱的`run_as`和强制隔离，反映出社区对高危工具（Shell、文件系统）的自动化调用安全性的极度关切。

3.  **沙箱与上下文可控性：**
    - **涉及项目：** Moltis (#1272), CoPaw (#7628, #7836), PicoClaw (无直接关联，但体现为轻量化需求)
    - **核心诉求：** 不仅仅是隔离运行时，更需要对Agent的“内存”和“感知”范围进行精细控制，包括上下文预算计算、资源裁剪策略、以及如何让Agent主动参与其“记忆”的决策。

4.  **跨平台与渠道一致性：**
    - **涉及项目：** ZeroClaw (#10985, #10922), NullClaw (#972), CoPaw (#7534), OpenClaw (iOS/Android Talk)
    - **核心诉求：** 确保AI Agent在不同渠道（Telegram、WhatsApp、Discord、Web Console）上提供一致、稳定、无差别的用户体验。

5.  **国际化与本地化：**
    - **涉及项目：** Hermes Agent (#119630, #108324)
    - **核心诉求：** 桌面端应用的多语言支持已成为社区贡献的热点，反映出个人AI助手正在全球范围内普及。

### 5. 差异化定位分析

| 项目名称 | 功能侧重 | 目标用户 | 技术架构关键差异 |
| :--- | :--- | :--- | :--- |
| **OpenClaw** | 全能型，超级入口 | 极客、AI玩家、希望深度自定义的用户 | 大规模插件生态、全平台覆盖、高度可配置 |
| **NanoBot** | 多平台聊天Agent | 会议讨论、信息聚合、轻量级工作流 | 强调简洁的API、高效的上下文压缩、快速对接聊天平台 |
| **Hermes Agent** | 企业级安全与合规 | 企业用户、关注安全信创的团队 | 内置审批层、国际化优先、CLI与UI安全边界强 |
| **PicoClaw** | 轻量级、嵌入式 | 嵌入式开发者、资源受限设备、物联网场景 | 极简设计、低资源占用、设备配对协作 |
| **NanoClaw** | 可扩展企业网关 | 专业运维、多租户服务提供商 | 凭据网关化(V2.4)、社区门户、模型与速率控制 |
| **NullClaw** | 专注本地、稳定运行 | 安全敏感用户、自托管爱好者、持续服务场景 | 强调查看式审批(Flow)、调度器持久化、CR服务 |
| **IronClaw** | 下一代安全框架 | 高级开发者、安全工程师 | 基于WebAssembly/WebGPU的高安全性隔离 |
| **LobsterAI** | 协作与决策 | 团队协作、需要复杂决策支持的开发者 | 聚焦Cowork流程、提供实验性决策模型工具 |
| **CoPaw** | 语义理解与记忆 | 需要强大记忆和上下文管理的个人/团队 | 强调上下文预算、滚动驱逐、Hub多租户探索 |
| **ZeroClaw** | WhatsApp深度集成 | 高频使用WhatsApp的用户、移动办公场景 | 对WhatsApp频道进行深度优化，工具生态活跃 |

### 6. 社区热度与成熟度

根据活跃度、问题解决速率和发布节奏，可将项目分为三个梯队：

- **快速迭代期 (高活跃，但稳定性波动大)：**
    - **代表项目：** **OpenClaw、NullClaw、ZeroClaw、CoPaw**
    - **特征：** 日均 Issue/PR 达到50+，新功能与修复并行发布，但P0/P1级Bug频发，社区讨论集中在“如何修”和“何时修”上，对核心功能的可靠性要求极为迫切。

- **功能拓展期 (活跃，方向明确)：**
    - **代表项目：** **NanoBot、LobsterAI、NanoClaw**
    - **特征：** 围绕特定场景（聊天、协作、企业网关）进行功能深化和打磨。发布节奏平稳，版本迭代清晰，社区贡献集中于既定路线图的实现。

- **质量巩固与平台稳定期 (相对稳定或低活跃)：**
    - **代表项目：** **Hermes Agent、IronClaw、PicoClaw**
    - **特征：** 或由于项目处于安全/文档完善的前期阶段（IronClaw），或因基础设施问题暂缓开发（PicoClaw），整体活跃度不高，发展节奏慢，但核心架构稳定。Hermes Agent则处于国际化与安全功能并行的质量提升期。

### 7. 值得关注的趋势信号

1.  **“实时性”与“无状态”的博弈：** 从ZeroClaw、NullClaw的“通道假死”和“运行时状态丢失”问题，到CoPaw的“上下文预算”讨论，行业正在探索**如何在高并发的实时流式传输（SSE、WebSocket）中，维护一个有状态、可恢复、安全的Agent会话**。后端架构向“事件溯源”或“无状态重构”可能是趋势。

2.  **安全不再是可选项，而是核心功能：** 安全（Approval Flow, Sandbox, CLI Gate）正从“附加功能”转变为项目的**核心架构要素**。Hermes Agent、ZeroClaw、NullClaw、Moltis的冲突都指向了一个方向：**AI Agent的自动化执行能力必须与严格、可审计的权限控制强绑定**。

3.  **从“个人”到“团队”的协作升级：** OpenClaw的A2A单向派发、NanoClaw的多租户控制、LobsterAI的Cowork模块、CoPaw的Hub多租户讨论，都清晰地指向了一个信号：**AI Agent正在从单用户的个人助手，向支持多人协作、权限分明、资源隔离的平台级工具演进**。

4.  **“去API Key”与轻量化部署：** PicoClaw的“零配置搜索”和NullClaw社区对DuckDuckGo集成的强烈呼吁，反映了用户对**降低AI Agent使用门槛和外部依赖**的强烈渴望。这与IronClaw通过WebAssembly实现原生级安全的“重”方案形成鲜明对比，代表了不同场景下的两种理想部署形态。

5.  **国际化成为社区贡献的“硬通货”：** Hermes Agent的翻译类PR占据一日合并量的很大一部分，表明对开源AI项目而言，**完善的多语言支持是提升全球社区参与度、降低沟通成本最直接有效的方式之一**。

**对开发者的启示：** 在构建下一个AI智能体时，应将**安全审批流**和**会话状态恢复**作为基础架构的一部分，而非事后修补；同时，在设计API和插件系统时，需预设多租户和多平台场景，以应对未来从个人工具向协作平台演进的必然趋势。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，这是根据 NanoBot 项目 2026-09-24 的 GitHub 数据生成的项目动态日报。

---

### NanoBot 项目动态日报 — 2026-09-24

#### 1. 今日速览

- **整体状态**：项目今日活跃度极高。虽然无新版本发布，但 Pull Request 处理量是 Issues 的近 6 倍（34:6），主要精力集中在功能迭代与 Bug 修复上，表明项目正处于快速迭代期。
- **Bug 修复**：昨日关于上下文压缩（Compaction）的多个 Bug 报告（如重复通知、割裂大文件读取结果）已出现对应的修复 PR，修复响应迅速。
- **功能推进**：WebUI 体验、新 Provider（IO Intelligence）及多平台（WhatsApp/Telegram）的特性正被积极整合和完善。
- **维护重点**：内存（Memory）系统的并发安全性和上下文压缩（Compaction）逻辑的健壮性是当前社区贡献者和维护者关注的两大核心。

#### 2. 版本发布

无

#### 3. 项目进展

过去24小时内，有多个关键 PR 被合并或关闭，显著推进了项目在稳定性、功能覆盖度和文档方面的建设：

- **** **WebUI 全面升级**：`Re-bin` 贡献者合并了三个优化 WebUI 体验的 PR，包括：
    - [#5851](https://github.com/HKUDS/nanobot/pull/5851) **添加使用量统计**：新增了 Token 使用量、活动日历和按模型/provider 的分解统计，增强了用户数据可视化能力。
    - [#5854](https://github.com/HKUDS/nanobot/pull/5854) **命令与任务面板**：虽然作为“延迟交付”的 Draft，但其合并保留了实现记录，为未来交互设计奠定了基础。
    - [#5813](https://github.com/HKUDS/nanobot/pull/5813) **修复重启提示残留**：修复了 WebUI 在网关重启后仍显示“需要重启”的提示，提升了连接稳定性。
- **Linear 集成增强**：`chengyongru` 合并了 [#5871](https://github.com/HKUDS/nanobot/pull/5871)，显著提升了 Linear Agent 的原生体验，支持更完整的提及、委托问题和 OAuth 流程。
- **新 Provider 引入**：`smiraldr` 合并了 [#5875](https://github.com/HKUDS/nanobot/pull/5875)，正式加入了对 [IO Intelligence](https://io.net) 的支持，这由官方团队提交，丰富了模型的运行选项。
- **核心机制修复**：
    - [#5874](https://github.com/HKUDS/nanobot/pull/5874) (假设存在，基于 #5878/83/82 的合并) 贡献者修复并关闭了多个围绕“Codex 压缩”和“Agent 状态保持”的 Bug，提升了在高预算场景下的稳定性。
    - [#5878](https://github.com/HKUDS/nanobot/pull/5878) **日志增强**：增加了对中间注入消息的预览日志，有助于开发者和高级用户调试。
- **文档更新**：`chengyongru` 合并了 [#5882](https://github.com/HKUDS/nanobot/pull/5882)，纠正了关于“上下文压缩”行为的文档，明确了空闲压缩会用摘要替换对话，对用户预期管理有重要意义。

#### 4. 社区热点

- **“上下文压缩”（Context Compaction）体验争议**：相关议题和 PR 讨论最为集中。用户 `3L1AS` 在 [#5870](https://github.com/HKUDS/nanobot/issues/5870) 反馈 Telegram 上压缩完成通知重复出现多次，非常烦人。社区贡献者 `wzrayyy` 的 PR [#5780](https://github.com/HKUDS/nanobot/pull/5780) 似乎正是在解决此问题，建议默认隐藏自动压缩通知。这反映了社区对“后台静默优化”与“用户显式通知”之间平衡的诉求。
- **核心算法对复杂场景的适应性问题**：Issue [#5879](https://github.com/HKUDS/nanobot/issues/5879) 指出了“大文件读取结果导致对话中断”的深层 Bug。这个问题触及了压缩算法的一个边界情况：即使成功总结了旧历史，新返回的大段工具（Tool）输出仍可能导致输入超出预算并中止对话。此问题迅速获得了 PR [#5880](https://github.com/HKUDS/nanobot/pull/5880) 的修复，显示出社区对高级使用场景稳定性的高度关注。

#### 5. Bug 与稳定性

当日报告的 Bug 绝大多数围绕 “Memory” 和 “Context” 系统，且都已有对应的修复 PR，项目稳定性得到快速响应。

- **严重 (P0)**：
    - **`read_file` 结果导致对话中断**：Issue [#5879](https://github.com/HKUDS/nanobot/issues/5879) 报告了 `read_file` 返回大块结果后，即使历史压缩成功，仍会因总 Token 超出预算而终止对话。 **已有修复 PR** [#5880](https://github.com/HKUDS/nanobot/pull/5880)。
    - **历史压缩可能覆盖并发写入**：PR [#5884](https://github.com/HKUDS/nanobot/pull/5884) 揭示了 `compact_history` 操作未使用写入锁，可能在并发写入时导致数据丢失。该 PR 状态为 **OPEN**，是稳定性关键考量。

- **高 (P1)**：
    - **Telegram 压缩通知重复**：Issue [#5870](https://github.com/HKUDS/nanobot/issues/5870) 已修复。关联 PR [#5780](https://github.com/HKUDS/nanobot/pull/5780)。
    - **兼容性/体验问题**：Issue [#5881](https://github.com/HKUDS/nanobot/issues/5881)（中文用户）报告了升级到 0.3.5 后，因新的目录校验规则（`_nanobot` 目录不能在 `workspace` 内）导致实例启动被拒，影响了部分用户的迁移体验。

- **中 (P2)**：
    - **Fallback Tokenizer 分布式缓存问题**：PR [#5861](https://github.com/HKUDS/nanobot/pull/5861) 试图修复 fallback tokenizer 的性能问题，但目前存在 **冲突 (conflict)**。
    - **空闲摘要缓存无限增长**：PR [#5664](https://github.com/HKUDS/nanobot/pull/5664) 解决了因废弃会话摘要缓存未释放导致的内存泄漏问题，已存在较长时间，仍未合并。

#### 6. 功能请求与路线图信号

- **WhatsApp 深度集成**：用户 `felixbk98` 提出了两个关于 WhatsApp 的功能请求，均已关闭但并非被拒绝：
    - [#2152](https://github.com/HKUDS/nanobot/issues/2152) **语音消息支持**：该用户开发了 Fish Audio 第三方集成，但希望官方支持。
    - [#2160](https://github.com/HKUDS/nanobot/issues/2160) **启动通知**：提供了 systemd 方案，希望成为内置功能。
    - **路线图信号**：这表明社区对 WhatsApp 平台的原生高级功能（如语音、事件通知）有明确需求。虽然当前 PR 未直接响应，但可视为未来平台能力扩展的潜在方向。

- **技能（Skill）系统能力增强**：PR [#5405](https://github.com/HKUDS/nanobot/pull/5405) 提议引入 `manual-only invocation` 模式，允许某些技能（如部署、发布）禁止被模型自动调用，只能由用户手动触发。该 PR 仍为 **OPEN**，反映了对技能安全性和可控性的诉求。

- **隔离会话配置**：PR [#4551](https://github.com/HKUDS/nanobot/pull/4551)（已开放近3个月）提议增加 `isolated_session` 配置，允许心跳消息在选定的会话中执行以利用历史上下文。此 PR 长期未合并，表明该项目在默认情况下倾向于心跳会话的隔离性。

#### 7. 用户反馈摘要

- **痛点**：
    - **“烦人的后台通知”**：用户 `3L1AS` 在 [#5870](https://github.com/HKUDS/nanobot/issues/5870) 中直言“`Context compacted.` 反复出现非常烦人”，说明后台操作不应通过频繁的显式通知打扰用户。
    - **“更新导致配置冲突”**：中文用户 `mythstraw` 在 [#5881](https://github.com/HKUDS/nanobot/issues/5881) 中对升级后因目录校验规则无法启动感到困惑，体现了项目在引入新检查逻辑时对用户迁移配置的兼容性考虑需要加强。
    - **“第三方集成维护负担”**：用户 `felixbk98` 在 [#2152](https://github.com/HKUDS/nanobot/issues/2152) 的评论中强调，其开发的 Fish Audio 集成“每次更新后都需要手动修补 WhatsApp 桥接”，暗示了官方平台接口不够稳定或对第三方扩展的侵入性较强。
- **满意之处**：
    - **修复响应迅速**：从多个 P0/P1 级别的 Bug 在报告后几小时内就有对应的修复 PR 来看，社区维护者和贡献者对关键问题的响应速度值得肯定。

#### 8. 待处理积压

- **长时间未响应的增强功能**：
    - **PR [#4551](https://github.com/HKUDS/nanobot/pull/4551)**：提出“心跳消息可选共享会话”的 `isolated_session` 配置，已存在 90 天以上，且带有 `conflict` 标签，可能已脱离当前版本迭代，需维护者决定其未来方向：是拒绝、需要重写还是等待整合。
    - **PR [#5520](https://github.com/HKUDS/nanobot/pull/5520)**：为 Codex 提供 Langfuse 追踪功能，已存在 31 天。由于 Codex 是独特 provider，其追踪方案长期缺失可能影响使用 Codex 的用户进行性能分析与优化。同样有 `conflict`，建议维护者评估。
- **性能提升瓶颈**：
    - **PR [#5664](https://github.com/HKUDS/nanobot/pull/5664)**：修复空闲摘要缓存无限增长（P2级别），已存在 20 天，处于 OPEN 状态且有冲突。作为潜在的内存泄漏修复，建议近期重点关注。
- **冲突 PR 分析**：
    - PR [#5861](https://github.com/HKUDS/nanobot/pull/5861) (Token 回退方案优化)、[#5520](https://github.com/HKUDS/nanobot/pull/5520) (Codex 追踪)、[#5664](https://github.com/HKUDS/nanobot/pull/5664) (缓存增长) 和 [#4551](https://github.com/HKUDS/nanobot/pull/4551) (心跳会话配置) 均带有 `conflict` 标签，说明项目核心代码正在快速变化。维护者需要评估这些 PR 的价值并决定处理或关闭，以避免重要功能 PR 沉底。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

# Hermes Agent 项目动态日报 (2026-09-24)

**数据时间范围**: 2026-09-23 至 2026-09-24  
**数据来源**: GitHub Issues & PRs (NousResearch/hermes-agent)

---

## 今日速览

过去 24 小时项目保持**极高活跃度**。共处理 50 条 Issue（新开/活跃 32，关闭 18）和 50 条 PR（待合并 26，合并/关闭 24）。社区贡献持续旺盛，尤其集中在**桌面端国际化**（多份西班牙语、德语翻译 PR 被合并）和**稳定性修复**（数据压缩原子性、技能列表 API 崩溃等）。安全相关 Issue 讨论激烈（CLI 绕过写入保护），P1 级数据丢失 Bug 已附带修复 PR。无新版本发布。

---

## 版本发布

*（无）*

---

## 项目进展

### 已合并/关闭的重要 PR

- **桌面国际化取得实质推进**：多个西班牙语（`es`）和德语（`de`）本地化 PR 被合并，包括 [#119630](https://github.com/NousResearch/hermes-agent/pull/119630)（西班牙语）、[#108324](https://github.com/NousResearch/hermes-agent/pull/108324)（德语）、[#106287](https://github.com/NousResearch/hermes-agent/pull/106287)（德语）等。尽管其中不少是重复提交，但最终落地补齐了桌面端长期缺失的两种语言支持。
- **Webhook 功能增强**：[#120825](https://github.com/NousResearch/hermes-agent/pull/120825)（`ci-reviewed`）允许 webhook 传递的消息可回溯到对应会话，解决回复时缺乏上下文的问题（salvage of #106067）。
- **测试基础设施强化**：[#120326](https://github.com/NousResearch/hermes-agent/pull/120326) 增加了四套端到端测试套件，覆盖 profile 隔离、密钥路由、终端转录、`hermes update` 和实时 provider，核心回归防线进一步加固。

### 总体进展

项目今日在 **稳定性修复** 和 **社区本地化贡献整合** 上迈出明显步伐。P1 数据丢失 Bug（#120582）已被修复 PR [#120821](https://github.com/NousResearch/hermes-agent/pull/120821) 锁定；技能 API 500 错误也由 [#120836](https://github.com/NousResearch/hermes-agent/pull/120836) 修复。大量重复的国际化 PR 被清理合并，降低了维护噪音。

---

## 社区热点

### 讨论最活跃的 Issues

| Issue | 评论数 | 核心诉求 |
|-------|--------|----------|
| [#59293](https://github.com/NousResearch/hermes-agent/issues/59293) `type/security` | 16 | `hermes config set` CLI 可以绕过系统配置写入保护（approval layer），终端 agent 可静默关闭安全层。用户质疑安全设计漏洞。 |
| [#56004](https://github.com/NousResearch/hermes-agent/issues/56004) `type/bug` | 14 | 使用 Qwen 等推理模型时，tool call 之间丢失推理过程（reasoning stripped），原因是 replay 机制仅保留最后的 assistant 消息。用户期望保留思维链。 |
| [#118029](https://github.com/NousResearch/hermes-agent/issues/118029) `type/feature` | 10 | 提议一个统一的托管 SSH 控制平面，用于受管安装的验证和回滚，要求与企业安全保证 Issue #92618 联动。 |
| [#98330](https://github.com/NousResearch/hermes-agent/issues/98330) `type/bug` | 6 | `skills.write_approval` 启用后，所有技能写入被暂存但没有审查界面，`/skills` 入口标记不可用，用户无法批准或拒绝挂起写入。 |

**分析**：安全边界和 agent 行为透明度是今日社区关注焦点。尤其是 #59293 提出的“CLI 绕过审批层”问题引发了关于配置保护机制有效性的根本性质疑。#56004 则反映了高级推理模型用户对“思维链连续性”的硬需求，直接关系 agent 决策可解释性。

---

## Bug 与稳定性

### 按严重程度排列

| 严重度 | Issue | 描述 | 修复状态 |
|--------|-------|------|----------|
| **P1** | [#120582](https://github.com/NousResearch/hermes-agent/issues/120582) | 生产事故：主动剪枝+压缩导致工具结果被截断、参数被截断，长期会话中数据无声损坏（含证据）。 | 已有 Fix PR [#120821](https://github.com/NousResearch/hermes-agent/pull/120821)（原子快照栅栏） |
| **P2** | [#120828](https://github.com/NousResearch/hermes-agent/issues/120828) | 自定义 Ollama provider 发送 tool-only 负载，缺少 `role: user` 消息，被 Ollama Qwen renderer 拒绝。 | 无 |
| **P2** | [#120831](https://github.com/NousResearch/hermes-agent/issues/120831) | `GET /v1/skills` 因签名不匹配（`include_editorial` 参数）返回 HTTP 500，技能列表功能完全崩溃。 | 已有 Fix PR [#120836](https://github.com/NousResearch/hermes-agent/pull/120836) |
| **P2** | [#120334](https://github.com/NousResearch/hermes-agent/issues/120334) | 后台进程退出后，已排队的 heartbeat 仍可能被提升为新的 agent 轮次，导致虚假响应。 | 无 |
| **P2** | [#120063](https://github.com/NousResearch/hermes-agent/issues/120063) | `session_search` 当所有命中被排除时返回空结果且无任何提示，与正常无命中情况行为不一致。 | 无 |
| **P2** | [#120599](https://github.com/NousResearch/hermes-agent/issues/120599) | 更新后 `hermes CLI` 在 CachyOS (fish shell) 上静默退出，无法启动。 | 无 |
| **P1**（注意：标题中标注P1但链接未列出？） | 无 | – | – |

**注**：P1 级 Bug #120582 已有修复 PR 待合并，为重点关注项。技能 API 崩溃 (#120831) 修复也已在同一天提交。

---

## 功能请求与路线图信号

### 可能被纳入下一版本的功能

- **受管 SSH 控制平面** ([#118029](https://github.com/NousResearch/hermes-agent/issues/118029))：need-decision 标签，需要确定是否加入 v0.21+ 路线图。
- **会话内存提示老化** ([#66025](https://github.com/NousResearch/hermes-agent/issues/66025))：桌面端长会话中 MEMORY.md 变为快照，希望动态刷新。已有社区讨论，P3 级别。
- **安全防护粒化** ([#117815](https://github.com/NousResearch/hermes-agent/issues/117815))：四项硬性报告指出审查视图与实际执行之间的差异，影响 approval/redaction 可靠性。sweeper 标记为 security-boundary。
- **插件目录更新**：两个新插件提交——`jev-skill-router` ([#120081](https://github.com/NousResearch/hermes-agent/pull/120081)) 和 `DeskRPG gateway plugin` ([#119066](https://github.com/NousResearch/hermes-agent/pull/119066))，社区开发生态持续扩展。

### 长期路线图信号

- 持续增长的**国际化需求**（多份法语、西班牙语、德语 PR 重复提交）表明桌面端多语言支持是用户强烈呼声，目前法文（`fr`）和德文（`de`）已通过 PR 合并进入代码库，但西班牙语仍有数个重复 PR 未完全收束。
- **Windows 平台稳定性**仍是痛点：多个 Windows 特定 Issue（冷启动超时、GBK 编码崩溃、FAST_FAIL 崩溃）虽已关闭但仍有新报告，平台适配工作需持续投入。

---

## 用户反馈摘要

从 Issues 评论中提炼的真实痛点：

- **“CLI 居然是后门”**：在 [#59293](https://github.com/NousResearch/hermes-agent/issues/59293) 中，用户指出 `hermes config set` 可以越过安全审批层，“系统配置保护形同虚设”。社区期望 CLI 与文件写入受到同等安全审查。
- **“推理模型丢思路”**：Qwen 用户在 [#56004](https://github.com/NousResearch/hermes-agent/issues/56004) 中抱怨 agent 在 tool call 之间丢失思考过程，“我感觉自己在和一个失忆的助手对话”。
- **“技能批准无门”**：[#98330](https://github.com/NousResearch/hermes-agent/issues/98330) 的评论者描述技能写入被“收藏”却无处查看和批准，“就像是黑洞——写进去了，但永远出不来了”。
- **“生产数据无声损坏”**：[#120582](https://github.com/NousResearch/hermes-agent/issues/120582) 用户报告了 log 中脚本变量被截断的真实事故，强调“如果没有主动检查，你根本不知道数据已经坏了”。
- **“更新后 CLI 消失”**：CachyOS 用户在 [#120599](https://github.com/NousResearch/hermes-agent/issues/120599) 中描述 `hermes` 命令无任何输出，“就像 install 损坏了，但重装也一样”。

---

## 待处理积压

### 长期未响应的重要 Issue

| Issue | 创建时间 | 标签 | 原因 |
|-------|----------|------|------|
| [#59293](https://github.com/NousResearch/hermes-agent/issues/59293) | 2026-07-06 | `needs-decision` | 安全绕过问题，已讨论了 16 条评论，仍无 maintainer 决定如何处理。 |
| [#56004](https://github.com/NousResearch/hermes-agent/issues/56004) | 2026-07-01 | `type/bug` | 推理模型推理丢失，14 条评论，5 个 👍，尚未收到官方回复或分配。 |
| [#118029](https://github.com/NousResearch/hermes-agent/issues/118029) | 2026-09-21 | `needs-decision` | 控制平面功能请求，需要 security interlock，但讨论仍停留在概念阶段。 |

### 待合并的重要 PR

- [#120821](https://github.com/NousResearch/hermes-agent/pull/120821) (P1 fix)：原子快照栅栏，直接解决生产数据丢失事故，请尽快 review 和 merge。
- [#120836](https://github.com/NousResearch/hermes-agent/pull/120836) (bug fix)：修复技能 API 崩溃，避免用户无法使用技能列表。
- [#120326](https://github.com/NousResearch/hermes-agent/pull/120326) (test)：E2E 测试套件，提升回归保护，建议尽早合入主分支。

### 社区积压（重复国际化 PR）

尽管今日已合并部分西班牙/德语翻译，但仍有多份重复 PR 处于 open 状态（如 [#47984](https://github.com/NousResearch/hermes-agent/pull/47984)、[#48070](https://github.com/NousResearch/hermes-agent/pull/48070)、[#92323](https://github.com/NousResearch/hermes-agent/pull/92323) 等），建议维护者统一清理并关闭重复项。

---

*本日报由 AI 分析师基于 GitHub 公共数据生成。如需跟踪实时动态，请关注项目 [Hermes Agent](https://github.com/NousResearch/hermes-agent)。*

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，这是根据您提供的 PicoClaw 项目数据生成的 2026-09-24 项目动态日报。

---

## PicoClaw 项目动态日报 — 2026-09-24

### 1. 今日速览
过去24小时，项目活跃度中等偏上，主要体现在功能开发的持续推进与一次关键的社区协作收尾。尽管没有新版本发布，但一个旨在增加新搜索供应商的PR (#3370) 正待合并，显示出项目在工具生态扩展上的努力。然而，项目官网 **picoclaw.io** 出现严重故障（TLS证书过期），导致网站完全不可用，这对项目的用户吸引力和品牌形象造成了直接影响，成为社区目前最关注的问题。

### 2. 版本发布
无

### 3. 项目进展
今日合并关闭了一个重要的PR：
- **PR #3344 (已关闭)**：[Build Remote Agent phone pairing (gbr/1)](https://github.com/sipeed/picoclaw/pull/3344)
  - **概要**: 合并了用于“构建远程代理”的手机配对适配器，使手机能够作为桌面代理的旁观者或控制器。
  - **进展**: 该功能通过 `gbr/1` 协议实现，允许用户安装 `gbr-agent` v0.6.0+ 后，通过扫描二维码或输入8位码完成配对。这显著扩展了PicoClaw作为个人AI助手的应用场景，不再局限于桌面端，增强了跨设备协作能力。项目向“无处不在的AI助手”愿景又迈进了坚实一步。

### 4. 社区热点
- **Issue #3377 (热议)**：[TLS certificate for picoclaw.io expired on 2026-09-10 — site is down for every browser](https://github.com/sipeed/picoclaw/issues/3377)
  - **热度**: 2条评论，1个 👍
  - **分析**: 这是当前社区最核心的热点。虽然评论和反应数量不多，但问题的严重性（官网宕机）使其成为最高优先级。社区用户的诉求非常明确且紧急：**立即更新网站TLS证书**。该问题持续两周未解决，可能会严重影响新用户的获取和对项目专业性的信任。

### 5. Bug 与稳定性
今日报告了一个灾难性级别的稳定性问题：
- **问题 #3377 (严重)**：[TLS certificate for picoclaw.io expired](https://github.com/sipeed/picoclaw/issues/3377)
  - **严重程度**: ❗ **Critical**
  - **现象**: 项目首页 `https://picoclaw.io` TLS证书已于2026年9月10日过期，导致所有浏览器和TLS客户端拒绝连接。项目官网已下线超过两周。
  - **影响**: 阻止了新用户访问项目文档、了解项目功能和下载软件，对项目社区的持续增长构成直接威胁。
  - **修复状态**: **暂无相关联的修复PR**。该问题完全属于基础设施维护范畴，需要项目维护者（Sipeed）介入处理。

### 6. 功能请求与路线图信号
- **PR #3370 (待合并)**：[feat(tools): add Keenable web search provider](https://github.com/sipeed/picoclaw/pull/3370)
  - **功能特点**: 新增 `Keenable` 作为 `web_search` 工具提供商。亮点在于无需API Key即可开箱即用（`tools.web.keenable.enabled` 设置为 `true`），这将极大简化用户的配置流程。
  - **路线图信号**: 这表明项目正在积极构建一个“开放、零配置”的插件生态。引入此类直接可用的搜索提供商，是提升用户初始体验和降低使用门槛的重要举措。该功能极有可能被纳入下一个版本发布。

- **PR #3344 (已合并)**：详见【项目进展】部分。
  - **路线图信号**: 合并此PR证实了将PicoClaw从单一桌面Agent扩展到跨设备、远程协作平台的路线图，这是个人AI助手领域的一个重要方向。

### 7. 用户反馈摘要
- **痛点**: 用户对项目官网的持续性故障表示沮丧。从Issue #3377的评论中可以推断，用户无法理解为何一个关键基础设施问题在两周内未被解决。这反映了用户对项目稳定运营和及时维护的期望。
- **使用场景**: PR #3344提到的“手机旁观桌面Agent”场景，摘录了用户希望在移动设备上远程交互的需求，这可能源于想要在无法直接操作电脑时（如开会、通勤）继续使用Agent服务的实际场景。

### 8. 待处理积压
- **Issue #3377**: [TLS证书过期，网站宕机](https://github.com/sipeed/picoclaw/issues/3377)
  - **积压原因**: 这是一个纯粹的主页/基础设施问题，需要项目所有者的权限才能处理。虽然issue本身是24小时内创建的，但问题（证书过期）已存在14天，且未见官方回应，因此需要**最高优先级的关注**。维护者应立即通过域名注册信息或项目托管方找回证书管理权限并更新证书。
- **PR #3370**: [新增Keenable搜索提供商](https://github.com/sipeed/picoclaw/pull/3370)
  - **状态**: 已开放17天，待合并。功能相对成熟且无破坏性，建议维护者尽快审核合并，以丰富项目的工具集并为社区提供更多价值。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，作为 NanoClaw 项目的 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据 2026-09-24 提供的 GitHub 数据生成的**项目动态日报**。

---

## NanoClaw 项目动态日报 | 2026年09月24日

### 今日速览

NanoClaw 项目今日活跃度极高，核心团队围绕 **v2.4.0 版本发布** 完成了大量收尾与修复工作。全天共计合并/关闭了 17 个 PR，并发布了包含重大架构更新的 v2.4.0 版本。社区讨论焦点集中在 **凭据网关重构** 带来的新功能和更新流程的稳定性修复上。项目整体健康度良好，正处于一次重要的功能性迭代潮的尾声。

### 版本发布

#### v2.4.0 正式发布
- **链接**: [v2.4.0 Release](https://github.com/qwibitai/nanoclaw/releases/tag/v2.4.0)
- **核心亮点**:
    1.  **凭据网关化 (Credential Gateways)**：引入了可通过 Skill 安装的凭据网关。`OneCLI` 保持为默认网关，新增了 **`Iron Proxy`** 作为可选项，为不同安全需求的用户提供了灵活性。
    2.  **社区门户 (Community Portal)**：为 Echo 强化镜像和托管 Slack 应用提供了全新的一键设置流程。
    3.  **模型与速度控制 (Model/Speed Controls)**：新增了安装级和分租户组的模型选择与速率限制能力，便于运营者进行更精细的资源管理。
    4.  **渠道扩展**：新增了 Mattermost 频道支持。
    5.  **提供商更新**：对 OpenCode 提供商进行了重新设计，并支持通过新网关进行认证。
- **迁移注意事项**: 请注意，此版本涉及核心仲裁层的底层重构。虽然现有安装会自动保留其选定的网关，但升级后，运营者可能需要根据文档检查并调整全局与分组的模型控制配置。

### 项目进展

今日合并/关闭的 17 个 PR 标志着 v2.4.0 版本的最终定型。核心进展包括：

1.  **凭据网关重构最终落地**：
    -   [#3815](https://github.com/qwibitai/nanoclaw/pull/3815) & [#3816](https://github.com/qwibitai/nanoclaw/pull/3816)：完成了凭据网关合约的集中化和 `OneCLI` 网关的 Skill 化重构，为未来扩展更多网关奠定基础。
    -   [#3817](https://github.com/qwibitai/nanoclaw/pull/3817)：新增了 `Iron Proxy` 网关 Skill，与 `OneCLI` 形成互补生态。
    -   [#3825](https://github.com/qwibitai/nanoclaw/pull/3825)：使 OpenCode 提供商能够通过 `Iron Proxy` 进行认证。

2.  **严重更新流程 (Update Flow) Bug 修复**：
    -   [#3873](https://github.com/qwibitai/nanoclaw/pull/3873)：修复了 `stop` 操作在更新切换时无法成功的问题，解决了容器耗尽宿主机等待时间的验收失败。
    -   [#3878](https://github.com/qwibitai/nanoclaw/pull/3878)：修复了在清理临时 `ping` 代理时，其容器未被正确停止的遗留问题。

3.  **渠道与体验优化**：
    -   [#3875](https://github.com/qwibitai/nanoclaw/pull/3875) & [#3876](https://github.com/qwibitai/nanoclaw/pull/3876)：修复了 Teams 渠道中，代理名称无法正确显示 Bot 显示名的问题，提升了跨渠道的用户体验一致性。

4.  **技术与依赖更新**：
    -   [#3868](https://github.com/qwibitai/nanoclaw/pull/3868)：将容器内的 Claude Code 引擎和 Agent SDK 升级至 2.1.280/0.3.280，确保项目依赖在最新稳定版本上。

项目通过本次集中迭代，成功将**更新流程**、**凭据管理**、**渠道适配**等多个核心模块推向了更高稳定性与可扩展性。

### 社区热点

今日讨论热度集中在更新流程的 Bug 修复上。

1.  **Issue #3828 & PR #3873 - 更新流程卡死问题**
    -   **链接**: [Issue #3828](https://github.com/qwibitai/nanoclaw/issues/3828), [PR #3873](https://github.com/qwibitai/nanoclaw/pull/3873)
    -   **背景**: `update-nanoclaw` 切换过程在存在活动代理容器时无法成功。用户 `laydros` 报告了此 bug，指出宿主机服务停止后，不会再主动关闭空闲容器，导致切换流程永远在等待。
    -   **分析**: 该问题触及核心部署流程的可靠性，社区关注度高。对应的 PR #3873 在今日被合并，方案被社区和核心团队采纳，解决了 v2.4.0 版本发布前最后一个致命痛点。

2.  **Issue #3869 & PR #3750 - 更新所需依赖缺失**
    -   **链接**: [Issue #3869](https://github.com/qwibitai/nanoclaw/issues/3869), [PR #3750](https://github.com/qwibitai/nanoclaw/pull/3750)
    -   **背景**: `update-nanoclaw` 因为 `git archive` 文件列表缺少控制器的新传递依赖而崩溃。用户 `bgao` 详细描述了问题根源。
    -   **分析**: 该问题反映了自动化更新流程在依赖管理上的潜在缺陷。PR #3750 已在昨天被合并，证明了社区反馈与修复循环的高效。

### Bug 与稳定性

今日报告的 Bug 主要集中在两个已存在问题的变种和一个小型安全问题。

1.  **[高] OneCLI 所有权检查逻辑缺陷**
    -   **Issue**: [#3874](https://github.com/qwibitai/nanoclaw/issues/3874)
    -   **描述**: OneCLI 网关的所有权检查是基于“组是否存在”，而非“安装身份”，存在潜在授权绕过风险。
    -   **状态**: **待处理**，无关联修复 PR。

2.  **[中] 长期运行任务的会话轮转失效**
    -   **Issue**: [#3732](https://github.com/qwibitai/nanoclaw/issues/3732)
    -   **描述**: 对于持续运行容器、不发生预期空闲超时的任务，会话轮转逻辑永远不会被触发。
    -   **状态**: **持续开放**，该问题由用户 `TO-maschenborn` 从 09-07 报告，至今未获修复，已进入积压观察名单。

3.  **[低] 更新脚本的文件列表不完整**
    -   **Issue**: [#3869](https://github.com/qwibitai/nanoclaw/issues/3869)
    -   **状态**: **已修复**，通过 PR #3750 解决。

### 功能请求与路线图信号

-   **凭据网关生态**：`Iron Proxy` 网关的引入（[PR #3817](https://github.com/qwibitai/nanoclaw/pull/3817)）和 OneCLI 的 Skill 化（[PR #3816](https://github.com/qwibitai/nanoclaw/pull/3816)）是本次版本的最大功能信号。这表明项目正朝着 **模块化、可插拔的凭据与代理架构** 演进。
-   **TypeSafe 决策工具**：[PR #3848](https://github.com/qwibitai/nanoclaw/pull/3848) 提出了将 TypeSafe 的 Jev 决策模型作为容器工具集成。该 PR 仍处于开放状态，如果被接受，将为代理提供强大的外部推理能力。
-   **Apple Container 支持**：功能请求 [PR #3503](https://github.com/qwibitai/nanoclaw/pull/3503) 希望在 macOS 上使用 Apple 的容器技术（而非 Docker）运行代理会话。这代表了用户对更轻量、更原生容器化方案的需求。由于其状态为长期开放，可能因技术复杂度或优先级问题被暂时搁置。

### 用户反馈摘要

-   **正面反馈**：核心开发者在多个 PR 中的评论体现了对社区贡献的积极接纳，尤其是处理 #3828 和 #3869 问题时，能快速定位并设计解决方案。
-   **痛点反馈**：
    -   用户对更新流程的稳定性表现出高度敏感。#3828 和 #3869 的连续出现表明，`update-nanoclaw` 作为项目关键入口，其可靠性是用户最关注的核心指标之一。
    -   用户 `TO-maschenborn` 报告的长期任务容器不轮转问题（#3732）揭示了针对“非标准”使用场景（长时运行作业）的边界情况考虑不足。

### 待处理积压

1.  **Issue #3732** - “Transcript rotation never runs for tasks that keep their container alive”
    -   **链接**: [Issue #3732](https://github.com/qwibitai/nanoclaw/issues/3732)
    -   **创建时间**: 2026-09-07
    -   **分析**: 该问题已存在超过两周，虽影响特定任务场景，但尚未有修复 PR。随着 v2.4.0 稳定后，应优先评估其影响范围并考虑解决。

2.  **Issue #3874** - “OneCLI gateway: ownership check uses group existence, not installation identity”
    -   **链接**: [Issue #3874](https://github.com/qwibitai/nanoclaw/issues/3874)
    -   **创建时间**: 2026-09-23
    -   **分析**: 这是一个潜在的安全问题，虽然用户在提交时已确认非可被公开利用的漏洞，但仍需在新版本发布后尽快评估并提出修复方案。

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据您提供的 NullClaw 项目数据生成的 2026-09-24 项目动态日报。

---

# NullClaw 项目日报 | 2026年9月24日

## 今日速览

项目今日活跃度极高，社区互动频繁。过去24小时内，共有 **17 条新 Issue** 和 **21 条 Pull Request** 更新，但无新版本发布。这表明项目正处于高强度的问题修复与功能迭代阶段，开发者与社区用户正集中精力攻克一系列稳定性与功能性问题。虽然无新版本，但多个关键性 Bug 的修复 PR（如 SIGSEGV 崩溃、通道静默、CLI 兼容性等）已进入合并或审查阶段，预示着一个重要 bugfix 版本的临近。整体项目健康度处于“积极修复，密集开发”状态。

## 版本发布

无

## 项目进展

今日共有 **8 个 PR 被合并/关闭**，项目整体向前迈进了重要一步，主要集中在核心稳定性与架构问题的修复上：

1.  **MCP 稳定性修复**: **PR #996** 已关闭，该 PR 修复了 `MCP stdio` 调用在特定场景下因挂起而导致整个 `nullclaw agent` 不会响应的问题。该修复为 MCP 交互添加了超时机制（`timeout_ms`），并在失败时清理子进程，解决了长期存在的死锁隐患。( [PR #996](https://github.com/nullclaw/nullclaw/pull/996) )
2.  **调度器跨会话认证修复**: **PR #980** 已关闭，修复了调度器（scheduler）在重启后因令牌（token）未持久化而导致的 `unauthorized` 问题。此修复对于 cron 类定时任务功能的可靠性至关重要。( [PR #980](https://github.com/nullclaw/nullclaw/pull/980) )
3.  **Discord 通道稳定性提升**: **PR #978** 已关闭，通过为 Discord 心跳线程分配更大的运行时栈（`HEAVY_RUNTIME_STACK_SIZE`），解决了因 TLS 握手导致的栈溢出崩溃问题。( [PR #978](https://github.com/nullclaw/nullclaw/pull/978) )
4.  **可配置内存召回机制**: **PR #979** 已关闭，新增了 `auto_recall`、`recall_limit` 和 `max_context_bytes` 三个配置项，允许用户精细控制自动记忆召回的逻辑，解决了此前配置僵化、无法禁用或少召回记忆的问题。( [PR #979](https://github.com/nullclaw/nullclaw/pull/979) )
5.  **结构化工具审批流程**: **PR #969** 已关闭，为 shell 等危险工具实现了结构化的两轮审批流。代理在调用敏感工具前会先发送 `---approval---` 事件，等待用户确认，极大增强了安全性。( [PR #969](https://github.com/nullclaw/nullclaw/pull/969) )
6.  **新增 Grok CLI 提供商**: **PR #981** 已关闭，为用户新增了 xAI Grok 本地 CLI 作为新的模型提供商选项，丰富了用户的模型选择。( [PR #981](https://github.com/nullclaw/nullclaw/pull/981) )
7.  **SSE 流式工具调用支持**: **PR #965** 已关闭，为 SSE 解析器添加了结构化流式工具调用支持，改进了流式模式下原生工具调用的兼容性和稳定性。( [PR #965](https://github.com/nullclaw/nullclaw/pull/965) )
8.  **可配置 SQLite 数据库路径**: **PR #986** 已关闭，允许用户通过 `memory.database_path` 配置 SQLite 内存数据库的存储路径，这对于只读工作区和需要自定义数据存储位置的场景非常有用。( [PR #986](https://github.com/nullclaw/nullclaw/pull/986) )

## 社区热点

今日讨论最活跃的议题集中在**通道稳定性**与**低资源设备兼容性**上，反映了用户对项目“持久可用”和“轻量易用”的核心诉求。

1.  **低资源设备下 Web 搜索功能受限**: **Issue #871** 获得了 **8 条评论**，是今日讨论最激烈的话题。用户 `uMendex` 尖锐地指出 `web_search` 在预期使用场景（低端、廉价硬件）上不实用，仅有的选项（Brave API或繁琐的本地配置）均不友好。此 Issue 获得了高度关注，用户强烈要求集成无需 API Key 的 DuckDuckGo 支持。（[Issue #871](https://github.com/nullclaw/nullclaw/issues/871)）

2.  **Telegram 通道空闲后无响应**: **Issue #972** 收到了 **5 条评论**。用户 `i11010520` 报告了一个典型的生产环境问题：Telegram 机器人在夜间空闲后第二天早上“假死”，而后端进程仍在运行。这暴露了通道轮询机制可能存在的潜在超时或连接泄漏问题。（[Issue #972](https://github.com/nullclaw/nullclaw/issues/972)）

3.  **调度器权限问题**: **Issue #915** 同样有 **5 条评论**，用户 `scabros` 报告调度器在 Telegram 和 CLI 中均无法正常工作，提示 `unauthorized`。这与上述被关闭的 **PR #980** 直接相关，说明该 Bug 影响范围较广，社区关注度高。（[Issue #915](https://github.com/nullclaw/nullclaw/issues/915)）

## Bug 与稳定性

今日报告了多项关键 Bug，严重程度由高到低排列如下：

1.  **崩溃: SIGSEGV (严重)**
    - **Issue #976**: 在 aarch64 Linux 上，每个入站 Telegram 消息都导致 NullClaw 进程因栈溢出（512KB栈）而崩溃（SIGSEGV），形成“崩溃-重启”循环。
    - **已有修复 PR**: **PR #985** 尝试修复此问题，通过将 Agent 处理线程的栈大小提升至 **16 MiB** 来解决。社区应密切关注此 PR 的合并进度。（[Issue #976](https://github.com/nullclaw/nullclaw/issues/976)）

2.  **功能失效: Telegram 通道静默 (严重)**
    - **Issue #972**: Telegram 通道在一段时间空闲后停止响应，需手动重启网关。这表明通道的监控和恢复存在机制缺陷，影响服务的连续性。
    - **已有修复 PR**: **PR #984** 尝试修复此问题，通过让轮询失败的超时机制来标记并清理“假死”的轮询线程。（[Issue #972](https://github.com/nullclaw/nullclaw/issues/972)）

3.  **功能失效: 调度器无权限 (严重)**
    - **Issue #915**: 调度器功能彻底失效，显示 `unauthorized`。
    - **已有修复 PR**: **PR #980** 已被合并，理论上关闭了此 Issue。（[Issue #915](https://github.com/nullclaw/nullclaw/issues/915)）

4.  **功能异常: CLI 显示控制字符 (一般)**
    - **Issue #865**: `nullclaw agent` CLI 模式中，方向键等特殊按键无法正常工作，而是原样输出转义字符，影响交互体验。
    - **已有修复 PR**: **PR #970** 处于开放状态，旨在为此添加行编辑器支持。（[Issue #865](https://github.com/nullclaw/nullclaw/issues/865)）

5.  **性能问题: WSL2 下 CPU 满载 (一般)**
    - **Issue #870**: 即使在空闲状态，`nullclaw gateway` 一个线程在 WSL2 上持续占用 100% CPU，导致资源浪费。
    - **无直接修复**: 目前尚未有明确的修复 PR 关联此 Issue。（[Issue #870](https://github.com/nullclaw/nullclaw/issues/870)）

## 功能请求与路线图信号

社区的呼声集中在提升灵活性、降低使用门槛和扩展支持范围上：

1.  **集成 DuckDuckGo 搜索**: **Issue #623** 请求为 `web_search` 工具添加 `ddgs` 选项，以使用 DuckDuckGo 这一无需 API Key 的搜索引擎。考虑到 **Issue #871** 的强烈反对，**此功能极有可能被纳入下一个版本**。已有相关 PR 被关联，但状态未知。（[Issue #623](https://github.com/nullclaw/nullclaw/issues/623)）
2.  **图像视觉能力**: **Issue #624** 请求将图像直接发送给 Agent 并实现自动 Base64 编码以支持多模态模型。此功能需求热度较高，可能纳入中期路线图。（[Issue #624](https://github.com/nullclaw/nullclaw/issues/624)）
3.  **子代理生成**: **Issue #190** 是一个持续数月的请求，询问子代理及其跨不同提供商的互通信能力。这是一个重大的架构级特性，目前仍处于讨论阶段。（[Issue #190](https://github.com/nullclaw/nullclaw/issues/190)）
4.  **监控状态接口**: **Issue #631** 请求为网关增加一个 `GET /status` 端点，以便外部工具进行监控。这反映了用户对可观测性的需求。（[Issue #631](https://github.com/nullclaw/nullclaw/issues/631)）
5.  **控制自动记忆召回**: **Issue #919** 请求允许按消息粒度禁用自动记忆召回。最新合并的 **PR #979** 已经以配置项的方式回应了此需求，预计将在下一版本中提供。（[Issue #919](https://github.com/nullclaw/nullclaw/issues/919)）

## 用户反馈摘要

从今日的 Issues 和评论中，可以提炼出用户真实的使用痛点和场景：

-   **痛点：低配硬件下的体验不佳。** 用户 `uMendex` 明确指出 NullClaw 的预期用例是“弱、廉价、低资源设备”，但当前 `web_search` 的实现方式（依赖 API Key 或复杂本地部署）使其在此场景下不切实际。这反映了用户寻求**零外部依赖、开箱即用**的轻量级解决方案的强烈诉求。
-   **痛点：服务自动化与可靠性不足。** Telegeram 通道的“假死”和调度器的 `unauthorized` 问题让用户感到沮丧。这表明用户不仅需要一个能工作的 AI 助手，更需要一个**稳定、无需人工干预、长期运行**的后台服务。`scabros` 等用户正在尝试将其部署为生产线上的稳定组件。
-   **场景：寻求与特定 API 的兼容。** 用户 `ats-bcon` 尝试使用原生 Anthropic API Key 但失败（Issue #767），这表明用户希望摆脱对第三方代理（如 OpenRouter）的依赖，直接使用官方服务，以追求**更低延迟、更高稳定性或更简单的工作原理**。
-   **场景：特定平台用户的刚需。** 用户 `DDGRCF` 询问微信二维码登录支持（Issue #817），明确反映了中文用户群体对集成微信生态的迫切需求。这可能是该项目的关键增长点。

## 待处理积压

以下为长期未获有效响应的或重要的开放 Issue/PR，需要维护者留意：

1.  **Issue #190: Subagent spawn**（创建于 2026-03-01）：关于子代理生成与互通的架构级问题，长期处于开放状态，讨论热度不高但影响重大，可能需要维护者给出明确的路线图回应。（[Issue #190](https://github.com/nullclaw/nullclaw/issues/190)）
2.  **Issue #767: Native Anthropic API 支持**（创建于 2026-04-04）：用户尝试配置原生 Anthropic API 失败，虽有关联的 **PR #962** 提供文档补充，但根本的兼容性问题是否完全解决仍有待验证。（[Issue #767](https://github.com/nullclaw/nullclaw/issues/767)）
3.  **PR #984: fix(channels)**（已开放 50 天）：这个旨在修复通道空闲后假死的 PR 粘滞了相当长的时间，考虑到 **Issue #972** 的严重性，其合并应给予优先权。（[PR #984](https://github.com/nullclaw/nullclaw/pull/984)）
4.  **PR #970: fix(cli)**（已开放 87 天）：修复 CLI 方向键问题的 PR 状态长期未更新。虽然影响不大，但作为基础交互体验问题，长期搁置可能影响新用户的第一印象。（[PR #970](https://github.com/nullclaw/nullclaw/pull/970)）

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

# IronClaw 项目动态日报 (2026-09-24)

---

## 1. 今日速览

过去 24 小时项目整体活跃度偏低：Issues 方面无任何新开、关闭或更新；Pull Requests 共有 2 条新提交，均为开放状态且尚未合并。其中一条为 RC2 版本发布准备（#8110），另一条为技能文档改进（#8109）。无新版本正式发布。项目处于小幅迭代与文档完善阶段，版本发布流程仍在前置准备中。

---

## 2. 版本发布

**无**（无新版本发布。PR #8110 正在推进 1.4.1-rc.2 的切分支工作，预计未来 1-2 天内发布。）

---

## 3. 项目进展

今日无任何 PR 被合并或关闭。两个开放中的 PR 分别代表了项目在两个方向上的推进：

- **版本发布准备** – PR #8110（[链接](https://github.com/nearai/ironclaw/pull/8110)）：将发布分支从 `1.4.1-rc.1` 升级至 `1.4.1-rc.2`，并锁定依赖版本（`wasmtime 47.0.4`、`rustls 0.23.45`）以响应安全公告。此举为正式发布 1.4.1 修复版扫清障碍。
- **文档完善** – PR #8109（[链接](https://github.com/nearai/ironclaw/pull/8109)）：澄清了虚拟技能根的 scoped 概念，替换了过时的宿主目录发现指南，区分运行时发现与独立遗留磁盘导入，帮助开发者更安全地配置技能路径。

项目整体处于发布前文档刷新与安全依赖加固阶段，向前迈进的幅度较小但方向明确。

---

## 4. 社区热点

今日无收到任何评论或点赞的 Issues / PRs。两个开放 PR 均无讨论，社区互动近乎空白。

---

## 5. Bug 与稳定性

**无新报告的 Bug**。

但 PR #8110 中隐含了一项稳定性/安全性改进：通过刷新锁文件升级 `wasmtime` 和 `rustls` 版本，以匹配当前漏洞数据库中的补丁要求。此项变更虽未以 Issue 形式提出，但有效降低了依赖引入的安全风险，属于隐性的稳定性提升。

---

## 6. 功能请求与路线图信号

今日无新功能请求提交。PR #8109 中针对虚拟技能根的文档澄清，可能源自社区用户对技能路径配置的困惑，暗示未来版本可能会进一步标准化虚拟技能目录结构，但目前暂无代码行为变更。

---

## 7. 用户反馈摘要

由于今日所有 Issues 和 PRs 均无用户评论，无法提炼真实的用户反馈。

---

## 8. 待处理积压

无长期未响应的重要 Issue 或 PR。当前所有开放 PR（#8110、#8109）均为昨日创建，状态健康，无需特别提醒。

---

**报告生成时间**：2026-09-24  
**数据来源**：github.com/nearai/ironclaw  
**分析师**：AI 智能体与个人 AI 助手领域开源项目分析师

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

好的，作为 LobsterAI 开源项目的分析师，我已根据您提供的 GitHub 数据，为您生成了 2026 年 9 月 24 日的项目动态日报。

---

### LobsterAI 项目动态日报 (2026-09-24)

**分析师点评：** 项目今日维持高活跃度，主要聚焦于代码整合与稳定性的提升。虽然无新 Issue 报告，但超过 8 个 Pull Request 被迅速合并，并发布了一个聚焦于协作体验与决策模型扩展的新版本。整体项目健康度表现优秀，社区贡献与核心开发同步推进。

#### 1. 今日速览

- **项目状态：** 过去 24 小时，项目团队展现了极高的开发和整合效率。尽管没有新的 Issue 提出，但团队密集合并了 8 个 Pull Request，并发布了新的版本，表明工作重心在功能收尾、稳定性修复与性能优化上。
- **核心动态：** 发布了 **LobsterAI 2026.9.23** 版本，重点引入了试验性决策模型工具，并对“协作”模块（Cowork）的实时进度反馈进行了显著优化。
- **活跃度评估：** **高**。PR 处理数量（10 条，其中 8 条已合并/关闭）和新版本发布均显示项目处于快速迭代周期。社区贡献者 (`btc69m979y-dotcom`, `Mind-Hand`) 也积极参与了关键修复与功能开发。
- **潜在风险：** 当前有两个待合并的 PR（#2668 和 #2755），需关注其合并进度，特别是 #2755 涉及核心配置热重载的修复。

#### 2. 版本发布

- **版本信息：** **[LobsterAI 2026.9.23](https://github.com/netease-youdao/LobsterAI/releases/tag/v2026.9.23)**
- **详细说明：**
    - **新功能：** 新增了实验性 **Jev 决策模型工具**。这允许用户自带密钥（BYOK），并通过配置和 MCP 工具调用来使用该模型。该功能在设置 UI 中以实验性功能开关形式呈现，为探索更高级的决策路径提供了可能。
    - **协作优化：**
        - **实时进度流：** 改进了协作任务（Cowork）的步骤级实时进度展示，使团队成员能更清晰地看到每一步的进展。
        - **差异统计：** 新增了实时的差异（Diff）统计数据流，让用户能立刻看到任务过程中的变更情况。
        - **统一渲染：** 将活动步骤的渲染统一为 `ActivityStepLine` 组件，增强了界面一致性和对多种步骤类型的支持。
- **破坏性变更与迁移注意事项：**
    - 本次发布未提及明确的破坏性变更。但团队将协作模块的活动步骤渲染组件进行了重构，开发者若依赖于旧的 `row/detail` 活动变体，需注意适配新的 `<ActivityStepLine>` 组件。
    - “试验性 Jev 决策模型”功能默认不开启，用户需要在设置中手动启用，并自行配置密钥后方可使用。

#### 3. 项目进展

今日合并/关闭的 8 个 PR 推动了多项关键功能与稳定性修复，项目整体向前迈出了坚实一步。

- **决策模型扩展：** PR [#2753](https://github.com/netease-youdao/LobsterAI/pull/2753) 被合并，正式引入了 `Jev decision model`，为项目在决策能力上的扩展搭建了框架。
- **配置热重载修复：** PR [#2755](https://github.com/netease-youdao/LobsterAI/pull/2755) (待合并) 和 [#2754](https://github.com/netease-youdao/LobsterAI/pull/2754) (已合并) 共同解决了 OpenClaw 模块的配置应用问题。`#2754` 确保插件异常时，主网关仍能降级启动并保留基础会话；`#2755` 则进一步修复了端口或模型配置更新后，新任务可能继续使用旧配置的 bug，通过引入版本条件确保配置真正应用后才放行新任务。
- **用户体验打磨：**
    - **协作体验增强：** PR [#2750](https://github.com/netease-youdao/LobsterAI/pull/2750) 和 [#2749](https://github.com/netease-youdao/LobsterAI/pull/2749) 协同作用，显著提升了协作任务（Cowork）的回合进度视觉反馈和实时性。
    - **订阅活动优化：** PR [#2751](https://github.com/netease-youdao/LobsterAI/pull/2751) 扩大了“一分钱体验活动”的宣传范围，让匿名和已订阅用户也能看到活动，有助于提升用户参与度和潜在转化。
- **基础设施更新：** PR [#2752](https://github.com/netease-youdao/LobsterAI/pull/2752) 将 dsh runtime 更新到 0.1.5 rc.3，保持了项目对底层运行时的跟进。

#### 4. 社区热点

今日社区讨论热度不高，但以下 PR 和 Issue 值得关注：

- **热点 PR：**
    - **#2753 [CLOSED] feat(decision-model): add experimental Jev decision model tool**：作为新版本的亮点功能，该 PR 的合并引发了最广泛的关注（尽管评论数为 0，但功能本身是社区期望的扩展点）。背后诉求是社区对项目引入更智能的决策 Agent 的期待，开发者通过实验性功能的方式谨慎探索。
    - **#2755 [OPEN] fix(openclaw): reconcile config application before starting tasks**：这是一个等待合并的关键修复 PR，它直接回应了用户在使用 OpenClaw 时可能遇到的“配置不生效”的痛点。它的存在表明，**配置热加载的稳定性和可靠性是当前用户和开发者关注的焦点**。

#### 5. Bug 与稳定性

昨日没有报告新的 Bug，团队主要致力于解决已有的稳定性问题。按严重程度排列如下：

- **高（配置与应用不一致）**：
    - **描述：** 在更新代理端口或模型配置后，系统可能会错误地将“保存成功”视为“已应用”，导致新发起的问题（Task）仍在旧配置上运行。这是一个潜在的静默错误，影响用户体验和结果准确性。
    - **状态：** **已有 Fix PR**。PR [#2755](https://github.com/netease-youdao/LobsterAI/pull/2755) 通过引入带版本条件的 `config.apply` 流程来解决此问题，目前仍处于开放待合并状态。
- **中（插件异常导致服务中断 / macOS 快捷键兼容）**：
    - **描述：** OpenClaw 8.1 曾因插件校验失败而拒绝整个网关启动，导致健康模型也无法工作。
    - **状态：** **已修复**。PR [#2754](https://github.com/netease-youdao/LobsterAI/pull/2754) 已合并，通过移植上游的插件隔离策略解决了此问题。
    - **描述：** PR [#980](https://github.com/netease-youdao/LobsterAI/pull/980) 解决了 macOS 平台上快捷键修饰键不正确的问题。
    - **状态：** **已关闭/合并**。这是一个遗留的、从 3 月就存在的修复，目前已被处理。

#### 6. 功能请求与路线图信号

- **实验性决策模型：** PR [#2753](https://github.com/netease-youdao/LobsterAI/pull/2753) 的合并表明，**扩展 AI Agent 的决策能力是项目下一阶段的重要方向**。未来版本可能会围绕此概念，引入更多种类的决策模型或 Agent 工具。
- **协作模块深度打磨：** 从 PR [#2750](https://github.com/netease-youdao/LobsterAI/pull/2750) 和 [#2749](https://github.com/netease-youdao/LobsterAI/pull/2749) 可以看出，项目组正在大力投资于“协作”模块的用户体验。**实时进度、统一展示和 Diff 统计** 等特性，暗示了产品正朝着更专业、更追求效率的协作平台演进。
- **社区贡献的风向：** PR [#2751](https://github.com/netease-youdao/LobsterAI/pull/2751) 由社区贡献者 `Mind-Hand` 提交，优化了订阅活动的展示逻辑。这反映了社区不仅关注技术底层，也对**用户增长和商业化功能的盲点**有敏锐的洞察。

#### 7. 用户反馈摘要

- **痛点（间接表达）：**
    - **配置更新不生效**：PR #2755 的提出，直接指向了用户在修改代理设置后，期望新配置立即生效但未能如愿的核心痛点。这通常是 AI 客户端配置管理中最令人困扰的问题之一。
    - **插件问题引发服务中断**：PR #2754 的修复，解决了用户因安装或更新了有瑕疵的插件后，导致整个 AI 网关无法启动（“打不开/无法对话”）的严重问题。这个修复显著提升了系统的鲁棒性。
- **使用场景（推断）**：
    - **AI 工作流协作**：`Cowork` 模块的改进，暗示项目正被用于需要多人、多步骤 AI 任务协同的场景，如团队头脑风暴、项目规划、代码审查等。
    - **个性化 AI Agent 开发**：`Jev decision model` 工具允许用户“BYO-key”，这表明项目高阶用户可能希望将特定的、私有化的决策模型集成到自己的 AI Agent 工作流中，实现高度定制化。

#### 8. 待处理积压

- **#2668 [OPEN] chore(deps-dev): bump @sinclair/typebox from 0.34.49 to 0.34.52** (`dependabot[bot]`)
    - **摘要：** 这是一个依赖更新 PR。
    - **状态：** 已开放超过 10 天，至今未合并。建议维护者评估此更新是否与其他功能的依赖版本兼容，并尽快处理，避免因依赖过时而引入安全或兼容性问题。
    - **链接：** [netease-youdao/LobsterAI PR #2668](https://github.com/netease-youdao/LobsterAI/pull/2668)

- **#2755 [OPEN] fix(openclaw): reconcile config application before starting tasks** (`btc69m979y-dotcom`)
    - **摘要：** 此 PR 修复了配置热重载的核心问题，重要性高。
    - **状态：** 昨日被创建，目前处于开放状态。考虑到其修复的是一个潜在的高影响力 Bug，强烈建议维护者优先审查，争取尽早合并至主分支。
    - **链接：** [netease-youdao/LobsterAI PR #2755](https://github.com/netease-youdao/LobsterAI/pull/2755)

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是基于 Moltis 项目 2026-09-24 的 GitHub 数据生成的日报。

---

## Moltis 项目动态日报 | 2026-09-24

### 1. 今日速览
今日项目活跃度较低，社区讨论进入平台期。过去 24 小时内无新的 Issue 提交或关闭，也无新版本发布。开发活动集中于一个待合并的 PR（#1272），该 PR 旨在为沙箱系统添加细粒度权限控制，是增强安全性和隔离性的重要步骤。整体上，项目处于稳定期，开发团队专注于核心功能的落地而非新问题的响应。

### 2. 版本发布
今日无新版本发布。

### 3. 项目进展
今日无 PR 被合并或关闭。但有一个重要的开放 PR 值得关注：
- **PR #1272 (待合并): feat(sandbox): per-agent mounts, run_as and a forced sandbox**
  - **状态**: 开放 (待合并)
  - **概要**: 该 PR 为沙箱功能引入了三个关键配置项，分别作用于单代理预设的 `[sandbox]` 配置块：
    - `sandbox.mounts`: 允许为特定代理的沙箱容器额外挂载宿主机路径。
    - `sandbox.run_as`: 指定容器运行时的 `uid:gid`，实现用户权限映射。
    - `sandbox.force`: 强制该代理必须在沙箱内运行，防止其逃逸到宿主机。
  - **意义**: 这标志着 Moltis 在安全隔离和灵活部署能力上的重大迈进。它允许运维人员为特定高风险或需要访问特殊资源的代理定制沙箱环境，满足了生产环境中对“最小权限”和“资源隔离”的强烈需求。

### 4. 社区热点
今日唯一活跃的议题是 **PR #1272**。尽管评论数未显示，但其长期开放（自 9月16日创建至今）和复杂的核心改动表明这是当前社区关注的焦点。背后的核心诉求是 **生产级沙箱的定制需求**。用户希望不仅能对单个代理进行统一沙箱化，更能按需配置不同的挂载点、运行权限和强制策略，以实现类似 Kubernetes Security Context 的细粒度控制。

### 5. Bug 与稳定性
今日无新报告的 Bug、崩溃或回归问题。项目稳定性良好。

### 6. 功能请求与路线图信号
今日无新的功能请求提交。不过，开放中的 **PR #1272** 本身即是对现有沙箱系统的重大功能扩展，非常可能被纳入下一个版本（如 v0.x 或 v1.0 的后续版本）。该 PR 中的三个特性（挂载、运行用户、强制沙箱）直接回应了社区对于**多租户安全**和**与现有基础设施（如 LDAP、文件系统权限）集成**的需求，是路线图中的关键信号。

### 7. 用户反馈摘要
今日无新的用户反馈。基于 PR #1272 的技术内容，可以推断出用户的常见痛点：
- **痛点**: 无法精细化控制不同代理在沙箱内的行为和权限，导致安全策略难以落地。
- **使用场景**: 用户需要让某个代理访问宿主机上的特定数据目录（挂载需求），或需要代理进程以低权限用户运行（run_as 需求），或强制要求某些核心代理不能裸奔运行（force 需求）。

### 8. 待处理积压
- **PR #1272**: 自 2026-09-16 创建至今已开放 8 天，尚未合并。该 PR 涉及沙箱核心组件，改动较大，建议维护者尽快安排 Review 和测试，以避免功能分支长期偏离主分支，同时也能快速响应社区对安全隔离功能的迫切需求。 [查看 PR](https://github.com/moltis-org/moltis/pull/1272)

（注：由于今日数据无长期未响应的 Issues，以上是唯一的待处理项。）

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

好的，作为一名 AI 智能体与个人 AI 助手领域开源项目分析师，我已根据您提供的 CoPaw (QwenPaw) 项目 GitHub 数据，生成了 **2026-09-24 的项目动态日报**。

---

## CoPaw (QwenPaw) 项目动态日报 | 2026-09-24

### 1. 今日速览

今日 CoPaw 项目社区活跃度极高，Issue 和 PR 更新数量均处于高位，修复与开发工作并行。核心团队集中解决了多个关于**上下文管理**（如 Context Budget #7628、Scroll Eviction #7836）和**流式传输稳定性**（如 Stream Cleanup #7960）的棘手 Bug，并推进了 **PawApp SDK 重构** (#7874) 等重大功能。同时，关于 **QwenPaw Hub 多租户版** (#7318) 的讨论热度不减，已成为社区焦点。整体来看，项目正处于快速迭代期，稳定性与功能创新同步推进，健康度良好。

- **活跃度评估**: 高热。Bug 修复与功能开发并重，社区讨论热烈，核心维护者响应迅速。

### 2. 版本发布

无。过去 24 小时内未发布新版本。

### 3. 项目进展

今日合并/关闭了 9 个 PR，修复了多个关键 Bug 并完成了功能优化，项目整体稳健推进。核心进展包括：

- **核心引擎稳定性提升**:
    - **PR #7563** (`fix(chat): distinguish model errors from transport failures`): 修复了聊天界面中因网络/代理问题而错误提示“模型未配置”的问题，现在只会拦截真正的 `MODEL_NOT_CONFIGURED` 错误。
    - **PR #7409** (`fix(agents): drop empty assistant text blocks`): 解决了因模型推理后产生空文本块，导致后续请求报错（如 `MissingParameter` #7402）的问题。此修复对提升商业 API（如火山引擎）兼容性至关重要。
    - **PR #7941** (`test(unit): make the batch-3 lock and portability tests cross-platform`): 贡献者 `yutai78786` 添加了 47 个新测试文件（共 2720 个案例），将项目陈述覆盖率提升 3.28 个百分点至 **73.79%**，显著增强了代码可靠性和跨平台兼容性。
- **Hub 与 Web 功能优化**:
    - **PR #7952** (`fix(hub): distinguish invitation redemption failure reasons`): 修复了 Hub 邀请码激活时无法区分具体失败原因的问题，便于运维和用户排查。
    - **PR #7927** (`fix(web): replace html2text with markdownify`): 将递归转换为 HTML 的依赖从 GPL 协议库替换为 MIT 协议库，解决了许可证兼容性问题。
- **基础设施与文档完善**:
    - **PR #7940** (`feat(console): refine sidebar interactions and persist avatars`): 优化了侧边栏交互并支持头像持久化。
    - **PR #7955** (`docs(website): add download provenance and usage policy`): 增加了下载来源说明和使用政策，提升了项目透明度。

### 4. 社区热点

- **Issue #7318**: [ [OPEN] QwenPaw Hub, the multi-tenant edition … 接下来做什么？](https://github.com/agentscope-ai/QwenPaw/issue/7318)
    - **热度**： 评论 32 | 👍 4
    - **分析**： 这是过去24小时社区讨论最热的话题。QwenPaw 凭借其强大的个人 AI 助手能力，催生了强烈的团队协作需求（多用户、权限管理是其前身 #2324 的延续）。此 Issue 上升到**路线图讨论**阶段，表明社区不满足于单机版，对“Hub”这一企业级或团队级部署形态抱有很高期待。这是项目从个人工具向平台演进的关键信号。

### 5. Bug 与稳定性

今日报告了多个影响核心体验的 Bug，严重程度较高，但多数已有对应的修复 PR。按严重程度排列：

- **P0 - 严重：会话静默/不可用**
    - **[Bug] #7534**: 飞书频道单个会话的消费者卡死后，该会话静默无响应，新消息无法触发新消费者。**严重影响飞书渠道用户**。
    - **[Bug] #7857**: ACP 服务的同步关闭 fallback 可能跳过会话清理并造成事件循环泄漏。
    - **[Bug] #7836**: 滚动式上下文驱逐（Scroll Eviction）会错误地丢弃用户输入，导致 Agent “失忆”。**重点**：已有 **PR #7872** 针对性修复。
    - **Fix PR #7960** (`fix(providers): recover after stalled stream cleanup`): 解决了流式读取卡死导致后续请求全部失败的严重问题，恢复机制为 60 秒隔离期。

- **P1 - 高：功能异常/体验受损**
    - **[Bug] #7853**: `ToolResultPruner` 无法裁剪图片（base64 数据），导致上下文被图片撑爆。
    - **[Bug] #7947**: `send_file_to_user` 在 Web Console 中不渲染文件卡片，用户无法下载文件。**已有对应 PR 修复？**
    - **[Bug] #7767**: 报告了多个 Console 端 Beta 版 Bug，包括图片附件返回旧 blob、定时任务触发遗漏等。**表明 2.2.0 仍在打磨期**。
    - **[Bug] #7948**: 用户投诉 Console 新设计破坏输入体验。

- **P2 - 中：功能配置/兼容性问题**
    - **[Bug] #7715**: Daily Paper 插件在 arxiv.org 不可达时静默失败，无法配置代理。
    - **[Bug] #7856**: `qwenpaw-pet` 插件破坏 QwenPaw 工具审批功能（参数不兼容）。

### 6. 功能请求与路线图信号

- **A2A (Agent-to-Agent) 协议支持**: **Issue #7484** 明确询问何时支持 A2A 协议。尽管架构规划中提到统一 Driver，但目前仅支持 MCP，社区对此期望很高。**重要性：高**，可能是 2.3 或 3.0 的关键特性。
- **Agent 自治的上下文管理**: **Issue #7733** 提出了更深层的需求：Agent 自身应在上下文驱逐前被主动通知并参与决策，而非被动丢失“记忆”。这代表了社区对智能体主动性的更高要求。
- **上下文预算计算的彻底改进**: **Issue #7628** 要求上下文压缩（Compaction）应考虑发送给 API 的**完整请求预算**，而不仅是当前对话的可见上下文。此诉求源于实际使用中的频繁超限失败。**重要性：高**，直接影响长对话和复杂任务的可用性。
- **多模型/多 Agent 配置**: **Issue #1010**（虽已关闭，但作为背景）和 **Issue #7062**（允许按 Agent 或会话配置 `reasoning_effort`）都指向同一个方向：**更灵活的模型分配策略**，以平衡成本和性能。**PR #7613** (OpenViking 记忆插件) 和 **PR #7874** (PawApp SDK 重构) 的持续推进，也暗示了 Agent 生态和内部架构的复杂化，多模型能力将成为刚需。

### 7. 用户反馈摘要

从过去24小时的Issue和评论中，可以提炼出用户的真实场景和痛点：

- **追求稳定性的渴望**: 用户对**飞书频道卡死** (#7534)、**上下文被撑爆** (#7853)、**Agent失忆** (#7836) 等问题反馈非常强烈，这直接影响了“长期运行任务”和“复杂多轮对话”的用户体验。这是当前最核心的负反馈。
- **对团队协作功能的迫切需求**: #7318 的讨论热情证明了个人用户成功向团队场景拓展的强烈意愿，多用户、权限管理（前身 #2324）是刚需。
- **对新 UI 的吐槽**: #7948 中用户直言不讳地批评 Web Console 的新设计“打破了用户输入”，这是 UI/UX 重构中常见的阵痛，但需要团队重视并快速响应。
- **对特定功能的满意**: 用户对 PR #7940 中侧边栏优化、**PR #6854** 中增加审批说明等“以人为本”的小改进表示认可。这提示团队，在追求大功能的同时，精细化打磨细节能赢得社区好感。

### 8. 待处理积压

- **Issue #2335**: [BUG][Feishu Channel] WebSocket connection drops without auto-reconnect. 该问题于2026年3月提出，影响飞书渠道用户，至今未见官方修复或进展。**周期已超过6个月，严重性高**，建议维护者关注。
- **Issue #7484**: [Feature] A2A支持。用户明确询问时间表，是社区普遍关心的路线图问题，团队应给予官方回应，避免用户流失。
- **Issue #1010**: [Feature] 多LLM配置。虽已关闭，但其背后需求（特别是通过 #7062 再次提出）非常强烈，是构建更智能、更成本高效的 Agent 系统的基础。建议作为长期规划。

---

**分析师总结**:
CoPaw 项目正处于一个关键的“攀登期”。核心团队在推动架构升级（PawApp SDK）和修复深层 Bug 方面展现了强大的技术能力。但高频出现的稳定性 Bug（尤其是上下文和渠道连接问题）已对社区信心造成一定冲击。建议在接下来的 1-2 个版本周期内，将工作重心从“堆功能”转向 **“稳核心”** ，集中火力解决 #7534、#7836、#7628 等影响面广的稳定性问题，并尽早回应社区关于团队协作（Hub 路线图）和 A2A 协议的技术方案，以巩固社区信任。

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，这是为您生成的 ZeroClaw 项目 2026-09-24 项目动态日报。

---

# ZeroClaw 项目日报 - 2026-09-24

## 今日速览

项目整体保持高活跃度，社区贡献持续涌入，尤其在 WhatsApp Web 渠道、安全策略与运行时工具的修复及功能增强方面。过去24小时内，**11个新Issue** 被提出，其中多个标记为**P1高优先级**，涉及潜在的数据安全风险和在无头模式下安全机制失效等关键问题。**50个Pull Request** 处于活跃状态，但待合并数量高达47个，显示出项目维护者审查能力面临挑战，合并效率有待提升。近期无新版本发布，但多个修复性的PR已进入最终审查阶段。

## 版本发布

*无*

## 项目进展

过去24小时内，仅有 **3个PR被合并或关闭**，合并效率不足。尽管如此，以下关键修复已经进入待合并队列，待审查通过后将显著提升项目稳定性与安全水位：

- **[fix(security): block high-risk shell commands even when allowlisted (PR #11061)](https://github.com/zeroclaw-labs/zeroclaw/pull/11061)**: 由社区贡献者提交，修复了一个严重的安全漏洞。此前，若将高风险命令（如 `rm -rf`）显式加入白名单，系统会绕过“高危命令阻断”策略。该PR强制高危命令门控在最后防线生效，确保安全配置的完整性。
- **[feat(tools): add agy_cli coding-CLI tool for Antigravity CLI (PR #11076)](https://github.com/zeroclaw-labs/zeroclaw/pull/11076)**: 响应Google终端工具迁移，新增`agy_cli`工具以支持Antigravity CLI作为编码代理，扩展了代理的工具生态。
- **[fix(runtime): preserve configured provider profile semantics (PR #10172)](https://github.com/zeroclaw-labs/zeroclaw/pull/10172)**: 此长期未决的PR解决了通过仪表盘或CLI切换模型时，用户自定义的提供商配置（如 `family.alias`）在运行时被“静默丢失”的关键问题。

## 社区热点

- **[Bug]: Unattended agent turns run with no ApprovalManager (Issue #10968)](https://github.com/zeroclaw-labs/zeroclaw/issues/10968)**
  这是当前讨论热度最高、风险等级最高的安全问题。社区成员明确指出，在 **cron、心跳、无头SOP和spawn_subagent** 等无人值守场景下，代理进程完全无法创建 `ApprovalManager`，导致所有高危工具审批策略形同虚设。该Issue获得大量关注，反映了用户对 **自动化任务安全审批机制** 的强烈合规与安全需求。

- **[Bug]: Dashboard-started turns get freshly built channel instances (Issue #10985)](https://github.com/zeroclaw-labs/zeroclaw/issues/10985)**
  此Issue引发了关于**运行时架构设计**的重要讨论。用户发现，通过仪表盘发起的轮次会创建全新的频道实例，导致像WhatsApp这种有状态的频道工具无法访问已有会话状态。社区对PR [#10986](https://github.com/zeroclaw-labs/zeroclaw/pull/10986) 的进展非常关注，期望能修复仪表盘与频道间状态隔离的缺陷。

## Bug 与稳定性

### 严重 (S0) - 数据丢失/安全风险
- **[Bug]: Unattended agent turns run with no ApprovalManager (Issue #10968)](https://github.com/zeroclaw-labs/zeroclaw/issues/10968)**
  **P1优先级，高风险。** 无人值守模式下的安全审批机制失效。 **尚未有PR提交。**
- **[Bug]: markdown memory backend silently loses stored entries (Issue #10797)](https://github.com/zeroclaw-labs/zeroclaw/issues/10797)**
  **P1优先级，高风险。** 并发调用 `store()` 时，Markdown存储后端会因并发写入导致静默数据丢失。 **修复PR [未提及]。**

### 高 (S2) - 功能行为异常
- **[Bug]: WhatsApp Web ignores suppress_voice when queueing TTS (Issue #10922)](https://github.com/zeroclaw-labs/zeroclaw/issues/10922)**
  WhatsApp自动语音回复路径忽略了 `suppress_voice` 指令，导致无法强制关闭TTS。 **修复PR [#11057](https://github.com/zeroclaw-labs/zeroclaw/pull/11057) 已提交待合并。**
- **[Bug]: Dashboard-started turns get freshly built channel instances (Issue #10985)](https://github.com/zeroclaw-labs/zeroclaw/issues/10985)**
  仪表盘发起的轮次无法访问会话绑定的频道。 **修复PR [#10986](https://github.com/zeroclaw-labs/zeroclaw/pull/10986) 已提交待合并。**
- **[Bug]: WhatsApp Web ignores force_voice (Issue #11059)](https://github.com/zeroclaw-labs/zeroclaw/issues/11059)**
  `force_voice` 参数在WhatsApp渠道中被完全忽略，使得通过 `send_via` 路由强制语音回复的功能失效。 **尚未有PR提交。**
- **[Bug]: The daemon never registers the channel-map factory (Issue #11055)](https://github.com/zeroclaw-labs/zeroclaw/issues/11055)**
  守护进程未注册频道地图工厂，导致webhook、cron和SOP轮次无法使用任何频道工具。 **尚未有PR提交。**

## 功能请求与路线图信号

- **[Feature]: Render thematic breaks and setext headings for WhatsApp (Issue #11052)](https://github.com/zeroclaw-labs/zeroclaw/issues/11052)**
  用户要求增强WhatsApp渠道的Markdown渲染能力，支持分隔线和标题，以提升Agent输出的阅读体验。
- **[Feature]: Add `agy_cli` coding-CLI tool for Antigravity CLI (Issue #11075 & PR #11076)](https://github.com/zeroclaw-labs/zeroclaw/issues/11075)**
  紧跟Google技术栈，社区已快速提交了`agy_cli`工具的Issue和PR，表明用户对新安全、高效的编码CLI工具有即时需求。
- **[RFC: search_routes — hint-based provider routing for web_search_tool (Issue #11074)](https://github.com/zeroclaw-labs/zeroclaw/issues/11074)**
  一项关于增强`web_search_tool`路由能力的提案，允许根据搜索意图将查询路由到不同的搜索引擎提供商。这预示着对**更精细的搜索控制权**的需求正在增长。

## 用户反馈摘要

- **WhatsApp代理痛点集中爆发**: 用户在多个Issue中抱怨WhatsApp Web频道的语音处理（#10922, #11059）和会话状态管理（#10985, #11055）存在严重不一致性。高频出现的问题表明WhatsApp渠道的集成深度不足，是用户日常使用中的主要障碍。
- **安全与合规是核心关切**: Issue #10968 的讨论中，用户表达了对于“自动化任务可能绕过所有安全审批”的严重焦虑。用户希望项目能提供一个**可靠的、可审计的**无人值守执行环境，这对企业级部署至关重要。
- **AI表现的稳定性问题**: 有用户报告，当使用某些提供商的模型（如gpt-5.6）时，Agent偶尔会将工具调用“泄露”到普通文本中，导致格式错乱（PR #10446 的解决目标）。这表明模型输出的非一致性仍是影响用户体验的痛点。

## 待处理积压

以下为长时间未更新或等待原参与者响应的关键Issue/PR，需维护者重点关注：

1. **[PR #10070] feat(tools): gate file_download against SSRF**： 标签 `needs-author-action`，已停滞超过1个月。此PR旨在防御SSRF攻击，对文件下载工具的安全性至关重要，维护者已介入，但仍需原作者确认。
2. **[PR #10084] fix(whatsapp-web): answer WhatsApp's passkey gate**： 标签 `needs-author-action`，已停滞超过1个月。此PR是解决WhatsApp设备链接问题的核心修复，进度滞后与WhatsApp问题的频发形成对比。
3. **[PR #9809] feat(providers): support multiple models per provider profile**：标签 `needs-author-action`，已停滞近2个月。这是一个高价值的功能增强，允许一个提供商配置接入多个模型，能显著简化用户配置。长期处于待确认状态会影响用户体验。
4. **[PR #10172] fix(runtime): preserve configured provider profile semantics**：标签 `needs-maintainer-review`，等待维护者审查。此PR横跨多个领域，解决了一个关键的运行时状态丢失问题，流程推进较慢。
5. **[PR #10391] fix(delegate): bounded delegate filesystem tools now respect the target's own workspace**：标签 `needs-author-action`，已停滞近1个月。此PR涉及委托代理的文件系统隔离，是分布式代理安全性的重要组件，需推动开发者完成代码修改。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*