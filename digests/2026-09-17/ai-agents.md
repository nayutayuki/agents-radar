# OpenClaw 生态日报 2026-09-17

> Issues: 500 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-09-17 00:52 UTC

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

# OpenClaw 项目日报 — 2026-09-17

---

## 1. 今日速览

过去 24 小时项目极度活跃，共产生 **500 条 Issue 更新**（新开/活跃 323，关闭 177）和 **500 条 PR 更新**（待合并 287，已合并/关闭 213），社区参与度与修复节奏均处于高位。然而，**P0/P1 级稳定性问题密集爆发**，尤其是 **2026.9.3 → 2026.9.4 更新流程在多平台上出现阻塞性失败**，同时遗留的内存泄漏、子进程僵尸化、网关启动超时等问题仍在持续影响用户。虽然大量修复 PR 已进入待合状态，但项目当前整体健康度偏低，**用户升级信心受到冲击**。

---

## 2. 版本发布

**无新版本发布**。上一个版本 2026.9.4 仍为最新，但已有多个针对该版本的紧急修复 PR 在审查中。

---

## 3. 项目进展

今日共有 **213 个 PR 被合并或关闭**，涉及领域包括：

- **更新/回滚可靠性**：`#145169`（大 XL）修复了失败更新后回滚时保留较新数据的问题，关联多个 Doctor 恢复场景。
- **WebChat 内部会话**：`#148360` 修复了后台命令完成未在 WebChat 中产生回复的问题。
- **大舰队性能**：`#150223` 修复了 632-agent 规模下模型准备阻塞主线程导致健康检查超时的问题，直接关联 `#149538`。
- **插件状态管理**：`#150274` 释放了已废弃插件的回调，并减少元数据检查时的临时分配。
- **渠道兼容性**：`#150416` 修复了 Microsoft Teams 频道中去抖导致多线程回复被合并的问题；`#147886` 使飞书渠道接受文档中标记的 Markdown 表格模式。
- **配置与类型安全**：多个重构 PR（如 `#150404`、`#150405`、`#150415`）将配置 DTO 与 Zod schema 对齐，减少运行时类型漂移。

> 部分关键关闭的 Issue 也反映了进展：例如 `#146265`（AsyncWorkScope 生命周期 bug）已关闭，`#145929`（认证锁死）已关闭，`#149198`（stale_lane_task 过早释放）已关闭。

---

## 4. 社区热点

| 排名 | Issue / PR | 评论数 | 摘要 | 链接 |
|------|------------|--------|------|------|
| 1 | [#97616] | 30 | **僵尸子进程泄漏**，hook/tool 子进程未回收，运行时退化 | [链接](https://github.com/openclaw/openclaw/issues/97616) |
| 2 | [#91588] | 25 | **网关内存泄漏**，RSS 从 350MB 涨至 15.5GB，OOM 反复崩溃 | [链接](https://github.com/openclaw/openclaw/issues/91588) |
| 3 | [#144911] | 24 | **MCP 服务超时导致未捕获 Promise 拒绝**，整个网关崩溃 | [链接](https://github.com/openclaw/openclaw/issues/144911) |
| 4 | [#111897] | 19 | **并发运行时副本消息去重失败**，同一 session lane 下重复回复 | [链接](https://github.com/openclaw/openclaw/issues/111897) |
| 5 | [#150201] | 14 | **Windows 更新快照失败**，SQLite 检查超时，阻断升级 | [链接](https://github.com/openclaw/openclaw/issues/150201) |

**社区诉求分析**：用户最关心的是 **持续运行稳定性**（内存泄漏、OOM、子进程泄漏）和 **升级可靠性**（多个平台更新失败）。这些高频评论 Issue 均带有 `P0`/`P1` 和 `crash-loop` 标签，说明问题已严重影响生产使用，社区期待维护者优先排查。

---

## 5. Bug 与稳定性

按严重程度排列（P0 > P1 > P2），标记是否已有对应修复 PR：

| 优先级 | Issue | 标题 | 影响 | 已有 Fix PR |
|--------|-------|------|------|-------------|
| **P0** | [#150201](https://github.com/openclaw/openclaw/issues/150201) | Windows 更新快照失败，SQLite 超时 | 阻断 Windows 用户升级至 2026.9.4 | 无（需关联） |
| **P0** | [#149538](https://github.com/openclaw/openclaw/issues/149538) | 网关就绪后无响应，每次 /health 超时（632-agent） | 服务完全不可用 | 关联 `#150223`（已提交） |
| **P0** | [#146394](https://github.com/openclaw/openclaw/issues/146394) | 更新失败 `global-install-failed`（linux/arm64） | 升级阻塞 | 无 |
| **P0** | [#144739](https://github.com/openclaw/openclaw/issues/144739) | npm 更新从 2026.9.3 到 2026.9.4 时使用 schema-17 候选状态 | 升级后数据迁移冲突 | 无 |
| **P0** | [#70903](https://github.com/openclaw/openclaw/issues/70903) | 持久化 provider cooldown 在恢复后仍阻断用户（stale） | 长时间无法使用 AI 服务 | 无 |
| **P0** | [#148681](https://github.com/openclaw/openclaw/issues/148681) | 更新失败 `finalize:doctor`（linux/x64） | 升级无法完成 | 无 |
| **P1** | [#97616](https://github.com/openclaw/openclaw/issues/97616) | 子进程僵尸累积导致运行时退化 | 性能下降 | 无 |
| **P1** | [#91588](https://github.com/openclaw/openclaw/issues/91588) | 网关内存泄漏至 OOM | 服务反复崩溃重启 | 无 |
| **P1** | [#144911](https://github.com/openclaw/openclaw/issues/144911) | MCP 超时导致未捕获异常 | 进程崩溃 | 无 |
| **P1** | [#111897](https://github.com/openclaw/openclaw/issues/111897) | 并发运行时重复回复 | 消息冗余 | 无 |
| **P1** | [#148707](https://github.com/openclaw/openclaw/issues/148707) | 回复丢失 `no active tool authority snapshot`（2026.9.4 回归） | 用户消息丢失 | 无 |
| **P1** | [#137332](https://github.com/openclaw/openclaw/issues/137332) | requester-settle 批次永久重试 | 子任务永远无法完成 | 无 |
| **P2** | [#123009](https://github.com/openclaw/openclaw/issues/123009) | Codex 订阅每五分钟检查阻塞 | 限制频率异常 | 无 |
| **P2** | [#146004](https://github.com/openclaw/openclaw/issues/146004) | 子代理完成触发非预期的仪表盘心跳 | 测试/监控误报 | 无 |

> 注：多个 P0 更新失败问题均指向 2026.9.4 候选版本的 Doctor 迁移流程缺陷，维护者已开跟踪 Issue `#145252` 协调修复。

---

## 6. 功能请求与路线图信号

近期用户提出的功能需求集中在 **部署灵活性与运维简化**：

| Issue | 标题 | 当前状态 | 关联 PR/路线图 |
|-------|------|----------|----------------|
| [#86881](https://github.com/openclaw/openclaw/issues/86881) | **Gateway‑lite 模式**：不加载 AI harness 的轻量部署 | **已关闭**（stale，但有维护者讨论） | 无直接 PR，但暗示项目考虑拆分 |
| [#44309](https://github.com/openclaw/openclaw/issues/44309) | **单向调度模式**：A2A 只发不收，避免 ping‑pong | OPEN / stale | 无 |
| [#49259](https://github.com/openclaw/openclaw/issues/49259) | Dashboard 中清理孤立会话 | OPEN / stale | 无 |
| [#76247](https://github.com/openclaw/openclaw/issues/76247) | 原生 dispatch 落地 ACK / receiver-entry 遥测 | OPEN / stale | 无 |
| [#44291](https://github.com/openclaw/openclaw/issues/44291) | 为 Windows 贡献者添加 PowerShell 测试覆盖 | OPEN / stale | 无 |

以上功能多数处于 **stale** 状态，未进入近期开发队列。短期内项目仍以 **稳定性修复** 为首要任务。

---

## 7. 用户反馈摘要

从 Issue 评论与报告中提炼的真实用户痛点：

- **更新恐惧**：多位用户报告从 2026.9.3 升级到 2026.9.4 失败，回滚或重试均无效（参考 `#146394`、`#150201`、`#144739`）。用户在评论中表达了对“每次更新都心惊胆战”的无奈。
- **生产环境不可用**：632-agent fleet 用户反馈网关启动后立即无响应（`#149538`），导致整个智能体农场瘫痪。另一用户报告内存泄漏导致 OOM 每 2-3 天发生一次（`#91588`），必须手动重启。
- **消息丢失与重复**：Telegram、iMessage 用户发现回复重复或部分丢失，影响日常对话体验（`#111897`、`#143632`、`#148707`）。
- **子进程泄漏**：长期运行用户发现 `openclaw` 进程下堆积数百个僵尸进程，导致系统 load 升高（`#97616`）。
- **MCP 集成脆弱**：第三方 MCP 服务器初始化超时即拖垮整个网关，社区呼吁更健壮的隔离和超时处理（`#144911`）。

**满意点**：部分用户在遗留 Issue 中感谢了维护者对特定场景的修复（如 `#90098` 大附件处理），但整体满意度因近期回归问题而下降。

---

## 8. 待处理积压

以下为长期未响应或等待维护者审查的重要 Issue / PR：

| 类型 | 编号 | 标题 | 优先级 | 上次更新 | 备注 |
|------|------|------|--------|----------|------|
| Issue | [#70903](https://github.com/openclaw/openclaw/issues/70903) | 持久化 provider cooldown 阻断用户 | **P0** | 2026-09-16 | stale，未分配 |
| Issue | [#111897](https://github.com/openclaw/openclaw/issues/111897) | 并发运行时重复回复 | **P1** | 2026-09-16 | 等待维护者审查 |
| Issue | [#136311](https://github.com/openclaw/openclaw/issues/136311) | 内存索引锁永久占用，重建失败 | **P1** | 2026-09-16 | 等待产品决策 |
| Issue | [#123009](https://github.com/openclaw/openclaw/issues/123009) | Codex 订阅阻塞每五分钟 | **P2** | 2026-09-16 | 等待产品决策/安全审查 |
| Issue | [#119411](https://github.com/openclaw/openclaw/issues/119411) | 文件监视器从不重新索引 | **P1** | 2026-09-16 | 无 assignee |
| PR | [#91245](https://github.com/openclaw/openclaw/pull/91245) | 恢复 channel turn 别名 | **P1** | 2026-09-17 | 等待作者响应（⏳） |
| PR | [#129393](https://github.com/openclaw/openclaw/pull/129393) | 排除脚手架测试文件不发布 | **P2** | 2026-09-17 | 等待维护者查看 |
| PR | [#115670](https://github.com/openclaw/openclaw/pull/115670) | `claws add` 支持现有工作目录 | **P2** | 2026-09-17 | 等待维护者查看 |

建议维护团队优先处理 **P0 更新失败类**（`#150201`、`#146394`、`#148681`）和 **内存泄漏/僵尸进程**（`#91588`、`#97616`），以恢复社区信任。

---

**日报生成时间**：2026-09-17 23:59 UTC  
**数据来源**：OpenClaw GitHub 仓库（openclaw/openclaw）  
**分析师**：AI 智能体与个人 AI 助手领域开源项目分析师

---

## 横向生态对比

# 2026-09-17 个人 AI 助手开源生态横向对比分析报告

---

## 1. 生态全景

个人 AI 助手与自主智能体开源生态正处于 **“快速迭代与稳定性巩固并存的矛盾期”**。头部项目（OpenClaw、NanoBot、CoPaw、ZeroClaw）每日产生数百条 Issue/PR，社区参与度极高，但伴随而来的是 **P0/P1 级稳定性问题密集爆发**——内存泄漏、子进程僵尸、升级阻塞、多会话串扰成为跨项目共性问题。与此同时，中小型项目（Moltis、PicoClaw、NullClaw）保持稳定维护节奏，在特定方向（如斜杠命令、移动端、沙箱粒度）稳步推进。整体而言，生态正从“功能堆叠”转向“质量优先”，用户对生产环境可用性的诉求已压倒对新功能的期待。

---

## 2. 各项目活跃度对比

| 项目名 | 24h Issues 更新 | 24h PR 更新 | 今日 Release | 健康度评估 |
|--------|----------------|------------|-------------|------------|
| **OpenClaw** | 500（新开/活跃 323，关闭 177） | 500（待合 287，合并/关闭 213） | 无 | 🔴 偏低：P0/P1 崩溃频发，升级受阻 |
| **NanoBot** | 未单独统计（但 20 个 PR 更新） | 20 个 PR（5 合并/关闭） | 无 | 🟡 中等：社区响应快，但多会话串扰未修 |
| **Hermes Agent** | 50（关闭 39） | 50（关闭 18） | 无 | 🟡 中等：Kanban 问题集中，消息重复严重 |
| **NanoClaw** | 0（新增） | 34（合并/关闭 9，待合 25） | 无 | 🟢 较高：大规模重构推进，CI 挂起受控 |
| **PicoClaw** | 0（关闭 1） | 0（合并 2 个遗留 PR） | 无 | 🟢 稳定：低活跃但遗留 Bug 清理积极 |
| **NullClaw** | 1（关闭 1） | 0 | 无 | 🟢 稳定：极低活跃，无新问题 |
| **LobsterAI** | 9（均关闭） | 18（均合并/关闭） | 无 | 🟢 较高：集中清理大量积压，修复涵盖并发/UI |
| **CoPaw (QwenPaw)** | 25（新开/活跃 13） | 37（待合 25） | 无 | 🟡 中等：重大功能 PR（Hub/语音）推进，但子代理超时等 Bug 未解 |
| **ZeroClaw** | 36 | 50（待合 47） | 无 | 🟡 中等：PR 积压严重，但代码质量（反 Slop）行动积极 |
| **Moltis** | 1（关闭）| 2（待合） | 无 | 🟢 稳定：斜杠命令功能合并，沙箱粒度 PR 待审 |
| **IronClaw** | 0 | 0 | 无 | 🟢 无活动 |
| **TinyClaw** | 0 | 0 | 无 | 🟢 无活动 |
| **ZeptoClaw** | 0 | 0 | 无 | 🟢 无活动 |

> **说明**：健康度评估基于 Issue/PR 密度、严重 Bug 占比、合并效率综合判断。

---

## 3. OpenClaw 在生态中的定位

- **核心参照地位**：OpenClaw 社区规模遥遥领先（单日 500+ Issue/PR），是事实上的“主参考实现”。其他项目（如 LobsterAI、NanoClaw）的修复 PR 明确提及“参考 OpenClaw 的 Doctor 迁移流程”或“共享状态 schema 对齐”。
- **技术路线差异**：OpenClaw 采用 **Doctor 迁移机制** 处理版本升级，复杂度高但意图覆盖多平台；而 NanoBot 和 Moltis 更倾向于轻量、无侵入的配置演化。当前 OpenClaw 的 P0 升级失败问题（`global-install-failed`、SQLite 超时）正暴露该路线的脆弱性。
- **优势与短板**：OpenClaw 的渠道兼容性（飞书、Teams、Telegram、iMessage 等）和 Agent 规模（632-agent 舰队）是其核心壁垒；但正因规模过大，内存泄漏、子进程泄漏、MCP 超时等稳定性问题成为“成长的阿喀琉斯之踵”，用户信心受冲击。
- **社区对比**：OpenClaw 的 PR 合并/关闭数（213）高于 NanoBot（5）和 ZeroClaw（3），但待合 PR 也最多（287），说明维护者资源紧张，吞吐量已到瓶颈。

---

## 4. 共同关注的技术方向

| 技术方向 | 涉及项目 | 具体诉求 |
|----------|----------|----------|
| **多会话隔离与并发安全** | OpenClaw、NanoBot、Hermes Agent、CoPaw | 共享内存/工作区污染、会话串扰、消息重复分发、响应丢失 |
| **MCP 集成健壮性** | OpenClaw、Moltis、CoPaw | 超时导致进程崩溃、启动失败永不重试、结构化内容重复 |
| **内存泄漏与资源回收** | OpenClaw、CoPaw、ZeroClaw | 网关 RSS 涨至 15GB+、子进程僵尸、容器 OOM、长连接堆积 |
| **更新/部署可靠性** | OpenClaw、NanoClaw、LobsterAI | 升级快照失败、回滚后保留较新数据、CI 挂起（Bun spawnSync） |
| **沙箱/容器隔离粒度** | Moltis、CoPaw、ZeroClaw | Agent 级挂载、运行用户控制、强制沙箱逃逸检测 |
| **轻量部署与架构拆分** | OpenClaw（Gateway-lite）、NanoBot、ZeroClaw | 不加载 AI harness、仅工具模式、RPC 认证 |
| **Agent 间通信（A2A）** | OpenClaw、CoPaw、Hermes Agent | 单向调度、Hindsight 记忆隔离、子代理结果跟踪 |
| **国际化（i18n）** | CoPaw、OpenClaw | 工具审批卡硬编码英文，需要多语言支持 |
| **模型调用动态控制** | NanoBot、Moltis、ZeroClaw | 推理自动升级、异步工具调用、不同任务用不同模型 |

---

## 5. 差异化定位分析

| 项目 | 功能侧重 | 目标用户 | 技术架构关键差异 |
|------|----------|----------|------------------|
| **OpenClaw** | 全渠道、大规模 Agent 舰队、版本 Doctor 迁移 | 企业/重度用户 | 多模块耦合（网关+运行时+Doctor），Node.js + SQLite |
| **NanoBot** | 快速迭代、Dream 整合、TUI 体验 | 开发者和个人用户 | 轻量架构，配置驱动，社区 PR 响应快 |
| **Hermes Agent** | Kanban 工作流、看板管理、工作者调度 | 运维/自动化团队 | 工作流引擎 + 网关分层，有独立工作者池 |
| **NanoClaw** | 网关重构（Iron Proxy）、仅工具交付模式 | 部署灵活性高的用户 | 聚焦网关层，运行时（Bun）重构，CI 基础设施优化 |
| **PicoClaw** | 嵌入式/轻量、Telegram 集成 | 低功耗设备/嵌入式 | 代码量小，适配 Sipeed 硬件，依赖 OpenClaw 生态 |
| **NullClaw** | 移动端原生客户端探索 | 移动端偏好用户 | 讨论阶段，参考 Swift/Kotlin + Rust 跨端方案 |
| **LobsterAI** | 企业协作（钉钉、飞书）、桌面应用集成 | 中国团队协作用户 | 由网易有道维护，强 IM 集成，沙箱探针，配置同步 |
| **CoPaw (QwenPaw)** | 中文社区、Hub 多租户、实时语音、数据洞察 | 中文个人/团队用户 | 基于 Qwen 模型，Hub 成员治理，语音/数据 App 扩展 |
| **ZeroClaw** | Rust 核心、代码质量（反 Slop）、RPC 安全 | 对安全/性能敏感的用户 | 全 Rust 实现，ACP 协议测试，原子配置，CI 构建缓存 |
| **Moltis** | 斜杠命令扩展、沙箱粒度控制、构建加速 | 注重交互灵活性和多租户隔离 | Rust 实现，cargo 缓存脚本化，每 Agent 沙箱配置 |

---

## 6. 社区热度与成熟度分层

| 层级 | 项目 | 特征 |
|------|------|------|
| **🔥 高活跃·快速迭代** | OpenClaw、NanoBot、NanoClaw、ZeroClaw、CoPaw | 日均 Issue/PR > 20，功能与 Bug 修复并行，社区讨论密集 |
| **🟡 中等活跃·质量巩固** | Hermes Agent、LobsterAI、Moltis | 日均 Issue/PR 10~20，集中清理积压，修复已知关键 Bug |
| **🟢 稳定维护** | PicoClaw、NullClaw | 日均 Issue/PR < 5，偶有 PR 合并，无重大新问题 |
| **⚪ 无活动** | IronClaw、TinyClaw、ZeptoClaw | 24h 零更新，暂不活跃 |

**趋势**：大部分活跃项目正在从“功能开发”转向“稳定性攻坚”，尤其是 OpenClaw 和 CoPaw 的严重 Bug 短期内仍需大量投入。NanoClaw 和 ZeroClaw 通过架构重构（Iron Proxy、反 Slop）主动预防未来问题，可能率先步入成熟期。

---

## 7. 值得关注的趋势信号

1. **多会话隔离成为刚需**：用户不再满足于单 Agent 对话，多任务并行时数据污染、消息串扰已从“偶发”变为“高频投诉”。这一趋势将推动项目必须引入会话级互斥锁、工作区隔离或分布式事务——是短期内的架构重点。

2. **MCP 集成从“可用”走向“健壮”**：多个项目同时遭遇 MCP 超时崩溃、启动失败永不重试、结构化内容重复等问题。MCP 作为 Agent 与外部工具的核心协议，其可靠性直接影响生产环境接受度，预计下一版本将普遍增加重试/回退/隔离机制。

3. **更新/部署流程的“容错性”短板暴露**：OpenClaw、NanoClaw、LobsterAI 均出现因升级失败导致用户无法使用产品的场景。用户对“每次更新都心惊胆战”的反馈表明，**幂等升级、增量快照、回滚保护** 将成为所有项目必须基础设施化的能力。

4. **沙箱隔离从“全局”走向“Agent 级”**：Moltis 和 ZeroClaw 已率先引入每 Agent 沙箱配置（挂载路径、运行用户、强制模式），响应了多租户/安全敏感场景的需求。短期内其他项目大概率跟进。

5. **国际化（i18n）需求浮现**：CoPaw 用户明确提出工具审批卡等核心交互界面应支持多语言，OpenClaw 的飞书/Teams 渠道也涉及语言适配，表明生态正从英语主导转向全球化。

6. **模型调用动态化**：NanoBot 的“自动推理升级”和 Moltis 的“辅助模型配置”预示未来 Agent 将根据任务复杂性自动选择模型/参数，这是提升资源利用率和响应质量的关键方向。

7. **Agent 间通信（A2A）标准化**：OpenClaw、CoPaw、Hermes Agent 同时出现子代理结果跟踪、Hindsight 记忆隔离、单向调度等需求，说明多 Agent 协作场景已从原型进入实际使用，需要标准化的协议和隔离机制。

---

**对开发者的参考价值**：以上趋势提示 — 若计划构建个人 AI 助手或参与生态建设，**优先投入多会话隔离、MCP 健壮性、升级容错、Agent 级沙箱** 四个方向将获得最高社区关注度与产出比。同时关注 Rust 安全实践（ZeroClaw）、跨语言桥接（NullClaw）和移动端实时交互（CoPaw）等差异化路径，可形成竞争壁垒。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，这是根据您提供的 NanoBot 项目数据生成的动态日报。

---

# NanoBot 项目动态日报 | 2026-09-17

## 1. 今日速览

过去 24 小时内，NanoBot 项目保持了极高的活跃度，维护者响应迅速。主要特点如下：**PR 合并/关闭动作频繁**（5 个），显示出维护者正在积极清理和合并待处理的改进与修复；**Bug 修复成为绝对主线**，超过 10 个 PR 专注于修复各类稳定性、代理循环和工具调用问题，其中多个 PR 直接回应了社区报告的严重 Bug（如 #5781 Dream 循环问题）；**社区贡献持续涌入**，20 个 PR 中有大量来自外部贡献者，显示项目生态健康。总体而言，项目处于 **高强度的迭代优化阶段**，稳定性是当前核心关注点。

## 2. 版本发布

无新版本发布。尽管 Issue #5788 宣布了 v0.3.5 的发布，但该 Issue 在过去 24 小时内创建，其关联的 Release 创建时间早于本报告统计窗口。报告期内无新 Release 产生。

## 3. 项目进展

过去 24 小时内，项目在 Bug 修复和文档更新方面取得了实质性进展。以下为已合并/关闭的重要 PR：

- **PR #5782 [CLOSED] fix(dream): enforce configured iteration limit**
    - **摘要**：该 PR 直接修复了社区报告的关键问题 #5781。它恢复并应用了独立的 `dream.maxIterations` 配置项（默认值为 15），防止梦境（Dream）持续合并过程占用全局 200 次工具调用限制，从而避免长时间的代理循环。
    - **意义**：这是一个高优先级的稳定性修复，直接解决了因配置被忽略导致的任务执行失控问题。
    - **链接**: [PR #5782](https://github.com/HKUDS/nanobot/pull/5782)

- **PR #5789 [CLOSED] docs: refresh README WebUI screenshots**
    - **摘要**：由核心成员 chengyongru 提交，更新了 README 中的 WebUI 截图，以反映最新的界面功能和布局，包括新主题、多面板工作台、上下文使用情况和自动化日历视图。
    - **意义**：提升了项目文档的准确性和吸引力，帮助新用户更直观地了解项目能力。
    - **链接**: [PR #5789](https://github.com/HKUDS/nanobot/pull/5789)

- **PR #5791 [CLOSED] fix(tui): keep input responsive during agent output**
    - **摘要**：修复了 TUI（终端用户界面）中，代理输出时输入框可能无响应的问题。通过按批处理网关输出，保证了用户输入回调不被阻塞。
    - **意义**：显著改善了 TUI 用户的使用体验，使交互更加流畅。
    - **链接**: [PR #5791](https://github.com/HKUDS/nanobot/pull/5791)

- **PR #5756 [CLOSED] test(security): keep proxy-clearing fixtures hermetic on hosts with OS-level proxies**
    - **摘要**：增强了测试环境的隔离性，确保代理清理测试夹具在设置了系统级代理的主机上也能正常工作，防止跨环境干扰。
    - **意义**：提升了测试套件的可靠性和安全性，有助于维护代码质量。
    - **链接**: [PR #5756](https://github.com/HKUDS/nanobot/pull/5756)

- **PR #2595 [CLOSED] refactor: rename tool progress text variable for clarity**
    - **摘要**：一个代码重构优化，将工具进度路径中的变量名重命名以增加代码可读性。
    - **意义**：提升代码库质量和可维护性。
    - **链接**: [PR #2595](https://github.com/HKUDS/nanobot/pull/2595)

## 4. 社区热点

- **Issue #5781: Dream 循环与配置退化**
    - **讨论热度**：3 条评论，1 个 👍
    - **诉求分析**：该 Issue 揭示了**配置系统与用户体验的断层**。用户发现 `dream.maxIterations` 被标记为已弃用且失效，导致梦境任务自动回退到全局的 200 次工具调用上限，从而引发持续数十分钟的无效循环。社区迫切希望**已定义的配置项能够被可靠执行**，避免因默认值过高导致的资源浪费和任务挂死。该问题已通过 **PR #5782** 修复，反映了社区反馈的高效转化。
    - **链接**: [Issue #5781](https://github.com/HKUDS/nanobot/issue/5781)

- **PR #5718: 支持 OpenRouter 原生图像生成 API**
    - **讨论热度**：该 PR 虽无新评论，但其作为新增功能 PR 受到关注。
    - **诉求分析**：该功能请求旨在集成 OpenRouter 最新的图像生成 API，以确保 Nanobot 的 `generate_image` 工具能兼容并利用更多图像生成模型。这表明社区对**工具链的扩展性和兼容性**有持续的需求，希望项目能快速跟进上游服务提供商的更新。
    - **链接**: [PR #5718](https://github.com/HKUDS/nanobot/pull/5718)

## 5. Bug 与稳定性

今日报告的 Bug 和回归问题数量较多，但大部分已有对应的修复 PR，显示项目维护者反应迅速。

- **[高严重度] Issue #5781: Dream 任务陷入长时间循环**
    - **描述**：`dream.maxIterations` 配置被弃用导致梦境任务无限接近全局 200 次上限，造成资源浪费。
    - **修复状态**：已修复，对应 PR #5782 已合并。
    - **链接**: [Issue #5781](https://github.com/HKUDS/nanobot/issue/5781)

- **[中严重度] PR #5792: 跨会话消息投递问题 (fix(agent): serialize and batch per-session messages)**
    - **描述**：多个用户同时在不同会话中发送消息时，可能出现响应串扰（A 会话的响应出现在 B 会话）。这是一个典型的并发问题。
    - **优先级**：P1（高优先级）
    - **修复状态**：已提出修复 PR #5792，待合并。
    - **链接**: [PR #5792](https://github.com/HKUDS/nanobot/pull/5792)

- **[中严重度] PR #5794: 跨会话响应投递错误 (fix: cross-session response delivery in agent loop)**
    - **描述**：与 #5792 类似，描述了用户在快速切换会话时，响应被错误地投递到另一个会话的问题。
    - **优先级**：未明确标注，但问题性质与 P1 类似。
    - **修复状态**：已提出修复 PR #5794，待合并。
    - **链接**: [PR #5794](https://github.com/HKUDS/nanobot/pull/5794)

- **[中严重度] PR #5796 & #5795: `edit_file` 工具空格/缩进问题**
    - **描述**：`edit_file` 工具在进行内联替换时，会错误地移除分隔符空格（#5796）或丢失缩进并插入多余空行（#5795）。
    - **优先级**：P2
    - **修复状态**：已提出修复 PR #5796 和 #5795，待合并。
    - **链接**: [PR #5796](https://github.com/HKUDS/nanobot/pull/5796)，[PR #5795](https://github.com/HKUDS/nanobot/pull/5795)

- **[低严重度] PR #5765 & #5766 & #5762: Cron 工具与 API 行为问题**
    - **描述**：包含 API 流式参数 `stream` 非布尔值误判、Cron 任务字段冲突时静默丢弃、Cron 接受过去时间导致任务永久挂起等多项逻辑缺陷。
    - **优先级**：P2
    - **修复状态**：均已提出修复 PR，待合并。
    - **链接**: [PR #5765](https://github.com/HKUDS/nanobot/pull/5765)，[PR #5766](https://github.com/HKUDS/nanobot/pull/5766)，[PR #5762](https://github.com/HKUDS/nanobot/pull/5762)

- **[低严重度] PR #5793: `list_dir` 递归目录忽略规则错误**
    - **描述**：递归列出目录时，如果路径中包含 `build`、`dist` 等被忽略的目录名，会导致整个子目录树被错误地认为为空。
    - **优先级**：P2
    - **修复状态**：已提出修复 PR #5793，待合并。
    - **链接**: [PR #5793](https://github.com/HKUDS/nanobot/pull/5793)

## 6. 功能请求与路线图信号

- **Issue #4419: 自动推理努力升级（Automatic reasoning effort escalation）**
    - **需求**：希望 Nanobot 能根据任务复杂性自动调整模型的 `reasoningEffort` 参数（例如，从默认到高级），实现智能化的推理资源调度。
    - **路线图信号**：此项需求涉及对核心代理循环的改造，以支持动态参数调整。近期 PR 集中于修复，尚未看到直接实现此功能的 PR，但作为一项可显著提升智能体能力的 feature，它很可能是下一版本的方向之一。
    - **链接**: [Issue #4419](https://github.com/HKUDS/nanobot/issue/4419)

- **Issue #5731: 集成 AnySearch 作为 `web_fetch` 后端**
    - **需求**：AnySearch 团队提出，将其作为一种无需 API 密钥、有匿名配额限制的网页抓取后端集成到 Nanobot 中。
    - **路线图信号**：这是一个来自第三方服务商的主动贡献，如果集成，将极大丰富 Nanobot 的搜索能力，并提供另一种成本效益更高的选择。这符合项目扩展工具生态系统的潜在愿景。
    - **链接**: [Issue #5731](https://github.com/HKUDS/nanobot/issue/5731)

- **PR #5718: 支持 OpenRouter 原生图像生成 API**
    - **进展**：虽然是一个功能请求，但已经有对应的 PR #5718 在积极开发中。这表明支持新的或更新的提供商原生 API 是短期的路线图重点。
    - **链接**: [PR #5718](https://github.com/HKUDS/nanobot/pull/5718)

- **PR #5520: 为 Codex Provider 添加 Langfuse 追踪**
    - **分析**：该 PR 旨在为 Codex 专有接口添加 Langfuse 可观测性追踪。这显示了社区对提高项目**可观测性和可调试性**的兴趣，尤其是在混合了不同 API 实现的 provider 中。
    - **链接**: [PR #5520](https://github.com/HKUDS/nanobot/pull/5520)

## 7. 用户反馈摘要

- **主要痛点：配置项被弃用/忽略**：Issue #5781 的用户明确指出 `dream.maxIterations` 被标记为弃用且不生效，导致其任务执行失控。这代表了用户对**配置文件权威性**的深切担忧，即他们期望严格遵循已显式设置的参数。
- **功能使用场景：Scheduled Dream 持续整合**：用户在 #5781 中描述了具体的自动化运维场景，即使用 Scheduled Dream 进行知识的定期整合。这表明 Nanobot 的“梦境”功能已被用户作为**长期、无人值守的数据处理工具**用于生产或半生产环境。
- **开发体验：`edit_file` 工具的精度问题**：PR #5796 和 #5795 的修复对象，反映了开发者在使用代码编辑工具时对**精确性和原子性**的高要求。细微的空格或缩进变化都会导致代码语义错误，这是代理工具在代码生成/编辑场景下的关键痛点。
- **多会话下的混乱**：PR #5792 和 #5794 的问题直接报告了用户在**多线程/多窗口**使用模式下的糟糕体验：响应串扰完全破坏了对话的预期逻辑，这是多会话架构中一个严重且影响面广的 Bug。

## 8. 待处理积压

以下为长期未响应，但值得维护者关注的重要 Issue 或 PR。本报告周期内未发现新的长期未响应项，但以下先前报告的项仍悬而未决：

- **Issue #4419: 自动推理努力升级**
    - **状态**：已创建近 3 个月 (创建于 2026-06-20)，有 5 条评论。作为一个有潜力的新功能，其讨论似乎已停止，建议维护者重新评估其优先级并给予反馈。
    - **链接**: [Issue #4419](https://github.com/HKUDS/nanobot/issue/4419)

- **PR #5152: 标记子代理部分完成结果**
    - **状态**：创建于 2026-07-28，已打开近 2 个月。此 PR 旨在解决子代理异步结果跟踪问题，是防止响应丢失或混乱的基础性改进。考虑到最近出现了多个与会话/响应串扰相关的回归问题（PR #5792, #5794），该 PR 的优先级可能因此提高。
    - **链接**: [PR #5152](https://github.com/HKUDS/nanobot/pull/5152)

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域的开源项目分析师，我将根据您提供的 Hermes Agent GitHub 数据，生成 2026-09-17 的项目动态日报。

---

# Hermes Agent 项目动态日报 | 2026-09-17

## 1. 今日速览

项目今日维持高活跃度，社区主要聚焦于 Bug 修复和稳定性提升。过去 24 小时内，共有 **50 个 Issue** 和 **50 个 PR** 被更新，关闭/合并的数量（39 个 Issue, 18 个 PR）几乎与新增/待处理的数量持平，显示出维护团队正在积极清理积压问题。当日未发布新版本，工作重心在于修补已知缺陷，特别是围绕 **Kanban 工作流**、**网关/消息传递** 以及 **并发会话隔离** 的核心 Bug 修复。整体来看，项目正处于高强度的迭代和维护周期中。

## 2. 版本发布

**无**

## 3. 项目进展

今日项目中多项重要修复已被合并或关闭，显著提升了系统的稳定性和可靠性。

- **Kanban 工作流修复**: 针对 Kanban 系统的一系列 Bug 已得到解决。`#113616` 修复了自动心跳桥接静默失败的问题，使工作者进程的

Claim 状态能被正确维护。`#113632` 修复了未记录工作者 PID 的 Kanban 行永远卡在 `running` 状态的问题，现在这些行可以被正确回收。`#113604` 修复了工作者将交付物直接写入附件目录后，无法被正确注册的问题。这些修复显著增强了 Kanban 系统的健壮性。

- **核心与网关稳定性**: `#113169` (关连 Issue `#112909`) 修复了 Codex 模式下，高推理强度请求被小型提示的门狗错误杀死的问题，保护了长时间静默思考过程。`#113213` 修复了安装日志中显示的 ANSI 转义码乱码问题，提升了用户体验。`#113216` (关连 Issue `#112319`) 修复了使用固定 Profile 时，每次命令都显示错误的 `HERMES_HOME` 回退警告，消除了不必要的噪音。

- **自动化与代码质量**: 合并了由自动化机器人提交的代码格式化 PR (`#113630`)，确保了代码风格的统一。

**链接**: [PR #113616](https://github.com/NousResearch/hermes-agent/pull/113616), [PR #113632](https://github.com/NousResearch/hermes-agent/pull/113632), [PR #113604](https://github.com/NousResearch/hermes-agent/pull/113604), [PR #113169](https://github.com/NousResearch/hermes-agent/pull/113169), [PR #113213](https://github.com/NousResearch/hermes-agent/pull/113213), [PR #113216](https://github.com/NousResearch/hermes-agent/pull/113216)

## 4. 社区热点

今日讨论热度最高的议题主要集中在两大问题上：

1.  **并发会话的内存/工作区污染问题 (`#46303`)**: 该 Issue 获得了 **8 条评论**，是今日最受关注的问题。用户 `markob100` 报告了一个严重 Bug：当同时运行多个桌面会话时，共享内存和 Git 工作树导致会话间数据交叉污染，且没有任何隔离机制。这表明用户对**数据安全性和多任务并行处理**的需求极为强烈，现有架构在应对真实多会话场景时存在根本性缺陷。

2.  **MoA (Mixture-of-Agents) 计费与模型状态显示问题**: `#112359` 和 `#54509` 分别讨论了 MoA 模式下的计费不透明问题和 WebUI 模型徽章显示错误。前者（3条评论）反映了用户对**成本归属清晰度**的诉求，不理解为何聚合器模型（agggregator）而非引用模型（reference）被计费。后者（3条评论）则是在抱怨**UI 状态与实际运行状态不同步**，即在模型回退时，界面依然显示错误的模型名称，影响了用户对系统状态的认知。

**链接**: [Issue #46303](https://github.com/NousResearch/hermes-agent/Issue/46303), [Issue #112359](https://github.com/NousResearch/hermes-agent/Issue/112359), [Issue #54509](https://github.com/NousResearch/hermes-agent/Issue/54509)

## 5. Bug 与稳定性

今日报告了大量 Bug，覆盖了从核心到网关的多个方面，按严重程度排列如下：

- **P1 (严重)**:
    - **Telegram 网关失聪** (`#113618`, Open): 更新后，Telegram 网关的看门狗无法恢复断连的轮询器，导致网关看似在线但无法接收消息，必须重启进程才能恢复。已有社区成员关注，影响消息可用性。
    - **NO_REPLY 静默标记被错误拦截** (`#113031`, Closed): 在会话心跳上返回的 `NO_REPLY` 标记被错误地拒绝并生成了警告，导致心跳功能失效。该问题已关闭，表明已找到解决方案。

- **P2 (重要)**:
    - **Kanban 工作者连续无状态重启** (`#113611`, Open): 看门狗无法检测到工作者无状态退出（exit rc=0）后重启的情况，导致同一任务被无限次重复执行（最多观测到 16次），造成资源浪费。
    - **Discord 消息重复分发** (`#113631`, Open): 重连后，Discord 网关的消息回溯功能会重复分发已处理过的消息，导致单个消息在 12 小时内被重复执行 24 次，严重浪费资源和造成回复混乱。
    - **跨会话文件写入安全漏洞修复** (`#113628`, Open): 报告了文件写入保护机制在特定部署（如使用 Profile HOME）下存在漏洞。
    - **`/branch` 命令与运行中的 agent 发生竞态** (`#112137`, Closed): 在 agent 还在运行时使用 `/branch` 命令会导致会话身份切换，使得后续消息被错误地发送到新的分支会话。问题已关闭。

- **P3 (一般)**:
    - 其他问题包括：Kanban 运行行状态分类不一致 (`#113610`)、CRON 交付超时记录错误 (`#113608`)、STT 进程失败被掩盖 (`#112582`)、以及技能内容因缓存问题无法检索 (`#112763`) 等。

**链接**: [Issue #113618](https://github.com/NousResearch/hermes-agent/Issue/113618), [Issue #113031](https://github.com/NousResearch/hermes-agent/Issue/113031), [Issue #113611](https://github.com/NousResearch/hermes-agent/Issue/113611), [Issue #113631](https://github.com/NousResearch/hermes-agent/Issue/113631), [Issue #113628](https://github.com/NousResearch/hermes-agent/Issue/113628), [Issue #112137](https://github.com/NousResearch/hermes-agent/Issue/112137)

## 6. 功能请求与路线图信号

今日社区提出的功能请求更多是围绕现有功能的改进和修整，而非全新的功能。

- **MoA 计费透明化**: 用户 `benbarclay` 的 Issue `#112359` 明确提出了改进 MoA（Mixture-of-Agents）用户界面的需求，核心诉求是让用户能清晰看到**聚合器（Aggregator）才是实际计费的模型**。已有 PR `#113605` (修复 API server 会话恢复问题) 和 `#113606` (为会话流添加工具审批功能) 在同时进行，表明团队正集中解决 MoA/Gateway 相关的体验问题。预计下一版本会包含 MoA 相关的计费或状态显示改进。
- **机器人聊天工具调用限制**: PR `#113607` 提出了一个需求：为群聊（Bot Chat）中的 agent 添加每轮 3 个工具调用的预算上限。这可能是为了平衡群聊体验，防止单个回复占用过多处理时间。该需求相对独立，有可能被快速纳入。
- **Hindsight 内存与 Agent 间对话隔离**: PR `#113625` 引入了一个新特性：让 Hindsight 记忆提供者能识别并标记 agent 之间的对话（A2A turns），使其不出现在用户的回忆中。这是一个针对特定场景（多 Agent 协作）的精细化管理功能，如果成熟，可能会在后续版本中作为可选特性发布。

**链接**: [Issue #112359](https://github.com/NousResearch/hermes-agent/Issue/112359), [PR #113607](https://github.com/NousResearch/hermes-agent/pull/113607), [PR #113625](https://github.com/NousResearch/hermes-agent/pull/113625)

## 7. 用户反馈摘要

从今日的 Issues 和反馈中，可以提炼出以下用户痛点:

- **对数据隔离性的迫切需求**: 用户 `markob100` 在 Bug `#46303` 中详细描述了并发会话带来的共享内存和 Git 工作树污染问题，这直接影响了可靠性，是当前最让用户感到困扰的痛点之一。
- **对系统状态感知的强烈不满**: 多个 Bug (如 `#54509` WebUI 模型徽章、`#112319` 错误的 HOME 警告、`#113029` 会话状态显示错误) 表明用户非常依赖 UI 获取准确的系统状态，任何不一致都会引起混淆和信任感降低。
- **对盲目重复操作的无奈**: 用户 `KenyBoi` 报告了 Kanban 工作者连续 16 次重启的 Bug (`#113611`)，而 `makocult` 报告了 Discord 消息被重复分发 24 次的 Bug (`#113631`)。这种无意义的系统资源浪费和潜在的数据重复处理行为严重消耗了用户的耐心。
- **对成本控制的理解需求**: 用户 `benbarclay` 的反馈 (`#112359`) 清晰地表达了用户期望能理解和预测自己的服务成本，特别是当复杂的架构（如 MoA）导致计费逻辑不直观时。

## 8. 待处理积压

**待跟进的重要 Issue**:

- **[Bug]: Concurrent sessions cross-contaminate** (`#46303`, P2, 创建于2026-06-14): 该问题已存在三个月，评论数持续增加。尽管描述详尽，但目前仍未看到对应的修复 PR。随着系统并发使用的增多，这个问题可能会日益凸显，建议维护者优先评估并制定解决方案。链接: [Issue #46303](https://github.com/NousResearch/hermes-agent/Issue/46303)

- **[Bug]: WebUI model badge does not reflect runtime model during fallback activation** (`#54509`, P3, 创建于2026-06-28): 一个小但影响感知的问题，也存在了近三个月而无进展。用户期望能实时看到正在运行的模型，尤其是在使用了回退机制的情况下。链接: [Issue #54509](https://github.com/NousResearch/hermes-agent/Issue/54509)

**待合并的 PR**:

- **固定文件写入安全漏洞的 PR** (`#113629`): 该 PR 直接对应今日新开的 P2 级安全 Issue `#113628`，响应非常迅速。鉴于其涉及安全性，建议尽快审核并合并。链接: [PR #113629](https://github.com/NousResearch/hermes-agent/pull/113629)

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

# PicoClaw 项目动态日报 | 2026-09-17

---

## 1. 今日速览

过去 24 小时项目整体活跃度偏低：**无新 Issue 和 PR 开启**，共关闭 1 个历史 Issue 和 2 个遗留 PR，另有一个近一个月前提交的 PR 仍处于待合并状态。合并的两项 PR 均针对 Telegram 集成中的对话连续性缺陷进行了修复，提升了 Bot 在群组场景下的响应准确性。无新版本发布。项目当前处于稳定维护期，核心贡献节奏放缓，但遗留问题的清理仍在进行。

---

## 2. 版本发布

无新版本发布。

---

## 3. 项目进展

今日共合并/关闭 2 个 PR，均来自同一贡献者 `hugodeco`，聚焦 Telegram 适配层的两个关键修复：

- **PR #3357** `fix(telegram): treat replies to the bot's own messages as implicit mentions`  
  修复了群组 `mention_only: true` 模式下，用户直接回复 Bot 消息时被静默忽略的问题。现在回复 Bot 自己的消息被视为隐式提及，无需再手动添加 `@`，显著改善了群聊中的对话连续性。  
  [🔗 sipeed/picoclaw PR #3357](https://github.com/sipeed/picoclaw/pull/3357)

- **PR #3356** `fix(telegram): re-attach quoted documents when replying to a file message`  
  解决了用户引用/回复文件消息时，Bot 仅收到 `[file]` 占位符而非实际文件的故障。此前语音/音频已被正确处理，但文档类媒体被遗漏，现改为统一重新附加引用中的文档。  
  [🔗 sipeed/picoclaw PR #3356](https://github.com/sipeed/picoclaw/pull/3356)

这两个修复均属于**用户可直接感知的 Telegram 消息处理回归**，合并后提升了 Bot 在群聊场景下的鲁棒性。

此外，一个**待合并**的 PR **#3344** 仍在开放中（详见第 8 节），未取得进展。

---

## 4. 社区热点

今日无高活跃度或高评论量的讨论。唯一有较多互动的是已关闭的 Issue **#3343**（共 4 条评论），该问题于 2026-08-22 提出，2026-09-16 被自动关闭（标记为 stale）。问题描述了**工具反馈动画无限调用 Telegram `editMessageText` API 导致被限流**，用户称产生了超过 22.8 万次编辑尝试。该问题虽已关闭，但反映了 Telegram 重试机制与动画循环之间的潜在缺陷，值得维护者在后续版本中主动加入防重试保护。  
[🔗 sipeed/picoclaw Issue #3343](https://github.com/sipeed/picoclaw/issues/3343)

---

## 5. Bug 与稳定性

| 严重程度 | 说明 | 状态 | 相关链接 |
|----------|------|------|----------|
| 中等 | 工具反馈动画在 Agent 停止后仍持续调用 Telegram `editMessageText`，导致超过 22.8 万次 API 调用并触发限流。该问题在 26 天后被自动关闭（stale），**无修复 PR 与之关联**。 | 已关闭（未修复） | [Issue #3343](https://github.com/sipeed/picoclaw/issues/3343) |
| 低 | 群组 `mention_only` 模式下回复 Bot 消息被忽略 | 已通过 PR #3357 修复 | [PR #3357](https://github.com/sipeed/picoclaw/pull/3357) |
| 低 | 引用文件消息时文件内容丢失 | 已通过 PR #3356 修复 | [PR #3356](https://github.com/sipeed/picoclaw/pull/3356) |

> ⚠️ 注意：#3343 作为 **stale 自动关闭**，意味着该 Bug 在代码中仍可能存在，建议维护者评估是否需要在工具反馈超时逻辑中加入强制取消循环的保护。

---

## 6. 功能请求与路线图信号

今日无新增功能请求。但待合并的 PR **#3344** `Add Build Remote Agent phone pairing (gbr/1)` 是一项实质性的新功能——允许手机作为远程伴侣设备配对并观看桌面 Agent 运行。该 PR 引入了 `gbr/1` 协议适配器，支持二维码和 8 字符码配对，监听 `127.0.0.1:8788` 或 stdio。如果该 PR 被合并，将扩展 PicoClaw 的使用场景至**移动端远程监控**，属于路线图中的重要增强。  
[🔗 sipeed/picoclaw PR #3344](https://github.com/sipeed/picoclaw/pull/3344)

---

## 7. 用户反馈摘要

从 Issue **#3343** 的摘要中可提炼出以下真实用户痛点：

- **资源浪费与 API 滥用**：Agent 完成一次推理后，工具反馈动画独立于 Agent 生命周期，持续触发 API 调用，导致几日内累计 22.8 万次编辑请求。用户对此表达了强烈不满（'produced over 228,000 edit attempts'）。
- **缺乏超时/清理机制**：当 Agent 不再产生新消息时，动画循环未被取消，说明当前设计未将工具反馈生命周期与 Agent 执行状态绑定。

无其他用户满意度或场景描述。

---

## 8. 待处理积压

| 项目 | 类型 | 创建日期 | 最后更新 | 状态 | 链接 |
|------|------|----------|----------|------|------|
| Add Build Remote Agent phone pairing (gbr/1) | PR | 2026-08-23 | 2026-09-16 | **待合并**，已开放 25 天，无评论，可能需要维护者审核或补充测试 | [PR #3344](https://github.com/sipeed/picoclaw/pull/3344) |

该 PR 仍无任何评论或 review，长期搁置可能降低贡献者积极性。建议维护者评估其代码质量与协议兼容性，决定是否合并或关闭，并给予反馈。

此外，**Issue #3343** 虽已关闭，但作为已知 Bug 并未修复，应被视为**技术债务**，建议在未来里程碑中重新开放并分配修复。

---

*数据统计截止时间：2026-09-17 UTC 00:00，数据来源：GitHub API*

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据您提供的 NanoClaw 项目数据生成的日报。

---

## NanoClaw 项目动态日报 | 2026-09-17

### 1. 今日速览

今日项目活跃度极高，虽无新版本发布，但 Pull Request (PR) 处理量惊人，达到34条，其中9条已合并/关闭，25条待合并，表明项目核心团队正在进行大规模的重构与功能迭代。过去24小时内未报告新的Issue，但已有的2个Issue均指向了因Bun运行时引起的严重CI挂起问题，社区对此高度关注。整体来看，项目正处在一轮重要的架构升级和Bug修复周期中，进展迅速。

### 2. 版本发布

无。

### 3. 项目进展

今日合并/关闭的9个PR中，多个核心贡献者的工作被接受，项目在稳定性、基础设施和功能模块上均有实质性推进：

- **修复Bun运行时导致的CI挂起问题**：PR #3841 针对 `add-opencode` 测试中因 Bun 的 `spawnSync` 引起的6小时挂起问题，改用异步 `spawn` 以避免进程阻塞。这是对已报告Bug (#3839) 的直接修复，对项目CI稳定性至关重要。([链接](https://github.com/nanocoai/nanoclaw/pull/3841))
- **重构网关凭证系统**：PR #3824 已关闭，它为核心网关层增加了共享的凭证连接接口，允许不同AI服务提供商在不控制网关管理API的情况下描述其认证方式。这是PR #3815 大型重构的前置工作。([链接](https://github.com/nanocoai/nanoclaw/pull/3824))
- **CI流程优化**：PR #3836 已合并，将为“注册表-技能”测试任务设定20分钟的超时限制，防止挂起的测试任务长时间占用CI资源。([链接](https://github.com/nanocoai/nanoclaw/pull/3836))
- **Iron Proxy Gateway 修复**：PR #3843 修复了 Iron Proxy 前向代理中的WebSocket握手和上行帧传输问题，确保其能与其他提供商（如Codex）端到端工作。([链接](https://github.com/nanocoai/nanoclaw/pull/3843))

这些合并表明，项目当前工作重心是解决底层运行时缺陷、优化CI/CD基础设施，同时推进“Iron Proxy”等关键网关功能的稳定接入。

### 4. 社区热点

今日讨论焦点集中在两个关联的Bug报告上：

- **#3839 [Bug] `registry-skills: add-opencode reapply pass hangs in bun test until the 6-hour cancel`**：该Issue报告了在CI环境中，`bun test` 会因底层进程问题无响应挂起长达6小时。尽管没有直接评论，但该问题引发了最高的关注，并直接催生了PR #3841和 #3836 等高优先级修复。([链接](https://github.com/nanocoai/nanoclaw/issues/3839))
- **#3842 [Hardening] `upload-trace still runs curl through Bun's spawnSync, which can wedge the poll loop`**：该Issue指向了相同的根因——Bun的 `spawnSync` 函数存在Bug。它明确指出即使在上一个相关修复后，`upload-trace` 功能仍然存在此风险。这表明社区对运行时稳定性的诉求非常强烈和具体。([链接](https://github.com/nanocoai/nanoclaw/issues/3842))

**分析**：社区的核心诉求是项目运行的稳定性。Bun 1.4.0 版本的 `spawnSync` Bug 已成为影响CI和开发者体验的“拦路虎”。相关Issue和PR的快速联动，证明了维护者和社区正在联手努力解决这个关键问题。

### 5. Bug 与稳定性

今日报告的Bug均与运行时的核心稳定性相关，严重程度为“严重”，因为它们直接导致CI流程完全失效。

| 问题 | 严重程度 | 描述 | 是否有修复PR |
| :--- | :--- | :--- | :--- |
| Issue #3839: `bun test` 挂起 | **严重** | CI中 `add-opencode` 测试因Bun的 `spawnSync` 问题挂起6小时。 | 是 (PR #3841) |
| Issue #3842: `upload-trace` 导致轮询阻塞 | **严重** | 相同的 `spawnSync` Bug 可能导致 `upload-trace` 功能阻塞主循环。 | 待定 (作为强化项提出) |

除了上述Issue，PR #3803 也试图修复一个关于Webhook端口恢复测试的稳定性问题，通过在Fixtrue持有的端口上进行监听，避免了因端口竞争导致的测试失败。这表明项目也在解决更细微的测试稳定性问题。([链接](https://github.com/nanocoai/nanoclaw/pull/3803))

### 6. 功能请求与路线图信号

今日没有新增直接的功能请求类Issue，但从今日合并/待审的PR中，可以清晰看到项目的功能开发方向：

- **“Iron Proxy” 网关集成**：PR #3817 标志着引入“Iron Proxy”作为可选网关方案，这是一个重要的功能特性。多个相关PR（如#3825、#3818、#3843）都围绕此展开，表明这是一个高优先级的路线图项。它旨在为用户提供不同于“OneCLI”的AI网关选择，增强了项目的灵活性和自主权。
- **“工具仅”交付模式**：PR #3781 和 #3713 正在推进一个名为“tools-only”的交付模式。这允许为某些AI服务提供商（其无法可靠地以最终文本形式发送回复）配置仅通过工具（如API调用）进行结果交付，提升了与多种AI提供商的兼容性。
- **安装脚本改进**：PR #3844 改进了 `setup.sh` 脚本，解决了在通过系统包管理器（如apt、dnf）安装Node.js的Linux系统上，pnpm安装失败的问题。这体现了对更广泛用户环境的兼容性改进。

**判断**：下一版本很可能包含“Iron Proxy”网关、“工具仅”交付模式以及对安装流程的重大改进。这些功能响应了社区对更灵活、更可靠的Agent基础设施的需求。

### 7. 用户反馈摘要

由于今日新增的Issue和PR评论数为0，因此无法直接从评论中获取用户反馈。但从Bug报告的内容来看，用户（核心开发贡献者 `glifocat`）的反馈非常专业且深入：他们不仅指出现象，还**准确追踪到了底层依赖（Bun 1.4.0）的Bug**，甚至链接到了Bun项目的对应Issue (`oven-sh/bun#34069`)。这表明NanoClaw项目的用户群体技术能力强，并且项目维护者与用户之间的沟通是高效的。

### 8. 待处理积压

以下是长期未处理但值得关注的重要工作项：

- **PR #2681** (`fix(service): skip linger on per-home-encrypted systems`): 创建于2026年6月3日，旨在解决家庭目录加密系统上的服务问题，已3个月未被合并。
- **PR #3156** (`fix(agent-runner): carry channel attachments to providers as structured parts`): 创建于2026年7月30日，旨在改进附件传递机制，至今处于开放状态约1个半月。
- **PR #2301** (`feat(add-github): polling mode, git access question, safe OneCLI secret merge`): 创建于2026年5月6日，是一个大型功能PR，添加了轮询模式等，已有4个月未合并。

这些长期开放的PR同时涉及Bug修复和功能增强，可能与当前高优先级的开发任务（如网关重构）存在冲突或依赖关系。建议维护团队对其状态进行回顾，明确是搁置、搁置并计划放弃，还是需要更多输入。

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

好的，遵照您的要求，以下是根据提供的 NullClaw 项目 GitHub 数据生成的 2026-09-17 项目动态日报。

---

# NullClaw 项目日报 | 2026-09-17

## 1. 今日速览
- 过去 24 小时项目整体活跃度较低，仅处理了 **1 条 Issue**，无新的 Pull Request 或版本发布。
- 核心动态是 **Issue #999 被关闭**，该 Issue 探讨了将外部项目 `litter` 的移动端 GUI 架构移植到 `human-guard-rail` 中，作为 NullClaw 的移动客户端。关闭原因未见详细说明，但表明社区对该方向的讨论已告一段落。
- 无新 PR 合并或关闭，项目主干代码未发生变更，开发节奏趋于平稳。
- 社区讨论冷清，仅有该 Issue 附带 **1 条评论**，未形成广泛讨论或关注。
- **活跃度评估：低**。项目处于日常维护与微调阶段，无明显功能推进或社区热点。

## 3. 项目进展
- **无重要 PR 合并或关闭**。项目主干代码在过去 24 小时内无变更。
- 唯一值得关注的是 **Issue #999 被关闭**，该 Issue 提出将 `litter`（一个原生 iOS/Android agentic-coding 客户端，基于 Swift/Kotlin + Rust 核心）的架构模式复用到 `human-guard-rail`（目前为纯 Android/Gradle 应用），以构建 NullClaw 的移动客户端。尽管 Issue 已关闭，但其探索方向暗示项目团队可能仍在对移动端交互方案进行评估，但短期内或未纳入优先级。

## 4. 社区热点
- **Issue #999**（[链接](https://github.com/nullclaw/nullclaw/issues/999)）是今日唯一有讨论的 Issue，但仅获 **0 👍** 和 **1 条评论**，热度极低。  
  **诉求分析**：作者 `Azdwarf5Azdwarf` 提出的核心需求是**复用成熟移动端架构以快速构建 NullClaw 原生客户端**。`litter` 项目使用 UniFFI 桥接 Rust 核心与 Swift/Kotlin UI，是一种低耦合、高性能的跨端方案。该议题反映了社区中对**更轻量、更原生、可脱离 Web 界面的移动端使用体验**的潜在期待。Issue 被关闭可能意味着团队已有替代方案，或认为该方向与当前路线图不符。

## 5. Bug 与稳定性
- **无新 Bug 报告**。过去 24 小时内未出现崩溃、回归或稳定性相关的 Issue，项目当前无明显已知关键问题。

## 6. 功能请求与路线图信号
- **Issue #999** 实际上是一个功能探索类议题，其内容可视为一个**功能请求**：希望将 NullClaw 的客户端能力扩展到原生移动端。该请求虽已关闭，但提供了清晰的架构参考（`litter` 的 UniFFI 方式）。  
  **路线图信号**：项目 `human-guard-rail` 目前是纯 Android 应用，而 `litter` 是双端方案。该 Issue 暗示社区希望 NullClaw 能有一个**跨平台、原生、防篡改（human-guard-rail）的移动客户端**。未来版本是否纳入取决于团队对移动端客户端的优先级评估。目前无对应 PR 或分支，暂无明确纳入下一版本的迹象。

## 7. 用户反馈摘要
- 由于仅有 **1 条评论** 且未公开内容，无法提炼具体用户痛点或满意度评价。从 Issue 标题和描述推测，作者对 `litter` 的架构较为满意，并希望将其优点引入 NullClaw 生态，可能反映出对 **“移动端体验割裂”或“当前客户端过重”** 的关切。建议项目组关注该方向以丰富用户使用场景。

## 8. 待处理积压
- **无**。当前无长期未响应的重要 Issue 或 PR，项目 backlog 较为干净。注意：`human-guard-rail` 仓库的状态未在此数据中体现，如有跨仓库依赖，建议额外关注。

---

**报告生成时间**：2026-09-17  
**数据源**：NullClaw GitHub 仓库（github.com/nullclaw/nullclaw）  
**分析师**：AI 智能体与个人 AI 助手领域开源项目分析师

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

# LobsterAI 项目动态日报  
**日期：2026-09-17**  
**数据来源：GitHub (netease-youdao/LobsterAI)**  

---

## 今日速览  
过去 24 小时项目维护活跃度显著：共关闭 **9 个 Issues** 和 **18 个 Pull Requests**，所有条目均已完成处理。虽然这些 Issues/PR 大多创建于 2026 年 3 月（带有 `[stale]` 标签），但均在今日统一关闭，表明维护团队对历史积压进行了集中清理和修复验证。PR 合并内容覆盖并发安全、定时任务可靠性、用户界面优化、MCP 连接管理等多个关键领域，项目整体稳定性和用户体验得到有效提升。无新版本发布。

---

## 项目进展  
今日合并/关闭的 18 个 PR 主要推进了以下方向：

### 1. 并发安全与竞态修复（共 5 个 PR）  
- **[#1090](https://github.com/netease-youdao/LobsterAI/pull/1090)**：CoworkRunner 增加 per-session 重入保护，防止并发 `startSession`/`continueSession` 导致流式消息损坏和重复。  
- **[#1100](https://github.com/netease-youdao/LobsterAI/pull/1100)**：IM 消息处理加入 per-conversation 互斥锁，解决重复会话创建和消息响应丢失（关联 Issue #1099）。  
- **[#1101](https://github.com/netease-youdao/LobsterAI/pull/1101)**：跨 Provider 切换模型后立即发消息报错的竞态条件修复（等待 gateway 重启完成后再允许发送）。  
- **[#1108](https://github.com/netease-youdao/LobsterAI/pull/1108)**：定时任务 `pollOnce()` 增加重入保护和 `pollGeneration` 计数器，消除幽灵事件（关联 Issue #1107）。  
- **[#1127](https://github.com/netease-youdao/LobsterAI/pull/1127)**：MCP `stop()` 方法取消强制关闭定时器，防止关闭新 Server 的连接。

### 2. 用户体验提升（共 6 个 PR）  
- **[#1119](https://github.com/netease-youdao/LobsterAI/pull/1119)**：工具权限弹窗支持 Enter 确认 / Escape 拒绝键盘快捷键（关联 Issue #1117）。  
- **[#1121](https://github.com/netease-youdao/LobsterAI/pull/1121)**：会话出错后底部显示错误横幅，支持一键 Retry 重发最后一条消息（关联 Issue #1120）。  
- **[#1125](https://github.com/netease-youdao/LobsterAI/pull/1125)**：会话列表增加消息内容全文搜索与关键词高亮。  
- **[#1138](https://github.com/netease-youdao/LobsterAI/pull/1138)**：Cowork 会话中工具调用错误时以红色背景高亮显示，并添加“跳至最新”按钮。  
- **[#1122](https://github.com/netease-youdao/LobsterAI/pull/1122)**：移除表格 Table 顶部和底部的多余空白（关联 Issue #1112）。  
- **[#1102](https://github.com/netease-youdao/LobsterAI/pull/1102)**：定时任务开关按钮增加 tooltip 提示。

### 3. 基础设施与修复（共 7 个 PR）  
- **[#2688](https://github.com/netease-youdao/LobsterAI/pull/2688)**：修复上游模型认证失败导致 LobsterAI 代理凭证锁定五小时的缺陷。  
- **[#2689](https://github.com/netease-youdao/LobsterAI/pull/2689)**：OpenClaw 启动前迁移共享状态 schema，提高升级兼容性。  
- **[#2690](https://github.com/netease-youdao/LobsterAI/pull/2690)**：OpenClaw 修复流程增加按阶段备份与回滚机制。  
- **[#1103](https://github.com/netease-youdao/LobsterAI/pull/1103)**：设置页面增加 Docker 沙箱就绪探针与状态 UI。  
- **[#1113](https://github.com/netease-youdao/LobsterAI/pull/1113)**：当 gateway 工作负载排空时立即刷新延迟的配置同步。  
- **[#1106](https://github.com/netease-youdao/LobsterAI/pull/1106)**：修复钉钉定时任务 IM 通知因 conversationId 前缀导致路由失败的问题。  
- **[#1130](https://github.com/netease-youdao/LobsterAI/pull/1130)**：修复 Anthropic SSE 流式解析因缺失行缓冲导致数据丢失的问题。

---

## 社区热点  
今日所有 Issues 评论量均在 2-3 条，讨论较为平淡。但从 Issue 描述及对应 PR 数量可看出社区关注重点：  
- **表格样式问题**（[#1112](https://github.com/netease-youdao/LobsterAI/issues/1112)）有 3 条评论，用户提供了截图对比，属于 UI 细节反馈。  
- **IM 并发与定时任务可靠性**是社区多次提交的领域（贡献者 MaoQianTu 连续提交了多个高质量 Bug 报告与修复 PR），表明团队对协作模块的稳定性有持续需求。  
- **会话 Retry**（[#1120](https://github.com/netease-youdao/LobsterAI/issues/1120)）和**键盘快捷键**（[#1117](https://github.com/netease-youdao/LobsterAI/issues/1117)）反映了用户对提升操作效率的强烈诉求。

---

## Bug 与稳定性  
今日关闭的 Bug 报告及修复情况（按严重程度排列）：  

| 严重程度 | Issue | 描述 | 修复 PR | 状态 |
|----------|-------|------|---------|------|
| 高 | [#1099](https://github.com/netease-youdao/LobsterAI/issues/1099) | IM 消息并发导致重复会话创建和消息响应丢失 | [#1100](https://github.com/netease-youdao/LobsterAI/pull/1100) | ✅ 已合并 |
| 高 | [#1107](https://github.com/netease-youdao/LobsterAI/issues/1107) | 定时任务 `pollOnce()` 无重入保护，`stopPolling()` 后幽灵事件 | [#1108](https://github.com/netease-youdao/LobsterAI/pull/1108) | ✅ 已合并 |
| 中 | [#1105](https://github.com/netease-youdao/LobsterAI/issues/1105) | 钉钉定时通知因 conversationId 前缀导致无法送达 | [#1106](https://github.com/netease-youdao/LobsterAI/pull/1106) | ✅ 已合并 |
| 中 | [#1112](https://github.com/netease-youdao/LobsterAI/issues/1112) | 表格顶部/底部异常留白 | [#1122](https://github.com/netease-youdao/LobsterAI/pull/1122) | ✅ 已合并 |
| 低 | [#1124](https://github.com/netease-youdao/LobsterAI/issues/1124) | 退出登录后安装最新版本仍提示“Lobster AI 无法关闭” | 无明确关联 PR | ⏳ 已关闭未修复（可能为安装器问题） |
| 低 | [#1139](https://github.com/netease-youdao/LobsterAI/issues/1139) | 新建重名 Agent 后任务记录未立即显示 | 无关联 PR | ⏳ 已关闭未修复 |
| 中 | [#1096](https://github.com/netease-youdao/LobsterAI/issues/1096) | Markdown 转 PDF 时打开多余浏览器页面并显示会员框 | 无关联 PR | ⏳ 已关闭未修复 |

此外，通过 PR [#1130](https://github.com/netease-youdao/LobsterAI/pull/1130) 修复了 Anthropic SSE 流式解析数据丢失的隐蔽 Bug（关联 Issue #922），降低高吞吐场景下的数据损坏风险。

---

## 功能请求与路线图信号  
今日关闭了 3 个功能请求 Issue，且均有对应 PR 合并，表明这些功能已被确认并实现，极大概率纳入下一版本：  

- **工具权限弹窗键盘快捷键**（[#1117](https://github.com/netease-youdao/LobsterAI/issues/1117) → PR [#1119](https://github.com/netease-youdao/LobsterAI/pull/1119)）  
- **会话出错后一键 Retry**（[#1120](https://github.com/netease-youdao/LobsterAI/issues/1120) → PR [#1121](https://github.com/netease-youdao/LobsterAI/pull/1121)）  
- **会话内容全文搜索与关键词高亮**（[#1125](https://github.com/netease-youdao/LobsterAI/pull/1125) 虽非 Issue，但为独立新功能 PR）  

此外，PR [#1103](https://github.com/netease-youdao/LobsterAI/pull/1103) 添加了 Docker 沙箱就绪探针，暗示未来可能推进沙箱执行模式的用户可见性。PR [#1138](https://github.com/netease-youdao/LobsterAI/pull/1138) 的工具错误高亮和跳转功能也属于用户呼声较高的易用性改进。

---

## 用户反馈摘要  
从今日关闭的 Issues 评论中可以提取以下用户声音：  

- **对安装流程的不满**：用户“liangshuang24yy-bit”报告在已关闭并退出登录后，安装最新版本时仍弹出“Lobster AI 无法关闭”对话框，感到困惑（[#1124](https://github.com/netease-youdao/LobsterAI/issues/1124)）。  
- **对会话恢复的迫切需求**：用户“MaoQianTu”在 [#1120](https://github.com/netease-youdao/LobsterAI/issues/1120) 中描述“用户完全没有恢复路径——只能手动复制 Prompt，新建会话，粘贴内容重发”，体现了当前错误恢复体验的巨大痛点。该需求已被实现。  
- **对键盘工作流的追求**：用户在 [#1117](https://github.com/netease-youdao/LobsterAI/issues/1117) 提到“移开手来点击，打断了用键盘驱动的编码流”，典型的开发者工作流优化诉求。  
- **对 Agent 管理一致性的困惑**：用户“tzhouzhou”在 [#1139](https://github.com/netease-youdao/LobsterAI/issues/1139) 中反馈重名 Agent 创建后任务记录不立即刷新的问题，虽未修复，但反映了前端状态同步的不足。

---

## 待处理积压  
今日所有 Issues 和 PR 均已关闭，目前公开仓库中 **无长期未响应的开放 Issue 或 PR**。但以下 Issue 虽已关闭但未附带修复 PR，可能需维护者后续跟进：  

- [#1096](https://github.com/netease-youdao/LobsterAI/issues/1096)（Markdown 转 PDF 异常）  
- [#1124](https://github.com/netease-youdao/LobsterAI/issues/1124)（安装器弹窗问题）  
- [#1139](https://github.com/netease-youdao/LobsterAI/issues/1139)（重名 Agent 任务记录未刷新）  

建议维护者在版本发布前确认这些问题的复现环境及是否已在其他 PR 中修复，或明确标记为“无法复现/非预期行为”。

---

*报告生成时间：2026-09-17 18:00 UTC | 数据截止：2026-09-17 00:00 UTC*

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

## Moltis 项目日报 — 2026-09-17

### 1. 今日速览

过去 24 小时内，项目保持中等活跃度：合并了一条酝酿数月的大功能 PR（新增 5 个斜杠命令及辅助模型配置），同时两个面向沙箱和构建加速的 PR 进入待合并状态。Bug 方面，一个关于添加节点后沙箱无法运行的长期 issue 终于关闭；新上报的远程 MCP 服务器崩溃后永不重试的问题（#1271）因影响面广、无临时解决方案，值得社群关注。无新版本发布。

### 2. 版本发布 *(省略)*

### 3. 项目进展

- **#926 [CLOSED] — feat: 新增 5 个斜杠命令及辅助模型配置**  
  由 `penso` 提交，该 PR 引入了 `/btw`（临时侧问）、`/fast`（快速回答）、`/insights`（深层分析）、`/steer`（引导）、`/queue`（队列）五个命令，灵感来自 Hermes Agent 的特性分析。同时新增了辅助模型配置骨架，允许为不同任务调用不同模型。该项目历时近5个月，历经多次迭代后于昨日合并，标志着 Moltis 交互能力的重要扩展。  
  [PR #926](https://github.com/moltis-org/moltis/pull/926)

- **#1272 [OPEN] — feat(sandbox): 每 agent 级挂载、运行用户及强制沙箱**  
  由 `Bergmann89` 提交，允许在 agent 预设中配置独立沙箱挂载路径、容器运行的 uid:gid，以及禁止 agent 在沙箱外运行。此 PR 将沙箱配置粒度从全局下沉至 agent 级别，提升多租户场景的安全性与灵活性。  
  [PR #1272](https://github.com/moltis-org/moltis/pull/1272)

- **#1270 [OPEN] — feat(build): 跨镜像构建缓存 cargo 并脚本化构建**  
  同样来自 `Bergmann89`，通过将 cargo 目标目录和 crate 注册表设为 BuildKit 缓存挂载，使增量构建仅编译变更部分，冷构建从零编译全工作空间耗时虽长，但后续重建仅需几秒。该 PR 将显著改善 CI 和本地迭代效率。  
  [PR #1270](https://github.com/moltis-org/moltis/pull/1270)

### 4. 社区热点

- **#1271 [OPEN] — 远程 MCP 服务器启动失败永不重试，丢失会话导致后续调用全部失败**  
  由 `tomachianura` 报告，描述了 remote MCP over streamable HTTP 的场景中，若服务器启动时失败，`McpManager::start_enabled` 仅记录日志后放弃，健康检查模块只重启状态变化的服务器，导致死掉的服务器永不被重新尝试。更严重的是，如果服务器启动后崩溃导致会话丢失，后续所有对该服务器的方法调用都将失败。该 issue 暂无评论，但缺陷逻辑清晰、影响严重（需要手动重启 Moltis 才能恢复），已引发维护者注意。  
  [Issue #1271](https://github.com/moltis-org/moltis/issues/1271)

- **#1246 [CLOSED] — [bug] 添加节点后无法在沙箱中运行**  
  用户 `maop` 报告，在添加新节点后沙箱功能失效。经过近三周的排查（创建于 8月28日），昨日终于关闭。虽未明确修复方式，但该问题的关闭意味着相关场景恢复正常。  
  [Issue #1246](https://github.com/moltis-org/moltis/issues/1246)

### 5. Bug 与稳定性

| 严重程度 | Issue | 描述 | 修复状态 |
|---------|-------|------|---------|
| 🔴 严重 | [#1271](https://github.com/moltis-org/moltis/issues/1271) | 远程 MCP 服务器启动失败后永不重试，且会话丢失后所有调用失败，需要手动重启 Moltis 才能恢复 | 无关联 PR，待解决 |
| 🟢 已修复 | [#1246](https://github.com/moltis-org/moltis/issues/1246) | 添加节点后沙箱无法运行 | 昨日关闭，推断已合并修复 |

### 6. 功能请求与路线图信号

- **沙箱粒度控制**：PR #1272 新增 agent 级挂载、运行用户和强制沙箱，回应了多租户环境中不同 agent 需要不同文件系统隔离和安全上下文的诉求。该功能很可能进入下一版本。
- **构建缓存与脚本化**：PR #1270 针对开发体验优化，减少反复编译痛点，是持续改进构建流程的信号。
- **斜杠命令扩展**：已合并的 #926 引入指挥官式交互，暗示项目正朝“更细粒度的 LLM 调用控制”方向演进。用户可能进一步期待自定义命令支持。

### 7. 用户反馈摘要

- **#1246** 用户 `maop` 在沙箱节点添加后遭遇运行失败，经过较长时间等待获得关闭。虽然问题已解决，但用户对修复速度可能不太满意（从8月28日至9月16日）。
- **#1271** 用户 `tomachianura` 清晰地描述了远程 MCP 服务器不可恢复的故障模型，指出需要手动重启 Moltis 才能恢复，这是重度用户不可接受的。目前无临时解决方案，请求维护者尽快修复。

### 8. 待处理积压

当前无显著积压的长期未响应 issue 或 PR。但以下待合并 PR 若持续未合并，可能影响开发节奏：
- **#1272** (sandbox per-agent 功能) 创建于 9月16日，目前无冲突，预期较快合并。
- **#1270** (构建缓存) 创建于 9月15日，涉及 CI/构建流程变更，可能需要更多 review。

建议维护者优先关注 **#1271** 的复现与修复，以免影响使用远程 MCP 的用户体验。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我将根据您提供的 GitHub 数据，为您生成 CoPaw (QwenPaw) 项目在 **2026年9月17日** 的动态日报。

---

## 📅 CoPaw 项目动态日报 | 2026年9月17日

### 1. 今日速览

过去24小时内，CoPaw 项目社区活跃度极高，Issues 和 PR 更新数量均维持在较高水平。数据显示，共有 **25 条 Issues 更新**（其中新开/活跃 13 条）和 **37 条 PR 更新**（其中待合并 25 条），体现了社区强烈的参与度和贡献热情。尽管今日无新版本发布，但核心功能（如 Hub 多租户版、实时语音对话）和关键 Bug 修复（尤其是内存泄漏问题）的 PR 正在积极推进中，项目整体处于紧锣密鼓的迭代阶段。不过，部分严重 Bug（如子代理超时、内存泄漏复合路径）的持续讨论也说明稳定性仍是当前必须重点攻克的难题。

### 2. 版本发布

无新版本发布。

### 3. 项目进展

- **核心功能改进与合并：**
  - **[PR #7783] (已合并): fix(ACP): Improves the experience of delegating work to external ACP runners**。修复了外部 ACP runner 回复被重复或碎片化的问题，以及与“collapse-msg”功能相关的错误，提升了 ACP 任务委托的体验。
  - **[PR #4171] (已合并): feat: add memory-distill tool plugin with title-diffing distillation engine**。合并了“记忆蒸馏”工具插件，该插件通过标题差异分析引擎，能实现约 92% 的噪音降低，帮助更好地提炼和整合记忆。
  - **[PR #7120] (已合并): security: enable shell evasion checks by default + regression test**。默认启用所有 7 项 shell 逃逸检查，加强了项目的基础安全性。
  - **[PR #6569] (已合并): fix(console): suppress EIO/EPIPE print errors after detached TTY**。修复了终端关闭后，QwenPaw 进程残留导致的 IO 错误打印问题。

- **重要功能推进中：**
  - **[PR #7779] (开放中): feat(hub): add model gateway, member governance and usage dashboard**。此 PR 为 QwenPaw Hub 增加了模型网关、成员治理和使用仪表盘功能，是迈向多租户版 Hub 的关键一步。
  - **[PR #7785] (开放中): feat(voice): add realtime voice chat**。引入了实时语音对话功能，支持在现有聊天界面中进行语音输入、播放、打断等操作，标志着项目在交互模式上的重大拓展。
  - **[PR #7637] (开放中): feat(qwenpaw-data): QwenPaw-Data app 0.3.0**。推进了 QwenPaw-Data 应用，支持用户连接数据源、通过自然语言提问并生成报告。

**小结**：项目进展迅速，在安全、外部集成、记忆管理和数据交互等多个维度都有所突破。Hub 和语音功能的 PR 尤为引人注目，预示着下一版本将带来重大功能升级。

### 4. 社区热点

- **[Issue #7318] (热门讨论中): QwenPaw Hub, the multi-tenant edition, is coming in 2.2.0: what should we build next?**
  - **热度**：29条评论，4 👍
  - **链接**: [agentscope-ai/QwenPaw Issue #7318](https://github.com/agentscope-ai/QwenPaw/issu...)
  - **分析**：这是关于即将发布的 2.2.0 版本中多租户版 Hub 的公开讨论。社区对此功能呼声极高，开发者正积极收集用户对于团队协同、权限管理等核心功能的建议。这不仅是当前最热的话题，也直接反映了项目从个人工具向平台级产品演进的核心路线。

- **[Issue #7678] (热门讨论中): [Bug]: spawn subAgent**
  - **热度**：9条评论
  - **链接**: [agentscope-ai/QwenPaw Issue #7678](https://github.com/agentscope-ai/QwenPaw/issu...)
  - **分析**：用户报告了一个严重的稳定性问题：通过 `spawn subAgent` 创建的子代理任务全部超时失败，即使设置了很长的超时时间也无法解决。此问题引发了用户对 Multi-Agent 模式下任务调度和可靠性的深切担忧。

- **[PR #6969] (关键待审): fix: avoid duplicate tool result when MCP returns structuredContent (#6958)**
  - **热度**：虽评论数不突出，但修复的是核心工具调用机制的 Bug，且从8月13日起就已处于“Under Review”状态，社区关注度很高。
  - **链接**: [agentscope-ai/QwenPaw PR #6969](https://github.com/agentscope-ai/QwenPaw/PR/6969)
  - **分析**：此 PR 解决了一个在社区中被广泛反馈的问题：当 MCP 工具同时返回文本和结构化内容时，会产生重复结果。

### 5. Bug 与稳定性

以下是今日报告的 Bug，按严重程度排序：

- **严重**:
  - **[Issue #7722] (开放): Memory exhaustion compounds through three paths**。报告了导致容器 OOM 的内存泄漏问题，并详细分析了三条复合路径（无限流缓冲、长连接实例堆积、死循环门卫逃逸）。这是一个影响深远的稳定性问题，如果得不到修复，将严重制约项目在长任务和高并发场景下的部署。**（已有 PR #7808 尝试修复）**
  - **[Issue #7678] (开放): spawn subAgent timeout**。如社区热点所述，子代理创建后全部超时，影响核心 Agent 协作功能，属于严重的功能性错误。

- **中高**:
  - **[Issue #7815] (开放): Console does not recover from a failed lazy page chunk load**。控制台在懒加载页面失败后，UI 陷入死锁，除刷新外无法恢复，严重影响用户体验。
  - **[Issue #7814] & [Issue #7813] (开放): Console SSE robustness gaps**。报告了控制台 SSE 流在遇到空载荷 (`null`) 时会导致整个流卡死，使前端用户无法看到 AI 的流式响应。
  - **[Issue #7799] (已关闭): v2.2.1 Console 仍不显示 Agent 用 send_file_to_user 发送的图片**。这是一个回归问题，指示 `send_file_to_user` 功能在 2.2.1 版本中再次失效，图片只在流式输出时短暂可见。

- **中低**:
  - **[Issue #7689] (已关闭): PDF document blocks still sent to multimodal chat-completions endpoints after #7621**。修复了在特定场景下 PDF 文档块依然会发送给多模态端点的问题。
  - **[Issue #7817] (开放): [Feishu/Lark Channel] p2p 发消息 230101**。报告了飞书渠道 p2p 消息发送失败的集成问题，对特定渠道用户影响较大。

### 6. 功能请求与路线图信号

- **即将到来的功能**:
  - **[Issue #7318]**: **QwenPaw Hub 多租户版**。面向企业/团队的多用户、权限管理功能已被提上日程，是 2.2.0 版本的核心亮点。
  - **[PR #7785]**: **实时语音对话**。从“打字”到“语音”，交互方式的重大迭代，将由一个专门的主题 PR 推进。

- **潜在纳入的功能**:
  - **[Issue #7801] (开放): Feature: chat mode selector - Discuss vs Execute**。社区明确提出了需要“讨论模式”和“执行模式”的区分，以避免 AI 在执行前未经充分讨论就修改文件或执行命令。这一诉求与 Agent 安全可控的理念高度契合，很可能在未来版本中被实现。
  - **[Issue #7809] (开放): Feature: Tool approval cards & notifications are hardcoded English — add i18n support**。用户对国际化（i18n）的需求开始显现，特别是工具审批卡这样的核心交互界面。
  - **[Issue #7797] (已关闭): [Feature]: 希望产物只输出任务目标产出物**。用户希望 Agent 能智能清理中间文件、临时文件，只保留最终产物。这是一个提升用户体验的实用功能。

### 7. 用户反馈摘要

- **痛点与不满**:
  - **稳定性问题突出**：多位用户报告了子代理超时（#7678）和控制台冻结（#7815, #7813）等问题，表明当前版本的可靠性和健壮性尚待提升。
  - **上下文管理失控**：用户 `xiaohushi512` 连续报告了 SubAgent 超时（#7678）和上下文管理相关问题（#7810），情绪较为沮丧，主要问题在于：手动设置的最大上下文长度（131K）总是被突破（达到 271K），且自动压缩功能不触发。
  - **集成问题**：飞书渠道的 p2p 消息发送报错（#7817）和微信渠道的文件 URL 错误（#7792）表明，非 Console 渠道的集成稳定性和适配性存在明显短板。

- **使用场景**:
  - **团队协作**：#7318 的讨论热度表明，大量个人用户开始希望将 QwenPaw 应用于团队场景，对权限管理、模型共享等功能有迫切需求。
  - **内容创作**：Creator 插件相关的 Bug（#7720, #7693）显示，创意工作者正在使用 QwenPaw 进行多图生成等复杂任务，并对 UI 状态一致性和任务调度有专业要求。
  - **自动办公**：用户对任务完成提醒（#7800）、输出产物清理（#7797）等功能的需求，揭示出 AI 助手在日常工作中越来越长的使用时长和对“免维护”体验的期望。

### 8. 待处理积压

- **[PR #6969] (开放): fix: avoid duplicate tool result when MCP returns structuredContent**
  - 状态：**“Under Review” 已超一个月**。
  - 链接: [agentscope-ai/QwenPaw PR #6969](https://github.com/agentscope-ai/QwenPaw/PR/6969)
  - 提醒：这是一个非常核心的 Bug 修复 PR，自 2026-08-13 起就处于未合并状态。它直接影响到工具调用的可靠性，**建议维护者优先处理此 PR，以尽快解决社区广泛反馈的重复结果问题**。

- **[PR #6776] (开放): fix(browser): self-heal dead Playwright driver connections**
  - 状态：**“Under Review” 已超一个月**。
  - 链接: [agentscope-ai/QwenPaw PR #6776](https://github.com/agentscope-ai/QwenPaw/PR/6776)
  - 提醒：浏览器自动化是一个重要场景，此 PR 解决了 Playwright 驱动死后无法恢复的问题。与 #6969 类似，长时间的搁置可能会让社区贡献者的积极性受挫。

- **[Issue #7650] (开放): 来着频道的参数如何透传给mcp工具**
  - 状态：虽然被标记为 `wontfix`，但用户提问并未得到明确、详细的“指导”，而只是被标记状态。
  - 链接: [agentscope-ai/QwenPaw Issue #7650](https://github.com/agentscope-ai/QwenPaw/issu...)
  - 提醒：对于这种“如何实现某功能”的提问，即使不在项目计划内，给予更具体的技术指引或文档建议，也有助于维护良好的社区氛围。

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，以下是为您生成的 ZeroClaw 项目动态日报。

---

# ZeroClaw 项目日报 | 2026-09-17

## 今日速览

ZeroClaw 项目今日保持极高的活跃度，24小时内产生了36条Issue更新和50条PR更新，但PR合并效率较低，积压量高达47个。社区讨论焦点集中在**Rust代码反“Slop”政策清理**、**维护者决策队列**以及对**Slack频道扩展**和**浏览器工具功能补全**的强烈需求上。项目在**运行时稳定性**（如Panic修复）和**配置管理**（如原子性批量写入）方面有重要进展，但大量高风险PR（如代理生命周期协调、RPC认证）仍处于待审状态，成为项目发展的主要瓶颈。

## 项目进展

- **运行时稳定性提升**：PR [#10134](https://github.com/zeroclaw-labs/zeroclaw/pull/10134) 被合并，将运行时中17个可能导致Panic的位置（如`unwrap`、`unreachable!`）转换为更安全的错误返回或故障关闭逻辑，显著提升了代理调度、工具注册等核心路径的健壮性。
- **ACP协议测试完善**：PR [#10913](https://github.com/zeroclaw-labs/zeroclaw/pull/10913) 提出了一个新的测试，通过JSON-RPC协议栈驱动ACP（Agent Communication Protocol）的`deliver_file`交互，替代了之前的直接处理器调用，使测试更接近真实场景。
- **配置管理迈向原子化**：PR [#10911](https://github.com/zeroclaw-labs/zeroclaw/pull/10911) 引入了“原子性实时修订”功能，旨在解决配置保存后，无法确定哪些运行中的消费者已应用更改的问题（关联Issue #10892），为未来的实时配置变更打下了基础。

## 社区热点

1.  **Rust代码反“Slop”政策债务清理（[#10118](https://github.com/zeroclaw-labs/zeroclaw/issues/10118)）**：评论数达到16条，是本日最受瞩目的议题。该Issue旨在系统性地清理代码中不符合“反Slop”政策的Rust模式，涉及超过300个候选问题点，覆盖生产代码中的Panic、不安全代码、错误处理不当等。这反映出社区对代码质量和安全性的高度重视，是一场大规模、有组织的代码健康度改进行动。

2.  **维护者决策队列（[#8692](https://github.com/zeroclaw-labs/zeroclaw/issues/8692)）**：15条评论紧随其后。这是一个关于流程的Issue，提出建立一个统一的“维护者决策队列”，用于跟踪RFC、设计问题和发布政策等需要维护者决策的议题。这表明随着项目规模扩大，社区正在积极寻求更高效的决策和沟通机制，避免关键议题被淹没在大量Issue中。

## Bug 与稳定性

- **严重（S2 - 降级行为）且高风险：**
    - **工具返回图像丢失（[#10885](https://github.com/zeroclaw-labs/zeroclaw/issues/10885)）**：用户反馈在同一个对话轮次中，执行一个不相关的工具调用后，之前由其他工具返回的图像会消失。已有修复PR或关联任务（标签 `follow-up`）。
    - **非视觉模型因图像标记引发错误（[#10887](https://github.com/zeroclaw-labs/zeroclaw/issues/10887)）**：当用户消息中包含类似图像的标记文本（即使未指向可加载图片）时，非视觉模型会直接返回`ProviderCapabilityError`，导致对话中断。
    - **流式文本防护误触发（[#10912](https://github.com/zeroclaw-labs/zeroclaw/issues/10912)）**：流式输出中的“文本防护”机制过于敏感，当普通文本中包含类似工具结果格式的内容时，会直接抑制整个回复，并重试3次后报错。
- **中等（S3 - 小问题）：**
    - **Telegram媒体组测试超时（[#10883](https://github.com/zeroclaw-labs/zeroclaw/issues/10883)）**：CI中的一个测试`media_group_listener`在并行运行时会出现间歇性失败，提示有竞争条件或超时问题。

## 功能请求与路线图信号

- **异步函数工具（[#10704](https://github.com/zeroclaw-labs/zeroclaw/issues/10704)）**：提出希望支持OpenAI Response API中的异步工具调用，让模型在后台工具未执行完时能继续处理其他任务，从而提高效率。这是一个影响架构的重要特性请求，可能纳入下一阶段路线图。
- **浏览器工具功能扩展（[#9945](https://github.com/zeroclaw-labs/zeroclaw/issues/9945)）**：用户指出当前的`browser`工具仅暴露了底层`agent-browser`库100多个命令中的16个，导致iframe、对话框、标签页和表单控件等操作无法实现。该请求具有高风险标签，是提升浏览器自动化的关键需求。
- **Slack Events API模式（[#9022](https://github.com/zeroclaw-labs/zeroclaw/issues/9022)）**：请求为Slack频道增加HTTP Request URL模式，以支持按需伸缩的部署模式，同时提升实时性。已有相应PR在讨论中。

## 用户反馈摘要

- **核心痛点**：用户对“工具返回图像在下一轮丢失”[#10885] 感到困扰，这直接影响了多模态交互体验。此外，“Cron任务执行时缺乏上下文”[#6105] 也是一个持续存在的痛点，导致定时任务的效果不佳。
- **使用场景**：用户希望利用ZeroClaw进行更复杂的任务编排，比如“有界子代理循环进行网络调研”[#9833]，以及通过“SOP引擎”实现可暂停/恢复的流程控制[#9687]。
- **满意点**：项目对“Rust代码质量控制”的持续投入[#10118] 获得了社区的积极响应和长评论讨论。对“RPC配置原子写入”[#10823] 功能的开发响应了用户对配置管理稳定性的需求。

## 待处理积压

以下Issue和PR长期未得到关键维护者的响应或合并，已成为项目健康度的潜在风险：

1.  **高风险PR积压**：
    - **[#10241](https://github.com/zeroclaw-labs/zeroclaw/pull/10241) - 修复频道驱动的Shell审批路由**：涉及多个频道和安全性，影响范围广，但状态仍为`needs-maintainer-review`。
    - **[#10259](https://github.com/zeroclaw-labs/zeroclaw/pull/10259) - 为RPC强制认证用户**：是RPC安全性的关键环节，依赖其他PR，且尺寸为XL，社区作者（JordanTheJet）已贡献巨大工作量。
    - **[#10621](https://github.com/zeroclaw-labs/zeroclaw/pull/10621) - 协调代理生命周期突变**：这是一个XL尺寸的核心改动，涉及运行时、网关、CLI等多个模块，一旦合并将影响深远，但维护者尚未给出明确审查结论。
2.  **等待作者响应**：
    - **[#9833](https://github.com/zeroclaw-labs/zeroclaw/pull/9833) - 添加web_research工具** 和 **[#9134](https://github.com/zeroclaw-labs/zeroclaw/pull/9134) - 插件修复**：都标记为 `needs-author-action`，可能因维护者需要更多信息或修改而导致停滞。
3.  **RFC/设计决策阻塞**：
    - **[#7497](https://github.com/zeroclaw-labs/zeroclaw/issues/7497) - OCI注册表插件存储RFC**：高风险、关键特性（插件分发），因状态被`blocked`而长时间无进展。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*