# OpenClaw 生态日报 2026-09-25

> Issues: 500 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-09-25 00:47 UTC

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

好的，请查收基于OpenClaw (github.com/openclaw/openclaw) 2026-09-24日数据生成的日报。

---

## OpenClaw 项目动态日报 — 2026-09-25

### 1. 今日速览

今日项目活跃度**极高**。单日内有高达500条Issues和500条PR的更新，显示出社区强烈的反馈和开发热情。然而，开发迭代中暴露出的稳定性问题也极为突出，**P0级崩溃和回归问题**（如网关假死、核心CPU 100%、更新回滚等）成为社区讨论焦点，表明项目当前可能处于一个密集的Bug修复和稳定性加固周期。虽无新版本发布，但已有多个关键修复PR提交，项目正积极向 **2026.9.7** 版本冲刺。

### 2. 版本发布

无新版本发布。

### 3. 项目进展

今日虽然PR合并/关闭数量（119条）低于待合并数量（381条），但依然有多个关键修复和重构被合入主线，显著推进了项目的稳定性与代码质量。

- **关键问题修复**：
    - [#157107](https://github.com/openclaw/openclaw/issues/157107)（**P0, 已关闭**）：修复了 `2026.9.6` 版本中 `prepared-model-catalog` 工作线程无限循环重建插件，导致所有Agent运行被阻塞的严重问题。该修复直接挽救了 `2026.9.6` 版本的可用性。
    - [#157011](https://github.com/openclaw/openclaw/issues/157011)（**P0, 已关闭**）：解决了 `2026.9.5` 到 `2026.9.6` 的托管更新始终回滚的问题，根因是更新历史记录中的 `RangeError`。此修复保证了升级流程的可靠性。
    - [#137705](https://github.com/openclaw/openclaw/issues/137705)（**已关闭**）：修复了Telegram频道中，当Markdown链接包含 `file://` 等未授权协议时，会泄露源代码的问题，提升了信息安全和用户体验。

- **重大重构与性能优化**：
    - [#157294](https://github.com/openclaw/openclaw/pull/157294)（**已合并**）：对Agent的 Runner、Harness（适配器）和恢复逻辑进行了重构 (“deslop”)，旨在消除代码重复，统一并稳定核心路径。
    - [#154069](https://github.com/openclaw/openclaw/pull/154069)（**待审查**）：将会话记录（transcript）的“投影”操作（一种繁重的SQL发布操作）卸载到后台线程执行，旨在避免阻塞主线程，提升网关整体响应速度。

### 4. 社区热点

今日社区讨论的焦点高度集中在**系统稳定性与资源消耗**上，尤其是以下几个问题引发了激烈讨论：

- **[#144911](https://github.com/openclaw/openclaw/issues/144911) [Bug]: MCP Server 初始化超时导致整个网关崩溃** (评论: 30)
    - **诉求**: 这是一个严重的崩溃问题，当MCP Server在30秒内未能完成初始化时，会导致整个网关进程因未处理的Promise拒绝而崩溃。用户不仅要求修复这个Bug，更要求一个更健壮的、不会导致级联故障的错误处理机制。

- **[#155753](https://github.com/openclaw/openclaw/issues/155753) [Bug]: 模型目录过期/重建循环导致单CPU核心 100%** (评论: 23)
    - **诉求**: 这是一个刺痛的性能问题。`readFullModelCatalog()` 函数在每次读取时都触发 `refreshExpiredCatalog()`，而目录的TTL（~60秒）很短，形成了无限循环，导致一个CPU核心被100%占用。用户底层需求是紧急的性能修复和更智能的缓存刷新策略。

- **[#149538](https://github.com/openclaw/openclaw/issues/149538) [Bug]: 网关 Ready 后无法提供服务，健康检查超时** (评论: 21)
    - **诉求**: 一个“假死”问题。网关显示“ready”但实际事件循环被阻塞，无法响应任何请求。该问题自2026年9月中旬报告以来，评论数持续增长，显示出大量用户在特定环境中（如大规模Agent部署）遭遇此问题，成为当前最严重的可用性阻塞点之一。

### 5. Bug 与稳定性

今日报告的Bug数量极多，且严重程度普遍很高。以下按严重性排列：

- **P0 (崩溃/阻塞/发布阻塞)**:
    - **[#149538](https://github.com/openclaw/openclaw/issues/149538)**: 网关“假死”问题，严重的可用性缺陷。**无关联Fix PR**。
    - **[#157107](https://github.com/openclaw/openclaw/issues/157107)**: 插件重建循环阻塞Agent运行。**已修复并关闭**。
    - **[#157011](https://github.com/openclaw/openclaw/issues/157011)**: 更新始终回滚。**已修复并关闭**。
    - **[#157234](https://github.com/openclaw/openclaw/issues/157234)**: 因“agent数据库租约活跃”导致更新恢复失败。**无关联Fix PR**。
    - **[#115256](https://github.com/openclaw/openclaw/issues/115256)**: 桌面应用导致网关启动循环。**无关联Fix PR**。
    - **[#155859](https://github.com/openclaw/openclaw/issues/155859)**: 网关启动时间与启用插件数量成线性增长。**无关联Fix PR**。
    - **[#152839](https://github.com/openclaw/openclaw/issues/152839)**: 在部分系统（如Synology NAS）上因 `openat2` 系统调用不可用导致网关启动失败。**无关联Fix PR**。

- **P1 (重要功能受损/性能严重下降)**:
    - **[#144911](https://github.com/openclaw/openclaw/issues/144911)**: MCP 超时导致网关崩溃。**无关联Fix PR**。
    - **[#157617](https://github.com/openclaw/openclaw/issues/157617)**: 会话写入队列因数据库维护工作长时间等待。**无关联Fix PR**。
    - **[#110190](https://github.com/openclaw/openclaw/issues/110190)**: 运行时上下文载体放错位置导致模型混淆。**无关联Fix PR**。
    - **[#119087](https://github.com/openclaw/openclaw/issues/119087)**: 网关冷启动时间退化2.5倍。**有关联PR**。

- **P2 (中等影响/非关键路径问题)**:
    - **[#156191](https://github.com/openclaw/openclaw/issues/156191)**: 多Agent场景下目录生成产生内存压力。**无关联Fix PR**。
    - **[#156930](https://github.com/openclaw/openclaw/issues/156930)**: Codex 插件状态打开失败，每30秒报错一次。**无关联Fix PR**。

### 6. 功能请求与路线图信号

- **智能会话自动命名** ([#99583](https://github.com/openclaw/openclaw/issues/99583))：用户提议利用已有的LLM自动生成器，根据对话内容懒加载地为会话生成标题，并支持主题变化后自动重命名。此功能若实现将极大改善多会话管理体验，属于期待值较高的功能。
- **持久化的自然语言规则学习** ([#41366](https://github.com/openclaw/openclaw/issues/41366))：用户希望Agent在群聊中学习的自然语言规则能持久化保存，并解决与工作区规则（`AGENTS.md`）的冲突。这反映了社区对更稳定、可控的Agent行为的需求。
- **多模型提供商配置** ([#81960](https://github.com/openclaw/openclaw/issues/81960))：用户希望在`openclaw onboard`初始化流程中就能配置多个模型提供商，而不是在后期手动配置。这表明简化初始设置流程是社区普遍诉求。
- **`openat2` 优雅降级** ([#152839](https://github.com/openclaw/openclaw/issues/152839))：有用户请求在 `openat2` 系统调用不可用时（如在特定容器或NAS环境中），项目能提供优雅降级方案或清晰的错误提示，而非直接崩溃。这指向了对更广泛环境兼容性的需求。已有PR [#157661](https://github.com/openclaw/openclaw/pull/157661) 尝试解决。

### 7. 用户反馈摘要

- **痛点**:
    - **崩溃和阻塞是最大痛点**：从 [Issue #144911](https://github.com/openclaw/openclaw/issues/144911) 和 [#149538](https://github.com/openclaw/openclaw/issues/149538) 的评论区可以看出，用户对“由于一个微小组件故障就导致整个系统宕机”的脆弱性表示强烈不满。
    - **资源消耗令人担忧**：CPU 100%占用([#155753](https://github.com/openclaw/openclaw/issues/155753))和内存泄漏([#156191](https://github.com/openclaw/openclaw/issues/156191))问题让资源受限环境（如树莓派、低配VPS）的用户感到困扰。
    - **升级体验不佳**：[Issue #157011](https://github.com/openclaw/openclaw/issues/157011)中用户在升级时遭遇回滚，而[#142580](https://github.com/openclaw/openclaw/issues/142580)中用户报告升级表面成功但核心功能失效，这些都透露了用户在升级过程中的挫败感。
- **使用场景**:
    - 用户广泛使用 **MCP Server** ([#144911](https://github.com/openclaw/openclaw/issues/144911)) 来集成外部工具，但其稳定性和连接性（[#98435](https://github.com/openclaw/openclaw/issues/98435)）是核心关注点。
    - **Telegram 频道** ([#143278](https://github.com/openclaw/openclaw/issues/143278), [#137705](https://github.com/openclaw/openclaw/issues/137705)) 依然是最活跃的渠道之一，对其消息格式和内部信息泄露问题非常敏感。
    - 大量**多Agent部署**的用户，正向系统并发处理能力提出挑战，如网关假死([#149538](https://github.com/openclaw/openclaw/issues/149538))和Catalog重建风暴([#157107](https://github.com/openclaw/openclaw/issues/157107))。
- **满意之处**: 用户对智能体强大的任务处理能力和丰富的集成渠道（如Telegram、代码CLI等）给予了肯定，但稳定性的问题让这些优势大打折扣。

### 8. 待处理积压

以下为长期未关闭、严重影响体验或有较高价值但尚未得到及时响应的Issue，建议维护者优先关注：

- **[#112423](https://github.com/openclaw/openclaw/issues/112423)** (创建于 2026-07-21): **P1** - 大型SQLite转录清理阻塞网关事件循环。该功能是日常会话管理的一部分，但存在高达20条评论，讨论了两个月仍未解决，可能涉及到艰难的架构决策。
- **[#98435](https://github.com/openclaw/openclaw/issues/98435)** (创建于 2026-07-01): **P1** - MCP循环回环在网关重启后无法自动重连。该问题直接影响用户重启服务后的使用体验，且 “recovered=1” 状态存在误导性，已存在近三个月。
- **[#110190](https://github.com/openclaw/openclaw/issues/110190)** (创建于 2026-07-17): **P1** - 运行时上下文载体位置错误导致模型混淆。此问题影响所有与模型交互的准确性，社区给出了详细的根因分析，亟需有Product Decision的介入，以确定最优解决方案。

---

## 横向生态对比

好的，作为 AI 智能体与个人 AI 助手开源生态的资深技术分析师，基于您提供的 2026-09-25 各项目动态，我为您生成一份横向对比分析报告。

---

### AI 智能体与个人 AI 助手开源生态横向对比分析报告 (2026-09-25)

**报告日期：** 2026-09-25
**分析师：** AI 开源生态技术分析师

---

#### 1. 生态全景

当前，个人 AI 助手与自主智能体开源生态呈现出 **“核心驱动、多点开花、集体冲刺稳定性”** 的态势。以 OpenClaw 为生态基石，一批各有侧重的项目（如 NanoBot、Hermes Agent、ZeroClaw）正在快速迭代，形成差异化竞争。然而，生态的整体健康度受到**稳定性瓶颈**的严峻挑战——P0级崩溃、资源泄漏和升级回滚成为跨项目的共性问题，这表明生态正从“功能扩展期”艰难地向“质量巩固期”过渡。同时，社区对**多Agent协作、生产级部署、安全管控和成本优化**的需求空前高涨，正推动项目向平台化和企业级演进。

#### 2. 各项目活跃度对比

| 项目名称 | 今日活跃度 | Issues (新开/活跃) | PRs (待合并/已合并) | Release | 健康度评估 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | **极高** | ~500条 | ~500条 (381待/119已合并) | 无 | **有风险**：社区极度活跃，但大量P0级崩溃和回归问题暴露，处于密集修补期 |
| **NanoBot** | **高** | 53条 | 39条 (13待/26已合并) | 无 | **良好**：维护者响应迅速，合并效率高，重点关注WebUI本地化与渠道兼容性 |
| **Hermes Agent** | **高** | 50条 | ~48条 (48待/2已合并) | **v0.21.5** | **良好**：版本发布稳定，但PR积压严重，社区贡献闭环效率需提升 |
| **ZeroClaw** | **极高** | 27条 | 50条 (38待/12已合并) | 无 | **有风险**：安全跟踪与严重Bug并存，但CI优化和核心修复积极，处于功能与稳性定并重阶段 |
| **LobsterAI** | **高** | 16条 (已关闭) | 46条 (已合并/关闭) | 无 | **健壮**：集中清理历史债务和UI/UX打磨，进入稳定性冲刺，代码整合能力强 |
| **CoPaw** | **中高** | 31条 | 23条 (17待/6已合并) | 无 | **良好**：Bug修复与功能推进并行，多租户和记忆问题社区讨论热烈 |
| **NullClaw** | **中高** | 12条 | 25条 (8已合并) | 无 | **良好**：核心稳定性修复和文档完善取得实质进展，社区互动健康 |
| **NanoClaw** | **中等** | 2条 | 13条 (3已合并) | 无 | **良好**：聚焦于Iron Proxy功能修复，社区虽小但反馈精准，响应快速 |
| **PicoClaw** | **低** | 2条 | 8条 (0已合并) | 无 | **停滞风险**：PR合并停滞，重复Bug报告未解决，移动端体验受损 |
| **IronClaw** | **低** | 1条 | 1条 | **v1.4.1-rc.2** | **稳定**：进入稳定迭代期，版本发布解决特定配置Bug，社区互动不多 |
| **TinyClaw** | - | - | - | - | **静默**：过去24小时无活动 |
| **Moltis** | - | - | - | - | **静默**：过去24小时无活动 |
| **ZeptoClaw** | - | - | - | - | **静默**：过去24小时无活动 |

#### 3. OpenClaw 在生态中的定位

- **生态核心与基线参照：** OpenClaw 是无可争议的生态核心，其社区规模和问题量级（单日500+ Issue/PR）远超其他项目。它是所有衍生项目（如 PicoClaw、NanoClaw）和受影响项目（如 LobsterAI 对其有原生支持）的 **“功能与架构基准”** 。其他项目在 API 设计、插件模型和 MCP 集成等方面都高度参照 OpenClaw。
- **优势：** 拥有最庞大的插件生态、最丰富的渠道集成（Telegram、Discord等）和最活跃的贡献者社区。其功能全面性（网关、Agent、MCP、记忆）使其成为“全栈”个人 AI 助手的标杆。
- **劣势与风险：** 当前正经历 **“成长阵痛”** ，版本迭代过快导致稳定性失控。大量P0级Bug（网关假死、CPU100%打满）直接冲击了用户信任。其“大而全”的架构在低资源环境（如树莓派）下表现不佳，给PicoClaw等轻量化项目留下了生存空间。
- **技术路线差异：** 相比 ZeroClaw 强调安全合规和独立网络层，OpenClaw 更侧重于**功能集成与社区驱动**。其问题修复的优先级往往由社区呼声决定，而非严格的产品路线图。这与 LobsterAI 由单一商业实体（网易有道）主导、目标明确的路线形成对比。

#### 4. 共同关注的技术方向

多个项目呈现出高度重合的技术诉求，这表明了生态级的发展瓶颈和机遇：

1.  **稳定性与健壮性提升:**
    - **涉及项目：** **OpenClaw**, **NanoBot**, **Hermes Agent**, **CoPaw**, **ZeroClaw**, **NullClaw**
    - **具体诉求：**
        - **级联故障保护：** 避免单个组件（如MCP Server、插件）崩溃导致整个网关宕机（OpenClaw #144911）。
        - **资源死锁与泄漏：** 解决上下文压缩死锁（NanoBot #5849）、CPU 100%循环（OpenClaw #155753）、内存泄漏（CoPaw #7966）。
        - **升级/降级路径安全：** 确保升级过程可回滚且不损坏数据（OpenClaw #157011, Hermes Agent #63577）。
    - **趋势洞察：** 整个生态正在为过去的快速功能扩张付出“技术债务”代价，未来数月，“缺陷修复”将取代“功能开发”成为主旋律。

2.  **多Agent协作与集群管理:**
    - **涉及项目：** **ZeroClaw**, **CoPaw**, **NanoBot**
    - **具体诉求：**
        - **Agent间通信：** 允许不同会话的Agent直接交换消息，无需人工介入（ZeroClaw #11027）。
        - **多租户与资源隔离：** 支持团队级多用户，并为主机上的每个Agent设置资源上限（CoPaw #7318, ZeroClaw #10970）。
        - **会话管理与状态同步：** 多窗口/多设备间的会话状态同步（Hermes Agent #121531）。
    - **趋势洞察：** AI 助手正从“单用户单实例”向“多Agent协作集群”演进，这要求底层架构对状态管理、资源隔离和网络通信有更高级的支持。

3.  **安全性与企业级管控:**
    - **涉及项目：** **ZeroClaw**, **Hermes Agent**, **NanoClaw**
    - **具体诉求：**
        - **敏感信息保护：** 防止秘密日志泄露（Hermes Agent #121566）、密码同步绕过审查（Hermes Agent #115104）。
        - **细粒度审批与权限：** 支持无交互场景下的预设审批规则（ZeroClaw #10968），以及按主机维度的自动审批（NanoClaw #3881）。
        - **CVE/漏洞修复：** 持续追踪并修复依赖库中的安全漏洞（ZeroClaw #8519）。
    - **趋势洞察：** 随着Agent被赋予更多权限（执行命令、调用API），安全管控从“必要项”升级为“决定生死”的核心功能。缺乏安全方案的项目将在企业级部署中被淘汰。

4.  **轻量化与本地化部署:**
    - **涉及项目：** **NullClaw**, **CoPaw**, **TinyClaw/ZeptoClaw (静默)**
    - **具体诉求：**
        - **低资源设备兼容：** 能在树莓派、NAS等设备上运行（OpenClaw #152839, NullClaw #871）。
        - **断网/非联网场景：** 用户希望在无法联网的情况下也能使用核心功能。
        - **WebUI本地化：** 提供多语言界面，降低非英语用户门槛（NanoBot #5367）。
    - **趋势洞察：** 个人用户对**数据主权**和**低成本运行**的渴望，催生了对更轻量、更高效、能完全本地运行解决方案的强烈需求。这为PicoClaw、TinyClaw等“微型版”提供了市场机会。

#### 5. 差异化定位分析

| 项目名称 | 功能侧重 | 目标用户 | 核心差异化 / 技术架构 |
| :--- | :--- | :--- | :--- |
| **OpenClaw** | 全功能个人AI助手/网关 | 开发者、技术爱好者、社区贡献者 | **生态核心**：功能全面，集成度高，社区驱动。架构复杂，但生态资源最丰富。 |
| **NanoBot** | UI/UX 优先的AI助手 | 追求体验的终端用户、Web重度使用者 | **WebUI极致优化**：在界面本地化、多渠道兼容性上投入巨大。运行轻量，响应迅速。 |
| **Hermes Agent** | 桌面端AI原生体验 | 开发者、需要强交互的桌面用户 | **桌面端为核心**：深度绑定IDE与桌面环境，提供类似Copilot的集成体验。架构上强调本地优先。 |
| **ZeroClaw** | 生产级安全AI网关 | 企业、有安全合规需求的团队 | **零信任安全架构**：内置OIDC、SOP控制面、细粒度权限。联网层（ZeroRelay）可定制，强调审计与合规。 |
| **CoPaw** | 企业级协作Agent平台 | 团队协作、企业IT | **多租户与渠道隔离**：支持飞书、企业微信等国内主流办公软件。记忆与上下文管理是其重点。 |
| **LobsterAI** | 开发者编码协作助手 | 中国开发者、AI编码用户 | **垂直深耕AI编码**：深度集成OpenClaw生态，但功能聚焦于代码生成与审查。由网易有道主导，产品目标明确。 |
| **NullClaw** | 社区驱动的通用AI助手 | 开发者、社区贡献者 | **维护效率高**：尽管社区规模不比OpenClaw，但Bug修复与PR合并速度快。文档质量好（中英双语）。 |
| **NanoClaw** | Iron Proxy 实验性网关 | 寻求更智能代理工作流的开发者 | **聚焦Iron Proxy**：唯一一个为Agent自主调用外部服务提供审批与管理框架的项目。实验性、技术前沿。 |
| **PicoClaw** | 移动端轻量AI助手 | 移动端重度用户 | **极简移动端体验**：专为移动设备（如Pocket）设计的TUI和低功耗版本。牺牲部分功能换取极致轻量。 |
| **IronClaw** | 基础平台稳定迭代 | 自托管用户、稳定性追求者 | **保守稳定优先**：不追求新功能，专注于修复已知Bug和提升部署兼容性，是生态中的“稳健基石”。 |

#### 6. 社区热度与成熟度

- **活跃度第一梯队 (极高/高):**
    - **OpenClaw, ZeroClaw, LobsterAI, NanoBot:** 这些项目拥有庞大的社区基础，每日处理和生成大量Issue/PR，是生态创新的主要引擎。其中 **OpenClaw** 和 **ZeroClaw** 问题最多，暴露了快速扩张的复杂性；**LobsterAI** 则显示出强大的代码整合能力，正在进行深度维护。
- **活跃度第二梯队 (中高/中等):**
    - **Hermes Agent, NullClaw, CoPaw, NanoClaw:** 这些项目社区规模适中，但互动健康，Bug反馈精准，开发进度可预测。**Hermes Agent** 和 **CoPaw** 正在从功能快速迭代向质量巩固过渡；**NullClaw** 和 **NanoClaw** 则展现出“小而精”的特点。
- **活跃度第三梯队 (低/静默):**
    - **PicoClaw, IronClaw, TinyClaw, Moltis, ZeptoClaw:** 这些项目或是进入了稳定期（IronClaw），或是处于停滞/低维护状态（PicoClaw, TinyClaw, Moltis）。其中 **PicoClaw** 的PR合并停滞是一个危险信号，提示其可能缺乏持续维护资源。

#### 7. 值得关注的趋势信号

1.  **从“功能盛宴”到“稳定饥荒”**：整个生态的社区声音表明，**首次配置成功率和长期运行稳定性**远比一个“酷炫的新功能”更重要。开发者对“开箱即用”、“不崩溃”、“升级安全”的诉求达到了顶峰。这是一个明确的信号：**项目维护的下半场，是“可靠性工程师”而非“功能工程师”的舞台。**
2.  **“推理成本”成为核心设计因素**：用户不仅关心API调用费用（OpenClaw #81960, ZeroClaw #11103），更关心Token浪费问题（LobsterAI #2230, #2121）。这意味着，下一代AI助手需要在**上下文管理、记忆压缩、模型选择**等环节进行精细化计算，将“经济性”作为与“智能性”并列的核心指标。
3.  **安全是硬门槛，而非附加功能**：从ZeroClaw的安全跟踪器到Hermes Agent的凭证泄露，再到NanoClaw的代理审批，**安全已非锦上添花，而是进入企业级市场的入场券**。未来，任何缺乏内置OIDC、RBAC、审计日志和沙箱执行能力的项目，将自动被企业IT团队屏蔽。
4.  **“省电”与“低功耗”重获关注**：随着个人AI设备（如RISC-V笔记本、AI Pin）普及，一批TinyClaw、ZeptoClaw类项目虽然在日报中静默，但其代表的**“极致省电AI”**方向需求真实存在。**能效比**（每瓦特产生的智能）将成为衡量个人AI助手优劣的新维度。这对于开发嵌入式或移动端AI应用的开发者有重要参考价值。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，这是根据您提供的 NanoBot GitHub 数据生成的 2026-09-25 项目动态日报。

---

## NanoBot 项目动态日报 | 2026-09-25

### 今日速览

今日项目社区活跃度极高，Issues 和 PR 更新总量达 53 条，显示出强劲的开发和维护动力。**合并/关闭的 PR 数量（26）远超待合并数量（13）**，表明维护团队响应迅速，清除积压的效率很高。社区讨论热点集中在 **WebUI 本地化**、**渠道兼容性** (如 Matrix/Discord/飞书)、**后台任务稳定性** 以及 **新 API 适配** 上。整体来看，项目正稳步推进，重点关注用户体验的本地化、渠道功能的完善以及底层稳定性的增强。

### 版本发布

- **无新版本发布**

### 项目进展

今日共有 **26 个 PR 被合并或关闭**，项目在多个方面取得了实质性进展：

- **核心稳定性与错误处理**:
    - **PR #5724** 和 **PR #5431** 已合并，解决了困扰已久的 `AgentLoop.schedule_background()` 无法捕获并报告后台任务异常的问题。这提升了系统的健壮性，确保失败的后台操作（如会话归档、标题生成）能被正确记录。
    - **PR #5807** 已合并，修复了 Discord 渠道在停止时未清理反应（emoji）任务状态的问题，避免了内存泄漏和状态不一致。
    - **PR #5292** 已合并，修复了 Matrix 渠道的“回复”功能，现在机器人能正确地将回复与用户的原消息关联起来，改善了 Matrix 用户的使用体验。

- **用户界面与WebUI**:
    - **PR #5367** (`feat(webui): localize agent activity`) 已合并。这是一个重要的功能更新，现在 Agent 的活动状态文本（如“搜索文件”、“读取文件”）会跟随 WebUI 的界面语言显示，完成了 WebUI 本地化的最后一块拼图。
    - **PR #5905** 和 **PR #5904** 已合并，主要优化了 WebUI 的页面路由、聊天加载性能和移动端交互，减少了不必要的页面重载和数据请求。

- **API与新功能**:
    - **PR #1387** (`feat: add Anthropic extended thinking support`) 已合并。为 Anthropic 模型增加了“扩展思考”模式，支持设置 token 预算，同时保持了与 OpenAI 系列模型的兼容性。

### 社区热点

今日讨论和关注度最高的议题集中在以下几个方面：

1.  **新 API 适配需求 (Issue #5896)**
    - **简介**: 用户请求为 `opencode_go` 的 `muse-spark` 模型系列增加对 **OpenAI Responses API** (`/responses`) 的支持，因为当前的 `Chat Completions` 端点接口返回 500 错误。
    - **链接**: [Issue #5896](https://github.com/HKUDS/nanobot/issues/5896)
    - **洞察**: 此 Issue 被打上 `feature request` 和 `priority: p2` 标签，且已有对应的 **PR #5906** 正在处理中。这表明社区对多模型/多 API 格式兼容的需求非常迫切，项目团队也已迅速响应。

2.  **自动上下文压缩死锁 (Issue #5849)**
    - **简介**: 用户报告了严重的稳定性问题：自动压缩路径 (`summarize_transcript`) 缺乏 token 预算保护，当对话历史过长时，压缩操作本身会因超出模型输入限制而失败，导致上下文永远无法恢复。
    - **链接**: [Issue #5849](https://github.com/HKUDS/nanobot/issues/5849)
    - **洞察**: 这是一个影响核心功能的 Bug，可能导致长对话会话无法继续或丢失信息。社区对此表现出高度担忧，因为它直接关系到 AI 对话的连续性和可靠性。

3.  **升级冲突与用户预期 (Issue #5881)**
    - **简介**: 多名用户在升级到 0.3.5 版本后遇到困扰，新版本严格限制了 `_nanobot` 配置目录必须位于 workspace 之外，与部分用户的多实例部署习惯冲突，导致无法启动。
    - **链接**: [Issue #5881](https://github.com/HKUDS/nanobot/issues/5881)
    - **洞察**: 该 Issue 在短时间内获得关注并已关闭，说明维护者与用户展开了沟通。这反映出项目在快速迭代中，一些安全性或架构调整可能会影响既有用户的部署习惯，需要更清晰的迁移说明。

### Bug 与稳定性

今日报告的 Bug 按严重程度排列如下：

- **严重 (Critical)**:
    - **自动压缩死锁 (#5849)**: `summarize_transcript` 路径无 token 预算保护，可能导致长对话完全卡死。**暂无直接 fix PR**，但相关 PR [#5257](https://github.com/HKUDS/nanobot/pull/5257) 对持续目标循环的修复可能与此相关。
    - **飞书渠道内部消息泄露 (#5903)**: 内部分隔符消息（"Continue the active task..."）意外发送给用户。这是一个信息泄露和干扰用户的问题。**暂无 fix PR**。

- **中等 (Medium)**:
    - **Copilot GPT-6 模型系列兼容性问题 (#5898)**: 用户报告 `v0.3.5` 版本无法通过 GitHub Copilot 使用 GPT-6 系列模型。**暂无 fix PR**。
    - **升级配置冲突 (#5881)**: 0.3.5 版本的目录校验规则导致用户升级失败。**已关闭**，表明已解决或达成共识。

- **低 (Low)**:
    - **Discord 运行时残留任务 (#5806)**: `_reset_runtime_state()` 未清理反应任务。**已有 fix PR [#5864](https://github.com/HKUDS/nanobot/pull/5864)** 和已合并的 **[#5807](https://github.com/HKUDS/nanobot/pull/5807)**。

### 功能请求与路线图信号

今日用户提出了多项新功能请求，结合已有 PR，判断以下功能很可能进入下一版本：

- **新 API 提供商支持**:
    - **OpenCode Go 的 Responses API (#5896)**: **已有对应 PR [#5906](https://github.com/HKUDS/nanobot/pull/5906) 正在处理中**，预计很快会合并。
    - **Opper 内置提供商 (#5845)**: **已有 PR [#5845](https://github.com/HKUDS/nanobot/pull/5845) 正在处理中**。

- **WebUI 体验增强**:
    - **即写即存草稿 (#5910)**: 用户在切换对话时保留输入框草稿。这是一个非常合理且提升体验的功能，很有可能实现。
    - **消息队列/等待室 (#5909)**: 允许在 Agent 忙碌时排队发送消息。这是个复杂但用户呼声很高的功能，可能会进入更长期的路线图。
    - **实时 Token 速率显示 (#5908)**: 在流式回复时显示 tokens/s。这是一个“锦上添花”的增强，对调试和用户体验都有好处。

- **渠道与通知优化**:
    - **Telegram 话题重命名 (#5902)**: **已有对应 PR [#5902](https://github.com/HKUDS/nanobot/pull/5902) 正在处理中**，并根据生成的对话标题自动重命名 Telegram 论坛话题。
    - **静默上下文压缩 (#5900)**: 用户希望压缩操作在后台静默完成，不再向渠道发送通知。**已有对应 PR [#5780](https://github.com/HKUDS/nanobot/pull/5780) 正在处理中**，旨在默认禁止自动压缩通知。

### 用户反馈摘要

从今日的 Issues 评论中，可以提炼出以下用户反馈要点：

- **WebUI 本地化用户**: “终于成功了！现在整个界面看起来都协调了。” (对 #5367 合并的积极反馈)
- **Telegram 代码高亮用户**: “反引号代码块可以正常显示了，但波浪线代码块还是会被错误渲染。这个 PR (#5911) 解决了我的大麻烦。” (持续关注代码渲染的一致性)
- **遇到压缩死锁用户**: “这是我遇到最严重的问题，一个会话进行到一半就彻底卡死了，因为它无法压缩自己。” (对 #5849 的担忧)
- **升级受挫用户**: “我理解安全考虑，但强制要求移动目录对我的两个实例部署很不友好。希望有更平滑的升级指南。” (对 #5881 的不满与理解)
- **静默压缩请求者**: “压缩是好事，但每次都发一条‘我正在压缩’的消息给我，真的很烦人。” (对 #5900 的期待)

### 待处理积压

以下 Issue 或 PR 持续未合并，提醒维护者关注：

- **持续性目标循环修复 (PR #5257)**: 该 PR 旨在解决因自动触发“继续”指令导致的无限回复循环问题。尽管已存在多日（8月5日创建），但尚未合并，是影响自主 Agent 可用性的关键修复。**强烈建议尽快审阅合并**。
- **工作区内运行时文件处理 (PR #5260)**: 解决因 `_nanobot` 目录位于 workspace 内导致内存读取异常的问题。这与已关闭的 Issue #5881 高度相关，但采用了不同的解决方案。如需确定最终方案，建议审阅并与用户沟通。
- **XAI Grok/OpenAI Codex 的 SSE 推理事件处理 (PR #5834)**: 修复了 `consume_sse_with_reasoning` 函数忽略 `reasoning_text` 事件的问题。虽然持续时间不长，但这是一个重要的 Bug 修复，建议在下一个版本周期内合并。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是根据您提供的 Hermes Agent 项目 2026年9月25日数据生成的日报。

---

# Hermes Agent 项目动态日报 (2026-09-25)

## 1. 今日速览

今日，Hermes Agent 项目展现出极高的社区活跃度和强大的问题处理能力。过去 24 小时内，项目收到了 50 条 Issue 更新，其中 14 条为新开或活跃 Issue，36 条已被关闭，显示出维护团队对用户反馈的积极响应。尽管 Pull Request (PR) 积压量较大（48 条待合并），但大量修复和优化工作正在同步进行。项目发布了补丁版本 v0.21.5，旨在提升下游用户的稳定性。整体来看，项目正处于功能快速迭代与稳定性加固并重的阶段，社区健康度良好，但 PR 审查和合并速度需提升以匹配活跃的开发势头。

## 2. 版本发布

**Hermes Agent v0.21.5 (v2026.9.24)**
- **发布日期:** 2026年9月24日
- **发布类型:** 补丁版本 (Patch)
- **更新内容:**
    - 此版本是将自 v0.21.4 以来合并的约 460 个 PR 整合打包成一个稳定的标记版本。
    - 面向下游消费者（如 Docker 镜像、Hermes Cloud 和托管部署）提供更稳定的基础。
- **破坏性变更 (Breaking Changes):** 无声明。
- **迁移注意事项:**
    - 这是一个稳定版本的打包，直接升级即可。
    - 官方建议回顾在此版本窗口期间发布的相关变更日志或 PR，以了解具体改动。

## 3. 项目进展

尽管今日合并/关闭的 PR 数量不多(2条)，但专家分析待合并的 48 个 PR 后发现，项目在多个关键领域取得了实质性的功能增强和稳定性修复，预计将在未来几天内被合并。

- **桌面端修复 (Deskop):**
    - **配置文件记录缓存隔离:** 修复了切换网关后，配置保存会错误覆盖前一个设备记录的 Bug ([PR #121416](https://github.com/NousResearch/hermes-agent/pull/121416))。
    - **Wayland 原生支持:** 改进了 Linux 上原生 Wayland 会话的桌面端显示，不再依赖 XWayland ([PR #121377](https://github.com/NousResearch/hermes-agent/pull/121377))。
    - **远程后端心跳支持:** 修复了 Windows 桌面版连接远程后端时，`/heartbeat` 和循环无法正常工作的重复问题 ([Issue #109858](https://github.com/NousResearch/hermes-agent/issues/109858))。
- **网关与核心 (Gateway/Core):**
    - **主机网关环境隔离:** 确保从特定 profile 启动的网关进程不会篡改主机网关的环境变量，防止配置串扰 ([PR #121478](https://github.com/NousResearch/hermes-agent/pull/121478))。
    - **安装流程优化:** 优化了 `HERMES_DESKTOP_IGNORE_EXISTING` 标志的处理逻辑，避免了忽略现有运行时后仍尝试安装的重复操作 ([PR #121443](https://github.com/NousResearch/hermes-agent/pull/121443))。
- **AI 模型 (Models):**
    - **模型选择过滤:** 修复了聊天目录和模型选择器会提供图片/视频生成模型的问题，确保只有聊天模型可供选择 ([PR #121442](https://github.com/NousResearch/hermes-agent/pull/121442))。
- **安全 (Security):**
    - **秘密日志清除:** 上线了一个修复 PR，当 `reasoning` 字段的内容为空但长度停止时，将触发清除逻辑，防止敏感推理过程泄露 ([PR #121566](https://github.com/NousResearch/hermes-agent/pull/121566))。

## 4. 社区热点

今日社区讨论的核心集中在桌面端的用户体验和跨平台兼容性上，尤其是 Windows 平台的稳定性和 Bot 模式功能的完善。

1.  **[Issue #92760](https://github.com/NousResearch/hermes-agent/issues/92760) - Bot Mode 群组回复缓慢与桌面 UI 打磨 (已关闭)**
    - **热度：** 7 条评论
    - **核心诉求：** 用户反馈 Bot Mode 下，群聊机器人回复极慢且偶尔会完全停止响应。根本原因在于回复机制是基于轮询（poll-driven）而非推送（push-driven）。此 Issue 已被关闭，预计相关修复已包含在 v0.21.5 版本中。

2.  **[Issue #57812](https://github.com/NousResearch/hermes-agent/issues/57812) - macOS 无法通过局域网连接远程 LLM (开放中)**
    - **热度：** 6 条评论
    - **核心诉求：** 这是一个长期存在的问题（自 7 月起）。用户报告在 macOS 上，Hermes Agent 无法连接到同一局域网的远程 LLM，但系统 Python 环境却可以。这可能指向 Hermes 内部网络环境隔离或证书验证问题，是用户跨设备部署的一大障碍。

3.  **[Issue #89697](https://github.com/NousResearch/hermes-agent/issues/89697) - 桌面端选择 profile 后侧边栏不切换 (已关闭)**
    - **热度：** 4 条评论
    - **核心诉求：** 用户在多 profile 设置中，点击切换 profile 后，其后端虽已启动，但侧边栏仍显示之前 profile 的会话。问题出在 `$activeGatewayProfile` 状态未更新，导致会话列表未刷新。此问题已关闭，表明已修复。

## 5. Bug 与稳定性

今日报告的 Bug 主要集中在 Desktop 应用和 Windows 平台，以下为严重程度排序：

| 严重程度 | Issue / Bug 描述 | 影响范围 | 是否有 Fix PR |
| :--- | :--- | :--- | :--- |
| **P0 紧急** | **[Desktop] 会话记录完全冻结** ([#76030](https://github.com/NousResearch/hermes-agent/issues/76030)) | 桌面端用户 (已关闭) | 已关闭，推测已在 v0.21.5 中修复 |
| **P2 高** | **[Windows] `hermes update` 破坏本地提交和聊天** ([#63577](https://github.com/NousResearch/hermes-agent/issues/63577)) | Windows用户 (已关闭) | 已关闭，推测已修复 |
| **P2 高** | **[Windows] 桌面端心跳和循环功能对远程后端无效** ([#109858](https://github.com/NousResearch/hermes-agent/issues/109858)) | Windows + 远程后端 | 已关闭 (作为重复) |
| **P2 高** | **[macOS/Desktop] 桌面端无法连接至 `hermes serve` 的后端** ([#85605](https://github.com/NousResearch/hermes-agent/issues/85605)) | macOS 用户 (已关闭) | 已关闭，推测已修复 |
| **P2 高** | **[Docker] 镜像缺少 `google-cloud-pubsub` 库** ([#91437](https://github.com/NousResearch/hermes-agent/issues/91437)) | Docker 用户 (已关闭) | 已关闭，推测已修复 |
| **P2 中** | **[macOS] 无法连接局域网内远程 LLM** ([#57812](https://github.com/NousResearch/hermes-agent/issues/57812)) | macOS 用户 (开放中) | **无** |
| **P3 低** | **[Desktop] 打开丢失的本地文件提示无应用打开** ([#122027](https://github.com/NousResearch/hermes-agent/issues/122027)) | 桌面端用户 (开放中) | **无** |

**专家研判：** 今日关闭的 Bug 数量众多，且涵盖了多项 P0/P1 级别的重大问题，这表明开发团队正在集中精力解决影响核心体验的顽疾。但是，`#57812` 这个开放了两个多月的问题依然存在，可能涉及较深的网络架构或平台差异，值得继续关注。

## 6. 功能请求与路线图信号

今日最显著的功能请求信号来自大量待合并的 PR，它们很可能被纳入即将到来的 v0.22 版本中：

1.  **Hermes Cloud 系统浏览器登录:** `[PR #121204](https://github.com/NousResearch/hermes-agent/pull/121204)` 正在推进桌面端通过系统浏览器进行 OAuth 2.0 登录，这是提升用户体验和安全性的重要一步，很可能纳入近期里程碑。
2.  **Kanban 事件流优化:** `[PR #121412](https://github.com/NousResearch/hermes-agent/pull/121412)` 旨在优化看板（kanban）功能的后端事件流，从“全量拉取”改为“尾端增量推送”，这将显著提升大型看板的加载速度。这表明项目在持续优化已有功能性能。
3.  **Windows ARM64 原生浏览器二进制支持:** `[PR #121470](https://github.com/NousResearch/hermes-agent/pull/121470)` 尝试解决 Windows ARM64 设备上的浏览器功能异常问题，体现了项目对新硬件架构的适配意愿。
4.  **多窗口同步并防止提交乱序:** `[PR #121531](https://github.com/NousResearch/hermes-agent/pull/121531)` 通过广播状态更新和拒绝过期提交，解决多窗口模式下会话状态不同步的问题，这是一个提升高级用户协作体验的重要举措。

## 7. 用户反馈摘要

- **#92760 (Bot Mode)** 的用户描述了非常具体的场景：“**Bot Mode 群聊中，机器人回复慢得要命，而且经常没声音了**”。他们准确地找到了根因是“拉取模式”而非“推送模式”，显示了社区用户具有相当高的专业水平。
- **#63577 (Windows 更新)** 的用户对更新流程体验极差，批评道：“**`hermes update` 在 Windows 上有四个严重缺陷**”，包括拒绝启动、杀死活跃会话和破坏本地代码。这反映了 Windows 平台用户对更新流程稳定性的强烈不满。
- **#82383 (Windows 安装器失败)** 的反馈获得 2 个👍，用户幽默地表述为“**Hermes-Setup.exe 失败了，因为它自带的 npm 版本不被仓库认可**”，这指出了构建流程中一个低级但影响重大的依赖版本错误。
- **#82169 (macOS 更新死锁)** 的用户形容更新过程“**经常是不可能的**”，因为多个更新入口会互相争夺锁，导致更新过程极不稳定。这反映出更新机制在多入口场景下的设计缺陷。

## 8. 待处理积压

以下问题已存在较长时间且尚未解决，提醒维护者关注：

1.  **[Issue #57812](https://github.com/NousResearch/hermes-agent/issues/57812) - macOS 局域网连接远程 LLM 失败 (已开放 84天)**
    - **状态：** 开放中，社区已经讨论了两个多月。
    - **潜在影响：** 严重限制了用户使用 Hermes 在本地网络部署 LLM 的能力，对希望私有化部署的用户是重大障碍。修复此问题可能会提升项目的“开发者体验”口碑。
2.  **[Issue #115104](https://github.com/NousResearch/hermes-agent/issues/115104) - 内存提供者同步绕过密码审查 (已开放 7天)**
    - **状态：** 开放中，已被标记为安全类型（`type/security`）。
    - **潜在影响：** 这是一个严重的安全问题，意味着用户的 API 密钥、密码等敏感信息在通过外部内存提供者同步时，会以明文形式存储。此问题应被提升至最高优先级处理。
3.  **大量待合并 PR (48条)**
    - **状态：** 超过 95% 的 PR 仍在等待合并。
    - **潜在影响：** 社区提交了大量修复和新功能（包括上述用户反馈的痛点），如果这些工作不能及时合并，会打击贡献者的积极性，并导致用户在后续版本中才体验到关键的稳定性修复。

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是基于提供数据生成的 PicoClaw 项目动态日报。

---

### PicoClaw 项目动态日报 | 2026-09-25

**日报生成时间:** 2026-09-25 00:00 UTC

#### 1. 今日速览

今日 PicoClaw 项目整体 **活跃度较高**，主要体现在 Pull Request (PR) 提交密集，尤其是由 Dependabot 发起的多项依赖更新 PR，表明项目维护者正积极进行技术栈的现代化与安全性升级。然而，**项目进展呈现“提交活跃、合并停滞”的状态**：过去 24 小时内虽有 8 个 PR 待合并，但无任何 PR 被成功合并或关闭，也未发布新版本。同时，一个关于多行输入被拆分的问题被重复报告（Issues #3390/#3391），虽其中一个已被仓促关闭，但核心 Bug 尚未被修复，这可能会影响用户在移动端的使用体验。

#### 2. 版本发布

无新版本发布。

#### 3. 项目进展

今日无任何 Pull Request (PR) 被合并或关闭。尽管如此，以下处于待合并状态的 PR 代表了项目近期的关键发展方向，值得关注：

- **功能与集成**:
    - **PR #3381 - 切换 OpenAI 至 Responses API**: 作者 `XenonR` 提议将 OpenAI 提供商切换至最新的 Responses API。这是一个重大的非破坏性功能更新，若合并，将确保 PicoClaw 对 OpenAI 最新模型和功能的兼容性。
    - **PR #3376 - 修复 DeltaChat 配置错误**: 作者 `luisgdev` 提供了一个关键修复，通过将 DeltaChat 初始化为自定义通道来解决其启动时的配置验证错误。
    - **PR #3371 - 新增 OpenCode Go 提供商**: 作者 `EMTumariscal` 提交了新功能，增加了对 `opencode.ai` 平台的支持，丰富了 PicoClaw 的模型生态。

- **依赖与基础设施**:
    - **Dependabot 批量更新**: 共有 5 个来自 Dependabot 的依赖更新 PR（#3385 至 #3389），涉及 `mautrix` (Matrix协议库)、`line-bot-sdk-go`、`anthropic-sdk-go`、`go-sdk` (MCP协议) 和 `golang.org/x/crypto`。这些更新对于提升项目的 **稳定性、安全性以及对第三方服务的新特性支持** 至关重要。

**结论**: 项目虽未有合并事件，但多项功能性 PR 和批量依赖更新堆叠，显示项目正处于一个 **待合并的功能发布窗口期**。一旦合并，将带来显著的平台扩展和安全更新。

#### 4. 社区热点

今日社区讨论热度整体不高，但出现了值得关注的重复报告情况。

- **热点 Bug 报告**: **Issues #3390** 和 **#3391** 描述了完全相同的 Bug：在 Pico 客户端（移动 TUI）中，粘贴多行文本（如诗歌、代码块）会被自动分割成多条消息发送。
    - **现象**: 用户 `chentianxiong123` 似乎提交了两次完全相同的报告，其中 #3390 在其提交后立即被关闭（可能是误操作或重复标记），而 #3391 仍处于开放状态。
    - **分析与诉求**: 该行为严重破坏了用户预期的消息结构，尤其对于需要保持格式完整性的场景（如分享代码、诗歌、配置文件）造成极大困扰。社区的诉求是 **修复消息输入的底层解析逻辑**，使其能正确处理换行符。

#### 5. Bug 与稳定性

**严重程度: 高**

- **描述**: **Pico 客户端多行输入错误分割** (Issues #3390/#3391)
- **摘要**: 在移动端 TUI 中，多行文本粘贴时，文本被换行符分割成多条独立消息发送。
- **影响**: 影响核心聊天功能在移动端的可用性和数据完整性。
- **状态**: **未修复**。虽 #3390 被关闭，但 #3391 仍为开放状态。目前尚无关联的 Fix PR。
- **链接**: [Issue #3391](https://github.com/sipeed/picoclaw/issues/3391)

#### 6. 功能请求与路线图信号

今日未发现用户提出的新功能请求。项目的功能发展方向主要来自 **待合并的 PR**：

- **扩展模型生态**: `opencode-go` (PR #3371) 和 `Responses API` (PR #3381) 的接入，强烈暗示项目正在向 **去中心化、多模型架构** 演进，路线图可能包含对更多非 OpenAI 标准模型的支持。
- **平台兼容性修复**: `DeltaChat` 配置错误的修复 (PR #3376) 表明项目正在积极扩展和稳定其 **去中心化通信渠道** 的支持。

#### 7. 用户反馈摘要

- **核心痛点**: 用户对 **移动端 TUI 的输入体验** 提出了明确的批评。多行文本自动分拆是一个设计上的缺陷，它破坏了用户在移动设备上进行复杂文本输入（如粘贴代码）的流程，这显然是严重影响用户满意度的功能问题。
- **使用场景**: 用户可能在移动端进行 **代码或格式化文本的快速分享**、**使用聊天界面作为笔记工具** 等。当前的 Bug 使得这些场景无法正常工作。

#### 8. 待处理积压

以下 PR 标签为 `[stale]`，表明它们已数日未获得有效进展或评论，需要维护者关注：

- **PR #3381 - 切换到 OpenAI Responses API** (创建: 2026-09-17): 架构级的重要更新，长期搁置可能落后于上游 API 变更。
- **PR #3376 - 修复 DeltaChat 配置错误** (创建: 2026-09-10): 修复一个阻止特定频道启动的 Bug，影响该功能的用户基础。
- **PR #3371 - 新增 OpenCode Go 提供商** (创建: 2026-09-08): 增加新模型接入点，长期未合并会打击贡献者积极性。
- **链接**: [PR #3381](https://github.com/sipeed/picoclaw/pull/3381), [PR #3376](https://github.com/sipeed/picoclaw/pull/3376), [PR #3371](https://github.com/sipeed/picoclaw/pull/3371)

此外，**重复的 Bug 报告 (#3390 与 #3391)** 也需要维护者处理，以保持 Issue 列表的清晰并正式确认该 Bug 的存在。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域的开源项目分析师，以下是根据您提供的 NanoClaw 项目数据生成的 2026-09-25 项目动态日报。

---

## NanoClaw 项目动态日报 | 2026-09-25

### 1. 今日速览

今日项目活跃度非常高，尤其是在 Bug 修复和代码库维护方面。过去 24 小时内，虽然无新版本发布，但处理了高达 13 个 PR，其中 3 个已合并，显示了核心团队对近期反馈（特别是围绕 `Iron Proxy` 和 `Setup` 流程）的快速响应。社区提出的两个新 Issues 均围绕 `Iron Proxy` 功能，揭示了该功能在多架构支持和安全策略灵活性上的不足，并已触发相关的修复 PR。项目整体健康度良好，正处于一次集中的“Bug 清理与稳定性提升”冲刺阶段。

### 3. 项目进展

今日有 **3 个 PR** 被合并或关闭，主要集中在 CLI 工具完善和 Agent 交互体验优化：

- **`#3882` [CLOSED]** **[CLI, Core]** `fix(cli): list every approval status and drop reason the host writes`
  修复了 `ncl approvals help` 和 `ncl dropped-messages help` 命令的帮助信息，使其能完整列出所有审批状态和丢弃原因，确保开发者能准确理解系统的行为逻辑。
  [PR #3882](nanocoai/nanoclaw PR #3882)

- **`#3885` [CLOSED]** **[Setup, Core]** `fix(setup): keep the Claude CLI offer to runs that chose Claude`
  解决了安装流程中的一个逻辑缺陷。此前，如果在选择 Agent 运行时之前安装失败，系统会错误地提示用户安装 Claude CLI。现在，系统仅在用户已选择 Claude 作为运行时后才提供此选项，避免了不必要的引导。
  [PR #3885](nanocoai/nanoclaw PR #3885)

- **`#3890` [CLOSED]** **[Agent Runner]** `feat(agent-runner): explain inbound message blocks in the chat system prompt`
  这是一个用户体验的小改进。当向 Claude 发送聊天消息时，系统现在会在提示词中解释 `<message>`、`<dm-history>` 等不同信息块的含义，帮助 AI 更好地理解多轮对话的上下文结构。
  [PR #3890](nanocoai/nanoclaw PR #3890)

### 4. 社区热点

今日最受关注的议题无疑是 **`Iron Proxy`** 的相关功能，所有社区互动（Issues & PRs）都围绕此主题展开。

- **`#3888` [OPEN]** **Iron Proxy 在 ARM64 主机上安装失败。**
  这是一个由用户 `glifocat` 报告的实际使用问题。问题明确指出，`ironsh/iron-control` 镜像仅支持 `amd64`，导致在如 NVIDIA DGX Spark 等 ARM64 设备上部署失败。此 Issue 背后是用户对**跨平台兼容性**的强烈诉求。
  [Issue #3888](nanocoai/nanoclaw Issue #3888)

- **`#3881` [OPEN]** **请求：为 Iron Proxy 添加逐主机自动审批规则。**
  用户希望在 Iron Proxy 网关上实现更灵活的自动审批，让工具技能可以无需每次请求都弹出人工审批卡片，就能调用预先批准的主机。这反映了用户对**智能代理工作流效率**和**减少不必要人工干预**的需求。
  [Issue #3881](nanocoai/nanoclaw Issue #3881)

核心贡献者 `glifocat` 不仅报告了问题，还快速提交了对应的修复 PR (`#3891`)，展现了社区的自愈能力和极高的响应效率。

### 5. Bug 与稳定性

今日报告的 Bug 均已有对应的修复 PR，但尚未全部合并，需要重点关注：

| 严重程度 | Bug 描述 | 相关 Issue | 相关 Fix PR |
| :--- | :--- | :--- | :--- |
| **严重** | **`Iron Proxy` 在 ARM64 主机上安装失败**，容器因架构错误而崩溃，导致整个功能无法在非 x86 平台上使用。 | [Issue #3888](nanocoai/nanoclaw Issue #3888) | [PR #3891](nanocoai/nanoclaw PR #3891) |
| **中等** | **长期输出块导致心跳超时**：当 Claude 流式传输一个较长的内容块时，Agent 容器的心跳信号未能及时更新，可能会被宿主进程错误地杀死。 | (隐含于 PR #3893) | [PR #3893](nanocoai/nanoclaw PR #3893) |
| **低** | **`Iron Proxy` 重新安装失败**：当卸载或失败后，残留的 `Docker` 卷和容器未能被清理，导致无法重新安装。 | (隐含于 PR #3883) | [PR #3883](nanocoai/nanoclaw PR #3883) |
| **低** | **安装流程提示错误**：在某些失败场景下，系统错误地建议安装 `Claude CLI`，干扰了用户操作。 | (隐含于 PR #3884) | [PR #3884](nanocoai/nanoclaw PR #3884) |

此外，还有 2 个关于**测试稳定性（Timing Flakes）** 的 Bug 修复 PR (`#3892`, `#3887`)，这体现了项目对 CI 可靠性的持续改进。

### 6. 功能请求与路线图信号

- **`#3881` (Iron Proxy 自动审批规则)**：这是一个明确的功能请求，来自活跃用户。虽然尚未合并，但考虑到 `Iron Proxy` 是当前的核心功能且备受关注，此功能很可能被纳入下一个版本的小迭代中。
- **`#3890` (解释 Chat 消息块)**：此功能已在今日合并，表明项目团队正在持续优化 Agent 的交互质量，属于短期内已实现的路线图信号。
- **WhatsApp 多 Agent 身份标识 (`#3509`, `#3510`)**：虽然这些 PR 已存在超过一个月，但最近被更新，表明项目团队未放弃对特定通道（如 WhatsApp）的深度功能开发，未来可能将 “多 Agent 共享频道” 支持提升优先级。

### 7. 用户反馈摘要

从今日的 Issues 和 PR 评论中，可以提炼出以下真实用户痛点：

- **硬件兼容性是第一大痛点**：用户 `glifocat` 明确表示在 **NVIDIA DGX Spark (ARM64)** 上无法使用 `Iron Proxy` 功能，这直接阻断了一批使用非 x86 硬件（如 Apple Silicon Mac 或 ARM 云服务器）的用户。
- **工作流效率瓶颈**：用户对 `Iron Proxy` 的“每次请求都弹出审批卡片”机制感到不满，认为这严重拖慢了自动化工作的效率。这暗示用户更倾向于“设置好后就不再被打扰”的零信任或基于规则的自动化模式。
- **对 CLI 工具的准确性要求较高**：修复 `ncl` 帮助信息 (`#3882`) 的背后，是用户期望命令行工具能准确反映系统状态的诉求，不准确的信息会带来调试和使用的困惑。

### 8. 待处理积压

以下为长时间未合并或更新的 PR，提醒维护者关注：

- **`#3510` [OPEN] **[Channels]** `whatsapp: per-agent sender label in shared mode`**，创建于近一个月前。这是实现 WhatsApp 多 Agent 协作的关键 PR，至今未合并，可能因涉及与 `#3509` 的联调问题而阻塞。
  [PR #3510](nanocoai/nanoclaw PR #3510)

- **`#3509` [OPEN] **[Core, Channels]** `delivery: pass the sending agent's label to channel adapters`**，也创建于近一个月前。作为 `#3510` 的前置 PR，它同样处于停滞状态。项目团队可能需要评估并加速这两个 PR 的合并，以便在 WhatsApp 等渠道上提供更丰富的多 Agent 协作能力。
  [PR #3509](nanocoai/nanoclaw PR #3509)

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我将根据您提供的 NullClaw 项目数据，生成一份结构清晰、数据驱动的 2026-09-25 项目动态日报。

---

## NullClaw 项目动态日报 | 2026-09-25

### 1. 今日速览

过去24小时内，NullClaw 项目在稳定性修复和文档完善方面取得了实质性进展。社区活跃度较高，共处理了12条 Issue 和25条 PR，其中8个 PR 已被合并或关闭，显示项目维护者正在积极清理积压。值得关注的是，一批由社区贡献者（如 `vernonstinebaker`）发起的、针对关键 Bug（如内存召回、CLI 输出损坏）的修复 PR 与功能增强（如技能符号链接支持）在同一天密集提交，表明项目正在进入一个快速迭代和修补的周期。尽管没有新版本发布，但整体项目健康度良好。

### 2. 版本发布

今日无新版本发布。

### 3. 项目进展

今日项目向前迈出了重要一步，主要集中在**核心稳定性修复**和**文档体系完善**上。以下为今日合并/关闭的重要 PR，它们共同提升了项目的健壮性和可维护性：

- **核心Bug修复**：
    - **PR #996** `fix(mcp): bound stdio response waits` **已合并**。这是一个关键的稳定性修复，解决了 Issue #991 中描述的 MCP stdio 调用可能无限期挂起的问题，现在对超时进行了限制并清理了子进程。
    - **PR #991** `MCP stdio calls can hang indefinitely behind the Proxmox launcher lock` **已关闭**。该问题的修复方案已被合并。
    - **PR #986** `GEN-548: make SQLite memory database path configurable` **已合并**。此功能使 SQLite 数据库路径可配置，增加了部署的灵活性，尤其是对只读工作区场景。

- **关键功能恢复**：
    - **PR #1002** `discord: run typing thread on the heavy runtime stack` **已合并**。此 PR 从 PR #978 中提取了关键的栈溢出修复，解决了 Discord 网关因线程栈过小（512KB）而在执行 TLS 操作时崩溃的问题，现在将其提升至 2 MiB。这是一个直接影响生产稳定性的修复。
    - **PR #1001** `feat(memory): add configurable auto-recall, recall_limit, max_context_bytes` **已合并**。此 PR 恢复了 PR #979 中引入的内存召回控制功能，为用户提供了更精细的管理模型上下文和行为的选项。

- **用户体验与文档改进**：
    - **PR #1004** `fix(providers): log scrubbed provider error bodies on non-2xx` **已合并**。此修复解决了无输出问题，现在当调用 API 失败时，会记录提供商返回的错误信息（但会隐去敏感凭证），极大地改善了调试体验。
    - **PR #1003** `feat(skills): follow symlinked skill directories` **已合并**。此功能直接响应了 Issue #995 的请求，现在 `nullclaw skills list` 可以识别并跟随符号链接，方便用户管理技能目录。
    - **PR #1008** `docs: repair the index and add subsystem guides` **已合并**。修复了文档索引的渲染问题，并新增了关于 MCP、子代理等子系统的中文和英文文档，显著降低了新用户的入门门槛。
    - **PR #1007** `docs: explain the diagnostics logging flags` **已合并**。文档现在清晰地解释了诊断日志的各种标志，有助于用户进行故障排查。

### 4. 社区热点

今日社区最活跃的讨论集中在 **Issue #1000** 和 **Issue #991**。

- **[Issue #1000] [enhancement] ollama incompatibility notification** (评论: 3，状态: OPEN)
    - **链接**: [Issue #1000](https://github.com/nullclaw/nullclaw/issues/1000)
    - **诉求分析**: 用户 `aaafgcfg` 提出当 Ollama 模型不支持工具调用（tool）时，NullClaw 只显示一个模糊的“adapter error”，缺乏有意义的错误信息，迫使用户使用 Wireshark 抓包才能定位问题。这反映了**社区对更友好、更清晰的错误处理和诊断信息的强烈需求**，尤其是在集成第三方服务时。

- **[Issue #991] MCP stdio calls can hang indefinitely behind the Proxmox launcher lock** (评论: 3，状态: CLOSED)
    - **链接**: [Issue #991](https://github.com/nullclaw/nullclaw/issues/991)
    - **诉求分析**: 用户在 Proxmox 环境下运行时遇到 MCP stdio 调用无限期挂起，这是一个严重的中断服务的问题。该问题获得了社区关注，并迅速在 PR #996 中得到修复并关闭。这显示社区**对生产环境下的稳定性和资源竞争问题非常敏感**，而项目维护者的快速响应也赢得了社区的信任。

### 5. Bug 与稳定性

今日报告的 Bug 均已有相应的修复 PR，显示了项目良好的响应速度。

- **严重**:
    1.  **[CLOSED] MCP stdio 无限期挂起** (Issue #991) - 已由 PR #996 修复。
    2.  **[CLOSED] 内存归档召回问题** (PR #1005) - 修复了归档会话被错误地召回，导致模型将当前消息误认为是历史记录的 Bug。这是模型行为正确性的关键修复。
    3.  **[CLOSED] CLI 流式输出损坏** (PR #1006) - 修复了在 macOS 系统上流式输出时，由于错误使用 `pwrite` 导致输出内容被截断或损坏的 Bug。

- **一般**:
    1.  **[OPEN] Ollama 不兼容通知不清晰** (Issue #1000) - 不是崩溃，但会导致严重的调试体验问题。暂无关联的修复 PR，但已有类似方向的 PR #1004 改善了提供商的错误日志。

### 6. 功能请求与路线图信号

今日用户提出的新功能需求，结合已有的 PR，显示了项目未来的发展方向：

-  **Ollama 兼容性**: 社区希望 NullClaw 能主动检测并通知用户 Ollama 模型是否支持工具调用 (Issue #1000)。这与 PR #1004 的方向一致，后者旨在更好地暴露后端 API 的错误。
-  **技能管理灵活性**: 支持技能目录的符号链接 (Issue #995) 已被 PR #1003 实现，这是一个快速响应用户需求并已合并的正面案例。
-  **配置易用性**： 用户希望提供一个更完善的示例配置文件 (Issue #867)。这直接指向了项目对新用户的不友好痛点，预计后续会持续改善文档和默认配置。
-  **运行时透明性**: 用户希望观察到 AI 的“思考/推理”过程 (Issue #886)，以避免任务卡住时无从知晓。这是一个常见的用户需求，虽然今日没有直接的 PR，但它将被视为提升用户体验的重要信号。

### 7. 用户反馈摘要

从今日的 Issues 和 PR 评论中可以提炼出以下用户声音：

- **痛点**:
    - **调试困难**: 用户强烈抱怨当模型或 API 配置不正确时，错误信息过于模糊（如“adapter error”），导致不得不进行网络抓包（使用 Wireshark）才能定位问题 (Issue #1000)。
    - **配置门槛高**: 默认配置文件“残缺不全”，导致用户难以让项目运行起来，这表明**入门体验是当前用户满意度的主要瓶颈** (Issue #867)。
    - **运行时黑盒**: AI 在长时间任务（如阅读邮件）中没有反馈，用户无法知道是卡住了还是在工作 (Issue #886)。

- **场景**:
    - **低资源设备部署**: Issue #871 的讨论反映了用户对在树莓派、弱终端等低资源设备上运行 NullClaw 的兴趣，但这与当前依赖外部 API 的网络搜索功能相矛盾。
    - **Telegram/Discord 网关**: 多个 Bug 修复（#976, #978）和讨论都围绕于将 NullClaw 作为 Telegram/Discord 机器人网关运行，这是项目最主要的应用场景之一。

- **满意度**: 社区对 Bug 的修复和功能请求的响应速度感到满意，例如 Issue #991 和 #995 均在短时间内被解决。

### 8. 待处理积压

以下为开放时间较长或对项目健康至关重要，需引起维护者关注的待处理项：

1.  **[PR #966] fix(http): secure buffered curl fallback on Android**
    - **链接**: [PR #966](https://github.com/nullclaw/nullclaw/pull/966)
    - **关注点**: 此 PR 旨在修复 Android (Termux) 平台的网络连接问题。该 PR 已开放超过3个月，至今未被合并或关闭。由于 Android 是一个重要的移动端平台，这个积压问题可能影响该平台用户的体验，建议尽快审议。

2.  **[PR #983] fix(providers): use pinned curl path for proxied requests**
    - **链接**: [PR #983](https://github.com/nullclaw/nullclaw/pull/983)
    - **关注点**: 此 PR 旨在通过 curl 路由代理请求，解决特定网络下的稳定性问题。该 PR 也开放了较长时间 (53天)，建议评估其与 PR #966 的优先级。

3.  **[PR #777] docs: structural cleanup** & **[PR #776] docs: add MCP, subagents, skills, voice, and hardware documentation**
    - **链接**: [PR #777](https://github.com/nullclaw/nullclaw/pull/777), [PR #776](https://github.com/nullclaw/nullclaw/pull/776)
    - **关注点**: 这两个文档 PR 由 `telagod` 提交，已经开放了5个多月。虽然今日已有新文档（PR #1008）被合并，但这些更早的 PR 可能包含了已经被覆盖或需要协调的内容。建议维护者审视这两个积压的 PR，确认其内容是否仍有价值，或是否应被关闭以避免混淆。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我将根据您提供的 IronClaw 项目数据，生成一份结构化的项目动态日报。

---

## IronClaw 项目日报 — 2026-09-25

### 1. 今日速览

过去24小时内，IronClaw 项目活动量处于中等偏低水平，主要集中于常规维护与问题追踪。核心亮点是发布了 `v1.4.1-rc.2` 候选版本，修复了 Google OAuth 客户端配置的关键问题。同时，社区通过每日失败分类 Issue 系统性地追踪模型质量退化，显示出项目对稳定性的重视。整体而言，项目进入了一个稳定的迭代期，开发节奏健康，但社区互动热度不高。

### 2. 版本发布

- **`ironclaw-v1.4.1-rc.2`** (1.4.1-rc.2) - **2026-09-24**
  - **发布说明**: 这是 `1.4.0` 版本基础上的第二个补丁候选版本，与 `RC1` 修复内容相同，旨在进一步验证稳定性。
  - **主要修复**: **Google 扩展程序 (Gmail, Google Calendar) 激活问题**。此前，如果部署环境通过 Web UI 而非环境变量提供 Google OAuth 客户端信息，相关扩展将无法激活。此版本已修复该问题，大幅简化了基于 UI 的部署配置流程。
  - **破坏性变更**: 无。
  - **迁移注意事项**: 对于使用环境变量配置 OAuth 的用户无影响。之前因该问题受阻的部署者，升级至此版本后应能正常使用 Google 扩展功能。

**链接**: [IronClaw Release v1.4.1-rc.2](https://github.com/nearai/ironclaw/releases/tag/ironclaw-v1.4.1-rc.2)

### 3. 项目进展

今日没有 PR 被合并或关闭。目前，唯一待处理的 PR #7988 是维护性的基础工作，而非功能推进。因此，项目截至今日暂无实质性功能向前迈进，主要进展体现在解决特定配置 Bug 的版本发布上。

### 4. 社区热点

今日社区讨论热度较低，这与 `v1.4.1-rc.2` 主要针对特定部署场景修复有关，未能引发广泛讨论。

- **Issues #8111**: 此 Issue 是自动化生成的每日故障分类报告，虽然评论和反应数为零，但其内容本身是社区热议的焦点。它系统性地分析了 `officeqa` 套件中38个未通过测试的案例，并明确指出这些失败均为 **模型（deepseek-v4-flash）自身质量缺陷**，而非 IronClaw 代码或基础设施问题。这反映了社区对于**模型能力边界**与**基准测试结果**之间关系的关注。

**链接**: [Issue #8111](https://github.com/nearai/ironclaw/issues/8111)

### 5. Bug 与稳定性

- **严重 Bug (已修复)**:
  - **问题描述**: Google 扩展程序 (Gmail, Google Calendar) 在特定部署配置下无法激活。
  - **影响范围**: 所有仅通过 Web UI 配置 Google OAuth 客户端的部署环境。
  - **当前状态**: 已在 `v1.4.1-rc.2` 中修复。
  - **链接**: [Release Notes](https://github.com/nearai/ironclaw/releases/tag/ironclaw-v1.4.1-rc.2)

- **模型质量稳定性问题 (正在追踪)**:
  - **问题描述**: `officeqa` 基准测试套件中，38个任务因使用 OCR 数字化文档，导致 `deepseek-v4-flash` 模型产生大量“非通过”结果。
  - **影响范围**: 特定的 OCR 场景下的基准测试成绩。
  - **当前状态**: 通过 Issue #8111 进行追踪和分析，确认是模型输入质量导致的失败，非代码 Bug。**暂无修复 PR**，因为这属于模型能力或数据预处理优化范畴。
  - **链接**: [Issue #8111](https://github.com/nearai/ironclaw/issues/8111)

### 6. 功能请求与路线图信号

今日没有新的功能请求 Issue。当前版本主要聚焦于修复稳定性 Bug。从过去发布的 `v1.4.0` 到现在的 `v1.4.1-rc.2`，项目重心是**提高核心扩展的部署兼容性和系统稳定性**。尚未看到明确信号指向下一版本的新功能规划。

### 7. 用户反馈摘要

今日无有效的用户反馈。唯一的 Issue #8111 为自动化报告，其中无用户评论。这表明当前版本的部署和体验较为平稳，或者用户尚未发现值得反馈的问题。

### 8. 待处理积压

- **PR #7988 [size: XS, risk: low, contributor: core] chore(agents): refresh codebase knowledge graph**
  - **状态**: `[OPEN]`，自 2026-08-29 创建，至今已超过三周。
  - **内容**: 此 PR 由 CI 机器人自动发起，用于刷新代码库知识图谱的快照。属于维护性任务，风险低。
  - **提醒**: 此 PR 长期未合并可能会使知识图谱与最新代码产生偏差，影响依赖其功能的准确性。建议维护者尽快审查并合并，以免造成信息滞后。

**链接**: [PR #7988](https://github.com/nearai/ironclaw/pull/7988)

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

好的，作为 LobsterAI 开源项目分析师，以下是基于您提供的数据生成的 2026-09-25 项目动态日报。

---

## **LobsterAI 项目日报 | 2026年9月25日**

### **1. 今日速览**

今日项目整体活跃度较高，维护工作密集，主要体现为大规模的 PR 合并与关闭。过去24小时内，项目合并/关闭了46个 PR，同时解决了16个历史 Issue，显示出强大的代码整合与问题清理能力。核心贡献者 `fisherdaddy` 贡献了数个高价值的修复 PR，重点解决了模型输出截断、工具调用异常以及 UI 布局一致性问题。尽管 Issue 与 PR 的“关闭/合并”数量很高，但新开启的讨论和需求提交较少，说明项目在当前阶段更多地处于消化历史债务、打磨稳定性的状态。

### **2. 版本发布**

*无*

### **3. 项目进展**

过去24小时内，项目在核心稳定性、UI/UX及生态兼容性方面取得了重要进展，合并/关闭了多个“跨模块”的PR。关键进展如下：

- **核心修复：模型输出截断与工具调用**：
    - **PR #2761**: 修复了因 `max_tokens` 默认值过低，导致GLM-5.3等模型输出被截断的问题。该问题源于模型目录未能扫描到预安装的第三方提供商插件。此修复对使用非主流模型提供商的用户至关重要。
    - **PR #2759**: 修复了 OpenAI 兼容接口的“格式错误的工具调用”问题。当模型返回包含非法字符的参数时，该修复能自动修补并允许内部重试，防止副作用操作被错误丢弃，显著提升了基于 Agent 任务的成功率。
- **UI/UX 重构**：
    - **PR #2762 / #2760**: 对应用主题和布局进行了重大调整，包括采用中性灰度色调、侧边栏与主内容区域边缘对齐、导航项目采用药丸形按钮，并优化了窗口大小自适应逻辑。这预示着一次视觉和交互上的全面升级。
- **功能前瞻**：
    - **PR #2758** (待合并): 引入了 `@alison-xx` 提交的“原生 OpenClaw 进度卡片”功能，允许在 Cowork 界面直观展示多步骤任务的进度状态，这将极大提升用户在执行复杂任务时的体验。

**结论**：项目在“代码质量维护”和“体验打磨”上投入了主要精力，同时也有针对未来功能（如任务进度可视化）的积累。

### **4. 社区热点**

今日社区讨论热度不高，大部分历史 Issue 被统一清理。从被清理的议题中，可以看出一些长期存在的用户关切点：

- **性能与稳定性问题**：
    - **Issue #2079**: “执行结果窗口滚动到顶端会假死”是一个可复现的 bug，影响用户日常操作，但已被标记为 stale 并关闭，**建议开发者确认是否为永久修复**。
    - **Issue #2230**: “同一个模型在 LobsterAI 比 CodeBuddy 慢很多”，耗时为后者10倍且消耗1000倍 Token。该问题指向了底层架构或 token 计数机制的严重差异，是当前性能优化的关键方向。

- **功能与设计建议**：
    - **Issue #2120**: 用户提出的多项针对性建议，包括预输入任务、延长单次运行时长和 UI 布局优化，说明了活跃用户在日常开发中对工作流连续性和界面效率的强需求。

### **5. Bug 与稳定性**

今日无新 Bug 报告，但项目集中关闭了历史遗留的多个严重 Bug，主要包括：

- **严重 Bug (已关闭)**:
    - **[性能] Issue #2079**: 窗口假死问题。[链接](https://github.com/netease-youdao/LobsterAI/issues/2079)
    - **[功能] Issue #2121**: Token 因重复输出浪费。[链接](https://github.com/netease-youdao/LobsterAI/issues/2121)
    - **[UI] Issue #1861**: 模型切换后图片附件状态不同步，该问题已有对应修复 PR ([PR #2373](https://github.com/netease-youdao/LobsterAI/pull/2373)) 被关闭，应已被修复。
    - **[系统] Issue #2214**: 数据备份功能导致主进程卡死。[链接](https://github.com/netease-youdao/LobsterAI/issues/2214)
    - **[安装] Issue #2215**: 安装失败问题。[链接](https://github.com/netease-youdao/LobsterAI/issues/2215)
- **严重安全漏洞 (已关闭)**:
    - 由 `YLChen-007` 报告的一系列安全问题（涉及本地文件读取、SSRF、令牌劫持、文件泄露等）在今天被集中关闭，表明这些安全漏洞在前期版本中已得到处理，但需确认是否已随发布版本修复。

**当前待修复 Bug**:
- **Issue #2385 (状态: OPEN)**: “对话框无法添加文件夹”，这是一个被标记为 stale 但仍处于开启状态的功能性缺陷，影响用户的操作便捷性。
    [链接](https://github.com/netease-youdao/LobsterAI/issues/2385)

### **6. 功能请求与路线图信号**

尽管今日新功能请求较少，但依然可以从活跃的 PR 中窥见项目的演进方向：

- **即将到来的功能**:
    - **任务可视化 (PR #2758)**: 在 Cowork 界面显示原生 OpenClaw 进度卡片。该 PR 处于**待合并**状态，意味着在下个版本中，复杂任务执行的透明度和可控性将大幅提升。
    - **新 API 网关集成 (PR #2504, 状态: OPEN)**: 新增 OrcaRouter 作为一级提供商。表明项目正在持续扩展模型生态和 API 选择范围，增强与不同网关的兼容性。
- **社区的远期构想**:
    - **Issue #2180 (已关闭)**: 一个大规模的“AI Collaborator”平台升级提案，涉及自然语言命令栏、跨模型编排等，虽为社区提议，但反映了用户对 LobsterAI 向更高阶协作平台演进的期待。
    - **Issue #2239 (已关闭)**: 用户提出的“编程工具 OpenClaw 化”趋势判断和深度联动建议，为项目在开发者生态中的定位提供了有价值的参考。

### **7. 用户反馈摘要**

从 Issues 评论中，我们提炼出以下真实用户痛点：

- **性能焦虑**：用户对 Token 消耗非常敏感。`nbjoe` 担心重复输出浪费 Token (`#2121`)，而 `woxinsj` 详细对比了同一模型在不同工具中的巨大性能差异 (`#2230`)，这暗示项目可能需要对 Token 计数机制和响应效率进行彻底审查。
- **工作流断裂感**：用户在 `#2120` 中表达了对“任务执行连续性”的渴望，希望在当前任务运行时能预输入下一条指令。这说明核心用户群体（开发者）期望 LobsterAI 不仅是对话助手，更是一个高效的任务编排与执行平台。
- **配置与操作不透明**：`AL-Mint` 在 `#2216` 中提到 Memory Search 的 embedding provider 被锁定，导致 API 配额用尽后功能不可用，指出了系统配置的僵化问题。

### **8. 待处理积压**

- **待合并的重要 PR**:
    - **PR #2758**: “显示原生 OpenClaw 进度卡片”。预计将对用户体验产生积极影响，应优先纳入下一版本。
    - **PR #2374**: “添加永久隐藏侧边栏广告条的设置”。该PR已被标记为 `stale`，若项目采纳，可解决用户关于 UI 广告的反馈。
    - **PR #2452**: “修复斜杠模型 ID 的提供商前缀丢失问题”。涉及模型 ID 解析的关键逻辑，影响使用特定模型（如 `deepseek-ai/DeepSeek-V4-Flash`）的用户。
- **长期未更新的开放 Issue**:
    - **Issue #1861**: “图片附件不随模型切换重新处理”。虽然可能已通过 `PR #2373` 修复，但 Issue 本身仍处于 `OPEN` 状态，建议开发者更新其状态或添加具体修复版本标签。

---

**总结**：LobsterAI 项目当前处于 **“高质量维护与功能打磨”** 的冲刺阶段。今日关闭/合并了大量历史问题，核心贡献者积极通过 PR 修复关键漏洞和提升 UI 一致性。项目健康度良好，但需警惕历史安全问题的版本发布确认。社区反馈聚焦于性能、工作流和透明度，这与当前 PR 的修复方向（如模型截断、进度卡片）高度吻合。

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

# CoPaw 项目动态日报 | 2026-09-25

## 今日速览  
过去24小时项目共处理31条Issue（新开/活跃18条，已关闭13条）和23条PR（待合并17条，已合并/关闭6条），无新版本发布。社区讨论热度集中在多租户Hub规划、模型兼容性以及Agent长期记忆问题。技术侧重点在于修复上下文压缩、Provider流稳定性和控制台界面回归缺陷。整体活跃度中等偏高，修复与功能推进并行，贡献者参与积极（含多位首次贡献者）。

## 项目进展  
今日合并/关闭了6个PR，部分重要内容如下：

- **[#7972](https://github.com/agentscope-ai/QwenPaw/pull/7972) – fix(console): default session list grouping to source**  
  控制台会话侧边栏默认分组模式从`date`改为`source`，解决v2.2.2b3侧边栏重设计导致的群组功能不可见问题。  
- **[#7971](https://github.com/agentscope-ai/QwenPaw/pull/7971) – fix(console): gate tool-call lifecycle queries on execution start**  
  修复控制台在模型生成参数完成后即轮询工具调用状态，导致过早请求的问题。  
- **[#7960](https://github.com/agentscope-ai/QwenPaw/pull/7960) – fix(providers): recover after stalled stream cleanup**  
  为Provider流停滞后的清理增加60秒单调超时，防止Provider/模型被永久隔离。  
- **[#5659](https://github.com/agentscope-ai/QwenPaw/pull/5659) – fix(chat): allow sending attachments without text**  
  允许用户仅上传附件（无文字）即可发送消息，满足企业微信等场景的文件直接处理需求。  

此外，**#7964**（Langfuse工具`output`记录修复）、**#7961**（替换GPL许可的`html2text`依赖为MIT许可的`markdownify`）等修复也已合入，项目正向更稳定、合规的方向迈进。

## 社区热点  
| 序号 | Issue/PR | 评论数 | 核心诉求 |
|------|----------|--------|----------|
| 1 | [#7318](https://github.com/agentscope-ai/QwenPaw/issues/7318) 多租户Hub规划 | 32 | 社区强烈要求支持团队级多用户运行，作者主动征集下一阶段开发方向 |
| 2 | [#4474](https://github.com/agentscope-ai/QwenPaw/issues/4474) 是否支持ChatGPT-5.5 | 9 | 用户配置后无法使用，期望官方明确模型兼容列表 |
| 3 | [#7571](https://github.com/agentscope-ai/QwenPaw/issues/7571) 记忆遗忘问题 | 8 | 用户抱怨Agent经常忘记配置的路径和规则，需反复强调 |
| 4 | [#7576](https://github.com/agentscope-ai/QwenPaw/issues/7576) RetryChatModel硬编码context_size | 6 | 所有模型被强制设为32768，触发`CONTEXT_UNFIT`错误 |
| 5 | [#7628](https://github.com/agentscope-ai/QwenPaw/issues/7628) 上下文压缩超预算 | 6 | 压缩后仍可能超出Provider预算，导致活跃轮次失败 |

**分析**：多租户与记忆持久性是两个最受关注的话题，前者是产品形态拓展，后者直接影响用户体验。社区对模型兼容性（尤其新模型）和上下文管理机制的稳定性有较高期待。

## Bug 与稳定性  
按严重程度排列：

1. **严重 – 会话永久不可用**  
   - [#7966](https://github.com/agentscope-ai/QwenPaw/issues/7966) Provider切换后历史中的`file://`媒体URL被拒绝，会话永久损坏。  
     → 已有修复PR **#7973**（`fix(agents): recover from rejected media URLs`）  
   - [#7534](https://github.com/agentscope-ai/QwenPaw/issues/7534) 飞书会话消费者卡死，新消息无法创建新消费者，整个会话静默无响应。  
     → **暂无已合并fix**（待跟进）

2. **中等 – 功能中断**  
   - [#7968](https://github.com/agentscope-ai/QwenPaw/issues/7968) 控制台v2.2.2b3侧边栏重设计导致无法创建/查看聊天群组。  
     → 已通过**#7972**修复默认分组逻辑。  
   - [#7856](https://github.com/agentscope-ai/QwenPaw/issues/7856) `qwenpaw-pet 0.1.1`插件因丢弃`actor`参数导致工具审批流程断裂。  
     → **暂无fix PR**（已关闭，可能由插件维护者修复）  
   - [#4244](https://github.com/agentscope-ai/QwenPaw/issues/4244) `shell_evasion_checks.newlines=True`默认阻止多行命令，且无提示。  
     → 尚未有对应fix PR。

3. **低严重 – 日志或性能问题**  
   - [#7715](https://github.com/agentscope-ai/QwenPaw/issues/7715) Daily Paper插件在arxiv.org不可达时静默失败，错误消息掩盖真实原因。  
   - [#7963](https://github.com/agentscope-ai/QwenPaw/issues/7963) Langfuse工具观察始终不记录输出（已被**#7964**修复）。  
   - [#7943](https://github.com/agentscope-ai/QwenPaw/issues/7943) Windows沙箱ACL设在驱动器根目录可能锁定卷。

## 功能请求与路线图信号  
以下需求用户呼声较高，且部分已有实现PR：

- **官方移动端App**（[#7976](https://github.com/agentscope-ai/QwenPaw/issues/7976)）：用户希望至少推出Android端，安全连接自托管服务。目前无对应PR，属于长期产品需求。
- **实时语音聊天**（[#7785](https://github.com/agentscope-ai/QwenPaw/pull/7785)）：已提交PR，支持Provider可配置的对话式语音输入/播放，复用现有聊天路径。预期可能进入下一版本。
- **持久化分页会话记录**（[#7931](https://github.com/agentscope-ai/QwenPaw/pull/7931)）：PR已提交，基于SQLite存储和分页读取。可提升长会话历史查询体验。
- **记忆写入独立模型**（[#7719](https://github.com/agentscope-ai/QwenPaw/pull/7719)）：允许为ReMeLight记忆写操作指定不同模型（如低成本模型），节省token。PR待合并。
- **多标签终端**（[#7861](https://github.com/agentscope-ai/QwenPaw/pull/7861)）：控制台新增经过身份验证的多标签终端，支持独立工作目录。功能较为成熟。
- **禁用预制模型/频道**（[#7957](https://github.com/agentscope-ai/QwenPaw/issues/7957)）：用户希望手动停用不需要的预置项，属于UI改进需求，暂无PR。

## 用户反馈摘要  
从今日活跃Issue评论中提炼真实场景与痛点：

- **Agent记忆不可靠**（#7571）：“反复强调，还是会忘记路径。”用户在做插件开发，需要Agent记住A路径用于开发、C路径用于部署，但Agent经常跑错目录，导致自动化部署覆盖错误。期望更持久的上下文或配置化记忆。
- **飞书会话卡死**（#7534）：“消费者不再返回拉取下一条，也不崩溃，队列永远不空。”用户反馈DM会话运行数小时后静默失效，新消息无法触发恢复，只能重启服务。
- **上下文压缩丢失工具调用结构**（#5856）：“tool_call数据结构在压缩时被转为纯文本，导致下游400错误。”该问题在长工具链任务中尤为突出，用户期待保留结构化数据的压缩策略。
- **文件保护绕过后门**（#2967）：“当文件工具被禁用时，Agent自动退回到`execute_shell_command`绕过保护。”用户指出安全机制存在绕过隐患，建议统一审批入口。
- **新UI回归问题**（#7968）：“升级v2.2.2b3后聊天群组不见了。”用户对控制台侧边栏重新设计导致的功能丢失表示失望，希望团队加强回归测试。

## 待处理积压  
以下Issue/PR长期未获得维护者响应或处于停滞状态，需重点关注：

| 编号 | 类型 | 标题 | 创建/最后更新 | 重要性 |
|------|------|------|----------------|--------|
| [#1452](https://github.com/agentscope-ai/QwenPaw/issues/1452) | Issue | Docker部署Ollama联网功能咨询 | 2026-03-13 | 用户期待明确的联网使用按钮功能 |
| [#2013](https://github.com/agentscope-ai/QwenPaw/issues/2013) | Issue | 企业微信能否同时支持两个机器人 | 2026-03-21 | 多Agent多频道场景限制 |
| [#1957](https://github.com/agentscope-ai/QwenPaw/issues/1957) | Issue | Matrix本地部署机器人无法回复 | 2026-03-20 | 关键集成缺陷 |
| [#7500](https://github.com/agentscope-ai/QwenPaw/pull/7500) | PR | forward OpenAI extra_headers | 2026-09-02 | 已待合并22天，影响自定义端点兼容性 |
| [#7785](https://github.com/agentscope-ai/QwenPaw/pull/7785) | PR | 实时语音聊天 | 2026-09-15 | 新功能，待合并10天 |

建议维护者优先关注企业微信多机器人限制（#2013）和 Matrix 集成（#1957），这两个问题已存在超过6个月且直接影响多频道部署方案。

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

# ZeroClaw 项目动态日报 — 2026-09-25

**数据统计周期：** 2026-09-24 至 2026-09-25  
**数据来源：** GitHub 仓库 [zeroclaw-labs/zeroclaw](https://github.com/zeroclaw-labs/zeroclaw) Issues & PRs

---

## 1. 今日速览

- **整体活跃度：** 极高。过去 24 小时共产生 27 条 Issue 更新（23 条新开/活跃，4 条已关闭）和 50 条 PR 更新（38 条待合并，12 条已合并/关闭），仅 Issue 区就有约 15 位不同作者提交了内容。项目正处于密集的迭代和问题修复阶段。
- **关键进展：** 安全与合规方面取得突破——关闭了高优先级安全跟踪器 #9899（移除 matrix-sdk 导致的 CVE 豁免），合入了修复 WebSocket 断开导致 Agent 中断的 PR #10538，以及多项 CI 效率优化（#11063、#11069、#11070、#11064）。
- **未解风险：** 仍有多个 P1 级别的严重 Bug 处于开放状态（#10968 无审核管理器导致静默失效、#10797 Markdown 内存后端并发丢失数据、#11087 Windows 关闭窗口后无法重新打开/退出等），需要维护者高度关注。
- **社区输入活跃：** 新功能请求 RFC 集中出现（#11096 风险驱动的合并新鲜度、#11027 Agent 间会话消息、#10970 主机级资源限制），反映了用户对生产级多 Agent 部署和运维安全的强烈需求。

---

## 2. 版本发布

过去 24 小时内无新版本发布。  
当前里程碑跟踪显示 v0.8.6 和 v0.9.0 仍在推进中，相关跟踪器 #7432 和 #8358 均处于活跃状态。

---

## 3. 项目进展

本报告期内有 12 个 PR 被合并或关闭，重点推进了以下工作：

### 已合并/关闭的重要 PR

| PR 编号 | 标题 | 类型 | 影响 |
|--------|------|------|------|
| [#10538](https://github.com/zeroclaw-labs/zeroclaw/issues/10538) | fix(gateway): keep the agent turn running when the chat WebSocket disconnects | Bug 修复（XL 尺寸） | 修复了用户在 Web 仪表盘关闭聊天窗口后 Agent 被错误终止的 #8559 根本原因。 |
| [#11063](https://github.com/zeroclaw-labs/zeroclaw/issues/11063) | ci(codeql): pin the Rust scan runner label and retire CI_USE_BLACKSMITH | CI 优化 | 清理历史环境变量，统一 CI 标签。 |
| [#11069](https://github.com/zeroclaw-labs/zeroclaw/issues/11069) | perf(ci): give colliding Rust matrix legs distinct cache keys | 性能优化 | 避免不同依赖集的编译缓存冲突，预计可减少约 13 个作业的重复编译时间。 |
| [#11070](https://github.com/zeroclaw-labs/zeroclaw/issues/11070) | perf(ci): skip Docker source builds when only the release workflow changed | 性能优化 | 当仅发布流程文件变更时跳过完整的 Docker 映像构建（避免 7 个编译腿）。 |
| [#11064](https://github.com/zeroclaw-labs/zeroclaw/issues/11064) | perf(ci): run the Windows task-owner recovery tests as a parallel job | 并行化 | Windows 编译腿中拆分测试与编译，减少流水线阻塞时间。 |
| [#11073](https://github.com/zeroclaw-labs/zeroclaw/issues/11073) | perf(ci): run CodeQL on master pushes only when analyzed code changes | 性能优化 | CodeQL 扫描仅在 Rust/配置变更时触发，减少不必要的 90 分钟扫描。 |
| [#11083](https://github.com/zeroclaw-labs/zeroclaw/issues/11083) | fix(gateway): drive webhook-started SOP agent steps | Bug 修复 | 修复 Webhook 触发的 SOP 中 `ExecuteStep` 永远不会执行的问题（#9805 的补残）。 |

### 关键里程碑进展

- **SOP 控制面**（跟踪器 #8288）：
  PR #10155（SOP 运行日志与去重）仍处于开放状态，本日合并的 #11083 解决了 Webhook 触发 SOP 的核心阻塞问题，使 SOP 自动化功能向 5/5 成熟度迈进了一步。
- **OIDC 身份认证**（跟踪器 #8289）：
  PR #10259（在 RPC 上强制认证身份）仍然开放，依赖 #10248 等前置 PR。该 PR 是 OIDC 里程碑第三阶段的核心。
- **ZeroRelay 原生传输**（跟踪器 #8358）：
  新 PR #11089（从链接预填充前端注册表单）已提交，继续推进浏览器注册流程。

---

## 4. 社区热点

### 讨论最活跃的 Issue

- [#8692](https://github.com/zeroclaw-labs/zeroclaw/issues/8692) **[Tracker]** Maintainer decision queue  
  - 评论：15 条 | 持续更新  
  - 内容：作为 RFC 和设计决策的维护者队列，本日无新增，但长期保持高频关注。

- [#6489](https://github.com/zeroclaw-labs/zeroclaw/issues/6489) **[Tracker]** Unified capability catalog and plugin migration roadmap  
  - 评论：8 条  
  - 内容：将集成与 WASM 插件统一为单一能力目录的路线图跟踪器，社区对“一切皆插件”理念讨论热烈。

- [#8519](https://github.com/zeroclaw-labs/zeroclaw/issues/8519) **Reconcile cargo-audit ignores and remediate wasmtime-wasi CVEs**  
  - 评论：7 条 | 本周仍有新讨论  
  - 背景：安全 CI 中 `cargo audit` 与 `cargo deny` 忽略列表不一致导致 CVE 遗漏，社区贡献者正在推动统一策略。

### 最新高参与度 RFC

- [#10970](https://github.com/zeroclaw-labs/zeroclaw/issues/10970) **Host-scoped admission control and per-agent resource bounds**  
  - 作者：JordanTheJet | 创建 2 天前，已有 5 条评论  
  - 核心诉求：当一台机器运行大量 Agent 时，需要主机级的并发限流和内存上限，以避免稳定性退化。

- [#11027](https://github.com/zeroclaw-labs/zeroclaw/issues/11027) **Agent-to-agent session messaging with receiver discretion**  
  - 作者：Audacity88 | 创建 3 天前，3 条评论  
  - 核心诉求：需要允许不同会话中的 Agent 直接交换消息（发现、协调），而不必通过人工复制粘贴。这反映了多 Agent 协作场景的迫切需求。

**分析：** 社区对 **多 Agent 集群管理** 和 **生产级安全管控** 的关注显著升温。近期涌现的 RFC 几乎都围绕 Agent 间通信、主机级资源边界、零信任身份认证等企业级特性，表明 ZeroClaw 正在从个人工具向团队/组织级平台演进。

---

## 5. Bug 与稳定性

### 严重性 S0（数据丢失/安全风险）

| Issue | 标题 | 状态 | 说明 |
|-------|------|------|------|
| [#10968](https://github.com/zeroclaw-labs/zeroclaw/issues/10968) | Unattended agent turns run with no ApprovalManager | **OPEN** (P1) | 无交互场景（cron/heartbeat/SOP）未初始化 ApprovalManager，导致风险配置文件中的工具审批形同虚设。**尚无 fix PR。** |
| [#10797](https://github.com/zeroclaw-labs/zeroclaw/issues/10797) | markdown memory backend silently loses stored entries | **OPEN** (P1) | 并发 `store()` 调用导致文件覆盖丢失数据。**尚无 fix PR。** |

### 严重性 S1（工作流阻塞）

| Issue | 标题 | 状态 | 说明 |
|-------|------|------|------|
| [#11087](https://github.com/zeroclaw-labs/zeroclaw/issues/11087) | Windows — after closing the window the app can be neither reopened nor quit | **OPEN** (P1) | Windows 桌面版关闭窗口后进程残留，无法重新启动也无法退出。**尚无 fix PR。** |

### 严重性 S2（行为退化）

| Issue | 标题 | 状态 | 说明 |
|-------|------|------|------|
| [#11094](https://github.com/zeroclaw-labs/zeroclaw/issues/11094) | Apple preflight tests can fail when the retry sleep mock intercepts subprocess polling | **OPEN** | CI 测试稳定性问题，模拟睡眠影响了真实的子进程轮询。作者已标识。 |
| [#11093](https://github.com/zeroclaw-labs/zeroclaw/issues/11093) | Stable docs promotion leaves root llms files out of sync | **OPEN** | 文档版本切换时 `llms.txt` 未更新，影响 LLM 文档索引。 |

### 近期已关闭的严重 Bug

- [#9899](https://github.com/zeroclaw-labs/zeroclaw/issues/9899) `bitmaps` CVE 跟踪器 —— **已关闭**（相关修复已通过依赖升级完成）。
- [#10948](https://github.com/zeroclaw-labs/zeroclaw/issues/10948) 中断范围键在组件边界冲突 —— **已关闭**（已在 #11083 配套修复中解决）。

**稳定性趋势：** 本日合入了两个影响范围较大的 Bug 修复（WebSocket 中断、Webhook SOP 不执行），但仍有 3 个 P1 严重 Bug 未得到解决，尤其是 #10968 和 #10797 直接影响无值守运行的安全性，建议维护者优先调度。

---

## 6. 功能请求与路线图信号

### 新提出功能请求（本日新增）

- [#11103](https://github.com/zeroclaw-labs/zeroclaw/issues/11103) **feat(providers): add Cheaper Inference as a typed OpenAI-compatible provider**  
  用户请求增加一个名为 `cheaperinference` 的 provider 类型，对接新兴的 LLM 网关服务。这类请求反映了社区对低成本推理后端的需求。

- [#11100](https://github.com/zeroclaw-labs/zeroclaw/issues/11100) **Preserve configured provider aliases in cost-rate catalog prefill**  
  希望仪表盘和 ZeroCode 在预填充成本费率时保留用户设置的 provider 别名，而不是降级到家族名。属于用户体验优化。

- [#11096](https://github.com/zeroclaw-labs/zeroclaw/issues/11096) **RFC: Risk-based merge-result freshness**  
  讨论应基于变更风险等级决定 PR 合并时是否需要重新基于最新 master 运行检查，以减少不必要的 CI 消耗。该 RFC 若被接受，将影响合并策略。

- [#11088](https://github.com/zeroclaw-labs/zeroclaw/issues/11088) **Docs: Move multi-agent setup guide from Contributing to Agents**  
  文档重新组织：将多 Agent 部署指南从“贡献指南”移到“Agent”章节，降低新用户的学习门槛。

### 可能纳入下个版本的信号

- **Plugins 运行时化**（跟踪器 #8850）已有配套 PR [#11081](https://github.com/zeroclaw-labs/zeroclaw/issues/11081)（host-mediated sockets, WebSocket, TLS profiles, durable state）处于开放状态，该 PR 是 #8850 的关键实现，若合入将使可选通道/工具彻底脱离编译期特征，大幅减少二进制体积。
- **ZeroRelay 前端** 的 PR #11089（预填充链接参数）和 #10315（重新添加浏览器注册入口）均活跃，表明 v0.9.0 的注册流程正在快速打磨。
- **运行时组合边界**：PR #11090/#11092 提出了公开运行时组合契约的草案，若经核心团队批准，将允许第三方嵌入式使用 ZeroClaw 运行时。

---

## 7. 用户反馈摘要

从 Issues 评论中提炼的真实用户痛点与场景（基于文字描述）：

- **痛点①：无交互环境下的工具审批失效**  
  用户在 #10968 中报告：“当 Agent 通过 cron 或 webhook 自动运行时，风险配置中的工具审批完全不起作用，等于没有安全审计。” 这一反馈直接触发了该 Bug 的升级。

- **痛点②：Web 仪表盘会话管理混乱**  
  #8559 的评论提到：“我只是关掉了聊天窗口，Agent 就以为我取消了任务，所有工作都中断了。我不能在 Agent 工作的同时做其他事甚至查看它的文件。” 该问题已由 PR #10538 修复，预计在下一个版本中解决。

- **痛点③：Windows 桌面应用体验差**  
  #11087 简短但尖锐：“关闭窗口后应用没有退出，进程驻留且无法重新打开，只能通过任务管理器杀死。” 这暴露了桌面端生命周期管理的缺陷。

- **愿望：更低的推理成本与灵活配置**  
  #11103 和 #11100 的提出者均提到希望对接更便宜的 LLM 网关，并在成本核算中保留自定义别名，说明用户正在将 ZeroClaw 用于生产环境并关心成本可追溯性。

- **社区贡献者积极反馈：** PR #11039（添加 You.com MCP 搜索示例）来自外部贡献者 mouse-value-add，其评论表达了对文档易用性的认可：“这个例子会让新用户更清楚如何配置外部搜索工具。”

---

## 8. 待处理积压

### 长期未响应的严重 Issue

| Issue | 标题 | 创建时间 | 最后更新 | 当前状态 |
|-------|------|----------|----------|----------|
| [#7432](https://github.com/zeroclaw-labs/zeroclaw/issues/7432) | [Tracker]: Runtime and gateway delivery - v0.8.6 and v0.9.0 | 2026-06-09 | 2026-09-24 | 依赖多个子任务，进展缓慢 |
| [#8358](https://github.com/zeroclaw-labs/zeroclaw/issues/8358) | [Tracker]: ZeroRelay native transport and v0.9.0 readiness | 2026-06-26 | 2026-09-24 | 同样依赖多个 PR，需关注整体阻塞项 |
| [#8288](https://github.com/zeroclaw-labs/zeroclaw/issues/8288) | [Tracker]: SOP milestone: daemon-owned SOP control plane to 5/5 | 2026-06-24 | 2026-09-24 | 本日有进度（#11083 合并），但仍有多个子 PR 积压 |

### 需维护者关注的开放 PR

- [#7821](https://github.com/zeroclaw-labs/zeroclaw/issues/7821) **feat(security): canonical sandbox_policy schema with application-layer enforcement**  
  - 已停留 100 天+，标记 `needs-author-action`，作者 rarean 需回应审查意见。
- [#10259](https://github.com/zeroclaw-labs/zeroclaw/issues/10259) **feat(security): enforce authenticated principals on RPC**  
  - 自 8 月 22 日起开放，是 OIDC 里程碑的关键 PR，但依赖大量前置合并。建议确保 CI 检查通过后尽快合并或拆分。

### 提醒

- **#10814 发布效率跟踪器**记录了大量 CI 优化任务，本日的多个 CI 优化 PR（#11063-#11073）已开始兑现，但仍需关注剩余改进项（如并行化发布流程）。
- **#10970 及 #11027 两个 RFC** 尚未收到维护者正式回复，建议在下周的核心会议中讨论，以引导社区贡献方向。

---

**日报生成时间：** 2026-09-25  
**分析师：** AI 开源项目分析师  
**数据来源：** GitHub zeroclaw-labs/zeroclaw

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*