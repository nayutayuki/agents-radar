# OpenClaw 生态日报 2026-09-22

> Issues: 500 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-09-22 01:08 UTC

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

# OpenClaw 项目动态日报 – 2026-09-22

## 1. 今日速览

过去24小时内，项目保持了极高的社区活跃度：**500条 Issue 更新**（其中新开/活跃 451 条、关闭 49 条）、**500条 PR 更新**（待合并 309 条、已合并/关闭 191 条），并发布了 **1 个 LTS 版本**。**P0/P1 级别 Bug 持续集中**在 Gateway 内存泄漏、SQLite WAL 无限增长、多 Agent 会话消息丢失等核心稳定性领域，社区讨论热烈，多项修复 PR 已进入审查阶段。总体来看，项目处于 **高频迭代与稳定性攻坚并重** 的状态，社区协作强度高。

## 2. 版本发布

### 🔖 v2026.7.35 — gateway-only extended-stable (LTS)

- **发布时间**：2026-09-22  
- **发布链接**：[openclaw/openclaw Releases · v2026.7.35](https://github.com/openclaw/openclaw/releases/tag/v2026.7.35)  
- **内容概要**：该版本基于 2026 年 7 月底的快照，额外包含关键安全更新、可靠性/性能修复以及新型号支持。官方说明明确标注为 **gateway-only extended-stable**（当前 LTS 等效版本），建议对稳定性要求高的生产环境部署此版本。  
- **注意事项**：当前最新主线版为 **2026.9.5**（非 LTS），v2026.7.35 与主线版之间可能存在功能/配置差异，迁移前请仔细阅读升级文档。已在 LTS 上运行的设备可安全应用此补丁级更新。

## 3. 项目进展

过去 24 小时内，共有 **191 个 PR 被合并或关闭**，推动多项核心功能与修复。以下为今日关键合并/处理进度：

- **【修复】更新中断处理**（PR [#152727](https://github.com/openclaw/openclaw/pull/152727)）：解决了 `openclaw update` 在升级过程中因 Gateway 验证中断导致 CLI 永久卡死的问题。合并后更新流程增加了有界探测与自动重试，提升升级稳定性。  
- **【安全】提供商违规处理**（PR [#155214](https://github.com/openclaw/openclaw/pull/155214)）：修复了因 `misalignment_policy_violation` 导致聊天停止后，提供商调查结果丢失以及输入框仍可输入的问题。合并后用户能清晰看到违规原因并暂停交互，提升应用安全性。  
- **【性能】Session worker 成员快照复用**（PR [#154707](https://github.com/openclaw/openclaw/pull/154707)）：优化多 viewer 场景下的 group metadata 读取，减少请求线程的重复扫描，降低 Gateway 负载。  
- **【兼容】角色模型限制**（PR [#154839](https://github.com/openclaw/openclaw/pull/154839)）已打开待审查：将角色模型限制应用于模型选择器，防止受限用户看到或选择其角色不允许的模型。涉及 iOS/macOS/WebUI 等多个前端，属于安全边界增强。  
- **【测试】CI 成本优化**（PR [#154959](https://github.com/openclaw/openclaw/pull/154959)）已合并：调整隔离 Gateway 测试的超时权重，避免小型 PR 被长时间占用。

## 4. 社区热点

以下为今日评论数最高、社区反应最集中的议题（均为 OPEN 状态）：

| 议题 | 评论数 | 核心诉求 |
|------|--------|----------|
| [#143524](https://github.com/openclaw/openclaw/issues/143524) **Agent SQLite WAL 无限增长 (P0, Gold Shrimp)** | 50 | Windows 上 Agent 的 sqlite-wal 文件在数天内膨胀至 1.4–2.8 GB，即使设置了 `wal_autocheckpoint=1000` 也无法触发检查点，导致 Gateway 启动阻塞。社区强烈要求紧急修复。 |
| [#91588](https://github.com/openclaw/openclaw/issues/91588) **Gateway 内存泄漏 (P1, Silver Shellfish)** | 31 | Gateway 进程 RSS 从 350 MB 增长至 15.5 GB 后 OOM 被 kill，触发反复重启。影响所有长时间运行的生产环境。 |
| [#91009](https://github.com/openclaw/openclaw/issues/91009) **Codex PreToolUse 钩子 CPU 耗尽 (P0, Silver Shellfish)** | 26 | Codex 集成中 `pre_tool_use` 事件触发大量短命进程，每个占用 100%+ CPU，导致 Gateway RPC 停滞。 |
| [#48003](https://github.com/openclaw/openclaw/issues/48003) **Steer 模式消息注入失败 (P1, Silver Shellfish)** | 20 | `messages.queue.mode: "steer"` 无法将用户消息注入正在运行的主会话 turn，导致消息被排队至 turn 结束，用户体验差。 |
| [#153257](https://github.com/openclaw/openclaw/issues/153257) **2026.9.5 更新导致 8 小时故障恢复 (P0, Gold Shrimp)** | 19 | 用户升级后环境彻底不稳定，从稳定状态变为 8 小时故障恢复。社区对 2026.9.5 的稳定性表示强烈质疑。 |

**社区情绪**：用户普遍对 **P0 级稳定性问题**（WAL、内存泄漏、CPU 耗尽）感到焦虑，呼吁维护者优先合并已有 Fix PR。同时，较老但未修复的 Issue（如 #48003 从 3 月至今）持续积累，社区对部分功能长期未解决表示失望。

## 5. Bug 与稳定性（按严重程度排列）

### P0 / 严重崩溃类

- **[#143524] Agent SQLite WAL 无界增长**：Windows 平台，WAL 文件数天内飙升至 2.8 GB 且无法 checkpoint。**状态**：`needs-maintainer-review`，尚无 Fix PR。  
- **[#91009] Codex PreToolUse 钩子 CPU 耗尽**：特定事件触发大量子进程，Gateway RPC 停滞。**状态**：`clawsweeper:no-new-fix-pr`，无新 Fix PR。  
- **[#153257] 2026.9.5 更新导致 8 小时故障**：用户强烈投诉。**状态**：`clawsweeper:needs-maintainer-review`，需调查升级引入的回归。  
- **[#89278] Codex OAuth 刷新超时导致 cron/heartbeat 失败**（P0, Diamond Lobster）：认证成功但超时 10s 导致定时任务失败，影响所有使用 OAuth 的自动化。**状态**：已有 `linked-pr-open`（PR [#148567](https://github.com/openclaw/openclaw/pull/148567) 正在处理 Sign in with ChatGPT，但未直接修复此问题）。  
- **[#40001] Write 工具缺少追加模式**（P0, Diamond Lobster）：隔离 cron 会话直接覆盖共享文件，导致数据静默丢失。**状态**：`clawsweeper:needs-product-decision`，尚未有 Fix PR。

### P1 / 严重功能与数据丢失

- **[#91588] Gateway 内存泄漏**（P1, Silver Shellfish）：OOM 循环崩溃。**状态**：`clawsweeper:no-new-fix-pr`。  
- **[#48003] Steer 模式消息丢失**（P1, Silver Shellfish）：消息无法即时注入。**状态**：`clawsweeper:linked-pr-open`（PR [#154922](https://github.com/openclaw/openclaw/pull/154922) 可能涉及隐式作用域，但未明确修复此 issue）。  
- **[#97616] 子进程泄漏导致僵尸进程累积**（P1, Silver Shellfish）：hook/tool 子进程未被收割。**状态**：尚无 Fix PR。  
- **[#148707] 2026.9.4 回复丢失**（P1, Silver Shellfish）：第二 run 抢占后回复被丢弃。**状态**：`clawsweeper:needs-info`。  
- **[#91931] 预填充 SOUL.md 导致 BOOTSTRAP.md 被错误删除**（P0, Diamond Lobster）：用户预配置的工作空间在首次运行前被标记为已完成引导，数据丢失。**状态**：已有 `linked-pr-open`（PR [#154727](https://github.com/openclaw/openclaw/pull/154727) 涉及 subagent facts，但未直接修复）。

### 近期已关闭的 Bug

- **[#154571] /tmp 构建目录泄漏**（2026.9.5）：每次加载外部插件产生 ~430 MB 未清理的临时目录。**已在 9.21 关闭**，推测已合并修复。  
- **[#153246] Plugin 构建临时目录 7.5 GB/天**（2026.9.19 → 9.21 关闭）：同样问题，已关闭。  
- **[#146637] npm 更新失败（2026.9.3→9.4）**（2026.9.13 → 9.21 关闭）：全局安装 swap 阶段报错，已修复。

## 6. 功能请求与路线图信号

今日讨论中以下功能请求获得较高关注，可能与后续版本直接相关：

- **多 Agent TTS/STT 配置覆盖**（[#66252](https://github.com/openclaw/openclaw/issues/66252)）：允许每个 Agent 使用不同的语音、语言或提供商。评论 8 条，标记为 `P3 / off-meta tidepool`，但用户呼声较高。  
- **Per-Agent dreaming 配置**（[#67413](https://github.com/openclaw/openclaw/issues/67413)）：支持单独控制每个 workspace 的 dreaming 开关，避免全量并发的 OOM 风险。已有 5 个 👍，但是 `stale` 状态。  
- **Slack Modal 支持**（[#88154](https://github.com/openclaw/openclaw/issues/88154)）：提供原生 Modal UI 以收集结构化输入。P2，社区讨论积极。  
- **多 Slot 内存架构**（[#60572](https://github.com/openclaw/openclaw/issues/60572)）：将单内存槽扩展为多个专用槽，允许不同提供者同时处理不同层级的内存。已有 3 个 👍。  
- **chatCompletions endpoint 模型忽略**（[#30381](https://github.com/openclaw/openclaw/issues/30381)）：当使用 `x-openclaw-agent-id` 时，无需验证 `model` 字段，兼容外部客户端。已有 2 个 👍，P2，有 `linked-pr-open`（可能已进入实现阶段）。

**信号判断**：TTS/STT 和 Memory 架构方向可能是 **2026 Q4 的路线图候选**；而 Slack Modal、chatCompletions 兼容性需求因有明确 PR 关联，**有望在 2026.10/11 版本中落地**。

## 7. 用户反馈摘要

从今日活跃的 Issue 评论中提炼出以下真实用户痛点与场景：

1. **稳定性首当其冲**：多位用户反馈升级到 2026.9.x 后出现严重退化。如 Issue #153257 作者直言“I genuinely regret upgrading to OpenClaw 2026.9.5”，认为此前稳定环境被彻底破坏。  
2. **数据库膨胀影响日常运维**：Windows 用户（#143524）描述 Agent SQLite WAL 达到 2.8 GB，不得不手动 TRUNCATE 后仍快速回弹，缺乏自动化清理机制，基本运维成本激增。  
3. **消息丢失导致对话断裂**：Steer 模式（#48003）和回复抢占（#148707）情境下用户无法获得完整回复，影响 Telegram/WebChat 使用体验。  
4. **长时间未修复的老 bug 令人沮丧**：Issue #40001（Write 缺追加模式，3月提出）和 #48003（3月提出）仍无修复 PR，社区多次在评论中催促。  
5. **升级体验不佳**：多位用户反映 `openclaw update` 失败，且失败原因码不清晰（#154114 “No usable, authenticated, tool-capable inference route”），迫使回滚旧版本。  
6. **文档缺失 K8s 部署最佳实践**：Issue #91455 指出官方 Kubernetes 安装文档指导不清晰，用户尝试后遇到困难。

**正面反馈**：部分用户（如 #73537）表达了长期使用 OpenClaw 的感激之情，认为其已成为日常生活和工作的核心工具。社区整体对项目愿景持认可态度，但稳定性问题正在侵蚀信任。

## 8. 待处理积压（长期未响应的关键 Issue/PR）

以下 Issue 和 PR 已开放较长时间，且维护者未分配或未提供明确计划，建议本周内给出回应：

| 项目 | 创建时间 | 优先级 | 状态标签 | 备注 |
|------|----------|--------|----------|------|
| [#67413](https://github.com/openclaw/openclaw/issues/67413) Per-Agent dreaming | 2026-04-15 | P2 | `stale`, `needs-product-decision` | 已 stale，无维护者回复，用户已提新 issue 催促。 |
| [#81182](https://github.com/openclaw/openclaw/issues/81182) 溢出恢复应优先截断工具结果 | 2026-05-12 | P1 | `clawsweeper:linked-pr-open` | 有 linked PR 但未关闭，需确认进度。 |
| [#69208](https://github.com/openclaw/openclaw/issues/69208) 跨渠道重复 transcript 问题 | 2026-04-20 | P1 | `needs-product-decision` | 厂商决策停滞，影响多通道用户。 |
| [#73537](https://github.com/openclaw/openclaw/issues/73537) 生产稳定性标签 | 2026-04-28 | P3 | `stale`, `needs-product-decision` | 用户呼吁区分稳定版/实验版发布。 |
| [#154114](https://github.com/openclaw/openclaw/issues/154114) update 候选排练失败（P0） | 2026-09-20 | P0 | `clawsweeper:needs-maintainer-review` | 影响所有会自动更新的用户，需紧急确认是否已有 PR 在准备。 |
| [#152727](https://github.com/openclaw/openclaw/pull/152727) 更新中断修复（PR） | 2026-09-19 | P1 | 已合并 | 已合并，但后续需确认其是否完全解决了 #154114 中的问题。 |

---

**总结**：OpenClaw 项目社区活跃度极高，但核心稳定性问题仍处于高发期。管理层应优先分配资源到 **P0 级 Bug 修复**（WAL 增长、内存泄漏、OAuth 超时），并主动沟通路线图以恢复社区信心。功能类 issue 虽然讨论热烈，但需在稳定性改善后方可大规模推进。

---

## 横向生态对比

## 个人 AI 助手/自主智能体开源生态横向对比分析报告（2026-09-22）

### 1. 生态全景
当前个人 AI 助手与自主智能体开源生态呈现 **“双高”特征**：项目活跃度普遍极高，但稳定性问题成为制约用户信任的核心瓶颈。以 OpenClaw 为首的头部项目日均处理数百条 Issue/PR，社区贡献热情高涨；但大量 P0/P1 级 Bug（内存泄漏、数据库无限增长、循环死锁）同时暴露了快速迭代中的质量债。与此同时，安全、多代理协作、本地化等方向成为多项目共同探索的下一增长点，整体生态处于 **“功能扩展与质量巩固并行”** 的关键阶段。

### 2. 各项目活跃度对比（2026-09-22）

| 项目 | 日新增活跃Issues | 日新增PR | 日合并PR | 版本发布 | 健康度评估 |
|------|-----------------|----------|---------|---------|------------|
| **OpenClaw** | 451 | 500 | 191 | 1 (LTS) | 中等（高频迭代，P0问题持续） |
| **Hermes Agent** | 50 | 50 | ~3 | 0 | 良好（快速修复严重Bug） |
| **ZeroClaw** | 50 | 50 | 少量 | 0 | 中等（大量PR待审，安全风险偏高） |
| **CoPaw** | 8 | 33 (17待合并+16合并) | 16 | 0 | 较好（修复密集，但提示注入未解） |
| **NanoBot** | 3 | 28 | 4 | 0 | 良好（社区响应快，WebUI丰富） |
| **LobsterAI** | 2 | 17 | 15 | 0 | 良好（集中修复启动/迁移问题） |
| **NanoClaw** | 1 | 7 | 1 | 0 | 中等（社区贡献活跃，审查积压） |
| **PicoClaw** | 1 | 7 | 1 | 0 | 中等（性能Bug悬而未决） |
| **IronClaw** | 1 | 2 | 1 | 0 (候选) | 良好（稳定迭代，模型质量追踪） |
| **Moltis** | 2 | 2 | 0 | 0 | 中等（功能PR待审，无合并） |
| **NullClaw** | 0 | 0 | 0 | 0 | 不活跃 |
| **TinyClaw** | 0 | 0 | 0 | 0 | 不活跃 |
| **ZeptoClaw** | 0 | 0 | 0 | 0 | 不活跃 |

### 3. OpenClaw 在生态中的定位
- **核心参照地位**：日活跃度为第二名 Hermes Agent 的 9 倍，社区体量遥遥领先；版本体系完备（LTS vs 主线），生产部署指南最成熟。
- **技术路线差异**：采用 **Gateway + Agent 分离架构**，强调模块化与多会话管理；而 Hermes Agent 侧重 **插件系统与桌面端集成**，NanoBot 聚焦 **现代化 WebUI 自动化**，ZeroClaw 则主攻 **安全沙箱与代理间通信**。
- **稳定性挑战**：尽管拥有最大社区，却也是 P0 级 Bug 最多的项目（WAL 增长、内存泄露、升级回退），正在“规模”与“质量”间艰难平衡，与 Hermes Agent、NanoBot 等“快速修复、较少积压”形成对比。

### 4. 共同关注的技术方向
| 方向 | 涉及项目 | 具体诉求 |
|------|---------|----------|
| **本地/离线模型支持** | Moltis, OpenClaw（TTS/STT功能请求） | 离线 TTS、本地推理、减少云依赖 |
| **资源控制与稳定性** | OpenClaw, NanoBot, ZeroClaw, CoPaw | WAL 无限增长、自动压缩死锁、主机级资源限制、循环误终止 |
| **跨平台兼容性** | Hermes Agent, LobsterAI, NanoClaw | Windows/macOS 启动崩溃、符号链接问题、包管理器检测 |
| **升级与迁移体验** | OpenClaw, LobsterAI, NanoClaw | 升级后故障回退、遗留数据迁移、脚本兼容性 |
| **安全与权限** | OpenClaw, CoPaw, ZeroClaw | 提供商违规处理、持久性提示注入、沙箱绕过、授权漏洞 |
| **多代理协作** | OpenClaw（多Agent会话）, ZeroClaw（代理间消息RFC） | 跨代理通信、资源共享、任务编排 |
| **UI/移动端体验** | NanoBot, PicoClaw, Hermes Agent | 输入卡顿、移动端侧边栏、重复回复、渐进式Web应用 |

### 5. 差异化定位分析
| 维度 | OpenClaw | Hermes Agent | NanoBot | ZeroClaw | CoPaw | LobsterAI |
|------|----------|--------------|---------|----------|-------|-----------|
| **功能侧重** | 通用个人助手，全功能集成 | 插件生态驱动，桌面端优先 | 轻量WebUI，自动化工作流 | 企业级沙箱，多代理安全 | 任务循环可靠性，Agent技能系统 | 中国IM生态（微信/飞书/QQ） |
| **目标用户** | 重度开发者/自部署团队 | 插件开发者和桌面用户 | 追求现代UI/移动端用户 | 追求安全合规的企业 | 需要稳定长对话的开发者 | 中国地区消息机器人用户 |
| **核心架构** | Gateway + Agent 异步 | 插件系统 + 运行时 | 自动化管道 + WebUI | 沙箱隔离 + 代理间RPC | 循环检测 + 技能系统 | 桌面应用 + 通道适配器 |
| **稳定性风格** | 大版本但有波动 | 快速热修复 | 高质量但功能少 | 功能丰富但审核慢 | 修复密集但安全风险高 | 依赖兼容性专注 |

### 6. 社区热度与成熟度
- **第一梯队（超高活跃/快速迭代）**：OpenClaw, Hermes Agent, ZeroClaw, CoPaw  
  日均数十条 Issue/PR，社区贡献者众多，但 P0 级 Bug 频发，适合有运维能力的团队跟进主线。
- **第二梯队（活跃/质量巩固）**：NanoBot, LobsterAI, NanoClaw, PicoClaw  
  活跃度适中，修复速度快，功能相对聚焦，适合实际使用与贡献。
- **第三梯队（低活跃/稳定维护）**：IronClaw, Moltis  
  迭代放缓，专注于特定场景（IronClaw 模型评估、Moltis 语音）。
- **未活跃项目**：NullClaw, TinyClaw, ZeptoClaw  
  短期无更新，

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，以下是为您生成的 NanoBot 项目动态日报。

---

# NanoBot 项目动态日报 | 2026-09-22

## 今日速览

今日项目活跃度极高，尤其在核心逻辑修复与 WebUI 功能迭代上齐头并进。**PR 活动创下近期峰值**，共有 28 条 PR 更新，其中 24 条待合并，表明开发团队正在进行密集的功能交付期。社区反馈主要聚焦于**两个核心稳定性问题**：自动上下文压缩的死锁风险与长会话构建阶段的高延迟。针对这两个问题，社区贡献者已迅速提交修复 PR，体现了良好的社区响应机制。总体来说，项目处于“全力冲刺新功能 + 快速修补关键 bug”的健康节奏。

## 版本发布

无新版本发布。

## 项目进展

今日有 4 个 PR 被合并/关闭，同时多个修复关键问题的 PR 已提交，项目核心稳定性与 WebUI 体验有望在下个版本中获得显著提升。

- **日志与可观测性系统改进**： [#5840](https://github.com/HKUDS/nanobot/pull/5840) 已被合并。该 PR 标准化了 CLI 日志，增加了清晰的请求/会话/轮次关联 ID，并修复了 13 处 `exc_info=True` 的误用。这为开发者排查问题提供了强有力的数据支撑。

- **移动端 WebUI 体验修复**：关联 Issue [#5770](https://github.com/HKUDS/nanobot/issues/5770) 已被关闭，表明移动端侧边栏搜索按钮误触发的 bug 已通过相关 PR 修复。

- **关键 Bug 修复 PR 已就绪**：
    - [#5857](https://github.com/HKUDS/nanobot/pull/5857) 针对自动化转录总结死锁问题 [#5849](https://github.com/HKUDS/nanobot/issues/5849) 提出修复方案，通过在发送给总结模型前对历史进行 Token 预算检查，防止上下文超限导致永久死锁。
    - [#5846](https://github.com/HKUDS/nanobot/pull/5846) 针对长会话 BUILD 阶段延迟问题 [#5843](https://github.com/HKUDS/nanobot/issues/5843) 提出修复方案，通过添加详细的结构化 DEBUG 计时事件，以识别和优化各子阶段的性能瓶颈。

## 社区热点

今日社区讨论的焦点明确集中在**性能与死锁**这两个高影响度问题上，同时也反映了对 WebUI 交互体验的强烈需求。

1.  **自动压缩死锁风险 (Issue #5849)**：[#5849](https://github.com/HKUDS/nanobot/issues/5849) 报告了一个严重的逻辑错误：自动压缩路径没有 Token 预算保护，当上下文长度超过模型上限时，压缩操作会永远无法完成，导致死锁。该问题获得了社区的迅速响应，贡献者 [iuiu-py] 随即提交了修复 PR [#5857](https://github.com/HKUDS/nanobot/pull/5857)。这凸显了社区对核心 Agent 运行稳定性的高度关注。
2.  **长会话构建阶段延迟 (Issue #5843)**：[#5843](https://github.com/HKUDS/nanobot/issues/5843) 描述了在长会话中，每次用户提问后，BUILD 阶段会无故等待 10 秒到数十秒。此问题严重影响了用户体验，贡献者 [Solaris-star] 已提交 PR [#5846](https://github.com/HKUDS/nanobot/pull/5846) 进行诊断优化。
3.  **WebUI 功能大量涌现**：以 [Re-bin] 为首的多位贡献者提交了多个 WebUI 功能 PR，包括**命令面板** ([#5856](https://github.com/HKUDS/nanobot/pull/5856))、**子任务输出面板** ([#5855](https://github.com/HKUDS/nanobot/pull/5855))、**图片生成展示** ([#5853](https://github.com/HKUDS/nanobot/pull/5853))、**使用量统计** ([#5851](https://github.com/HKUDS/nanobot/pull/5851)) 等。这表明社区不仅关注稳定性，也对提升用户交互的丰富度和信息密度抱有强烈热情。

## Bug 与稳定性

今日共收到 3 个 Issues，其中包含两个严重 Bug，均已有一个或多个修复 PR 提交。

| 严重程度 | Issue/PR | 描述 | 状态 |
| :--- | :--- | :--- | :--- |
| **严重** | [#5849](https://github.com/HKUDS/nanobot/issues/5849) | **自动压缩死锁**：`summarize_transcript` 无预算保护，历史超出输入预算后导致压缩永久无法恢复。 | 已有修复 PR [#5857](https://github.com/HKUDS/nanobot/pull/5857) |
| **严重** | [#5843](https://github.com/HKUDS/nanobot/issues/5843) | **BUILD 阶段延迟**：长会话在 LLM 调用前存在 10 秒至数十秒的未知等待。 | 已有诊断修复 PR [#5846](https://github.com/HKUDS/nanobot/pull/5846) |
| **中等** | [#5770](https://github.com/HKUDS/nanobot/issues/5770) | **移动端 UI Bug**：打开侧边栏时错误地聚焦了搜索按钮并显示提示。 | **已关闭**，已修复。 |

## 功能请求与路线图信号

今日的功能请求主要体现在新提交的 PR 中，这些 PR 很可能成为下一个小版本的核心内容。

- **核心能力扩展**：
    - **作用域命令系统** ([#5854](https://github.com/HKUDS/nanobot/pull/5854))：引入可复用的提示词命令，支持实例/工作空间作用域，并添加管理界面。这为高级用户和团队协作提供了强大的配置能力。
    - **新的底层 Provider 支持** ([#5845](https://github.com/HKUDS/nanobot/pull/5845))：请求添加 **Opper** 作为内置 Gateway Provider，体现了社区对模型多样化的持续需求。
    - **复用型 JEV 客户端** ([#5825](https://github.com/HKUDS/nanobot/pull/5825))：为 OpenRouter 决策端点添加可复用的客户端，为未来实现心跳、策略选择等功能奠定基础。

- **WebUI 体验显著增强**：
    - 大量来自 [Re-bin] 的 PR 正在重构 WebUI 的交互范式，包括**文件操作菜单** ([#5850](https://github.com/HKUDS/nanobot/pull/5850))、**链接预览与操作** ([#5852](https://github.com/HKUDS/nanobot/pull/5852))、**Mermaid 图表渲染** ([#5848](https://github.com/HKUDS/nanobot/pull/5848)) 和**会话级文件预览** ([#5847](https://github.com/HKUDS/nanobot/pull/5847))。这说明下一个版本的 WebUI 将具备更接近成熟桌面应用的交互体验。

## 用户反馈摘要

以下是从 Issues 和 PR 描述中提炼的用户典型场景与痛点：

- **核心痛点 - 会话太长无法使用**：用户报告在复杂对话任务中，由于自动总结机制存在死锁，导致对话完全卡死，无法恢复。这是对 Agent 记忆管理机制的信任危机，是必须优先解决的关键问题。(来源: [#5849](https://github.com/HKUDS/nanobot/issues/5849))
- **核心痛点 - 响应太慢**：长会话中用户需要耐心等待数十秒才能看到首个 Token 输出。用户对这种“静默延迟”感到困惑，不清楚这是否是预期行为。这表明系统缺乏有效的进度反馈。(来源: [#5843](https://github.com/HKUDS/nanobot/issues/5843))
- **社区共识 - 对 WebUI 的强烈改造意愿**：多位贡献者正在从文件操作、命令管理、数据可视化等多个维度改造 WebUI，这暗示用户对终端式的交互感到不够直观，迫切需要一个功能更丰富、交互更自然的图形界面。

## 待处理积压

以下为开放时间较长且对功能或稳定性有根本性影响，但尚未合并的 PR，建议维护者优先评估：

- **[#4819](https://github.com/HKUDS/nanobot/pull/4819) (更新: 2026-09-21)**：修复内存问题，将合并锁存储从 `WeakValueDictionary` 改为普通字典。该 PR 解决了一个潜在的、难以追踪的并发 bug，已开放超过 2 个月，建议尽快审查合并，以避免因垃圾回收导致的锁失效问题。
- **[#4820](https://github.com/HKUDS/nanobot/pull/4820) (更新: 2026-09-21)**：拒绝 Web 获取中非字符串的 URL。该 PR 修复了因类型错误导致的缓存签名污染问题，属于防御性编程和小 bug 修复，建议一并审查。
- **[#5412](https://github.com/HKUDS/nanobot/pull/5412) (更新: 2026-09-21)**：确保网关后台进程的输出能及时刷入日志。对于调试和监控后台进程至关重要，已开放超过 1 个月，建议合并。
- **[#5641](https://github.com/HKUDS/nanobot/pull/5641) (更新: 2026-09-21)**：修复 iOS PWA (渐进式 Web 应用) 的点击和状态栏问题。该 PR 对移动端用户至关重要，但其关联 Issue [#5770](https://github.com/HKUDS/nanobot/issues/5770) 已关闭，可能需要确认该 PR 是否为最终修复方案并处理合并冲突。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据您提供的 Hermes Agent 项目数据生成的 2026 年 9 月 22 日项目动态日报。

---

### Hermes Agent 项目日报 | 2026 年 9 月 22 日

---

#### 1. 今日速览

今日 Hermes Agent 项目社区活动极其活跃，展现了极高的维护和开发投入。过去 24 小时内，共产生 50 条 Issue 和 50 条 PR，其中大量 Issue 为 P2 级 Bug 报告，表明项目在快速迭代的同时，也正面临一些影响稳定性的系统性问题。值得关注的是，项目团队反应迅速，已针对多个 P1/P2 级严重 Bug（如 Windows 启动崩溃、图像数据永久删除）提交并合并了修复 PR。同时，社区提交的 PR 数量庞大（待合并达 48 条），反映了开发者生态的健康成长和高参与度。总体来看，项目处于“高并发迭代、高强度问题修复”的关键阶段，活跃度评估为 **极高**。

#### 2. 版本发布

-   **Hermes Agent v0.21.4 (v2026.9.21)**
    -   **发布内容**：这是一个补丁（Patch）版本，主要目标是将自 v0.21.3 以来合并的约 1,800 个 PR 整合为一个稳定的标签版本，供下游消费者（如 Docker 镜像、Hermes Cloud 等）使用。该版本**不包含**自上次发布以来的详细功能更新说明。
    -   **破坏性变更**：发布说明中未提及。
    -   **迁移注意事项**：对于使用 Docker 镜像或托管部署的用户，这是一个推荐的稳定升级版本。由于是补丁整合版，升级路径相对平滑，但建议在非生产环境先行验证。

#### 3. 项目进展

今日项目核心进展体现在对**严重 Bug** 的快速修复上，以下为已合并/关闭的里程碑式 PR 及 Issue：

-   **[CLOSED] Issue #118026 (P0): Windows 平台启动失败**：修复了因 `fcntl` 模块在 Windows 上缺失 `F_RDLCK` 导致后端进程崩溃的严重问题。此 Issue 已关闭，表明 Windows 用户的体验回归正常。
-   **[CLOSED] PR #118300 (P1): 图像拒绝处理**：修复了当提供商拒绝图片内容时，恢复路径会错误地**永久删除整个会话中所有图片**的严重 Bug。该 PR 已被合并，并成功关闭了 Issue #118053。
-   **[OPEN] PR #118610 (P2): 桌面端重复回复**：提交了修复桌面端偶发渲染重复助手回复问题的 PR，通过保留回复的持久化行 ID 和工具身份，避免了等文本内容相同的误判。
-   **[OPEN] PR #118647 (P2): 网关重启数据丢失**：提交了修复网关重启时，后台审查（post-turn background review）任务导致数据丢失或状态不一致问题的 PR，确保审查任务在重启边界处被正确清理。

项目整体向前迈进了坚实的一步，尤其是在**数据安全**和**平台兼容性**方面，通过快速修复几个关键 Bug，显著提升了项目在用户生产环境中的可靠性。

#### 4. 社区热点

以下 Issue 和 PR 获得了最广泛的社区讨论和关注，反映了当前用户的痛点与诉求：

1.  **[Issue #35060 (8 条评论) - 功能请求：Home Assistant 集成](https://github.com/nousresearch/hermes-agent/issues/35060)**
    -   **诉求分析**：用户强烈希望在 Home Assistant 的 `watch_entities` 功能中，能够**自定义事件转发目标**（如 WhatsApp、Telegram），而非仅限平台内部通知。这代表了用户对于构建个性化、跨平台智能家居通知管道的深层需求，也是 Hermes Agent 拓展物联网场景的关键功能。

2.  **[Issue #96355 (8 条评论) - Bug：`delegate_task` 返回虚假完成状态](https://github.com/nousresearch/hermes-agent/issues/96355)**
    -   **诉求分析**：即使“输出模式”验证失败，`delegate_task` 工具仍可能报告任务“完成（completed）”。这是一个对**任务可靠性**有严重影响的逻辑 Bug。用户对基于 Agent 的任务调度系统的“承诺”充满不信任，社区讨论聚焦于需要将验证状态正确传播到任务生命周期的终点。

3.  **[Issue #70108 (7 条评论) - Bug：桌面端重复渲染回复](https://github.com/nousresearch/hermes-agent/issues/70108)**
    -   **诉求分析**：用户报告桌面端应用会渲染出重复的助手回复气泡，但数据库却只记录了一份。这是一个影响聊天界面**用户体验**的典型前端问题，用户期待一个干净、无重复的对话流。社区普遍认同这是一个与状态同步和前端渲染逻辑相关的复杂 Bug。

#### 5. Bug 与稳定性

今日报告的 Bug 集中在 P1/P2 级别，**数据安全**和**核心功能可靠性**是两大主题。以下为按严重程度排列的关键问题：

-   **P1 级**
    -   **[已修复] [#118053](https://github.com/nousresearch/hermes-agent/issues/118053) - 图像拒绝导致永久删除**：提供商拒绝图像内容后的恢复路径会删除会话中的所有图片。**(对应修复 PR #118300 已合并)**
    -   **[已关闭] [#118026](https://github.com/nousresearch/hermes-agent/issues/118026) - Windows 启动失败**：因 `fcntl` 模块兼容性问题导致后端崩溃。

-   **P2 级**
    -   [#118628](https://github.com/nousresearch/hermes-agent/issues/118628) - 桌面端关闭会话强制中断进行中的任务，且中断的回复不显示。
    -   [#110126](https://github.com/nousresearch/hermes-agent/issues/110126) - 输出截断 (`finish_reason='length'`) 是一个涉及四个子系统的系统性故障。
    -   [#107559](https://github.com/nousresearch/hermes-agent/issues/107559) - Cron 任务在手动运行后，`run` 动作被死锁，永久拒绝后续执行。
    -   [#107516](https://github.com/nousresearch/hermes-agent/issues/107516) - 上下文压缩在辅助模型繁忙时可无限重试，无退避或上限。
    -   [#118643](https://github.com/nousresearch/hermes-agent/issues/118643) - 桌面端“更新 Hermes”功能在特定场景下会导致网关的 `sys.modules` 过时，引发 `ImportError`。

-   **P3 级**
    -   [#118618](https://github.com/nousresearch/hermes-agent/issues/118618) - `get_default_hermes_root` 函数未处理 `Path.resolve` 可能抛出的 `OSError`，导致配置解析异常。
    -   [#118619](https://github.com/nousresearch/hermes-agent/issues/118619) - Camofox VNC 实时预览链接因 `/health` 接口缺失端口信息而无法发现。

#### 6. 功能请求与路线图信号

今日提交的功能请求和 PR 揭示了社区对项目未来发展的核心期望：

-   **强信号：Plugin Catalog 扩展**
    -   **PR #118299** ([hermes-lossless-context-manager](https://github.com/nousresearch/hermes-agent/pull/118299)): 社区贡献的“无损上下文管理器”插件，通过 SQLite DAG 确保消息永不丢失。**信号**：表明社区正寻求更可靠、更定制化的上下文管理方案，未来可能被纳入核心或作为官方推荐插件。
    -   **PR #118322** ([hermes-zh 简中本地化](https://github.com/nousresearch/hermes-agent/pull/118322)): 一个完整的官方生命周期简体中文本地化插件。**信号**：强烈预示着项目将重点拓展中文用户市场，后续版本可能会加强 i18n 支持。

-   **中等信号：路由与配置优化**
    -   **PR #103965** ([per-task profile routing](https://github.com/nousresearch/hermes-agent/pull/103965)): 支持为 `delegate_task` 的每个子任务指定不同的 Hermes 配置文件（模型、主机、内存等）。**信号**：这将极大丰富多模态、多代理协同的应用场景，是通往高级工作流编排的关键功能。
    -   **PR #118645** ([fail-closed per-turn model routing](https://github.com/nousresearch/hermes-agent/pull/118645)): 引入“关闭即失败”的每轮次模型路由策略。**信号**：反映了社区对模型调用安全性和可控性的高标准要求，旨在防止意外使用错误模型导致的各种问题。

#### 7. 用户反馈摘要

从今天活跃的 Issue 评论中，可以提炼出以下真实用户声音：

-   **对核心任务信任的渴望**：来自 Issue #96355，用户对 `delegate_task` 的虚假完成状态感到困扰，希望系统能诚实地反馈成功与否，这是构建可靠复杂工作流的基石。
-   **对配置灵活性的需求**：来自 Issue #35060，用户不再满足于开箱即用的设定，渴望深度自定义能力，尤其是将系统事件与个人偏好的第三方服务（如通信软件）打通。
-   **对桌面端核心交互的修复期待**：来自 Issue #70108 和 #118628，用户对桌面端界面上的重复回复、强制中断等基础交互问题反馈强烈，认为这些是严重影响日常使用体验的“烦人” Bug。
-   **对模型路由问题的困惑**：来自 Issue #110126，用户将“输出截断”描述为“系统性故障”，反映出对目前通过修改配置来缓解模型能力限制（如最大输出 Token）的方式感到不满，期望从根本上解决。
-   **对 Windows 和 macOS 平台问题的担忧**：来自 Issue #118026 和 #118643，用户对平台特有的崩溃和升级问题感到沮丧，尤其是在 Windows 上，这是阻止团队采用的关键障碍之一。

#### 8. 待处理积压

以下为部分长期未得到核心团队响应或处理的、社区反馈强烈的 Issue 和 PR，提醒维护者关注：

-   **Issue #47246** ([背景/守护进程模式](https://github.com/nousresearch/hermes-agent/issues/47246)): 自 2026 年 6 月提出的功能请求，希望桌面端能像后台服务一样运行，无需保持终端窗口。**状态**：无核心开发者回复。
-   **PR #57487** ([网关死亡循环修复](https://github.com/nousresearch/hermes-agent/pull/57487)): 自 2026 年 7 月提交的 PR，旨在修复由于策略验证失败导致网关陷入“启动-退出-重启”死循环的问题。**状态**：已创建两个月，等待合并。
-   **PR #53356** ([桌面端扫描器配置](https://github.com/nousresearch/hermes-agent/pull/53356)): 自 2026 年 6 月提交，为桌面端仓库扫描器增加配置项（如排除路径、扫描根目录限制）。**状态**：同样等待了两个多月，未有进展。
-   **PR #53669** ([凭证文件路径修复](https://github.com/nousresearch/hermes-agent/pull/53669)): 自 2026 年 6 月提交，修复因符号链接导致的技能（Skills）拷贝问题。**状态**：长期未决。

以上 PR 和 Issue 均围绕着提升可用性、修复长期存在的痛点的核心诉求，建议项目团队适当分配资源进行审查和合并。

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，作为AI智能体与个人AI助手领域开源项目分析师，以下是为 **PicoClaw (github.com/sipeed/picoclaw)** 生成的项目动态日报。

---

# **PicoClaw 项目动态日报 | 2026-09-22**

## 1. 今日速览
过去24小时内，项目整体活跃度处于**中等偏上**水平。**社区讨论热烈**，一个关于Web UI长历史对话输入卡顿的Bug成为焦点，汇聚了13条评论。功能开发方面进展平稳，两个重要功能PR（IRC多行消息支持与OAuth Scope修复）持续等待合并。同时，昨日成功解决了一个因第三方库版本冲突导致的QQ频道频道授权失败问题，体现了维护者对依赖问题的响应能力。今日**无新版本发布**。

## 2. 版本发布
无。

## 3. 项目进展
今日项目在代码合并方面**无明显推进**。主要事件为：
- **PR #3384 已关闭**：一个由AI Agent误提交至本仓库的PR已被标记并关闭，未对项目产生实际影响。
- **Bug #3365 已关闭**：该Issue报告了QQ频道通道因`botgo`与`resty`库版本不兼容导致的401授权失败问题。通过社区讨论，该问题根源已被定位并解决，增强了项目对第三方平台集成的稳定性。

整体来看，项目核心代码库虽无新代码合并，但成功处理了外围依赖问题，并在社区形成了有价值的讨论。

## 4. 社区热点
**热点 Issue： [#3281 Web UI输入卡顿问题](https://github.com/sipeed/picoclaw/issues/3281)**
- **状态**：开放中，过去24小时更新活跃。
- **热度**：13条评论，2个👍。
- **分析**：这是当前社区最关切的问题。用户反馈当会话历史稍长时，Web UI的输入框反应变得非常延迟。背后的核心诉求是**对前端渲染性能的优化**，尤其是在处理大量聊天记录时的重绘与状态更新的效率问题。这直接影响了核心聊天体验，需要开发团队重点投入。

## 5. Bug 与稳定性
### [严重] Web UI 输入卡顿
- **Issue**: [#3281](https://github.com/sipeed/picoclaw/issues/3281)
- **描述**：在较长会话历史下，Web UI输入框出现严重卡顿，影响日常使用。
- **状态**：**未修复**。目前无关联的Fix PR。

### [已解决] QQ 频道401授权失败
- **Issue**: [#3365](https://github.com/sipeed/picoclaw/issues/3365)
- **描述**：因`botgo v0.2.1`与`resty v2.17`版本不兼容导致`Authorization`参数错误。
- **状态**：**已关闭**。问题已被定位并解决，建议用户在构建时注意依赖版本锁定。

## 6. 功能请求与路线图信号
- **[Feature] 支持 OpenAI 兼容提供者**：Issue [#3366](https://github.com/sipeed/picoclaw/issues/3366) 提出增加对OpenAI兼容API（如自托管路由器）的支持。这是当前大模型应用集成的主流需求，**极有可能被纳入下一版本开发路线图**。社区对该功能的讨论正从“是否要造轮子”转向“如何实现最优雅的配置”。
- **[PR] IRCv3 多行消息支持**：PR [#3354](https://github.com/sipeed/picoclaw/pull/3354) 仍为开放状态。该功能将显著提升IRC通道的聊天质量，将长消息或代码块作为完整消息接收。合并优先级较高。

## 7. 用户反馈摘要
- **痛点聚焦**：用户`xpader`在 #3281 中描述了随着对话历史变长，输入延迟呈线性增加的问题，这暴露了前端在处理大型虚拟列表或DOM更新时的性能瓶颈。
- **使用场景**：用户`ItachiSan`在 #3366 中提出希望接入自建的路由器（如9Router），典型使用场景为需要通过统一网关管理多个后端模型服务的企业或高级用户。
- **满意度**：用户`crazysarah`对于 #3365 问题的快速定位和解决表示积极反馈（Issue被关闭），表明社区对平台兼容性问题的响应速度持肯定态度。

## 8. 待处理积压
- **#3281 Web UI输入卡顿**：虽非“长期未响应”，但其复杂的性能问题可能需要大规模重构。建议维护者**尽快标记优先级**并分配资源，防止用户流失。
- **#3354 IRC多行消息支持**：该PR已开放21天，且功能明确、代码改动合理，**建议维护者尽快进行代码审查并合并**，以保持IRC通道功能的竞争力。
- **#3378 OAuth Scope修复**：该项目PR修复了一个潜在的Bug，虽未合并，但其功能性直接关系到OAuth集成的正确性，不应被遗忘。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

# NanoClaw 项目动态日报 — 2026-09-22

## 1. 今日速览

- 过去24小时内项目保持中等活跃度：新增1个 Issue，收到7个 PR 更新（其中1个已合并关闭，6个待合并）。
- 唯一的新 Issue（#3860）报告了 `restart.sh` 在 `FORCE_COLOR=1` 环境下时间戳解析失败的问题，影响重启脚本的可靠性。
- 已合并的 PR #2689 解决了 Signal 适配器中 DM 路由和消息投递的多个一致性问题，是 channel 层的重要稳定性改进。
- 多个待合并的 PR 集中在 Signal/WhatsApp 通道修复、CLI 构建优化、安装脚本兼容性及错误路由等方面，社区贡献活跃。
- 无新版本发布，项目处于持续修复与功能完善阶段。

## 2. 版本发布

无新版本发布。

## 3. 项目进展

### 已合并/关闭 PR

**#2689 [CLOSED] fix(signal): DM platform ID consistency, isMention, and ask_question/approval delivery**  
- **作者**: klingel | **更新**: 2026-09-21  
- **摘要**: 修复 Signal 私信中 `isMention` 未设置导致首次消息被丢弃的问题；统一 DM 平台 ID 前缀为 `signal:`；确保 `ask_question` 和 `approval` 消息正确投递。  
- **意义**: 提升 Signal 通道的私信可靠性，解决了用户无法收到首次消息的严重缺陷。  
- **[链接](https://github.com/nanocoai/nanoclaw/pull/2689)**

## 4. 社区热点

### #3860 [OPEN] restart.sh: FORCE_COLOR makes the restart timestamp unparseable  
- **作者**: witek | **创建**: 2026-09-21 | **评论**: 0 | 👍: 0  
- **问题核心**: `setup/lib/restart.sh` 通过 `node -e 'console.log(Date.now())'` 获取时间戳，但 pnpm 子进程中 `FORCE_COLOR=1` 导致 Node.js 对数字输出添加颜色转义码，使后续解析失败。  
- **社区诉求**: 要求修复重启脚本的兼容性，避免因环境变量导致时间戳格式异常。用户 witek 可能是运维或高级用户，该问题影响自动重启流程的稳定性。  
- **[链接](https://github.com/nanocoai/nanoclaw/issues/3860)**

### #3837 [OPEN] [area/channels] fix(signal): consolidate attachment, DM-routing, and outbound-queue fixes  
- **作者**: seefood | **更新**: 2026-09-21  
- **摘要**: 将多个 Signal 适配器的修复整合到一个补丁中，包括附件处理（图片、语音、文件）统一通过挂载的 inbox 机制，以及 DM 路由和出队逻辑的修正。  
- **社区热度**: 虽然评论数为 0，但该 PR 整合了多个久悬的修复，且更新日期接近，可能是维护者正在审阅的重点。  
- **[链接](https://github.com/nanocoai/nanoclaw/pull/3837)**

## 5. Bug 与稳定性

### 严重级别：高

- **#3860 [OPEN] restart.sh: FORCE_COLOR 导致重启时间戳不可解析**  
  问题影响所有使用 pnpm 执行 `restart.sh` 的用户，可能导致重启时间记录错误或自动化流程中断。无现有修复 PR，需尽快处理。  
  **[链接](https://github.com/nanocoai/nanoclaw/issues/3860)**

### 严重级别：中

- **#3311 [OPEN] fix(agent-runner): route scheduled-task errors to the operator**  
  定时任务抛出异常时，错误消息因缺少路由字段而无法正确发送给操作员。该问题影响任务监控与告警。已有 PR #3311 待合并。  
  **[链接](https://github.com/nanocoai/nanoclaw/pull/3311)**

- **#3273 [OPEN] fix(setup): detect package manager in install-node.sh**  
  安装脚本在非 Debian 系 Linux（如 Fedora、Arch）上无条件执行 `apt-get` 导致安装失败。PR #3273 提供了包管理器自动检测，待合并。  
  **[链接](https://github.com/nanocoai/nanoclaw/pull/3273)**

### 严重级别：低

- **#3420 [OPEN] fix(add-macos-statusbar): make Swift code and plist labels slug-aware**  
  状态栏守护服务使用旧版 label `com.nanoclaw`，而新版使用 `com.nanoclaw-v2-<slug>`，导致 macOS 用户无法正常启动服务。  
  **[链接](https://github.com/nanocoai/nanoclaw/pull/3420)**

## 6. 功能请求与路线图信号

### 已实现/在途的功能

- **WhatsApp 群组名称识别** (#3859)  
  PR #3859 实现了 `resolveChannelName` 方法，使注册卡片能正确显示 WhatsApp 群组名称而非通用名。预计将随下一版本合并，提升用户体验。  
  **[链接](https://github.com/nanocoai/nanoclaw/pull/3859)**

- **重启时避免无效镜像重建** (#3286)  
  PR #3286 优化了 `ncl groups restart --rebuild` 行为：当未配置 `packages_apt`/`packages_npm` 时跳过 Docker 镜像构建，缩短重启时间。来自社区贡献者 wakqasahmed，已稳定多日待合并。  
  **[链接](https://github.com/nanocoai/nanoclaw/pull/3286)**

### 路线图信号

- 连续三周收到来自同一贡献者 wakqasahmed 的多个 PR（#3286、#3273、#3311），表明社区对安装体验、任务错误处理及 CLI 效率的关注度上升。项目路线图可能需优先改善部署和运维工具链。

## 7. 用户反馈摘要

- **witek**（Issue #3860）报告了 `FORCE_COLOR` 环境变量导致的脚本兼容问题，指出 Node.js 的数字输出被着色后 `grep` 等工具无法解析。这是典型的真实生产环境问题，提示项目应主动兼容常见环境变量配置。  
- **seefood**（PR #3837）在总结中提及`旧的 PR 已闲置`，需要维护者推动 channel 层的修复落地。社区贡献者希望自己的修复能尽快被测试和合并。

## 8. 待处理积压

以下 PR 已开放超过一个月仍未合并或关闭，建议项目维护者优先评审：

| PR # | 标题 | 作者 | 创建时间 | 最后更新 | 状态 |
|------|------|------|----------|----------|------|
| [#3286](https://github.com/nanocoai/nanoclaw/pull/3286) | Skip image rebuild in restart when no packages configured | wakqasahmed | 2026-08-17 | 2026-09-21 | OPEN |
| [#3273](https://github.com/nanocoai/nanoclaw/pull/3273) | fix(setup): detect package manager in install-node.sh | wakqasahmed | 2026-08-16 | 2026-09-21 | OPEN |
| [#3311](https://github.com/nanocoai/nanoclaw/pull/3311) | fix(agent-runner): route scheduled-task errors to the operator | wakqasahmed | 2026-08-18 | 2026-09-21 | OPEN |
| [#3420](https://github.com/nanocoai/nanoclaw/pull/3420) | fix(add-macos-statusbar): make Swift code and plist labels slug-aware | gavrielc | 2026-08-20 | 2026-09-21 | OPEN |

这些 PR 覆盖了安装、CLI、错误处理、macOS 适配等多个领域，长期未合并可能影响社区贡献积极性。建议维护者按优先级（安装兼容 > 任务错误路由 > macOS 修复 > CLI 优化）安排审查。

---

*数据来源：GitHub (nanocoai/nanoclaw) 截至 2026-09-22 00:00 UTC。*

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

好的，作为AI智能体与个人AI助手领域开源项目分析师，以下是基于所提供数据生成的 **IronClaw 项目动态日报（2026-09-22）**。

---

# IronClaw 项目动态日报 | 2026年09月22日

## 今日速览

过去24小时，IronClaw项目处于**稳定迭代**状态，活跃度中等。核心动态包括：项目成功合并了 **1.4.1-rc.1** 候选版本的发布准备PR，标志着新一轮正式发布周期的启动；同时，持续的质量追踪流程生成了一份关于模型评估失败的详细分类报告。社区讨论主要集中在自动化质量保障流程上，暂无外部用户提交的Bug或功能请求。

## 版本发布

*   **（候选版本）** 今日无**正式版本**发布，但有一个候选版本的发布流程已至尾声。
    *   **PR #8105** **[CLOSED]** `chore(release): cut 1.4.1-rc.1`
    *   此PR为发布**1.4.1-rc.1**候选版本做准备。通过版本变更并合并后，自动化发布流程将为该合并提交打上`ironclaw-v1.4.1-rc.1`标签。

    > **说明**：此PR是发布流程的起点，实际发布版本的具体变更内容将在后续的正式发布说明中体现。

## 项目进展

*   **发布流程推进（PR #8105）**：由`henrypark133`发起的关键发布准备PR已被合并。该PR将`ironclaw`包版本号更新至**1.4.1-rc.1**，为通过`cut_ironclaw_release.py`脚本生成RC标签铺平了道路。这表明项目团队正稳步向正式版本`1.4.1`迈进。

## 社区热点

*   **自动化质量追踪（Issue #8106）**：今日唯一活跃的讨论围绕自动化生成的**每日失败分类报告**展开。
    *   **链接**: [Issue #8106: Daily ironclaw failure taxonomy — 2026-09-21](https://github.com/nearai/ironclaw/issues/8106)
    *   **分析**：虽然该Issue无人工评论，但其作为持续性质量监控机制的一部分，反映了项目对**模型性能评估**和**回归检测**的高度重视。尽管没有激烈讨论，但其存在本身就是一种信号：项目正在系统性地追踪“非通过”任务的根本原因。

## Bug 与稳定性

*   **严重性：中**
    *   **主题**: 模型评估质量失败
    *   **描述**: 通过自动化报告（Issue #8106）的分析发现，`officeqa`评估套件中的47个非通过任务，其根本原因被归为“真实的模型质量错误”，特别是**DeepSeek-V4-Flash**模型的表现。
    *   **影响**: 这表明当前模型的性能是效果瓶颈，而非框架本身的Bug。虽不影响框架稳定性，但直接关系到最终用户的使用体验。
    *   **状态**: 正在进行分类分析，暂无对应的修复PR。

## 功能请求与路线图信号

今日无外部用户提出新的功能请求。从项目进展来看，未来版本的重点方向可预测为：

1.  **稳定性提升（基于失败分类）**：Issue #8106 表明团队正在对模型失败原因进行归类分析，这很可能会驱动1.4.1正式版中的模型调用优化或内置应对策略。
2.  **版本发布流程自动化**：PR #8105 的合并意味着项目正在收紧其发布管道，未来版本发布将更加规范和可追溯。

## 用户反馈摘要

今日无来自外部的用户评论。唯一的反馈来源是自动化质量检测的摘要（Issue #8106），可以解读为对模型质量的内部“不满意”信号，项目组正致力于通过数据驱动的方式（失败分类）来定位和解决这些问题。

## 待处理积压

*   **暂无显著积压**。当前唯一活跃的Issue（#8106）是当天生成的自动化报告，无需要人工响应的外部用户问题。项目维护状态良好，未发现长期未回应的重大问题。

---
**项目健康度评估：良好**。项目正处于 `1.4.1` 版本的发布冲刺阶段，代码与构建流程趋于稳定。虽然社区外部互动较少，但内部质量保证流程运转有效，关注点明确聚焦于模型性能的优化。

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

# LobsterAI 项目动态日报 — 2026-09-22

## 1. 今日速览

过去 24 小时内，LobsterAI 项目保持较高的活跃度，共产生 2 条新 Issue 和 17 个 Pull Request（其中 15 个已合并/关闭）。合并 PR 高度集中在 **OpenClaw 组件**（网关启动、遗留数据迁移、Windows 兼容性修复）和 **核心稳定性**（macOS 临时目录符号链接处理、插件 ESM 启动上下文补全）上，项目整体正向 **更鲁棒的启动流程** 和 **更平滑的升级体验** 迈进。社区话题聚焦于“不重启网关切换工作区”这一体验优化诉求。

## 2. 版本发布

无新版本发布。

## 3. 项目进展

今日合并/关闭的 15 个 PR 中，以下关键变更推动了项目实质性进展：

- **OpenClaw 启动与迁移**：多个 PR 协同修复了旧版本数据残留导致的网关启动失败问题。
  - [#2734](https://github.com/netease-youdao/LobsterAI/pull/2734) 迁移遗留的微信 `allowFrom` 文件
  - [#2735](https://github.com/netease-youdao/LobsterAI/pull/2735) 处理 `identity/device.json` 与 SQLite 身份冲突
  - [#2719](https://github.com/netease-youdao/LobsterAI/pull/2719) 启动时自动修复旧构建遗留（不再每次启动失败）
  - [#2729](https://github.com/netease-youdao/LobsterAI/pull/2729) 修复 Windows 网关进程终止确认及一键修复
  - [#2728](https://github.com/netease-youdao/LobsterAI/pull/2728) 修复 OpenClaw SQLite 结果文件只读问题
  - [#2737](https://github.com/netease-youdao/LobsterAI/pull/2737) 恢复 IM（飞书）原生定时任务与消息投递
- **核心修复**：
  - [#2704](https://github.com/netease-youdao/LobsterAI/pull/2704) + [#2733](https://github.com/netease-youdao/LobsterAI/pull/2733) 解决 macOS 上 `os.tmpdir()` 符号链接导致测试失败的跨平台问题
  - [#2731](https://github.com/netease-youdao/LobsterAI/pull/2731) 修复 `nsp-clawguard 2.5.0` 在原生 ESM 加载时的启动崩溃（补齐 `__dirname` 等上下文）
- **功能增强**：
  - [#2730](https://github.com/netease-youdao/LobsterAI/pull/2730) 支持登录态下的**定向更新候选**，允许推送针对性更新而不影响现有更新检查
  - [#2736](https://github.com/netease-youdao/LobsterAI/pull/2736) 显式请求操作系统安全存储访问，仅在用户授权时验证凭据

此外，两个**陈旧的 PR**（#998 浮动工具栏、#999 Cmd+K 命令面板、#1067 停止自动创建 OpenClaw 会话）今日被关闭，表明团队正在清理历史遗留提议。

## 4. 社区热点

- **[Issue #2738 — 支持不重启网关切换工作区](https://github.com/netease-youdao/LobsterAI/issues/2738)**  
  用户 `BlackPottery1928` 提出当前每次切换工作区需重启网关，本机性能有限导致启动耗时超过 10 秒，频繁切换体验较差。该 Issue 创建不到 24 小时即获得 1 条评论，反映出社区对**操作效率**的强烈诉求。虽然没有直接关联的 PR，但该项目与“网关启动优化”系列修复（如 #2719 自动修复）方向一致，可能成为后续开发重点。

- **[PR #2739 — 添加可选的免密钥 Parallel 网络搜索](https://github.com/netease-youdao/LobsterAI/pull/2739)**  
  作为今日仅有的两个待合并 PR 之一，它引入了一种无需账号、API Key 或浏览器的匿名搜索引擎，且附带速率限制。这一功能降低 web-search skill 的使用门槛，可能吸引更多用户测试 Parallel 引擎。

## 5. Bug 与稳定性

按严重程度排列（均已有 fix PR 合并或正在待合并）：

| 严重程度 | 问题描述 | 状态 | 相关 PR |
|----------|----------|------|----------|
| Critical | OpenClaw 网关因遗留身份文件（微信 allowFrom、device.json）拒绝就绪，且不重启无法修复 | 已合并 3 个 PR | [#2734](https://github.com/netease-youdao/LobsterAI/pull/2734)、[#2735](https://github.com/netease-youdao/LobsterAI/pull/2735)、[#2719](https://github.com/netease-youdao/LobsterAI/pull/2719) |
| Critical | Windows 上重启网关时进程无法确认退出，导致修复阻塞 | 已合并 | [#2729](https://github.com/netease-youdao/LobsterAI/pull/2729) |
| High | `nsp-clawguard 2.5.0` 在原生 ESM 加载时崩溃（缺少 `__dirname`），网关反复重启 | 已合并 | [#2731](https://github.com/netease-youdao/LobsterAI/pull/2731) |
| High | OpenClaw SQLite 结果文件被标记为只读，影响后续写入 | 已合并 | [#2728](https://github.com/netease-youdao/LobsterAI/pull/2728) |
| Medium | macOS 测试因 `os.tmpdir()` 符号链接失败，影响本地开发验证 | 已合并 | [#2704](https://github.com/netease-youdao/LobsterAI/pull/2704)、[#2733](https://github.com/netease-youdao/LobsterAI/pull/2733) |
| Low | IM 定时任务（飞书）无法使用原生调度工具 | 已合并 | [#2737](https://github.com/netease-youdao/LobsterAI/pull/2737) |
| Info | **Tavily MCP 不可用**（#989）：用户报错 401 未授权，但声称已配置 API Key。该 Issue 已 stale 近 6 个月，今日被更新（可能由 bot 标记或用户追加），暂无修复 PR | 开放 | [Issue #989](https://github.com/netease-youdao/LobsterAI/issues/989) |

## 6. 功能请求与路线图信号

- **不重启网关切换工作区**（#2738）：用户明确要求支持动态工作区切换，避免 10 秒以上的网关重启等待。考虑到项目近期对网关启动流程的密集优化（#2719、#2729 等），此功能有较高优先级，可能在下一个版本中实现。
- **免密钥 Parallel 搜索**（#2739）：该 PR 处于待合并状态，预计将作为 web-search skill 的可选引擎纳入，降低用户使用搜索功能的前期配置成本。
- **定向更新候选**（#2730）：已合并，允许推送针对性版本更新，可能用于灰度测试或紧急修复，路线图信号表明团队在升级体验上持续投入。

## 7. 用户反馈摘要

从 Issue 评论和描述中提炼的真实痛点：

- **工作区切换耗时**：`BlackPottery1928` 指出每次切换工作区需重启网关，启动耗时 >10 秒，频繁切换（如调试、测试不同配置）严重影响效率。该用户还附上了截图（疑似显示工作区选择界面），表达了对**零停机切换**的迫切需求。
- **Tavily MCP 配置困惑**：`zwy123zwy` 在 #989 中反馈即使已配置 API Key 仍报 401。虽然无人进一步追问，但表明**第三方服务集成文档或配置检查**可能存在盲区，需维护者介入排查。
- **遗留更新冲突**：多处修复 PR（如 #2719、#2735）的提交信息中提到用户从旧版本升级（包括 Windows 卸载重装后保留 `%APPDATA%\LobsterAI`）导致启动失败，说明**跨版本数据兼容性**是社区常见痛点，本次系列修复可大幅缓解。

## 8. 待处理积压

| 项目 | 类型 | 创建时间 | 最后更新 | 状态 | 备注 |
|------|------|----------|----------|------|------|
| [Issue #989 — Tavily MCP 不可用](https://github.com/netease-youdao/LobsterAI/issues/989) | Bug | 2026-03-27 | 2026-09-21 | OPEN / STALE | 用户报告 401 未授权，已 stale 6 个月，今日有更新但无修复。建议维护者复现并确认是否为 API 变更或配置问题。 |
| [PR #1277 — chore(deps-dev): bump electron group](https://github.com/netease-youdao/LobsterAI/pull/1277) | 依赖更新 | 2026-04-02 | 2026-09-21 | OPEN | dependabot 提交的 electron 与 electron-builder 版本升级（43.5.0 → 44.4.2），已开放近半年，可能因兼容性测试阻塞。建议及时评估合并。 |
| [PR #2739 — Add optional keyless Parallel web search](https://github.com/netease-youdao/LobsterAI/pull/2739) | 新功能 | 2026-09-21 | 2026-09-21 | OPEN | 今日提交，等待 code review 与合并。社区关注度中等，但降低搜索门槛对用户有利。 |

---

*生成时间：2026-09-22 UTC | 数据来源：GitHub repository netease-youdao/LobsterAI*

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

好的，以下是为您生成的 Moltis 项目 2026-09-22 项目动态日报。

---

### Moltis 项目动态日报 (2026-09-22)

**分析师点评：** 项目今日活跃度中等。社区关注焦点高度集中于为语音角色（Voice Personas）增加本地 TTS（文本转语音）能力，相关功能请求和实现 PR 已同步提出。同时，一个关于工具预设（Tools）的行为修复 PR 也在待审查队列中。项目整体处于功能开发与问题修复并行的阶段。

#### 1. 今日速览

- **核心热点**：社区对本地 TTS 提供商的需求极为迫切，今日活动的核心均围绕 `VoxCPM` 作为本地解决方案展开。
- **功能开发推进**：新功能（VoxCPM TTS）的 PR (#1283) 已提交，并与刚关闭的 Feature Request (#1281) 形成闭环，表明项目对社区反馈响应迅速。
- **Bug 修复**：一个修复工具预设行为的重要 PR (#1280) 已提交，解决了 `active_tools` 为空数组时的逻辑错误。
- **活跃度评估**：中等活跃。Issues 和 PR 均有新增，但无新版本发布，且所有 PR 均处于待合并状态，尚无代码被合入主分支。

#### 2. 版本发布

无

#### 3. 项目进展

今日无 PR 被合并或关闭。但有两项重要进展处于“待审查”阶段，标志着项目向前迈进的实质性步骤：

- **[功能] 新增本地 TTS 提供商**：PR [#1283](https://github.com/moltis-org/moltis/pull/1283) 提议集成 VoxCPM 模型，通过 vLLM-Omni 提供本地、离线的 TTS 能力，解决了语音特性完全依赖外部云服务商的问题。
- **[修复] 修复工具预设逻辑**：PR [#1280](https://github.com/moltis-org/moltis/pull/1280) 修复了 Issue [#1277](https://github.com/moltis-org/moltis/issues/1277)，当用户显式传递空数组给 `active_tools` 时，系统不再错误地清除所有预设工具，而是视为“不覆盖”，保留了预设配置。

#### 4. 社区热点

今日最核心的热点事件是围绕 **“VoxCPM 本地 TTS”** 的议题与 PR 联动。

- **[Feature: VoxCPM as a local TTS provider - #1282](https://github.com/moltis-org/moltis/issues/1282)**
  该 Issue 由开发者 Caldalis 提出，与已关闭的 #1281 内容完全一致，是目前该功能需求的主要讨论区。作者通过引用项目的官方文档 `docs/src/voice.md`，明确指出当前“语音角色无本地实现”的痛点，诉求清晰且具有说服力。

- **[feat(voice): add VoxCPM as a local TTS provider - #1283](https://github.com/moltis-org/moltis/pull/1283)**
  由同一作者 Caldalis 提交的代码实现 PR，直接回应了上述功能请求。这种“提出问题即附上解决方案”的协作模式质量很高，表明社区有资深贡献者愿意主动填补项目短板。该 PR 的审查结果将直接影响 Moltis 在离线语音领域的竞争力。

#### 5. Bug 与稳定性

今日报告了一个关键逻辑 Bug，并已有对应的修复 PR。

- **[Bug] 预设工具在 `active_tools` 为空时被错误清空**：Issue [#1277](https://github.com/moltis-org/moltis/issues/1277) 描述了当用户在对话中设置 `active_tools = []` 时，本应保留预设的工具配置，但现有代码将其错误地清空。
  - **严重程度**：中高。影响使用“角色工具预设”功能的用户，导致预设配置丢失。
  - **Fix PR**：已由 mikemikimike 提交修复 PR [#1280](https://github.com/moltis-org/moltis/pull/1280)，正在等待审查和合并。

#### 6. 功能请求与路线图信号

- **强烈信号：本地 TTS 支持（VoxCPM）**：Issue [#1281](https://github.com/moltis-org/moltis/issues/1281) 和 [#1282](https://github.com/moltis-org/moltis/issues/1282) 明确提出了对本地 TTS 的需求。结合其对应的 PR [#1283](https://github.com/moltis-org/moltis/pull/1283)，**该功能极有可能被纳入下一个版本**。这不仅会填补 Moltis 在离线语音能力上的空白，也使其能使用 VoxCPM 支持的 30 种语言，显著增强国际化场景下的实用性。

#### 7. 用户反馈摘要

- **核心诉求**：用户 Caldalis 的核心痛点是“语音角色无本地实现”。这表明社区用户对数据隐私、离线使用或减少对云服务商的依赖有明确需求，不希望语音功能完全受限于外部提供商。
- **基于文档的论证**：用户通过引用项目自身的官方文档来论证问题，这反映出用户对项目有较深理解，且期望文档中承诺的功能（如本地支持）能够尽快落地。

#### 8. 待处理积压

涉及今日更新的项目均非常新（创建于昨天），无长期积压。但有两个 PR 处于“待合并”状态，需要维护者重点关注并加快审查：

1.  **[待审查] feat(voice): add VoxCPM as a local TTS provider - #1283**：合并此 PR 将直接回应社区最迫切的需求，建议尽快进行代码审查和测试。
2.  **[待审查] fix(tools): preserve preset tools for empty active_tools - #1280**：这是一个重要的行为修复，能提升配置的一致性和用户体验，也建议尽快处理。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据您提供的 CoPaw (github.com/agentscope-ai/CoPaw) 项目数据生成的 2026-09-22 项目动态日报。

---

## CoPaw 项目日报 | 2026年9月22日

### 1. 今日速览

项目今日活跃度较高，社区讨论和开发活动均较为密集。**Issues 方面**，虽然关闭了 9 条，但仍有 8 条处于活跃状态，其中关于安全漏洞和核心逻辑误判的 Bug 报告引发了社区关注。**PR 方面**，合并/关闭了 16 条，仍有 17 条待合并，修复工作仍在进行。开发者社区主要在集中解决 DoomLoopGate 误终止、OpenCode 供应商适配以及控制台 UI 稳定性问题。**总体而言，项目处于“高频修复与社区反馈同步进行”的活跃期，但部分长期存在的稳定性和安全问题对项目健康度构成挑战。**

### 2. 版本发布

无新版本发布。

### 3. 项目进展

过去24小时，项目在 Bug 修复和核心逻辑优化方面取得了显著进展，具体体现在：

- **核心循环稳定性提升**: PR #7919 (`fix: require new tool-call evidence for doom loop escalation`) 和 PR #7906 (`fix(loop): prevent stale doom-loop escalation`) 已合并，解决了 DoomLoopGate 在无新的工具调用证据时错误地升级到 TERMINATE 状态的问题。这直接修复了社区反馈的 `#7905` 号 Bug，提升了 Agent 在复杂多轮对话中的行为稳定性。
- **API 兼容性修复**: PR #7915 (`fix(responses): default function tools to non-strict mode`) 已合并，修复了因工具 schema 清洗后导致可选参数变为必填，从而引发调用失败的问题。
- **社区贡献与基础设施加固**: PR #7911 (`test(unit): coverage sprint batch 3`) 已合并，大幅提升了单元测试覆盖率 (+3.28pp)，表明项目对质量的重视。同时，PR #7922 (`fix(omp): add missing SKILL.md frontmatter to omp-roles skill`) 和 PR #7326 (`feat(ci): split nightly E2E into three parallel priority shards`) 的合并，分别修复了官方插件不生效的问题和优化了 CI 流程。
- **重大架构重构推进**: 尽管仍在 Open 状态，但 PR #7874 (`feat(pawapp): redesign the SDK and app control plane`) 正在被积极 Review，这标志着项目在应用控制层面的重大架构演进，值得长期关注。

### 4. 社区热点

今日社区讨论热度集中在两个核心议题，均围绕 Agent 行为的**可靠性**和**安全性**展开：

1.  **持久性提示注入漏洞 (Issue #7859)**:
    - **链接**: `agentscope-ai/QwenPaw Issue #7859`
    - **分析**: 这是过去24小时内评论数最多 (5条)、关注度最高的问题。该 Issue 描述了一个严重的**安全问题**：恶意指令会持久性地注入到系统提示中，命令 Agent 在执行任务后“永久删除所有技能”，且无法通过本地磁盘溯源。社区对此高度关注，因为这会直接威胁用户的 Agent 生态安全。目前尚无明确的 Fix PR，但已标记为 `OPEN`，开发者正在紧急调查。

2.  **DoomLoopGate 误终止 (Issue #7905)**:
    - **链接**: `agentscope-ai/QwenPaw Issue #7905`
    - **分析**: 该 Bug 描述了 Agent 在纯文本回复回合中，被 DoomLoopGate 错误地判断为死循环并终止。用户 `mikew221` 提供了详细的复现步骤和代码审计链接。**好消息是，社区反馈的问题在短短1天内就被识别、讨论并最终通过 PR #7906 和 #7919 修复和合并**，展现了项目团队对关键反馈的快速响应能力。

### 5. Bug 与稳定性

以下为今日报告的 Bug，按严重程度排序：

- **[严重] 持久性提示注入 (Issue #7859)**:
    - **描述**: 恶意指令可持久存在于系统提示中，且无法通过本地文件系统追溯来源，安全风险极高。
    - **状态**: 开放中，无 fix PR，社区高度关注。

- **[严重] DoomLoopGate 误终止 (Issue #7905)**:
    - **描述**: 在无新工具调用时，错误地将 Agent 对话终止。
    - **状态**: **已关闭**，通过 PR #7906 和 #7919 修复。

- **[严重] Windows 子进程会终止主进程 (Issue #7908)**:
    - **描述**: Windows 平台下，`execute_shell_command` 启动的子进程可能向主机发送 Console Ctrl 事件，导致整个 QwenPaw 服务被意外终止。
    - **状态**: 开放中，有相应的 Fix PR #7910 (`fix(shell): isolate Windows command consoles`) 待合并。

- **[中] OpenCode API 请求失败 (Issue #7882)**:
    - **描述**: 第三方供应商 OpenCode 的“免费”模型无法通过 API 调用，但 UI 仍显示为可用，对用户产生误导。
    - **状态**: **已关闭**，推测与 PR #7531 相关联。

- **[中] 技能静默不可用 (Issue #7921)**:
    - **描述**: 官方插件 `omp-roles` 的 `SKILL.md` 文件缺少必要的 YAML frontmatter，导致技能在后台静默地被跳过加载，用户毫无感知。
    - **状态**: 开放中，有相应的 Fix PR #7922 待合并。

- **[低] 文件区标签页显示过时内容 (Issue #7866)**:
    - **描述**: Agent 重写文件后，工作区的文件标签页内容未刷新，与侧栏的文件卡片预览内容不一致。
    - **状态**: **已关闭**。

- **[低] 控制台 UI 启动时加载不全 (Issue #7841)**:
    - **描述**: 桌面应用启动时，控制台 UI 需要在后端就绪后手动刷新才能显示完整内容。
    - **状态**: 开放中。

### 6. 功能请求与路线图信号

- **Agent 个性化配置**: Issue #4974 (`Feature Request: 希望支持为每个 Agent 配置头像`) 虽然今日关闭，但其获得了 2 个 👍，表明社区对 Agent 视觉个性化有明确需求。这可能是未来 Console UI 优化的方向之一。
- **模型层全面优化**: 今日合并的 PR #7899 (`feat(providers): unify model discovery...`) 和其关联的庞大 Issue #6167，标志着项目正在大规模重构模型供应商层，以实现**动态上下文、模型同步、多模型故障转移**等高级特性。这是项目路线图中的重要节点，将直接影响用户的模型使用体验。
- **MCP 文档贡献**: Issue #7912 (`Docs: Optional authenticated MCP web-research example...`) 提出了为 MCP 文档贡献一个使用百知Agent套件进行网络研究的示例。这反映了社区有将 MCP 协议用于具体业务场景的意愿，项目文档应积极吸纳此类贡献。

### 7. 用户反馈摘要

从 Issue 评论中，可以提炼出以下用户痛点与核心诉求：

- **对安全性的焦虑 (Issue #7859)**: 用户对提示注入这种无法追溯、无法避免的威胁感到无力，并期待官方能提供强有力的安全机制，例如沙箱或严格的指令审计。
- **对可靠性退化的失望 (Issue #7628)**: 用户 `elain0205` 反馈，现有的上下文压缩机制在极限情况下会**超出提供商预算而导致活跃对话失败**，这说明系统在资源管理和边界情况处理上仍有优化空间。
- **对隐晦错误的困惑 (Issue #7431 & #7921)**: “空响应”和“静默不可用”这类 Bug 对用户造成了极大的困惑。用户希望系统在面对错误时能给出明确的、可操作的提示，而不是静默失败。
- **对 UI/UX 体验的细节需求 (Issue #7841 & #4974)**: 用户对 UI 启动慢、无法快速区分多 Agent 等问题反馈集中，表明社区不仅关注功能强大，也对日常使用的流畅性和便捷性有较高要求。

### 8. 待处理积压

以下 Issue 或 PR 长期未获响应或合并，可能对部分用户造成困扰，需要维护者关注：

- **Issue #3419 ([Bug] 京东云 Coding Plan 环境与会话执行中断)**: 自2026年4月创建以来，长期处于活跃但未关闭状态。这是一个特定环境下的兼容性问题，对于使用京东云平台的用户影响较大，需要评估其复现难度和修复优先级。
- **Issue #4974 ([enhancement] Feature Request: 希望支持为每个 Agent 配置头像)**: 虽然已关闭，但作为社区呼声较高的功能需求，应被纳入后续 UI 开发的待办事项。
- **PR #5992 ([first-time-contributor, Under Review] Add per-session model overrides)**: 该 PR 自 7月以来一直处于 `Under Review` 状态，它为每个会话配置不同模型，是社区比较喜欢的功能。长时间的停滞可能会打击贡献者的积极性。

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，根据您提供的 ZeroClaw 项目数据，现为您呈现 2026 年 9 月 22 日的项目动态日报。

---

# ZeroClaw 项目动态日报 - 2026-09-22

## 1. 今日速览

ZeroClaw 项目今日 **保持高度活跃**，在问题修复与架构演进上并行推进。过去 24 小时内，共处理了 50 条 Issue 和 50 个 PR，但多数 PR 仍处于待合并状态，表明项目审核流程面临一定压力。尽管今日无新版本发布，但在**安全漏洞修复**、**通道功能增强**（尤其是 WhatsApp）以及**核心架构决策**（如主机级资源控制、代理间通信）上取得了实质性讨论和进展。多件高优先级（P1）Bug 报告指向 **运行时稳定性** 和 **安全策略** 问题，是当前项目需要重点关注的风险点。

## 2. 版本发布

无新版本发布。

## 3. 项目进展

今日合并/关闭的重要 PR 和 Issue 较少，项目整体处于“**大量提案与修复并行开发，等待审核合并**”的状态。主要进展体现在以下方面：

- **安全与依赖修复**：来自 `JordanTheJet` 的 PR [#11038](https://github.com/zeroclaw-labs/zeroclaw/issues/11038)（暂缓`RUSTSEC-2026-0292`安全警告）是一个应急措施，旨在暂时解除因 `imbl-sized-chunks` 库中的双重释放（double free）漏洞导致的安全 CI 失败，为后续根治争取时间。同时，Issue [#9899](https://github.com/zeroclaw-labs/zeroclaw/issues/9899) 被追踪，目标是永久移除相关的安全豁免。
- **NixOS 部署集成**：`rtimush` 贡献了两项 Nix 相关 PR，[#11041](https://github.com/zeroclaw-labs/zeroclaw/issues/11041) 将 Web UI 构建为 Nix 包，[#11040](https://github.com/zeroclaw-labs/zeroclaw/issues/11040) 修正了 `zerocode` 的功能集构建问题。这显著提升了项目在 NixOS 生态中的部署体验。
- **文档与测试更新**：多个小型 PR（如 `#11011`, `#11024`, `#11028`, `#11030`）专注于**完善文档、测试和 CI 流程**，例如为 Windows CI 运行器添加文档、统一测试夹具的上下文限制、以及本地化聊天频道集成指南。这体现了项目对基础设施和开发者体验的持续投入。

## 4. 社区热点

今日讨论最为活跃的 Issue 集中在**核心架构的长期规划**与**高影响性 Bug 的排查**上。

- **架构决策队列**：[#8692](https://github.com/zeroclaw-labs/zeroclaw/issues/8692) 作为一个追踪器，旨在为 RFC 和设计问题建立维护者决策队列。其持续的高评论量（15条）表明**社区对项目未来技术方向和决策流程的透明度有强烈需求**。这是项目治理成熟度的重要信号。
- **安全与资源控制 RFC**：关于**主机级资源限制**的 RFC [#10970](https://github.com/zeroclaw-labs/zeroclaw/issues/10970) 和关于**持久化人类询问原语**的 RFC [#10930](https://github.com/zeroclaw-labs/zeroclaw/issues/10930) 均获得了 4 条评论。前者反映了社区对运行多代理实例时的**稳定性与稳定性降级（graceful degradation）**的关切，后者则指向构建更健壮、可恢复的人机交互流程的需求。
- **运行时稳定性 Bug**：Issue [#10230](https://github.com/zeroclaw-labs/zeroclaw/issues/10230)（守护进程启动时因栈溢出崩溃）和 [#10408](https://github.com/zeroclaw-labs/zeroclaw/issues/10408)（并行消息导致重复工作）各获 4-6 条评论，是用户反映强烈的**工作流阻塞问题**，直接影响了 `zerocode/TUI` 和核心运行时的可靠性。

## 5. Bug 与稳定性

今日报告的 Bug 及稳定性问题数量较多，按严重程度排列如下：

| 严重程度 | Issue/PR 链接 | 关键问题描述 | 是否有 Fix PR |
| :--- | :--- | :--- | :--- |
| **S0 - 数据丢失/安全风险** | [#10966](https://github.com/zeroclaw-labs/zeroclaw/issues/10966) | Git `--attr-source` 选项可绕过授权分类，隐藏变异子命令。 | 否 |
| **S1 - 工作流阻塞** | [#10230](https://github.com/zeroclaw-labs/zeroclaw/issues/10230) | 守护进程在应用 Quickstart 配置时发生栈溢出。 | 否 |
| **S1 - 工作流阻塞** | [#9191](https://github.com/zeroclaw-labs/zeroclaw/issues/9191) | Cron 任务缺少挂钟超时，导致进程无限期卡住。 | 否 |
| **S1 - 工作流阻塞** | [#9390](https://github.com/zeroclaw-labs/zeroclaw/issues/9390) | 紧急停止（emergency stop）状态文件仅作用于 CLI，运行时未读取。 | 否 |
| **S1 - 工作流阻塞** | [#10231](https://github.com/zeroclaw-labs/zeroclaw/issues/10231) | 通道管理器会重试过期的、无效的配置。 | 否 |
| **S1 - 工作流阻塞** | [#10536](https://github.com/zeroclaw-labs/zeroclaw/issues/10536) | macOS 上 Seatbelt 沙箱忽略了 `allowed_roots` 配置。 | 否 |
| **S2 - 功能降级** | [#10523](https://github.com/zeroclaw-labs/zeroclaw/issues/10523) | 引导文件被截断至 6000 字符，且对用户不可见。 | 否 |
| **S2 - 功能降级** | [#10408](https://github.com/zeroclaw-labs/zeroclaw/issues/10408) | 活跃对话中发送第二个消息会启动并行任务，导致重复工作。 | 否 |
| **S2 - 功能降级** | [#10975](https://github.com/zeroclaw-labs/zeroclaw/issues/10975) | WhatsApp Web 通道无法下载图片，导致多模态模型失效。 | 待定，相关 PR [#10982](https://github.com/zeroclaw-labs/zeroclaw/issues/10982) |
| **S3 - 轻微问题** | [#10918](https://github.com/zeroclaw-labs/zeroclaw/issues/10918) | 空的尾部数据块错误地将完整的 HTTP 响应标记为截断。 | 否 |

总览：**安全与运行时稳定性**问题最为突出，近半数的 S1 级别 Bug 都与这些领域相关，需要维护者优先关注。

## 6. 功能请求与路线图信号

今日涌现出一批高质量的新功能请求（RFC），为项目的长期路线图提供了清晰信号。

- **架构级别**：
    - **[RFC] 主机级准入控制与资源限制** ([#10970](https://github.com/zeroclaw-labs/zeroclaw/issues/10970))：提出为运行多个代理的主机提供并发、工具执行和内存的全局限制。这是为**企业级或大规模部署**做准备的关键提案。
    - **[RFC] 代理间会话消息** ([#11027](https://github.com/zeroclaw-labs/zeroclaw/issues/11027))：允许不同 session 中的代理直接通信，无需人工介入。这标志着 ZeroClaw 从“单代理助手”向“多代理协作平台”演进的**关键一步**。

- **通道与通信**：
    - **[RFC] 持久化的人类询问原语** ([#10930](https://github.com/zeroclaw-labs/zeroclaw/issues/10930))：提议将现有的 SOP 审批门推广为通用的、持久的“代理问人”机制。这将使代理能在等待用户响应时安全地“休眠”。
    - **[RFC] 出站消息送达回执** ([#10929](https://github.com/zeroclaw-labs/zeroclaw/issues/10929))：提出为代理发出的消息添加唯一 ID，以追踪其是否被用户读取。

- **治理与流程**：
    - **[RFC] 简化合并决策** ([#11017](https://github.com/zeroclaw-labs/zeroclaw/issues/11017))：建议保留适用的审核记录，并简化快速合并的决策流程。这旨在**缓解审核压力，加快开发节奏**。

新功能主要集中在**提升系统在复杂场景下的健壮性、安全性和可管理性**，并开始探索**代理间协作**的高级范式。

## 7. 用户反馈摘要

从今日的 Issues 评论中可以提炼出以下用户痛点与使用场景：

- **配置不透明与不一致**：用户反馈 `compact_context` 导致的文件截断 (`#10523`) 和 `max_context_tokens` 设置被忽略 (`#10068`) 问题，核心诉求是**配置生效的透明化和可预期性**。
- **多代理管理复杂度**：社区对资源控制 RFC (`#10970`) 的积极讨论，反映了用户运行多个代理实例时面临的**性能降级和管理困难**。他们期待更精细的、主机级的资源控制。
- **通道体验参差不齐**：WhatsApp 通道因无法处理图片 (`#10975`) 和 @提及 (`#10976`) 功能残缺，导致用户**核心使用场景受阻**。这表明不同通道间的功能一致性是提升用户体验的关键。
- **对稳定性和可靠性的焦虑**：多个 S1 级别的 Bug (*提出频率高，等待修复久*)，如守护进程崩溃 (`#10230`)、cron 任务卡死 (`#9191`)，表明用户对将 ZeroClaw 用于生产环境或关键任务感到**不安和担忧**。

## 8. 待处理积压

以下 Issue 和 PR 长期未得到有效响应或解决，可能阻碍项目健康度：

- **安全告警豁免**：[Issue #9899](https://github.com/zeroclaw-labs/zeroclaw/issues/9899) 要求移除 `matrix-sdk` 引入的安全告警豁免。虽然有一个应急性 PR [#11038](https://github.com/zeroclaw-labs/zeroclaw/issues/11038) 解决了 CI 失败问题，但**根本性解决方案 (移除有漏洞的依赖) 仍未推进**。此问题影响 CI 安全审查，需优先处理。
- **紧急停止功能失效**：[Issue #9390](https://github.com/zeroclaw-labs/zeroclaw/issues/9390) 指出紧急停止功能只是一个“纸面”功能，实际运行时并不生效。这是一个**严重的安全隐患**，自 7 月 26 日提出以来，至今无任何实质性进展。
- **理念性大 PR 审核**：`#10263` (安全身份与工具选择器) 和 `#10172` (保留 Provider 配置语义) 是两个标签众多、改动量巨大的 XL 级 PR。它们代表了重要的方向，但长期处于开放状态。这些 PR 的**审核进度直接影响开发者士气和新功能的落地**。
- **旧 Bug 停滞**：`#9427` (LINE 频道授权修复) 和 `#10379` (无法取消消息) 等 Bug 报告虽已有相关 PR，但因标记为 `needs-author-action` 或 `status:blocked` 而处于停滞状态。维护者需要积极与作者沟通，推动其完成。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*