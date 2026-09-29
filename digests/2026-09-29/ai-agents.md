# OpenClaw 生态日报 2026-09-29

> Issues: 500 | PRs: 500 | 覆盖项目: 13 个 | 生成时间: 2026-09-29 02:17 UTC

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

好的，作为AI智能体与个人AI助手领域的开源项目分析师，我已根据您提供的OpenClaw项目数据，为您生成了2026年9月29日的项目动态日报。

---

### OpenClaw 项目动态日报 | 2026年9月29日

**分析师点评：** 项目正处于 **高活跃度、高压力** 的发展阶段。社区反馈极为踊跃（单日Issues 500条），但系统稳定性问题突出，尤其是2026.9.5和9.6版本引入了多项严重的回归性Bug（内存泄漏、启动崩溃、数据丢失），构成了当前版本发布的主要阻碍。项目维护团队正通过“Fixes Tracker”和大量的“needs-maintainer-review”标签进行紧急响应，但合并速率（PR合并率35%）与问题产生的速率（新开433条）之间存在明显差距。

---

### 1. 今日速览

- **社区极度活跃**：过去24小时内，项目收到了**500条**Issue和**500条**PR更新，新开/活跃Issue高达**433条**，表明社区用户正在大量报告问题或寻求帮助。
- **修复压力巨大**：仅有**67条**Issue和**176条**PR被关闭/合并，积压待处理的PR达到**324条**。大量高优先级（P0/P1）的回归性Bug正等待修复或维护者审查。
- **稳定性遭遇挑战**：当前版本（2026.9.5/9.6）引入了多个影响网关可用性的严重Bug，包括启动挂起、崩溃循环、内存泄漏和数据损坏，成为社区讨论和项目修复的绝对焦点。
- **修复工作有序推进**：社区维护者已建立 **“2026.9.7 Fixes Tracker”** (#157531)，明确追踪从9.6到9.7版本间需要修复的21个候选问题，表明团队已系统性地着手解决当前危机。

---

### 2. 版本发布

**无**

（过去24小时内无新版本发布。）

---

### 3. 项目进展

尽管面临严重的稳定性危机，项目仍在推进一些关键的功能改进和重构，体现了团队的长线思维。

- **推进子代理稳定性 (PR #160203)**：`fix(subagents): avoid Gateway blocking while Stop saves state` 修复了子代理停止时阻塞网关线程的问题，提升了多代理场景下的系统响应性。该PR已准备好供维护者审查。
- **性能优化（持续进行）**：
    - `perf(sessions): retain maintenance plans across unrelated activity` (PR #160815) 旨在优化会话维护，避免无关活动干扰已准备好的归档计划，提升繁忙网关的性能。
    - `perf(ci): run qualified unit tests with native Bun` (PR #159988) 通过使用Bun加速CI测试，提升开发效率。
- **重构与清理 (PR #160662)**：`refactor(agents): deslop subagents, sessions, harness and CLI runner` 对代理子系统进行了代码清理和去重，旨在简化核心代码并提升长期可维护性。
- **新模型支持 (PR #160847)**：`feat(anthropic): support Claude Sonnet 5.5` 已提交PR，为即将或已发布的Anthropic新模型提供及时支持。

---

### 4. 社区热点

以下为过去24小时内讨论热度最高的议题，集中反映了社区的核心关切：

1.  **[Issue #149538] 网关启动后无响应 (22条评论)**：这是一个P0级问题，报告称`main`分支构建的网关在进入“ready”状态后，`/health`探针始终超时，事件循环被饿死，RSS内存不断攀升直至OOM。该问题被标记为“gold shrimp”，是一起严重且影响广泛的集群级事故。

2.  **[Issue #157067] Windows上克隆环境失败 (17条评论)**：用户报告在Windows环境下，隔离的cron任务设置无法正确克隆环境Proxy传递给子进程，导致失败。这是一个影响平台兼容性的P1级Bug。

3.  **[Issue #97616] 子进程泄漏导致僵尸进程积累 (16条评论)**：这是一个长期存在的Bug，报告称OpenClaw未能正确回收通过hook/tool执行产生的子进程，导致僵尸进程累积和运行时性能下降。该问题被标记为回归，用户通过一个👍表达了强烈关注。

4.  **[Issue #40001] Write工具缺乏追加模式 (16条评论)**：用户的长期痛点，`write`工具不支持追加模式，导致隔离的cron会话在写入共享文件时总是覆盖而非追加，造成数据丢失。该问题被评为P0，是会话功能的关键缺失。

5.  **[Issue #157531] 2026.9.7 修复追踪 (15条评论)**：创始人RomneyDa创建的“Fixes Tracker”是当前社区关注的焦点。它列出了18/21个候选修复，涵盖了隐私、用户体验、崩溃等关键领域，是社区判断项目即时走向的核心列表。

---

### 5. Bug 与稳定性

过去24小时报告了多个严重的稳定性问题，**2026.9.5和2026.9.6版本的回归问题是当前主要矛盾**。

| 严重程度 | 影响范围 | Issue / PR 链接 | 描述 | 修复状态 |
| :--- | :--- | :--- | :--- | :--- |
| **P0** | 核心可用性 | [Issue #149538](https://github.com/openclaw/openclaw/issues/149538) | 网关启动后不响应/health探针，事件循环饿死 | 无 |
| **P0** | 数据丢失，核心功能 | [Issue #40001](https://github.com/openclaw/openclaw/issues/40001) | `write`工具无追加模式，隔离cron会话导致数据覆盖 | 无 |
| **P0** | 核心可用性 | [Issue #157531](https://github.com/openclaw/openclaw/issues/157531) | 2026.9.7 Fixes Tracker，追踪多项P0/P1问题 | 已建立追踪 |
| **P0** | 磁盘I/O，运行稳定性 | [Issue #156571](https://github.com/openclaw/openclaw/issues/156571) | 2026.9.5版本模型目录worker泄漏临时文件，填满磁盘 | 无 |
| **P0** | 稳定性 | [Issue #157160](https://github.com/openclaw/openclaw/issues/157160) | 网关在`plugin-doctor-post-session-state`阶段崩溃循环 | 无 |
| **P0** | 用户体验，升级阻塞 | [Issue #154924](https://github.com/openclaw/openclaw/issues/154924) | `openclaw update`全局安装失败（`global-install-failed`） | 无 |
| **P1** | 稳定性，数据一致性 | [Issue #158095](https://github.com/openclaw/openclaw/issues/158095) | 网关worker获取数据库生命周期锁后未释放，导致后续操作全部失败 | 无 |
| **P1** | 性能，稳定性 | [Issue #158936](https://github.com/openclaw/openclaw/issues/158936) | macOS上网关启动慢，被看门狗误杀，导致重启循环 | 无 |
| **P1** | 性能，SSD磨损 | [Issue #157989](https://github.com/openclaw/openclaw/issues/157989) | 2026.9.5版本插件源码捕获导致大量重复文件读写（单命令1.1-1.4GB） | 无 |
| **P1** | 性能 | [Issue #159596](https://github.com/openclaw/openclaw/issues/159596) | 2026.9.6版本网关内存呈现“锯齿”模式，频繁触发内存压力事件 | 无 |
| **P1** | 性能 | [Issue #160548](https://github.com/openclaw/openclaw/issues/160548) | 2026.9.6版本模型目录worker每5分钟泄漏约1GB内存 | 无 |

**值得关注的是**，许多修复PR已处于“等待作者”或“准备审查”状态，例如与子代理状态保存 (#160203) 和会话维护 (#160815) 相关的PR，表明团队正在努力解决这些问题。

---

### 6. 功能请求与路线图信号

- **模型提供商诉求**：用户明确要求增加 **[Databricks Unity Gateway](https://github.com/openclaw/openclaw/issues/155633)** 作为官方模型提供商，并已附带了实现PR (#155634)。这反映了企业对模型流量必须经过其专有网关的合规性需求，很可能被纳入下一版本。
- **用户体验优化**：
    - 用户提议将 **Memory/Embedding 配置加入设置向导** 作为强制步骤 (#16670)，这是提升新用户开箱体验的关键建议。
    - 用户要求为 **Talk Mode 添加空闲超时自动停用功能** (#46844)，解决其持续消耗API资源的问题。
- **工具集扩展**：用户期待的新功能还包括创建 **CLI工具来检索/列出已发布的应用** (#16271) 和 **`openclaw tasks list` 支持`--tag`过滤** (#16088)，这些是提升CLI日常使用便捷性的功能。

---

### 7. 用户反馈摘要

- **反馈主题：升级受阻与困扰**
    - **“我便条里最重要的内容都被覆盖了，而不是追加进去……这让我完全无法信任cron任务。”** —— 来自 Issue #40001 的用户，表达了对`write`工具缺乏追加模式导致数据丢失的强烈不满。
    - **“我现在卡在2026.9.5上，完全无法升级到2026.9.6，因为更新过程会在‘update-candidate-state’阶段无限挂起。”** —— 来自 Issue #156986 的用户，描述升级过程挂起的困境。
    - **“Stable版的用户无法升级到2026.9.5/9.6，因为候选版本预演步骤失败了。”** —— 来自 Issue #154114 的用户，反馈官方更新机制自身出现故障。

- **反馈主题：对稳定性的担忧**
    - **“我的Gateway每5分钟就会触发一次内存压力事件，然后杀死一个worker进程……这种情况每天会发生约200次。”** —— 来自 Issue #159596 的用户，描述了内存泄漏带来的糟糕体验。
    - **“我的macOS App在重启后总是在40-70秒的启动阶段被杀掉，然后陷入无限重启循环。”** —— 来自 Issue #158936 的用户，反馈macOS版本在看门狗机制下的稳定性问题。
    - **“运行一天后，SSD的写入量达到了~13TB……这不仅仅是性能问题，更是硬件健康问题。”** —— 来自 Issue #157989 的用户，对插件系统导致的高硬盘I/O表示严重担忧。

---

### 8. 待处理积压

以下是一些长期未解决或“被搁置”但影响重要的议题，需要维护者特别关注：

1.  **[Issue #16670] (P2) - 记忆/嵌入设置应成为设置向导的强制步骤**：自2026年2月提出，距今已超过7个月。该建议能显著提升新用户留存率，建议重新评估并排入路线图。
    - 链接: [https://github.com/openclaw/openclaw/issues/16670](https://github.com/openclaw/openclaw/issues/16670)

2.  **[Issue #120006] (P2) - CLI会话重置导致工具历史丢失，且并发CLI会话作用在同一会话key上**：自8月提出，涉及`claude-cli`后端的数据一致性和用户体验问题，至今仍缺少维护者决策。
    - 链接: [https://github.com/openclaw/openclaw/issues/120006](https://github.com/openclaw/openclaw/issues/120006)

3.  **[Issue #84037] (P1) - 改善Codex应用服务器的稳定状态CPU及辅助进程开销**：一个从2026年5月就提出的性能改进请求，虽非新Bug，但持续影响使用Codex运行时的用户资源占用。
    - 链接: [https://github.com/openclaw/openclaw/issues/84037](https://github.com/openclaw/openclaw/issues/84037)

4.  **[PR #128872] (P2) - 修复自动回复中`message_tool_only`的决定与交付路径分离**：一个自8月就提交的功能性修复PR，旨在解决特定聊天类型下Agent回复的逻辑问题，但仍停留在“需要证明”阶段，等待作者的最终验证。
    - 链接: [https://github.com/openclaw/openclaw/pull/128872](https://github.com/openclaw/openclaw/pull/128872)

---

## 横向生态对比

好的，作为AI智能体与个人AI助手开源生态的资深技术分析师，我已根据您提供的11个项目的详细动态日报，为您生成了一份横向对比分析报告。

---

### 个人AI助手/自主智能体开源生态横向对比分析报告 (2026-09-29)

#### 1. 生态全景

当前个人AI助手与自主智能体开源生态呈现出 **“极度活跃、压力巨大、分化明显”** 的整体态势。一方面，社区参与度极高，以OpenClaw、NanoBot、PicoClaw为代表的头部项目，日均处理数百条Issues和PR，社区反馈极为踊跃，推动了功能和模型的快速迭代（如对GPT-6、Claude Sonnet 5.5等新模型的及时支持，以及对Agent协作能力的深度探索）。另一方面，这种快速迭代也付出了稳定性代价，多项目（OpenClaw、NanoBot、Hermes Agent）均报告了严重的回归性Bug与数据丢失风险，项目正处于 **“能力快速扩张”与“稳定性巩固”** 相互拉扯的关键阶段。此外，安全与隐私（如MCP信任门、会话信息泄露、权限绕过）正成为社区最核心的关切，预示着生态正从“功能可用”向“企业级可信任”跨越。

#### 2. 各项目活跃度对比

| 项目名称 | Issues (新开/活跃) | PRs (新开/活跃) | PRs 合并/关闭 | 新版本发布 | 健康度评估 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | 500 / 433 | 500 | 176 (合并) | 无 | 🔴 高压力，稳定性危机 |
| **NanoBot** | 8 | 24 | 10 (合并) | 无 | 🟡 高密度迭代，修复及时 |
| **Hermes Agent** | 50 / 22 | 50 | 11 (合并) | 无 | 🟡 高活跃，P2级Bug集中爆发 |
| **PicoClaw** | 7 / 6 | 10 | 0 | 无 | 🟠 社区活跃，官方维护真空 |
| **NanoClaw** | 无/少量 | 少量 | 19 (合并) | 无 | 🟢 维护者活跃，聚焦稳定性修复 |
| **LobsterAI** | 5 (均为旧issue) | 14 | 13 (合并) | 无 | 🟢 清扫技术债务，聚焦发布分支 |
| **ZeroClaw** | 50 | 50 | 11 (合并) | 无 | 🟡 极高活跃，安全与稳定性并重 |
| **NullClaw** | 16 (旧issue关闭) | 6 (合并) | 6 | 无 | 🟢 积极处理积压，项目趋于稳定 |
| **Moltis** | 0 | 1 | 0 | 无 | 🟢 低活跃，功能收敛期 |
| **IronClaw** | 2 | 3 | 1 (合并) | 无 | 🟢 中等活跃，聚焦UI与文档 |
| **ZeptoClaw** | 2 | 1 | 0 | 无 | 🟢 低活跃，功能补全期 |
| **TinyClaw** | 0 | 0 | 0 | 无 | ⚪ 无活动，疑似停滞 |
| **CoPaw** | 数据缺失 | 数据缺失 | 数据缺失 | 无 | ⚪ 摘要生成失败，状态不明 |

- **🔴 高压区：** OpenClaw (稳定性危机)、PicoClaw (维护真空)。
- **🟡 快速迭代区：** NanoBot、Hermes Agent、ZeroClaw。
- **🟢 质量巩固/功能补全区：** NanoClaw、LobsterAI、NullClaw、Moltis、ZeptoClaw、IronClaw。

#### 3. OpenClaw 在生态中的定位

**OpenClaw 无疑是当前生态的“核心参照物”与“压力测试标杆”**。
- **优势与定位：** 其社区规模和活跃度远超他者（单日500条Issue/PR），这不仅是代码库的繁荣，更是其作为“事实标准”地位的体现。它正在为整个生态探索边界，例如在子代理（subagents）稳定性、多会话管理、性能优化等方面的投入，都代表了该领域最前沿的技术挑战。
- **技术路线差异：** 与NanoBot、NullClaw等通过“原子写入”、“ripgrep”等底层优化来提升稳定性不同，OpenClaw当前正经历更大的架构性阵痛。其技术进步（如Fixes Tracker的建立）与稳定性代价（大量回归性Bug）并存，反映了其作为“先行者”所承担的复杂性和风险。
- **社区规模对比：** OpenClaw的社区活跃度是其他项目的数倍乃至数十倍。NanoBot、ZeroClaw虽也保持高活跃，但其讨论深度和广度与OpenClaw的“集群级事故”讨论相比，仍显聚焦。OpenClaw的社区反馈已成为分析师判断行业痛点的最主要风向标。

#### 4. 共同关注的技术方向

多个项目不约而同地涌现出以下需求，反映了行业共性痛点：

1.  **模型与提供商扩展：** 多个项目（NanoBot、ZeroClaw、NullClaw、Moltis、IronClaw）正在或已经集成新的模型提供商（如Tsubasa、Eden AI、Keenable），这表明生态正从依赖单一模型向“模型路由器”或“多云/多后端策略”演进。
2.  **稳定性与数据安全是首要攻坚方向：**
    - **数据丢失/损坏：** **OpenClaw** (`write` 工具无追加模式)、**NanoBot** (并发写入损坏)、**ZeptoClaw** (输出截断)、**ZeroClaw** (并发文件编辑) 均报告了此类问题。
    - **回归性Bug：** **OpenClaw** (多版本引入内存泄漏、启动崩溃)、**Hermes Agent** (桌面端重复渲染) 面临相似困境。
    - **安全隐私：** **NanoBot** (飞书消息泄露)、**Hermes Agent** (MCP信任门检测失败)、**ZeroClaw** (会话恢复权限绕过) 表明安全模型实现仍显脆弱。
3.  **用户界面与体验优化：**
    - **实时性与透明度：** **OpenClaw** (Talk Mode超时)、**NanoBot** (WebUI实时速率展示) 用户对Agent行为的实时反馈有更高期待。
    - **易用性：** **Hermes Agent** (更新流程失败)、**NullClaw** (Web UI配置困难) 用户对“开箱即用”和健壮的更新机制诉求强烈。
4.  **Agent协作与工具生态：**
    - **Zeroclaw** 提出“插件看板”、**OpenClaw** 强化子代理稳定性，表明Agent协作（多代理、子代理）和复杂的工具使用（如文档编辑、协作面板）是能力提升的下一个增长点。

#### 5. 差异化定位分析

| 项目 | 功能侧重 | 目标用户 | 技术架构/实现特点 | 当前阶段 |
| :--- | :--- | :--- | :--- | :--- |
| **OpenClaw** | 通用型，全能型Agent，深度CLI/桌面交互 | 重度开发者、高级用户、社区贡献者 | 复杂、模块化，自研运行时，深度集成多种Provider | **快速扩张与稳定性危机并存** |
| **NanoBot** | 性能优先，轻量级，强工具执行 | 开发者、效率派 | 强底层性能优化 (原子写、ripgrep、Token预热) | **高密度功能迭代** |
| **Hermes Agent** | 桌面应用体验，看板/委托任务 | 桌面端用户、项目经理 | 专注macOS/Windows桌面端，看板插件，委托工作流 | **P2级Bug集中修复** |
| **PicoClaw** | 轻量级，跨平台，IRC/多种渠道 | 极客、多通道用户 | 模块化、高度可配置，但官方维护缺失 | **社区自救，维护真空** |
| **ZeroClaw** | 企业级，多租户，强安全与身份访问 | 企业内部团队、SaaS服务商 | 面向企业（RBAC、OIDC），重视成本核算与审计 | **构建企业级基础设施** |
| **NanoClaw** | 自动化安装与更新体验 | 运维、开发者 | 高度关注更新流程、容器管理、回滚等“运营”环节 | **解决特定领域的“最后10%”痛点** |
| **LobsterAI** | 协作面板与文档编辑 | 知识工作者、创意团队 | 强调多Agent协作 (cowork)、文档处理能力 (Office) | **收敛功能，打磨协作体验** |
| **NullClaw** | 多提供商/多渠道，智能管道 | 寻求高灵活性的用户 | 通过“自适应智能管道”实现自我学习和质量循环 | **清扫积压，功能整合** |

#### 6. 社区热度与成熟度

- **第一梯队（极度活跃，快速迭代）：** **OpenClaw**。其社区规模、反馈强度和技术讨论深度遥遥领先，代表了生态的最前沿和最痛点。
- **第二梯队（高活跃，迭代与修复并行）：** **NanoBot**、**ZeroClaw**、**Hermes Agent**。这些项目社区活跃，有明确的版本目标和路线图，但同样面临显著的稳定性挑战，处于“高速发展”与“质量巩固”的磨合期。
- **第三梯队（中等活跃，聚焦特定领域）：** **NanoClaw**、**PicoClaw**、**LobsterAI**、**NullClaw**、**IronClaw**。这些项目或专注于解决特定问题（如更新流程），或在特定领域（如协作、渠道）深耕，社区讨论更具针对性，而非广泛的通用议题。
- **第四梯队（低活跃/维护模式）：** **Moltis**、**ZeptoClaw**、**TinyClaw**、**CoPaw**。这些项目活动较少，或处于功能收敛阶段，或缺乏维护，更多是满足小众、特定场景的需求。

#### 7. 值得关注的趋势信号

1.  **AI Agent 的“企业级信任”时代已来：** 从 **ZeroClaw** 的多租户安全、**OpenClaw** 和 **Hermes Agent** 的MCP信任机制，到 **NanoBot** 的飞书消息泄露，社区对安全、权限、隐私、审计的诉求从“锦上添花”变为“核心功能”。未来，谁能构建更完善的信任基础设施，谁就能赢得企业级市场。
2.  **从“功能堆砌”到“体验打磨”：** **LobsterAI** 专注协作面板优化、**NanoClaw** 死磕更新流程、**NullClaw** 修复错误提示，都表明竞争已从“能做到什么”转向“用户用得爽不爽、稳不稳”。**极致稳定性和流畅的用户体验将成为下一阶段的护城河。**
3.  **“模型路由器”模式正在形成：** 多项目（OpenClaw, ZeroClaw, Moltis, NullClaw）支持多个模型提供商，用户正从“绑定某个模型”转向“根据任务选择最佳模型”。这要求Agent框架必须提供统一的、灵活的接口来管理这些异构资源。
4.  **Agent 协作能力成为关键竞争点：** **OpenClaw** 的子代理、**LobsterAI** 的Cowork、**ZeroClaw** 的委托任务，都指向了同一个方向：单个Agent的能力是有限的，未来的杀手级应用将是 **“Agent团队”** 的协作。谁能提供更流畅、更可靠的Agent间通信和任务调度机制，谁就将抢占先机。
5.  **社区治理与反馈循环决定项目成败：** **OpenClaw** 的“Fixes Tracker”和 **ZeptoClaw** 由开发者主动发起的关键修复（输出溢出），体现了健康社区的自驱力。而 **PicoClaw** 的维护真空和社区催生Fork，则发出了“社区流失”的警钟。**维护者的响应速度和透明度，正成为开源项目能否持续繁荣的决定性变量。**

**对AI智能体开发者的参考价值：** 当前是进入该领域的最佳时机，但应放弃“大而全”的幻想。建议开发者关注1-2个核心场景（如**定制Agent工作流**、**开发杀手级插件/工具**），并优先选择在**稳定性和安全模型**上投入最多的项目作为底座（如Node.ZeroClaw或NanoBot的底层优化思路），避免被卷入上游的架构动荡中。

---

## 同赛道项目详细报告

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，我将根据您提供的 NanoBot GitHub 数据，生成格式规范、内容翔实的项目动态日报。

---

# NanoBot 项目动态日报 | 2026-09-29

## 今日速览

今日项目活跃度极高，主要集中在 **Bug 修复**与**新功能集成**两大方向。24小时内处理了8个Issue和24个PR，其中有多项关键修复已合并，包括针对文件写入崩溃的**原子写操作**、Web获取工具的错误传播以及飞书渠道的消息泄露问题。社区对新模型（如 GPT-6 Sol/Luna）的兼容性反馈集中，同时有数个重量级新特性（如 Claude on Vertex AI、Unbrowse 读取后端、子智能体聚合结果）的PR正在积极审阅中。整体来看，项目处于**高密度迭代期**，修复速度及时，但新特性积压也在增加。

## 版本发布

无

## 项目进展

今日合并/关闭了10个PR，主要集中在修复与优化，项目在稳定性和性能上迈出了坚实一步。以下是关键进展：

- **🔒 文件系统稳定性提升：** PR [#5953](https://github.com/HKUDS/nanobot/pull/5953)（由 louisss1016 贡献）为 `WriteFileTool`、`EditFileTool` 等工具实现了原子写入，解决了并发写入导致的数据损坏问题，这是一个影响广泛的底层修复。
- **🔧 Web工具错误处理优化：** PR [#5949](https://github.com/HKUDS/nanobot/pull/5949)（由 KailBug 贡献）修复了 `web_fetch` 工具在失败时仍返回“成功”状态的问题，现在会正确触发错误处理生命周期。
- **🕒 会话超时机制改进：** PR [#5957](https://github.com/HKUDS/nanobot/pull/5957)（由 KailBug 贡献）强制对执行会话实施硬超时，无需依赖轮询机制，增强了系统健壮性。
- **🖥️ WebUI 修复与更新：** PR [#5952](https://github.com/HKUDS/nanobot/pull/5952)（由 chengyongru 贡献）修复了 WebUI 标题生成失败的问题，并更新了贡献者名单（PR [#5951](https://github.com/HKUDS/nanobot/pull/5951)），新增27位贡献者。
- **⚡️ 性能优化：** PR [#5948](https://github.com/HKUDS/nanobot/pull/5948)（由 chengyongru 贡献）集成了 `ripgrep` 用于本地文件搜索，显著提升搜索效率。PR [#5861](https://github.com/HKUDS/nanobot/pull/5861)（由 chengyongru 贡献）在后台预热回退tokenizer，降低了首次启动的延迟。

## 社区热点

今日最活跃的讨论集中在以下两个Bug上：

1.  **[Issue #5924] Agent 陷入 Sudo 循环**
    -   **描述：** Agent 在执行需要 `sudo` 权限的命令时，授予的权限仅持续一个回合，导致 Agent 陷入“授权-失败-重试”的死循环，最终因达到最大迭代次数而卡死。
    -   **链接：** [HKUDS/nanobot Issue #5924](https://github.com/HKUDS/nanobot/issues/5924)
    -   **分析：** 这是用户**操作体验的严重痛点**，直接导致 Agent 无法完成需要提权的任务。社区对此类“Agent 行为不够智能”的场景非常敏感。

2.  **[Issue #5903] 飞书渠道内部会话检查点消息泄露**
    -   **描述：** 飞书渠道中，属于内部机制的会话检查点信息（如“Continue the active task from the working-memory checkpoint above.”）在空闲压缩后，被当作普通消息推送给用户，造成信息泄露和困惑。
    -   **链接：** [HKUDS/nanobot Issue #5903](https://github.com/HKUDS/nanobot/issues/5903)
    -   **分析：** 这暴露了**渠道适配层的逻辑缺陷**，未能正确过滤内部消息。用户对此非常不满，认为这是重要的隐私和体验问题。

## Bug 与稳定性

| 严重程度 | 问题 ID | 描述 | 状态 | Fix PR |
| :--- | :--- | :--- | :--- | :--- |
| **P0 - 致命** | [#5924](https://github.com/HKUDS/nanobot/issues/5924) | Agent 陷入 Sudo 循环，无法继续任务 | **开放中** | 无 |
| **P0 - 致命** | [#4798](https://github.com/HKUDS/nanobot/issues/4798) | 并发文件写入导致工作区文件损坏 | **长期开放** | **[#5953](https://github.com/HKUDS/nanobot/pull/5953) (已合并)** |
| **P1 - 严重** | [#5898](https://github.com/HKUDS/nanobot/issues/5898) | 不支持通过 GitHub Copilot 调用 GPT-6 模型系列 | **开放中** | 无 |
| **P1 - 严重** | [#5903](https://github.com/HKUDS/nanobot/issues/5903) | 飞书渠道内部检查点消息泄露给用户 | **开放中** | 无 |
| **P2 - 一般** | [#5843](https://github.com/HKUDS/nanobot/issues/5843) | 长会话的 BUILD 阶段存在10秒以上的延迟 | **已关闭** | 无 |
| **P2 - 一般** | [#5956](https://github.com/HKUDS/nanobot/issues/5956) | 飞书渠道的通知无法关闭，压缩通知会被发送到频道 | **开放中** | 无 |
| **N/A** | [#5939](https://github.com/HKUDS/nanobot/issues/5939) | Codex 模型发现遗漏 GPT-6 Sol 和 Luna | **已关闭** | **[#5952](https://github.com/HKUDS/nanobot/pull/5952) (已合并)** |

**分析：** 今天最重要的Bug修复是针对文件损坏的P0问题，已通过合入的PR [#5953](https://github.com/HKUDS/nanobot/pull/5953)解决。但Agent循环和模型兼容性问题仍在，是当前稳定性的主要风险点。

## 功能请求与路线图信号

今日提交的功能请求数量较多，显示出社区对项目功能扩展的强烈期待：

- **实时生成速度展示：** [Issue #5908](https://github.com/HKUDS/nanobot/issues/5908) 提议在WebUI流式回复时展示实时 Tokens/s 指标，这是一个典型的**用户对性能和透明度有更高要求**的信号。
- **新 Provider 支持：** PR [#5955](https://github.com/HKUDS/nanobot/pull/5955)（Claude on Vertex AI）和 PR [#5945](https://github.com/HKUDS/nanobot/pull/5945)（Unbrowse 读取后端）正在活跃开发中，表明项目正积极拥抱**多云、多后端**策略以增强灵活性。
- **增强的 Agent 能力：** PR [#5954](https://github.com/HKUDS/nanobot/pull/5954)（子智能体聚合结果）和 PR [#5902](https://github.com/HKUDS/nanobot/pull/5902)（Telegram 话题重命名）表明项目在**提升 Agent 协作**和**渠道用户体验**方面有明确规划。
- **成本优化：** PR [#4549](https://github.com/HKUDS/nanobot/pull/4549)（心跳模型可配置更便宜模型）是一个已经开放数月的长期PR，说明社区对于**降低使用成本**有持续性需求。

**路线图信号：** 从合并的 PR [#5861](https://github.com/HKUDS/nanobot/pull/5861)（后台预热tokenizer）和 [#5948](https://github.com/HKUDS/nanobot/pull/5948)（集成ripgrep）来看，项目维护者正在**优先解决性能瓶颈**。同时，大量新Provider的PR暗示**“支持更多的模型和API”**是未来的重要方向。

## 用户反馈摘要

从今日的Issues评论中，我们可以提炼出以下真实用户痛点：

- **Agent 行为不够智能：** 用户对 Agent 陷入 `sudo` 循环的行为感到沮丧。用户期望Agent能更聪明地处理权限问题，而不是机械地重试。这反映了用户希望Agent具备**更高级的上下文理解和解决问题的能力**。
- **渠道私有性不足：** 用户对飞书渠道泄露内部消息的问题反应强烈。这表明用户**非常在意使用场景的隔离和隐私**，任何跨场景的信息泄漏都是不可接受的。
- **模型兼容性焦虑：** 用户担心新模型（如 GPT-6）发布后，项目能否快速跟进支持。Issue #5898 和 #5939 都指向了这一点，说明**用户对“最新最好的模型”有很强的渴望**，并期望项目能无缝衔接。
- **学习成本和配置复杂度：** 虽然本次数据没有直接体现，但从“Sudo循环”、“飞书配置”、“无in-place edit”等具体问题可以看出，用户在配置和使用过程中仍会遇到各种**阻碍性细节**，说明易用性仍有优化空间。

## 待处理积压

- **[Issue #4798] 并发文件写入损坏（P0）：**
    - **描述：** 最早于7月6日报告，是严重的文件损坏问题。
    - **链接：** [HKUDS/nanobot Issue #4798](https://github.com/HKUDS/nanobot/issues/4798)
    - **提醒：** 尽管修复 PR [#5953](https://github.com/HKUDS/nanobot/pull/5953) 今日已合并，但Issue尚未关闭。**请维护者确认PR的修复范围，并关闭此Issue，确保社区知晓该长期问题已解决。**

- **[PR #4549] 心跳模型配置（新功能）：**
    - **描述：** 提议允许为后台心跳配置更便宜的模型以降低成本。已开放超过3个月。
    - **链接：** [HKUDS/nanobot PR #4549](https://github.com/HKUDS/nanobot/pull/4549)
    - **提醒：** 这是一个成熟的、对用户有价值的功能。请维护者**评估是否将其纳入下一个版本的发布计划**，或给予社区明确的反馈，以避免社区贡献积极性受挫。

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

***

# Hermes Agent 项目动态日报
**日期**: 2026-09-29

---

## 今日速览

今日项目活跃度极高，24小时内处理了50条Issues和50条PRs，反映了社区参与度和维护团队的响应速度。新开与关闭的Issue数量接近（22 vs 28），表明问题处理闭环效率良好。然而，高活跃度的背后是大量P2级Bug的集中爆发，特别是桌面端、更新流程和会话状态管理的反复出现，提示项目可能进入了稳定性考验期。值得关注的是，问题评论数普遍较低（2-3条），且近半年前遗留的“Hindsight”内存插件问题至今未解决，社区深度讨论与长期积压问题的解决效率有待提高。

---

## 版本发布

无

---

## 项目进展

今日共有11个PR被合并/关闭，项目在功能和修复方面取得了以下关键进展：

- **会话与状态管理**：
    - **PR #126960 (已合并)**: 修复了`tui_gateway`中用户在按下“Stop”后，后台事件（如异步代理或看板事件）会意外自动启动新模型回合的问题，确保用户停止操作后会话保持安静状态。
    - **PR #79510 (已关闭)**: 修复了在`dashboard.turn_isolation`模式下，模型切换指令无法传递到计算主机子进程的问题，该修复确保模型选择器对用户是实际生效的。
- **模型与代理核心**：
    - **PR #119568 (已合并)**: 移除了不存在的模型“GPT-6 Terra”及“Terra Pro”的元数据引用，净化了模型家族目录，避免模型选择错误。
    - **PR #91963 (已关闭)**: 为委托任务结果新增了稳定、隐私安全的归因ID（`delegation_id`、`subagent_id`、`child_session_id`），增强分布式任务追踪能力。
- **基础设施与发布**：
    - **PR #75707 (已关闭)**: 为Runs API实现了基于精确ID的待处理审批恢复机制，允许断线客户端查询并确认审批，避免状态丢失。

**项目向前迈进了约 +4 个关键修复/功能**，主要集中在提升桌面端操作逻辑的正确性、完善分布式任务模型、并净化数据源。

---

## 社区热点

今日讨论最活跃的问题主要围绕桌面端核心体验和工具兼容性。评论数最高的两个问题暴露出用户对**响应式界面**和**安全信任机制**的强烈诉求：

1.  **[Bug]: macOS Desktop renders duplicate assistant reply on d0288be5** (Issue #123801)
    - **链接**: [NousResearch/hermes-agent Issue #123801](https://github.com/NousResearch/hermes-agent/issues/123801)
    - **数据**: 评论 15， 👍 0
    - **分析**: 该Bug是今日讨论的绝对热点，用户详细描述了在macOS桌面上看到的完全相同的助理回复重复渲染问题。尽管数据库仅存储一行，但UI却显示了两次。这直接触犯了用户对聊天界面**数据一致性**和**UI正确性**的基本期望，背后是前端渲染逻辑与数据模型同步出了问题，是典型的“界面级”体验Bug。用户反复验证服务端数据以排除干扰，显示了强烈的主动性。

2.  **[Bug]: MCP trust gate: readOnlyHint never detected on live-discovered tools** (Issue #88858)
    - **链接**: [NousResearch/hermes-agent Issue #88858](https://github.com/NousResearch/hermes-agent/issues/88858)
    - **数据**: 评论 10， 👍 1
    - **分析**: 该问题主要抱怨MCP信任门对于标记为只读的工具（`readOnlyHint: true`）未能正确识别，导致所有工具都被视为可读写，每次操作都弹窗询问，使“不可信”服务器几乎不可用。用户不仅报告了Bug，还深入分析了原因（camelCase vs snake_case），并尝试了多种绕过方法，展现了技术深度和解决问题的决心。这反映了用户对**更细致、更可配置的安全访问控制**的强烈需求，信任门机制的粒度直接影响到工具生态的可用性和用户体验。

---

## Bug 与稳定性

今天报告的Bug高度集中在**会话状态**和**更新流程**两个领域，按严重程度排列如下：

**严重(P0/P1)：**
- **[Bug]: patch V4A `Delete File` on a symlink deletes the file it points to** (Issue #123824)
    - **严重程度**: P0（数据安全）
    - **状态**: 开放，无对应PR
    - **链接**: [NousResearch/hermes-agent Issue #123824](https://github.com/NousResearch/hermes-agent/issues/123824)
    - **摘要**: 对符号链接（symlink）执行`Delete File`和`Move File`操作时，会错误地作用于链接指向的目标文件，而不是链接本身。这是一个严重的数据丢失风险，特别是当V4A工具用于自动化任务时。

- **[Bug]: macOS Desktop renders duplicate assistant reply** (Issue #123801)
    - **严重程度**: P1（核心功能）
    - **状态**: 开放，无对应PR
    - **链接**: [NousResearch/hermes-agent Issue #123801](https://github.com/NousResearch/hermes-agent/issues/123801)
    - **摘要**: macOS桌面端渲染重复的助理回复（见社区热点分析）。

**中等(P2)：**
以下是今日报告的P2级别Bug，均无直接对应的修复PR。

- **[Bug]: Windows hermes update fails in source preparation: WinError 5 deleting .previous-python libcrypto DLL** (Issue #124807) - [链接](https://github.com/NousResearch/hermes-agent/issues/124807) - Windows更新因文件占用失败。
- **[BUG] hermes update on a multi-profile host: host-gateway relaunch inherits the launching profile's HERMES_HOME** (Issue #126470) - [链接](https://github.com/NousResearch/hermes-agent/issues/126470) - 多Profile配置文件下的更新Bug导致网关启动异常。
- **[Bug]: Desktop: assistant reply renders twice (adjacent, verbatim) on a fresh client** (Issue #126524) - [链接](https://github.com/NousResearch/hermes-agent/issues/126524) - 与#123801类似，但发生在全新客户端上。
- **[Bug]: read_file fails with "Cannot read '<cwd>': not a regular file" when relay models emit file_path** (Issue #124860) - [链接](https://github.com/NousResearch/hermes-agent/issues/124860) - 自定义代理模型使用`file_path`参数名导致`read_file`工具失败。
- **[Bug]: todo_list silently accepts unknown params ({action,list}) and returns an empty success-shaped result** (Issue #126656) - [链接](https://github.com/NousResearch/hermes-agent/issues/126656) - `todo_list`工具静默接受未知参数，造成“伪成功”结果。
- **[B] BUG: cron passes the model pin literally — seat model.aliases never resolve** (Issue #126655) - [链接](https://github.com/NousResearch/hermes-agent/issues/126655) - 定时任务（Cron）的模型别名解析失效，导致定时任务失败。

**低严重度(P3)：**
- **[Bug]: Hindsight plugin local_embedded requires hindsight-all, but plugin.yaml only lists hindsight-client** (Issue #7718) - [链接](https://github.com/NousResearch/hermes-agent/issues/7718) - 长期未解依赖问题。
- **[Bug]: Desktop project session/file browser remains rooted at ~/.hermes; folder selector is disabled** (Issue #117890) - [链接](https://github.com/NousResearch/hermes-agent/issues/117890) - 桌面端项目文件浏览器根目录错误。

---

## 功能请求与路线图信号

今天用户提出的新功能需求不多，但十分精准：

- **稳定消息身份标识**: Issue #126265（[链接](https://github.com/NousResearch/hermes-agent/issues/126265)）提出为消息引入稳定、持久的唯一ID（`message_uid`），以解决消息在复制、压缩、回溯过程中身份丢失的问题。这属于**基础设施级的增强**，将对插件开发、会话持久化和状态管理产生深远影响。已有相关的PR #91963在今日被合并（提供子任务ID），表明项目方可能正在系统性地解决这个问题，该功能很可能被纳入下一版本的路线图。
- **文档化更新与SDK管理流程**: Issue #120882（[链接](https://github.com/NousResearch/hermes-agent/issues/120882)）是一个来自CLPI的文档请求，要求清晰记录模型更新、SDK版本管理等流程。虽然属于P3级别，但对于提升用户自服务能力和降低社区支持压力至关重要，可能会作为里程碑内的“用户体验改进”子任务被采纳。

此外，PR #115081（[链接](https://github.com/NousResearch/hermes-agent/pull/115081)）为看板插件新增了运行时上限徽章、板级分类信号等功能，属于桌面端的迭代优化，可能反映了官方对看板工具场景的未来规划。

---

## 用户反馈摘要

从今日的Issues评论中，可以提炼出以下真实用户痛点和使用场景：

- **频繁的更新体验问题**：多位Windows用户报告更新过程失败，原因包括文件被占用、进程锁定等（Issue #124807, #83211, #77277）。一位用户无奈地表示“manual PID kills never help because the Desktop app's own backend keeps respawning”，显示出更新故障已严重影响其日常工作流。macOS用户也遇到了更新后服务死亡的问题（Issue #121209）。**更新流程的健壮性是用户当前最强烈的不满之一**。
- **不可预期的工具行为**：Issue #123824（symlink删除）和#124860（`file_path`参数）暴露了工具对边缘情况的处理不足，可能导致用户数据丢失或任务静默失败。用户Jonpol01评价道：“patch V4A `Delete File` on a symlink deletes the file it points to”，语气中透露出措手不及与对数据安全的担忧。
- **核心功能不一致的挫折感**：多人同时报告桌面端助理回复重复渲染的问题（#123801, #126524），而数据库却显示正常。用户H4sagent详细记录了复现步骤，并指出“session list also double-renders”，表明这不是个例，而是特定环境下的系统性问题。这极大影响了用户对桌面端应用作为主要交互界面的信心。
- **对配置灵活性的高需求**：用户在MCP信任门（#88858）`hermes doctor`报告健康但更新失败（#98384）等场景中，希望项目提供更精细、更可靠的配置项，而不是非0即1的硬限制。用户giustozzi在#88858中直接点出“camelCase attr vs snake_case in the SDK”这种技术细节，表明用户不仅仅是报告Bug，更是希望参与改进。

---

## 待处理积压

以下为长期未响应或优先级被压制的重要Issue和PR，可能成为项目健康度的隐患：

1.  **Issue #7718 - Hindsight插件依赖缺失** (创建: 2026-04-11)
    - **链接**: [NousResearch/hermes-agent Issue #7718](https://github.com/NousResearch/hermes-agent/issues/7718)
    - **当前**: 开放，P3，持续5个月
    - **风险**: 该`local_embedded`模式问题导致内存插件静默失效，但用户无法得到明确反馈。随着时间推移，依赖该功能的社区插件可能受到更大影响。

2.  **Issue #88858 - MCP信任门兼容性**(创建: 2026-08-18)
    - **链接**: [NousResearch/hermes-agent Issue #88858](https://github.com/NousResearch/hermes-agent/issues/88858)
    - **当前**: 开放，P2，持续1.5个月，有10条评论
    - **风险**: 这是今天讨论热点之一，但问题已存在一个多月。MCP信任门的可用性是拓展工具生态的核心问题，长期搁置会打击第三方工具开发者积极性。

3.  **PR #58344 - Session Health技能** (创建: 2026-07-04，待合并)
    - **链接**: [NousResearch/hermes-agent Issue #58344](https://github.com/NousResearch/hermes-agent/issues/58344)
    - **当前**: 开放，无更新，持续3个月
    - **风险**: 该PR提供了一个颇有价值的自我诊断技能，但长时间未被审阅合并，可能挫伤贡献者的积极性。

4.  **PR #57700 - 代理衰竭冷却修复**(创建: 2026-07-03，待合并)
    - **链接**: [NousResearch/hermes-agent Issue #57700](https://github.com/NousResearch/hermes-agent/issues/57700)
    - **当前**: 开放，无更新，持续3个月
    - **风险**: 该修复旨在防止代理在特定场景下被永久锁死，是一个明确的Regression修复。长期搁置可能导致更复杂的会话状态问题。

**建议**：维护团队应优先评估**P0/P1级别Bug**（#123824, #123801）的修复方案。同时，针对上述长期积压的Issue/PR，特别是那些已有明确修复方案或设计文档的，应安排审阅或给出明确回应，以保持社区贡献的活力和项目的透明健康度。

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

**PicoClaw 项目动态日报 (2026-09-29)**  
**数据来源**: GitHub – sipeed/picoclaw  
**数据周期**: 过去 24 小时  

---

### 1️⃣ 今日速览  
- 项目过去 24 小时**活跃度回升**：共产生 7 条 Issue（6 新开，1 关闭）和 10 条 PR（全部待合并）。  
- **一位新贡献者 (x1F916) 集中提交了 5 个可靠性修复 PR**，涵盖 Agent 核心、通道管理、配置持久化、更新器等多个模块，表明社区正主动修补积压缺陷。  
- 然而，**主仓库的维护状态仍令人担忧**：一条新 Issue (#3398) 公开声明项目“目前似乎未被维护”，并推广了一个活跃 fork。同时，**大量 PR 和 Issue 被 stale bot 标记**，长期无人响应。  
- 安全警报凸显：一位安全研究者请求启用私有漏洞报告（#3405），暗示已发现潜在漏洞。  
- **整体健康度评分**：⚠️ 中低（社区贡献活跃，但官方维护缺席，积压严重，存在 fork 分流风险）。  

---

### 2️⃣ 版本发布  
*无新版本发布。* → 本日省略该部分。  

---

### 3️⃣ 项目进展  
- **今日无 PR 被合并或关闭**（10 条 PR 均为待合并状态）。主要进展来自于**新提交的 5 个 PR**，全部由贡献者 **x1F916** 在同一天（2026-09-28）创建并提交：  

| PR | 标题 | 关键修复点 | 状态 |
|---|---|---|---|
| #3403 | `fix(agent): deliver async tool results to the originating session` | 异步工具结果曾错误发送到默认 Agent 主会话，导致多会话混乱。现已修正路由逻辑。 | 待合并 |
| #3402 | `fix(agent): resolve the owning agent in context managers` | 非默认 Agent 会话中，上下文管理器错误调用了路由代理；基于 #3316 重提。 | 待合并 |
| #3401 | `fix(channels): make Reload synchronous and nil-safe` | 通道重载时可能因 nil 实例或异步竞态导致 panic，转为同步且加空检查。 | 待合并 |
| #3400 | `fix(config): persist all api_keys and enabled flag of multi-key models` | 多密钥模型在配置保存时只保留第一个密钥，丢失 `Enabled` 标记，导致每次自动保存都破坏配置。 | 待合并 |
| #3399 | `fix(updater): select the matching 32-bit ARM release asset` | 32 位 ARM 更新时总是下载 arm64 包，因资产名含 `"arm"` 子串匹配错误。 | 待合并 |

这些 PR 直接提升了**核心稳定性**，若能合并，将显著减少配置损坏、崩溃和功能错误。  

- 此外，**#3347**（修复 Web UI 输入卡顿）仍待合并，其作者 iMilnb 已明确表示经过本地测试无卡顿。  

---

### 4️⃣ 社区热点  
1. **#3398 [Notice] Active Fork & Continued Maintenance: afjcjsbx/picoclaw**  
   - 创建者 **afjcjsbx** 公开声明主仓库不再维护，并宣布了一个活跃 fork。该 Issue 虽零评论，但**直接动摇了用户对主项目的信心**。若维护者不迅速回应，可能导致社区迁移。  
   - [链接](https://github.com/sipeed/picoclaw/issues/3398)  

2. **#3405 [Open] Please enable private vulnerability reporting**  
   - 安全研究者 **x1F916**（同日提交多个修复的贡献者）请求启用 GitHub 私有漏洞报告，暗示已发现需私下披露的安全问题。该项目目前缺乏安全政策文件（SECURITY.md）。  
   - [链接](https://github.com/sipeed/picoclaw/issues/3405)  

3. **#3281 [BUG] Web UI chat input lag**  
   - 该 bug 自 7 月 21 日以来已有 15 条评论、2 个 👍，至今未合并修复 PR #3347。用户明显感受到历史会话长时输入卡顿的痛点，频繁在评论区催促。  
   - [链接](https://github.com/sipeed/picoclaw/issues/3281)  

---

### 5️⃣ Bug 与稳定性  
按严重程度排列（结合已存在的修复 PR）：  

| 严重性 | Issue/PR | 问题描述 | 修复状态 |
|---|---|---|---|
| 🔴 严重 | #3404 (Issue) | 核心循环、通道管理、配置、更新器多处可重现的 bug（由 x1F916 在 Issue 中列出，未提供对应单 Issue） | 已提交 #3399~#3403 五个修复 PR，但未合并 |
| 🔴 严重 | #3401 (PR) | 通道重载时 nil 指针 panic，导致网关崩溃退出 | PR 待合并 |
| 🔴 严重 | #3400 (PR) | 多密钥模型配置保存丢失 `Enabled` 和部分密钥，每次自动保存都会破坏配置 | PR 待合并 |
| 🟠 中等 | #3347 (PR) | Web UI 历史一长输入卡顿（对应 #3281） | PR 待合并（已有本地测试通过） |
| 🟡 低 | #3399 (PR) | 32 位 ARM 更新下载 arm64 包，安装失败 | PR 待合并 |
| 🟡 低 | #258 (Issue, 已关闭) | 2 月安全审计发现的严重漏洞（已有修复？但 Issue 被 stale 关闭） | 已关闭，但无对应 Fix PR 证据 |

**注意**：Issue #258（安全审计）已于昨日被关闭，但未关联任何合并的修复 PR，可能已被 stale bot 自动关闭，**存在潜在遗留风险**。

---

### 6️⃣ 功能请求与路线图信号  
- **#3366 – Add support for OpenAI compatible providers**  
  用户希望添加自定义 OpenAI 兼容提供商（如自托管路由器）。该请求有 5 条评论，且已有同类 PR #3397（仅请求添加 Tsubasa 提供商）补充。**若#3366被采纳，可统合多个OpenAI兼容请求**，可能下一版本引入。  
  [链接](https://github.com/sipeed/picoclaw/issues/3366)  

- **#3397 – Add Tsubasa to existing OpenAI-compatible provider catalog**  
  新增 Tsubasa 提供商的小型配置请求。与 #3366 重叠，可并入统一方案。  
  [链接](https://github.com/sipeed/picoclaw/issues/3397)  

- **#3370 – feat(tools): add Keenable web search provider**  
  商业搜索平台 Keenable 作为 web_search 工具提供商。虽功能具体，但**无 API 密钥即可使用**，可能降低新用户使用门槛。PR 待合并。  
  [链接](https://github.com/sipeed/picoclaw/pull/3370)  

- **#3354 – feat(irc): assemble IRCv3 multiline messages**  
  完善 IRC 频道支持，接收多行消息。IRC 用户较专业，但提升 PicoClaw 作为多通道 AI 助手的覆盖度。  
  [链接](https://github.com/sipeed/picoclaw/pull/3354)  

**路线图信号**：OpenAI 兼容提供商的呼声最高（#3366、#3397），且实现成本较低（可直接复用 OpenAI 代码）。下一版本若发布，很可能包含此功能。  

---

### 7️⃣ 用户反馈摘要  
从 Issue 评论中提炼（主要来自 #3281 和 #3366）：  

- **#3281 Web UI 卡顿**：用户“xpader”表示输入框在长历史会话中“非常卡顿”，其他用户附件评论“Same issue here”、“Still not fixed”。一位用户称“我不得不定期清除聊天历史才能继续使用”。**核心痛点**：Web UI 前端渲染未优化，导致大数据量下响应迟钝。  
- **#3366 OpenAI 兼容**：用户“ItachiSan”提出“我希望能使用自托管的 OpenAI 路由，避免数据离开本地”。评论区多位用户赞同，表示“这样就不用依赖特定云供应商了”。**需求本质**：灵活性与隐私控制。  
- **#3404 可靠性修复**：贡献者 x1F916 在 Issue 中描述：“我查阅了核心代码，发现多个可重现的 bug，其中一些曾被报告甚至修复过，但被 stale bot 关闭之前无人关注。” 这表明用户对 **stale bot 自动关闭未解决问题**感到沮丧。  

---

### 8️⃣ 待处理积压  
以下为长期未响应、但影响重大的 Issue 或 PR：  

| 条目 | 创建/最后更新 | 重要性 | 建议行动 |
|---|---|---|---|
| **#3281 Web UI 输入卡顿** | 2026-07-21 / 2026-09-29 | 🔴 影响大量 Web 用户 | 尽快审查、合并修复 PR #3347 |
| **#3366 OpenAI 兼容提供商** | 2026-09-04 / 2026-09-28 | 🟠 高需求，有助于生态扩展 | 确认是否纳入路线图，指派负责人 |
| **#3378 修复 OAuth scope** | 2026-09-12 / 2026-09-28 | 🟠 影响 OAuth 登录 | 回顾配置 scopes 修复，若有测试则合并 |
| **#3222 deltachat 重构** | 2026-07-03 / 2026-09-28 | 🟡 减负代码 200LOC，清理旧特性 | 需要维护者审查重构是否引入回归 |
| **#258 安全审计**（已关闭） | 2026-02-16 / 关闭于 2026-09-28 | 🔴 曾标记 CRITICAL 漏洞，但 Issue 被关闭 | **建议重新打开**，或确认漏洞已修复 |
| **#3405 请求启用私有漏洞报告** | 2026-09-28 | 🔴 安全研究者暗示已发现漏洞 | 立即启用私有报告，添加 SECURITY.md |

---

**总结**：PicoClaw 社区贡献热情不减，但官方维护真空导致修复积压和用户信心动摇。若维护者能及时合并 x1F916 提交的 5 个修复 PR 并回复活跃 fork 声明，项目仍有转机。否则，生态分裂风险将急剧上升。

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域开源项目分析师，这是根据您提供的 NanoClaw 项目数据生成的 2026-09-29 项目动态日报。

---

## NanoClaw 项目动态日报 | 2026-09-29

### 今日速览

过去24小时，NanoClaw 项目维护者表现出极高的活跃度，核心聚焦于 `update-nanoclaw` 更新流程的稳定性修复。虽然无新版本发布，但合并/关闭了 19 个 PR，并解决了多个导致更新流程失败的关键 Bug。当前有 13 个 PR 处于待合并状态，项目整体处于高强度 bug 修复与稳定性增强阶段。社区反馈集中于更新流程的健壮性、代理/网关配置的兼容性以及容器管理的问题。

### 项目进展

今日合并/关闭了 19 个 Pull Request，对项目的稳定性和功能完整性有显著推进：

-   **更新流程 (Update Flow) 可靠性提升**：这是今日修复的核心领域。多個 PR 旨在修复 `/update-nanoclaw` 流程中的问题，包括：
    -   **修复容器清理问题**：`#3948` 修复了更新过程中会错误删除网关（如 Iron Proxy）容器的问题，保证了更新后代理功能可正常使用。
    -   **修复回滚逻辑**：`#3957` 和 `#3956` 分别修复了预任务脚本超时后子进程未被杀死，以及回滚操作未正确停止正在运行的主机进程和代理容器的问题。
    -   **修复配置问题**：`#3949` 修复了 Mattermost 集成在环境变量缺失时运行验证失败的问题。
    -   **修复错误处理**：`#3959` 通过异步化子进程方式，解决了 CI 中因 `spawnSync` 引起的挂起问题。
-   **核心系统健壮性增强**：
    -   `#3958` 修复了日志处理时，序列化非 JSON 数据（如循环引用）导致主机进程崩溃的问题。
    -   `#3946` 优化了技能应用失败时的错误提示，现在会显示具体的失败步骤和原因，而非通用错误信息。
-   **网关与代理适配**：
    -   `#3950` 实现了 Iron 网关对运营商自建本地 CA 证书的信任，支持使用 `https://models.home.arpa/v1` 这样的私有域名访问本地模型，扩展了部署场景。
    -   `#3960` 改进了 OneCLI 适配器的错误信息，使其更清晰地指向凭据而非通用提供者，有助于快速定位问题。
-   **安装与卸载完善**：
    -   `#3883` 确保卸载时干净地移除 Iron Control 的数据库，避免了重新安装时的状态冲突。
    -   `#3920` 限制了安装辅助代理在已有环境中的默认权限，提升了安全性。

### 社区热点

今日社区讨论的焦点高度集中，但评论数普遍偏少。最受关注的是新提交的 **Bug #3961**，因为它直接关联到核心的更新流程。

-   **#3961 [bug] /update-nanoclaw reports phase: complete without restarting the host**：作者报告了在更新后，系统提示更新完成，但后台服务并未实际重启，导致代码未生效。这是一个严重的用户反馈，直接影响了用户对更新流程的信任。
    -   **诉求分析**：用户对更新流程的“可靠性”和“透明度”有极高要求。系统应能准确检测服务状态，并在无法正常重启时明确告警并阻止“完成”状态的错误报告。
    -   **链接**：[#3961](https://github.com/nanocoai/nanoclaw/issues/3961)

*注：其他 Issues 和 PRs 评论量均为零，表明讨论主要集中在新问题的报告和 PR 的技术开发上，而非广泛社区辩论。*

### Bug 与稳定性

今日报告的 Bug 数量不多（4条），但严重性较高，主要影响核心流程。

1.  **[严重] /update-nanoclaw 更新后服务未重启 (#3961)**：作者报告更新流程在后台服务未能成功重启的情况下，错误地报告了“完成”状态。这会导致用户认为更新成功，但实际运行的是旧代码。**目前无 Fix PR 与之直接关联，但 #3962 正在解决更新流程的问题。** [链接](https://github.com/nanocoai/nanoclaw/issues/3961)

2.  **[严重] 更新流程中控制器归档缺失文件 (#3906，已关闭)**：此问题报告了在特定 commit 后，更新流程因为缺少关键文件而失败。该 Issue 已在今日被关闭，表明相关的修复 PR 已被合并。 [链接](https://github.com/nanocoai/nanoclaw/issues/3906)

3.  **[中等] 网关检测在 pnpm 输出警告时失败 (#3907，已关闭)**：一个特定的环境问题，即子进程的标准输出被非预期内容污染，导致网关检测中断。该问题已于今日关闭。 [链接](https://github.com/nanocoai/nanoclaw/issues/3907)

4.  **[低] registry-skills: 测试挂起 6 小时 (#3839，已关闭)**：一个源于工具链的集成测试长时挂起问题，已于今日关闭。 [链接](https://github.com/nanocoai/nanoclaw/issues/3839)

### 功能请求与路线图信号

今日无直接的功能请求 Issue 提交。但从合并的 PR 中可以观察到明确的功能演进方向：

-   **增强本地化部署能力**：`#3950` (信任私有CA) 和 `#3654` (修复 `NO_PROXY` 以访问本地 MCP 服务) 的推进，强烈暗示项目正致力于提升在本地、私有化场景下的部署体验，这可能是许多企业用户或高级用户的关键需求。
-   **改善错误诊断与提示**：`#3946` (显示技能步骤具体错误) 和 `#3960` (改进OneCLI错误信息) 反映了提升可诊断性的趋势，让用户和开发者在遇到问题时能更快定位原因。这将成为提高用户满意度的关键。

### 用户反馈摘要

从今日的 Issues 中，可以提炼出用户明确的痛点：

-   **信任危机**：用户对 `/update-nanoclaw` 流程产生了不信任。Bug #3961 中，用户指出更新成功提示具有欺骗性，因为实际服务并未切换。这表明用户需要一个“高度可验证”的更新流程。
-   **环境兼容性挑战**：用户面临多样化的网络和环境配置问题，如 `pnpm` 工作区输出污染、HTTPS 代理设置时机不当 (#3901)、以及 `host.docker.internal` 在特定网关配置下不可达 (#3654)。用户期望项目能更好地处理各种边缘环境。
-   **对容器管理的关注**：用户反馈 (#3948 修复) 指出，更新流程会错误地删除网关核心容器，导致后续所有功能瘫痪。这揭示了用户对容器，特别是关键基础设施容器的生命周期管理非常敏感。

### 待处理积压

今日无长期未响应的旧 Issue 或 PR。所有待处理项（1个 Bug、13个 PR）均为近两天内新提交，状态健康。值得特别关注的是与更新流程相关的待合并 PR：

-   **#3962 fix(update): refuse cutover when the service liveness probe itself fails**：此 PR 直接回应用户在 #3961 中反馈的“更新后服务未重启”问题，通过加强服务探针检查来阻止错误的更新完成。这是目前最关键的待合并 PR。
    -   **链接**：[#3962](https://github.com/nanocoai/nanoclaw/pull/3962)
-   **#3956 fix(update): rollback stops the live nohup host and drains agent containers**：此 PR 针对回滚逻辑，同样是更新流程稳定性的一部分。
    -   **链接**：[#3956](https://github.com/nanocoai/nanoclaw/pull/3956)
-   **#3963 test(update): remove the data symlink with unlinkSync, not rmSync**：一个修复更新测试套件的 PR，确保其在特定 Node.js 版本上能正常通过，保障了 CI 流程的可靠性。
    -   **链接**：[#3963](https://github.com/nanocoai/nanoclaw/pull/3963)

**维护者建议**：优先合并 #3962，它对稳定用户最关心的更新流程至关重要。随后应关注 #3956 以完善回滚路径。

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

# NullClaw 项目动态日报 | 2026-09-29

## 📊 今日速览

过去24小时内，项目维护者积极处理了16个历史Issue和6个历史PR的关闭/合并，显示维护团队正在集中清扫积压任务。唯一新开的Issue（#764）为社区品牌合作请求，唯一新开的PR（#1013）尝试新增Tsubasa提供商。无新版本发布。整体项目健康度良好，维护响应及时，社区活跃度中等。

---

## 🚀 项目进展

今日共有 **6个PR被合并/关闭**，推进了多项核心功能与修复：

- **#1014 – v20260929**：发布前准备工作，包括：将Web搜索固定为配置的提供商、修复Exa拒绝重复Content-Type报头的Bug、在官方QQ回复前剥离Markdown标记。为下一个补丁版本做准备。  
  [PR #1014](https://github.com/nullclaw/nullclaw/pull/1014)

- **#990 – feat(providers): 新增Eden AI作为OpenAI兼容网关**：通过`OpenAiCompatibleProvider`快速接入Eden AI（欧盟基础），用户只需设置`EDEN_AI_API_KEY`即可使用，扩展了多提供商生态。  
  [PR #990](https://github.com/nullclaw/nullclaw/pull/990)

- **#319 – 修复钉钉消息发送与撤回支持**：将钉钉渠道从纯Webhook升级为官方Bot API，实现OAuth2令牌管理与消息撤回功能，解决了用户反馈的“只发不收”问题。  
  [PR #319](https://github.com/nullclaw/nullclaw/pull/319)

- **#527 – 自适应智能管道 + 邮件/WhatsApp Web渠道**：引入完整的后交互质量循环（Turn Scorer、Skill Router等），同时新增邮件和WhatsApp Web通道。该项目级别PR使NullClaw具备了初步的自我学习和多通道扩展能力。  
  [PR #527](https://github.com/nullclaw/nullclaw/pull/527)

- **#667 – 完整双向邮件IMAP轮询**：将邮件通道从只发送升级为双向IMAP轮询（支持IDLE推送与自动回退HTTP轮询），并增强网络韧性。  
  [PR #667](https://github.com/nullclaw/nullclaw/pull/667)

- **#411 – 工具自定义系统**：实现基于触发词优先级的工具配置系统，用户可为工具预设参数、触发关键词，提升工具调用的灵活性。  
  [PR #411](https://github.com/nullclaw/nullclaw/pull/411)

**项目整体向前迈进一步：** 多提供商支持、通信渠道（钉钉、邮件、WhatsApp）得到实质性增强，工具系统与学习管道开始成型，为后续Agent智能化奠定了基础。

---

## 💬 社区热点

今日讨论热度集中在以下议题（评论数均≥5）：

| Issue | 标题 | 评论 | 链接 |
|-------|------|------|------|
| #861 | How to enable the Web UI on headless VPS server? | 5 | [Issue #861](https://github.com/nullclaw/nullclaw/issues/861) |
| #190 | Subagent spawn | 5 | [Issue #190](https://github.com/nullclaw/nullclaw/issues/190) |
| #354 | Service stops working after Homebrew upgrade | 5 | [Issue #354](https://github.com/nullclaw/nullclaw/issues/354) |
| #376 | DingTalk only supports sending, not receiving | 5 | [Issue #376](https://github.com/nullclaw/nullclaw/issues/376) |
| #619 | Improve error message: `error.ApiError` | 5 | [Issue #619](https://github.com/nullclaw/nullclaw/issues/619) |

**用户诉求分析：**  
- **易用性痛点**：用户eabase直言对README中Web UI配置理解困难（#861），希望获得更通俗的指南。  
- **功能缺失**：钉钉、飞书等IM渠道的“只发不收”问题（#376, #477）是高频反馈，今日PR #319已修复钉钉方向。  
- **升级兼容性**：Homebrew升级后服务失效（#354）是常见平台问题，需改进安装脚本。  
- **错误信息可读性**：用户ats-bcon反馈`error.ApiError`缺乏上下文（#619），希望增强日志友好度。

另外，唯一**OPEN的Issue #764**（添加NullClaw logo到Agent Skills客户端列表）得到5条评论，显示社区有推动项目曝光的需求。  
[Issue #764](https://github.com/nullclaw/nullclaw/issues/764)

---

## 🐛 Bug 与稳定性

今日关闭的Bug类Issue共9条，严重程度均为中等或较低，无崩溃或数据损失报告：

| Issue | 标题 | 严重程度 | 状态 |
|-------|------|----------|------|
| #354 | Homebrew升级后服务停止 | 中 | 已关闭（未关联修复PR） |
| #408 | 工具调用解析错误（冒号误提取为工具名） | 高 | 已关闭（疑似已修复） |
| #477 | 飞书WS断开 | 中 | 已关闭 |
| #665 | `error.NoResponseContent` | 中 | 已关闭 |
| #932 | 文档中Zig版本错误 | 低 | 已关闭 |

**关键修复**：  
- 工具调用解析Bug (#408)：模型生成的合法JSON中的冒号被错误解析为工具名称，今已关闭，表明已在某次合并中修复。  
- 文档Zig版本错误 (#932)：指定Zig 0.15.2导致构建失败，正确版本应为0.16.0，今日关闭说明文档已更新。

**稳定性趋势**：无新报告的高危或回归Bug，项目主力版本趋于稳定。

---

## 🧩 功能请求与路线图信号

用户今日提出的功能请求（从已关闭或OPEN的Issue/PR中识别）及潜在纳入版本的可能性：

| 请求 | 用户呼声 | 当前状态 | 未来纳入可能性 |
|------|----------|----------|----------------|
| 添加`GET /status`端点供外部监控 (#631) | 👍 1 | 已关闭 | **高** — 社区+4个赞，PR #527中的智能管道已包含部分监控概念 |
| 视觉管道：直接向Agent发送图片 (#624) | 0 | 已关闭 | **中** — 用户自建skill实现，但未纳入核心，若需求持续可能列入路线图 |
| 添加ddgs选项用于Web搜索 (#623) | 0 | 已关闭 | **中** — 类似PR #1014已优化搜索配置，但未使用ddgs |
| 改进config.json配置项说明 (#613) | 👍 4 | 已关闭 | **高** — 用户诉求强烈，维护者应已在文档上做出改进 |
| 支持CloudFlare/Nginx隧道 (#495) | 0 | 已关闭 | **低** — 非核心功能，已有官方隧道方案 |

**路线图信号**：  
- **监控能力**：`GET /status` 端点请求（#631）获得较高关注，结合PR #527的智能管道，下一版本很可能加入官方监控端。  
- **配置文档**：改进配置说明（#613）呼声最高（4个赞），维护者已关闭该Issue，推测文档已更新。

---

## 👤 用户反馈摘要

从今日关闭的Issues评论中提取真实用户反馈：

- **“我理解不了README中70%的内容”** – eabase (#861) 表达了对Web UI隧道设置的困惑，希望用人类语言描述。  
- **“作为测试人员，看到`error.ApiError`很沮丧，不知道哪里出了问题”** – ats-bcon (#619) 强调错误信息需要更具体。  
- **“我按文档创建了自定义技能，但Agent无法将其作为工具调用”** – opryshok (#427) 揭示了技能注册与Agent实际调用之间的断层。  
- **“有些配置选项好像没用，对新人不友好”** – balehu86 (#613) 要求增强配置项的说明和默认值示例。  
- **“我用Zig 0.15.2构建失败，看了源码才发现要0.16.0”** – nulldoubt (#932) 指出文档版本错误导致构建浪费。  
- **“钉钉网关显示只发送不接收，CLI却正常”** – Lancernix (#376) 发现IM渠道的双向通信缺失。

**用户满意点**：  
- PR #319 修复钉钉双向通信后，相应Issue (#376) 被关闭，用户问题得到解决。  
- PR #990 新增Eden AI提供商，为欧盟用户提供合规选项。

---

## 📋 待处理积压

当前仅存 **1个OPEN Issue** 和 **1个OPEN PR**，均需维护者关注：

| 编号 | 标题 | 创建时间 | 最后更新 | 建议行动 |
|------|------|----------|----------|----------|
| #764 | Add NullClaw logo to official Agent Skills client list | 2026-04-03 | 2026-09-28 | 已开放近6个月，社区有5条评论。维护者应尽快评估是否加入，并回复社区。 |
| #1013 | feat(providers): add Tsubasa chat-completions provider | 2026-09-28 | 2026-09-28 | 新提交PR，添加Tsubasa提供商。需进行代码审查与测试。 |

**提醒：** 虽然大部分积压已于今日清理，但#764是品牌曝光和社区参与的重要机会，建议优先回应。PR #1013继续沿用`OpenAiCompatibleProvider`模式，风险较低，可快速合并以丰富提供商矩阵。

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

# IronClaw 项目日报 — 2026-09-29

## 今日速览

过去 24 小时内，IronClaw 项目保持了中等活跃度。新增 2 个 Issue（均处于开放状态），其中 1 个为日常失败分类报告，另 1 个涉及新功能请求。Pull Request 方面有 3 条更新，1 条已合并关闭，2 条仍待审查。无新版本发布。项目在稳定性修复（WebUI 路由）、文档维护与代码知识图谱刷新方面有可见进展。

## 项目进展

### 合并/关闭的 PR

- **#5132** — [CLOSED] [fix(webui-v2): redirect invalid chat thread routes](https://github.com/nearai/ironclaw/pull/5132)  
  作者 `flyagents`（新贡献者）。此 PR 修复了 WebUI V2 中无效聊天会话路由的重定向逻辑，确保深链接缺失时会话列表稳定后再判定，同时保留了本地创建/选中的会话活跃状态。该修复为 XL 规模、低风险，增强了前端交互的鲁棒性。这是项目今日唯一合并的 PR，也是新贡献者提交的首个合并请求，对社区参与度有积极信号。

### 待合并的 PR

- **#6698** — [OPEN] [docs: update OpenWiki wiki](https://github.com/nearai/ironclaw/pull/6698)  
  由 `ironclaw-ci[bot]` 自动发起，持续更新 `openwiki/` 叙事文档。已开启 2 个月，需人工审核后合并。
- **#7988** — [OPEN] [chore(agents): refresh codebase knowledge graph](https://github.com/nearai/ironclaw/pull/7988)  
  由 CI 自动生成，更新代码库记忆图谱的快照，维护基础架构健康。

项目整体在用户体验（WebUI 路由）和文档/知识管理（OpenWiki 和知识图谱）两个方向持续投入，但无重大功能上线。

## 社区热点

今日无高互动（评论为 0）的 Issue 或 PR。以下两个新 Issue 虽无讨论但值得关注：

- **#8116** — [Daily ironclaw failure taxonomy — 2026-09-28](https://github.com/nearai/ironclaw/issues/8116)  
  作者 `pranavraja99` 发布了每日失败分类报告，重点分析了 `officeqa` 套件的 31 个未通过任务，指出除 1 个外均为 DeepSeek-V4-Flash 模型自身的质量错误。该报告为持续集成过程中的质量监控信号，可能引发对模型评估流程的讨论。
- **#8115** — [Add a Tsubasa registry entry with an explicit 32K context-budget path](https://github.com/nearai/ironclaw/issues/8115)  
  用户请求为 Tsubasa 提供商添加显式注册表条目，以避免手动配置端点/模型。这反映了用户对简化多模型配置的需求，属于功能请求。

## Bug 与稳定性

- **#5132（已合）** — 修复了 WebUI V2 中无效聊天路由导致的页面异常，属于用户体验稳定性改进。无严重等级 Bug 被报告。
- **#8116** 中提及的 31 个未通过任务基本被判定为模型质量错误，非 IronClaw 本身的代码缺陷，但持续监控有助于评估基准测试的可靠性。

当前无新引入的崩溃或回归问题。

## 功能请求与路线图信号

- **#8115** — [Add a Tsubasa registry entry with an explicit 32K context-budget path](https://github.com/nearai/ironclaw/issues/8115)  
  用户要求将 Tsubasa 作为命名提供商集成，以减少手动输入端点与模型的步骤。IronClaw 已有 OpenAI 兼容后端，该请求属于 UI/UX 层面的配置简化。鉴于项目近期在 WebUI V2 上的投入，此功能有可能被纳入下一迭代版本，但尚无对应 PR 追踪。

其他未发现明确路线图信号。

## 用户反馈摘要

今日所有 Issue 和 PR 评论均为 0，未收集到直接的用户反馈。从 Issue 内容可以推测：
- 用户 `pranavraja99`（可能是维护者或重度测试者）持续关注基准测试失败模式，反映项目对评估质量的重视。
- 用户 `cenab` 提出 Tsubasa 配置痛点，说明多模型支持场景下配置的便利性仍需改善。

## 待处理积压

以下 PR 长期未响应，建议维护团队优先评审：

- **#6698** — OpenWiki 文档刷新（开启 64 天，由 CI 生成，需人工审批）
  → 链接：[nearai/ironclaw PR #6698](https://github.com/nearai/ironclaw/pull/6698)
- **#7988** — 代码知识图谱刷新（开启 31 天，CI 生成，需正常合并）
  → 链接：[nearai/ironclaw PR #7988](https://github.com/nearai/ironclaw/pull/7988)

此外，今日新开的 **#8116**（失败分类）和 **#8115**（功能请求）均暂无响应，但因其时效性较高（分类报告为日更），建议尽快回顾并标注后续行动。

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

# LobsterAI 项目动态日报 | 2026-09-29

## 1. 今日速览

过去 24 小时项目活跃度显著回升，共处理 5 条 Issue 和 14 条 Pull Request。其中 13 条 PR 已合并/关闭，仅 1 条依赖更新 PR 待合并；功能交付集中在对 **OpenClaw 网关** 的稳定性修复（启动死锁、超时处理、锁清理）以及 **Cowork 协作面板** 与 **文档编辑** 等新能力的落地。Issue 方面无新增报告，5 条均为 3 月遗留的旧问题被标记为 stale 后重新更新状态，说明维护者正在清理历史积压。整体来看，项目正在从 `release/2026.9.24` 分支的收尾阶段迈向新版本迭代，核心组件可靠性得到提升。

---

## 2. 版本发布

**无**（过去 24 小时内无新版本 Release）

---

## 3. 项目进展

### 3.1 核心功能：OpenClaw 网关稳定性与诊断大幅改善

- **PR #2775** `fix(openclaw): start the gateway once on app launch`  
  修复应用启动时 OpenClaw 网关被重复启动三次的问题（IM 频道同步导致），减少启动等待时间约 80 秒。  
  → 已合并至 `release/2026.9.24`

- **PR #2774** `fix(openclaw): improve repair timeout handling and diagnostics`  
  一键修复命令从固定 60 秒超时改为基于输出活动的有界等待（至少 5 分钟，最长 15 分钟静默终止），并保存诊断日志，避免慢配置校验被提前打断。  
  → 已合并

- **PR #2772** `fix(openclaw): skip orphan non-ASCII agent dirs when counting legacy session stores`  
  移除纯中文 Agent 目录被错误计入旧会话统计导致启动死锁的问题。  
  → 已合并

- **PR #2771** `fix(openclaw): reclaim gateway locks whose recorded PID was reused`  
  Windows 下非正常关闭后，网关锁文件记录的 PID 可能被系统或其他进程重用，导致后续启动和一键修复失败。改用 SQLite 排他事务锁检测替代 PID 检查。  
  → 已合并

- **PR #2773** `test(openclaw): verify legacy session discovery recovery`  
  补充旧会话目录修复的回归测试与验收记录，确保 #2772 的改动不会引入新问题。  
  → 已合并

### 3.2 新能力：Cowork 协作面板体验优化与文档编辑支持

- **PR #2778** `feat(cowork): show OpenClaw progress cards above the composer`  
  Agent 使用 `progress_card` 工具生成的计划卡片现在会显示在输入框上方，用户可实时查看任务进度，而非仅看到原始工具调用记录。  
  → 已合并

- **PR #2777** `feat(cowork): keep long running turns to their latest five steps`  
  长耗时操作（如 DeepSeek 模型连续调用工具数分钟）不再刷屏，仅保留最近 5 步，大幅降低对话干扰。  
  → 已合并

- **PR #2776** `feat: support ppt/word/excel document editing`  
  新增对 PowerPoint、Word、Excel 文档的编辑支持（通过 OpenClaw 集成），覆盖了 `area: openclaw, skills, artifacts` 等多个模块。  
  → 已合并

### 3.3 安全与遗留问题修复

本周另有 6 条从 3 月积压的 PR 被统一关闭（标记为 stale 后确认修复），包括：
- `fix(agent): fix Create Agent modal overflow problem` (#969)
- `fix(security): reject protocol-relative URLs in markdown link transform` (#974)
- `fix(im): xiaomifeng gateway unrecoverable after kicked-offline event` (#975)
- `fix(security): shell:openExternal IPC 接口未校验 URL 协议` (#1034)
- `fix(openclaw): fix node not found on Windows when WSL and Git Bash coexist` (#1037)
- `fix(im): NimGateway 重连后消息去重缓存未清空` (#1035)

这些修复此前已于 2026 年 3–4 月合入，本次标记为最终关闭以清理 backlog。

---

## 4. 社区热点

过去 24 小时内未产生高讨论量的 Issue 或 PR（所有公开 Issue 评论数 ≤2）。最受关注的仍是 3 月份报告的几个用户错误场景，虽被标记为 stale 但尚未关闭：

- **#968** 自己新建的 Agent 使用 skill-creator 查询杭州天气预报，浏览器数据不准确且无法关闭  
  → 评论区较少，但截图显示功能异常，可能属于技能工具链兼容性问题。

- **#972** 使用 QWEN 模型时，关闭模型并保存后卡在“AI引擎正在启动网关”，再连接仍不可用  
  → 该问题可能与 #2775 修复的网关重复启动有关，建议用户升级到包含 #2775 的版本后验证。

- **#973** macOS 快捷设置中错误显示 Ctrl 而非 ⌘ 键  
  → 体验细节问题，三月底报告后未收到回复，建议维护者确认是否已修复或排期。

---

## 5. Bug 与稳定性

今日无新增 Bug 报告。历史遗留 Bug 中，严重程度较高且已有对应 fix 的有：

| Issue | 问题描述 | 严重程度 | 是否有 fix PR |
|-------|----------|----------|--------------|
| #1035 (已关闭) | NimGateway 重连后消息去重缓存未清空，导致正常消息被丢弃 | **高**（数据丢失） | PR #1035 已合并 |
| #972 | 关闭模型后网关状态死锁，无法恢复 | **高**（功能不可用） | 可能已被 PR #2775 覆盖 |
| #1034 (已关闭) | `shell:openExternal` IPC 未校验 URL 协议，存在任意协议风险 | **中**（安全） | PR #1034 已合并 |
| #973 | macOS 快捷键显示 Ctrl 而非 ⌘ | **低**（体验） | 无对应 fix |

---

## 6. 功能请求与路线图信号

- **文档编辑（PPT/Word/Excel）**：PR #2776 已实现，预计纳入下一版本发布。
- **Cowork 协作可视化增强**：PR #2778（进度卡片）和 PR #2777（步骤折叠）表明项目正在打磨用户可见的 Agent 执行流程，未来可能进一步支持交互式暂停/编辑。
- **Gateway 启动优化**：多 PR 集中修复启动死锁、锁冲突，说明团队正努力降低用户的初始等待焦虑，该方向可能在后续版本中引入更优雅的状态提示。

未发现用户明确提出的全新功能需求。

---

## 7. 用户反馈摘要

从 Issues 评论（尽管数量有限）提炼：

- **“AI 引擎正在启动网关”循环弹窗**（#972）：用户描述关闭 QWEN 模型后返回主界面就一直弹窗，连接成功也无法使用。这是典型的网关状态机 bug，社区用户希望能自主重置网关或获得更清晰的错误提示。
- **天气预报技能结果不匹配**（#968）：用户期望 Agent 查询杭州天气，但浏览器显示的地理位置错误。可能与 skill-creator 的坐标解析或默认浏览器行为有关，属于工具链端到端测试的盲区。
- **模型内容输出混乱**（#971）：生成小说封面却输出大量无关内容。可能是 prompt 模板或工具选择问题，但仅有一条评论，缺乏更多上下文。

---

## 8. 待处理积压

以下为长期未响应的开放 Issue，可能因未复现或缺乏优先级被搁置，建议维护者下周重新评估：

| 编号 | 标题 | 创建/更新日期 | 最后评论 |
|------|------|--------------|----------|
| #968 | 自己新建的 Agent 中，skill-creator 查询杭州天气预报弹窗数据不对且无法关闭 | 2026-03-27 / 2026-09-28 | 1 |
| #971 | 内容输出错乱，答非所问 | 2026-03-27 / 2026-09-28 | 1 |
| #972 | 使用 QWEN 模型后卡在“AI引擎正在启动网关”弹窗 | 2026-03-27 / 2026-09-28 | 1 |
| #973 | macOS 快捷键显示 Ctrl 而非 ⌘ | 2026-03-27 / 2026-09-28 | 1 |
| #1277 | [OPEN] chore(deps-dev): bump the electron group | 2026-04-02 / 2026-09-28 | 待合并 |

其中 #1277 是 Dependabot 提出的依赖更新（Electron 43 → 44），已长期未合入，建议在下一个版本窗口前评审合并，以跟进安全修复。

---

**总结**：项目过去 24 小时以技术债务清偿和稳定性优化为主基调，OpenClaw 网关的几项修复直接解决了用户报告的“启动死锁”和“重复网关”痛点；同时 Cowork 协作面板的体验改进和文档编辑功能为后续版本增加了鲜明亮点。维护团队应趁势关闭 #968/#971/#972 等遗留问题，并推动 #1277 的依赖更新，保持项目健康度持续向好。

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

过去24小时无活动。

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

# Moltis 项目动态日报 — 2026-09-29

## 1. 今日速览

- 项目过去24小时未产生新的Issue，也未关闭任何Issue，社区活跃度偏低，表明项目当前处于功能开发收敛阶段。
- 有一项PR#1288处于待合并状态，旨在为模型注册表新增“Tsubasa”提供商，属于向OpenAI兼容生态的扩展。
- 无新版本发布，项目整体运行平稳，但缺少用户反馈与Bug报告，可能意味着测试覆盖或社区参与度有待提升。
- 代码库健康度良好，主要精力集中在单一PR的完善与合并准备上。

## 2. 版本发布

无。

## 3. 项目进展

- **待合并 PR：** [`#1288`](https://github.com/moltis-org/moltis/pull/1288) – feat: add Tsubasa provider to setup and model registry  
  **作者：** cenab  
  **状态：** OPEN  
  **摘要：** 该PR将Tsubasa集成到现有的提供商设置和OpenAI兼容注册表中。Provider使用环境变量 `TSUBASA_API_KEY`，默认API端点 `https://api.tsubasa.sh/v1`，并注册了 `tsubasa-fast` 和 `tsubasa-pro` 两个模型，均支持32,768 token的上下文窗口。同时更新了配置名称验证、模板生成逻辑和README文档。  
  **意义：** 此项扩展使得Moltis能够支持更多第三方推理服务，增强了模型选择的灵活性，向多提供商架构进一步迈进。目前该PR尚未合并，需关注后续review与CI状态。

## 4. 社区热点

今日无讨论活跃或评论多的Issue/PR。PR#1288尚未产生评论或反响，社区关注度较低。

## 5. Bug 与稳定性

今日未报告任何Bug、崩溃或回归问题。

## 6. 功能请求与路线图信号

- 虽然今日无新功能请求Issue，但PR#1288的提交（新增Tsubasa提供商）暗示社区或维护者有意扩充对非官方OpenAI兼容服务的支持。这可能是路线图中“多提供商统一接口”方向的一步。
- 该PR引入的模型参数（32k上下文）也为后续支持更长上下文模型提供了模板。

## 7. 用户反馈摘要

今日无用户反馈或评论。

## 8. 待处理积压

- 当前无长期未响应的Issue或PR。PR#1288已在一天内得到关注，但尚未被合并或review。建议维护者尽快安排代码审查，避免积压。

---

**总结：** Moltis今日处于低活跃的稳定期，唯一的变化是待合并的Tsubasa提供商支持。项目缺乏社区互动，维护者可适当引导用户参与测试或反馈。下一步应推进PR#1288合并，并持续关注新供应商接入后的兼容性测试。

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

⚠️ 摘要生成失败。

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

# ZeptoClaw 项目动态日报  
**日期：2026-09-29**  
*数据来源：[GitHub - qhkm/zeptoclaw](https://github.com/qhkm/zeptoclaw)*  

---

## 1. 今日速览  
- 过去24小时项目活跃度**中等**：新增2个Issue（均为开放状态）、1个Pull Request（待合并），无版本发布。  
- 社区出现一个**功能询问**：用户询问是否存在类似 ohmypi 的 `/goal` 模式，暗示对持续运行/条件终止代理的需求。  
- 开发者提交了一个**高优先级PR**（#708），旨在解决工具输出被截断后彻底丢失的问题，对应Issue #707标记为 P2-high。  
- 项目整体健康度良好：无新Bug报告，核心开发仍在推进关键特性。

---

## 2. 版本发布  
*暂无新版本发布。*  

---

## 3. 项目进展  
- **PR #708（OPEN）**：`feat(tools): spill oversized tool output instead of discarding it`  
  作者 qhkm 提交了该PR，将工具输出超过预算（>2000行/50KB）时原本被截断并丢弃的字节，**写入 `~/.zeptoclaw/sessions/<key>/spill/` 目录下**，并在上下文中替换为预览、文件路径及一行摘要。  
  - 影响组件：`shell`、`grep`、`filesystem`、`find`（均调用 `truncate_tool_output`）  
  - 此举**从根本上解决了模型无法访问截断信息的痛点**，属于架构级改进。  
  - 当前状态：待合并，未发现冲突或负面评论。  
  - [链接](https://github.com/qhkm/zeptoclaw/pull/708)

---

## 4. 社区热点  
### 最受关注 Issue：**#709** – `is there a goal mode?`  
- 作者：abda11ah  
- 创建/更新：2026-09-28  
- 评论数：0 | 🏷️ 需求讨论  
- 核心诉求：用户期望 ZeptoClaw 能支持类似 ohmypi（omp）中的 `/goal` 模式，即代理**持续工作直到某个条件被满足**。  
- 虽然目前无评论，但该提问反映了真实用户场景——**需要长时、条件驱动的自主代理**，对路线图有潜在参考价值。  
- [链接](https://github.com/qhkm/zeptoclaw/issues/709)

### 高优先级 Issue：**#707** – `[feat, area:tools, P2-high] spill oversized tool output`  
- 作者：qhkm  
- 匹配的PR #708 已提交，社区暂无额外讨论，但该功能被标记为 P2-high，说明维护者重视。  
- [链接](https://github.com/qhkm/zeptoclaw/issues/707)

---

## 5. Bug 与稳定性  
- **今日未报告任何 Bug、崩溃或回归问题**。  
- 所有活跃记录均为功能请求/增强，项目稳定性当前未见风险。

---

## 6. 功能请求与路线图信号  
| Issue/PR | 需求描述 | 纳入下一版本可能性 | 备注 |
|----------|----------|--------------------|------|
| [#709](https://github.com/qhkm/zeptoclaw/issues/709) | 增加 `/goal` 模式，支持代理持续运行直到条件满足 | **中等**（需设计实现，已有社区呼声） | 无关联PR，需等待维护者评估 |
| [#707/PR#708](https://github.com/qhkm/zeptoclaw/issues/707) | 工具输出超限时写入本地文件而非丢弃 | **高**（PR已提交，P2-high） | 极可能合并至下一个正式版本 |

**路线图信号**：项目当前着力改善工具输出处理机制，提升模型对长输出的可访问性；同时用户对“持续执行模式”表现出兴趣，可能成为下一阶段功能候选。

---

## 7. 用户反馈摘要  
- **用户提问（#709）**：明确对比 ohmypi 的 `/goal` 模式，说明 ZeptoClaw 当前缺乏这一能力，用户可能来自 CLI 多步骤自动化场景。  
- **无其他评论**：由于两天内数据有限，暂时没有更多用户满意/不满意反馈。  
- 总体而言，社区主要表达了对**代理持续性执行**的期待，以及对**截断数据可恢复性**的工程改进（由开发者主动发起）。

---

## 8. 待处理积压  
- **无长期未响应的重要 Issue/PR**。  
- 但可关注：  
  - **#709** 创建接近24小时，尚未有维护者回复，建议尽早跟进以收集更多需求细节。  
  - **PR #708** 等待审核与合并，若有冲突或测试问题应及时协调。  

---

**报告结束**  
*本日报由 AI 分析师生成，基于截至 2026-09-29 的 GitHub 公开数据。*

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

好的，作为 AI 智能体与个人 AI 助手领域的开源项目分析师，我已根据 ZeroClaw 项目 (github.com/zeroclaw-labs/zeroclaw) 提供的 GitHub 数据，生成了 2026-09-29 的项目动态日报。

***

# ZeroClaw 项目动态日报 | 2026-09-29

**项目整体健康度评估：高活跃度 / 高压力**。项目今日维持了极高的开发与协作强度，Issues 和 PR 处理量均达到 50 条。尽管无新版本发布，但核心推进显著，特别是在安全加固、配置系统演进以及运行时功能补全方面。然而，高优 Bug 频发（如数据丢失、安全权限绕过）和大量 PR 的长时间等待合并，表明项目在性能和稳定性的快速迭代中正经历 “技术债务偿还” 与 “新功能交付” 并行的压力期。

---

### 1. 今日速览

- **极高活跃度**：过去24小时内，项目处理了50条Issues和50条PR，但合并与关闭率较低（Issues关闭率50%，PR合并/关闭率22%），表明大部分精力仍在审核与讨论环节。
- **安全与稳定性是主旋律**：今日关闭和活跃的议题中，大量涉及数据丢失风险（S0级）、权限绕过和配置错误，尤其是针对多租户安全、会话恢复的权限状态、以及成本核算等问题。
- **重大功能推进**：事件系统（Observer）和配置架构（Schema V4）的里程碑式 PR 已合并，为后续开发奠定了更稳固的基础。同时，数个大型功能PR（如会话提示词挂载、代理循环重构）正在积极审核中。

---

### 2. 版本发布

**无新版本发布**。

---

### 3. 项目进展

今日合并/关闭了数个对项目架构和稳定性至关重要的 PR，标志着项目核心基础设施的进一步完善。

- **事件系统核心化**：PR [#11131](https://github.com/zeroclaw-labs/zeroclaw/pull/11131) (feat(runtime): own the observer event firehose in the daemon) **已合并**。这是一个关键性合并，它将事件观察总线 (`BroadcastObserver`) 的所有权从可选的网关层转移到了核心守护进程（daemon）。这意味着即使在不运行网关的情况下，RPC 客户端（如 ZeroCode， TUI）也能通过 `logs/subscribe` 实时获取事件，解决了之前运行时纯守护进程模式下事件丢失的问题。
- **配置系统演进**：PR [#11218](https://github.com/zeroclaw-labs/zeroclaw/pull/11218) (fix(config): migrate retired keys at schema V4) 和 [#11217](https://github.com/zeroclaw-labs/zeroclaw/pull/11217) (fix(config): stop migrating current-format configs that omit schema_version) **已合并**。这两项合并共同推进了配置系统向 Schema V4 的演进。V4 版本清理了已废弃的配置项，并修复了因 `schema_version` 字段缺失导致配置文件被错误迁移的问题，提高了配置加载的准确性和性能。
- **关键安全修复**：多个涉及安全性和数据丢失的 Bug 在今日关闭，对应的修复 PR 已合并或正在审核。例如：
  - 修复了并发文件编辑导致数据丢失的 [#11136](https://github.com/zeroclaw-labs/zeroclaw/issues/11136) 已被标记为关闭。
  - 修复了成本跟踪系统中 Anthropic 提供者始终报告 $0.00 消费的 [#9816](https://github.com/zeroclaw-labs/zeroclaw/issues/9816) 已被关闭。
  - 修复了 `block_high_risk_commands = false` 配置不生效的 [#10164](https://github.com/zeroclaw-labs/zeroclaw/issues/10164) 已被关闭。

**总结**：项目在核心运维和基础设施层面（事件系统、配置管理、安全漏洞修复）迈出了坚实的一步，为后续更高阶功能（如插件、高级认证）的稳定运行提供了保障。

---

### 4. 社区热点

今日讨论最热烈的话题主要集中在以下几个长期悬而未决、影响广泛的设计提案和技术债问题上：

- **RFC投票流程简化**：[#10549](https://github.com/zeroclaw-labs/zeroclaw/issues/10549) (RFC: Simplify RFC voting by removing mandatory discussion windows) 以 12 条评论成为今日讨论焦点，且已被关闭。该提案旨在取消强制性的讨论窗口期（48/72小时），并引入“修订即停止当前快照”的机制，以加速内部决策。该 RFC 被迅速接受并关闭，说明社区对提升内部治理效率有高度共识。
- **多租户安全与身份访问**：[#5982](https://github.com/zeroclaw-labs/zeroclaw/issues/5982) (Feature: Per-sender RBAC for multi-tenant agent deployments) 和 [#8289](https://github.com/zeroclaw-labs/zeroclaw/issues/8289) (OIDC milestone) 持续获得高关注。这反映了社区对于企业级部署场景下，细粒度权限控制和标准身份认证集成的迫切需求。相关的 PR [#10592](https://github.com/zeroclaw-labs/zeroclaw/pull/10592) (relay claim) 和 [#10573](https://github.com/zeroclaw-labs/zeroclaw/issues/10573) (网关配对令牌绑定) 正在同步推进，是项目向企业级迈进的关键信号。
- **插件生态扩展**：[#8832](https://github.com/zeroclaw-labs/zeroclaw/issues/8832) (Plugin-owned Kanban board for agent work) 有 9 条评论。这表明社区对插件的能力边界抱有更高期望，希望插件不仅能提供工具，还能拥有独立的持久化状态和交互界面（如看板）。当前项目已通过 [#11081](https://github.com/zeroclaw-labs/zeroclaw/pull/11081) 交付了 “每个实例的持久化状态” 基础，社区正积极推动在此之上构建具体的插件应用。

---

### 5. Bug 与稳定性

今日报告的 Bug 主要集中在 **数据丢失** 和 **安全风险** 两大类别，多被标记为最高严重级别 (S0)。

- **S0 - 数据丢失：**
  - **[已关闭] #11136** [[链接](https://github.com/zeroclaw-labs/zeroclaw/issues/11136)]：高优 Bug。在 `parallel_tools` 模式下，对同一文件的并发 `file_edit/file_write` 调用会静默丢失其中一个编辑结果，构成数据丢失风险。
- **S0 - 安全风险：**
  - **[开放] #11197** [[链接](https://github.com/zeroclaw-labs/zeroclaw/issues/11197)]：严重安全漏洞。当管理员撤销 `admin` 权限后，通过**恢复会话（session resume）** 操作，用户依然可以访问之前被授予的转发环境变量。这是一个权限状态的缓存不一致问题。已有修复 PR 关联。
  - **[已关闭] #10121** [[链接](https://github.com/zeroclaw-labs/zeroclaw/issues/10121)]：ZeroCode 进程在 Code/ACP 轮次完成前退出，会导致部分结果丢失。该问题已被修复。
- **S2 - 功能退化：**
  - **[已关闭] #10186** [[链接](https://github.com/zeroclaw-labs/zeroclaw/issues/10186)]：终端回退文本路径绕过了部分实时交付接口，可能导致用户看到的信息不完整或错误。
  - **[已关闭] #9708** [[链接](https://github.com/zeroclaw-labs/zeroclaw/issues/9708)]：守护进程的 `stdout` 和 `stderr` 日志文件缺少大小和轮转限制，可能导致磁盘空间耗尽。

**稳定性信号**：高优先级 (P0/P1) 的 Bug 修复速度快，显示项目对稳定性的重视。但层出不穷的安全类 Bug（如会话状态恢复、权限检查不一致）也暗示了复杂的安全模型在实现上仍然脆弱。

---

### 6. 功能请求与路线图信号

今日的 Issues 和 PR 揭示了未来版本可能的演进方向，主要集中在插件生态和细粒度身份访问控制。

- **插件生态的深化**：**`topic:plugins`** 相关的议题持续活跃。
  - **插件看板**：`#8832` 讨论的是插件拥有自己的看板，这暗示了未来插件可能不仅仅是工具集合，而是可以成为具有 UI 和工作流能力的“应用”。
  - **编译时特性标志移至运行时插件**：`#8850` 要求将可选的频道（Channels）和工具（Tools）从编译时的 feature flag 迁移至运行时的插件，这将是提升系统模块化和部署灵活性的重大改进，已被纳入 `type:tracker` 跟踪。
  - **SaaS 工具门控**：PR `#11221` 提议将一堆 SaaS 工具（Jira， Notion 等）隐藏在编译期 feature 之后。这与 `#8850` 的方向一致，但更偏向于二进制体积优化。如果社区接受 `#8850` 的方案，则 `#11221` 可能是一种过渡或作为可选方案。

- **身份与访问控制是企业级应用的核心**：**`topic:identity-access`** 标签下的工作依然是第一优先级。
  - **OIDC里程碑收尾**：`#8289` 作为 OIDC 集成的收尾跟踪器，今天被关闭。这表明 OIDC 的基础栈已完全合并。接下来的重点将是利用这个基础，实现更高级的用例。
  - **网关配对令牌**：`#10573` 要求将网关配对令牌绑定到已有的用户（roster users）上，以实现基于角色的远程访问。这被标记为已接受的后续工作，有望在下一版本（v0.9）中落地。

---

### 7. 用户反馈摘要

从 Issues 的评论中可以提炼出以下用户关注点：

- **配置系统复杂性**：多位贡献者（如 `JordanTheJet`）在 PR `#11218` 和 `#11217` 的评论中详细讨论了配置迁移的历史遗留问题。反馈显示，用户手写或模板生成的配置文件容易因缺少 `schema_version` 字段而被错误解析，导致非预期的行为。新的 V4 方案旨在解决此痛点，使配置处理更透明、可预测。
- **对清晰权限模型的渴求**：`#5982` 的评论中，用户期望一个独立的 `[rbac.*]` 子系统，但最终社区决策将其建立在现有的 `agent/risk-profile` 模型上，以降低复杂性。这反映了社区在 “灵活性” 和 “可维护性”之间的权衡，最终倾向于后者。用户普遍接受了这个折衷方案。
- **成本核算的信任危机**：`#9816` 中用户 `bitsbyritik` 报告，由于 Anthropic 提供者成本始终显示为 $0，导致每日/每月预算上限检查完全失效。这对于依赖预算控制来管理费用的用户是重大痛点。该 Bug 的迅速关闭（已修复）应该能显著提升用户对成本管理功能的信任度。
- **对“胶水代码”的反感**：在 `#10549` 讨论 RFC 流程简化时，社区普遍认为强制性的讨论窗口期是“不必要的摩擦”。成员们倾向于认为，如果大家对某个方向有共识，就不应被固定的时间窗口所强制延迟。这体现了开源社区追求高效、扁平的决策文化。

---

### 8. 待处理积压

以下是一些长期未响应或关键路径上的待办项，需要维护者特别关注。

- **重要 PR 等待审核与合并**：
  - [#10391](https://github.com/zeroclaw-labs/zeroclaw/pull/10391) (fix(delegate): bounded delegate filesystem tools) **已开放34天**，标记为 `size:XL` 和 `risk:high`。这个 PR 旨在修复委派工具的文件系统边界问题，对于多租户和插件生态至关重要，但其庞大的代码变更量可能是主要障碍。
  - [#10407](https://github.com/zeroclaw-labs/zeroclaw/pull/10407) (feat(sessions): add persistent session prompt attachments) **已开放33天**，同样是 `size:XL`。这是一个呼声很高的功能，但因其改动范围涉及几乎所有频道和工具，审核难度大。作为对比，其相关的跟踪 Issue `#9475` 可能已经被关闭或状态更新。
  - [#10592](https://github.com/zeroclaw-labs/zeroclaw/pull/10592) (feat(relay): self-serve enrollment via `relay claim`) **已开放26天**。此 PR 是 `topic:zerorelay` 路线图的关键部分，直接影响到用户通过 ZeroRelay 进行自服务的体验。它依赖的底层 PR [#10525](https://github.com/zeroclaw-labs/zeroclaw/pull/10525) 已合并，本 PR 应优先处理。

- **关键 Issue 需分配负责人**：
  - [#11197](https://github.com/zeroclaw-labs/zeroclaw/issues/11197) [Bug]: Session resume restores forwarded environment after admin revocation **S0级安全风险**。虽然已被接受并有 follow-up 标签，但应明确指定负责开发的工程师，并优先分配资源，避免安全漏洞长期暴露。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*