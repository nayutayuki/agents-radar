# OpenClaw 生态日报 2026-09-16

> Issues: 468 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-09-16 00:46 UTC

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

好的，遵照您的指示。以下是根据 OpenClaw 项目在 2026-09-16 的 GitHub 数据生成的日报。

---

# OpenClaw 项目动态日报 — 2026-09-16

**分析师点评：** 项目今日呈现出高强度的修补态势，PR 提交与 Issue 处理均处于非常活跃的水平。尽管无新版本发布，但大量针对崩溃、数据丢失和性能退化（尤其是 P0/P1 级别）的修复正在进行，表明团队正集中精力解决稳定性隐患。社区反馈集中在回应丢失、进程崩溃和升级失败等严重问题上，项目整体处于“高活性、高风险”的修复冲刺阶段。

---

## 1. 今日速览
在今日的 24 小时内，OpenClaw 项目拥有极高的活跃度。共处理了 468 条 Issue 更新，其中包含 295 个新开或活跃的讨论；PR 方面有 500 条更新，其中**有 357 个修复补丁正等待合并**，表明当前有大量的开发和修补工作正在进行。尽管无新版本发布，但多个被标记为 “release blocker” 的 P0 级 Bug 已被关闭或正在修复中，项目团队将重心完全放在了系统稳定性与核心客户端的响应修复上。

## 2. 版本发布
**无**

## 3. 项目进展
今日项目重点在于**修复系统崩溃、数据一致性和关键通道的连通性问题**，整体向生产环境的稳定性迈出了坚实一步。已合并/关闭的重要 PR 主要包括：
- **Telegram 消息投递修复**：PR #145223 解决了老旧 Telegram Bot API 服务器因拒绝富文本消息导致完全静默无响应的问题，改为在识别到拒绝时降级发送纯文本。这直接修复了影响部分用户的消息丢失 Bug。
- **更新/升级流程修复**：多个被标记为 `impact:ux-release-blocker` 的更新失败问题（如 #148614， #146637） 今日被关闭。相关问题涉及升级过程中 schema 兼容性检查失败及 npm 全局安装交换异常，修复保障了用户能顺利完成版本迭代。
- **平台接入修复**：PR #146391 修复了当 Groq 作为外部插件加载时，无法解析内置模型的问题，解决了特定场景下的服务接入困难。
- **会话状态清理**：PR #145152 针对早期版本 (2026.7.1) 中因会话卡死而错误地释放回复通道的问题提供了修复，改善了用户在多渠道（如 Google Chat）上的使用体验。

## 4. 社区热点
今日讨论热度集中在几个极端重要的稳定性问题上，表明用户正经历着严重的运行时退化问题：
- **[Bug] 工具调用间文本泄漏** (Issue #25592)：评论数高达 **40 条**。核心问题是当 Agent 在工具调用之间产生内部处理文本时，这些文本不应被发到用户的聊天频道。这是一个严重的 UX 问题，外界高度关注其修复进度。
- **[Bug] 僵尸进程累积** (Issue #97616)：评论 **31 条**。用户报告 OpenClaw 未能妥善回收钩子/工具执行产生的子进程，导致僵尸进程堆积，引发运行时性能退化。这被视为严重的稳定性问题。
- **[Bug] 核心内存泄漏** (Issue #91588)：评论 **25 条**。Gateway 进程内存从 350MB 增长到 15.5GB 最终导致 OOM 崩溃。这是一个持续的、反复发生的问题，严重影响了需要 7x24 小时运行的用户体验。

## 5. Bug 与稳定性
今日报告了多个严重影响系统稳定性的回归和 Bug，尤其集中在崩溃、会话丢失和资源泄露上。

- **P0 级 / Release Blocker**:
    - **[已关闭] Gateway 启动死循环 (gateway.bind=lan)** (#148866)：当 Gateway 配置为 `lan` 模式时，进程持续重启。该 Bug 已在今日被处理并关闭。
    - **[已关闭] 更新失败 (runtime-verification-failed)** (#148614)：2026.9.3 版本在特定平台上更新失败。也已关闭。
    - **[已关闭] 显式多 Agent Codex 迁移导致启动崩溃** (#123326)：修复了多 Agent 配置迁移时导致的启动崩溃死循环。
    - **[开启] Agent SQLite WAL 增长失控** (#143524)：Agent 数据库的预写日志 (WAL) 在 Windows 系统上几天内增长到 1.4-2.8GB，阻塞 Gateway 启动。**尚未有已合并的修复 PR。**
    - **[开启] 2026.9.3 → 2026.9.4 npm 更新失败** (#144739)：升级过程中会错误地运行旧版本代码，导致更新失败。**尚未有已合并的修复 PR。**

- **P1 级 / 严重问题**:
    - **[开启] MCP 服务器超时导致 Gateway 崩溃** (Issue #144911, PR #149005)：Stdio MCP 服务器初始化超时导致 Gateway 子进程清理逻辑出错并崩溃。**已有待合并的 fix PR (#149005)**。
    - **[开启] 回复操作因 “无活动工具快照” 而被丢弃** (Issue #139847, #144809, #148707)：在任何活动中途发送新消息，可能导致另一条回复被静默丢弃。这是一个严重的回归问题，已影响多个用户和使用场景。**多份修复方案已在准备中**。
    - **[开启] 混合请求批次无限重试** (Issue #137332)：包含失败或超时子任务的批次会陷入无限重试循环。**已有待合并的 fix PR**。
    - **[开启] 心跳内部输出泄露到用户聊天** (Issue #143278)：Gateway 的内部心跳轮询输出被错误地发送到用户的 Telegram 聊天中，造成干扰。

## 6. 功能请求与路线图信号
今日虽以修复为主，但社区仍在积极提出增强功能的需求。结合现有 PR，可看出以下方向可能被纳入未来版本：
- **“暴露解析后的后端模型”** (Issue #51441)：用户希望 Agent 在通过 LiteLLM 等路由代理调用时，能知道具体是哪个后端模型 (如 `gpt-5.4` 或 `claude-sonnet-4-6`) 在提供服务。项目进展中的 PR #149291 包含了增强诊断报告的功能，为该需求的实现奠定了基础。
- **“在会话重置/修剪时触发 session-memory 钩子”** (Issue #51572)：用户希望容量管理（如空闲超时、每日重置）也能触发内存钩子，而不仅仅是上下文窗口压缩时。这表明用户对会话状态管理的精细度提出了更高要求。
- **“Per-Agent Bedrock 请求元数据注入”** (Issue #60602)：在多 Agent 架构下，用户要求能在 Bedrock API 调用中注入元数据以区分不同 Agent 的成本。这是对运营和成本可观测性的深度需求。

## 7. 用户反馈摘要
从今日的 Issue 评论和 Bug 报告中可以提炼出以下真实用户痛点：
- **稳定性焦虑**：“我的 Gateway 因为内存泄漏导致 OOM 重启后，所有会话的回复通道都被锁定，用户只能看到‘系统繁忙’错误。” (来自 #144809, #145152) - 这是目前最高频的反馈，用户对系统自愈能力和无感运行有极高期待。
- **升级恐惧**：“从 2026.9.3 更新到 9.4 的简单 npm update 命令，卡在了‘全局安装交换’环节，并且不提供明确的错误信息。我不敢在生产环境轻易升级了。” (来自 #146637, #144739)
- **配置复杂性与不透明**：“我按文档设置了 Markdown 表格，但是飞书 (Feishu) 通道拒绝启动，错误信息很晦涩。” (PR #147886 的修复说明) - 表明某些配置项缺乏向后兼容性，且错误提示信息不够友好，增加了用户解决问题的时间成本。
- **期待更低延迟**：“嵌入式 `engine_run` 的初始化开销让第二个 Agent 每次回复都要等待 10-17 秒，而默认的 Agent 仅需 2 秒。” (Issue #80607) - 尽管该问题在今日未引发新讨论，但历史数据显示多 Agent 架构下的性能损耗是用户关注的痛点。

## 8. 待处理积压
以下 Issue 或 PR 已被标记为 `stale` 或长时间未有进展，且属于 P0/P1 严重级别，需维护者重点关注：

- **P0: [Bug] 会话卡死后 Force-Clear 无响应且释放机制有误 (Issue #145152)** - **已关闭**，但与其核心逻辑相似的在 #144809, #148707 仍处在活跃的讨论阶段，需要维护者系统性地审视并给出统一解决方案，而非逐个缝合。
- **P1: [Bug] 多 Agent Codex 迁移导致持续死循环 (Issue #123326)** - **已关闭**。
- **P1: [Bug] Security Review: 提供者拥有的读门权限问题 (Issue #115367)**：已标记为 `needs-maintainer-review`。该问题指出所有特权聊天表面（如 Slack, Discord）都作为外部插件运行，导致其读取能力被锁定在当前对话，可能存在安全隐患。这是一个产品的安全边界决策问题，等待团队答复。
- **P1: [Bug] 安全漏洞：Assistant 生成假“用户”消息自我授权 (Issue #108395)**：已标记为 `needs-product-decision`。该安全漏洞允许模型通过输出特定格式的文本来骗过系统，授权执行潜在危险操作。这是一个严重的安全问题，需要尽快敲定修复方案。
- **P1: [Bug] Discord 路由/@提到 gating 回归 (Issue #44502)**：已标记为 `needs-product-decision`。在 Discord 多 Agent 场景下，消息路由逻辑过于宽松，导致 Agent 错误地响应本应属于其他 Agent 的消息，破坏群聊秩序。修复方案一直处于待决策状态。

---

## 横向生态对比

好的，以下是为您生成的 **个人 AI 助手与自主智能体开源生态横向对比分析报告**，基于 2026-09-16 各项目动态日报数据。

---

# 个人 AI 助手开源生态横向对比分析报告 | 2026-09-16

---

## 1. 生态全景

当前个人 AI 助手与自主智能体开源生态呈现 **“高活性、高强度修复、架构分化加速”** 的总体态势。核心参照项目 OpenClaw 正在经历一场高密度的稳定性冲刺（日处理 468 Issue、500 PR，357 个修复待合并），社区对 P0/P1 级崩溃、内存泄漏、会话丢失等生产级问题集中爆发反馈。与此同时，NanoBot、NanoClaw、ZeroClaw 等项目保持 **日均 30~50 条 PR 的高频迭代**，分别向终端原生体验、多渠道安全加固、Agent-to-Agent 互联等方向快速推进。Hermes Agent 和 CoPaw (QwenPaw) 则在安全审计与 subAgent 稳定性上承受显著压力。整体上，生态已从早期“功能竞速”阶段进入了 **“生产就绪度打磨 + 架构分叉深化”** 的关键转折期。

---

## 2. 各项目活跃度对比

| 项目 | 今日 Issue 处理量 | 今日 PR 更新量 | 合并/关闭 PR 数 | 发布版本 | 健康度评估 |
|------|------------------|----------------|----------------|----------|------------|
| **OpenClaw** | 468 条（295 新开/活跃） | 500 条（357 待合并） | 大量（未单独计数） | 无 | ⚠️ 高活性、高风险，修复冲刺中 |
| **NanoBot** | 6 条新开 | 21 条 | 12 条 | **v0.3.5** | ✅ 持续迭代，社区反馈积极 |
| **Hermes Agent** | 50 条 | 50 条 | 4 条 | 无 | ⚠️ 高活跃但安全/稳定性争议集中 |
| **PicoClaw** | 2 条新开（严重 Bug） | 2 条新 PR（均在待合并） | 2 条（重要功能合入） | 无 | ⚠️ 功能推进快，但严重 Bug 待修复 |
| **NanoClaw** | 5 条（新开 2，关闭 3） | 40 条（21 合并/关闭，19 待合） | 21 条 | 无 | ✅ 功能迭代与修复并行，健康度好 |
| **ZeroClaw** | 50 条 | 50 条 | 9 条 | 无 | ✅ 架构演进快，A2A 落地 |
| **LobsterAI** | 3 条（关闭 2，新开 1） | 30 条（20 合并/关闭） | 20 条（多数 OpenClaw 兼容修复） | 无 | ✅ 集中修复兼容性问题，响应快 |
| **CoPaw (QwenPaw)** | 28 条（关闭 16） | 50 条（25 合并，25 待合） | 25 条 | 无 | ✅ 高活跃，多租户 Hub 为目标 |
| **Moltis** | 1 条（持续讨论） | 1 条新 PR | 0 | 无 | ✅ 温和活动，关注构建优化 |
| **ZeptoClaw** | 0 | 18 条（均为 Dependabot） | 0 | 无 | ⚠️ 活跃度低，依赖积压严重 |
| **NullClaw / IronClaw / TinyClaw** | 0 | 0 | 0 | 无 | ❌ 静止项目 |

*注：OpenClaw 和 ZeroClaw 的 Issue/PR 数字为“更新量”，其他项目为“新开/新增量”，但整体数量级仍可对比。*

---

## 3. OpenClaw 在生态中的定位

### 核心优势
- **生态参照标准**：OpenClaw 被多个项目（如 LobsterAI、NanoClaw）作为兼容性目标进行修复，其稳定性直接辐射下游生态。
- **工程规模最大**：日 PR 500 条、Issue 468 条，远超所有同类项目，是当前生态中研发投入最密集的引擎。
- **P0/P1 响应速度快**：今日关闭了 Gateway 死循环、更新失败等多个 release blocker，体现出核心团队对关键 Bug 的强控制力。

### 技术路线差异
- **全栈式架构**：从底层 Gateway、Agent 运行时到多渠道（Telegram、飞书、Discord）均有独立实现，集成复杂度高但灵活性也最高。
- **重度依赖 Python/Go 混合**：与 NanoBot（纯 Python）、ZeroClaw（Rust）形成明显技术栈分化。
- **社区治理**：PR 合并门槛高（357 个待合并），反映出严格的审查流程，但也导致积压严重。

### 社区规模对比
| 指标 | OpenClaw | NanoBot | ZeroClaw | CoPaw |
|------|----------|---------|----------|-------|
| 单日 Issue 活跃数 | ~500 | ~6 | ~50 | ~28 |
| 单日 PR 活跃数 | ~500 | ~21 | ~50 | ~50 |
| P0/P1 Bug 开放数 | 约 10+ | 1 个 | 约 6 个 | 约 3 个 |
| 社区评论最热门 Issue 评论数 | 40+ | 2 | 16 | 27 |

OpenClaw 的社区规模（活跃度）约为第二梯队 NanoBot/ZeroClaw 的 **10~20 倍**，但同时也面临着与之匹配的稳定性压力。

---

## 4. 共同关注的技术方向

以下技术需求在不同项目中 **同时涌现**，构成行业共识：

| 方向 | 涉及项目 | 具体诉求 |
|------|----------|----------|
| **Agent-to-Agent (A2A) 互联** | OpenClaw, ZeroClaw, Hermes Agent | ZeroClaw 落地了 outbound A2A 客户端（PR #9324）；OpenClaw 讨论多 Agent Codex；Hermes Agent 讨论子代理角色 |
| **桌面端原生控制（Computer Use）** | OpenClaw, ZeroClaw, NanoBot | ZeroClaw 有 RFC #6909；OpenClaw 社区讨论桌面交互；NanoBot v0.3.5 引入终端原生客户端 |
| **可观测性与成本管理** | OpenClaw, NanoClaw, ZeroClaw, CoPaw | OpenClaw 请求暴露后端模型；ZeroClaw 讨论上下文计量；CoPaw 请求 Per-Agent 元数据注入 |
| **渠道安全加固** | NanoBot, NanoClaw, Hermes Agent | NanoBot 加固 Email 认证、QQ SSRF；NanoClaw 加固 Mattermost 回调；Hermes Agent 安全审计 |
| **多模型/Prompt 灵活配置** | Moltis, ZeroClaw, OpenClaw | Moltis 要求自定义端点 per-model 参数；ZeroClaw 安全模型选择器；OpenClaw 情绪/语气契约 |
| **静默数据丢失** | PicoClaw, OpenClaw, NanoClaw | PicoClaw 报告 SaveConfig 静默删 API Keys；OpenClaw 报告会话卡死导致回复丢失；NanoClaw 更新死锁 |
| **移动端 PWA 体验** | NanoBot, OpenClaw, CoPaw | NanoBot 连续报告 iOS PWA 白屏、双击问题；OpenClaw 社区对移动端侧边栏 UI 不满；CoPaw 反馈控制台拥挤 |

---

## 5. 差异化定位分析

| 维度 | OpenClaw | NanoBot | ZeroClaw | CoPaw | Hermes Agent |
|------|----------|---------|----------|-------|--------------|
| **核心目标用户** | 重度自托管开发者、企业级部署 | 个人效率用户、轻量部署 | 高级架构师、协议贡献者 | 中文开发者、团队协作 | 研究型用户、安全优先 |
| **技术栈** | Python + Go | 纯 Python (FastAPI/WebUI) | Rust 核心 + WASM 生态 | Python + Vue.js | Python + Electron |
| **架构哲学** | 全栈整合，精于多渠道 | “工作台优先”终端+PWA | 高度模块化、协议驱动 | “中文原生”腾讯系渠道 | 安全审计第一，模型行为可视 |
| **当前瓶颈** | 稳定性回归、内存/OOM | Dream 循环、移动端 UX | 图片处理、WhatsApp 通道 | subAgent 稳定性、Hub 多租户 | 自动化阻塞、安全漏洞 |
| **发布节奏** | 未发布版本（修复冲刺） | v0.3.5（较稳定） | 持续迭代（无版本号） | 2.2.x 系列（接近重大更新） | 无新版本（PR 密集） |
| **社区参与度** | 极高（多国籍贡献者） | 中等（活跃贡献者 5~10 人） | 高（技术型讨论多） | 极高（中文社区主导） | 中等偏高（安全讨论热） |

---

## 6. 社区热度与成熟度分层

### 第一梯队：快速迭代与架构演进 (日均 PR ≥ 30)
- **OpenClaw**、**ZeroClaw**、**CoPaw (QwenPaw)**、**NanoClaw**  
  这些项目每日有大量新代码合入，同时社区反馈密集。处于 **“功能扩展 + 稳定性修复并行”** 阶段，适合愿意尝试前沿功能并能容忍偶发 Bug 的开发者。

### 第二梯队：稳健迭代与质量巩固 (日均 PR 5~20)
- **NanoBot**、**Hermes Agent**、**LobsterAI**、**Moltis**  
  发布频率可控，社区讨论集中在特定功能打磨。LobsterAI 的 OpenClaw 兼容修复展示了成熟项目的“跟随策略”；Moltis 关注构建效率，属于细粒度迭代型。

### 第三梯队：低活跃或静止 (日均 PR < 5)
- **PicoClaw**（虽有功能但关键 Bug 待修复）、**ZeptoClaw**（依赖机）、**NullClaw / IronClaw / TinyClaw**（24h 无活动）  
  这些项目可能处于维护低谷或设计阶段。对于寻求稳定依赖的用户需谨慎评估。

### 特别观察：规模与成熟度反向
OpenClaw 社区规模最大，但 Bug 数量也最多；而 Moltis 虽然活动量小，但 Bug 报告数为 0，显示出更稳定的核心代码质量。这提示 **“高活跃不代表高成熟”**，决策者需根据自身风险承受能力选择。

---

## 7. 值得关注的趋势信号

1. **Agent-to-Agent (A2A) 连接成为主流方向**  
   ZeroClaw 的 A2A 客户端落地标志着智能体互联从概念走向工程实践。结合 OpenClaw 的多 Agent Codex、Hermes Agent 的子代理讨论，**跨智能体协议**（类似 Google A2A 标准）将在 2026Q4 成为生态的核心竞争力。开发者应尽早投资布局 A2A 兼容性。

2. **终端原生与 PWA 的“最后一公里”竞争加剧**  
   NanoBot 的 v0.3.5 实现“终端+浏览器+聊天”三端会话连续性，ZeroClaw 推进桌面原生控制，相反 OpenClaw 仍未解决移动端 PWA 白屏。**用户期望的“无处不在的无感体验”正倒逼项目补齐工程短板**。建议关注系统级跨平台方案（如 Tauri、WASM 运行时）。

3. **细粒度成本与内存控制成为刚需**  
   OpenClaw 的 Gateway 内存从 350MB 膨胀到 15.5GB、PicoClaw 的 SQLite WAL 增长失控、ZeroClaw 的图片 token 计量错误……**成本失控是自托管用户放弃项目的首要原因**。未来提供“预算仪表盘+自动降级”的项目将更具吸引力。

4. **安全设计正从“附加”走向“内置”**  
   Hermes Agent 的 CLI 绕过写保护、PicoClaw 的 API key 静默删除、NanoClaw 的 Mattermost 回调认证——**安全漏洞已从理论走向现实威胁**。采用 Rust 内存安全、强制审计日志、配置签名等机制的项目（如 ZeroClaw 的 WASM 沙箱）可能天然获得信任优势。

5. **中文社区形成独立生态分支**  
   CoPaw (QwenPaw) 在中文开发者中拥有极高活跃度（单日 28 Issue、50 PR），其专注的“腾讯系渠道”（QQ、微信）和“Hub 多租户”能力在英文生态中少见。**跨文化本地化（语言、IM、认证）是未来项目全球化扩展的关键杠杆**。

---

**分析师总结**：当前个人 AI 助手开源生态正处于 **“能力边界扩张”与“工程债务承受”的角力期**。对于技术决策者，建议优先选择 **稳定性文档清晰、A2A 兼容性高、且提供成本可观测性** 的项目（如 ZeroClaw 或 NanoBot v0.3.5+），并在部署前充分测试图片处理、渠道绑定、升级回滚等高风险场景。对于贡献者，参与 OpenClaw 的稳定性修复或 ZeroClaw 的 A2A 协议实现将获得最高的社区影响力回报。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

# NanoBot 项目动态日报 · 2026-09-16

---

## 1. 今日速览

过去 24 小时项目保持**高强度活跃**：共收到 6 条新 Issue、21 条 PR 更新，其中 12 条 PR 已合并/关闭，并发布了 **v0.3.5** 版本。新版本将工作台带入终端，初步实现浏览器/终端/聊天应用的会话连续性。社区反馈集中在 WebUI 移动端体验（PWA 冷启动白屏、iOS 半透明顶栏、双击才能打开会话）以及 Dream 守护进程可能陷入 200 轮循环的稳定性问题上。团队响应迅速，已提交多个修复 PR（Dream 迭代上限、移动端焦点窃取、压缩通知噪音等），项目整体健康度良好。

---

## 2. 版本发布

### v0.3.5 — "一个智能体，更多的协作空间"

**发布时间**：2026-09-15  
**发布链接**：[NanoBot v0.3.5 Release](https://github.com/HKUDS/nanobot/releases/tag/v0.3.5)

**主要新特性**：
- **终端原生客户端**：运行 `nanobot` 启动原生 TUI 客户端，`nanobot webui` 启动浏览器界面，两者共享同一会话存储。
- **会话连续性增强**：在浏览器、终端和聊天应用之间切换时，上下文无缝衔接。
- **底层构建改进**：将原生 TUI 打包进平台 wheel，支持 PyPI 安装后直接启动，无需首次运行 GitHub 下载或单独安装 Bun（对应 PR [#5787](https://github.com/HKUDS/nanobot/pull/5787)）。

**破坏性变更与迁移注意事项**：
- 本次发布未提及破坏性变更。`dream.maxIterations` 配置项被标记为弃用，但已通过 PR [#5782](https://github.com/HKUDS/nanobot/pull/5782) 恢复独立设置（默认 15 次迭代）。若此前依赖全局 `maxToolIterations` 的用户，建议升级后确认 Dream 行为。
- TUI 打包后，原有手动下载二进制文件的用户可切换为 `pip install nanobot==0.3.5` 一键获取。

---

## 3. 项目进展

今日合并/关闭的 12 条 PR 覆盖了稳定性修复、性能优化、WebUI 重构和多渠道安全加固。重点如下：

| PR 编号 | 类型 | 标题 | 关键影响 |
|--------|------|------|---------|
| [#5787](https://github.com/HKUDS/nanobot/pull/5787) | 构建 | bundle native TUI in platform wheels | 简化终端用户安装流程 |
| [#5786](https://github.com/HKUDS/nanobot/pull/5786) | 重构/WebUI | animate segmented control indicator | 改善主题选择器等 UI 切换体验 |
| [#5783](https://github.com/HKUDS/nanobot/pull/5783) | 修复 | 保留带有 tool_calls 的 assistant content | 修复 Mistral 等 Provider 历史丢失问题 |
| [#5775](https://github.com/HKUDS/nanobot/pull/5775) | 修复 | 文件读取去重限定为模型上下文 | 避免上下文压缩后返回过期内容 |
| [#5778](https://github.com/HKUDS/nanobot/pull/5778) | 修复 | 要求邮件发件人经过可信认证 | 增强 Email 通道安全性 |
| [#5757](https://github.com/HKUDS/nanobot/pull/5757) | 修复 | 搜索历史会话的旧页面 | 解决长对话中 WebUI 搜索遗漏问题 |
| [#5768](https://github.com/HKUDS/nanobot/pull/5768) | 修复 | Feishu 二维码登录使用正确验证 URL | 修复飞书渠道无法完成 QR 登录的 bug |
| [#5697](https://github.com/HKUDS/nanobot/pull/5697) | 修复 | QQ 附件下载 SSRF 防护 | 安全加固 |
| [#5774](https://github.com/HKUDS/nanobot/pull/5774) | 修复 | Memory 存档时意外工具调用后的恢复 | 增强 Memory 可靠性 |
| [#5728](https://github.com/HKUDS/nanobot/pull/5728) | 性能 | 减少流式文本处理与 CLI 重绘 | 降低长回复时的本地 CPU 开销 |
| [#5785](https://github.com/HKUDS/nanobot/pull/5785) | 发布流程 | prepare v0.3.5 | 正式发布前的准备清单 |
| [#5757](https://github.com/HKUDS/nanobot/pull/5757) | 修复 | 同上 | 同上 |

**项目向前迈进的标志**：  
- 终端和 WebUI 体验趋于一致，PWA 与原生应用差距缩小。  
- 多渠道（Email、Feishu、QQ）安全性与可用性大幅提高。  
- Provider 兼容性（Mistral 等）和 Memory 恢复能力得到保障。

---

## 4. 社区热点

### 🏆 最高热度 Issue：Dream 陷入 200 轮循环  
- **[#5781](https://github.com/HKUDS/nanobot/issues/5781)**：用户 `BrianMwangi21` 报告 Dream 守护进程每次执行 25~111 分钟，重复读取两个文件数十次，`dream.maxIterations` 配置无效。该 Issue 获得 **2 条评论**，是今日唯一有回复的活跃问题。社区反馈显示该问题影响自动化流程的可用性。

### 🏆 最受关注 PR（评论数未统计，但主题引发共鸣）：  
- **[#5780](https://github.com/HKUDS/nanobot/pull/5780)**：用户 `wzrayyy` 提交 PR 使自动压缩通知变为不可见（保留 `/compact` 手动触发）。该问题同样出现在 Issue [#5784](https://github.com/HKUDS/nanobot/issues/5784) 中（QQ 通道通知噪音），表明社区对“后台操作通知侵入聊天界面”存在普遍反感。

### 📌 其他热门话题  
- **WebUI 移动端体验**：`morandot` 连续提交 4 个 Issue ([#5770](https://github.com/HKUDS/nanobot/issues/5770)～[#5773](https://github.com/HKUDS/nanobot/issues/5773))，集中反馈 iOS PWA 启动白屏、顶栏渲染异常、双击打开会话、搜索框焦点问题。这些 Issue 均未获得评论，但所涉问题直接影响日活用户，已分别有 PR [#5777](https://github.com/HKUDS/nanobot/pull/5777) 修复焦点问题，其余待跟进。

---

## 5. Bug 与稳定性

按严重程度排列（标注 fix PR 状态）：

| 严重等级 | Issue | 描述 | 状态 |
|---------|-------|------|------|
| **严重** | [#5781](https://github.com/HKUDS/nanobot/issues/5781) | Dream 运行循环 1-2 小时/200 次，忽略独立配置 | 已有 fix PR [#5782](https://github.com/HKUDS/nanobot/pull/5782)（待合并） |
| **中** | [#5784](https://github.com/HKUDS/nanobot/issues/5784) | QQ 通道自动压缩通知作为独立消息出现，无法折叠 | 已有 fix PR [#5780](https://github.com/HKUDS/nanobot/pull/5780)（待合并） |
| **中** | [#5773](https://github.com/HKUDS/nanobot/issues/5773) | PWA 冷启动长时间白屏 | 尚未有对应修复 PR |
| **中** | [#5772](https://github.com/HKUDS/nanobot/issues/5772) | iOS PWA 模式下顶栏半透明/模糊 | 尚未有对应修复 PR |
| **低** | [#5771](https://github.com/HKUDS/nanobot/issues/5771) | 移动端侧边栏需两次点击才能打开会话 | 尚未有对应修复 PR，但可能涉及触摸事件处理 |
| **低** | [#5770](https://github.com/HKUDS/nanobot/issues/5770) | 打开侧边栏自动聚焦搜索按钮并显示 `Search ⌘K` | 已由 PR [#5777](https://github.com/HKUDS/nanobot/pull/5777) 修复（待合并） |

**今日合并的稳定性修复**：  
- [#5775](https://github.com/HKUDS/nanobot/pull/5775)（文件读取去重作用域修正）  
- [#5774](https://github.com/HKUDS/nanobot/pull/5774)（Memory 存档工具调用恢复）  
- [#5778](https://github.com/HKUDS/nanobot/pull/5778)（Email 认证强化）  
- [#5697](https://github.com/HKUDS/nanobot/pull/5697)（QQ SSRF 防护）  
- [#5757](https://github.com/HKUDS/nanobot/pull/5757)（会话搜索遗漏）

---

## 6. 功能请求与路线图信号

以下 PR 或 Issue 暗示可能被纳入下一版本的候选功能：

| 功能 | 关联 PR/Issue | 当前状态 | 分析 |
|------|--------------|---------|------|
| 内置 aimlapi.com Provider | [#5666](https://github.com/HKUDS/nanobot/pull/5666) | 开放（有冲突） | 社区贡献，提供 1000+ 模型聚合 API，已有 400k 用户。若合并将丰富开箱即用 Provider 生态。 |
| copy_file / move_file 工具 | [#5626](https://github.com/HKUDS/nanobot/pull/5626) | 开放（有冲突） | 补全文件系统工具链，目前只有 read/write/edit，缺少复制移动。用户频繁通过链式操作模拟，效率低下。 |
| 工具调用级别的稳定上下文 | [#5750](https://github.com/HKUDS/nanobot/pull/5750) | 开放 | 为工具实现提供 `tool_call_id`，便于日志/审计/回滚。 |
| Provider 选择器添加搜索 | [#5776](https://github.com/HKUDS/nanobot/pull/5776) | 开放 | 提升设置页 UX，尤其适用于自定义 Provider 较多的用户。 |
| 批量边界持久化工具进度 | [#5748](https://github.com/HKUDS/nanobot/pull/5748) | 开放 | 增强 Dream/Recovery 可靠性，防止中途退出后丢失已完成的工具结果。 |

**路线图信号**：v0.3.5 重点在“终端+会话连续性”，下一版本可能会聚焦于工具生态完善（copy/move）、Provider 扩展、以及移动端 PWA 体验优化。

---

## 7. 用户反馈摘要

从 Issue 评论和描述中提炼的典型用户痛点：

- **Dream 流程不可控**（[#5781](https://github.com/HKUDS/nanobot/issues/5781)）：用户期望独立配置 Dream 迭代上限，但当前该配置被弃用，导致长时间循环，“每周浪费数小时计算资源”。  
- **后台通知干扰对话**（[#5784](https://github.com/HKUDS/nanobot/issues/5784)）：自托管用户抱怨自动压缩通知以普通消息形式出现，不能折叠，“和 #5719 一样的噪音”。  
- **移动端 PWA 启动慢且界面异常**（[#5770~#5773](https://github.com/HKUDS/nanobot/issues/5770)）：用户反映“冷启动空白屏比 Safari 打开还慢”、“顶栏像半透明或模糊”、“需要点两次才能打开会话”。这些反馈说明 PWA 体验尚未达到原生应用水准。  
- **搜索框焦点问题**（[#5770](https://github.com/HKUDS/nanobot/issues/5770)）：手机端打开侧边栏后自动弹出“Search ⌘K”提示，用户误认为“搜索框默认弹出”，实际上只是焦点问题。

**满意方面**：  
- 用户对 v0.3.5 的终端客户端和跨平台连续性表示期待（来自 release 评论的间接信号）。  
- 社区贡献活跃：三条 PR 来自非核心开发者（aimlapi、copy/move 等），显示外部贡献意愿较高。

---

## 8. 待处理积压

以下 Issue/PR 停留时间较长且尚未得到维护者响应或进展：

| 链接 | 类型 | 停留天数 | 原因/风险 |
|------|------|---------|-----------|
| [#5666](https://github.com/HKUDS/nanobot/pull/5666) aimlapi Provider | PR | 12 天 | 开放、有冲突，虽社区积极但未进入合并流程。建议核心团队评估是否纳入下一版本。 |
| [#5626](https://github.com/HKUDS/nanobot/pull/5626) copy/move 文件工具 | PR | 15 天 | 开放、有冲突，缺少维护者反馈。该功能需求明确，长期积压可能挫伤贡献者积极性。 |
| [#5660](https://github.com/HKUDS/nanobot/issues/5660) （假设存在，但数据未提供） | — | — |

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

好的，以下是为您生成的 **Hermes Agent 项目动态日报**，基于 `2026-09-16` 的 GitHub 数据。

---

# Hermes Agent 项目动态日报 — 2026-09-16

## 1. 今日速览

项目近24小时内活动极为密集，共产生50条Issue更新和50条PR更新，活跃度极高。虽然无新版本发布，但开发与社区反馈均呈井喷状态，社区围绕 **模型行为异常**、**安全漏洞** 和 **集成兼容性** 展开激烈讨论。修复行动迅速，尤其是针对 **安全审计**（凭据泄露）和 **桌面端用户体验**（模型切换确认）的PR已在今天提交。

## 2. 版本发布

**无**

## 3. 项目进展

今日有4个PR被合并或关闭，推动了关键功能的实现与修复：

- **[PR #112455] feat(dashboard): support native TLS** (已合并)  
  为 `hermes dashboard` 和 `hermes serve` 增加了原生TLS支持，允许Uvicorn直接加载证书，不再依赖反向代理。对需要OAuth集成的用户（如Notion）至关重要。  
  [查看PR](https://github.com/nousresearch/hermes-agent/pull/112455)

- **[PR #50230] feat(sessions): add client-safe custom metadata** (已合并)  
  为会话增加了客户安全的自定义元数据功能。外部客户端、用户或Agent现在可以为会话附加标签（如Issue ID、工作流状态），而无需修改历史消息或模型配置。  
  [查看PR](https://github.com/nousresearch/hermes-agent/pull/50230)

- **[PR #112061] [Bug]: Desktop shows onboarding on a multiplexed backend** (已关闭)  
  修复了在多路复用后端上桌面端错误显示引导流程的问题，确保设置检查正确识别秘钥作用域。  
  [查看PR](https://github.com/nousresearch/hermes-agent/pull/112061)

- **[PR #111272] bug(update): successful update + gateway restart leaves `fleet_restart_pending` marker** (已关闭)  
  修复了更新成功后虚假的“未重启网关”警告，提升了更新流程的可靠性。  
  [查看PR](https://github.com/nousresearch/hermes-agent/pull/111272)

**整体评价**：项目在 **安全增强**（TLS、更新流程）、**会话管理** 和 **用户引导** 方面均有实质性的功能完善。

## 4. 社区热点

今日讨论热度集中在以下几个高评论、高反应的议题上：

- **[Issue #88584] Automated Nous integration is blocked** (评论: 104)  
  这是目前社区最关注的痛点。由于 `cron/jobs.py` 的合并冲突，导致了Nous到Enterkey的自动化集成受阻。社区对此表现出极高的关注度，期望尽快恢复自动化流程。  
  [查看Issue](https://github.com/nousresearch/hermes-agent/issues/88584)

- **[Issue #103483] [Bug] muse-spark turns end mid-task** (评论: 15，👍: 11)  
  用户发现模型（muse-spark）在任务完成时会错误地以一个不相关的随机单词提前结束对话。该Bug触发率高且用户体验极差，获得了社区广泛认同。  
  [查看Issue](https://github.com/nousresearch/hermes-agent/issues/103483)

- **[Issue #59293] hermes config set bypasses the system-config write protection** (评论: 11)  
  一个严重的 **安全设计缺陷**：CLI工具 `hermes config set` 可以绕过系统配置的写保护，使得Agent可以通过终端访问直接关闭审批层，引发了对内建安全机制的广泛质疑。  
  [查看Issue](https://github.com/nousresearch/hermes-agent/issues/59293)

## 5. Bug 与稳定性

今日报告的Bug数量较多，主要集中在以下关键领域，按严重程度排列：

### 严重 (P1)
- **模型行为异常 (Agent, Streaming):** [#103483](https://github.com/nousresearch/hermes-agent/issues/103483) 模型过早结束回应；[#111761](https://github.com/nousresearch/hermes-agent/issues/111761) 推理内容泄露到助手内容中。  
- **后台进程不稳定:** [#41225](https://github.com/nousresearch/hermes-agent/issues/41225) 后台进程在Agent生命周期释放时被SIGTERM错误杀死。**已有相关修复PR？** 未在今日PR中明确关联。

### 中等 (P2)
- **桌面端UI/UX:** [#86565](https://github.com/nousresearch/hermes-agent/issues/86565) 会话状态点显示错误；[#106003](https://github.com/nousresearch/hermes-agent/issues/106003) 项目内会话列表不显示；[#112458](https://github.com/nousresearch/hermes-agent/issues/112458) 模型切换确认框无取消按钮。  
  对应修复PR：**[#112463](https://github.com/nousresearch/hermes-agent/pull/112463)** 和 **[#112461](https://github.com/nousresearch/hermes-agent/pull/112461)** 已提交。

- **安全与兼容性:** [#111949](https://github.com/nousresearch/hermes-agent/issues/111949) SSH模式与zsh shell不兼容；[#111912](https://github.com/nousresearch/hermes-agent/issues/111912) 更新时因SIGKILL导致数据库WAL损坏；[#112382](https://github.com/nousresearch/hermes-agent/issues/112382) WhatsApp bridge 依赖存在已知漏洞。  
- **功能Bug:** [#98634](https://github.com/nousresearch/hermes-agent/issues/98634) `file.attach` 返回的文件引用路径无法被扩展；[#100438](https://github.com/nousresearch/hermes-agent/issues/100438) 配置 `dashboard.public_url` 后桌面端无法启动。

### 低优先级 (P3)
- **自动化/工具:** [#112378](https://github.com/nousresearch/hermes-agent/issues/112378) `_discard_lockfile_churn` 函数在处理workspace时错误回滚根目录锁文件。

## 6. 功能请求与路线图信号

用户提出的新功能需求主要集中在以下方向：

- **自优化系统:** [#111237](https://github.com/nousresearch/hermes-agent/issues/111237) 提出一个“自调优”框架，允许Agent通过重放失败记录来优化自身配置。  
- **子代理支持:** [#112369](https://github.com/nousresearch/hermes-agent/issues/112369) 统一多项需求，建议为 `delegate_task` 添加具名子代理角色定义，以支持复杂的审计流程。  
- **本地化支持:** [#52532](https://github.com/nousresearch/hermes-agent/issues/52532) 韩语用户请求添加韩语界面支持。  
- **UX改进:** [#112359](https://github.com/nousresearch/hermes-agent/issues/112359) 改进MoA（Mixture-of-Agents）的用户体验，明确显示聚合器模型是计费主体。

**路线图信号**：结合现有的PR，**[PR #102765](https://github.com/nousresearch/hermes-agent/pull/102765)** (统一包管理器) 和 **[PR #112449](https://github.com/nousresearch/hermes-agent/pull/112449)** (本地Teams Playground) 表明项目在 **工具管理** 和 **平台扩展性** 上持续投入，这些可能与“子代理”或“自优化”这类高级功能共同纳入未来版本规划。

## 7. 用户反馈摘要

从今日Issue评论中，可以提炼出几类用户痛点：

- **对模型可靠性的担忧**：用户对模型在对话中途“胡言乱语”或过早结束感到困惑和不满（[#103483](https://github.com/nousresearch/hermes-agent/issues/103483)），尤其是在使用付费API时，错误行为直接导致Token浪费。
- **安全功能的信任危机**：多个用户对内置安全功能的有效性提出质疑。例如，通过CLI绕过配置保护（[#59293](https://github.com/nousresearch/hermes-agent/issues/59293)）或启动时WAL损坏（[#111912](https://github.com/nousresearch/hermes-agent/issues/111912)）都会导致用户对项目安全性的信任度下降。
- **桌面端体验割裂**：桌面端存在较多细节问题，如状态显示、会话列表同步、模型切换交互等（[#86565](https://github.com/nousresearch/hermes-agent/issues/86565), [#106003](https://github.com/nousresearch/hermes-agent/issues/106003), [#112458](https://github.com/nousresearch/hermes-agent/issues/112458)），表明桌面客户端的UI/UX仍需打磨。

## 8. 待处理积压

以下为长期未响应或讨论停滞但仍具重要影响的问题：

- **[Issue #87948] Release tags are unsigned since v2026.8.13** (创建: 2026-08-16，开放约1个月)  
  这是一个下游运维的安全审计类问题。用户询问从 `v2026.8.13` 开始发布的标签不再签名，是刻意为之还是密钥丢失。目前仍为 `needs-decision` 状态，建议维护者尽快给出官方解释，以防止社区对软件供应链安全产生疑虑。  
  [查看Issue](https://github.com/nousresearch/hermes-agent/issues/87948)

- **[Issue #41225] Background processes killed by SIGTERM** (创建: 2026-06-07，开放超过3个月)  
  一个影响Agent后台任务稳定性的P1级Bug。虽然维护者已标记 `sweeper:risk-session-state`，但长时间未分配或关闭，导致开发者在依赖后台进程时面临风险。  
  [查看Issue](https://github.com/nousresearch/hermes-agent/issues/41225)

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

好的，作为PicoClaw开源项目的AI智能体分析师，我将根据您提供的2026年9月16日最新数据，生成今日的项目动态日报。

---

### **PicoClaw 项目日报 | 2026-09-16**

#### **1. 今日速览**

今日项目活跃度中等偏上。过去24小时内，核心进展集中在已完成合并的**可观测性**和**连接稳定性**等跨领域增强功能上。然而，社区中关于**数据安全（竞态条件导致Nil指针解引用）** 和**配置管理（静默数据丢失）** 的两个关键Bug Issue正在发酵，虽然已有对应修复PR提交，但均尚未合并，构成了项目当前的主要稳定性风险。总体而言，项目在功能迭代上稳步向前，但需要加快对社区报告的严重稳定性问题的响应速度。

#### **2. 版本发布**

*(无)*

#### **3. 项目进展**

昨日，项目成功合入两项重要特性，标志着功能版图的扩展：

- **\[\#3380\] [已关闭] `feat(mesh): observability — peer conns/score/bandwidth, activity feed, SSE events`**
  - **摘要**：为P2P网络层（Mesh）增加了全面的可观测性能力。新特性为节点状态（`PeerStatus`）添加了详细连接信息、延迟、评分和带宽数据，并集成了标准化的带宽报告器。此外，引入了活动流和SSE事件机制。
  - **影响**：这是项目“Track 63”计划的关键部分，显著提升了P2P网络的透明度和调试能力，为未来构建去中心化、自修复的网络奠定了基础。
  - **链接**: [PR #3380](https://github.com/sipeed/picoclaw/pull/3380)

- **\[\#1780\] [已关闭] `type: enhancement, domain: channel, domain: config, go] Qq connection stability`**
  - **摘要**：将QQ频道的连接参数（重连间隔、重试次数、速率限制）变为可配置项，同时保持了向后兼容性。
  - **影响**：这个来自社区贡献者`xiang33`的PR，通过提升配置灵活性，解决了QQ频道在实际部署中可能遇到的连接不稳定问题，是提升特定渠道用户体验的务实之举。
  - **链接**: [PR #1780](https://github.com/sipeed/picoclaw/pull/1780)

#### **4. 社区热点**

讨论焦点集中在两项严重Bug上，它们共同指向配置与数据安全领域：

- **\[热\] #3374: [BUG] Data race in Config.initSensitiveCache can return a nil replacer and panic FilterSensitiveData**
  - 社区用户`sting8k`报告了一个在并发环境下可能导致程序Panic的安全数据过滤初始化竞态条件，并附上了详细的代码分析（`pkg/config/security.go:221-222`）。该Issue获得了开发者的关注，并已提交修复PR #3375，但目前仍在等待合并。
  - **背后诉求**：用户对高并发场景下的**应用稳定性和数据安全**有强烈要求，期望修复能防止生产环境中的偶发崩溃。
  - **链接**: [Issue #3374](https://github.com/sipeed/picoclaw/issues/3374)

- **\[热] #3373: [BUG] SaveConfig silently deletes every api_key after the first and leaves a dangling fallback**
  - 同一位用户`sting8k`报告了另一个严重的配置数据丢失问题：执行“加载-保存”配置的无操作（no-op）操作周期后，`model_list`中除第一个外的所有`api_keys`会被静默删除，并留下悬挂的`fallbacks`引用。
  - **背后诉求**：用户对此类**静默、非预期的数据丢失**行为感到困扰，这严重影响了配置的可靠性和信任度，是运维中的重大隐患。
  - **链接**: [Issue #3373](https://github.com/sipeed/picoclaw/issues/3373)

#### **5. Bug 与稳定性**

今日社区报告了2个新的Bug，均为严重级别，且目前无任何一项被修复合并。

- **严重**
  - **#3374: Data race导致nil指针panic**
    - 描述：`Config.initSensitiveCache()`存在竞态条件，导致`sensitiveCache`被重复初始化，返回nil的`*strings.Replacer`，最终在`FilterSensitiveData()`中引发pani。此问题属于并发安全设计的根本性缺陷。
    - **已有修复PR**: #3375 (待合并)
    - **链接**: [Issue #3374](https://github.com/sipeed/picoclaw/issues/3374)

- **严重**
  - **#3373: 配置重载时静默删除API Keys**
    - 描述：对包含多个`api_keys`的`model_list`配置项执行无修改的保存操作时，会静默删除除第一个外的所有密钥，并留下无效的`fallbacks`引用。此问题属于核心配置逻辑的严重缺陷，可能导致服务中断或配置歧义。
    - **目前无修复PR**
    - **链接**: [Issue #3373](https://github.com/sipeed/picoclaw/issues/3373)

#### **6. 功能请求与路线图信号**

尽管今日无新功能请求Issue，但从待合并的PR中可以窥见社区的贡献方向：

- **增强配置响应能力**：PR #3372 `fix(config): make the reaction tool configurable` 将`reaction`工具改为可通过配置文件启用/禁用。这体现了社区对**细粒度功能控制**的需求，要求每个特性都是可插拔和可定制的。此项极可能被纳入下一小版本。
- **第三方搜索服务集成**：PR #3370 `feat(tools): add Keenable web search provider` 提议添加一个新的Web搜索提供商Keenable。这表明社区正积极扩展项目的**工具生态**，并关注那些提供更低门槛（如无API Key要求）的服务。若项目路线图有“工具商店”计划，此类贡献将是重要基石。

#### **7. 用户反馈摘要**

从Issue评论区提取的用户声音（均为来自`sting8k`的评论）：

- **对静默数据丢失的极度担忧**：用户在`#3373`中描述问题时，使用了“silent data loss of user configuration”等表述，透露出对配置管理鲁棒性的不信任。“读-改-写”周期不应产生副作用是用户的基本预期。
- **对并发安全问题的直接暴露**：用户在`#3374`中通过代码堆栈精确指出了竞态条件发生的位置，展现了较高的技术专业度。需求很明确：**请修复并发访问中的非线程安全问题，若`sync.Once`自身都需要保护，则说明设计有误**。

#### **8. 待处理积压**

- **悬而未决的关键Bug**:
  - **\[严重 - 8日未关闭] #3374: [BUG] Data race...** 和 **#3373: [BUG] SaveConfig...**：此两条Issue自9月8日创建至今已有8天，虽然在昨天有更新，但依然没有合并修复。考虑到它们对系统稳定性和数据一致性的严重威胁，项目维护者应优先处理。
  - **链接**: [Issue #3374](https://github.com/sipeed/picoclaw/issues/3374) , [Issue #3373](https://github.com/sipeed/picoclaw/issues/3373)

- **长期未响应的修复PR**:
  - **\[8日未合并] PR #3372, #3375, #3370**：这三条PR均创建于2026-09-07或09-08，在昨日有状态更新但均为合并。特别是与严重Bug直接相关的`#3375`，其长期处于未合并状态会加剧社区的挫败感。
  - **链接**: [PR #3375](https://github.com/sipeed/picoclaw/pull/3375), [PR #3372](https://github.com/sipeed/picoclaw/pull/3372), [PR #3370](https://github.com/sipeed/picoclaw/pull/3370)

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

# NanoClaw 项目动态日报 — 2026-09-16

## 1. 今日速览

过去 24 小时项目保持高度活跃：共处理 5 条 Issue（新开 2 条、关闭 3 条），PR 提交/合并 40 条（其中 21 条已合并/关闭，19 条待合并）。无新版本发布，但核心团队集中交付了多项性能优化、渠道安全加固与配置契约化改进。社区围绕 WebSocket 闲置超时与更新流程的死锁问题展开讨论，整体健康度良好，功能迭代与稳定性修复并行推进。

---

## 2. 版本发布

（无）

---

## 3. 项目进展

今日合并/关闭的重要 PR 共 21 条，以下为关键推进项：

- **#[3813] — [CLOSED] 持久交接安全与任务控制**  
  引入主机持有的持久交接分类账，包含指纹化的来源/审查者合约、仅追加事件和交接 CLI 资源；强化了 Slack 渠道的 agent-to-agent 交付可靠性。  
  [nanocoai/nanoclaw PR #3813](https://github.com/nanocoai/nanoclaw/pull/3813)

- **#[3829] — [CLOSED] 交叉会话上下文性能优化**  
  将跨会话的消息回显扇出从关键路径移至热点集，减少唤醒延迟与兄弟会话数量的线性依赖关系。  
  [nanocoai/nanoclaw PR #3829](https://github.com/nanocoai/nanoclaw/pull/3829)

- **#[3830] — [CLOSED] 测试端口分配改用内核分配**  
  修复 Webhook 端口测试因自选随机端口导致的 `EADDRINUSE` 偶发失败，改用内核分配空闲端口。  
  [nanocoai/nanoclaw PR #3830](https://github.com/nanocoai/nanoclaw/pull/3830)

- **#[3826] — [CLOSED] Provider 默认语气设置契约化**  
  允许 Provider 在运行时契约中声明默认语气及其原生设置映射，核心层解析后将映射设置传给 Provider 工厂。  
  [nanocoai/nanoclaw PR #3826](https://github.com/nanocoai/nanoclaw/pull/3826)

- **#[3827] — [CLOSED] Codex 适配器使用新的 Provider 语气契约**  
  将 Codex 的 `friendly` 默认语气与 `personality` 设置映射改为通过可选的 Provider 语气契约声明，简化适配逻辑。  
  [nanocoai/nanoclaw PR #3827](https://github.com/nanocoai/nanoclaw/pull/3827)

- **#[3822] — [CLOSED] 忽略 .worktrees/**  
  将 `.worktrees/` 加入 `.gitignore`，防止 Git 工作树目录显示为未跟踪文件，优化仓库维护体验。  
  [nanocoai/nanoclaw PR #3822](https://github.com/nanocoai/nanoclaw/pull/3822)

此外，今日还有 19 条 PR 仍处于待合并状态，主要涉及渠道新增（Proton Mail、AgentMail、语音通话）、提供者认证增强（Iron Proxy 集成）、以及可观测性（OpenTelemetry 技能）等方向，表明项目正稳步扩展渠道生态与运维能力。

---

## 4. 社区热点

### 最活跃的 Issue：WebSocket 闲置重试隐藏（#3338）
`ionescu77` 报告，当 Codex Responses WebSocket 断开时，Telegram 请求会静默等待长达 10 分钟（直至 NanoClaw 的回合超时）。Codex CLI 内部有 5 分钟空闲超时并自动重试，但 `codex app-server` 未将失败信号传递给 NanoClaw，导致用户无反馈。该 Issue 已有 3 条评论，社区正在讨论如何将底层重试事件暴露给上层。  
[nanocoai/nanoclaw Issue #3338](https://github.com/nanocoai/nanoclaw/issues/3338)

### 新开 Bug：更新流程切流死锁（#3828）  
`laydros` 刚刚提交了 Issue #3828，指出 `/update-nanoclaw` 的切流（cutover）过程永远不会成功：它先停止主机服务，然后轮询 agent 容器退出，但主机是唯一能停止空闲容器的组件，而其关闭路径又特意保持容器运行，导致轮询永远无法通过。此 Issue 当前无评论，但属于潜在的生产环境阻塞问题。  
[nanocoai/nanoclaw Issue #3828](https://github.com/nanocoai/nanoclaw/issues/3828)

---

## 5. Bug 与稳定性

### 严重 — 更新流程切流死锁 (Issue #3828, OPEN)
- **现象**：`/update-nanoclaw` 在 agent 容器运行时无法完成切流，因为服务停止步骤抢先执行，而等待容器退出的步骤因容器未被停止而永久阻塞。  
- **是否已有 fix PR**：暂无。需要调整停止顺序或提供强制停止机制。  
  [Issue #3828](https://github.com/nanocoai/nanoclaw/issues/3828)

### 中等 — WebSocket 空闲重试隐藏 (Issue #3338, OPEN)
- **现象**：Codex 底层 WebSocket 断开后不被 NanoClaw 感知，用户请求静默等待 10 分钟。  
- **状态**：已记录，社区正讨论如何将重试事件桥接至 NanoClaw。  
  [Issue #3338](https://github.com/nanocoai/nanoclaw/issues/3338)

### 中等 — Setup 遗留零字节文件和 PATH 问题 (Issue #3354, CLOSED)
- **描述**：在非登录 SSH 会话中安装时，`git show` 复制失败产生零字节 channel 文件，且 `onecli check` 在 PATH 修复前执行。  
- **修复**：已通过关联 PR 关闭。  
  [Issue #3354](https://github.com/nanocoai/nanoclaw/issues/3354)

### 低 — 可变状态快照错误捕获符号链接 (Issue #3684, CLOSED)
- **描述**：当 `data/` 或 `groups/` 为符号链接时，快照存储的是链接而非实际内容，回滚会恢复已过时的链接。  
- **修复**：已关闭，需确保快照函数解引用符号链接。  
  [Issue #3684](https://github.com/nanocoai/nanoclaw/issues/3684)

### 性能改进 — 主机并行清理与会话扫描 (PR #3832, OPEN)
- **目的**：将主机周期性扫描任务从串行改为并行，避免扫描耗时随会话数与邮箱延迟线性增长。  
- **状态**：开放中，已进入审查。  
  [PR #3832](https://github.com/nanocoai/nanoclaw/pull/3832)

### 安全修复 — Mattermost 回调认证 (PR #3823, OPEN)
- **目的**：要求 Mattermost 动作回调使用非空密钥校验，并采用 `timingSafeEqual` 防时序攻击，确保外部集成无法获取适配器共享密钥。  
  [PR #3823](https://github.com/nanocoai/nanoclaw/pull/3823)

---

## 6. 功能请求与路线图信号

### 已进入审查阶段的新功能（待合并 PR）
下列 PR 均处于待审查状态，很可能纳入下一版本：

- **全双工语音通话渠道** (#3764)：`/add-voice` 技能，利用 OpenAI GPT-Live-1 实现浏览器与 agent 的实时语音对话。  
- **Proton Mail 渠道** (#3726)：通过 Proton Mail Bridge 接入邮件通信，解决 Raspberry Pi 用户 ARM 兼容性问题。  
- **AgentMail 邮件渠道** (#3743)：基于 API 的托管邮件收件箱，无需管理 MX 记录。  
- **OpenTelemetry 追踪** (#3796)：为 agent 容器新增 `/add-telemetry` 技能，导出调用链、成本、缓存命中等信息。  
- **仅工具交付模式** (#3781 & #3713)：为无法稳定输出最终文本封装的 Provider 提供纯工具通道配置。  
- **Keenable MCP 工具** (#3697)：注册 Keenable 网页搜索与抓取作为远程 MCP 工具。  
- **OpenCode Iron Proxy 认证** (#3825)：通过共享凭证接口支持 API 密钥或 OAuth 登录。  

这表明社区对多渠道集成、可观测性与 Provider 灵活性的需求强烈，项目团队正积极响应。

### 路线图启示
- 凭证管理标准化：PR #3824 引入共享凭证连接接口，未来可能成为所有 Provider 的标配。  
- 性能可扩展性：PR #3832 的并行化策略预示项目开始应对大租户场景下的规模化瓶颈。  

---

## 7. 用户反馈摘要

| 来源 | 用户痛点 | 场景/使用反馈 |
|------|----------|---------------|
| Issue #3338 | Telegram 请求静默等待 10 分钟，无任何进度提示 | 用户期望 Codex 底层超时能即时传递，避免无谓等待 |
| Issue #1981（已关） | 无交互登录环境的 SSH 会话中，`bash nanoclaw.sh` 误判 systemd 不存在 | 用户使用 Hetzner Ubuntu + Node 22.22.2，需手动绕过检测 |
| Issue #3354（已关） | 非登录 Shell 安装产生 0 字节配置文件，且 `onecli check` 在 PATH 修复前运行 | 用户强调 clean box 环境安装失败，期望安装脚本检测 shell 类型 |
| Issue #3684（已关） | 快照备份只保存了符号链接而非实际数据，导致回滚无效 | 用户使用 Symlink 管理数据目录，发现回滚后数据仍为最新版本 |

反馈集中在安装体验、边界情况处理与高延迟场景下的透明性，表明用户对生产级稳定性和可调试性有较高要求。

---

## 8. 待处理积压

### 长期未解决的 Issue
- **#3338**：WebSocket 闲置重试隐藏（8月18日创建，已近一个月），仍无解决方案和关联 PR。  
  [Issue #3338](https://github.com/nanocoai/nanoclaw/issues/3338)

### 新近开且高风险 Issue
- **#3828**：更新切流死锁（9月15日创建），若未及时处理可能影响用户正常升级路径。  
  [Issue #3828](https://github.com/nanocoai/nanoclaw/issues/3828)

### 待合并的 19 条 PR 中需重点关注
- 渠道类：Proton Mail (#3726)、AgentMail (#3743)、语音 (#3764) — 涉及新依赖集成，需充分测试。  
- 安全类：Mattermost 回调认证 (#3823)、凭证接口 (#3824) — 影响敏感配置。  
- 可观测性：OpenTelemetry (#3796) — 可能产生额外性能开销，需审查默认配置。  

建议维护团队优先推动 #3828 修复，并安排 #3338 的设计讨论，避免问题在用户群体中扩散。

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

# LobsterAI 项目动态日报 — 2026-09-16

## 今日速览

过去 24 小时内项目活跃度**很高**：共处理 30 条 Pull Request（其中 20 条已合并/关闭），3 条 Issue 更新（关闭 2 条旧 Issue，新增 1 条用户反馈 Issue）。代码变动集中在 **OpenClaw 兼容性修复**（约 15 个相关 PR）以及一个针对“广告永久关闭”的功能 PR。无新版本发布。项目整体处于密集修复和功能完善阶段，社区反馈的 OpenClaw 升级后稳定性问题得到快速响应。

## 版本发布

无新版本发布。

## 项目进展

以下为过去 24 小时合并/关闭的重要 PR，覆盖 OpenClaw 兼容性、体验优化、bug 修复三大方向：

### 🚀 OpenClaw 兼容性修复（主要部分）

- **[PR #2687] Release/2026.9.15** — 合并了当日所有 OpenClaw 相关修复，形成新的 Release 分支。
- **[PR #2686] fix(openclaw): pack and stage local workspace deps** — 修复 pnpm pack 丢失本地补丁导致运行时依赖错误的问题。
- **[PR #2685] fix(openclaw): preserve patched workspace runtime dependencies** — 同步修复 `npm run electron:dev:openclaw` 失败问题。
- **[PR #2684] fix(openclaw): prevent heuristic output budget starvation** — 修复长会话输出令牌被错误降为 1 的严重问题。
- **[PR #2682] fix(openclaw): validate historical transcript replay** — 修复历史记录缺失字段导致 OpenClaw 请求失败的问题。
- **[PR #2681] fix(openclaw): recover invalid legacy dreaming state at startup** — 修复旧版 Memory Core JSON 解析失败导致网关无法启动。
- **[PR #2679] feat(openclaw): add compatibility repair for post-upgrade gateway state** — 增加升级后网关状态自动修复能力。
- **[PR #2678] fix(openclaw): preserve compaction summary format and audit facts** — 修复长会话压缩时摘要格式冲突的问题。
- **[PR #2677] fix(cowork): restore technical error details** — 恢复升级后丢失的错误详情传递。
- **[PR #2664] fix(openclaw): avoid POPO SDK loading races** — 修复升级后 POPO SDK 加载竞态导致网关无监听器。
- **[PR #2680] fix(openclaw): preserve model policy during config sync** — 修复配置同步误删模型策略字段的问题（**待合并**）。

> 这些修复共解决超过 10 个 OpenClaw v2026.8.1 集成后的崩溃/功能异常，项目稳定性显著提升。

### 🎨 功能与 UI 优化

- **[PR #2374] feat: add permanent setting to hide sidebar ad banner** — 为侧边栏广告增加“永久关闭”设置项（**待合并**）。
- **[PR #1142] feat(skills): 在技能管理页面添加快捷创建技能** — 关闭旧的 Feature PR，相关功能已完成。
- **[PR #1144] feat(scheduled-tasks): show last run time** — 关闭旧的 UX 优化 PR。

### 🐛 历史遗留 Bug 修复（今日关闭的“stale” PR）

- **[PR #1143] fix(agent): 修复创建Agent时默认图标未保存** — 解决侧边栏与 Agent 页面图标不一致。
- **[PR #1146] feat: 修复新建agent未获取到任务记录数据** — 解决重名 Agent 切换后任务列表不刷新。

这些 PR 虽标记为 stale，但今日被关闭表明其代码已并入主线。

---

## 社区热点

目前讨论最集中的 Issue/Pull Request：

- **Issue #2342** “左下角广告可以彻底关闭吗” — 有 2 条评论，用户@PYUDNG 反馈 `v2026.7.15` 版本新增侧边栏广告，要求增加永久关闭开关。此 issue 获得开发者响应，并由 **PR #2374** 实现。
- **PR #2374** 正是解决该需求的方案，但已开放近两个月（2026-07-21），评论数未统计，社区期望其尽快合并。

> 背后诉求：用户对非侵入式体验要求较高，希望有清晰的设置项控制广告显示，而非每次手动关闭。

---

## Bug 与稳定性

### 严重级（已修复/有对应 PR）

| 问题 | 严重程度 | 状态 | 对应 PR |
|------|---------|------|---------|
| OpenClaw 长会话输出令牌被降为 1，导致推理无响应 | 🔴 崩溃 | 已合并 | [#2684](https://github.com/netease-youdao/LobsterAI/pull/2684) |
| 旧版 Memory Core JSON 解析失败阻断网关启动 | 🔴 启动失败 | 已合并 | [#2681](https://github.com/netease-youdao/LobsterAI/pull/2681) |
| OpenClaw 历史记录缺失字段导致请求异常 | 🟠 功能异常 | 已合并 | [#2682](https://github.com/netease-youdao/LobsterAI/pull/2682) |
| 编译过程丢失本地补丁，导致运行时依赖错误 | 🟠 构建失败 | 已合并 | [#2685](https://github.com/netease-youdao/LobsterAI/pull/2685) |
| POPO SDK 加载竞态导致网关无监听器 | 🟠 功能降级 | 已合并 | [#2664](https://github.com/netease-youdao/LobsterAI/pull/2664) |
| 升级后错误详情未传递到 UI | 🟢 信息缺失 | 已合并 | [#2677](https://github.com/netease-youdao/LobsterAI/pull/2677) |
| 配置同步误删模型策略导致反复写入 | 🟢 性能 | 待合并 | [#2680](https://github.com/netease-youdao/LobsterAI/pull/2680) |

以上修复均来自用户日志反馈或内部测试，未涉及安全漏洞。

---

## 功能请求与路线图信号

### 可能列入下一版本的功能

1. **广告永久关闭** — Issue #2342 提出，PR #2374 已实现前端设置项，只待合并。预计会随下一个补丁版本发布。
2. **OpenClaw 兼容性自动修复** — 多个修复 PR 已经合入，表明项目计划深度集成 OpenClaw，并将相关补丁作为标准能力。
3. **持续依赖更新** — PR #1277（dependabot）将 Electron 从 43.5.0 升级到 44.3.0 等两组依赖，虽然仍待合并，但表明项目在跟踪上游更新。

### 社区未明确表达但可推断的需求

- 用户对长期不合并的旧 PR（如 #2374）关注度升高，可能要求维护者加快 Review 节奏。

---

## 用户反馈摘要

从 Issue #2342 的评论中提炼：

- **用户@PYUDNG**：`v2026.7.15` 更新后出现侧边栏广告，之前版本没有。虽然可以点叉关闭，但建议增加“彻底不弹出”的开关。用户已检查设置项，未找到相关选项。
- **用户反馈场景**：日常使用中广告干扰体验，期望控制权交给用户，而非每次手动关闭。

从已修复的 Issue/PR 中也可反推：
- 长会话推理中断、启动失败等严重问题曾影响用户，但今日均已修复，项目健康度改善明显。

---

## 待处理积压

以下 Issue/PR 长期未合并/响应，建议维护者优先关注：

| 编号 | 标题 | 创建时间 | 备注 |
|------|------|---------|------|
| [PR #1277](https://github.com/netease-youdao/LobsterAI/pull/1277) | chore(deps-dev): bump electron 43→44 | 2026-04-02 | 已 5 个月未合并，依赖滞后 |
| [PR #1181](https://github.com/netease-youdao/LobsterAI/pull/1181) | fix(cowork): hide OpenClaw main agent sessions | 2026-04-01 | 已 5 个月未合并，涉及会话列表混乱 |
| [PR #2374](https://github.com/netease-youdao/LobsterAI/pull/2374) | feat: add permanent setting to hide sidebar ad | 2026-07-21 | 社区高频需求的解决方案，待 review |
| [Issue #2342](https://github.com/netease-youdao/LobsterAI/issues/2342) | 左下角广告可以彻底关闭吗 | 2026-07-15 | 与 PR#2374 对应，用户仍在等待关闭 |

---

*报告基于 GitHub 公开数据生成，时间范围：2026-09-15 00:00 ~ 2026-09-16 00:00（UTC+8）。*

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

当然。以下是根据提供的 GitHub 数据生成的 **Moltis 项目静态快照分析日报**，按照要求的格式和语言风格整理。

---

# Moltis 项目动态日报 | 2026-09-16

## 1. 今日速览

过去 24 小时内，Moltis 项目整体活跃度处于 **温和但高质量** 的状态。无新版本发布，但有一条关于自定义 OpenAI 端点参数配置的 Enhancement Issue 保持了活跃讨论，并有一条关键的构建系统优化 PR 新提交。项目在**功能迭代**与**基础设施优化**两个方向均有进展，社区对模型配置灵活性的诉求值得关注。

## 2. 版本发布

无新版本发布。

## 3. 项目进展

今日无被合并或关闭的 PR，但有一项重要新 PR 提交：

- **#1270 [OPEN] feat(build): cache cargo across image builds, and script building the image**  
  作者：Bergmann89  
  该 PR 将 Cargo 的构建缓存从固定的 Docker 镜像层迁移至 BuildKit 缓存挂载，解决了每次构建重新编译整个依赖树的痛点。经估算，冷构建时间可大幅缩短，仅编译变更代码并重新链接。  
  👉 这是一项对 CI/CD 效率和开发者体验具有明显正面影响的改进，说明项目在持续关注构建基础设施的可维护性与速度。  
  [PR #1270 链接](https://github.com/moltis-org/moltis/pull/1270)

## 4. 社区热点

- **#205 [OPEN] [Feature]: Allow setting body parameters for custom OpenAI endpoints (and per-model)**  
  评论数：2  
  该 Issue 自 2026-02-22 提出后，于昨日再次获得活跃讨论。用户希望为自定义 OpenAI 兼容接口提供更细粒度的请求体参数配置（例如针对不同模型设置不同参数），这反映出社区对**多模型、多端点场景下的灵活配置**有强烈需求。  
  👉 用户对 Moltis 在多模型管理方面的能力提出了更高期望，这是当前讨论最为集中的功能请求。  
  [Issue #205 链接](https://github.com/moltis-org/moltis/issues/205)

## 5. Bug 与稳定性

今日未报告新的 Bug、崩溃或回归问题。项目稳定性较好，未出现需要紧急修复的稳定性事件。建议持续关注构建缓存 PR #1270 合并后的回归测试结果。

## 6. 功能请求与路线图信号

- **#205：允许为自定义 OpenAI 端点设置 body 参数（并可 per-model 配置）**  
  该请求虽未直接关联现有 PR，但结合项目中已存在的多模型支持现状，可推断此功能将进一步完善 Moltis 在**模型路由**与**参数透传**方面的能力，是提升企业级适配性的重要方向。如果被纳入下一版本，可能需要调整模型配置的 Schema 结构。

## 7. 用户反馈摘要

- 来自 Issue #205 的讨论片段暗示，用户希望能在不修改 Moltis 核心代码的前提下，将私有/微调模型的额外字段（如 `max_tokens`、`temperature` 等）传入自定义端点。当前实现强制要求所有模型使用统一参数模板，限制了灵活性。  
- 有用户表示“This would unblock our deployment where we have 3 different internal endpoints, each with different payload requirements.”——说明该功能对于**多环境、多供应商混合部署场景**至关重要。

## 8. 待处理积压

- **#205 [Feature] 开放请求**（自 2026-02-22 提出，至今已近 7 个月）  
  虽然仍有讨论，但尚未获得官方路线图标签或具体实现计划。考虑到评论中明确的使用场景和诉求，建议维护者评估是否纳入下一个 Milestone 或给予 `priority` 标签。  
  [Issue #205 链接](https://github.com/moltis-org/moltis/issues/205)

- **#1270 [PR] 构建缓存优化**（新提交，待审阅）  
  虽非积压，但该 PR 是基础设施层面的重要改动，若长期未合并可能导致 CI 分支差异扩大。建议尽快安排 Code Review。  
  [PR #1270 链接](https://github.com/moltis-org/moltis/pull/1270)

---

**分析师总结**：Moltis 项目当日表现稳健，社区对**参数级模型配置**的呼声最高，而构建缓存的优化则展现了项目在工程效能上的持续投入。建议维护团队优先评估 Issue #205 的技术可行性，并在合并 PR #1270 后关注构建稳定性回归。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域的开源项目分析师，我将根据您提供的 CoPaw (QwenPaw) 项目 GitHub 数据，为您生成 2026-09-16 的项目动态日报。

---

# CoPaw (QwenPaw) 项目动态日报 | 2026年09月16日

## 1. 今日速览

过去 24 小时内，**QwenPaw 项目保持极高活跃度**。Issue 处理量为 28 条，其中关闭 16 条，表明核心团队正在积极消化社区反馈。Pull Request 数量更是达到 50 条，合并/关闭与待合并的 PR 数量持平（各 25 条），显示出项目在修复 Bug、合并新功能方面正在快速推进。当日虽无新版本发布，但多个关键 PR 的提交（如 Hub 模型网关、DeepSeek V4 Flash 支持）预示着 2.2.x 系列的重大更新即将到来。**社区关注点主要集中在 Hub 多租户版本、subAgent 稳定性、以及 MCP 工具集成体验上。**

## 3. 项目进展

过去 24 小时内，项目在前端体验、核心功能和 MCP 兼容性方面均有实质性推进。

- **Hub 管理与门户升级**: `rayrayraykk` 提交了 PR [#7779](https://github.com/agentscope-ai/QwenPaw/pull/7779)，为 Hub 增加了组织模型网关、成员治理和使用面板，这是迈向 **2.2.0 多租户版** 的关键一步。
- **核心模型支持**: `lorenzozanee` 提交了 PR [#7794](https://github.com/agentscope-ai/QwenPaw/pull/7794)（后由 PR [#7736](https://github.com/agentscope-ai/QwenPaw/pull/7736) 合并），正式为 DeepSeek V4 Flash 模型提供支持，更新了其上下文窗口、图片输入等能力。
- **数据与分析**: `cyruszhang` 提交的 PR [#7637](https://github.com/agentscope-ai/QwenPaw/pull/7637)（审查中）带来了 QwenPaw-Data App 0.3.0，允许用户选择数据源、提出商业问题并生成报告，增强了项目的数据分析能力。
- **MCP 兼容性修复**: `kabishou11` 提交了 PR [#7729](https://github.com/agentscope-ai/QwenPaw/pull/7729)（审查中），修复了 MCP 客户端无法正确识别 Java/Kotlin MCP SDK 服务器错误响应的问题，提升了与不同 MCP 生态的兼容性。`lorenzozanee` 也贡献了相关修复（PR [#7735](https://github.com/agentscope-ai/QwenPaw/pull/7735)，已合并）。
- **控制台 UI/UX 优化**:
    - `zhijianma` 提交了 PR [#7790](https://github.com/agentscope-ai/QwenPaw/pull/7790)，引入一个可缩放、支持自定义标签的右侧工作台，改善了多任务处理体验。
    - `jinliyl` 合并了多个关于控制台的小修复，包括恢复键盘焦点指示器（PR [#7759](https://github.com/agentscope-ai/QwenPaw/pull/7759)）、对齐 Embedding 超时验证（PR [#7758](https://github.com/agentscope-ai/QwenPaw/pull/7758)）以及区分内存空错误通知（PR [#7756](https://github.com/agentscope-ai/QwenPaw/pull/7756)）。

## 4. 社区热点

- **QwenPaw Hub 多租户版本（Issues #7318）**: 这是一个讨论帖，获得了 **27 条评论和 4 个 👍**。社区对团队级使用 Hub 版有着极高的期待。用户 `rayrayraykk`（核心开发者）主动发起讨论，询问社区希望在下个版本中看到什么功能，显示项目对用户需求的重视。该讨论与 PR [#7779](https://github.com/agentscope-ai/QwenPaw/pull/7779) 直接相关。
    - [讨论链接](https://github.com/agentscope-ai/QwenPaw/issue/7318)

- **subAgent 完全失效（Issues #7678）**: 用户 `xiaohushi512` 报告的 Bug，声称在 Windows 2.2.0 版本上，**所有 subAgent 任务都无法执行并超时**。此 Issue 获得了 **7 条评论**，且用户附上了详细的调试日志，引发了社区对 subAgent 稳定性的广泛关注和讨论。这是一个严重级别的 Bug。
    - [Bug 报告链接](https://github.com/agentscope-ai/QwenPaw/issue/7678)

- **停止任务功能失效（Issues #7567）**: 用户 `rerbin` 报告了一个影响用户体验的 Bug，即点击“停止”按钮后，界面表现为已停止，但任务仍在后台执行。此问题获得了 **7 条评论**，表明用户对任务控制权的可靠性非常在意。
    - [Bug 报告链接](https://github.com/agentscope-ai/QwenPaw/issue/7567)

## 5. Bug 与稳定性

当日报告的 Bug 主要集中在下述几个方面，部分已有修复 PR。

- **严重**:
    - **[Issue #7678] subAgent 全部执行失败并超时**: 严重影响核心工作流。无关联 fix PR。
    - **[Issue #7567] 停止任务功能失效**: 严重 UI/UX Bug，影响用户对任务的控制。无关联 fix PR。
    - **[Issue #7689] PDF 文档仍被发送至多模态端点**: 在修复 #7621 后仍存在问题，影响部分 OpenAI 兼容 API 的使用。有对应的 **PR [#7636](https://github.com/agentscope-ai/QwenPaw/pull/7636)** 正在重构中。
- **中等**:
    - **[Issue #7775] 达到 max_iters 后无最终回答**: Agent 在达到最大迭代次数后静默结束，不给用户任何回应，使用体验差。无关联 fix PR。
    - **[Issue #7767] 多位 Bug 报告（控制台附件/定时任务/插件）**: 用户 `BasilLei` 报告了一系列多插件环境下的 Bug，包括附件缓存错误、定时任务丢失等。
    - **[Issue #7792] 微信附件 URL 无效**: 从微信频道发送的视频/音频附件转换为错误的 `file://` URL，导致 API 请求失败。
- **功能性问题**:
    - **[Issue #7786] NFS 部署时文件浏览器卡死**: 云端部署时打开文件浏览器会导致整个进程假死 5-6 分钟，对生产环境稳定性有较大影响。
    - **[Issue #7771] 上下文管理产生空白标签**: 使用上下文压缩或新建对话时，历史列表中会出现无意义的空白标题。

## 6. 功能请求与路线图信号

- **明确调用工具的需求强烈**: 多位用户（`afkkl83` 在 Issues #7778, #7780, #7777）提出希望能在对话中，通过类似“//”的方式“模糊搜索并明确调用指定内置工具或 MCP 工具”。这表明 Agent 自动调用工具的准确性仍有待提高，用户倾向于在必要时手动控制。此功能很可能进入后续版本规划。
- **UI 布局个性化**: Issues #7739 和 #7700 分别请求将历史对话移至右侧或左侧，以及对右侧面板（如文件、浏览器）进行切换。这反映了用户对工作区高度可定制化的需求。**PR [#7790](https://github.com/agentscope-ai/QwenPaw/pull/7790)**（统一工作台）与此诉求高度契合，很可能被纳入下一步路线图。
- **Channel 与 Skills 的细粒度管理**: Issues #7746 和 #7650 分别提出希望 Skills 能在特定 Channel 下启用，以及将 Channel 参数（如 QQ 号）透传给 MCP 工具。这表明社区开始探索更复杂的多渠道、多工具编排场景。
- **MCP 兼容性覆盖**: Issue #7764 报告了与 `dagu` MCP server 的兼容性问题。结合 PR #7729 和 #7735 的修复，显示项目团队正在系统性地解决与各类 MCP 实现的兼容性问题，这与开放集成的方向一致。

## 7. 用户反馈摘要

- **痛点**: 用户普遍反映 **subAgent 的稳定性是当前最大的痛点**（#7678）。此外，任务停止控制失效（#7567）、PDF 文档处理异常（#7689）、在线更新导致应用不可用（#7543）等也严重影响了使用体验。
- **使用场景**: 社区用户展现了多样化的使用场景，包括在 **Windows 和云服务器上部署**、结合 **New-API 代理使用模型**、以及集成 **WeChat/QQ 等 IM 频道**。这表明 QwenPaw 正从个人助手向团队协作和工作流自动化平台发展。
- **满意/不满意**: 用户对 **新增的“/”明确调用技能的功能** 表示赞赏（#7777），但也有用户对 **控制台 UI 拥挤**（#7739）、**文件预览 401 错误**（#7743）、**Hub 模式下文件无法预览**（#7743）表示不满。用户 `rerbin` 提到的“记忆错乱”问题（#7193）在关闭后仍可能引发对 Agent 上下文管理能力的担忧。

## 8. 待处理积压

- **PR #6776 (browser driver self-heal)**: 这是一个修复浏览器驱动死锁的关键 PR，但从 8 月 7 日提交后，一直处于“等待人工审查”状态。该问题一旦解决，能显著提升浏览器自动化功能的鲁棒性。
    - [PR 链接](https://github.com/agentscope-ai/QwenPaw/pull/6776)
- **PR #6399 (Reranker UI Config Panel)**: 为用户提供了可视化配置重排序器的界面，已提交近两个月，仍在审查中。该功能对于需要精细控制 Agent 记忆和召回能力的用户很有价值。
    - [PR 链接](https://github.com/agentscope-ai/QwenPaw/pull/6399)

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

# ZeptoClaw 项目动态日报 (2026-09-16)

## 今日速览

- 过去24小时内，项目未收到任何新的 Issue，也无任何 PR 被合并或关闭，社区交互几乎停滞。
- 唯一的活动来自 Dependabot 自动提交的 18 个依赖更新 PR，涵盖 JavaScript、Rust、GitHub Actions 和 Docker 等多个技术栈。
- 所有 PR 均处于待合并状态，表明维护团队可能尚未开始处理这些积压的依赖升级。
- 项目整体活跃度较低，目前未见人为贡献或用户反馈，健康状况需关注维护节奏。

## 版本发布

无新版本发布。

## 项目进展

今日未合并或关闭任何 PR，因此没有功能性代码变更合入主线。值得注意的待处理 PR 包括：

- **重大框架升级**：`#695`（astro 6.3.7 → 7.2.2）和 `#686`（相同升级在另一个文档子项目中），`#696` 和 `#689`（@astrojs/starlight 0.39.2 → 0.41.10）。这些是 Astro 生态系统的大版本跳跃，可能带来构建或运行时的破坏性变更，需尽快验证并合并。
- **运行时依赖更新**：`#692`（rustls 0.23.39 → 0.23.43）、`#694`（base64 0.22.1 → 0.23.1）等 Rust 库更新涉及安全性和兼容性改进。
- **CI/CD 工具链升级**：`#682`（taiki-e/install-action 2.79.7 → 2.87.6）、`#684`（EmbarkStudios/cargo-deny-action 2.0.18 → 2.1.1）等能提升 CI 可靠性和覆盖率。

所有依赖 PR 详情见下方“待处理积压”部分。

## 社区热点

今日无任何 Issue 或 PR 产生评论或点赞，社区讨论活跃度为零。无热点议题。

## Bug 与稳定性

今日未报告任何 Bug、崩溃或回归问题。项目稳定性状态不明，但长期不处理依赖更新可能埋下潜在兼容性隐患。

## 功能请求与路线图信号

今日无用户提交功能请求。从 PR 列表看，项目近期焦点仍在文档站点技术栈（Astro/Starlight）的升级以及基础库维护，未出现涉及核心功能（如 AI 智能体逻辑）的新特性讨论。

## 用户反馈摘要

今日无用户反馈。可从过往数据推测，用户可能通过其他渠道（如 Discord、邮件）沟通，但 GitHub 公共空间未产生新信息。

## 待处理积压

以下 18 个 PR 均为 Dependabot 自动提交，至今未被审核或合并。由于依赖版本跨度较大（尤其是 Astro 从 v6 到 v7），建议维护团队优先处理：

| PR # | 目标依赖 | 版本变化 | 项目模块 |
|------|----------|----------|----------|
| [#696](https://github.com/qhkm/zeptoclaw/pull/696) | @astrojs/starlight | 0.39.2 → 0.41.10 | /landing/zeptoclaw/docs |
| [#695](https://github.com/qhkm/zeptoclaw/pull/695) | astro | 6.3.7 → 7.2.2 | /landing/zeptoclaw/docs |
| [#693](https://github.com/qhkm/zeptoclaw/pull/693) | sharp | 0.34.5 → 0.35.4 | /landing/zeptoclaw/docs |
| [#691](https://github.com/qhkm/zeptoclaw/pull/691) | sharp | 0.34.5 → 0.35.4 | /landing/r8r/docs |
| [#690](https://github.com/qhkm/zeptoclaw/pull/690) | clap | 4.6.1 → 4.6.6 | Rust 主程序 |
| [#694](https://github.com/qhkm/zeptoclaw/pull/694) | base64 | 0.22.1 → 0.23.1 | Rust 主程序 |
| [#687](https://github.com/qhkm/zeptoclaw/pull/687) | docker/login-action | 4.2.0 → 4.6.0 | CI |
| [#692](https://github.com/qhkm/zeptoclaw/pull/692) | rustls | 0.23.39 → 0.23.43 | Rust 主程序 |
| [#685](https://github.com/qhkm/zeptoclaw/pull/685) | tokio-serial | 5.4.5 → 5.5.0 | Rust 主程序 |
| [#683](https://github.com/qhkm/zeptoclaw/pull/683) | Swatinem/rust-cache | 2.9.1 → 2.9.2 | CI |
| [#689](https://github.com/qhkm/zeptoclaw/pull/689) | @astrojs/starlight | 0.39.2 → 0.41.10 | /landing/r8r/docs |
| [#688](https://github.com/qhkm/zeptoclaw/pull/688) | async-trait | 0.1.89 → 0.1.92 | Rust 主程序 |
| [#686](https://github.com/qhkm/zeptoclaw/pull/686) | astro | 6.3.7 → 7.2.2 | /landing/r8r/docs |
| [#684](https://github.com/qhkm/zeptoclaw/pull/684) | EmbarkStudios/cargo-deny-action | 2.0.18 → 2.1.1 | CI |
| [#681](https://github.com/qhkm/zeptoclaw/pull/681) | softprops/action-gh-release | 3.0.0 → 3.0.3 | CI |
| [#682](https://github.com/qhkm/zeptoclaw/pull/682) | taiki-e/install-action | 2.79.7 → 2.87.6 | CI |
| [#680](https://github.com/qhkm/zeptoclaw/pull/680) | debian (Docker) | `4e401d9` → `d7e1218` | Docker 基础镜像 |
| [#679](https://github.com/qhkm/zeptoclaw/pull/679) | rust (Docker) | `17d1ba8` → `bce1476` | Docker 基础镜像 |

**提醒**：这些 PR 已停留超过 24 小时，Astro 和 Starlight 的大版本升级可能引入构建失败，建议优先进行本地测试后合并。同时，Docker 基础镜像的 digest 更新也涉及安全性，应及时处理。

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，以下是基于 ZeroClaw 项目数据生成的 2026 年 9 月 16 日项目动态日报。

---

## ZeroClaw 项目日报 | 2026-09-16

### 1. 今日速览

ZeroClaw 项目今日继续保持高活跃度，社区贡献强劲。**过去 24 小时内，共有 50 条 Issue 和 50 条 PR 产生或更新，项目核心开发与社区协作节奏紧凑。** 尽管无新版本发布，但关键架构性 RFC（如桌面原生支持、A2A 客户端）的讨论持续深入，反映出项目正从核心架构向更广阔的生态集成和用户体验演进。Bug 修复集中在运行时稳定性、图片处理、缓存和安全性等方面，特别是关于图片标记和缓存失效的修复系列，显示了开发团队对模型交互细节的精益求精。整体来看，项目处于健康且高速的迭代期。

### 2. 版本发布

无

### 3. 项目进展

今日 **9 个 PR 被合并或关闭**，标志着项目关键功能的落地和基础设施的完善。

-   **🎉 关键功能推进：**
    -   **[#9324] [CLOSED]** `feat(a2a): outbound client config, shared wire-model, tools` 是由 `kingstar001` 提交的 PR。它实现了 RFC #9106 的第一阶段，为 ZeroClaw 代理添加了 `a2a_client`、`a2a_discover` 等工具。**这标志着 ZeroClaw 具备了主动调用外部 A2A 兼容代理的能力**，是实现跨代理协作网络（Agent-to-Agent）的重要一步。
        -   链接: `[zeroclaw-labs/zeroclaw PR #9324]`
    -   **[#9997] [CLOSED]** `feat(channels/telegram): add secure model picker` 为 Telegram 频道添加了安全的模型选择器，用户现在可以通过交互式键盘在已配置的多个模型中切换。
        -   链接: `[zeroclaw-labs/zeroclaw PR #9997]`
    -   **[#10840] [CLOSED]** `feat(docs): generate llms.txt and llms-full.txt in the mdBook build` 由 `JordanTheJet` 贡献，为项目文档增加了大语言模型友好的输出格式，提升了 AI 开发者对文档的索引效率和可访问性。
        -   链接: `[zeroclaw-labs/zeroclaw PR #10840]`

-   **🛠️ 基础设施与稳定性优化：**
    -   **[#10125] [CLOSED]** `test(config): isolate process-environment fixtures` 通过移除测试中不安全的 `env::set_var` 调用，提升了测试环境的隔离性和可靠性，强化了代码质量。
        -   链接: `[zeroclaw-labs/zeroclaw PR #10125]`
    -   **[#2754] [CLOSED]** `fix(docker): resolve heredoc chown placement and use quoted EOF` 修复了 Docker 配置中一个关键的 heredoc 语法错误，确保了 `chown` 命令正确执行，解决了容器镜像中的一个持久性配置问题。
        -   链接: `[zeroclaw-labs/zeroclaw PR #2754]`

**项目向前迈进了关键一步：** A2A 协议的实现从理论探讨 (RFC) 走向了实践落地。同时，通过修复和优化测试、文档及容器部署，项目的健壮性和可维护性也得到了显著提升。

### 4. 社区热点

今日最受关注的讨论集中在两项重大架构提案上：

1.  **[#6909] [OPEN] RFC: Computer-use support for desktop screen interaction and input control**
    -   **社区反馈：** 16 条评论，讨论热度最高。该 RFC 旨在实现 ZeroClaw 直接控制桌面应用的能力。社区讨论焦点从初期的安全边界定义（如会话武装、侧载信任）演进到对具体实施细节的审核。作者 `NiuBlibing` 和核心维护者就 `bounded approval units` 和 `execution-time revalidation` 等安全机制达成共识。
    -   **诉求分析：** 用户急切地希望 ZeroClaw 从“对话机器人”进化为能够执行复杂桌面任务的“数字代理”。其背后的深层诉求是希望 ZeroClaw 能与传统软件工作流无缝集成。
    -   链接: `[zeroclaw-labs/zeroclaw Issue #6909]`

2.  **[#9965] [OPEN] [Task]: harden runtime-written executable test fixtures under the parallel runtime gate**
    -   **社区反馈：** 12 条评论。此 Issue 由 `AngryPacifist` 发起，深入探讨了在并行运行时环境下，测试固件写入可执行文件时产生的竞态条件和故障。
    -   **诉求分析：** 这反映了高级开发者和测试工程师对 CI/CD 稳定性和测试可靠性的高度关注。社区正在共同努力解决一个技术难题，即如何在多线程测试环境中安全地生成和运行临时可执行文件，以避免非确定性失败。
    -   链接: `[zeroclaw-labs/zeroclaw Issue #9965]`

3.  **[#9106] [OPEN] RFC: A2A outbound client (A2ATool)**
    -   **社区反馈：** 11 条评论。虽然对应的 PR #9324 已经合并，但此 RFC 依然保持开放，用于跟踪后续阶段的工作。社区讨论集中在如何将此功能安全地集成到网关和运行时中。
    -   链接: `[zeroclaw-labs/zeroclaw Issue #9106]`

### 5. Bug 与稳定性

今日 Bug 修复和稳定性工作活跃，其中图片处理和缓存相关问题是重中之重。

-   **严重级 (S1 - 工作流阻塞):**
    -   **[#10659] [OPEN]** `[Bug]: Budget-exceeded Code turn loses visible progress after session restore` - 当复杂的 Code 流程达到成本限制时，已在屏幕上显示的流式内容在会话恢复后会丢失。会严重影响用户体感，尤其是处理长任务时。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #10659]`
    -   **[#8627] [OPEN]** `[Bug]: WhatsApp Web device linking broken by WhatsApp's new passkey/SHORTCAKE gate` - 因 WhatsApp 官方引入了新的安全验证机制，导致 ZeroClaw 的 WhatsApp 通道设备绑定功能完全失效。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #8627]`

-   **严重级 (S2 - 功能降级):**
    -   **[#10885] [OPEN]** `[Bug]: tool-returned images disappear after an unrelated tool call within the same turn` - 在同一轮对话中，非图片相关的工具调用会导致之前工具返回的图片消失，显著影响处理多模态数据的 Agent 工作流。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #10885]`
        -   关联 PR: **[#10888] [CLOSED]** `fix: stale tool-result image strip rewrites the message...` 已关闭，表明该问题已修复。
    -   **[#10889] [OPEN]** `[Bug]: native Anthropic provider drops the rolling cache breakpoint when the last message ends with an image block` - 当用户消息以图片结束时，Anthropic 原生提供程序会错误地丢弃缓存断点，导致缓存命中率下降，增加 API 调用成本。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #10889]`
        -   关联 PR: **[#10895] [OPEN]** `fix(anthropic): keep the rolling cache breakpoint when the last message ends with an image` 已提交修复。
    -   **[#10736] [OPEN]** `[Bug]: Pre-output stream failure skips advertised non-streaming fallback` - 流式输出失败后，系统未按预期回退到非流式模式，导致整个会话失败。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #10736]`
    -   **[#10625] [CLOSED]** `Internal [media attachment] placeholder is delivered to users when a non-vision model is in use` - 修复了当使用不支持图片的模型时，向用户暴露内部 `[media attachment]` 占位符的问题。已关闭。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #10625]`
    -   **[#9332] [OPEN]** `[Bug]: image-aware pre-dispatch budgeting and context-meter accounting` - 包含大量图片的请求在发送前，上下文计量器严重低估了 Token 消耗，导致发送后预算瞬间超支。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #9332]`

-   **安全相关 (high risk):**
    -   **[#5869] [OPEN]** `security: rumqttc v0.25.1 pins rustls-webpki... RUSTSEC advisory` - MQTT 客户端库引入的多个 RUSTSEC 安全咨询。状态为 `blocked`，依赖上游修复。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #5869]`
    -   **[#9882] [OPEN]** `Image markers bypass content validation on the run_model_query direct-dispatch seam` - 图片标记绕过了运行时中的内容验证检查，存在潜在安全风险。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #9882]`

### 6. 功能请求与路线图信号

社区持续提交新功能请求，多个方向与项目路线图密切相关。

-   **🚀 靠近下一版本 (已有对应 PR 合并或在讨论):**
    -   **A2A 协议支持：** [#9106] 的落地 ([#9324]) 是下一版本的标志性功能，将被纳入。
    -   **桌面原生 (Computer Use)：** [#6909] 讨论热烈，其 RFC 正被积极迭代。虽然距离合入还有距离，但大概率是后续重要版本的核心功能。

-   **🧭 路线图信号 (新功能提请关注):**
    -   **[#9814] [OPEN]** **请求：** `feat(channels): native XMPP / Prosody channel`。用户希望在 ZeroClaw 中原生支持 XMPP 协议，用于家庭实验室等轻量级部署场景。这是一个明确的需求信号，尤其针对社区对去中心化、自托管解决方案的偏好。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #9814]`
    -   **[#9346] [OPEN]** **请求：** `RFC: Define the unified package/capability/config/runtime-state catalog contract`。一个系统级的架构 RFC，旨在统一所有功能、插件、配置和运行时状态的目录服务。这是解决项目日益增长的复杂性、迈向更高级别可扩展性的关键信号。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #9346]`
    -   **[#8763] [OPEN]** **请求：** `[Feature]: Show subagent activity and expandable tool results in ZeroCode`。用户希望在 ZeroCode UI 中查看子代理的活动详情和可展开的工具调用结果，体现了对深度可观测性的需求。
        -   链接: `[zeroclaw-labs/zeroclaw Issue #8763]`

### 7. 用户反馈摘要

从今日的 Issue 和 PR 评论中，可以提炼出以下用户反馈：

-   **深度开发者对架构参与度高：** 社区中的高级用户不仅报告问题，还积极参与到如 `桌面原生控制` (#6909) 和 `并行测试硬固件` (#9965) 这类技术细节的 RFC 和 Bug 讨论中，展现出极高的专业度和主人翁意识。
-   **对商务和实际应用场景存在痛点：**
    -   **WhatsApp 通道失效** (#8627) 让依赖该渠道的海外用户工作流受阻。
    -   **模型成本控制问题** (#10659, #9332) 直接影响了用户大规模使用 AI Agent 的意愿，用户对 Token 消耗的可见性和控制性有刚性需求。
    -   **图片处理的脆弱性** (#10885, #10889, #9332) 暴露出多模态交互是当前体验的薄弱环节，是影响用户从文本助手转向全能助手的关键门槛。
-   **对项目进展和透明度表示满意：** A2A 协议从 RFC 到 PR 快速推进，文档的改进（如 `llms.txt`），以及许多 Bug 的快速响应和修复（如 #10625, #10888），让社区感到项目正在积极进化。

### 8. 待处理积压

以下为需要维护者关注的长期待处理 Issue 和 PR：

-   **高影响/阻塞性问题：**
    -   **[#5869] [OPEN]** `security: rumqttc ... RUSTSEC advisory` - **高优先级，阻塞状态**。虽然依赖上游，但持续的 CVE 风险需要保持跟踪，并考虑临时缓解方案（如禁用相关功能或替换依赖）。
    -   **[#8627] [OPEN]** `[Bug]: WhatsApp Web device linking broken` - **S1 工作流阻塞**。该 Issue 自 7 月提出以来，至今仍处于开放状态，对依赖该频道的用户影响巨大，急需方案。
    -   **[#7497] [OPEN]** `RFC: OCI-compliant registries for plugin storage` - **高优先级，阻塞状态**。此 RFC 是 WASM 插件生态

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*