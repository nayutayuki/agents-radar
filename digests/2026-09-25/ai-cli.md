# AI CLI 工具社区动态日报 2026-09-25

> 生成时间: 2026-09-25 00:47 UTC | 覆盖工具: 9 个

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

好的，作为专注于 AI 开发工具生态的资深技术分析师，以下是根据您提供的各工具社区日报生成的横向对比分析报告。

---

### AI CLI 工具生态横向对比分析报告 (2026-09-25)

#### 1. 生态全景

当前 AI CLI 工具生态正处于 **“拼刺刀”的存量博弈与差异化突围并存** 的阶段。一方面，所有工具都深陷于稳定性、沙箱安全、MCP 生态和用户体验的“基础设施”攻坚战中，**“能用”向“好用”的进化阵痛**是普遍主题。另一方面，各工具基于其背后的大模型能力和商业策略，在**会话协作、Agent自主性、IDE集成深度、以及特定硬件/模型支持**上开始拉开差距。生态整体呈现出“一超多强，但各有隐忧”的态势，没有绝对的代差优势，社区对Bug修复和体验打磨的耐心正在被消耗。

#### 2. 各工具活跃度对比

| 工具 | 新/活跃 Issues (24h) | 重要 PR (24h) | 版本发布 (24h) | 核心关注点 |
| :--- | :--- | :--- | :--- | :--- |
| **Claude Code** | 10 | 5 | 1 | Cowork Git授权、自动记忆透明度、MCP会话ID |
| **OpenAI Codex** | 10 | 10 | 6 | Windows卡顿、沙箱GPU支持、MCP缓存失效 |
| **Gemini CLI** | 10 | 10 | 1 | 子Agent行为异常、文件并发冲突、无限认证循环 |
| **Copilot CLI** | 10 | 1 | 2 | OOM崩溃、会话创建失败、认证令牌失效 |
| **Kimi Code CLI** | 0 | 1 | 0 | 社区静默期，仅一次安全依赖升级 |
| **OpenCode** | 10 | 10 | 0 | V2 schema失效、账号误封、MCP冷启动失败 |
| **Pi** | 10 | 10 | 0 | 配置忽略、TUI重绘风暴、多模型兼容性 |
| **Qwen Code** | 10 | 10 | 4 | 进程泄漏、TUI崩溃、Managed Agent双路径架构 |
| **DeepSeek TUI** | 10 | 10 | 0 | 子Agent预算死亡、压缩失败、新手引导缺失 |

**小结**：
- **高产梯队**：Claude Code, OpenAI Codex, Gemini CLI, OpenCode, Pi, Qwen Code 均保持着极高的社区互动和开发迭代节奏。
- **稳健梯队**：Copilot CLI 虽然问题多，但版本发布稳定，处理补丁积极。
- **静默梯队**：Kimi Code CLI 社区活跃度极低，处于“准休眠”状态，这是一个危险信号。
- **特殊案例**：DeepSeek TUI 虽然无新版本，但由创始人主导的“安全审计”带来了大量的高质量 Issue 和 PR，是一种高质量的“集中攻坚”模式。

#### 3. 共同关注的功能方向

AI CLI 工具虽然在实现细节上各异，但社区反映的共性需求非常集中：

1.  **会话与任务管理（7个工具提及）**：Claude Code (Cowork，#76248)、Copilot CLI (#4742, #2058)、Qwen Code (#12380)、OpenCode (#51244)、Pi (#9255) 均涉及会话分支、恢复、持久化及多会话隔离的问题。**核心诉求是支持更灵活、更可靠的工作流组织**。
2.  **MCP 生态基础建设（6个工具提及）**：Claude Code (#41836)、OpenAI Codex (#33266)、Gemini CLI (#29446)、Copilot CLI (#4948)、Qwen Code (#12562)、OpenCode (#48743) 等均暴露了MCP连接稳定性、缓存机制、会话标识、以及冷启动问题。**MCP协议的基础设施仍显脆弱，缺乏统一的会话标识和故障恢复标准**。
3.  **沙箱与安全性（6个工具提及）**：OpenAI Codex (#3141)、Gemini CLI (#22672, #29492)、Copilot CLI (#3534)、Pi (#9361)、DeepSeek TUI (#6555) 都涉及沙箱功能（GPU支持、Shell注入防护、路径安全）。**用户期望在“安全”与“可用性”之间找到更好的平衡点，并对安全策略的透明度有更高要求**。
4.  **配置与UI一致性（5个工具提及）**：OpenCode (#43748)、Pi (#9361, #9566)、DeepSeek TUI (#6563)、Claude Code (#95813)、Gemini CLI (#22267) 均报告了**配置项不生效、schema错误、或UI显示与预期不符**的问题。这反映出配置系统的健壮性和文档一致性是共同的短板。

#### 4. 差异化定位分析

| 工具 | 核心定位 | 差异化优势 | 主要短板 |
| :--- | :--- | :--- | :--- |
| **Claude Code** | 协作式计算（Cowork）与多模型支持 | 强模型（Opus）驱动的复杂任务分解，Cowork模式潜力大 | Cowork集成阵痛多，配置项失效（sandbox, totalTokensReminder） |
| **OpenAI Codex** | 深度集成IDE的桌面端AI工作台 | Windows桌面体验最丰富（App），与Codex模型、VS Code无缝联动 | Windows稳定性积重难返（渲染器、沙箱、卡顿），问题复现率高 |
| **Gemini CLI** | 面向子Agent编排的通用生产力工具 | 子Agent架构内建，多模型支持，灵活的Skills/Sub-agent扩展 | 子Agent行为不透明、故障多，配置系统复杂且易失效，导致开发者信任度下降 |
| **Copilot CLI** | 轻量级、原生的Git与CLI助手 | 与GitHub生态绑定紧，轻量化，功能聚焦（/copy, web_fetch） | 稳定性是最大痛点（OOM、session死锁），功能单一，社区贡献少 |
| **OpenCode** | TUI+Web双模的现代AI编码平台 | 创新的V2配置、丰富的TUI交互、强大的MCP生态融合 | 账号系统与计费模糊（用户封禁无申诉），国际化支持不足，Schema混乱 |
| **Pi** | 高度可扩展的终端AI代理 | 架构先进，扩展系统强大，主题/UI自定义程度高 | 跨平台兼容性差（Windows路径问题），TUI性能瓶颈，Bug修复响应滞后 |
| **Qwen Code** | 依托通义模型的云原生开发环境 | 强建模能力驱动的代码理解，Managed Agent双路径架构（daemon） | 平台兼容性（Windows进程泄漏，macOS PTY），TUI崩溃影响核心体验 |
| **DeepSeek TUI** | 硬核、追求极致性能与创新的Rust TUI | 创始人主导的“安全审计”显示出对底层稳定性的极端追求，功能创新（causal-memory） | 处于早期快速迭代期，Bug数量多，新手入门体验差 |

#### 5. 社区热度与成熟度

-   **第一梯队（高活跃 + 高期望）**：**OpenAI Codex** 和 **Claude Code** 社区讨论量最大，用户期望值也最高。它们处于“明星产品的放大镜”下，任何一个Bug都会被迅速放大并引发激烈讨论。**Gemini CLI** 和 **Qwen Code** 紧随其后，社区增长迅速，但面临“成长的烦恼”。
-   **第二梯队（高活跃 + 中成熟期）**：**OpenCode**、**Pi** 和 **DeepSeek TUI** 社区非常活跃，但多集中于功能请求、Bug报告和架构讨论。它们的目标用户更偏向于技术专家和开源爱好者，产品成熟度仍在快速迭代中。
-   **第三梯队（平稳/静默）**：**Copilot CLI** 社区热度中等，但用户反馈多是重复的稳定性问题，显示出产品成熟度虽高但进入了“维护期”。**Kimi Code CLI** 社区几近静默，产品可能存在隐忧或战略调整。

#### 6. 值得关注的趋势信号

1.  **稳定性成为“入局门槛”，而非“竞争优势”**：
    -   数据支撑：几乎所有顶级工具的热点Issue都是 **OOM、会话崩溃、沙箱失效、认证死锁** 等基础问题。**用户的耐心正在耗尽**，Copilot CLI 的 OOM 问题和 Windows 平台的普遍问题是典型代表。
    -   启示：对于开发者而言，选择工具时 **“不出错”比“多神奇”更重要**。优先考虑那些频繁发布补丁、主动承认并修复回归Bug的工具。

2.  **MCP 生态的“标准化瓶颈”**：
    -   数据支撑：Claude Code、OpenAI Codex、Gemini CLI、Qwen Code 无一例外地遇到了 MCP 连接的 **会话标识、缓存、冷启动、错误处理** 问题。
    -   启示：MCP 协议本身可能还需要一次重大的版本迭代，以解决 **无状态服务向有状态服务** 过渡的通用问题。开发者在使用多 MCP 工具时应预期到这些不稳定性。

3.  **“安全与可用性”的平衡木**：
    -   数据支撑：Claude Code (安全过滤器误报，密码硬阻断)，Copilot CLI (策略误封)，OpenAI Codex (沙箱GPU申请)，DeepSeek TUI (崩溃安全性审计)。
    -   启示：AI CLI 厂商都采取了“默认安全，限制优先”的策略。但社区反馈强烈要求提供 **“权威控制下的可选同意”** 和 **“更透明、更少误报”** 的安全策略。这在企业级应用中将是关键痛点。

4.  **“真实意图理解”成下一波突破口**：
    -   数据支撑：Gemini CLI 的 `决策门` PR 和 DeepSeek TUI 的 `可插拔记忆` 功能，都指向了**如何让AI资源（算力、Token）更精准地用于解决用户的实际问题**，而非消耗在无意义的模型调用上。
    -   启示：**轻量级预判模型 + 高效上下文管理** 将是下一阶段提升性能和降低成本的关键技术方向。这不仅关乎效率，更是实现更智能、更懂开发者的AI助理的必要条件。

5.  **“开源”与“封闭”的岔路口**：
    -   数据支撑：Kimi Code CLI 的静默与 DeepSeek TUI/OpenCode 的活跃极端对比。
    -   启示：在AI工具领域，**社区治理模式和响应速度** 已成为决定工具生命力的关键指标。一个活跃、受尊重的开源社区，其信任度远高于一个“被放弃”或仅靠企业主导的项目。对于技术决策者，考察工具的Issue响应速度和PR合并效率，是评估其长期健康度的有效方法。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

# Claude Code Skills 社区热点报告（数据截止 2026-09-25）

---

## 1. 热门 Skills 排行（按社区关注度排序）

以下 8 个 Pull Requests 在仓库中讨论最活跃、关注度最高，代表了当前社区热推的新 Skill 方向。

| 排行 | PR | Skill 功能 | 社区讨论热点 | 当前状态 |
|------|----|------------|--------------|----------|
| 1 | [#1298 fix(skill-creator)](https://github.com/anthropics/skills/pull/1298) | 修复 Skill Creator 的触发器评估机制，处理 Windows 兼容性和运行时失败 | Windows 下 subprocess pipe select() 失败、触发误报/漏报、优化评估准确性 | OPEN |
| 2 | [#1771 proofcore-contract-auditor](https://github.com/anthropics/skills/pull/1771) | 对 Solidity 和 Rust 智能合约进行静态分析，并将审计证明锚定到 TON 区块链 | Web3 开发者需求、零存储 Merkle 协议、可验证审计 | OPEN |
| 3 | [#1703 md2video-audio](https://github.com/anthropics/skills/pull/1703) | 将 Markdown 文档直接编译为带拟人语音的专业 MP4 视频（零成本） | 内容创作者、演示自动化、Marp + TTS 集成 | OPEN |
| 4 | [#822 AWT (AI Watch Tester)](https://github.com/anthropics/skills/pull/822) | AI 驱动的端到端（E2E）测试工具，零代码生成测试，支持视觉和浏览器控制 | 无代码测试、视觉断言、Claude 能力扩展 | OPEN |
| 5 | [#525 pyxel](https://github.com/anthropics/skills/pull/525) | 使用 Pyxel 引擎进行复古游戏开发、调试和验证 | 游戏开发、headless 输入驱动、帧检查机制 | OPEN |
| 6 | [#723 testing-patterns](https://github.com/anthropics/skills/pull/723) | 覆盖全栈测试模式的技能：单元测试、React 组件测试、集成测试、端到端测试 | 测试 Trophy 模型、AAA 模式、最佳实践 | OPEN |
| 7 | [#1245 notion-spec-to-implementation & quantitative-resume-auditor](https://github.com/anthropics/skills/pull/1245) | 将产品/技术规格转化为 Notion 任务并实现在代码中；量化简历审计 | 产品管理、Notion 集成、简历筛选 | OPEN |
| 8 | [#83 skill-quality-analyzer & skill-security-analyzer](https://github.com/anthropics/skills/pull/83) | 元技能：对 Claude Skills 进行质量评分（结构/文档/功能/安全性/性能） | 技能质量标准化、安全审计、工具化评估 | OPEN |

---

## 2. 社区需求趋势（从 Issues 中提炼）

社区通过 Issues 表达的核心诉求集中在以下方向：

| 需求主题 | 代表 Issue | 核心诉求 |
|----------|------------|----------|
| **安全与信任** | [#492](https://github.com/anthropics/skills/issues/492)（评论 43） | 社区技能放在 `anthropic/` 命名空间下造成信任边界漏洞，用户可能误将社区技能视为官方技能并授予过高权限 |
| **组织共享与协作** | [#228](https://github.com/anthropics/skills/issues/228)（评论 16） | 需要组织级别的技能共享库或直接分享链接，而非手动下载上传 |
| **技能评估与调试** | [#556](https://github.com/anthropics/skills/issues/556)（评论 12） | `run_eval.py` 评估框架下技能触发率为 0%，测试用例全部无效，需修复评估体系 |
| **技能持久化与恢复** | [#62](https://github.com/anthropics/skills/issues/62)（评论 10） | 已有技能意外消失，用户担心数据丢失与恢复机制 |
| **紧凑记忆表示** | [#1329](https://github.com/anthropics/skills/issues/1329)（评论 9） | 长运行 Agent 上下文被自身笔记占满，需要符号化、紧凑的代理状态表示方法 |
| **技能去重** | [#189](https://github.com/anthropics/skills/issues/189)（评论 6） | `document-skills` 和 `example-skills` 插件内容完全重复，导致上下文窗口浪费 |
| **上下文窗口优化** | [#1487](https://github.com/anthropics/skills/issues/1487)（评论 4） | `claude-api` skill 单次调用注入约 156k tokens，直接耗尽上下文窗口，需要限制注入量 |
| **Agent 治理模式** | [#412](https://github.com/anthropics/skills/issues/412)（评论 6） | 期望官方提供 Agent 系统的安全模式：策略执行、威胁检测、信任评分、审计跟踪 |
| **MCP 集成 / Skills 暴露为 API** | [#16](https://github.com/anthropics/skills/issues/16)（评论 4） | 将技能暴露为 MCP（Model Context Protocol）接口，实现标准化的 API 调用 |

> **趋势总结**：社区最迫切的四个方向是**安全信任**（命名空间问题）、**生态工具链**（评估/去重/上下文优化）、**组织级可用性**（共享/恢复）以及**技能标准化**（质量分析/API 化）。

---

## 3. 高潜力待合并 Skills（评论活跃但尚未合并的 PR）

以下 PR 社区讨论热度高、功能实用性强，预计近期有可能合并入主仓库：

| PR | 技能 | 亮点 | 现状 |
|----|------|------|------|
| [#1771 proofcore-contract-auditor](https://github.com/anthropics/skills/pull/1771) | Web3 智能合约审计 | 填补 Skills 生态在区块链安全领域的空白，技术成熟度较高 | OPEN |
| [#1703 md2video-audio](https://github.com/anthropics/skills/pull/1703) | Markdown→视频+语音 | 零成本、全自动化，适合内容创作者，集成稳定（Marp+TTS） | OPEN |
| [#822 AWT](https://github.com/anthropics/skills/pull/822) | AI 驱动 E2E 测试 | 开创性的视觉测试能力，零门槛自动生成测试脚本 | OPEN |
| [#525 pyxel](https://github.com/anthropics/skills/pull/525) | 复古游戏开发 | 完整的游戏开发调试工作流，已提供详细参考文档 | OPEN |
| [#723 testing-patterns](https://github.com/anthropics/skills/pull/723) | 全栈测试模式 | 覆盖从单元到 E2E 的完整体系，社区对测试自动化需求强烈 | OPEN |
| [#1245 notion-spec-to-implementation](https://github.com/anthropics/skills/pull/1245) | 产品→代码自动化 | 直接连接 Notion 演进与代码实现，提升产品效率 | OPEN |
| [#83 skill-quality-analyzer & security-analyzer](https://github.com/anthropics/skills/pull/83) | 元技能质量安全分析 | 推动技能标准化、安全审计自动化，促进生态健康发展 | OPEN |
| [#1776 blast-radius](https://github.com/anthropics/skills/pull/1776) | 批量/破坏性写入前检查 | 覆盖“查询正确但操作错误”的安全间隙，实用性极高 | OPEN |

---

## 4. 生态洞察

**当前社区在 Skills 层面最集中的诉求是：建立安全信任、评估与共享机制，使第三方技能生态从“自由提交”迈向“可信分发”。**  
具体表现为：命名空间信任漏洞（#492）、技能评估工具失效（#556）、组织共享缺失（#228）、重复与上下文浪费（#189/#1487）等问题频繁出现，社区在积极贡献高质量技能的同时，强烈要求官方提供配套的安全治理、质量审核与协作基础设施。

---

好的，作为专注于 AI 开发工具的技术分析师，我为您整理了 2026-09-25 的 Claude Code 社区动态日报。

---

# Claude Code 社区日报 | 2026-09-25

## 今日速览
今天社区动态活跃，主要集中在三个方面：**Cowork（云端协同）模式的 Git 代理与授权机制**遭遇持续反馈，被认为是近期的重大回归问题；**自动记忆（Auto-Memory）的透明度和控制权**成为新的讨论热点；此外，**安全过滤器的误报**以及对 `sandbox` 功能配置失效的困扰，仍是开发者高频提及的痛点。

---

## 版本发布

### v2.1.282 更新说明
- **新增 `maxProseWidth` 设置**：允许在宽终端中限制 Claude 输出文本（prose）的宽度，同时表格和代码块保持全宽显示，优化了阅读体验。
- **启动通知与诊断增强**：新增启动时的提示信息，并在 `/status` 命令和 `claude doctor` 诊断工具中，增加了对项目设置文件中被忽略的遥测变量的显示。

---

## 社区热点 Issues
### 1. 自动记忆（Auto-Memory）加载状态不透明
- **Issue #82056** [OPEN]：用户提出，会话无法判断自动记忆索引是完整加载、截断加载还是完全未加载，导致对模型上下文的不确定性。
- **社区热度**：55 条评论，1 个 👍。
- **为什么重要**：自动记忆是维持长期项目上下文的关键功能。缺乏加载状态的可见性，会使用户难以调试和信任 AI 的记忆行为，是提升开发者体验的核心需求。
- **链接**：https://github.com/anthropics/claude-code/issues/82056

### 2. Cowork模式 Git 代理阻断所有推送
- **Issue #76248** [OPEN]：云端 Cowork 会话无法推送到“授权仓库集”之外的仓库，即使用户提供细粒度 PAT（个人访问令牌）也无效。
- **社区热度**：38 条评论，15 个 👍。
- **为什么重要**：Cowork 是团队协作的核心场景，此 Bug 完全阻塞了开发者对第三方或非授权仓库的正常 Git 操作，影响巨大。社区对“授权仓库集”机制的实现方式提出了强烈质疑。
- **链接**：https://github.com/anthropics/claude-code/issues/76248

### 3. MCP 服务器无法区分并发会话
- **Issue #41836** [OPEN]：Claude Code 连接 MCP 服务器时，未发送会话或对话标识符，导致服务器无法维护每个会话的独立状态。
- **社区热度**：17 条评论，37 个 👍 (👍 数最高)。
- **为什么重要**：这是 MCP 生态系统的基础设施问题。随着 MCP 工具的增多，区分并发会话是构建有状态、多任务服务的先决条件，严重阻碍了高级 MCP 应用的开发。
- **链接**：https://github.com/anthropics/claude-code/issues/41836

### 4. `totalTokensReminder` 导致提示缓存失效
- **Issue #90018** [OPEN]：默认开启的 `totalTokensReminder` 功能，在工具循环中会导致可重复的提示缓存（prompt-cache）无法命中，关闭后恢复正常。
- **社区热度**：7 条评论，2 个 👍。
- **为什么重要**：提示缓存是降低成本和提高响应速度的关键。一个默认开启的功能反而破坏了缓存效果，对高频使用的开发者而言，这是一笔不容忽视的开销。
- **链接**：https://github.com/anthropics/claude-code/issues/90018

### 5. Opus 5.5 安全过滤器误报
- **Issue #96118** [OPEN]：Opus 5.5 的安全防护将用户的正常工具调用请求标记为 `reasoning_extraction` 违规，导致 API 错误。
- **社区热度**：6 条评论，1 个 👍。
- **为什么重要**：安全过滤器过于严格且误报率高，会打断正常开发流程，尤其是在需要模型进行复杂推理或工具调用时，严重影响用户体验和模型可用性。
- **链接**：https://github.com/anthropics/claude-code/issues/96118

### 6. 硬阻断输入密码，缺乏可配置的替代方案
- **Issue #78160** [OPEN]：Claude Code 拒绝在开发者的本地测试环境、并得到明确指令的情况下输入密码。
- **社区热度**：5 条评论，14 个 👍。
- **为什么重要**：虽然默认安全策略是可取的，但完全硬阻断破坏了自动化测试、CI/CD 等合法开发流程。社区需要“权限控制下的可选同意”机制，而不是一刀切的禁止。
- **链接**：https://github.com/anthropics/claude-code/issues/78160

### 7. `sandbox.excludedCommands` 配置失效
- **Issue #95813** [OPEN]：`sandbox.excludedCommands` 配置对列出的命令无效，这些命令仍会在沙箱中运行并因沙箱限制而失败。
- **社区热度**：2 条评论，4 个 👍。
- **为什么重要**：沙箱功能是安全开发的核心。配置项无效意味着用户无法信任该功能，也无法准确地将某些命令从沙箱隔离中排除，是一个严重的功能性 Bug。
- **链接**：https://github.com/anthropics/claude-code/issues/95813

### 8. 非会话文件变更被错误显示为代码差异
- **Issue #95930** [OPEN]：当用户切换 Git 分支或进行变基操作时，文件在磁盘上的变化会被 Claude Code 错误地显示为 AI 生成的编辑。
- **社区热度**：2 条评论，2 个 👍。
- **为什么重要**：这引入了严重的信息噪音和潜在的误导。开发者依赖清晰的编辑日志来理解 AI 的工作，这种混淆会破坏信任和调试效率。
- **链接**：https://github.com/anthropics/claude-code/issues/95930

### 9. Opus 5 用量被计入 Fable 模型限额
- **Issue #96035** [OPEN]：Opus 5 模型的使用量被错误地计入每周的 Fable 模型限额中。
- **社区热度**：1 条评论，2 个 👍。
- **为什么重要**：计费/配额错误直接影响用户的经济利益和模型选择策略。对于依赖高频次使用 Opus 模型的用户，这是需要立即关注的财务问题。
- **链接**：https://github.com/anthropics/claude-code/issues/96035

### 10. 崩溃后，后台进程被孤立，终端陷入鼠标报告模式
- **Issue #81210** [OPEN]：CLI 崩溃后，用户启动的后台进程成为孤儿，且终端陷入鼠标报告模式，无法正常使用。
- **社区热度**：2 条评论，0 个 👍。
- **为什么重要**：崩溃后的清理机制不完善，会污染用户的工作环境，需要手动重置终端，是极差的用户体验。这反映退出/崩溃处理流程存在严重缺陷。
- **链接**：https://github.com/anthropics/claude-code/issues/81210

---

## 重要 PR 进展
### 1. 修复分页读取 AGENTS.md 的计数问题
- **PR #96364** [CLOSED]：修复了一个问题，当自动分页读取嵌套的 AGENTS.md 文件时，不会将其计为“已投递”，从而确保后续读取仍能正确附加该文件上下文。
- **链接**：https://github.com/anthropics/claude-code/pull/96364

### 2. 修复 Git 强制颜色导致 diff 为空
- **PR #96363** [CLOSED]：当仓库的 Git 配置设置了 `color.ui=always` 时，`git diff` 会输出 ANSI 转义码，导致 diff 主体为空。此 PR 通过添加 `--no-color` 参数修复了此问题。
- **链接**：https://github.com/anthropics/claude-code/pull/96363

### 3. 遥测数据增加引擎版本信息
- **PR #96487** [CLOSED]：在遥测数据行中增加了引擎的版本（version）、基础版本（base version）和构建时间（build time）字段，以解决外部构建包无法上报版本的问题。
- **链接**：https://github.com/anthropics/claude-code/pull/96487

### 4. 优化 diff 模块，避免对只读命令重取 diff
- **PR #95423** [CLOSED]：优化了 diff 刷新逻辑。当工具栏持有只读命令（如 `ls`, `cat`）时，不再触发 diff 刷新，减少了不必要的性能开销。
- **链接**：https://github.com/anthropics/claude-code/pull/95423

### 5. 修复 `command.run` 钩子命令名匹配
- **PR #96570** [CLOSED]：修复了 `diff` 模块中 `command.run` 钩子的命令名匹配问题，确保引擎能正确识别该模块并决定是否在启动时等待其加载。
- **链接**：https://github.com/anthropics/claude-code/pull/96570

---

## 功能需求趋势
1.  **Cowork 与 Git 集成**：社区对 Cowork 模式的 Git 代理机制有强烈的反馈，核心诉求是**灵活的授权管理**和**透明的代理行为**。用户希望能在不同仓库间自由推送，而不是被“授权集”限制。
2.  **模型安全与可用性平衡**：“安全过滤器误报”是反复出现的主题。社区需求是**更精确、误报率更低的安全策略**，尤其是对 `reasoning_extraction` 等新规则的校准，以及为开发者提供明确的绕过/申诉途径。
3.  **上下文与管理透明度**：从 `#82056` (自动记忆) 和 `#90018` (缓存) 可见，开发者要求对 AI 的上下文管理（记忆加载了什么、缓存是否命中）有更高的**可见性和控制权**。
4.  **MCP 生态基础建设**：`#41836` (会话ID) 问题获得最高点赞，表明社区迫切希望**完善 MCP 协议的基础功能**，以支持更复杂的多会话、有状态的服务端应用。

---

## 开发者关注点
1.  **Cowork 模式的集成阵痛**：Cowork 是冷启动后最大的更新方向，但当前处于“阵痛期”。从 Git 代理失效 (`#76248`) 到文件工具操作副本 (`#96187`)，开发者对云端与本地环境的**集成稳定性**和**行为一致性**有很高期待。
2.  **配置失效的挫败感**：多个 Issue 指向了“配置项不起作用”的问题，如 `sandbox.excludedCommands` (`#95813`) 和 `totalTokensReminder` 的副作用 (`#90018`)。这引发了开发者的**信任危机**，他们需要每个设置项都能按照预期工作。
3.  **“过度保护”与“开发效率”的矛盾**：以密码输入 (`#78160`) 和内容过滤器 (`#96118`, `#96912`) 为代表，开发者普遍认为默认安全策略过于严格，**扼杀了合法的开发测试流程**。他们希望看到一个更智能、更可配置的安全体系，而不是一刀切的限制。
4.  **信息噪音与混淆**：`#95930` (非编辑显示为 diff) 展示了信息呈现的精确性问题。开发者依赖清晰的、可追溯的 AI 操作日志，任何混淆性的显示都会对信任和调试造成实际损害。

---
*以上内容由 AI 分析师基于公开数据生成，仅供参考。建议通过链接查看具体 Issue 或 PR 的最新进展。*

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报（2026-09-25）

## 今日速览

- Codex 核心引擎发布 `0.158.0-alpha.7~11` 系列及 `0.157.0-alpha.11.1` 紧急修复版，稳定性持续迭代。
- 社区最热 Issue #20214（Windows 桌面频繁卡顿）评论数达 112 条，成为当前最大痛点；#3141（沙箱 GPU 支持）获得 62 个 👍，呼声强烈。
- 今日批量合入 20 个 PR，涵盖语音恢复防错误、Pro Max 订阅支持、沙箱安全加固等关键功能与修复。

## 版本发布

过去 24 小时内，Codex 项目发布了 6 个 Rust 核心组件的 alpha 版本，均为增量更新，未提供详细变更日志：

- **[rust-v0.158.0-alpha.11](https://github.com/openai/codex/releases/tag/rust-v0.158.0-alpha.11)** 及 alpha.10、alpha.9、alpha.8、alpha.7
- **[rust-v0.157.0-alpha.11.1](https://github.com/openai/codex/releases/tag/rust-v0.157.0-alpha.11.1)**（可能为 0.157 系列的补丁）

> 建议关注 Rust 核心的构建与沙箱模块改动，预计后续会有更详细的 changelog。

## 社区热点 Issues（10 条）

1. **#20214 – Codex App 在 Windows 11 Pro 上频繁卡顿/冻结**  
   [链接](https://github.com/openai/codex/issues/20214)  
   - 112 评论，87 👍 | 状态：OPEN  
   - 重要性：Windows 用户最多、反馈最强烈。用户配置充足（Ryzen 5 5600, 32GB RAM）依然卡顿。  
   - 社区反应：大量用户附上日志，怀疑与渲染器或沙箱线程有关。

2. **#3141 – 允许沙箱内使用 GPU**  
   [链接](https://github.com/openai/codex/issues/3141)  
   - 39 评论，62 👍 | 状态：OPEN  
   - 重要性：Linux 下 nvidia-smi 被沙箱拦截，无法利用 GPU 加速推理或计算。科学计算与 AI 开发者强烈需求。  
   - 社区反应：已持续一年，需求热度不减。

3. **#44736 – Windows 项目预热身锁定本地镜像，启动时覆盖 node_repl 目录**  
   [链接](https://github.com/openai/codex/issues/44736)  
   - 18 评论，0 👍 | 状态：OPEN  
   - 重要性：影响 ChatGPT Projects 功能中 Work 模式的正常使用，导致工作目录冲突。  
   - 社区反应：用户提供详细复现步骤与临时 workaround。

4. **#42520 – Windows Chrome 集成：chrome-native-hosts-v2.json 未创建**  
   [链接](https://github.com/openai/codex/issues/42520)  
   - 15 评论，1 👍 | 状态：OPEN  
   - 重要性：桌面端 Chrome 浏览器集成失效，影响“读取当前页面”等关键交互。  
   - 社区反应：用户确认更新后仍旧复现。

5. **#46114 – Windows 桌面：提权沙箱在所有线程上失败**  
   [链接](https://github.com/openai/codex/issues/46114)  
   - 13 评论，4 👍 | 状态：OPEN  
   - 重要性：新开或恢复会话均立即报错，沙箱完全不可用。  
   - 社区反应：管理员启动、修复、重置均无效，属于严重回归。

6. **#47511 – 缺少 Git 提交/推送按钮（回归）**  
   [链接](https://github.com/openai/codex/issues/47511)  
   - 10 评论，27 👍 | 状态：OPEN  
   - 重要性：影响开发流程中频繁使用的版本控制操作。  
   - 社区反应：Pro 用户强烈要求恢复可见按钮。

7. **#33266 – MCP tools/list_changed 通知未刷新缓存**  
   [链接](https://github.com/openai/codex/issues/33266)  
   - 8 评论，9 👍 | 状态：OPEN  
   - 重要性：MCP 工具变更后，CLI 仍使用旧缓存，需手动重启。  
   - 社区反应：提供了可复现的 MCP 服务器。

8. **#46772 – Windows 桌面：每个聊天只能发送一条消息**  
   [链接](https://github.com/openai/codex/issues/46772)  
   - 5 评论，1 👍 | 状态：OPEN  
   - 重要性：严重阻塞正常对话流程。  
   - 社区反应：用户描述按 Enter 无反应，必须新建聊天。

9. **#46690 – Windows 渲染器内存泄漏达 4–7 GB，频繁崩溃**  
   [链接](https://github.com/openai/codex/issues/46690)  
   - 3 评论，0 👍 | 状态：OPEN  
   - 重要性：版本 26.915.4065.0 特有，回滚后稳定。  
   - 社区反应：内存飙升导致应用反复重载。

10. **#47972 – Windows Desktop 缺少 GPT-6 Astra/Sol/Luna 模型**  
    [链接](https://github.com/openai/codex/issues/47972)  
    - 2 评论，0 👍 | 状态：OPEN  
    - 重要性：CLI 和移动端可用，但桌面模型选择器中缺失，影响 Plus 用户使用最新模型。

## 重要 PR 进展（10 条）

1. **#47975 – 语音恢复时防止陈旧答案重新出现**  
   [链接](https://github.com/openai/codex/pull/47975)  
   - 状态：已合并 | 修复语音失败时队列中已播报的答案错误回显。

2. **#47974 – 保护 Git 目录可写根穿透**  
   [链接](https://github.com/openai/codex/pull/47974)  
   - 状态：已合并 | 防止因 `Seatbelt` 或 `bubblewrap` 挂载导致 `.git` 目录被意外写入。

3. **#47971 – 支持 Pro Max 订阅计划，更新 Pro 显示名称**  
   [链接](https://github.com/openai/codex/pull/47971)  
   - 状态：已合并 | 引入 `promax`，调整 `prolite`/`pro`/`promax` 显示为“Pro”/“Pro (More)”/“Pro (Max)”。

4. **#47970 – 暴露当前运行 turn 的环境选择**  
   [链接](https://github.com/openai/codex/pull/47970)  
   - 状态：已合并 | 新增 `current_turn_environment_selections()` 方法，便于调用方获取实时环境配置。

5. **#47968 – 处理 Btrfs 设备不匹配时的守护进程套接字屏蔽**  
   [链接](https://github.com/openai/codex/pull/47968)  
   - 状态：已合并 | 修复 Btrfs 子卷上 `st_dev` 与 mountinfo 不一致导致的沙箱挂载验证失败。

6. **#47967 – 将 Flex 容量故障暴露为独立终止错误**  
   [链接](https://github.com/openai/codex/pull/47967)  
   - 状态：已合并 | 当 API 返回 `flex_unavailable` 时，正常终止并显示明确提示，避免死循环重试。

7. **#47964 – 保留 Amazon Bedrock Runtime 的 client-agent 请求头**  
   [链接](https://github.com/openai/codex/pull/47964)  
   - 状态：已合并 | 确保 `x-amzn-mantle-client-agent: codex` 在 Bedrock Runtime 中不被清空。

8. **#47962 – 为 Cargo 和 Bazel rustc 任务请求透明大页**  
   [链接](https://github.com/openai/codex/pull/47962)  
   - 状态：已合并 | 通过 `MALLOC_CONF=thp:always` 提升编译性能。

9. **#47957 – 限制工具调用观察结果到输出消息预算**  
   [链接](https://github.com/openai/codex/pull/47957)  
   - 状态：已合并 | 保证总请求不超 15 MiB 上限，防止因过长参数导致截断或失败。

10. **#47956 – 支持图片编辑请求中的文件引用**  
    [链接](https://github.com/openai/codex/pull/47956)  
    - 状态：已合并 | 允许使用 `file_id` 引用对话历史中的图片进行编辑。

## 功能需求趋势

从近期 Issues 和 PR 中，社区最关注的功能方向包括：

- **Windows 桌面稳定性**：卡顿、崩溃、内存泄漏占据最高频反馈。
- **沙箱能力提升**：GPU 支持、Btrfs 兼容、挂载验证改进。
- **IDE 集成完善**：VS Code 扩展的多窗口、使用量显示、会话锁定恢复。
- **模型与订阅管理**：新模型（GPT-6 系列）在桌面端的缺失、Pro Max 新层级适配。
- **MCP 生态**：工具缓存失效、输入模式预算可配置、MCP 服务器与插件身份分离。
- **开发工作流**：Git 操作按钮回归、CLI 工作树过滤器、会话标题语言错误。

## 开发者关注点

- **Windows 平台成为积重难返的痛点**：从 #20214（卡顿）、#46114（沙箱全不可用）到 #46690（内存泄漏）、#46772（单条消息限制），Windows 用户几乎每周都遇到新的致命问题。
- **沙箱安全与灵活性矛盾**：用户希望获得 GPU、网络等更丰富的沙箱能力，但安全团队倾向于收紧权限（如 Btrfs 套接字屏蔽、Git 目录保护）。
- **使用量监控与计费透明度**：多个 Issues（#47637、#46707）反映使用量快速耗尽且缺乏明确解释，社区要求更精细的计量展示和控制。
- **会话锁定缺乏恢复机制**：跨设备/跨应用（VS Code + CLI）的冲突锁定导致对话永久不可用，用户强烈期望增加“强制解锁”或冲突迁移功能。

---
*数据来源：GitHub openai/codex 仓库，截止 2026-09-25 24:00 UTC。*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，这是为您生成的 Gemini CLI 社区动态日报。

---

# Gemini CLI 社区动态日报 — 2026年9月25日

## 今日速览

社区开发节奏保持稳定，重点聚焦于提升核心 CLI 的稳定性和子代理系统的可靠性。昨日发布了 `v0.62.0-nightly` 版本，主要修复了连接恢复时的 UI 反馈问题。在社区讨论中，关于子代理行为异常（如错误报告隐藏中断、无响应、不遵循设置）的 Bug 报告依然热度最高。与此同时，多项针对文件并发操作、终端输入处理和身份验证循环的关键 PR 取得进展，显著提升了用户体验。

## 版本发布

- **[v0.62.0-nightly.20260924.g8e70c862f](https://github.com/google-gemini/gemini-cli/releases/tag/v0.62.0-nightly.20260924.g8e70c862f)**
  - **修复 (CLI)**: 在连接恢复期间，现在会显示重试进度指示器，让用户能更直观地了解状态。
  - **其他**: 包含对 VS Code 集成测试的检查逻辑优化。

## 社区热点 Issues

以下挑选了 10 个评论最多、最受关注的 Issue，反映了社区当前最关心的问题。

1.  **Subagent 恢复后错误报告误导**
    - **Issue**: [#22323](https://github.com/google-gemini/gemini-cli/issues/22323)
    - **简介**: 当子代理（如 `codebase_investigator`）因达到最大执行轮数（MAX_TURNS）而中断时，它本应报告失败，却错误地报告为“目标达成”（success），给用户造成困惑。
    - **热度**: 13 条评论 | 2 👍
    - **关注点**: P1 级别 Bug，直接影响了用户对 Agent 工作状态的判断，社区对此问题反馈强烈。

2.  **通用 Agent 无响应**
    - **Issue**: [#21409](https://github.com/google-gemini/gemini-cli/issues/21409)
    - **简介**: 当 Gemini CLI 将任务交给通用（generalist）Agent 处理时，会无限期挂起，即使简单的文件夹创建任务也无法执行。
    - **热度**: 8 条评论 | 8 👍
    - **关注点**: 这是 P1 级别的严重 Bug，直接导致核心功能不可用，社区给出了高点赞和评论，是影响面最广的问题之一。

3.  **Agent 对自定义技能和子代理使用不足**
    - **Issue**: [#21968](https://github.com/google-gemini/gemini-cli/issues/21968)
    - **简介**: 用户反馈，Gemini CLI 不会主动使用用户配置的自定义技能（Skills）和子代理（Sub-agents），即使任务高度相关。只有在明确指示下才会使用。
    - **热度**: 6 条评论
    - **关注点**: 这削弱了 Agent 自定义扩展的价值，用户希望 AI 能更智能地调度底层工具。

4.  **Auto Memory 日志泄露风险**
    - **Issue**: [#26525](https://github.com/google-gemini/gemini-cli/issues/26525)
    - **简介**: Auto Memory 功能在读取本地聊天记录时，会将信息发送给模型处理，但秘钥（Secret）的脱敏操作发生在模型已接收内容之后，存在隐私泄露风险。
    - **热度**: 5 条评论
    - **关注点**: 这是 P2 级别的安全问题，社区对 AI Agent 的隐私和数据处理流程高度关注。

5.  **浏览器 Agent 覆盖 `settings.json` 配置**
    - **Issue**: [#22267](https://github.com/google-gemini/gemini-cli/issues/22267)
    - **简介**: 用户通过 `settings.json` 为浏览器 Agent 自定义的配置（如最大轮数 `maxTurns`）完全被忽略，Agent 总是使用默认值。
    - **热度**: 4 条评论
    - **关注点**: 配置系统失效，用户无法精确控制 Agent 行为，影响了高级用户的可定制性。

6.  **浏览器 Agent 在 Wayland 下失败**
    - **Issue**: [#21983](https://github.com/google-gemini/gemini-cli/issues/21983)
    - **简介**: 使用 Wayland 显示协议的 Linux 用户报告，浏览器子代理无法正常工作。
    - **热度**: 4 条评论 | 1 👍
    - **关注点**: 环境兼容性问题，限制了在特定发行版或桌面环境用户的使用。

7.  **检测到超过 128 个工具时出错**
    - **Issue**: [#24246](https://github.com/google-gemini/gemini-cli/issues/24246)
    - **简介**: 当用户启用的工具或技能数量过多（>128个）时，Gemini CLI 会返回 400 错误。
    - **热度**: 3 条评论
    - **关注点**: 随着 Agent 生态发展，“工具膨胀”问题开始显现，社区希望看到更智能的工具调度机制。

8.  **Bug 报告缺少子代理上下文**
    - **Issue**: [#21763](https://github.com/google-gemini/gemini-cli/issues/21763)
    - **简介**: 用户通过 `/bug` 命令提交错误报告时，报告只包含主会话信息，而无法提供子代理内部的工作细节，导致开发人员难以复现和定位问题。
    - **热度**: 2 条评论
    - **关注点**: P1 级别 Bug，影响了故障诊断效率，社区希望改进错误报告的详尽度。

9.  **模型在随机位置创建临时脚本**
    - **Issue**: [#23571](https://github.com/google-gemini/gemini-cli/issues/23571)
    - **简介**: 当限制模型仅通过 Shell 命令工作时，模型会倾向于在项目外的随机目录生成多个临时编辑脚本，造成工作区混乱。
    - **热度**: 3 条评论
    - **关注点**: P2 Bug，影响了工作区的整洁性和代码提交管理效率。

10. **Agent 应阻止破坏性行为**
    - **Issue**: [#22672](https://github.com/google-gemini/gemini-cli/issues/22672)
    - **简介**: 在处理复杂的 Git 操作时，模型可能会执行如 `git reset --force` 等具有潜在破坏性的命令，而社区认为 Agent 应主动识别并劝阻此类行为。
    - **热度**: 3 条评论 | 1 👍
    - **关注点**: 反映了社区对 Agent 安全和容错性的更高期待，希望 Agent 具备“风险意识”。

## 重要 PR 进展

以下 10 个 PR 代表了项目在核心功能、稳定性和安全性上的主要改进方向。

1.  **【已关闭】修复并发文件操作冲突**
    - **PR**: [#29494](https://github.com/google-gemini/gemini-cli/pull/29494)
    - **简介**: **核心修复**。通过序列化文件工具操作，解决了在子代理或批量调度中多个工具同时修改同一文件导致的数据竞争和更新丢失问题（Lost-update races）。
    - **重要性**: 直接提升了并发操作场景下的数据一致性，对修复 #21968 等 Agent 挂起问题可能具有根本性帮助。

2.  **【进行中】修复无限身份验证循环**
    - **PR**: [#29448](https://github.com/google-gemini/gemini-cli/pull/29448)
    - **简介**: 解决了 Windows、WSL 和无头环境中与 VS Code 扩展等工具产生文件竞争，导致 CLI 陷入无限身份验证循环的严重问题。
    - **重要性**: 针对 #28341 问题，是影响特定平台用户核心体验的修复。

3.  **【已关闭】修复终端输入“卡死”**
    - **PR**: [#29487](https://github.com/google-gemini/gemini-cli/pull/29487)
    - **简介**: 解决了在集成终端中运行时，按回车键后 CLI 无响应的问题。
    - **重要性**: 直接改善了与 IDE 集成场景下的用户体验。

4.  **【进行中】添加快速的“决策门”**
    - **PR**: [#29482](https://github.com/google-gemini/gemini-cli/pull/29482)
    - **简介**: 提出在调用主模型前，增加一个轻量级的“决策门”模型，快速预判用户意图，简单指令可直接快速响应，无需调用大型模型。
    - **重要性**: 一项旨在显著降低延迟和 token 成本的前沿架构探索。

5.  **【已关闭】处理损坏的 MCP JSON 配置**
    - **PR**: [#29446](https://github.com/google-gemini/gemini-cli/pull/29446)
    - **简介**: 区分了 `mcp-server-enablement.json` 文件不存在和内容错误两种情况，避免了因配置文件损坏导致 MCP 服务器状态被意外覆盖。
    - **重要性**: 增强了配置系统的鲁棒性，防止数据丢失。

6.  **【进行中】修复会话恢复时的重复响应**
    - **PR**: [#29490](https://github.com/google-gemini/gemini-cli/pull/29490)
    - **简介**: 修复了使用 `-r` 参数恢复会话时，工具响应结果被重复播放两次的问题。
    - **重要性**: 提升会话恢复功能的准确性，避免信息冗余。

7.  **【已关闭】限制工具输出大小**
    - **PR**: [#29451](https://github.com/google-gemini/gemini-cli/pull/29451)
    - **简介**: 对工具执行（如构建脚本、测试命令）的输出大小做了上限限制，并优化了长期运行 Agent 的内存生命周期，防止内存无限制增长。
    - **重要性**: 提升 CLI 在复杂、长时间任务中的稳定性，防止 OOM。

8.  **【进行中】阻止 Flash-Lite 模型继承高思考预算**
    - **PR**: [#29489](https://github.com/google-gemini/gemini-cli/pull/29489)
    - **简介**: 明确阻止 Flash-Lite 系列模型（如 `gemini-3.1-flash-lite`）继承 `ThinkingLevel.HIGH` 的高思考量配置，确保其轻快特性。
    - **重要性**: 体现了对不同模型差异化调优的精细化思路。

9.  **【进行中】修复 ACP 模式下的会话文件时间戳冲突**
    - **PR**: [#29463](https://github.com/google-gemini/gemini-cli/pull/29463)
    - **简介**: 修复了在 ACP 模式下，同一分钟内新建和加载会话时，因文件名相同导致会话状态被覆盖和丢失的 Bug。
    - **重要性**: 提升了 ACP 协议的稳定性和会话管理的可靠性。

10. **【进行中】修复 Shell 脚本中的安全注入风险**
    - **PR**: [#29492](https://github.com/google-gemini/gemini-cli/pull/29492)
    - **简介**: 在沙箱构建和网络设置过程中，避免了因 Shell 语句拼接而可能导致的命令注入攻击。
    - **重要性**: 一项重要的安全加固，提升了沙箱环境的安全性。

## 功能需求趋势

综合近期 Issues，社区最关注的功能方向包括：

- **Agent 自主性与正确性**：社区强烈期望 Agent 能更“聪明”地工作，例如：更主动地调用内置技能/子代理、更准确地报告自身状态、以及不要忽略用户的自定义配置。
- **稳定性与可靠性**：解决 Agent“挂起”、超时、在特定环境下失败等问题是最高优先级的诉求。开发者需要的是一个能够在复杂场景下稳定运行的工具。
- **安全与隐私沙箱**: 围绕 Auto Memory 的隐私数据处理、Shell 命令执行的安全性、以及主动阻止破坏性操作等议题，表明社区对 Agent 执行环境的安全性和可控性日益重视。
- **工具与配置管理精细度**: 用户希望更细致地控制 Agent 行为，包括：有效的全局/工作区配置继承、处理大量工具（>128）时的智能调度、以及修复损坏配置的容错能力。

## 开发者关注点

从社区反馈中，可以提炼出以下开发者痛点和高频需求：

- **子 Agent 的不透明性**: 开发者最头疼的是子 Agent 执行过程中的“黑盒”问题，包括挂起后无反馈、错误报告不准确、以及 Bug 报告缺少内部上下文，导致调试困难。
- **配置被忽略/未生效**: 用户对 `settings.json` 配置被浏览器 Agent 忽略、全局策略与工作区策略冲突等问题感到沮丧，需要更加可靠和直观的配置系统。
- **与 IDE 集成的不稳定性**: 在 VS Code 等 IDE 的集成终端中使用 CLI 时，会遇到回车无响应、认证循环等体验问题，这类问题影响了日常工作效率。
- **对 Agent 风险行为的焦虑**: 开发者担心 Agent 可能执行`git reset --force`等破坏性命令，希望在 Agent 的底层设计上增加安全保障或风险提示机制。

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区动态日报 | 2026-09-25

## 今日速览
昨日发布两个补丁版本（v1.0.89-2 / v1.0.89-3），主要修复表单持久化和改进本地会话操作体验。社区反馈中 **OOM 崩溃**、**会话创建失败** 和 **认证令牌失效** 成为最热门的痛点，多起 Issue 获大量评论与 👍 票。此外，**会话分支（/fork）** 功能需求被关闭但社区呼声依然很高。

## 版本发布
### v1.0.89-3（补丁）
- **Fixed**  
  - 表单中 `Other` 自定义答案在各问题间保持独立，不再互相干扰。

### v1.0.89-2（功能 + 改进）
- **Added**  
  - MCP 预注册 OAuth 客户端现在会遵守配置的 `oauthScopes`。  
  - 在本地会话中，当聊天输入为空时连续按两次 `Esc` 可撤回模型尚未开始回答的提示并将其从对话中移除。  
- **Improved**  
  - 在受支持的 Windows 版本上对沙箱化命令的执行做了改进（具体细节未展开）。

---

## 社区热点 Issues（精选 10 条）

### 1. [#4742] 桌面应用 1.1.15：无法创建第二个本地（分支）会话
- **评论：11 | 👍：5**  
- **摘要**：桌面版自动更新到 1.1.15 后，若同一项目已有活跃的本地会话，再创建新会失败，提示“项目已有活跃的本地工作区”。严重影响多分支并行工作。  
- [查看详情](https://github.com/github/copilot-cli/issues/4742)

### 2. [#2058] [已关闭] 添加 `/fork` 命令以分支会话
- **评论：10 | 👍：10**  
- **摘要**：用户希望 Copilot CLI 在执行多步目标时，可通过 `/fork` 创建一个子会话处理临时问题，而不干扰主线任务。虽已关闭，但社区仍强烈希望该功能回归或重新设计。  
- [查看详情](https://github.com/github/copilot-cli/issues/2058)

### 3. [#4535] [已关闭] `store_memory` 在 v1.0.81 预发布版中失败
- **评论：9 | 👍：1**  
- **摘要**：`store_memory` 工具因缺少实例 ID 导致调用失败，影响上下文记忆持久化。该问题在正式版中应已修复。  
- [查看详情](https://github.com/github/copilot-cli/issues/4535)

### 4. [#3534] WSL2 ARM64 下 `/copy` 因 `cmd.exe` 引用错误失败
- **评论：7 | 👍：5**  
- **摘要**：在 WSL2 ARM64 上，剪切板复制操作因 `clip.exe` 调用时引号处理错误而失败，影响日常使用。  
- [查看详情](https://github.com/github/copilot-cli/issues/3534)

### 5. [#2408] [已关闭] CLI 自动更新问题
- **评论：7 | 👍：5**  
- **摘要**：用户需要多次尝试才能获得最新版本，自动更新机制不可靠。  
- [查看详情](https://github.com/github/copilot-cli/issues/2408)

### 6. [#4725] Linux 平台频繁 JavaScript 堆内存溢出
- **评论：6 | 👍：1**  
- **摘要**：CLI 在运行几分钟后即因堆内存不足而崩溃，影响长时间使用。  
- [查看详情](https://github.com/github/copilot-cli/issues/4725)

### 7. [#4699] 长会话 `--resume` 时 OOM 崩溃，crash dump 写入当前目录
- **评论：6 | 👍：7**  
- **摘要**：1.0.82 版本在恢复长会话时反复 OOM（4 GiB 堆上限），且诊断文件写入用户 CWD，可能泄露敏感信息。  
- [查看详情](https://github.com/github/copilot-cli/issues/4699)

### 8. [#4905] 桌面应用会话数分钟后死亡：“GitHub credential registration is no longer available”
- **评论：5 | 👍：4**  
- **摘要**：桌面版 1.1.22 中会话启动后几分钟即因凭证注册失效而死亡，导致 MCP 服务器目录变 stale 并引发致命错误。  
- [查看详情](https://github.com/github/copilot-cli/issues/4905)

### 9. [#4929] 进程本地认证令牌停止刷新，所有提示失败
- **评论：5 | 👍：0**  
- **摘要**：长时间运行的 CLI 进程丢失认证，`/login` 无法恢复，必须重启进程。  
- [查看详情](https://github.com/github/copilot-cli/issues/4929)

### 10. [#3948] 任何 `web_fetch` 都返回 `TypeError: fetch failed`
- **评论：5 | 👍：2**  
- **摘要**：`web_fetch` 工具总是失败，但模型访问和登录均正常，疑似网络层特定 bug。  
- [查看详情](https://github.com/github/copilot-cli/issues/3948)

---

## 重要 PR 进展

昨日仅有 **1 条 PR** 获得更新：

### [#4948] [Open] 更新 github-script Action 引脚版本
- **作者**：klockhoffbjorn-collab  
- **摘要**：将 `actions/github-script` 的引用刷新至当前 v9.0.0 版本，确保 CI 流程使用最新稳定版。无运行时依赖修改。  
- [查看 PR](https://github.com/github/copilot-cli/pull/4948)

（注：目前仓库 PR 数量较少，社区贡献活跃度有待提升。）

---

## 功能需求趋势

基于近期 Issues 和讨论，社区最关注的 **功能方向** 包括：

1. **会话管理与分支**  
   - 希望增加 `/fork` 命令或类似机制，在不干扰主会话的情况下处理临时问题。  
2. **插件体验优化**  
   - 插件安装时支持稀疏检出（只下载必要文件），减少带宽和磁盘占用。  
   - 插件技能在市场注册后能正确注入主 Agent 的可用技能列表。  
3. **BYOK 凭证动态刷新**  
   - 支持在不重启 CLI 的情况下更新 BYOK 提供商凭据，以适应短生命周期令牌。  
4. **搜索历史时间线**  
   - 类似 tmux 的搜索模式，方便快速跳转到之前的会话条目。  
5. **MCP 集成增强**  
   - 改进 MCP 服务器的策略检查与注册流程，减少“被策略阻止”的误判。  
6. **Windows 平台兼容性**  
   - 修复沙箱、剪切板、PowerShell 受限模式等问题，提升企业环境体验。

---

## 开发者关注点

近期社区反馈中的 **高频痛点** 与 **共性需求**：

- **稳定性 & 崩溃**  
  - V8 堆内存溢出（OOM）是最大吐槽点，涉及长会话、压缩、事件存储故障等场景。  
  - 会话意外死亡或永久卡死，导致需要频繁重启进程。  
- **认证与授权**  
  - 认证令牌不刷新、进程级凭证失效、OAuth 流程中断等问题严重影响持续使用。  
  - 桌面应用与 CLI 之间凭证注册的可靠性不足。  
- **配置与策略**  
  - 沙箱策略在未完全确定时强制开启，覆盖用户主动关闭设置。  
  - 企业级 MCP 注册被策略误封，缺乏清晰的错误原因。  
- **平台支持**  
  - WSL2 ARM64 和 Windows 受限 PowerShell 环境存在多处兼容性缺陷。  
  - Linux 老旧 GLIBC 版本导致二进制无法启动。  
- **更新体验**  
  - 自动更新成功率低，需要多次尝试才能升级。

---

**数据截止**：2026-09-24 23:59 UTC  
**报告生成**：2026-09-25 AI 技术分析师  
**数据来源**：GitHub [github/copilot-cli](https://github.com/github/copilot-cli)

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

# Kimi Code CLI 社区动态日报 | 2026-09-25

---

## 今日速览

过去24小时内，Kimi Code CLI 仓库无新版本发布，无新 Issue 产生。唯一值得关注的动态是 **PR #2622（已合并）**：将 `pykaos` 工作区中的 `asyncssh` 依赖从 2.21.1 升级至 2.23.1，修复了两个中高危安全漏洞（GHSA-2wxc-x7rj-hg8f、GHSA-qr67-gv47-xwwh）。社区当前处于静默期，无用户反馈新增。

---

## 版本发布

无

---

## 社区热点 Issues

**统计时段内无新 Issue 或更新。** 仓库当前所有 Issue 均为已关闭或长期未更新状态，无活跃讨论。

---

## 重要 PR 进展

### #2622 — [CLOSED] deps: bump asyncssh to 2.23.1 in pykaos (GHSA-2wxc-x7rj-hg8f)
- **作者**: katsugtgz  
- **创建/更新**: 2026-08-28 / 2026-09-24  
- **摘要**: 将 `packages/kaos/pyproject.toml` 中 `asyncssh` 从 `==2.21.1` 升级至 `2.23.1`，对应 `uv.lock` 同步更新。修复的两个安全漏洞均涉及 SSH 协议实现中的认证绕过风险。  
- **状态**: 已合并  
- **链接**: [MoonshotAI/kimi-cli PR #2622](https://github.com/MoonshotAI/kimi-cli/pull/2622)

> 该 PR 是过去24小时内唯一有状态变更的 PR，虽然发布日期较早，但于2026-09-24由维护者合并，属于安全修复类合并，对使用 pykaos 组件的用户有直接影响。

---

## 功能需求趋势

由于过去24小时无新 Issue，无法基于最新数据归纳趋势。根据历史数据，社区长期关注以下几个方向（参考此前动态）：

1. **IDE 集成**：VS Code / JetBrains 插件支持  
2. **性能优化**：大文件处理、并发推理延迟  
3. **新模型支持**：如 DeepSeek V3、Qwen 2.5 等  
4. **本地化部署**：私有化数据与断网场景支持

---

## 开发者关注点

**过去24小时无新开发者反馈。** 近期常见痛点（来自历史记录）：

- API 密钥配置流程不够友好  
- 部分终端（Windows PowerShell）下 ANSI 转义字符显示异常  
- 长对话上下文窗口溢出时缺少明确提示

---

*数据来源：github.com/MoonshotAI/kimi-cli，统计时段 2026-09-24 18:00 UTC — 2026-09-25 18:00 UTC。*

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

好的，作为 AI 开发工具的技术分析师，根据您提供的 GitHub 数据，我为您生成了 2026-09-25 的 OpenCode 社区动态日报。

---

# OpenCode 社区动态日报 — 2026-09-25

## 今日速览

今日社区动态主要集中在 V2 配置 Schema 验证失效、用户账号被误封以及多 MCP 服务器冷启动失败的讨论上。核心开发者提交了多项关键修复，包括针对 `gray-matter` 缓存中毒、TUI 崩溃以及模型上下文窗口资源优化的 PR，态势平稳且高效。

## 版本发布

过去 24 小时内无新版本发布。

## 社区热点 Issues

1.  **#49057：Muse Spark 1.3 免费访问受限，无申诉路径**
    - **摘要**：用户在使用 OpenCode Zen 提供商的 Muse Spark 1.3 免费模型时，所有会话均返回 `[user_blocked]` 错误，且无任何申诉渠道。这是今日争议最大的 Issue，评论数量高达 15 条，社区反响强烈。
    - **链接**: [Issue #49057](https://github.com/anomalyco/opencode/issues/49057)

2.  **#43748：V2 配置 Schema 认证错误，拒绝有效字段**
    - **摘要**：发布于 `opencode.ai/config.json` 的 JSON Schema 描述的是 V1 旧版格式，与 V2 文档不符。这导致编辑器 IntelliSense 和校验工具将 `skills`、`mcp.*`、`permissions` 等有效 V2 字段标记为错误。该问题获 9 个 👍，说明影响了大量向 V2 迁移的开发者。
    - **链接**: [Issue #43748](https://github.com/anomalyco/opencode/issues/43748)

3.  **#50843：GitLab Duo 工作流在自管理实例上失败**
    - **摘要**：用户报告 GitLab Duo 工作流模型在自管理的 GitLab 实例上无法正常工作，涉及工作目录上下文获取和 OAuth 令牌过期刷新问题。这对企业级用户部署造成阻碍。
    - **链接**: [Issue #50843](https://github.com/anomalyco/opencode/issues/50843)

4.  **#48743：多个本地 MCP 服务器冷启动并发失败**
    - **摘要**：Windows 桌面用户配置了大量（如 14+）本地 stdio MCP 服务器后，在会话启动时所有服务器都被标记为错误，需要用户手动逐一重启。社区正在讨论一种官方的“预热/预加载”机制来解决此问题。
    - **链接**: [Issue #48743](https://github.com/anomalyco/opencode/issues/48743)

5.  **#50091：免费使用配额重置异常**
    - **摘要**：用户反馈免费配额在预期周期后并未重置，而是延长了限制时间，导致无法使用服务。该问题获得了 4 个 👍，说明有不少用户遭遇了计费系统的疑似 Bug。
    - **链接**: [Issue #50091](https://github.com/anomalyco/opencode/issues/50091)

6.  **#51087：非英语区域设置下 TodoWrite 导致会话崩溃**
    - **摘要**：在非英语语言环境下（已确认泰语），当会话中出现 `TodoWrite` 工具调用时，UI 渲染失败并报错 `TypeError: Iterable yielded undefined`，导致整个会话时间线无法显示。这是一个关键的国际化 Bug。
    - **链接**: [Issue #51087](https://github.com/anomalyco/opencode/issues/51087)

7.  **#50986：One Dark Pro 主题下工作区消息对比度过低**
    - **摘要**：用户反馈在使用 One Dark Pro 主题时，工作区会话中的用户消息文本与背景的对比度仅为 1.2:1，完全无法辨认。这是一个影响部分用户日常使用的 UI 可用性问题。
    - **链接**: [Issue #50986](https://github.com/anomalyco/opencode/issues/50986)

8.  **#51218：无效 YAML 前言的 Skills 文件被静默丢弃**
    - **摘要**：在一个长期运行的 `opencode serve` 进程中，`SKILL.md` 文件如包含无效 YAML 前言，会被静默忽略且无任何错误日志。更严重的是，`gray-matter` 库的缓存机制会导致问题“传染”，引发数据一致性问题。
    - **链接**: [Issue #51218](https://github.com/anomalyco/opencode/issues/51218)

9.  **#51202：GPT-6 Luna 压缩错误**
    - **摘要**：用户在未达到最大上下文长度时，对 `gpt-6 luna` 模型执行上下文压缩功能时收到错误提示。这可能是模型上下文的计算或阈值逻辑存在 Bug。
    - **链接**: [Issue #51202](https://github.com/anomalyco/opencode/issues/51202)

10. **#51244：请求增加本地/云端/混合模式选择**
    - **摘要**：用户提出新功能请求，希望能更便捷地在本地模型 (Ollama) 和云端模型 (OpenRouter, Anthropic) 之间切换，而非通过繁琐的 Provider 配置和模型选择器。这反映了社区对更灵活模型使用方式的诉求。
    - **链接**: [Issue #51244](https://github.com/anomalyco/opencode/issues/51244)

## 重要 PR 进展

1.  **#51245：修复 `gray-matter` 缓存问题**
    - **内容**：此 PR 直接解决了 Issue #51218。原因是 `gray-matter` 库在解析 YAML 前会将文件内容写入缓存，导致即使解析失败，缓存也被“污染”，后续请求会得到错误结果。
    - **链接**: [PR #51245](https://github.com/anomalyco/opencode/pull/51245)

2.  **#51242：验证 Code Mode 的 test262 测试**
    - **内容**：这是一个纯测试基础设施的更新，旨在将 `test262` 标准测试套件中的所有 `built-ins` 和 `language` 目录加入测试清单，并排除那些不被解释器支持的全局对象相关的文件，提升代码模式的鲁棒性。
    - **链接**: [PR #51242](https://github.com/anomalyco/opencode/pull/51242)

3.  **#51240：修复桌面版内嵌浏览器显示问题**
    - **内容**：修复了当菜单或弹出窗口（如悬停标签卡）覆盖内嵌浏览器时，浏览器页面会变空白的问题。
    - **链接**: [PR #51240](https://github.com/anomalyco/opencode/pull/51240)

4.  **#50619：修复 ACP 插件激活时序问题**
    - **内容**：修复了 ACP 服务在加载新会话目录前未调用 `plugin.awaitActivation` 的时序问题，该问题可能导致插件提供的 Provider 无法被异步发现和加载。
    - **链接**: [PR #50619](https://github.com/anomalyco/opencode/pull/50619)

5.  **#51239：修复 Code Mode 中对象解构和 Date 组件转换**
    - **内容**：修复了在 Code Mode 中，对原始值进行对象解构（如 `const { length } = "abc"`）时会报错的问题，并修复了 `Date` 组件在转换时的一些细微 Bug。
    - **链接**: [PR #51239](https://github.com/anomalyco/opencode/pull/51239)

6.  **#51210：修复 TUI 因 `fs.watch` 崩溃的问题**
    - **内容**：此 PR 修复了 TUI 在遇到 `ENOSPC` (文件系统监听器耗尽) 等错误时，因 `fs.watch` 抛出同步异常而直接崩溃的问题。
    - **链接**: [PR #51210](https://github.com/anomalyco/opencode/pull/51210)

7.  **#51235：优化自动上下文压缩的触发阈值**
    - **内容**：将自动压缩的触发点从固定的 20k/32k 改为根据模型上下文窗口大小动态调整，默认在达到可用输入窗口的 85% 时开始压缩，避免小窗口模型在每次步骤都被强制压缩。
    - **链接**: [PR #51235](https://github.com/anomalyco/opencode/pull/51235)

8.  **#51021：将输出限制适配到上下文窗口**
    - **内容**：一个较大的功能更新。它使输出的 token 限制能够更好地适配不同模型的上下文窗口大小，修复了“思考预算”等因限制发送而中断的问题。
    - **链接**: [PR #51021](https://github.com/anomalyco/opencode/pull/51021)

9.  **#50965：增加模型选择的 Hook**
    - **内容**：新特性 PR，为会话添加了一个 `model.select` Hook，允许插件在每次模型调用前动态选择模型，为高级用户提供了更灵活的路由能力。
    - **链接**: [PR #50965](https://github.com/anomalyco/opencode/pull/50965)

10. **#51237：优化标题生成模型，避免浪费**
    - **内容**：修复了 Copilot 标题生成时错误选择大模型（如 `gpt-5.6-luna`）的问题，使其改为使用更便宜的 `copilot-utility-small` 模型，避免不必要的计费。
    - **链接**: [PR #51237](https://github.com/anomalyco/opencode/pull/51237)

## 功能需求趋势

从今日的 Issues 来看，社区最关注的功能方向可以归纳为以下三点：

1.  **模型使用与控制的灵活性**：用户不再满足于简单的 Provider 配置，而是希望有更精细化的控制，例如 (#51244) 一键切换本地/云端模式，以及 (#51241) 插件允许自定义 Provider 图标。对模型选择的路由逻辑也提出了更灵活的需求 (#50965)。

2.  **权限管理的完善与透明化**：多个关于权限的 Bug (#51224, #51223) 表明，现有的权限弹窗系统在处理并发、代码模式下的 MCP 工具调用时存在缺陷，导致会话无响应或工具调用被“挂起”。用户希望权限系统更稳定、可见。

3.  **UI/UX 体验的深化优化**：除了修复对比度 (#50986) 和国际化崩溃 (#51087) 这类基础 Bug，社区开始关注更精细的交互体验，如 (#51229) 提出 TUI 中可折叠推理过程和工具调用输出、隐藏思考链条，以提高对话可读性。

## 开发者关注点

- **配置和 Schema**：V2 配置 `$schema` 与实际字段不匹配的问题 (#43748) 是社区最大的痛点，直接影响配置体验。同时，`jsonc` 文件支持不足 (#48786) 也是一个持续被提及的问题。
- **稳定性问题**：多个 Issue 指向了特定场景下的崩溃或功能失效，如非英语环境下的 Requirements/工具渲染 (#51087)、桌面端多 MCP 冷启动失败 (#48743) 等，这些问题严重影响核心工作流。
- **账号与计费**：用户账号被无通知、无申诉渠道地限制 (#49057) 以及免费配额重置异常 (#50091) 这两类问题，直接关系到用户信任和产品体验，是最需要开发者重点关注的“红线”问题。
- **遗留 Issue**：开发者社区中有部分历史 Issue 因某些原因被关闭但问题仍然存在，如 `.jsonc` 的支持 (#48786) 和标题生成失败 (#25344)，社区希望官方能重新审视，这反映出 Bug 跟踪和复现机制需要改善。

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

好的，这是为您生成的 Pi 社区动态日报。

---

## Pi 社区动态日报 | 2026-09-25

**数据来源:** github.com/badlogic/pi-mono (Earendil Works / Pi)

### 今日速览

今日社区活跃度极高，修复与功能提案密集涌现。尽管无新版本发布，但多项针对 TUI 渲染、平台兼容性（尤其是 Windows WSL 路径问题）和扩展系统稳定性的关键修复已进入合并阶段。此外，对新兴模型（如 GPT-6 Astra）的支持优化和遥测基础设施的扩展成为社区讨论热点。

### 社区热点 Issues （10 条）

1.  **#9361: Windows 下 `shellPath` 配置被静默忽略**
    - **重要性:** 严重。Windows 用户配置的 `bash` 路径在加载扩展后被忽略，系统转而使用 WSL 的 `bash.exe`，导致开发环境行为不一致，极难排查。
    - **社区反应:** 评论达 11 条，开发者关注度高，但尚未有核心团队回复或修复方案。
    - **链接:** [Issue #9361](https://github.com/earendil-works/pi/issues/9361)

2.  **#8896: `/export HTML` 静默丢弃隐藏上下文消息**
    - **重要性:** 高。用于减少 TUI 噪音的 `display: false` 消息，在导出成 HTML 后完全丢失。这导致导出的会话记录不完整，失去了对模型推理过程的宝贵 trace 信息。
    - **社区反应:** 评论 8 条。已有一个相关的修复 PR (#10020) 提出，社区期待合并。
    - **链接:** [Issue #8896](https://github.com/earendil-works/pi/issues/8896)

3.  **#8643: Bedrock 上 OpenAI 模型拒绝处理工具结果中的图片**
    - **重要性:** 中。使用 AWS Bedrock 上的 OpenAI 模型时，工具返回的图片链接无法被正确处理，破坏了多模态工具的可用性。贡献者已准备好修复方案。
    - **社区反应:** 获得 2 个 👍，开发者社区活跃，但修复路径在等待官方 review。
    - **链接:** [Issue #8643](https://github.com/earendil-works/pi/issues/8643)

4.  **#9674: Mistral 模型对话流中，空内容 `delta` 导致文本块异常打开**
    - **重要性:** 中。主要影响特定的 GLM 5.x 模型，会生成空白内容，导致回放时出错。此问题是旧 issue (#8069) 的后续，修复可恢复对原生 Mistral 提示缓存的利用。
    - **社区反应:** 7 条评论，表明这是一个针对特定模型但影响感知质量的问题。
    - **链接:** [Issue #9674](https://github.com/earendil-works/pi/issues/9674)

5.  **#9255: 长对话转录导致 TUI 全屏重绘风暴和文本跳跃**
    - **重要性:** 高。当对话历史超过终端高度时，TUI 会陷入持续的全屏重绘循环，导致画面剧烈抖动、文字重叠。严重影响用户与 AI 长时交互的体验。
    - **社区反应:** 获得 1 个 👍，7 条评论，开发者对性能问题的反馈非常具体。
    - **链接:** [Issue #9255](https://github.com/earendil-works/pi/issues/9255)

6.  **#9508: Pi 向兼容 OpenAI API 的第三方提供商发送了不支持的字段**
    - **重要性:** 高。Pi 的请求体中含有 OpenAI 特有的字段、角色或认证头，导致很多兼容提供商（如本地部署的 LLM）返回 400/422 错误，限制了工具的通用性。
    - **社区反应:** 6 条评论，这是一个影响范围较广的兼容性问题。
    - **链接:** [Issue #9508](https://github.com/earendil-works/pi/issues/9508)

7.  **#9566: 模型上下文窗口大小默认使用 128k，忽略真实可用值**
    - **重要性:** 高。当配置的模型 ID 与提供商暴露的 ID 匹配时，Pi 会错误地使用默认的 128k 上下文大小，而不是自动发现模型的实际最大值，导致资源浪费或功能受限。
    - **社区反应:** 获得 3 个 👍（最多），评论 5 条。说明这是一个用户普遍遇到的问题。
    - **链接:** [Issue #9566](https://github.com/earendil-works/pi/issues/9566)

8.  **#9512: 使用 GPT-6 Astra 时，上下文压缩因 Token 上限而失败**
    - **重要性:** 中到高。当使用 `max` 推理能力的 GPT-6 Astra 时，上下文压缩过程（summarization）经常因触发生成 Token 上限而失败，导致上下文溢出无法恢复。
    - **社区反应:** 获得 1 个 👍，5 条评论，是高价值模型用户的痛点。
    - **链接:** [Issue #9512](https://github.com/earendil-works/pi/issues/9512)

9.  **#9932: 扩展生命周期钩子 `before_agent_start` 中工具移除的顺序错误**
    - **重要性:** 中。开发者在 `before_agent_start` 钩子中使用 `setActiveTools()` 移除的工具，会被后续设置了 `forceSystemPrompt` 的钩子取消移除操作，导致工具控制逻辑失效。
    - **社区反应:** 4 条评论，这是一个比较隐蔽的扩展开发问题。
    - **链接:** [Issue #9932](https://github.com/earendil-works/pi/issues/9932)

10. **#10008: 用户反馈 Bug 报告无人处理，被自动关闭**
    - **重要性:** 情绪价值高 / 流程警示。用户提交 Bug 后发现是重复报告，且指出项目对开放性 issue（如 #9566）缺乏回应和跟进，抱怨自动关闭机制。
    - **社区反应:** 4 条评论，反映了社区对项目维护响应速度的关切。
    - **链接:** [Issue #10008](https://github.com/earendil-works/pi/issues/10008)

### 重要 PR 进展 （10 条）

1.  **#10020: 为 HTML 导出添加隐藏消息切换按钮**
    - **内容:** 修复 #8896，为导出的 HTML 文件添加一个切换按钮，允许用户显示/隐藏 `display: false` 的上下文消息。
    - **状态:** 已合并。
    - **链接:** [PR #10020](https://github.com/earendil-works/pi/pull/10020)

2.  **#10021: 为 `bash` 工具调用中的 Heredoc 和内联脚本添加语法高亮**
    - **内容:** 提升 TUI 体验，尤其针对倾向使用内联脚本而非内置编辑工具的模型。
    - **状态:** 开放中。
    - **链接:** [PR #10021](https://github.com/earendil-works/pi/pull/10021)

3.  **#9957: 改进 Kitty 协议图像显示时的尺寸扭曲问题**
    - **内容:** 通过选择扭曲度更低的宽高比，优化了图片在 TUI 中的渲染效果，并非完全修复但显著改善了部分场景。
    - **状态:** 已合并。
    - **链接:** [PR #9957](https://github.com/earendil-works/pi/pull/9957)

4.  **#10016: 修复在 `abort` 后，通过 `wake` 发送的跟进消息被丢弃的问题**
    - **内容:** 当模型因为 `abort` 停止后，扩展通过 `sendMessage` 发送的 `followUp` 消息现在能被正确拾取并处理。
    - **状态:** 开放中。
    - **链接:** [PR #10016](https://github.com/earendil-works/pi/pull/10016)

5.  **#9714: 支持 Azure Foundry 的 Chat Completions API 部署**
    - **内容:** 扩展 Azure 提供商支持，使其能用于使用 Chat Completions API 的模型（如 DeepSeek V4 Pro），此前仅支持 Responses API。
    - **状态:** 开放中。
    - **链接:** [PR #9714](https://github.com/earendil-works/pi/pull/9714)

6.  **#8398: 重构 TUI 和主题支持，暴露颜色值**
    - **内容:** 重大重构，为 Agent 提供更强大的样式能力，并为未来支持非终端 UI 铺路。保持了向后兼容性。
    - **状态:** 已合并。
    - **链接:** [PR #8398](https://github.com/earendil-works/pi/pull/8398)

7.  **#10009: 新增 `pi-otel` OTLP/HTTP 遥测导出包**
    - **内容:** 实现了一个新的、依赖轻量的包，通过 OTLP/HTTP 协议导出 Pi 的内部 telemetry 数据，方便接入现代可观测性后端。
    - **状态:** 已合并。
    - **链接:** [PR #10009](https://github.com/earendil-works/pi/pull/10009)

8.  **#9995: 修复并行工具调用在 `abort` 后导致某些工具结果丢失的问题**
    - **内容:** 修正了当并行执行多个工具任务时，如果其中某个任务被中止，其他未开始的任务结果会被丢弃的 bug。
    - **状态:** 已合并。
    - **链接:** [PR #9995](https://github.com/earendil-works/pi/pull/9995)

9.  **#9993: 在 Google Vertex AI 提供商中支持 Anthropic Claude 模型**
    - **内容:** 允许用户通过 Google Cloud 凭证使用 Vertex AI Model Garden 上托管的 Anthropic Claude 模型，扩展了云提供商支持。
    - **状态:** 已合并。
    - **链接:** [PR #9993](https://github.com/earendil-works/pi/pull/9993)

10. **#9988: 修复 TUI 中 `read` 工具渲染时，行范围参数被当作字符串拼接的问题**
    - **内容:** 解决了特定模型（如 `xiaomi/mimo-v2.6-flash`）发送字符串类型参数时，导致 TUI 显示错误的行号计算（如 25 + “13” - 1 = 2512）。
    - **状态:** 已合并。
    - **链接:** [PR #9988](https://github.com/earendil-works/pi/pull/9988)

### 功能需求趋势

1.  **扩展系统增强与平台兼容性:** 社区持续聚焦于扩展机制的健壮性（如 #9932 的工具移除顺序、#8349 的续写检测）和跨平台一致性（#9361 的 Windows 路径问题）。这是目前开发中最核心的痛点和改进方向。
2.  **TUI 性能与视觉体验优化:** 针对长对话的重绘风暴（#9255）、图像渲染错误（#8938, #9957）以及粘贴功能缺陷（#9786）的修复提案频现，表明 TUI 的稳定性和可用性是影响日常使用的关键。
3.  **多模型与多提供商支持:** 对非标准 / 新兴提供商的支持需求强烈，包括修复兼容性错误（#9508）、添加新的 API 端点（#9714, #9993）、以及优化对特定模型（如 GPT-6 Astra、GLM、Mistral）的适配（#9512, #9674, #8643）。
4.  **遥测与可观测性:** 新 PR #10009 添加了 OTLP 导出，标志着 Pi 开始重视运行时的可观测性，这对企业级和高级开发者用户有很强的吸引力。
5.  **开发者体验与 API 稳定性:** 有提案要求导出构建请求体的函数（#10001），以便于二次开发或调试，反映了用户对更高阶自定义和将 Pi 作为库来集成的需求。

### 开发者关注点

-   **配置被静默忽略:** Windows 下 `shellPath` 的消失（#9361）和模型上下文大小的错误默认值（#9566）是重大陷阱，开发者需要花大量时间排查这些“约定优于配置”带来的副作用。
-   **扩展状态管理复杂:** `before_agent_start` 钩子中工具集变更的相互覆盖（#9932）和 `session_shutdown` 钩子导致进程卡死（#9997）表明，扩展的生命周期和状态管理设计仍有缺陷，增加了编写稳定扩展的难度。
-   **错误信息不友好:** 当 `session_shutdown` 卡住时无任何反馈（#9997）；当上下文压缩失败时，错误信息含糊不清（#9512）。开发者需要更清晰的错误日志和堆栈信息来定位问题。
-   **性能瓶颈:** 长会话下的 TUI 渲染性能（#9255）和 AST 解析（#9508 提及的兼容性问题根源）是开发者日常使用中遇到的性能瓶颈。
-   **API 兼容性陷阱:** Pi 在向第三方服务发送请求时，未能严格遵循开放的 API 规范（#9508），导致开发者需要额外配置或修改代码来适配私有/本地模型，这与工具“即开即用”的愿景相悖。

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 | 2026-09-25

---

## 1. 今日速览

今日社区发布了 **v0.24.5 正式版**及配套的 Desktop、TypeScript SDK 版本，修复了多个积压 bug。最受关注的是 **Windows 下 conhost.exe 进程泄漏**（#11303，17 条评论）和 **TUI 因 React 最大更新深度崩溃**（#11500）。PR 方面，**MCP 连接保持**（#12562）和 **Linux 剪贴板粘贴无声失败**（#12666）的修复进入审查阶段，社区对 **Managed Agent 双路径架构**（#12380）的讨论持续升温。

---

## 2. 版本发布

### v0.24.5 正式版
- **亮点**：解耦 channel 的组成员访问与 senderPolicy（[#12475](https://github.com/QwenLM/qwen-code/pull/12475)），无已知 Breaking Changes。
- **完整更新列表**：请参见 GitHub Release。

### v0.24.5-nightly.20260924
- **包含**：`feat(sdk-java): Add the Hosted Harness private client` 和 `test(java): pin runtime-broker guard`。

### SDK TypeScript v0.1.15
- **捆绑 CLI 版本**：0.24.5（从同一分支构建）。
- **说明**：该版本捆绑的 CLI 可直接用于 TypeScript 项目。

### Qwen Code Desktop v0.24.5
- **修复**：`fix(serve): preserve session creation failure diagnostics`（[#12331](https://github.com/QwenLM/qwen-code/pull/12331)）。
- **新增**：`feat(sdk-java): Add managed runtime`。

---

## 3. 社区热点 Issues（Top 10）

1. **[#11303] Windows 下 conhost.exe 进程泄漏，12h 累计 347 个进程 / ~2.8 GB**
   - **为何重要**：严重影响 Windows 用户的长期运行稳定性，评论数最高（17）。
   - **社区反应**：已标记为 P1 性能 bug，待人工处理。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/11303)

2. **[#12380] 提议：Managed Agent 双路径架构与分阶段交付**
   - **为何重要**：定义了未来“会话拥有持久性、工作区绑定、可恢复工具执行”的核心架构方向。
   - **社区反应**：17 条评论，涉及 daemon、Web Shell、SDK 等广泛范围。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/12380)

3. **[#11500] TUI 在多后台 Agent 完成时静默退出（React #185）**
   - **为何重要**：影响所有使用交互终端的用户，P1 优先级。
   - **社区反应**：16 条评论，已定位为 Ink 的 `useBoxMetrics` 布局循环问题。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/11500)

4. **[#11872] Web Terminal 报 "[Error: PTY not available]"——macOS 代码签名阻止预编译**
   - **为何重要**：阻碍 macOS 用户的 Web Shell 功能，P1 平台 bug。
   - **社区反应**：14 条评论，需解决 `@lydell/node-pty` 的打包与签名。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/11872)

5. **[#11119] 后台 Shell 输出与唤醒通知在会话运行时回收时被静默丢弃**
   - **为何重要**：导致长时间运行的后台任务丢失产出，P1 核心 bug。
   - **社区反应**：10 条评论，涉及 daemon 的 Web Shell 会话管理。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/11119)

6. **[#8596] 废弃 Electron 桌面应用，重命名 desktop-shell 为 desktop**
   - **为何重要**：社区长期呼唤的统一桌面架构变更，影响后续发布策略。
   - **社区反应**：10 条评论，已进入 roadmap 讨论。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/8596)

7. **[#12053] 精简 Goal 运行时：从当轮证据判断完成，删除证据目录与检查点**
   - **为何重要**：消除一次 Goal 完成后无意义的多轮执行，提升资源效率。
   - **社区反应**：8 条评论，已关闭，但实现方案仍有讨论空间。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/12053)

8. **[#12416] Remote-SSH：每个 POST /session 都失败，提示 `write EPIPE` / `BridgeChannelClosedError`**
   - **为何重要**：影响所有 VS Code Remote-SSH 用户，P1 联调 bug。
   - **社区反应**：8 条评论，正在排查 companion 0.24.2 版本问题。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/12416)

9. **[#12381] 在 HTTP 网关超时后恢复原始会话创建结果**
   - **为何重要**：解决浏览器收到 504 时无法安全重试会话创建的痛点。
   - **社区反应**：7 条评论，属于面向生产环境的可靠性需求。
   - [查看详情](https://github.com/QwenLM/qwen-code/issues/12381)

10. **[#11956] 无参数工具的 'parameters' 字段序列化为 null，导致 OpenAI 兼容网关拒绝请求**
    - **为何重要**：直接破坏与严格 OpenAI 兼容服务的集成，P2 核心 bug。
    - **社区反应**：7 条评论，需要修复序列化逻辑。
    - [查看详情](https://github.com/QwenLM/qwen-code/issues/11956)

---

## 4. 重要 PR 进展（Top 10）

1. **[#12666] fix(cli): notify when the Linux clipboard tool is found but its query fails**
   - **功能**：当 wl-paste/xclip 查询失败时，不再静默丢弃，而是给出提示。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12666)

2. **[#12621] fix(core): Preserve Claude thinking across tool turns**
   - **功能**：保留 Claude 模型在工具调用间的 thinking 块，确保安全签名。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12621)

3. **[#12559] fix(cli): match ink's OpenTUI popup geometry and completion truncation**
   - **功能**：使 OpenTUI 渲染器与 ink 弹出框的几何形状、截断行为一致。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12559)

4. **[#12652] fix(web-shell): clear scrollbar-gutter in collapsed sidebar rail**
   - **功能**：修复侧边栏折叠时滚动条占位符导致布局偏移的问题。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12652)

5. **[#12562] fix(core): keep MCP server connected on a -32601 onerror**
   - **功能**：当 MCP 服务器返回 `-32601`（Method not found）时，不再断开连接，保持通信。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12562)

6. **[#12354] feat: add ui.hideStatusBar to reduce flickering in Qwen Code**
   - **功能**：新增设置 `ui.hideStatusBar`，允许隐藏状态栏减少闪烁。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12354)

7. **[#12358] feat(managed-agent): Add standalone managed agent stack**
   - **功能**：展示 Managed Agent 架构的端到端预览，包含 Java 控制平面、会话范围工具运行时等。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12358)

8. **[#12649] fix(standalone): pin @lydell/node-pty-linux-arm64 and fail release on missing prebuilds**
   - **功能**：为 Linux arm64 添加缺失的 `node-pty` 原生模块，并在发布时严格检查预编译文件。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/12649)

9. **[#11794] fix(cli): honor output language in stateless generation**
   - **功能**：无会话模式下的生成将应用 `general.outputLanguage` 设置，尊重用户语言偏好。
   - [查看详情](https://github.com/QwenLM/qwen-code/pull/11794)

10. **[#12626] fix(web-shell): fall back to a plain draft for New task in a Live chat without a draft target**
    - **功能**：在 Live 语音聊天会话中点击“New task”时，退回普通草稿，避免无工作区导致的错误。
    - [查看详情](https://github.com/QwenLM/qwen-code/pull/12626)

---

## 5. 功能需求趋势

从近期 Issues 可以看出社区最关注的方向：

- **会话管理与可靠性**：Managed Agent 双路径架构（#12380）、会话创建超时恢复（#12381）、后台 shell 输出丢失（#11119）——对生产环境稳定性要求增高。
- **多工作区 / 多根文件夹支持**：VS Code 多根工作区支持（#12628）、MCP 跨会话断开（#9675）——企业用户多项目协同场景。
- **性能与资源优化**：Windows 进程泄漏（#11303）、Goal 运行时精简（#12053）、系统一决策门（#12589）——降低资源占用和延迟。
- **UI/UX 改进**：TUI 崩溃（#11500）、隐藏状态栏（#6137）、侧边栏滚动条（#12453）——终端体验打磨。
- **MCP 兼容性**：MCP -32601 不中断连接（#12562、#12500）、参数序列化兼容 OpenAI（#11956）——工具生态互联。
- **Token 与上下文效率**：Agent 重复调查历史（#12579）、deferred 建议（#12235）——为本地 LLM 节省 token。

---

## 6. 开发者关注点

- **Windows 平台痛点多**：conhost.exe 进程泄漏、MCP 连接断开、PTY 不可用等问题频繁出现，社区期待专门针对 Windows 的稳定性修复。
- **TUI 崩溃影响日常使用**：多个后台 Agent 完成时的 React #185 错误导致终端直接退出，无错误提示，严重影响开发流程。
- **MCP 连接状态不透明**：工具调用后聊天挂起、权限丢失（#10056）、MCP 服务器在会话间断开（#9675）——开发者需要更清晰的连接状态可视化和自动重连。
- **后台任务通知延迟大**：最长延迟 12-19 分钟（#12207），批量释放导致信息过载，期望实时推送而非队列轮询。
- **权限队列阻塞所有会话**：一个空闲会话的未回答 prompt 会阻塞整个 daemon（#11795），开发者急需细粒度隔离或超时机制。

---

*数据来源：[QwenLM/qwen-code](https://github.com/QwenLM/qwen-code) | 生成时间：2026-09-25*

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，这是为您生成的 2026-09-25 DeepSeek TUI 社区动态日报。

---

# DeepSeek TUI 社区动态日报 | 2026-09-25

## 📈 今日速览
今日社区动态极为密集，主要以 **Bug 修复与系统稳定性加固** 为核心。创始人 @Hmbown 主导了大规模的“安全隐患审计”报告系列，提出了超过 10 个涉及崩溃安全、资源限制、竞态条件等底层问题，并已通过多个 PR 快速修复了子 Agent 预算死亡、会话恢复失败、编译错误等关键问题。同时，**官方模型路由** 和 **可插拔 Agent 记忆** 两大重量级功能提案正在社区热烈讨论中。

## 🐛 社区热点 Issues
1.  **[Feature] 可插拔 Agent 记忆：通用后端接缝，以 causal-memory / mem0 为参考实现**
    -  **重要性**: ⭐⭐⭐⭐⭐ (长期讨论, 核心功能)
    -  **社区反应**: 拥有 5 条评论，是近期最受关注的功能请求。用户希望打破当前硬编码的内存实现，支持第三方或自定义记忆后端，这是一个影响架构深度的长期需求。
    -  **链接**: [Issue #6050](https://github.com/Hmbown/Codewhale/issues/6050)

2.  **[Bug] 子 Agent 在每步输入上限达 10 万 tokens 时被杀死，且未进行压缩；应像父 Agent 一样压缩并继续**
    -  **重要性**: ⭐⭐⭐⭐⭐ (已修复的关键 Bug)
    -  **社区反应**: 由创始人直接报告和修复，反映了在复杂工作流中使用大上下文模型时的稳定性瓶颈。
    -  **链接**: [Issue #6504](https://github.com/Hmbown/Codewhale/issues/6504)

3.  **[Bug] 0.10.0 版本回退：Windows Terminal 多行粘贴会按行自提交**
    -  **重要性**: ⭐⭐⭐⭐ (影响特定用户群体的体验)
    -  **社区反应**: 反馈了 0.10.0 版本中一个此前已修复过的 Bug 再次出现，表明测试覆盖仍有缺口。
    -  **链接**: [Issue #6427](https://github.com/Hmbown/Codewhale/issues/6427)

4.  **[Bug] 首次运行：新用户从未看到入门引导；第一条消息丢失或重复，提供商选择器等界面面向开发者**
    -  **重要性**: ⭐⭐⭐⭐ (影响新用户留存)
    -  **社区反应**: 一份详细的新手体验审计报告，指出了 onboarding 流程的严重缺失，进而可能导致用户流失。
    -  **链接**: [Issue #6566](https://github.com/Hmbown/Codewhale/issues/6566)

5.  **[Bug] 压缩功能：记录的 16 次压缩中 15 次失败，摘要调用读取 ~219k tokens 且缓存命中率为 0%**
    -  **重要性**: ⭐⭐⭐⭐⭐ (严重影响性能和成本)
    -  **社区反应**: 一个非常严重的性能缺陷，几乎所有的压缩操作都无效，导致上下文窗口膨胀和缓存失效。
    -  **链接**: [Issue #6540](https://github.com/Hmbown/Codewhale/issues/6540)

6.  **[Bug] 背景工作：页脚显示步骤聊天噪音，Agent 名称不一致，高速缓存率被紧凑默认设置隐藏**
    -  **重要性**: ⭐⭐⭐⭐ (影响用户认知和信息获取)
    -  **社区反应**: 核心 UI 组件的问题，导致用户难以理解后台 Agent 的工作状态和系统性能。
    -  **链接**: [Issue #6565](https://github.com/Hmbown/Codewhale/issues/6565)

7.  **[Bug] 使用 deepseek-flash 模型时提示不支持图像输入**
    -  **重要性**: ⭐⭐⭐⭐ (影响特定模型体验)
    -  **社区反应**: 用户反馈了 DeepSeek 官方模型的功能兼容性问题。该问题后续已在 PR #6521 中解决。
    -  **链接**: [Issue #6421](https://github.com/Hmbown/Codewhale/issues/6421)

8.  **[Bug] 持久化写入不具备崩溃原子性（无 fsync 的 temp+rename / 部分提交）**
    -  **重要性**: ⭐⭐⭐⭐⭐ (数据安全与稳定性)
    -  **社区反应**: 这是“安全审计”系列中最严重的问题之一，揭示了数据库隐藏的崩溃安全风险。
    -  **链接**: [Issue #6555](https://github.com/Hmbown/Codewhale/issues/6555)

9.  **[Feature] 按对话设置：一个仅用于提案的设置工具，带有 per-change 审批卡和 /settings 命令**
    -  **重要性**: ⭐⭐⭐⭐ (创新功能构想)
    -  **社区反应**: 一个新颖的交互式设置方法，旨在解决用户不熟悉配置文件、设置难以发现的问题。
    -  **链接**: [Issue #6564](https://github.com/Hmbown/Codewhale/issues/6564)

10. **[Bug] `codewhale config set` 静默接受拼写错误和未知键；“你是不是想找”功能使用过期的键列表**
    -  **重要性**: ⭐⭐⭐ (配置体验问题)
    -  **社区反应**: 反映了 CLI 配置工具的健壮性和用户体验有待提升。
    -  **链接**: [Issue #6563](https://github.com/Hmbown/Codewhale/issues/6563)

## 🚀 重要 PR 进展
1.  **[feat] 官方模型路由：通过 /router 实现，集成 Jev (OpenRouter 或 TypeSafe) 及其他预设**
    -  **功能/修复**: 实现了用户友好的 GUI 模型路由配置，预置推荐方案，降低用户配置门槛。
    -  **链接**: [PR #6539](https://github.com/Hmbown/Codewhale/pull/6539)

2.  **[fix] 会话：窗内恢复接受了解析后的会话路径 (Windows)**
    -  **功能/修复**: 修复了 Windows 系统上因路径前缀问题导致无法恢复会话的关键 Bug。
    -  **链接**: [PR #6522](https://github.com/Hmbown/Codewhale/pull/6522)

3.  **[fix] 配置：deepseek-flash 在官方路由上接受图像输入**
    -  **功能/修复**: 修复了 DeepSeek Flash 模型无法处理图像输入的配置错误。
    -  **链接**: [PR #6521](https://github.com/Hmbown/Codewhale/pull/6521)

4.  **[fix] TUI：/model 列出你使用的模型：当前、固定/Fleet、最近使用；移除 legacy enabled_models**
    -  **功能/修复**: 优化了模型选择器的默认视图，使其更智能地展示用户常用模型。
    -  **链接**: [PR #6537](https://github.com/Hmbown/Codewhale/pull/6537)

5.  **[fix] 客户端：在任何 Chat Completions 路由上，推理内容始终被显示为“思考中”**
    -  **功能/修复**: 统一了所有模型推理内容的显示逻辑，修复了特定模型（如 Grok 4.7）思考过程不显示的问题。
    -  **链接**: [PR #6524](https://github.com/Hmbown/Codewhale/pull/6524)

6.  **[fix] CI (Windows)：让 NSIS 安装重试机制证明工具已成功安装**
    -  **功能/修复**: 修复了 CI 中 Windows 安装步骤的假阳性问题，提升了 CI 的可靠性。
    -  **链接**: [PR #6535](https://github.com/Hmbown/Codewhale/pull/6535)

7.  **[fix] 工具：可操作编辑遗漏，cwd 错误命名为根目录，无目标的 update_goal 为空操作**
    -  **功能/修复**: 修复了文件编辑错误信息不准确、工作目录显示问题，并处理了无目标时的 `update_goal` 空操作问题。
    -  **链接**: [PR #6548](https://github.com/Hmbown/Codewhale/pull/6548)

8.  **[fix] Agent：预算耗尽的子 Agent 将其确定性摘要作为可交付成果保留**
    -  **功能/修复**: 修复子 Agent 因预算耗尽而死亡时，其工作成果会丢失的问题。
    -  **链接**: [PR #6549](https://github.com/Hmbown/Codewhale/pull/6549)

9.  **[fix] 压缩：停止在回退窗口上的虚假紧急传递；复用 turn 的缓存前缀**
    -  **功能/修复**: 修复了 15/16 压缩操作失败的性能大 Bug，优化了缓存复用策略。
    -  **链接**: [PR #6544](https://github.com/Hmbown/Codewhale/pull/6544)

10. **[fix] 构建：清除 rustc 1.89 上未履行的 dead_code 期望；新增 MSRV CI 任务**
    -  **功能/修复**: 修复了使用最新 Rust 编译器时的构建错误，并设定了最低支持版本 (MSRV) 以保障构建稳定性。
    -  **链接**: [PR #6551](https://github.com/Hmbown/Codewhale/pull/6551)

## 💡 功能需求趋势
1.  **安全性**：社区对系统的稳定性和可靠性提出了更高要求，体现为大量关于**可插拔 Agent 记忆**、**资源/速率限制**和**无限制输入**的审计和提案。这表明用户希望 Codewhale 不仅能工作，还要**健壮、安全地工作**。
2.  **用户体验**：大量 Issue 和 PR 集中在新手引导、配置错误处理、UI 信息清晰度（如背景工作状态、模型选择器）等方面。这表明社区正从“能用”向“好用”转变，追求**更低的上手门槛和更清晰的反馈**，尤其是对 Windows 和新用户的优化。
3.  **现有功能故障排查**：关于压缩失败（#6540）、测试影响真实日志（#6534）、子 Agent 预算死亡（#6504）等 Issue 表明，社区正在**解决运行时稳定性和数据一致性的顽疾**，这是走向生产级应用的必要步骤。

## 🎯 开发者关注点
1.  **关键 Bug 复现与修复**：针对 `子 Agent 预算死亡` 和 `压缩失败` 这类影响工作流完成率的严重 Bug，开发者表现出极高的关注度，相关 Issue 被创始人迅速处理并关闭。
2.  **测试环境隔离**：`测试写入真实日志` 的 Bug 提示了测试环境与生产环境的隔离不足，这是开发者需要关注并改进测试基础设施的信号。
3.  **UI/UX 细节打磨**：“Esc”键功能冲突、工作流卡片信息过载、模型选择器默认列表不智能等问题，反映出 UI 细节仍存在大量使用上的摩擦，是后续版本优化的重点。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*