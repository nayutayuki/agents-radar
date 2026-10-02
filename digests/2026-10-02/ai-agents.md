# OpenClaw 生态日报 2026-10-02

> Issues: 500 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-10-02 01:48 UTC

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

# OpenClaw 项目动态日报 – 2026-10-02

---

## 1. 今日速览

OpenClaw 项目在过去 24 小时保持**极高活跃度**：共处理 500 条 Issue 更新（其中新开/活跃 278 条、关闭 222 条）和 500 条 PR 更新（待合并 291 条、合并/关闭 209 条）。新发布的 **v2026.8.34 extended-stable** 带来了安全修复与性能改进，但社区焦点集中在主分支 `2026.9.x` 系列上大量 **P0/P1 崩溃与回归问题**，尤其是 Windows 兼容性、SQLite 内存泄漏和 Gateway 启动阻塞等严重故障。维护者已提交多项修复 PR，项目整体处于“修复冲刺”阶段，健康度因高频回归事件而承压。

---

## 2. 版本发布

- **[v2026.8.34](https://github.com/openclaw/openclaw/releases/tag/v2026.8.34)**（gateway-only `extended-stable`）
  - 基于 2026 年 8 月底代码，叠加关键安全更新、可靠性/性能修复，以及新型号支持。
  - 这是当前等效于 LTS 的稳定分支，适合对最新功能不敏感的生产环境。
  - **破坏性变更**：无明确说明，但建议从早期版本升级的用户参考 `openclaw doctor` 迁移说明。
  - **迁移注意**：若从 2026.7.x 或更早版本升级，需确认网关配置与插件兼容性。

---

## 3. 项目进展

今日合并/关闭的 PR 共 209 条，以下为代表性的重要修复与推进：

- **[fix(update): capped update report drops Recovery and Verification when warnings fill it](https://github.com/openclaw/openclaw/pull/162146)**（已合并）：修复升级报告因警告过长而截断恢复/验证信息的问题，提升升级安全性。
- **[fix: completion turns lose delegation tools after same-model retries](https://github.com/openclaw/openclaw/pull/163032)**（已合并）：修复同模型重试后协调者丢失委托工具的问题，确保工作流连续性。
- **[fix(ios): enable x.ai realtime voice with reliable audio and spoken confirmations](https://github.com/openclaw/openclaw/pull/163146)**（开放中）：iOS 实时语音可靠性改进（关联 #163122、#138355），提供口播确认支持。
- **[fix(workers): settle remote turn ownership](https://github.com/openclaw/openclaw/pull/161759)**（开放中）：解决远程 Worker 取消/恢复后工作区归属竞争问题，提高多节点稳定性。
- **[perf(nodes): load only what a worker turn needs](https://github.com/openclaw/openclaw/pull/160442)**（开放中）：按需加载 Worker 能力，减少内存占用和首响应延迟。

整体来看，项目在**稳定性修复、性能优化、跨平台兼容（尤其是 Windows）、会话管理层**上取得了显著推进，但仍有大量高优先级 PR 待合并。

---

## 4. 社区热点

以下 Issue 和 PR 在今日讨论最为活跃，反映了用户核心诉求：

| 编号 | 标题 | 评论数 | 核心诉求 |
|------|------|--------|----------|
| [#143524](https://github.com/openclaw/openclaw/issues/143524) | [Bug]: Agent SQLite WAL 增长至 1.4–2.8 GB 且无法 checkpoint | 103 | 数据库性能灾难，Windows 用户尤其严重 |
| [#153257](https://github.com/openclaw/openclaw/issues/153257) | [Bug]: OpenClaw 2026.9.5 将稳定环境变为 8 小时故障恢复 | 40 | 升级后完全崩溃，用户强烈不满 |
| [#149538](https://github.com/openclaw/openclaw/issues/149538) | Gateway 就绪但不服务，/health 超时 | 23 | 大规模部署下网关假死 |
| [#157067](https://github.com/openclaw/openclaw/issues/157067) | Windows 下隔离 cron 设置传递不可克隆的 Proxy | 21 | Windows 平台任务调度失败 |
| [#139710](https://github.com/openclaw/openclaw/issues/139710) | mid-turn 插件热更新导致系统代理丢失回复 | 18 | 插件热加载可靠性问题 |
| [#159662](https://github.com/openclaw/openclaw/issues/159662) | prepared-model-catalog.worker.js 内存泄漏 ~4-5 GB/h | 14 | 内存泄漏导致服务不可用，provider 无关 |

**分析**：用户普遍受到**稳定性回归**和**Windows 兼容性**的困扰，尤其是 `2026.9.5`、`2026.9.6` 版本引入的严重问题。SQLite 不受控增长和内存泄漏是高频反馈，体现了对长期运行可靠性的迫切需求。

---

## 5. Bug 与稳定性

今日报告的 Bug 中按严重程度排列如下（标注是否存在修复 PR）：

| 等级 | Issue | 摘要 | 修复状态 |
|------|-------|------|----------|
| P0 | [#143524](https://github.com/openclaw/openclaw/issues/143524) | Agent SQLite WAL 无限增长，阻塞 Gateway 启动 | 尚无 fix PR，标记 `clawsweeper:no-new-fix-pr` |
| P0 | [#153257](https://github.com/openclaw/openclaw/issues/153257) | 升级 2026.9.5 后 8 小时故障恢复 | 标记 `clawsweeper:manual-only` |
| P0 | [#159662](https://github.com/openclaw/openclaw/issues/159662) | `prepared-model-catalog.worker.js` 内存泄漏 4-5 GB/h | 标记 `clawsweeper:needs-maintainer-review` |
| P0 | [#160521](https://github.com/openclaw/openclaw/issues/160521) | Gateway 崩溃：state DB 读取封印 → Worker 关闭 → 未处理拒绝 | 标记 `clawsweeper:needs-maintainer-review` |
| P0 | [#155859](https://github.com/openclaw/openclaw/issues/155859) | Gateway 启动时间随插件数量线性增长（120 秒预算耗尽） | 无 fix PR |
| P0 | [#158239](https://github.com/openclaw/openclaw/issues/158239) | 慢主机（kernel <5.6）Gateway 启动失败 | 无 fix PR |
| P0 | [#161953](https://github.com/openclaw/openclaw/issues/161953) | Windows 上 sessions.create 总是失败（`\\?\` 路径泄露） | 已关闭，修复在 [#161654](https://github.com/openclaw/openclaw/pull/161654) 中 |
| P0 | [#161828](https://github.com/openclaw/openclaw/issues/161828) | Windows 上 chat.send/heartbeat 仍因 DataCloneError 失败（根因未完全修复） | 开放中 |
| P0 | [#160386](https://github.com/openclaw/openclaw/issues/160386) | 2026.9.6 大会话库导致 SQLite I/O 压力与 WebUI 超时 | 无 fix PR |
| P0 | [#115642](https://github.com/openclaw/openclaw/issues/115642) | Billing cooldown 超时后仍阻塞 5 小时，缺乏探测恢复 | 无 fix PR |
| P1 | [#85030](https://github.com/openclaw/openclaw/issues/85030) | MCP 工具未注入子代理会话 | 已有相关 PR，但未关闭 |
| P1 | [#114612](https://github.com/openclaw/openclaw/issues/114612) | memory-core 表无限增长 | 无 fix PR，dupe parent |
| P1 | [#97616](https://github.com/openclaw/openclaw/issues/97616) | 钩子/工具子进程泄漏导致僵尸进程堆积 | 无 fix PR |

**结论**：当前存在大量 P0 恶性 Bug，尤其是在 Windows 和大规模部署场景下。部分关键修复（如 #161654、#163032）已被合并，但仍有多个 `clawsweeper:no-new-fix-pr` 问题等待维护者介入。

---

## 6. 功能请求与路线图信号

今日活跃的功能请求多来自长期积压，但部分可能与下一版本（2026.10.x）相关：

- **[Feature: Add denylist support for exec-approvals](https://github.com/openclaw/openclaw/issues/6615)**（P2，2026-02-01）：支持“允许全部，但阻止特定命令”的安全策略，已有 PR [#71097](https://github.com/openclaw/openclaw/issues/71097) 讨论类似方向。
- **[Feature: Audit log for agent memory changes](https://github.com/openclaw/openclaw/issues/20935)**（P2，2026-02-19）：添加记忆变更审计日志，适合合规需求场景。
- **[Improve Codex app-server steady-state CPU and helper process overhead](https://github.com/openclaw/openclaw/issues/84037)**（P1）：Codex 运行时 CPU 优化，已有讨论但未进入开发。
- **[Feature: Add denylist mode to exec.security for balanced security](https://github.com/openclaw/openclaw/issues/71097)**（enhancement，P2）：与 #6615 互补，可能合并为一个 PR。

**路线图信号**：Denylist 策略和记忆审计功能社区呼声较高，且已有成熟讨论，有望在 `2026.10.x` 或 `extended-stable` 后续版本中实现。Codex 性能优化则依赖于架构改进。

---

## 7. 用户反馈摘要

从评论区提炼真实用户声音：

- **“升级 2026.9.5 是我最后悔的决定，我的生产环境直接崩了 8 小时。”**（#153257）—— 强调版本回退机制和更严格的发布测试的必要性。
- **“SQLite WAL 在 Windows 上两天长到 2.8 GB，不得不手动 truncate。”**（#143524）—— 数据库管理功能缺失，用户期待自动维护。
- **“在 Windows 上每次运行 cron 都报 DataCloneError，完全无法使用。”**（#161654, #161828）—— Windows 用户群体感到被忽视，要求第一等支持。
- **“我们的 632 个 Agent 集群，Gateway 就绪后什么都不响应，必须 OOM 重启。”**（#149538）—— 大型企业用户对大规模部署的稳定性提出严肃质疑。
- **“插件热加载 mid-turn 会导致 agent 失去所有回复能力，而且错误提示指向了 `openclaw onboard` 这个误导性修复。”**（#139710）—— 用户体验设计问题：错误提示应指引正确排查方向。

**整体情绪**：用户对高级功能（如 MCP、记忆、实时语音）表示认可，但对 **2026.9 系列版本的稳定性强烈不满**，尤其是 Windows 和大规模场景。积极的一面是，社区修复响应速度较快（如 #163032 合并），且维护者正在批量处理 Windows 相关 Bug。

---

## 8. 待处理积压

以下 Issue/PR 长期未获足够关注，可能阻碍项目健康：

| 编号 | 类型 | 摘要 | 最后更新 | 备注 |
|------|------|------|----------|------|
| [#97616](https://github.com/openclaw/openclaw/issues/97616) | Bug | 钩子/工具子进程未收割导致僵尸堆积（P1，2026-06-29） | 2026-10-02 有更新但无 fix | 可能影响长期运行稳定性 |
| [#114612](https://github.com/openclaw/openclaw/issues/114612) | Bug | memory-core 表无保留策略，磁盘无限增长（P1，2026-07-27） | 2026-10-01 更新 | 父级 dedup，无开发动作 |
| [#114211](https://github.com/openclaw/openclaw/issues/114211) | Bug | Matrix 房间代理循环重启（P1，2026-07-27） | 2026-10-02 有讨论 | 需要 live-repro |
| [#6615](https://github.com/openclaw/openclaw/issues/6615) | Feature | exec-approvals 添加拒绝列表（P2，2026-02-01） | 已有 PR 但停滞 | 安全增强需求高 |
| [#71097](https://github.com/openclaw/openclaw/issues/71097) | Feature | exec.security 拒绝列表模式（P2，2026-04-24） | 2026-10-01 无实质进展 | 可与 #6615 合并推进 |
| [#20935](https://github.com/openclaw/openclaw/issues/20935) | Feature | 记忆变更审计日志（P2，2026-02-19） | 2026-10-01 更新 | 设计复杂度较高 |
| [#88084](https://github.com/openclaw/openclaw/issues/88084) | PR | 批准命令绕过活跃回复通道（P2，2026-05-29） | 等待作者回复 | 影响审批工作流 |
| [#114

---

## 横向生态对比

# 个人 AI 智能体开源生态横向对比日报分析（2026-10-02）

---

## 1. 生态全景

当前个人 AI 智能体/自主代理开源生态正处于 **“大规模整合与基础设施巩固”** 阶段。以 OpenClaw 为代表的旗舰项目在快速迭代中遭遇了严重的稳定性回归，尤其是 Windows 兼容性和数据库可靠性问题，迫使社区和开发者将重心从“功能堆叠”转向“缺陷修复与质量巩固”。与此同时，众多衍生/垂直项目（如 NanoBot、IronClaw、ZeroClaw）在并发控制、安全边界、插件系统等底层能力上加速攻坚，但整体呈现 **“头部承压、中间分化、尾部活跃”** 的格局。一个显著趋势是**持久化、多模态交互（Telegram/Discord 等平台）和跨实例协作**成为社区共同诉求，而**安全配置审计与去中心化身份管理**开始从企业用户渗透至开源社区。

---

## 2. 各项目活跃度对比

| 项目 | 今日 Issues 更新 | 今日 PR 活跃 | 今日版本发布 | 健康度评估 | 核心动态 |
|------|----------------|-------------|-------------|-----------|----------|
| **OpenClaw** | 500（278新开/222关闭） | 500（291待合并/209合并） | v2026.8.34 extended-stable | ⚠️ 承压（高频回归） | 修复冲刺，P0/P1 密集，Windows/SQLite/网关问题 |
| **NanoBot** | 0 | 3合并，17活跃 | 无 | ✅ 良好（平稳维护） | 代码清理，P1安全修复积压 |
| **Hermes Agent** | 50（新开/关闭未注明） | 50（全部待合并） | 无 | ⚠️ 高活跃但合并停滞 | P0性能问题（缓存失效），跨网关协作延期 |
| **PicoClaw** | 2新 | 2合并，12待合并 | 无 | ⚠️ 中等偏风险（官网宕机） | 证书过期3周未处理，多智能体框架合并 |
| **NanoClaw** | 4新 | 15合并，11待合并 | 无 | ✅ 良好（紧凑高效） | 安全/依赖加固，CI/CD，Discord修复 |
| **NullClaw** | 0 | 0 | 无 | ⏸️ 沉睡 | 无任何活动 |
| **IronClaw** | 2新 | 2待合并 | 无 | ✅ 良好（稳步推进） | 浏览器持久化、身份集成讨论活跃 |
| **LobsterAI** | 7更新（历史） | 7合并 | 无 | ⚠️ 中等（历史Bug积压） | OpenClaw兼容/UI修复，但多个半年前Bug未解决 |
| **TinyClaw** | 0 | 3历史清理 | 无 | ✅ 积极（清债利好） | Telegram 可靠性/交互/实时推送完成 |
| **Moltis** | 0 | 2待合并 | 无 | ✅ 低活跃但高质量 | TLS ALPN修复，MCP会话恢复 |
| **CoPaw** | 7新 | 2合并，7待合并 | 无 | ✅ 良好（团队响应快） | DeepSeek PDF破坏会话（P0），局域网回归 |
| **ZeptoClaw** | 0 | 0 | 无 | ⏸️ 沉睡 | 无活动 |
| **ZeroClaw** | 38活跃（更新） | 50待合并（0合并） | 无 | ⚠️ 承压（发布冲刺前） | 安全/权限重构，插件系统冲刺，社区对回归不满 |

**活跃度分层**：
- **极高（日Issue/PR>100）**：OpenClaw
- **高（日>10）**：Hermes Agent, NanoClaw, ZeroClaw
- **中（5-10）**：PicoClaw, CoPaw, LobsterAI
- **低（<5）**：NanoBot, IronClaw, TinyClaw, Moltis
- **无活动**：NullClaw, ZeptoClaw

---

## 3. OpenClaw 在生态中的定位

OpenClaw 作为个人 AI 智能体领域的 **“内核级基础设施”**，其地位相当于 Linux 领域的 Linux Kernel——绝大多数衍生产品（PicoClaw, NanoClaw, ZeroClaw, LobsterAI 等）在底层依赖或参考其架构。其优势体现在：

- **社区规模与贡献者深度**：日处理 500+ Issues/PRs，远超所有同类项目之和。
- **版本规划成熟**：拥有 `extended-stable` LTS 分支，并有明确的里程碑（2026.9.x 功能分支）。
- **平台/模型兼容性**：覆盖 Windows、macOS、Linux，支持数十种 LLM Provider。

**但当前脆弱性也最突出**：2026.9.x 系列引入的大量回归（P0 级 SQLite 失控、Gateway 假死、8小时恢复）使其在生产环境和 Windows 用户中声誉受损。相比之下，**NanoClaw** 和 **TinyClaw** 通过更紧凑的发布策略和聚焦修复实现了更高的稳定性满意度。**OpenClaw 的衍生产品通过锁定稳定分支、叠加定制补丁来对冲其主线的波动性。**

**技术路线差异**：
- OpenClaw 强调 **统一的网关-工作节点-插件架构**，支持高度定制（插件热更新、多会话管理），但复杂度导致回归频发。
- NanoBot 和 Hermes Agent 更侧重于 **轻量化、嵌入式运行时**，以较低的功能密度换取可预测性。
- TinyClaw 和 Moltis 则专注于 **特定协议（Telegram、MCP）的深度优化**，通过缩小范围降低风险。

---

## 4. 共同关注的技术方向

| 技术方向 | 涉及项目 | 具体诉求 |
|----------|---------|----------|
| **数据库/持久化可靠性** | OpenClaw, NanoClaw, ZeroClaw, LobsterAI | SQLite WAL 无限增长、内存泄漏、配置保存清空文件、会话状态丢失 |
| **Windows 平台兼容性** | OpenClaw, Hermes Agent, LobsterAI, CoPaw | 路径泄露（`\\?\`）、DataCloneError、PowerShell 目录创建失败、Cron/更新工具失效 |
| **多平台 IM 集成稳定性** | OpenClaw, NanoClaw, Hermes Agent, TinyClaw, CoPaw | Discord 按钮参数冲突、Telegram 消息丢失/格式/流式、Slack thinking状态缺失、WeCom/Matrix 截断 |
| **实时通信与交互** | OpenClaw, TinyClaw, Moltis, CoPaw | WebSocket 升级失败、流式数据行缓冲（SSE 丢失）、MCP 会话恢复、后台任务唤醒 |
| **安全与访问控制** | NanoBot, ZeroClaw, OpenClaw, IronClaw, NanoClaw | 受限 Shell 沙箱绕过、代理凭证写入可读 systemd 文件、命令拒绝列表（denylist）、去中心化身份、审计日志 |
| **跨实例/分布式协作** | OpenClaw, Hermes Agent, ZeroClaw, PicoClaw | 跨网关 Agent 协作、远程 Worker 归属竞争、多租户内存隔离 |
| **多智能体协同框架** | Hermes Agent, PicoClaw, ZeroClaw, CoPaw | 跨 Bot/网关协作、共享上下文池（Blackboard）、Human-in-the-Loop 工具、群聊稳定性 |
| **插件生态与扩展性** | OpenClaw, NanoClaw, ZeroClaw, CoPaw | 本地插件安装、插件热加载/热更新可靠性、主题语义扩展点、版本兼容性（WIT） |

**最突出的共性痛点**：**数据库持久化**（尤其 SQLite 和 WAL）和 **Windows 兼容性** 是生态级短板，影响所有用户群体的基础信任。

---

## 5. 差异化定位分析

| 维度 | OpenClaw | NanoBot | Hermes Agent | PicoClaw | NanoClaw | TinyClaw | Moltis | CoPaw | ZeroClaw |
|------|----------|---------|--------------|----------|----------|----------|--------|-------|----------|
| **功能侧重** | 全栈 AI Agent 平台 | 精简运行时/嵌入库 | 跨网关协作+桌面端 | 轻量移动/嵌入式 IoT | 生产级安全运维 | Telegram 极致集成 | MCP/Secret AI 协议 | 团队协作/多 Provider | 零信任/安全优先 |
| **目标用户** | 高级用户/企业/开发者 | 资源受限设备/库调用 | 中大型部署/实验性团队 | 边缘设备/RISC-V | 安全敏感的生产环境 | Telegram Bot 开发者 | 协议研究者/去中心化 App | 多语言团队/企业 | 零信任架构采纳者 |
| **技术架构** | 网关+Worker+插件（高耦合） | 单进程运行时（低耦合） | 分布式 Worker 集 | 轻量单会话架构 | 增强安全栈+CI/CD | 单协议深度绑定 | 纯 Rust/高性能 | Provider 适配层+UI | 运行时边界+插件系统 |
| **核心风险** | 回归频发，生产不稳定 | 功能稀疏，迭代慢 | 协作功能长期积压 | 基础设施（证书）维护缺失 | 社区规模较小 | 功能范围窄（仅 Telegram） | 活跃度过低 | DeepSeek 兼容性脆弱 | 发布冲刺质量不确定 |
| **技术路线** | 功能驱动，快速迭代 | 稳定优先，慎重构 | 社区驱动，讨论主导 | 衍生 OpenClaw，定制化 | 自动化+安全左移 | 需求驱动，精准修复 | 协议先行，少而精 | 面向生产痛点，快速响应 | 安全性+模块化 |

---

## 6. 社区热度与成熟度

**快速迭代阶段（功能新增为主，稳定性承压）**：
- **OpenClaw** – 最活跃但最不稳定的旗舰，用户群大，社区情绪“又爱又恨”。
- **ZeroClaw** – 正在全力冲刺 v0.8.6 发布，社区对安全/权限改革寄予厚望，但积压严重。
- **Hermes Agent** – 讨论活跃（跨网关协作、桌面端性能），但维护者响应滞后，PR 堆积。

**质量巩固阶段（修复为主，辅以小幅增强）**：
- **NanoClaw** – 高效的 CI/CD 和安全修复，社区满意度较高，适合生产依赖。
- **LobsterAI** – 积极合并修复，但半年前的历史 Bug 未解决，表现为“修复积压不如问题产生速度”。
- **CoPaw** – 团队响应快，但 DeepSeek 等 Provider 兼容性问题仍在发酵。

**稳定维护/蓄力阶段（活动低频但有突破）**：
- **NanoBot** – 代码清理为主，无重大发布，适合作为底层库稳定使用。
- **TinyClaw** – 清理历史债务，Telegram 集成完善，典型“小而美”。
- **Moltis** – 专注于 MCP 协议，低活跃但修复质量高。
- **PicoClaw** – 有创新（多 Agent 框架），但基础设施维护（证书）暴露管理短板。

**僵化/沉睡**：
- **NullClaw, ZeptoClaw** – 无任何活动，可能已冻结。

---

## 7. 值得关注的趋势信号

1. **“回归灾难”倒逼质量文化升级**  
   OpenClaw 的 `2026.9.5` 升级导致用户生产环境故障 8 小时（#153257），以及 NanoBot/ZeroClaw 的回归问题，正在推动社区呼吁更严格的回归测试、版本回退机制及自动化 CI 防线。**启示：任何 AI Agent 项目若缺乏 24 小时内的热修复管道和版本锁定机制，将难以获得企业信任。**

2. **数据库持久化成为最大的系统性风险**  
   从 OpenClaw 的 SQLite WAL 失控（#143524）、ZeroClaw 的 `Config::save()` 清空文件（#10495）到 NanoClaw 的 PreCompact 钩子失败，**持久化层（尤其是 SQLite）屡屡成为事故源头**。趋势：社区开始审视内置数据库的适用性，探索 WAL 管理策略、自动 checkpoint 及事务隔离改进。**对开发者：若构建 AI 应用，优先选择托管数据库或引入严格的灾备策略。**

3. **“平台围墙”迫使跨实例/跨网关协作成为刚需**  
   Hermes Agent 的 #97681（跨网关协作）积累了超过 30 条评论，PicoClaw 合并了多 Agent 共享上下文框架（#423），ZeroClaw 也推进了运行时嵌入边界。这表明**单一 Agent 已无法满足复杂用户需求**，未来需支持 Agent 之间、甚至不同 Instance 之间的任务拆分与结果合并。**启示：分布式 Agent 编排将成为下一个竞争焦点。**

4. **安全配置的“可审计性”从企业走向社区**  
   多个项目（NanoClaw #3990 安全审计工具，ZeroClaw 权限模型重塑，OpenClaw #6615 Denylist）显示，**用户不再满足于“能用”，而是要求可配置、可审计、可隔离的安全策略**。尤其是本地凭证管理（systemd 权限、密钥存储）引发广泛关注。**趋势：安全即特性的理念正从云原生下沉到边缘 AI 设备。**

5. **非英语/多语言社区的影响力上升**  
   LobsterAI（网易出身）收到大量 CJK 渲染相关反馈（#8068 #8067），CoPaw 也被 Chinese 用户提及。同时 TinyClaw 专注 Telegram（全球普及平台）而非纯英文场景。**这表明个人 AI 智能体正在突破英语中心社区，本地化渲染、IM 协议适配（WeChat、Discord、Telegram、WhatsApp）成为差异化关键。**

6. **“人机协同”交互模式（HITL）显性化**  
   CoPaw 的 #6274（ask_user_question 结构化 HITL 工具）获得社区强烈共鸣，TinyClaw 实现了 Telegram 内联键盘问答（#67），OpenClaw 也在修复审批卡过期机制。**这表明用户不满足于完全自主的 AI，而是希望在高风险决策中保持控制，即“回滚、确认、超时”成为标配。**

---

**总结**：当前生态处于 **“大浪淘沙”** 阶段，所有项目都在与自身增长带来的复杂度做斗争。OpenClaw 作为领头羊正承受最猛烈的批评，但其衍生产品（NanoClaw, TinyClaw）通过聚焦细分场景实现了局部领先。对于开发者而言，**短期应优先选择稳定性记录良好的项目（NanoClaw, TinyClaw, Moltis）**，并密切关注 OpenClaw 修复冲刺的结果以及对衍生组件的更新影响；**中期需关注跨实例协作、安全审计和 HITL 交互模式的标准化趋势**，这些将定义下一代个人 AI 智能体的能力边界。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据 NanoBot 项目在 2026-10-02 的 GitHub 数据生成的日报。

---

## NanoBot 项目动态日报 | 2026-10-02

**项目名称:** NanoBot (github.com/HKUDS/nanobot)
**数据时间范围:** 2026-10-01 至 2026-10-02
**分析师:** AI 分析师

---

### 1. 今日速览

今日 NanoBot 项目主要处于 **内部清理与长期PR持续迭代** 的阶段。过去 24 小时内，项目没有新的 Issue 被提出或关闭，表明社区报告新问题的节奏平稳。活跃度主要体现于 Pull Request (PR) 的持续更新，共有 17 条 PR 处于活跃状态。虽然大部分为历史遗留的 PR，但其持续的更新和合并活动（3 条合并/关闭）表明维护团队仍在积极推动代码重构、稳定性修复和安全加固。总体而言，项目 **健康度良好**，但近期缺乏新的 Feature 发布或重大版本更新，开发重心偏向于基础架构的巩固。

### 2. 版本发布

无

### 3. 项目进展

过去 24 小时内，项目有 3 条 PR 被合并或关闭。其中，`#5999` 在今日被关闭，这是一项重要的代码清理工作。

- **[CLOSED] PR #5999: refactor: remove unused runtime and WebUI helpers** (by chengyongru)
  - **摘要**: 该 PR 旨在移除随着运行时所有权变更和 WebUI 传输层演进后不再使用的辅助函数，包括重复的域名操作设置、无调用者的微信包装器，以及过时的测试代码。
  - **分析**: 此 PR 的关闭标志着项目在 **代码现代化和架构精简** 上又迈出了一步。清理无用代码有助于降低未来维护的复杂性，并减少潜在的 Bug 引入点。这通常是大型重构（如我们之前看到的 Session 状态迁移和 WebUI 传输改动）完成后的标准操作。
  - **链接**: [PR #5999](https://github.com/HKUDS/nanobot/pull/5999)

### 4. 社区热点

今日没有发现评论数量和点赞数特别高的热点 Issue 或 PR。这表明当前社区讨论的焦点主要集中在维护者推动的工作上，而非由社区单个热点事件驱动。

尽管如此，以下 PR 因其复杂度高、影响范围广，持续受到关注，是社区演进的核心：
- **PR #5941 (feat: webui):** 实现本地 WebUI 连接远程 NanoBot 实例的功能。这是对用户体验的重大增强，预计讨论热度会随其接近合并而上升。
- **PR #5536 (fix(exec)):** 修复受限 Shell 缺乏沙箱时的安全性问题，被评为 **P1** 优先级，是项目安全性的核心保障。
- **PR #5885 (feat(memory)):** 优化内存压缩逻辑，防止简短会话被总结后降低恢复质量。这是一个用户感知度很高的性能优化。

### 5. Bug 与稳定性

今日没有新的 Bug 报告。但项目有一系列高优先级的 Bug 修复 PR 正在积压中，主要涉及数据安全、会话一致性和 WebUI 行为。按严重性排序如下：

1.  **P0 关键**
    - **[OPEN] PR #5953: fix(tools): atomic writes for file tools** (by louisss1016)
      - 修复文件写入工具（WriteFileTool等）可能因系统崩溃或并发读取导致数据损坏（torn read）的问题。 **这是当前最严重的稳定性修复之一**。
      - 链接: [PR #5953](https://github.com/HKUDS/nanobot/pull/5953)

2.  **P1 高**
    - **[OPEN] PR #5536: fix(exec): fail closed when restricted shell lacks a sandbox** (by KDB-Wind)
      - 修复安全漏洞：当受限 Shell 缺乏沙箱保护时，命令执行可能绕过工作区边界。**这是一个关键的安全修复**，需要严格的审查。
      - 链接: [PR #5536](https://github.com/HKUDS/nanobot/pull/5536)
    - **[OPEN] PR #5943: refactor(session): centralize state ownership in SQLite** (by chengyongru)
      - 虽然被标记为重构，但其动机是修复由于共享可变 Session 状态引发的并发和数据一致性问题。
      - 链接: [PR #5943](https://github.com/HKUDS/nanobot/pull/5943)

3.  **P2 中**
    - **[OPEN] PR #5483: fix(session): prevent deleted sessions from being recreated by delayed messages** (by KDB-Wind)
    - **[OPEN] PR #5601: fix(webui): roll back rejected message side effects** (by KDB-Wind)
    - **[OPEN] PR #5678: fix(security): reject empty DNS results and cover SSRF guards** (by KDB-Wind)

### 6. 功能请求与路线图信号

近期没有新的功能请求 Issue，但以下开放 PR 揭露了用户或维护团队对未来路线的设想，很可能被纳入下一版本：

- **远程实例连接** (PR #5941): 允许本地 WebUI 连接远程运行的 NanoBot 实例。这指向了 **分布式部署和远程管理** 的用例，是项目向更企业级应用演进的关键一步。
- **结构化决策客户端** (PR #5825): 引入与 Provider 无关的结构化决策客户端，初始后端为 OpenRouter。这表明 NanoBot 正在构建 **更高级的决策流程** 支持，可能用于复杂的 Agent 路由和任务分配。
- **内存/会话优化** (PR #5885): 通过 Token 阈值控制会话摘要的生成，以保留简短会话的原始记录。这反映了对 **长短期记忆管理** 精细化的持续追求，是提升对话体验的核心。

综合来看，项目的路线图正朝着 **更强的可观测性、更安全的执行环境、更灵活的系统架构和更智能的上下文管理** 方向演进。

### 7. 用户反馈摘要

由于今日无新的 Issue 和活跃的评论互动，我们从现有 PR 的摘要和描述中提炼用户（包括开发者）的痛点：

- **数据安全与一致性**: 用户对文件操作可能导致的“内容撕裂”和系统崩溃后的“窗口期数据丢失”（源自 PR #5953）表现出高度关注，这直接关系到使用 NanoBot 处理敏感或重要文档时的信任度。
- **安全边界**: 开发者对于容器化或受限环境下的安全执行有明确需求（PR #5536），即不希望命令执行沙箱被绕过。这表明用户正在将 NanoBot 用于需要严格隔离的场景。
- **异步与并发问题**: 从多个 PR（如 #5483, #5339, #5257）可以看出，用户或贡献者在处理跨 Session、延迟消息和并发控制时遇到了诸如“会话被意外重建”或“临时聊天被丢弃”等问题，反映了在异步、高并发使用场景下的稳定性挑战。
- **用户体验**: 用户期望 WebUI 能更智能地处理 API 类型切换（PR #5698），并连接远程服务器（PR #5941），这表明他们希望获得更无缝、更强大的使用体验。

### 8. 待处理积压

以下是一些创建时间较早、且重要性较高的未合并 PR，需提醒维护者团队关注：

1.  **[OPEN] PR #5166 (created: 2026-07-29):** fix(agent): expire inherited goal permission outside scope (by syphrpunk)
    - 修复 `asyncio.create_task()` 导致的目标权限意外继承问题。这是一个难以察觉但后果严重的并发 bug，已积压超过两个月。
    - 链接: [PR #5166](https://github.com/HKUDS/nanobot/pull/5166)

2.  **[OPEN] PR #5257 (created: 2026-08-05):** fix(agent): bound sustained-goal continuation when the turn goes idle (by shakewingo)
    - 修复持续目标在空闲时无限重复回复的 bug。该问题直接影响 Agent 的对话效率与资源消耗。
    - 链接: [PR #5257](https://github.com/HKUDS/nanobot/pull/5257)

3.  **[OPEN] PR #5339 (created: 2026-08-11):** fix(webui): reject discarded temporary chat messages (by KDB-Wind)
    - 修复临时聊天在多步处理中被意外丢弃后，消息仍被发布的潜在问题。
    - 链接: [PR #5339](https://github.com/HKUDS/nanobot/pull/5339)

以上 PR 均出自不同贡献者之手，持续积压可能打击社区贡献者的积极性，并增加了后续合并时的冲突风险。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据 Hermes Agent 项目 2026年10月2日的 GitHub 数据生成的日报。

---

### Hermes Agent 项目动态日报 | 2026-10-02

---

#### 1. 今日速览

今日项目活跃度极高，Issues 和 PR 提交数量均达到50条，显示出社区强大的使用和贡献热情。**然而，一个显著的风险信号是，今日所有提交的 50 个 PR 均处于“待合并”状态，没有任何合并或关闭动作。** 这可能表明项目维护者正在进行集中审查，或者合并流程出现了暂时的瓶颈。与此同时，Bug 报告类型占比较高，并出现了一个 P0 级别的性能问题，表明项目在功能迭代的同时，稳定性和性能优化是当前社区关注的重点。

#### 2. 版本发布

**无**

---

#### 3. 项目进展

**今日没有任何 PR 被合并或关闭。**

虽然代码合并停滞，但社区贡献的修复意图非常明确。大量新提交的 PR（如 PR #131071 和 #131067）直接瞄准了当天报告的高优先级 Bug（如 Issue #130987 和 #131055），显示了积极的问题响应和修复动态。**这表明项目虽在合并流程上有延迟，但社区的修复和开发工作仍在高效推进。**

---

#### 4. 社区热点

今日社区讨论的焦点主要集中在几个长期悬而未决的重大功能和棘手的稳定性问题上。

-   **跨网关协作（#97681）**：热度最高的话题（30条评论）。这是一个长期的功能请求，旨在让不同的 Bot 在网关上协作。评论中讨论了该功能依赖于一个尚未完成的核心组件——统一网关运行时（#106742）。开发者文本人（Teknium）曾表示将优先稳定群聊功能，该项目已因此延期一个多月，社区期待其获得进展。
    -   👉 [Issue #97681](https://github.com/NousResearch/hermes-agent/issues/97681)

-   **桌面端性能/资源占用（#127647）**：一个追踪桌面客户端空闲时高资源消耗（CPU/GPU/内存）的综合性 Issue，收获26条评论。社区贡献者在此处进行“分诊”，并关联了多个相关 PR，明确了问题根因和修复路线，显示出用户对桌面端流畅度有较高期待。
    -   👉 [Issue #127647](https://github.com/NousResearch/hermes-agent/issues/127647)

-   **桌面端消息渲染重复显示（#127665）**：讨论人数众多（21条评论），用户描述了一个非常具体的 UI Bug，即同一助手的回复被渲染了两次。该 Bug 通过一条不同于之前已知 Bug 的路径触发，社区成员积极复现并提供帮助，体现了社区的协作精神。
    -   👉 [Issue #127665](https://github.com/NousResearch/hermes-agent/issues/127665)

#### 5. Bug 与稳定性

今日报告的 Bug 较多，严重程度较高。

-   **P0 临界**
    -   **网关提示缓存失效问题（#130895）**：网关在分区合并后的下一次对话会完全错过提示缓存，导致性能急剧下降。这直接影响用户体验和推理成本，是当日最高优先级的 Bug。目前已有相关的 PR（#130909）正在开发中以确保 Windows 兼容性。
        -   👉 [Issue #130895](https://github.com/NousResearch/hermes-agent/issues/130895)

-   **P1 严重**
    -   **Cron 外部 Worker 缺失依赖（#122529）**：Cron 调度器的外部工作进程无法找到正确的 Python 环境（缺少 `ruamel` 库），导致模块崩溃。影响所有升级后使用 Cron 功能的用户。
        -   👉 [Issue #122529](https://github.com/NousResearch/hermes-agent/issues/122529)
    -   **网关重启时等待时间过长（#130987）**：当 Cron 任务还在运行时重启网关，会导致网关进入长达30分钟的无响应状态。这是严重的管理问题，影响了服务的可用性。**已有对应的修复 PR #131071（待合并）**。
        -   👉 [Issue #130987](https://github.com/NousResearch/hermes-agent/issues/130987)

-   **P2 较高**
    -   **桌面端右键菜单劫持（#127313）**：新功能引入的回归 Bug，右键按住对话区域会弹出区域菜单而非上下文菜单，导致无法复制文本。影响桌面版用户的正常使用。
        -   👉 [Issue #127313](https://github.com/NousResearch/hermes-agent/issues/127313)
    -   **Windows 平台多路径问题**：今日集中出现了多个 Windows 原生问题，包括 `gateway migrate --multiplex` 命令失败（#124120）、Git 更新工具 404 错误（#127044）、桌面应用安装恢复权限拒绝（#124679）等。Windows 平台的兼容性需要重点关注。
        - 👉 [#124120](https://github.com/NousResearch/hermes-agent/issues/124120) | [#127044](https://github.com/NousResearch/hermes-agent/issues/127044) | [#124679](https://github.com/NousResearch/hermes-agent/issues/124679)
    -   **Linux 桌面沙箱标记污染（#131055）**：二次启动桌面客户端会错误地设置 `--no-sandbox` 标记，导致渲染器崩溃循环。**已有对应的修复 PR #131067（待合并）**。
        - 👉 [Issue #131055](https://github.com/NousResearch/hermes-agent/issues/131055)

#### 6. 功能请求与路线图信号

-   **跨 Bot/网关协作（#97681）**：如前所述，这是路线图上已规划的重大功能，但受制于核心基础设施的稳定性。一旦 `main` 分支上的群聊功能稳定，该项目将有望重启。
-   **Windows 桌面端系统托盘行为优化（#119120）**：用户期望将“最小化到托盘”和“关闭到托盘”的行为解耦，以更符合 Windows 的习惯。这是一个体验优化，可能在群聊功能稳定后被纳入下一版。
    - 👉 [Issue #119120](https://github.com/NousResearch/hermes-agent/issues/119120)
-   **决策模型扩展（#129686）**：用户希望支持更多的开源/小型决策模型（如 Jev, Tev1）。这是一个明确的信号，表明社区对更灵活、成本更低的私有部署方案有需求。
    - 👉 [Issue #129686](https://github.com/NousResearch/hermes-agent/issues/129686)
-   **桌面端选项卡显示 Agent 名称（#131072）**：有 PR 提交了一个新功能，允许在桌面会话标签中显示 Agent 名称。这是个小而实用的改进，如果被接受，将很快进入主线。
    - 👉 [PR #131072](https://github.com/NousResearch/hermes-agent/pull/131072)
-   **Kanban 审批归属功能（#91984）**：针对企业工作流，用户希望 Kanban 任务的操作能有完整的审计追踪。这是一个长线 PR，持续有讨论，表明社区对此有持续的需求。
    - 👉 [PR #91984](https://github.com/NousResearch/hermes-agent/pull/91984)
-   **自动回滚机制（#13603）**：一个从 4 月份就开始讨论的古老功能，希望升级失败后能自动回滚。虽然长期未解决，但今天仍有更新，表明这个痛点依然存在。
    - 👉 [Issue #13603](https://github.com/NousResearch/hermes-agent/issues/13603)

#### 7. 用户反馈摘要

-   **升级兼容性痛点**：多位用户报告升级后环境出现问题，主要是 `pm` 命令（包管理器）在升级后因 Python 版本不匹配而阻塞（#129751），以及 Cron Worker 环境错误（#122529）。这表明升级流程的测试和兼容性覆盖需要加强。
-   **插件生态体验**：用户报告 `mnemosyne` 插件虽然已安装配置，但相关工具仍报告“未初始化”（#125520）。这反映了插件与核心的交互可能存在隐蔽的错误处理或状态管理问题，影响了第三方生态的可靠性。
    - 👉 [Issue #125520](https://github.com/NousResearch/hermes-agent/issues/125520)
-   **Windows 用户环境痛点**：Windows 用户普遍面临着安装（#124679）、更新（#127044）、多配置（#124120）等基础操作的失败。这是目前平台兼容性上的明显短板。
-   **安全问题关注度提升**：用户持续提交安全相关的 Issue 和 PR，如 `npm audit` 报告（#129426）和备份权限限制（#131074）。这表明社区对安全问题有较高的敏感度，并主动提供修复方案。

#### 8. 待处理积压

-   **跨网关协作（#97681）**：作为社区讨论的焦点，该 Issue 因依赖项 (#106742) 导致的延期已超过一个月，需维护者再次评估优先级和发布计划。
-   **SMS 独立发送功能崩溃（#55377）**：这是一个已修复并关闭的 Bug，但今天被重新打开了，需要确认修复是否有效或出现了回归。
-   **邮件发送截断问题（#61990）**：自 7 月以来，用户对邮件发送截断问题表达了不满，但讨论已趋于停滞。这是一个影响用户体验的功能缺陷，值得重新审视。
-   **WeCom 平台消息截断（#19689）**：与 #61990 类似，同样涉及消息截断。虽然已被标记为 Bug 并有一段时间了，但似乎仍未有修复方案。
-   **多 Profile 环境变量写入问题（#77519）**：这是一个安全相关的 PR，被标记为 **“可替换”**。该 PR 在修复攻击面方面有重要价值，但因被认为是“另一种实现方式”而被阻塞。需要维护者做出最终决策，是接受此 PR 还是开发替代方案。

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，这是为您生成的 PicoClaw 项目动态日报。

---

# PicoClaw 项目动态日报 | 2026-10-02

## 今日速览

项目今日活跃度较高，共处理 14 条 PR，但与 Issues 更新的 2 条相比，变动较少。最关键的风险点在于 **官网（picoclaw.io）TLS 证书过期**（Issues #3377）问题仍未解决，且已持续超过三周，对项目品牌和用户信任度构成严重威胁。尽管修复类 PR 持续提交，但项目整体推进速度受限于大量待合并的 PR（12 条）和未处理的积压问题，健康度评定为 **中等偏风险**。

## 项目进展

今日共有 2 条 PR 被合并/关闭，标志着项目在特定功能修复和长期框架搭建上取得进展。

- **[#3376] [CLOSED] fix(deltachat): 初始化自定义渠道以解决配置验证错误**：该 PR 成功修复了启用 DeltaChat 渠道时，由于注册类型未知（`"deltachat"`）而导致的配置验证错误，解决了 Gateway 启动失败的关键问题。
  [查看合并 PR #3376](sipeed/picoclaw PR #3376)

- **[#423] [CLOSED] WIP: 多智能体协作框架与共享上下文**：虽然标注为“WIP”，但该 PR 的合并标志着项目在多智能体协作方面的基础框架已就位，包括共享上下文池（Blackboard）和智能体交接工具。这是从单一智能体向复杂多智能体交互迈出的重要一步。
  [查看合并 PR #423](sipeed/picoclaw PR #423)

## 社区热点

今日社区讨论最活跃、关注度最高的是官网宕机问题。

- **[#3377] [CRITICAL] TLS证书过期，网站无法访问**：该 Issue 获得 2 个 👍 和 3 条评论，评论量和关注度高。用户对于项目官方主页长期不可用表达了强烈不满，希望能尽快恢复访问。这暴露出项目在基础设施维护上的潜在漏洞。
  [查看 Issue #3377](sipeed/picoclaw Issue #3377)

## Bug 与稳定性

今日报告的 Bug 较少，共 2 条新 Issue，但风险等级差异巨大，且暂无直接修复 PR。

**Critical**:
- **网站 TLS 证书过期** (`[CRITICAL] [stale] #3377`)：picoclaw.io 全站瘫痪，所有浏览器拒绝连接。此问题已存在近一个月，直接影响新用户获取信息和项目形象。**暂无对应修复 PR**。
  [查看 Issue #3377](sipeed/picoclaw Issue #3377)

**Low**:
- **多行输入消息分割** (`[BUG] [stale] #3391`)：在 Pico 客户端中，粘贴多行文本会被自动分割成多条消息发送，破坏了消息的完整性。**暂无对应修复 PR**。
  [查看 Issue #3391](sipeed/picoclaw Issue #3391)

## 功能请求与路线图信号

今日提交的 PR 中包含一些新的功能特性，可能指向下一版本的方向。

- **按需切换消息发送模式**：虽无直接 Issue，但 PR #3414 与 Bug #3391 存在紧密关联。PR #3414 提出的“每次调用限制”功能，可用于约束智能体工具使用，而 Issue #3391 中的“消息分割”问题则提出了配置化消息处理的需求。结合两者，未来可能支持用户自定义消息分割/合并的配置，以适配不同场景。
- **新增 turn_time_budget 功能**：PR [#3414] 新增了智能体单轮对话的“挂钟时间预算”，让用户可配置智能体在单个回合内的最长处理时间。超时后，智能体会停止调用新工具并总结已完成工作，防止其无限循环。这体现了对用户体验和资源控制的优化。
  [查看 PR #3414](sipeed/picoclaw PR #3414)
- **新增 `opencode-go` Provider**：PR [#3371] 请求新增一个独立的 `opencode-go` 提供商，以保持 PicoClaw 对 OpenCode Go API 的兼容性。这表明社区对 API 兼容性和多提供商支持的需求持续存在。
  [查看 PR #3371](sipeed/picoclaw PR #3371)

## 用户反馈摘要

核心痛点集中在 **体验完整性** 和 **项目可用性** 上：

- **痛点：无法访问项目官网**：用户在 Issue #3377 中反馈，官方主页 picoclaw.io 因 TLS 证书过期而不能访问，对新用户和想要了解项目的人来说是致命的体验障碍。
- **不满意：消息结构被破坏**：用户反映，粘贴代码、诗歌等多行文本时，内容会被自动分割，破坏了原文结构，这在需要发送格式化信息（如代码块）的场景下不可用。

## 待处理积压

以下为长期未响应的重要 Issue 或 PR，需维护者重点关注：

1. **[#3377] [CRITICAL] 官网 TLS 证书过期**：该问题已停滞超过三周（创建于 2026-09-12），但严重程度最高。建议优先处理，可联系域名或证书托管方，或发布临时备用页面的公告。
   [查看 Issue #3377](sipeed/picoclaw Issue #3377)

2. **[#3399] [OPEN] 修复 32 位 ARM 架构更新问题**：该 PR 修复了 `picoclaw update` 命令在 32 位 ARM 设备上错误安装 arm64 二进制文件的严重 Bug。该问题已存在一周，可能导致用户设备更新后无法运行。
   [查看 PR #3399](sipeed/picoclaw PR #3399)

3. **[Driven by Dependabot] 依赖包更新 PRs**：`#3385`、`#3386`、`#3387`、`#3388`、`#3389` 等一批由 Dependabot 提交的依赖更新 PR 已开放一周，部分涉及安全或关键库（如 golang.org/x/crypto），长期不合并可能使项目暴露于已知漏洞风险中。
   [查看 PR #3385](sipeed/picoclaw PR #3385) | [#3386](sipeed/picoclaw PR #3386) | [#3387](sipeed/picoclaw PR #3387) | [#3388](sipeed/picoclaw PR #3388) | [#3389](sipeed/picoclaw PR #3389)

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，这是为您生成的 NanoClaw 项目动态日报。

---

## NanoClaw 项目动态日报 | 2026-10-02

### 今日速览

今日项目活跃度极高，尤其在代码提交和合并方面。过去24小时内共有26个PR更新，其中15个已合并或关闭，显示出维护团队在快速推进功能开发与修复。同时，有4个新的Issue被报告，涵盖了一个严重的高优先级Bug。社区热点集中在一个影响Discord集成的按钮参数冲突问题，以及对于工具链稳定性（如CLI分页、代理凭证安全）的讨论。总体来看，项目维护节奏紧凑，社区反馈积极。

### 版本发布

**无**

---

### 项目进展

今日共有15个PR被合并或关闭，不仅修复了多个关键Bug，还在安全性、依赖管理和CI/CD建设上取得了显著进展。

1.  **安全与依赖加固**
    - **[修复] 代理凭证安全** ([PR #3985](https://github.com/qwibitai/nanoclaw/pull/3985)): 修正了设置脚本将代理凭证（包含用户名密码）直接写入可被其他本地用户读取的systemd服务文件的漏洞，提升了本地安装的安全性。
    - **[依赖] 升级Iron Proxy** ([PR #3982](https://github.com/qwibitai/nanoclaw/pull/3982)): 将Iron Proxy版本从旧提交固定在v0.52.0标签，解决了30个已知的依赖项安全建议。
    - **[依赖] 升级gRPC** ([PR #3981](https://github.com/qwibitai/nanoclaw/pull/3981)): 将Iron前端代理中的gRPC版本升级，修复了6个安全漏洞。
    - **[依赖] 升级tsx运行器** ([PR #3977](https://github.com/qwibitai/nanoclaw/pull/3977)): 升级了tsx运行器，消除了在Node 26上运行时的 `module.register()` 弃用警告。
    - **[CI] 启用Dependabot** ([PR #3978](https://github.com/qwibitai/nanoclaw/pull/3978)): 为GitHub Actions工作流启用了Dependabot自动依赖更新，并移除了未启动的Renovate配置，增强了CI的自动化与安全性。

2.  **核心功能与稳定性修复**
    - **[修复] 审批卡超时与驳回** ([PR #3833](https://github.com/qwibitai/nanoclaw/pull/3833)): 为用户发起的审批卡片增加了过期（TTL）机制，并支持通过ID拒绝，解决了长期未处理的审批卡导致代理“卡住”的问题。
    - **[修复] HTTPS代理支持** ([PR #3901](https://github.com/qwibitai/nanoclaw/pull/3901)): 修复了在设置过程中，主机服务无法通过HTTPS代理访问互联网的问题。
    - **[修复] 更新脚本优化** ([PR #3963](https://github.com/qwibitai/nanoclaw/pull/3963)): 修正了更新脚本中的一个数据符号链接操作，使其在Node 24的特定版本下也能通过测试。
    - **[CI/CD] 发布Docker镜像** ([PR #3208](https://github.com/qwibitai/nanoclaw/pull/3208)): 新增了手动触发的CI工作流，用于构建并发布Agent镜像到Docker Hub，并加入了CVE门槛检查，为稳定发布做准备。
    - **[CI] 锁定Action版本** ([PR #3968](https://github.com/qwibitai/nanoclaw/pull/3968)): 将所有GitHub Actions和cosign工具锁定到精确版本，防止因上游标签移动导致的CI行为不可控风险。

这些合并操作显著增强了项目的安全性、稳定性，并优化了开发与发布流程。

---

### 社区热点

今日最受关注的讨论集中在 **`#3456`** Issue，它是一个关于Discord集成的高严重性Bug，获得了社区成员 `DawoudIO` 的详细报告和6条评论。

- **热点 Issue: [BUG] chat-sdk-bridge: Discord按钮参数冲突导致静默拒绝** ([Issue #3456](https://github.com/qwibitai/nanoclaw/issues/3456))
    - **严重性**: 高
    - **核心诉求**: 用户报告在Discord上使用 `ask_question` 功能时，所有选项按钮都无法正常工作，任何点击都会解析到错误选项。原因是 `createChatSdkBridge` 在构造按钮时，错误地同时设置了 `id` 和 `value` 参数，这违反了Discord的API规范，导致交互被静默拒绝。该Bug直接破坏了所有依赖此功能的审批流，社区急需修复。

- **热点 PR: [Feature] 引入更新频道机制** ([PR #3986](https://github.com/qwibitai/nanoclaw/pull/3986))
    - **核心诉求**: 社区成员 `glifocat` 提出了一项重要功能，允许用户通过 `NANOCLAW_UPDATE_CHANNEL` 环境变量选择更新频道（`stable` 稳定版或 `beta` 测试版）。这解决了 `/update-nanoclaw` 默认更新到 `main` 分支最新代码可能引入不稳定性的问题，满足了不同场景（生产与测试）的更新需求，讨论热度高。

---

### Bug 与稳定性

今日报告了4个新Issue，其中包含一个高严重性Bug和一个影响测试稳定性的Bug。

- **高严重性**
    - [**[BUG] Discord审批按钮参数冲突**](https://github.com/qwibitai/nanoclaw/issues/3456)（Issue #3456）：如前所述，该Bug导致Discord上的审批、提问卡片完全不可用。**已有修复PR #3833 在审查中**，但Issu#3456本身报告了另一个侧面问题，可能需要独立或额外修复。
- **中等严重性**
    - [**[BUG] OneCLI列表漏显**](https://github.com/qwibitai/nanoclaw/issues/3991)（Issue #3991）：用户报告 `onecli agents list` 等命令如果不指定 `--max` 参数，默认只显示前20个结果，且未给出任何提示，可能导致用户遗漏信息。
    - [**[BUG] PreCompact钩子因未注册邮箱失败**](https://github.com/qwibitai/nanoclaw/issues/3984)（Issue #3984）：在每次压缩（compaction）时，`PreCompact` 钩子因未检测到注册的邮箱而报错退出。这是一个影响自动维护流程的回归问题。
- **低严重性**
    - [**[CI] 权限测试受umask影响**](https://github.com/qwibitai/nanoclaw/pull/3979)（已合并/关闭 PR #3979）：修复了一个测试问题，该测试在自定义的 `umask` 环境下会失败，保证了测试环境的独立性。

---

### 功能请求与路线图信号

今日有2个新功能请求被提出，结合已有的PR，可以看出项目正在向更好的用户体验和更完善的安全运维方向发展。

- **[功能请求] 只读安全审计工具** ([Issue #3990](https://github.com/qwibitai/nanoclaw/issues/3990))：用户 `drsmk238` 提议增加一个 `security-audit` 能力，用于对运行中的NanoClaw实例进行只读检查，审计其配置的隔离性和补丁状态。这反映了社区对生产环境安全合规性的需求。
- **[功能请求与实现] 更新频道机制**：Issue #3986 提出的更新频道功能是社区讨论热点。这表明用户希望在生产与测试环境之间拥有更灵活的版本控制。
- **[功能请求与实现] 改进发布流程** ([PR #3987](https://github.com/qwibitai/nanoclaw/pull/3987))：提出允许维护者无需第二批准者即可发布 `-rc.N` 预发布版本，但对稳定版发布保留更严格的审批流程。这显示出项目在完善其发布策略。

这些信号表明，`下一版本` 可能聚焦于：
- 更安全的更新机制（更新频道）。
- 对运维友好的内置审计能力。
- 更灵活和严格的发布流程。

---

### 用户反馈摘要

从今日的讨论中，可以提炼出用户的一些核心声音：

- **痛点与不满**：
    - **Discord集成严重受损**：用户 `DawoudIO` 在 [#3456](https://github.com/qwibitai/nanoclaw/issues/3456) 中详细描述了Discord交互的“静默失败”问题，这是一种非常糟糕的用户体验，因为用户以为操作成功了，但实际被拒绝。
    - **CLI行为令人困惑**：用户 `drsmk238` 在 [#3991](https://github.com/qwibitai/nanoclaw/issues/3991) 中表达了 `onecli list` 默认分页行为的不理解，因为没有提示信息，容易造成数据未导全的错觉。
- **使用场景与期望**：
    - **寻求自动化安全审计**：用户 `drsmk238` 在 [#3990](https://github.com/qwibitai/nanoclaw/issues/3990) 中的请求反映了高级用户希望有一个便捷、安全的工具来巡检生产的配置合规性，减少手动排查的复杂度。

---

### 待处理积压

尽管今日项目活跃，仍有一些较老的Issue和PR待处理，需提醒维护团队关注。

- **待处理的长期PR**:
    - [**[PR #3570] 修复Telegram Markdown格式问题**](https://github.com/qwibitai/nanoclaw/pull/3570)（创建于2026-08-27）：此PR旨在修复Telegram消息因下划线数量为奇数而无法送达的问题（影响 `onecli connect` 链接的发送）。该PR已有一个多月未更新，可能维护团队在等待反馈或内部讨论。鉴于其影响广泛（所有Telegram用户），建议优先推进。
    - [**[PR #1343] 社区技能：/add-cli-backend**](https://github.com/qwibitai/nanoclaw/pull/1343)（创建于2026-03-22）：这是一个很早就提交的功能技能，旨在解决使用OAuth令牌违反Anthropic TOS的问题。该PR似乎已被长期搁置，建议维护团队明确其未来方向（合并、关闭或需要更新），以避免社区贡献者的积极性受损。

- **待处理的重要Issue**:
    - 无昨日新开但未被响应的严重Issue。

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是为您生成的 IronClaw 项目动态日报。

---

## IronClaw 项目动态日报
**日期**: 2026-10-02

### 1. 今日速览

过去24小时内，项目活跃度保持中等水平，社区贡献与内部维护并行推进。**主要动作为2个新Issue的提出和2个待合并PR的持续更新**，暂无新版本发布。一个重要的功能特性（#2358，加密浏览器持久化）在经历近6个月后获得更新，表明核心团队仍在稳步推进设计讨论。同时，自动化基准测试工具持续运行并报告了昨夜（10月1日）的失败分类（#8121），其中包含一个重复出现的 workspace 种子问题，需要关注其稳定性影响。

### 2. 版本发布

无。

### 3. 项目进展

过去24小时内**无PR被合并或关闭**。目前活跃的待合并PR反映了项目在以下两个方向上的进展：

- **外部身份与权限集成 (PR #7499)**：该PR由新贡献者提交，目标是通过`IdentyClaw` Passport为IronClaw代理提供宿主中介的身份验证能力。尽管未被合并，但该PR的持续更新（上次更新日期为昨天）表明其正在接受Code Review或修改，是项目向去中心化身份管理迈出的重要一步。
    - **链接**: [PR #7499](https://github.com/nearai/ironclaw/pull/7499)

- **基础设施与知识管理自动化 (PR #7988)**：这是一个由CI机器人自动提交的例行更新，用于刷新项目内嵌的知识图谱。此类PR的持续存在表明项目内部文档库正在持续演进，并为代理的代码理解提供了支持。
    - **链接**: [PR #7988](https://github.com/nearai/ironclaw/pull/7988)

### 4. 社区热点

今日讨论的焦点集中在**#2358** 这个关于浏览器持久化功能的老Issue上。

- **Issue #2358**: [feat(browser): add BrowserProfileStore trait with encrypted tarball persistence](https://github.com/nearai/ironclaw/issues/2358)
    - **状态**: 该项目创建于4月，昨日获得更新，包含1条评论。其核心诉求是希望在代理运行间保存浏览器会话状态（cookies、localStorage等），以避免用户反复认证。评论中提出的`encrypted tarball persistence`方案显示了社区对**安全存储敏感数据**的强烈需求。这个话题的活跃度表明，**高质量的会话持久性是提升代理自主性和用户体验的关键障碍**。
    - **潜在诉求**: 用户期望获得类似“无头浏览器持久化”的能力，以支持更复杂的、需要维护登录态的自动化任务。

### 5. Bug 与稳定性

本次统计周期内未发现新的严重Bug。关于稳定性，有一个自动化的监控报告需要关注：

- **Issue #8121**: [Daily ironclaw failure taxonomy — 2026-10-01](https://github.com/nearai/ironclaw/issues/8121)
    - **严重程度**: 中（关注）。这是一个由机器人自动生成的每日失败分类报告。它指出昨夜运行的`clawbench`测试中有128个非通过用例，且问题主要源于一个重复出现的**benchmark侧workspace-seeding缺陷**。虽然这并非代码库本身的bug，但它直接影响了项目核心基准测试的可靠性，增加了评估真实性能改进的难度。
    - **修复PR**: 无。该Issue仅“记录”而非“解决”问题。维护者需关注其是否为自动化测试基础设施的持续性问题。

### 6. 功能请求与路线图信号

今日的功能请求信号主要来自活跃的Issue和PR：

- **高优先级功能 – 加密的浏览器会话持久性**：`#2358` 的提案已被明确标记为 `[enhancement, scope: workspace, scope: secrets]`。这种对工作空间和机密管理的双重关注，强烈暗示这将是**下一阶段的核心特性之一**。其实现将解锁更高级的、需要长期运行和登录态的AI代理应用场景。

- **去中心化身份集成探索**：`PR #7499` 引入的`IdentyClaw Passport`概念是社区对身份层集成的一次具体尝试。虽然尚未被采纳，但来自外部贡献者的这种“host-mediated”方案为项目提供了新的思路，可能影响未来关于代理身份和权限模型的路线图决策。

### 7. 用户反馈摘要

基于有限的Issue评论，可以提炼出以下用户声音：

- **核心痛点：浏览器状态丢失**。在`#2358`的讨论中，用户明确指出了“每次重新认证”是操作高可用性代理的主要障碍。这表明当前代理在需要处理Web页面时，其状态管理能力是用户体验的一个主要瓶颈。
- **对安全性的关切**：`#2358`提案强调“加密tarball”来解决存储cookies（持有者令牌）的问题，反映了社区不仅关心“能不能存”，更关心“安不安全存”。这是一个积极的信号，表明用户对代理的安全基线有较高期望。

### 8. 待处理积压

- **核心功能PR长期未合并**：**PR #7499** (IdentyClaw Passport) 尽管由新贡献者提交且进行了更新，但创建已近2个月（自8月11日）仍未合并。这可能需要维护者给出更明确的反馈或决策，以避免挫伤外部贡献者的积极性。
    - **链接**: [PR #7499](https://github.com/nearai/ironclaw/pull/7499)

- **遗留功能提案等待明确反馈**：**Issue #2358** 的创建时间是4月12日，虽然最近有更新，但作为一项影响深远的特性，其设计讨论周期已经很长。社区希望看到更明确的时间线或阶段性进展计划。
    - **链接**: [Issue #2358](https://github.com/nearai/ironclaw/issues/2358)

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

# LobsterAI 项目日报 2026-10-02

## 1. 今日速览

项目昨日保持中等活跃度，共处理 **7 个 Pull Request**（全部合并/关闭），**0 个新版本发布**。Issues 侧无新开问题，7 个历史 Issue 获得更新（均仍为开放状态），未见新活跃讨论。合并的 PR 覆盖 OpenClaw 在 Windows 下的稳定回退、认证模型目录恢复、侧边栏动画优化、沙箱模式修复、生产构建压缩、本地插件安装支持以及老旧引擎代码清理。整体看项目在修复兼容性和技术债务清除上有稳步推进，但社区反馈的多个 Bug 和功能建议仍处于积压状态（stale 标记已超半年），建议维护者尽快规划优先级。

---

## 2. 版本发布

✅ 过去24小时无新版本发布。

---

## 3. 项目进展

昨日共合并/关闭 7 个 PR，主要进展如下：

| PR 编号 | 标题 | 影响域 | 内容摘要 |
|---------|------|--------|----------|
| [#2709](https://github.com/netease-youdao/LobsterAI/pull/2709) | fix(openclaw): fall back when Windows private SQLite staging dirs fail | OpenClaw / Windows | 修复 Windows 下安全软件/约束语言模式导致 PowerShell 创建私密 SQLite 目录失败的场景，提供回退机制，提升 OpenClaw 在受限环境下的兼容性。 |
| [#2788](https://github.com/netease-youdao/LobsterAI/pull/2788) | fix(auth): recover plan model catalog when logged out and prompt login in selector | 认证 / 模型选择器 | 修复登出后模型选择器为空的问题：在登出路径、刷新、窗口聚焦时重新加载公开定价目录；未登录时在模型选择器中显示登录提示。 |
| [#915](https://github.com/netease-youdao/LobsterAI/pull/915) | fix(sidebar): 侧边栏折叠过渡动画 + macOS 告警横幅文字遮挡修复 | 渲染层 | 移除 `.sidebar-transition { transition: none }` 规则，恢复折叠动画；修复 macOS 下告警横幅文字被侧边栏遮挡的问题。 |
| [#917](https://github.com/netease-youdao/LobsterAI/pull/917) | fix(cowork): restore sandbox execution mode from UI to OpenClaw config | Cowork | 修复 `coworkStore.ts` 中硬编码 `executionMode: 'local'`，现读取数据库配置并验证；同时修正沙箱模式映射。 |
| [#920](https://github.com/netease-youdao/LobsterAI/pull/920) | perf(build): enable esbuild minification for production builds | 构建 | 生产构建开启 esbuild 压缩（Renderer 使用 Vite 默认；Main/Preload 条件启用），减小产物体积。 |
| [#921](https://github.com/netease-youdao/LobsterAI/pull/921) | feat: add openclaw install local plugin | OpenClaw | 新增本地插件安装形式，允许从独立仓库安装插件（而非仅支持公共仓库或源码目录），附带使用文档。 |
| [#941](https://github.com/netease-youdao/LobsterAI/pull/941) | refactor(cowork): 删除 yd_cowork 引擎及 Claude Agent SDK 相关代码 | Cowork | 清理长期死代码（`coworkRunner.ts`、`claudeSdk.ts`、`claudeRuntimeAdapter.ts` 约 3100+ 行），收窄引擎类型为 `'openclaw'`。 |

**总结**：项目在 **OpenClaw 兼容性/沙箱/插件管理**、**认证与UI细节**、**构建性能** 以及 **代码清理** 四个方向均有实际推进，预计下一版本将包含这些改动。

---

## 4. 社区热点

昨日 **无新 Issue/PR** 引发高活跃讨论（所有 Issue 评论数均为 1）。以下历史 Issue 在技术上值得关注，但长时间未得到维护者回应：

- **[#922 – Anthropic SSE 流式解析未做行缓冲，丢失数据](https://github.com/netease-youdao/LobsterAI/issues/922)**  
  报告了关键的数据丢失 Bug：高吞吐时 SSE 数据行跨 chunk 导致 JSON.parse 失败并被 catch 吞掉。该问题直接影响流式文本完整性，但自 2026-03-26 以来未获回复。
- **[#926 – destroy() 调用不存在的 reject 导致崩溃](https://github.com/netease-youdao/LobsterAI/issues/926)**  
  明确指出了 `accumulator.reject` 缺少可选链，应用退出/重建时必现崩溃。同文件其他位置已正确使用可选链，修复简单但至今未合并。
- **[#943 – 增加模型调用的优先级 / 自适应切换](https://github.com/netease-youdao/LobsterAI/issues/943)**  
  用户提出了提升可用性的功能请求，并附上了模型配置错误时的截图和 IM 交互反馈。该建议涉及模型配置和故障转移逻辑，可能对后续版本有较大影响。

社区诉求集中在 **流式传输稳定性**、**崩溃修复** 和 **模型可用性保障**，建议维护者优先回应上述问题。

---

## 5. Bug 与稳定性

昨日未报告新 Bug，但以下 7 个历史 Bug 仍处于开放状态（均已 stale 超 6 个月），按严重程度排列：

| 严重度 | 编号 | 简述 | 是否有 Fix PR | 安全/影响 |
|--------|------|------|---------------|-----------|
| 🔴 崩溃 | [#926](https://github.com/netease-youdao/LobsterAI/issues/926) | `destroy()` 中 `accumulator.reject` 缺失可选链，应用退出时 TypeErro | 无 | 应用退出/IM handler 重建时必现崩溃 |
| 🟠 数据丢失 | [#922](https://github.com/netease-youdao/LobsterAI/issues/922) | Anthropic SSE 流式解析未做行缓冲，跨 chunk 数据被吞 | 无 | 高吞吐或网络拥堵时丢失流式文本 |
| 🟠 功能异常 | [#918](https://github.com/netease-youdao/LobsterAI/issues/918) | OpenClaw doctor 自动添加 weixin channel ID，但用户从未配置过微信 | 无 | 升级 3.25 后出现，影响 IM 配置 |
| 🟠 安全 | [#925](https://github.com/netease-youdao/LobsterAI/issues/925) | 询问安全漏洞报告渠道 | 无 | 需提供安全响应机制 |
| 🟢 体验 | [#927](https://github.com/netease-youdao/LobsterAI/issues/927) | 模型/供应商选择不支持键盘上下键切换 | 无 | 体验优化 |
| 🟢 视觉/功能 | [#928](https://github.com/netease-youdao/LobsterAI/issues/928) | 龙虾配套登录页面组件加载失败（网易员工按钮 – 返回 – 登录组件空） | 无 | 登录流程连续性中断 |
| 🟡 可用性 | [#943](https://github.com/netease-youdao/LobsterAI/issues/943) | 模型不可用时无法自适应切换其他模型 | 无 | 提升可用性 |

**注意**：虽然 PR [#941](https://github.com/netease-youdao/LobsterAI/pull/941) 删除了 `yd_cowork` 引擎死代码，但尚未与上述 Bug 直接关联。建议维护者对 #926、#922 提供快速修复。

---

## 6. 功能请求与路线图信号

昨日无新功能请求。以下历史功能请求可作为路线图参考：

- **[#921 – 本地插件安装](https://github.com/netease-youdao/LobsterAI/pull/921)** 已合并，预计下一版本将支持 `openclaw install local plugin` 命令，提升第三方开发便利性。
- **[#943 – 模型优先级与自适应切换](https://github.com/netease-youdao/LobsterAI/issues/943)** 尚未有配套 PR，但该功能需求明确（用户附有使用场景截图），可能成为下一个中期功能。建议将其纳入 `v3.26` 或 `v4.0` 计划。
- **[#927 – 键盘上下切换选择](https://github.com/netease-youdao/LobsterAI/issues/927)** 实现成本低且能提升熟练用户效率，可作为快速迭代的候选。

---

## 7. 用户反馈摘要

从近期 Issue 评论中可提炼以下真实用户反馈：

- **配置兼容性痛点**（来自 #918 作者 catubibu）：  
  “升级到 3.25 后，OpenClaw doctor 自动添加了微信 channel，但我从未配置过微信，只有飞书。心流修复不成功。” 表明升级后遗留了不必要的配置变更，用户预期为平滑升级。
- **崩溃影响体验**（来自 #926 作者 xiangliqu）：  
  “应用退出、IM handler 重建、gateway 重连时必现崩溃，中断资源清理流程。” 明确描述了崩溃触发路径及影响，用户希望尽快修复。
- **流式丢失**（来自 #922 作者 xiangliqu）：  
  “高吞吐或网络拥堵时更易触发 JSON.parse 失败并被 catch 吞掉，导致文本片段丢失。” 用户对数据完整性敏感，尤其语音转文字或长文本生成场景。
- **可用性诉求**（来自 #943 作者 chinazhoumin）：  
  “使用错误的模型，IM 沟通并不能获得很好动反馈。” 用户期望模型自动降级或切换，避免因单一模型不可用导致服务中断。

整体用户反馈显示 **稳定性** 和 **配置直观性** 是当前社区主要关切点，尤其是升级后引入的异常行为。

---

## 8. 待处理积压

以下 Issue/PR 已超过 6 个月未获实质性回复或修复，建议维护者逐一评估：

| 类型 | 编号 | 标题 | 最后更新 | 建议行动 |
|------|------|------|----------|----------|
| 🐛 Bug | [#918](https://github.com/netease-youdao/LobsterAI/issues/918) | openclaw doctor自动添加weixin | 2026-10-01 | 验证是否为配置迁移问题，考虑在 3.26 修复 |
| 🐛 Bug | [#922](https://github.com/netease-youdao/LobsterAI/issues/922) | Anthropic SSE 流式解析未做行缓冲 | 2026-10-01 | 参考 OpenAI 路由的 `sseBuffer` 实现修复 |
| 🐛 Bug | [#926](https://github.com/netease-youdao/LobsterAI/issues/926) | destroy() 调用不存在的 reject 导致崩溃 | 2026-10-01 | 简单一行 `?.` 修复，可快速合并 |
| 🛡️ 安全 | [#925](https://github.com/netease-youdao/LobsterAI/issues/925) | 是否有安全漏洞报告渠道 | 2026-10-01 | 建议创建 SECURITY.md 并回复用户 |
| ✨ 功能 | [#927](https://github.com/netease-youdao/LobsterAI/issues/927) | 模型/供应商选择支持键盘上下切换 | 2026-10-01 | 低风险优化，可纳入下次 Sprint |
| 🐛 Bug | [#928](https://github.com/netease-youdao/LobsterAI/issues/928) | 登录页面组件加载失败 | 2026-10-01 | 需排查前端路由状态 |
| ✨ 功能 | [#943](https://github.com/netease-youdao/LobsterAI/issues/943) | 增加模型调用优先级/自适应切换 | 2026-10-01 | 规划为中期功能，收集更多场景 |

**备注**：以上 Issue 均带有 `[stale]` 标签，表明机器人已自动标记为不活跃。建议维护者关闭已无效的反馈，或将有价值的议题重新指派责任人并设定里程碑。

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，根据您提供的 TinyClaw 项目数据，现呈上 2026-10-02 的项目动态日报。

---

### TinyClaw 项目日报 - 2026-10-02

#### 1. 今日速览

今日项目进入“黎明前的沉寂期”：过去24小时内无任何新 Issue 开启或新代码提交，社区讨论处于冻结状态。然而，一个关键动作是**维护者集中清理了3个来自今年2月的历史 PR**，它们均在昨日（10月1日）被合并或关闭。此举虽未带来今日的代码更新，但显著减少了项目积压，释放了“技术债务清理”的积极信号。当前项目活跃度较低，但历史遗留问题的解决表明底层开发工作仍在有序推进。

#### 2. 版本发布

今日无新版本发布。

#### 3. 项目进展

今日虽无新提交，但历史 PR 的关闭为项目带来了三项重要改进，标志着 Telegram 集成功能已从“基础可用”迈入“稳定与体验优化”阶段：

- **#48 [稳定性增强] 修复 Telegram 待发送消息持久化问题**
  - **状态**：已关闭 / 已合并
  - **内容**：修复了 `telegram-client.ts` 中 `pendingMessages` 映射（待发送消息队列）仅存于内存中的问题。此前，任何服务重启（包括 409 轮询冲突、`tinyclaw restart` 命令或崩溃）都会导致该队列清空，造成消息发送失败且无响应。
  - **影响**：这是对核心消息投递可靠性的关键修复。避免了在高频率或高负载场景下因重启导致的**消息静默丢失**问题，确保 Telegram Bot 能在故障恢复后继续正常工作。
  - **链接**: [TinyAGI/tinyagi PR #48](https://github.com/TinyAGI/tinyagi/pull/48)

- **#67 [功能增强] 在 Telegram 中实现交互式内联键盘问答**
  - **状态**：已关闭 / 已合并
  - **内容**：引入“问题桥接（question bridge）”机制。当 Claude 在非交互模式下（`-p` 参数）需要用户澄清时，能将问题以结构化的 `[QUESTION]` 标签输出，并通过 Telegram 内联键盘按钮展示给用户，实现了双向交互。
  - **影响**：彻底解决了 Claude 在静默模式下无法获取用户输入的痛点。现在用户可以在 Telegram 中通过点击按钮来回答 Claude 的疑问，从而解锁了更复杂、需要多轮确认的 AI 任务场景，显著提升了 `-p` 模式的实用性和用户体验。
  - **链接**: [TinyAGI/tinyagi PR #67](https://github.com/TinyAGI/tinyagi/pull/67)

- **#106 [体验优化] 为 Claude 响应添加 Telegram 流式直播预览**
  - **状态**：已关闭 / 已合并
  - **内容**：利用 Claude 的 `stream-json` 输出格式，将生成结果按片段（deltas）实时推送到 Telegram。Telegram 端编辑同一条消息，实现类似“打字机”效果的实时预览，并在完成后给出最终结果。
  - **影响**：大幅缩短了用户在 Telegram 上等待 Claude 生成内容的感知时间。从“等待-完整输出”转变为“实时观看生成过程”，降低了长时间等待带来的焦虑感，是响应式用户体验的重大升级。
  - **链接**: [TinyAGI/tinyagi PR #106](https://github.com/TinyAGI/tinyagi/pull/106)

#### 4. 社区热点

今日无社区讨论。昨日关闭的3个 PR 是近期关注焦点。它们的关闭预示了社区的潜在诉求：
- **对数据可靠性的担忧**：PR #48 的修复暗示部分用户可能因服务重启遭遇过消息丢失，这是对“可靠性”的无声诉求。
- **对交互深度的渴望**：PR #67 的引入表明社区不满足于简单的“问答”，希望 Claude 能在复杂任务中主动、互动地完成信息收集，推动AI更智能。
- **对实时性的期待**：PR #106 响应了用户对长时间等待 AI 输出的不耐烦，期望获得更即时的反馈。

#### 5. Bug 与稳定性

今日无新 Bug 报告。但昨日关闭的 PR #48 明确指出并修复了一个**关键级别**的稳定性 Bug：

- **严重程度**: 高
- **Bug 描述**: `telegram-client.ts` 中 `pendingMessages` 状态仅存于内存。服务重启后，所有待发送的 Telegram 消息（如 AI 问询结果）会丢失。用户将看到消息被静默删除，无法获知 AI 已完成的任何工作。
- **修复状态**: 已合并（通过 PR #48）。
- **潜在影响**: 此 Bug 是影响生产环境稳定性的重要威胁。PR #48 的合解除去了一个重大隐患。

#### 6. 功能请求与路线图信号

今日无新功能请求。从已合并的 PR 可以清晰判断项目当前阶段的路线图信号：

- **路线图信号：Telegram 集成的体验完善**。`#48`、`#67`、`#106` 这三个 PR 分别解决了 `可靠性`、`交互性` 和 `实时性` 三个核心体验维度。这表明维护者正专注于打磨 **Telegram 作为主要前端的能力**，以满足日常、高可靠性的使用场景。下一版本很可能会围绕 Telegram 功能的稳定性、交互流畅度和实时反馈进行整合。

#### 7. 用户反馈摘要

今日无直接用户评论。但合并的 PR 本身即是对早期反馈的响应：
- **反馈痛点（已解决）**: “每次重启后，我发给 Telegram 的消息就没了”——围绕 PR #48。
- **用户场景（已支持）**: “我需要 Claude 在我输入更多信息之前先问我现在需要什么。”——围绕 PR #67。
- **不满意点（已改善）**: “等几秒钟才看到完整回复太久了，我希望能先看到一点内容。”——围绕 PR #106。

#### 8. 待处理积压

得益于今日对3个历史 PR 的清理，项目积压状态显著改善。当前 GitHub 数据中无待合并的 PR，且上一次 Issue 更新完全静止。**目前无明显积压**，这为下一个开发周期提供了一个非常健康的起点。维护者应继续保持这种对历史遗留问题的清理节奏，以避免技术债务的快速积累。

**总结**：今日 TinyClaw 项目处于“静默清债”状态，虽然表面无新活动，但通过集中处理历史遗留问题，提升了项目的核心稳定性和 Telegram 用户体验，为后续开发奠定了良好基础。项目健康度信号积极。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

**Moltis 项目日报 | 2026-10-02**  
**数据区间：2026-10-01 00:00 UTC – 2026-10-01 23:59 UTC**

---

### 1. 今日速览

过去 24 小时项目无新 Issue 或无 Issue 变动，仅有两项 Pull Request 处于待合并状态，整体活动量较低。两项 PR 均聚焦于关键 Bug 修复：一项解决 TLS 监听器中 ALPN 协商导致 WebSocket 升级失败的问题，另一项增强 MCP（模型上下文协议）服务器的故障恢复与过期会话处理能力。项目当前处于“修复轮次”阶段，稳定性改善是主要方向，未出现破坏性变更或版本发布。

---

### 2. 版本发布

无新版本发布。

---

### 3. 项目进展

今日无已合并或关闭的 PR，但两项新提交的 PR 标志着重要修复的推进：

- **PR #1291** — 修正 TLS ALPN 协商，将协议限制为 HTTP/1.1  
  浏览器在与 Moltis 建立 TLS 连接时会协商到 HTTP/2，但 Moltis 未实现 RFC 8441 扩展 CONNECT，导致 WebSocket 升级返回 `405`。限制 ALPN 为 HTTP/1.1 后，WebSocket 功能可正常运行。  
  [moltis-org/moltis PR #1291](https://github.com/moltis-org/moltis/pull/1291)

- **PR #1290** — 改进 MCP 启动恢复与过期会话处理  
  跟踪 MCP 服务器启动次数，允许失败后进入 `dead` 状态并在健康监控中按指数退避重试（最多 5 次）；同时将流式 HTTP 404 响应中携带 `Mcp-Session-Id` 的情况视为会话丢失，从而自动恢复。  
  [moltis-org/moltis PR #1290](https://github.com/moltis-org/moltis/pull/1290)

两项 PR 均未包含评论或点赞，但代码变更涉及核心网络与协议层，预计将对 WebSocket 可靠性及 MCP 服务连续性带来实质性提升。

---

### 4. 社区热点

今日无显著讨论或高互动 Issue/PR。两项 PR 作者均为 Harbor404，评论数与点赞数均为 0，社区反馈暂未涌现。可能的原因包括：项目处于早期修复阶段，用户群体尚未对此类底层变更产生即时反馈；或者相关改动已在内部验证，未触发公开讨论。

---

### 5. Bug 与稳定性

收录两项 Bug 修复（均为待合并状态）：

| 严重程度 | 问题描述 | 关联 PR |
|----------|----------|---------|
| 高 | WebSocket 升级因 TLS ALPN 协商为 HTTP/2 而失败，返回 405 | [#1291](https://github.com/moltis-org/moltis/pull/1291) |
| 中 | MCP 服务器启动失败后不再重试，且流式 HTTP 404 导致会话永久丢失 | [#1290](https://github.com/moltis-org/moltis/pull/1290) |

暂无崩溃或回归报告。两项修复均直接针对用户可感知的错误场景，预计合并后将显著提升网络通信的兼容性与服务容错能力。

---

### 6. 功能请求与路线图信号

今日无新功能请求或路线图讨论。PR #1290 中提及的“支持 streamable HTTP 404 会话丢失检测”可视为对 MCP 协议健壮性的增强，虽非新功能，但为未来支持更复杂的会话管理埋下伏笔。目前路线图暂时聚焦于修复现有缺陷，尚未出现新特性信号。

---

### 7. 用户反馈摘要

由于今日无 Issue 更新且 PR 评论为空，无法直接提取用户反馈。但从 PR 摘要可推断用户痛点：

- 浏览器用户试图通过 Moltis 建立 WebSocket 连接时遇到 `405 Method Not Allowed` 错误（PR #1291 背景）。
- 使用 MCP 服务的用户面临“服务器启动失败后永不恢复”以及“网络波动导致会话永久丢失”的问题（PR #1290 背景）。

这些反馈均为未明示但技术上下文强烈暗示的真实场景，修复后预期能直接改善用户体验。

---

### 8. 待处理积压

当前无长期未回应的 Issue 或 PR。两项 PR 均为 2026-10-01 提交，仍在等待审核与合并。建议维护者优先审查 PR #1291，因其修复的 WebSocket 问题可能影响核心功能的使用。PR #1290 涉及重试与状态机逻辑，变更较大，需仔细验证回退机制与边界条件。

---

**日报总结：** 项目今日处于低活跃但高价值的修复阶段，无版本发布与社区讨论，两项待合并 PR 分别解决了 WebSocket 升级兼容性与 MCP 服务稳定性问题。建议尽快合并并发布补丁版本，以解决已知阻碍用户的关键 Bug。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

# CoPaw 项目动态日报（2026-10-02）

---

## 1. 今日速览

过去 24 小时内，CoPaw 项目保持高度活跃：共新增 7 个 Issue（全部为打开状态）和 9 个 Pull Request（2 个已合并/关闭，7 个待合并）。社区集中在 **Provider 兼容性**、**会话可靠性** 以及 **前端 UI 渲染** 三大方向提出问题和修复。暂无新版本发布，但多个高优 Bug 已有对应 PR 进行修复或处于合并流程。整体项目健康度良好，团队响应及时，但仍需关注若干生产环境影响的缺陷。

---

## 2. 版本发布

无新版本发布。

---

## 3. 项目进展

昨日合并/关闭的 2 个 PR 均直接提升了系统的稳定性与兼容性：

- **PR #8069** `fix(agents): restrict deepseek formatters to image media`（[链接](https://github.com/agentscope-ai/CoPaw/pull/8069)）  
  🔒 已关闭（合并）。该修复将 DeepSeek 提供商的默认输入类型从 `[text, image, audio, pdf]` 限制为仅 `image/*`，避免了 PDF 和音频块被序列化为 DeepSeek 不支持的格式而引发的 `400` 错误。这是对昨日 #8062 相关问题的快速跟进。

- **PR #8068** `fix(console): repair CJK emphasis boundaries in chat Markdown`（[链接](https://github.com/agentscope-ai/CoPaw/pull/8068)）  
  🔒 已关闭（合并）。解决了模型生成的 CJK 加粗文本中“句末标点被包在强调符号内”的渲染错误，使中文用户的聊天界面显示更符合预期。

**仍在等待评审的 PR 动向**：  
- #8063（后台任务完成后唤醒父会话）已有首次贡献者提交，核心逻辑基本完成；  
- #8072（隔离 E2E 状态测试）规模较大（XL），旨在解决 CI 环境中的测试稳定性；  
- #7569（Advisor Mode）作为长期功能分支，仍在持续更新，近期无新改动。

---

## 4. 社区热点

| 排名 | 编号 | 标题 | 评论数 | 👍数 | 核心诉求 |
|------|------|------|--------|------|----------|
| 1 | #6274 | [Feature]: 新增 ask_user_question 工具，支持 Human-in-the-Loop | 3 | 1 | Agent 在高风险/模糊场景下应暂停并向用户发起结构化多选题，避免自行猜测或导致副作用。 |
| 2 | #8064 | [Bug]: DeepSeek provider 发送 PDF 后永久破坏会话 | 2 | 0 | 用户在生产环境中发现，发送 PDF 之后的所有请求都返回 400，要求必须包含 `file_id` 或 `file_data`，导致会话完全不可用。 |
| 3 | #8073 | [Bug]: V2.2.2.beta4 无法访问对话页面（局域网访问时） | 1 | 0 | 从 V2.2.1 升级到 beta4 后，其他设备通过局域网访问本机服务时聊天页面无法打开，本地访问正常。 |

**分析**：  
- #6274 代表了用户对 **Agent 可控性** 的强烈需求，希望引入类似“人类审批”的交互模式，这是当前 LLM 应用从“自动化”走向“人机协同”的重要信号。  
- #8064 则反映了一个 **严重生产环境问题**：一旦触发一次 PDF 发送，整个会话废弃，严重影响部署者信心。社区评论中已有用户确认该问题在 `deepseek-flash` 下必现。  
- #8073 指出了 **版本兼容/网络配置** 的回归问题，影响多用户部署场景。

---

## 5. Bug 与稳定性

按严重程度排列（P0: 系统不可用 / 数据损坏，P1: 功能严重受限，P2: 体验不佳）

| 严重等级 | Issue | 标题 | 是否有修复 PR | 状态 |
|----------|-------|------|----------------|------|
| **P0** | [#8064](https://github.com/agentscope-ai/CoPaw/issues/8064) | DeepSeek provider 发送 PDF 后永久破坏会话 | 部分修复：PR #8069 限制了格式，但未解决初始 `send_file_to_user` 的失败场景，需进一步排查 | 打开，未分配 |
| **P0** | [#8073](https://github.com/agentscope-ai/CoPaw/issues/8073) | V2.2.2.beta4 局域网无法访问聊天页面 | 无 | 打开，待分析 |
| **P1** | [#8074](https://github.com/agentscope-ai/CoPaw/issues/8074) | OpenAI provider: `gpt-6` 系列模型连接测试失败 400（`_uses_max_completion_tokens` 白名单过窄） | 无（但用户已定位到代码行） | 打开，需修改白名单正则 |
| **P1** | [#8076](https://github.com/agentscope-ai/CoPaw/issues/8076) | `reload_agent` 在 drain 超时后静默丢弃 in-flight 任务 | 无 | 打开，需改进日志与通知机制 |
| **P2** | [#8066](https://github.com/agentscope-ai/CoPaw/pull/8066) | 空 DataBlock 被序列化为空 data URI 导致所有 Provider 拒绝（PR 已提交） | ✅ PR #8066 已打开 | 待合并 |
| **P2** | [#8067](https://github.com/agentscope-ai/CoPaw/pull/8067) | CJK 强调边界修复（渠道层，与已合并的 #8068 并行） | ✅ PR #8067 已打开 | 待合并 |

**小结**：今日最严重的两个 P0 Bug 均与 **网络/多端访问** 及 **DeepSeek 提供商** 相关，且无直接修复 PR 覆盖全部场景，建议维护团队优先分配资源。

---

## 6. 功能请求与路线图信号

| Issue | 功能简述 | 关联 PR/阶段 | 可能纳入版本 |
|-------|----------|--------------|--------------|
| [#6274](https://github.com/agentscope-ai/CoPaw/issues/6274) | 新增 `ask_user_question` 工具，支持 HITL 结构化交互 | 暂无 PR，社区反应积极 | 若接受，可能作为 v2.3 的新工具 |
| [#8075](https://github.com/agentscope-ai/CoPaw/issues/8075) | 更新 Codex SDK 版本以发现更多模型（如 gpt-5.6 系列） | 仅 Issue，无 PR | 可快速修复的依赖升级 |
| [#8071](https://github.com/agentscope-ai/CoPaw/issues/8071) | 插件可用的主题语义扩展点（override 层） | 无 | 属于 Console 插件系统增强 |
| [#7569](https://github.com/agentscope-ai/CoPaw/pull/7569) | Advisor Mode（双模型协作） | 大型 PR 进行中，等待 review | 可能 v2.3 核心特性 |

**分析**：  
- HITL 工具 (#6274) 获得社区初步认可，若被维护团队采纳，将大幅提升 Agent 在金融、医疗等领域的可用性。  
- Codex SDK 升级 (#8075) 是低风险改进，可快速合入。  
- Advisor Mode 已存在近一个月，建议维护者尽快安排评审，避免分支偏离主线。

---

## 7. 用户反馈摘要

从 Issue 评论中提炼真实用户痛点：

1. **DeepSeek 用户**（#8064 评论）：“我们团队已经在生产环境中切换回旧版本，因为一旦发送一份 PDF，整个会话就废了，需要重新创建。希望尽快修复。”
2. **局域网部署用户**（#8073 评论）：“升级后远程办公室同事完全无法使用聊天页面，但本地开发机正常。怀疑是 WebSocket 或域名校验的问题。”
3. **中文用户**（#8068 评论）：“模型经常把句号也加粗，导致页面显示很丑。感谢团队修复了这个 CJK 问题。”
4. **插件开发者**（#8071 评论）：“目前的主题系统只允许插件修改一个颜色变量，想要更细致的渐变、阴影控制只能 hack 全局 CSS。”

**满意度信号**：多个 Bug 报告者的语气较为急切，说明当前部分用户正被稳定性问题困扰；同时，社区对 CJK 渲染等体验优化表达感谢，表明 UI 细节的修复被下游充分认可。

---

## 8. 待处理积压

以下 Issue/PR 已超过 1 周未获得维护者标记或实质性响应：

| 编号 | 类型 | 标题 | 活跃状态 | 备注 |
|------|------|------|----------|------|
| [#7569](https://github.com/agentscope-ai/CoPaw/pull/7569) | PR | feat(modes): add Advisor Mode (size/XXXL) | 上次更新 2026-10-01（仅 re-base） | 已超过 30 天未获得 maintainer review，可能被遗忘 |
| [#6274](https://github.com/agentscope-ai/CoPaw/issues/6274) | Issue | [Feature] 新增 ask_user_question 工具 | 创建于 2026-07-20，最近一次更新 2026-10-01（社区评论） | 维护者未回复，建议给予初步反馈 |
| [#8064](https://github.com/agentscope-ai/CoPaw/issues/8064) | Issue | DeepSeek provider 会话永久破坏（P0） | 创建 2026-09-30，至今无 assignee | 严重级别高，需紧急确认责任人 |

**提醒维护者**：以上三项建议优先响应，尤其是 #8064 和 #7569，分别涉及生产事故和核心功能分支的长期沉淀。

---

*本日报由 AI 智能体基于 GitHub 公开数据自动生成，仅供项目健康度参考。所有数据截至 2026-10-01 23:59 UTC。*

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我已根据 ZeroClaw (github.com/zeroclaw-labs/zeroclaw) 在 2026-10-02 提供的 GitHub 数据，为您生成了以下项目动态日报。

---

## ZeroClaw 项目每日动态日报 | 2026-10-02

### 1. 今日速览

ZeroClaw 项目今日处于**高活跃度**状态，但正经历一个关键的 **「发布冲刺前的整合与修复」阶段**。核心贡献者（@JordanTheJet， @Aarlington, @IftekharUddin）集中提交了大量 PR，旨在解决安全漏洞、完善权限模型并推进插件系统的成熟度。然而，过去 24 小时内无任何 Issue 被关闭，也无任何 PR 被合并，积压的 50 个待合并 PR 和 38 个活跃 Issue 构成了巨大的交付压力。社区反馈集中在**安全、数据丢失风险和核心功能回归**等问题上，表明项目在快速迭代时正面临严峻的稳定性与质量挑战。

### 2. 版本发布

**无**

### 3. 项目进展

今日虽无 PR 被合并，但发起了一系列意义重大的 PR，标志着项目在多个关键领域取得了实质性推进，主要集中在三大方向：

-   **安全与权限模型重塑（主导者：@Aarlington）：** 一套由 4 个大型 PR 组成的连锁修复栈（PR #11408, #11409, #11410, #11411），旨在全面修复访问控制、代理授权和 SOP 引擎的安全弱点和逻辑缺陷。这对于保护用户数据和系统安全至关重要。
-   **公共运行时边界完成（主导者：@JordanTheJet）：** PR #11174 和 #11187 致力于重构运行时核心，使其能够被外部嵌入并明确提供能力，这为未来 ZeroClaw 作为库或服务被集成奠定了基础。
-   **插件系统与开发者体验（主导者：@IftekharUddin）：** 一系列 PR（如 #11302, #11308, #11309）旨在完善插件安装、绑定、能力清单和二进制尺寸分析等流程，这是向 v0.8.6 发布目标迈进的关键一步，目的是打造一个稳固、可扩展的插件生态系统。

### 4. 社区热点

-   **最受关注 Issue [#9600] - 会话持久化契约所有权与分层排序** (评论: 16)
    -   **链接：** [Issue #9600](https://github.com/zeroclaw-labs/zeroclaw/issues/9600)
    -   **分析：** 该追踪器 Issue 获得了 16 条评论，成为了社区最关注的焦点。这表明有 4 个独立的工作流都在触及同一个核心契约，社区对于**架构混乱、责任不清**的担忧超过了具体 Bug。开发者们急需明确本次重构的所有权以避免冲突和回归。

-   **高关注度 Bug 讨论：**
    -   **CPU 死循环问题** ([#9799](https://github.com/zeroclaw-labs/zeroclaw/issues/9799))：一个长期运行的守护进程（17小时）消耗 140-177% CPU 的严重问题，获得了 5 条评论。社区迫切需要一个可复现的步骤。
    -   **SOP 引擎执行顺序错乱** ([#10066](https://github.com/zeroclaw-labs/zeroclaw/issues/10066))：SOP 引擎在没有验证当前步骤输出时就提前执行后续步骤，这将导致工作流执行混乱，开发者对此感到担忧。

### 5. Bug 与稳定性

今日报告的 Bug 主要集中在**数据丢失/安全风险 (S0)** 和**工作流阻塞 (S1)** 两个级别，项目稳定性亮起红灯。

-   **严重等级 S0 (数据丢失/安全风险):**
    -   [#10495] `Config::save()` 可能将运营商配置清空为几乎空文件。**极高风险，尚无修复 PR。**
    -   [#11198] 委托代理的内存工具丢失主体作用域，导致数据访问到错误的空间。**已有跟进讨论，PR #11409 旨在修复。**
    -   [#11239] 拥有者会话未正确路由到私有内存平面。**已有跟进讨论，PR #11409 和 #11410 旨在修复。**

-   **严重等级 S1 (工作流阻塞):**
    -   [#10066] SOP 引擎执行顺序错乱。
    -   [#11387] `zerocode` 再次忽略启动目录（#10609 回归问题），强制使用 agent 工作区。**这是一个已修复过的功能再次出现回归，社区极为不满。**
    -   [#11369] Docker 镜像启动即退出，且中断的升级可能损坏数据库。**新报告，尚无修复 PR。**
    -   [#11418] "Copy" 一键复制功能失效。**新报告，影响用户交互体验。**

-   **严重等级 S2 (功能退化):**
    -   [#11333] 技能审核工具无法发现通过`skill_bundles`分配的技能。
    -   [#11332] 技能学习循环在特定渠道（如矩阵、webhook）中不运行。
    -   [#11257] WhatsApp Web 渠道丢弃传入媒体文件的描述文字。
    -   [#11204] OpenRouter 费用显示为`$0.00`，无法正确摄入使用成本。

### 6. 功能请求与路线图信号

-   **社区呼声高的新需求：**
    -   [#11416] Slack 的"正在输入…"状态消失：有用户抱怨在 v0.8.5 后，Slack  channel 中不再显示 agent 的“thinking”状态。这虽是小问题但直接影响用户体验。
    -   [#11418] 修复“复制”按钮：这是一个基础功能的 Bug 报告，也代表了用户对 UI/UX 稳定性的需求。
    -   **UI 配置编辑（隐含需求）：** PR #11419 试图让用户在 Web UI 和 TUI 中编辑 “secret key/value maps”，这回应了社区对配置便捷性和可操作性的长期诉求。

-   **可被纳入路线图的信号：**
    -   **公共 API 与嵌入能力：** PR #11174 和 #11187 积极推进“公共运行时组成边界”的完成，这表明团队可能计划在未来版本中提供更稳定的 API 以允许外部应用或服务嵌入 ZeroClaw Runtime，这是一个重要的路标信号。
    -   **插件系统的成熟度：** 多个 PR（#11302, #11305, #11308, #11309）的涌现，明确指示团队正在全力冲刺 **v0.8.6** 的插件系统里程碑。这将是下一个版本最核心的特性。

### 7. 用户反馈摘要

从 Issue 评论中可以提炼出以下真实用户反馈：

-   **痛点：**
    -   **配置丢失：** 用户 @JordanTheJet 报告“`Config::save()` can replace...with a near-empty file”（#10495），这是一个极其严重的痛点，可能导致用户全部配置丢失。
    -   **数据访问安全：** 用户 @Audacity88 报告“Delegated memory tools lose principal scope”（#11198），导致子代理能访问父代理的私有数据，这对于多租户或企业用户是致命缺陷。
    -   **无意义的认证行为：** 用户 @IftekharUddin 指出“config set...save an authorization edit the daemon refused”（#11323），给用户造成困惑，不知道配置是否生效。
    -   **功能回归：** 用户 @singlerider 报告“zerocode ignores its launch directory again”（#11387），这是对已修复 bug 的回归，直接破坏了用户的工作流习惯，表明测试覆盖不足。

-   **满意之处：**
    -   用户对项目的**迭代速度**和**主动解决问题**的努力表示认可。例如，Issue #10162 中该项目之前通过 PR #11098 解决了安装种子失败时可以重试的问题。
    -   用户 @bellorr 虽然报告了 bug，但其 agent 的 `skill_bundles` 功能“load and work fine”，表明核心功能在大部分情况下是稳定的。

### 8. 待处理积压

以下是一些长期存在且未得到有效回应的关键 Issue，建议维护者关注：

-   **高风险且被标记为 `no-stale` 的积压：**
    -   [#9394] `gateway.pairing_dashboard` 配置项完全无效，且配对码永久有效（2026-07-26 创建）。**这是一个明确的安全风险。** [Issue Link](https://github.com/zeroclaw-labs/zeroclaw/issues/9394)
    -   [#9624] Registry WIT 版本与主分支代码不兼容，破坏了已发布的组件（2026-08-01 创建）。**这直接阻碍了插件生态的运行。** [Issue Link](https://github.com/zeroclaw-labs/zeroclaw/issues/9624)
    -   [#7539] 增加对 `llama.cpp` 模型路由器的支持（2026-06-12 创建）。**该特性需求持续存在，但未进入深度开发阶段。** [Issue Link](https://github.com/zeroclaw-labs/zeroclaw/issues/7539)

-   **其他较重要积压：**
    -   [#11204] OpenRouter 费用追踪完全失效，影响用户对成本的控制和审计（2026-09-27 创建）。虽然标记为 `p1`，但仍需更多关注。 [Issue Link](https://github.com/zeroclaw-labs/zeroclaw/issues/11204)
    -   [#11332] 技能学习循环无法在网页 UI 和 channel 中运行，限制了功能覆盖面（2026-10-01 创建）。 [Issue Link](https://github.com/zeroclaw-labs/zeroclaw/issues/11332)

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*