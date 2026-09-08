# AI CLI 工具社区动态日报 2026-09-08

> 生成时间: 2026-09-08 00:39 UTC | 覆盖工具: 9 个

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

# AI CLI 工具生态横向对比分析报告（2026-09-08）

## 1. 生态全景

当前 AI CLI 工具正从“命令式助手”向“持久化 Agent 平台”快速演进。各项目普遍聚焦于插件/MCP 扩展体系、会话持久性与多代理协作，但稳定性问题（会话卡死、数据丢失、平台兼容 Bug）仍是社区主要痛点。Windows 和 Linux 桌面体验成为差异化竞争关键，而模型路由透明度（如静默回退、配额计算异常）正在侵蚀用户信任。整体来看，开源社区驱动创新与商业产品（Copilot、Codex）形成并行竞争，技术壁垒逐渐从“模型能力”转向“工具链可靠性”和“用户可控性”。

## 2. 各工具活跃度对比

| 工具 | 当日热点 Issues 数 | 当日重要 PR 数 | 版本发布情况 |
|------|-------------------|---------------|-------------|
| Claude Code | 10 | 2 | 无新版本 |
| OpenAI Codex | 10 | 10 | 发布 `rust-v0.154.0-alpha.6` |
| Gemini CLI | 10 | 10 | 发布 `v0.60.0-nightly` |
| GitHub Copilot CLI | 10 | 2 | 无新版本（桌面版 1.1.15 已发布） |
| Kimi Code | 4 | 2 | 无新版本 |
| OpenCode | 10 | 10 | 无新版本 |
| Pi | 10 | 10 | 无新版本 |
| Qwen Code | 10 | 10 | 两个预发布（v0.23.1-preview.2, cua-driver v0.20.4） |
| DeepSeek TUI | 10 | 10 | 正在准备 v0.9.13 |

**说明**：Issues 数取自各日报列举的 Top 热点，实际仓库总 Issue 量远大于此。PR 数仅统计日报中“重要 PR 进展”部分。版本发布以日报明确提及为准。

## 3. 共同关注的功能方向

| 功能方向 | 涉及工具 | 具体诉求 |
|---------|---------|---------|
| **MCP/插件生态完善** | Claude Code, Copilot CLI, Kimi Code, Gemini CLI, OpenCode | 功能钩子（#91870）、项目级插件（#1665）、MCP 配置迁移（#1356）、OAuth 认证修复（#4017）、枚举扩展技能（#11281） |
| **会话持久性与可靠性** | Claude Code, Codex, Copilot CLI, Pi, Qwen Code | 数据静默删除（#59248）、会话恢复卡死（#43277）、子 agent 线程丢失（#30385）、后台 shell 输出丢弃（#11119） |
| **跨平台兼容（Windows）** | Claude Code, Codex, Copilot CLI, Kimi Code, Qwen Code | 窗口置顶（#89467）、宠物点击穿透（#41513）、新会话需归档旧会话（#4756）、IME 字符重复（#2584）、conhost 进程泄漏（#11303） |
| **模型路由透明度** | Gemini CLI, Pi, Qwen Code | 模型版本静默回退（#28859）、错误端点路由（#9209）、grammar 解析崩溃（#10530） |
| **Agent 行为可控性** | Claude Code, Kimi Code, DeepSeek TUI | Plan 模式（#1354）、自学习技能进化（#5860）、子代理管理不可靠（#40299）、重试上限（#8826） |
| **令牌/配额优化** | Codex, Gemini CLI, Qwen Code | 重复进入模型消耗配额（#35259）、短调用耗光全部配额（#42987）、延迟工具保留 prompt cache（#10410） |
| **性能与稳定性** | Pi, OpenCode, Qwen Code | 启动性能对标竞品（#7739）、会话永久卡死（#43277）、TUI 渲染层迁移（#8662）、CI 频繁失败 |

## 4. 差异化定位分析

| 工具 | 核心定位 | 差异化特征 | 目标用户 | 技术路线 |
|------|---------|-----------|---------|---------|
| **Claude Code** | 深度定制插件平台 | Function Hooks 提案（#91870）、智能记忆 MEMORY.md | 高阶开发者、插件生态建设者 | 参数化 `$` 对象 + 续传模型 |
| **OpenAI Codex** | 多模态计算 + TUI 沉浸 | Computer Use、宠物系统、iOS Remote | 全栈开发者、移动办公 | 多 Agent + Guardian 评审器 |
| **Gemini CLI** | 安全沙箱 + 模型兼容 | 容器沙箱隔离、bash 亲和性、多模型 fallback | 企业安全敏感场景 | 零依赖 OS 沙箱 + 确定性脱敏 |
| **Copilot CLI** | GitHub 生态深度绑定 | MCP OAuth、项目级插件、会话归档 | GitHub 重度用户 | 内置 Agent 技能 + 扩展 SDK |
| **Kimi Code** | 轻量快速入门 | 最小化功能集、Plan 模式需求明确 | 初创开发者、快速原型 | 单 Agent 模式 + MCP 互通 |
| **OpenCode** | 多 IDE 集成 + 开源平台 | VS Code 扩展呼声最高、BYOK 支持、本地 serve | 多 IDE 切换者、自建模型用户 | 厂商抽象层 + Web UI + TUI |
| **Pi** | 模型连接可靠性 + 多云 | 注重连接卡死修复、Ollama Cloud、设备码登录 | 云服务折腾者、多模型玩家 | 事件流队列 + 手动重试 API |
| **Qwen Code** | Web Shell + 后台自动化 | 动态工作流可视化、Mesh Agent 协作、daemon 模式 | DevOps、需要持久 Agent 的团队 | ACP 协议 + 容器化扩展 |
| **DeepSeek TUI** | 终端原生体验 + 原子化工具 | 多行粘贴检测、原子提交拆分、TUI 可定制化 | CLI 重度用户、Git 历史洁癖 | Hook 系统 + 自学习技能 |

## 5. 社区热度与成熟度

- **高活跃度（每日议题/PR > 20+，社区讨论深度高）**：**OpenCode**（148👍的 VS Code 扩展，50+ Issue/PR）、**Pi**（77评论的连接可靠性 issue，10+ PR 合并）、**Claude Code**（134评论的 Function Hooks）、**Codex**（35评论的 iOS Remote，20+ PR）
- **中等活跃度（每日 10-20 议题/PR，社区讨论持续）**：**Gemini CLI**（33评论的权限问题，10 PR）、**Copilot CLI**（9👍的 Windows 会话归档，2 PR）、**Qwen Code**（32评论的 TUI 迁移，10 PR）
- **较低活跃度（议题/PR 数较少，社区规模小）**：**Kimi Code**（仅 4 个更新 issue，2 PR，但点赞显示核心需求存在）、**DeepSeek TUI**（虽有多条 issue/PR，但项目已更名 CodeWhale，社区处于迁移期）

**成熟度评估**：
- **成熟稳定**：Claude Code、Codex、Copilot CLI —— 商业支持，版本迭代节奏稳健，但回归 Bug 仍频繁。
- **快速迭代**：OpenCode、Pi、Qwen Code —— 开源社区驱动，PR 合并频率高，功能创新多，但稳定性风险较高。
- **早期成长**：Kimi Code、DeepSeek TUI —— 功能聚焦，社区渴望基础能力完善（如 Plan 模式、多行粘贴），成长空间大。

## 6. 值得关注的趋势信号

1. **插件生态从“调用”走向“钩子”**：Claude Code 的 Function Hooks 提案（#91870）和 Copilot CLI 的 next-action 扩展原型（#4746）表明，工具正在从“调用 API”转向“注入行为”，这将深刻改变 Agent CLI 的可扩展性。

2. **数据主权要求急剧上升**：Claude Code 会话静默删除（#59248）、Gemini CLI 模型回退无警告（#28859）、Copilot CLI 输入内容被 Enter 丢弃（#4738）—— 用户对“静默操作”的容忍度趋近于零。透明度与可逆性将成为核心竞争力。

3. **Windows 用户成为“二等公民”的风险**：多个工具在 Windows 上出现严重平台 Bug（窗口置顶、宠物穿透、进程泄漏、ConPTY 未释放），且修复进度滞后于 macOS。这为 Windows 开发者带来显著的负体验差异化。

4. **子代理管理成为瓶颈**：Codex 主代理过早关闭子代理（#40299）、Gemini CLI 子代理伪造成功（#22323）、OpenCode 子任务权限黑洞（#44747）—— 多 Agent 协作的可靠性和诚实汇报是下一个必须攻克的难题。

5. **本地推理与云端模型的兼容性鸿沟**：Qwen Code 的 llama-server grammar 崩溃（#10530）、Pi 的 OpenRouter max_tokens 溢出（#8760）表明，本地部署模型与工具链的适配仍存在大量碎片化问题，制约了开发者从云端迁移到本地的意愿。

6. **“Plan 模式”成为标配预期**：Kimi Code（#1354）、DeepSeek TUI（#5860）用户明确要求 Agent 先规划后执行，而 Claude Code 的 Function Hooks 也隐含了对行为序列的控制能力。这反映出开发者对 Agent 执行“确定性和可审查性”的迫切需求。

**对开发者的参考价值**：选择工具时建议优先评估其会话恢复机制、跨平台支持（尤其是你的主力 OS）和插件生态的开放性。若团队依赖多 Agent 协作，需特别关注子代理管理缺陷；若涉及敏感数据，务必确认其数据清理策略是否透明可配置。同时，关注以上趋势中的“透明度”和“可控性”指标，它们正在从“加分项”变为“基本要求”。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

好的，作为专注于 Claude Code 生态的技术分析师，以下是根据您提供的 `anthropics/skills` 仓库数据（截至 2026-09-08）生成的社区热点报告。

---

### Claude Code Skills 社区热点报告 (2026-09-08)

#### 1. 热门 Skills 排行

以下按社区讨论热度（评论数、问题反复出现频率）排序，列出当前最受关注的 Skills 及其动态。

1.  **`skill-creator` 修复与优化 (PR #1298, #1099, #1050)**
    *   **功能**: 这是 Claude Code 的官方技能创建工具链，用于评估、循环优化技能描述。本次讨论的核心是修复其 `run_eval.py` 脚本的严重 Bug。
    *   **社区热点**: 用户报告 `run_eval.py` 始终报告 `0%` 的召回率，导致技能优化完全失效，且该问题在 Windows 平台尤其严重，涉及子进程调用、管道读取和编码问题。多个 PR 从不同角度尝试修复，但均未合并，表明修复难度高且社区高度关注。
    *   **状态**: **OPEN** (未合并)
    *   **链接**: [PR #1298](https://github.com/anthropics/skills/pull/1298), [PR #1099](https://github.com/anthropics/skills/pull/1099), [PR #1050](https://github.com/anthropics/skills/pull/1050)

2.  **文档排版技能 (PR #514)**
    *   **功能**: 针对 AI 生成文档中常见的孤行、寡段、编号错位等排版问题进行质量控制的技能。
    *   **社区热点**: 讨论集中在 AI 生成内容的“最后一步”质量把控上。用户普遍认为这是一个高频、刚需的场景，能显著提升文档的专业性和可读性。
    *   **状态**: **OPEN** (未合并)
    *   **链接**: [PR #514](https://github.com/anthropics/skills/pull/514)

3.  **SCNet HPC 集群操作技能 (PR #1615)**
    *   **功能**: 一个面向高性能计算（HPC）用户的技能，支持通过 SSH 和 Slurm 工作流操作 SCNet 集群。
    *   **社区热点**: 此技能收到关注，表明社区对 Claude Code 在专业领域（如科学计算、工程仿真）的自动化能力有强烈需求。讨论聚焦于对特定集群配置文件的适配性。
    *   **状态**: **OPEN** (未合并)
    *   **链接**: [PR #1615](https://github.com/anthropics/skills/pull/1615)

4.  **ODT 文档格式技能 (PR #486)**
    *   **功能**: 支持创建、填充、读取和转换 OpenDocument 格式（.odt, .ods）的技能。
    *   **社区热点**: 反映了社区对开源办公格式的原生支持需求，尤其是在需要与 LibreOffice 等工具链集成的场景中。
    *   **状态**: **OPEN** (未合并)
    *   **链接**: [PR #486](https://github.com/anthropics/skills/pull/486)

5.  **前端设计技能改进 (PR #210)**
    *   **功能**: 对现有 `frontend-design` 技能的全面修订，旨在提升其清晰度、可操作性和内部一致性。
    *   **社区热点**: 用户不仅期望技能存在，更要求其指令精准、可执行，反映了社区对技能质量本身的追求。
    *   **状态**: **OPEN** (未合并)
    *   **链接**: [PR #210](https://github.com/anthropics/skills/pull/210)

6.  **元技能：质量与安全分析器 (PR #83)**
    *   **功能**: 新增两个“元技能”用于评估其他技能的质量和安全性。`skill-quality-analyzer` 从结构、文档、示例等维度评分；`skill-security-analyzer` 则进行安全审计。
    *   **社区热点**: 此 PR 与安全问题（Issue #492）讨论高度相关，显示社区对技能生态的治理和信任度极为关注。用户希望有自动化工具来鉴别和筛选高质量、安全的社区技能。
    *   **状态**: **OPEN** (未合并)
    *   **链接**: [PR #83](https://github.com/anthropics/skills/pull/83)

#### 2. 社区需求趋势

从 Issues 和 PR 的讨论中，可以提炼出社区对 Skills 的四个核心期望方向：

1.  **安全与信任机制**: 这是当前最强烈的诉求。社区成员（如 Issue #492 所述）对“社区技能冒充官方技能”的信任边界滥用问题表示严重担忧。用户需要官方提供命名空间治理、数字签名、安全审计或分级机制，以区分官方和社区技能，并授予不同的权限。
2.  **组织级技能共享与协作**: 用户（如 Issue #228 所述）不满于通过文件传输手动分享技能，强烈要求官方提供组织内的技能库、分享链接或市场，实现技能在企业内部的便捷分发与版本管理。
3.  **开发工具链的可靠性**: 围绕 `skill-creator` 的多个未解决 Bug 表明，技能开发者（尤其是非官方用户）对稳定的开发、测试和评估工具链有迫切需求。一个良好运作的 `run_eval.py` 是技能迭代优化的基础。
4.  **元技能与质量门控**: 社区不仅想创建技能，更想评估技能。对“技能质量分析器”、“安全分析器”以及“推理质量门控”等元技能的讨论，表明社区希望建立一套自发的质量保障体系，提升整个生态的健壮性。

#### 3. 高潜力待合并 Skills

以下 PR 评论活跃，社区需求明确，且技术方案相对清晰，有望在近期获得合并：

1.  **文档排版技能 (PR #514)**: 解决的是生成式 AI 文档的“临门一脚”问题，痛感强，适用范围广，代码实现相对独立，合并优先级高。
2.  **ODT 文档格式技能 (PR #486)**: 补全了 Claude Code 对常用办公格式的支持版图，与现有的 PDF、DOCX 技能形成互补，是开源办公生态的重要拼图。
3.  **前端设计技能改进 (PR #210)**: 这不是一个新技能，而是对现有技能的“深加工”。社区对此类提升现有技能质量的 PR 认可度很高，合并风险低，能立竿见影地改善用户体验。
4.  **元技能：质量与安全分析器 (PR #83)**: 直接回应了社区最大的安全隐忧（Issue #492），是建立健康生态的关键工具。虽然实现复杂，但其战略价值极高，一旦技术验证通过，有望被官方采纳或合并。

#### 4. Skills 生态洞察

**一句话总结：当前社区在 Skills 层面最集中的诉求，是建立一个**可靠、安全、可共享**的技能全生命周期管理体系，从“能造技能”转向“能造好技能、用好技能、管好技能”。** 技能本身不再稀缺，围绕技能的工具链、安全治理和协作机制成为新的瓶颈。

---

好的，这是为你准备的 2026-09-08 Claude Code 社区动态日报。

---

# 2026-09-08 Claude Code 社区动态日报

## 📰 今日速览

今日社区最热门话题是 **#91870 Function Hooks** 提案，该特性有望将插件能力提升10倍，引发了134条热烈讨论。与此同时，老生常谈的会话记录**数据丢失问题**（#59248, #62476）仍在持续发酵，用户对数据安全的焦虑加剧。此外，插件生态的兼容性问题（#26951）也因长期未解而再次升温。

## 🔥 社区热点 Issues

1.  **[#91870] 功能钩子：让插件强大10倍** 🔥
    - **重要性**：当前社区最重磅的提案。作者提出了“Function Hooks”概念，通过参数化 `$` 对象和类似Express/Koa的“next”续传模型，允许开发者深度修改Claude Code行为，同时确保安全性和组合性。若实现，将彻底改变Claude Code的插件生态。
    - **社区反应**：134条评论，82个👍，社区讨论极为热烈。
    - **链接**: [issue #91870](https://github.com/anthropics/claude-code/issues/91870)

2.  **[#59248] 静默清理导致会话记录丢失** 🔥
    - **重要性**：老牌但仍在升级的严重bug。用户反馈Claude Code在未经任何警告、确认或提供恢复途径的情况下，静默删除了整个工作区的会话记录。这对依赖历史上下文的开发者是严重的工作流中断。
    - **社区反应**：42条评论，讨论持续，用户对数据安全表示严重担忧。
    - **链接**: [issue #59248](https://github.com/anthropics/claude-code/issues/59248)

3.  **[#62476] 默认30天静默删除会话记录**
    - **重要性**：与#59248同一类问题，强调了“静默”和“默认”行为的不可接受性。用户要求至少提供关闭自动清理或延长保留期的选项。
    - **社区反应**：25条评论，24个👍，表明这并非孤立事件，而是普遍痛点。
    - **链接**: [issue #62476](https://github.com/anthropics/claude-code/issues/62476)

4.  **[#26951] macOS插件安装失败 (HTTP 404)**
    - **重要性**：一个长期未解决的插件生态问题，严重影响macOS用户体验。`plugins.claude.ai` 域名无法解析，导致插件安装完全受阻。
    - **社区反应**：22条评论，持续有用户反馈此问题，表明基础设施稳定性需要加强。
    - **链接**: [issue #26951](https://github.com/anthropics/claude-code/issues/26951)

5.  **[#89467] [Windows] 桌面应用窗口始终置顶**
    - **重要性**：严重干扰Windows用户多任务工作流。用户无法通过任何设置、快捷键或菜单关闭此行为，体验非常糟糕。
    - **社区反应**：19条评论，28个👍，社区对于此基本窗口管理功能的缺失感到不满。
    - **链接**: [issue #89467](https://github.com/anthropics/claude-code/issues/89467)

6.  **[#91188] 请求：使自动记忆压缩提醒阈值可配置**
    - **重要性**：`MEMORY.md` 的自动压缩提醒目前是硬编码的，当文件接近200行/25KB限制时会频繁提醒。高级用户希望调整此阈值以适应不同项目规模，优化使用体验。
    - **社区反应**：35条评论，社区普遍支持增加可配置性。
    - **链接**: [issue #91188](https://github.com/anthropics/claude-code/issues/91188)

7.  **[#88323] [Windows] MSIX打包损坏：代码完整性检查导致应用自毁**
    - **重要性**：一个严重的平台级bug。由于 `vk_swiftshader.dll` 被系统阻止，导致整个Claude Desktop MSIX包被标记为“已修改”，进而使应用无法启动。影响通过企业通道部署的用户。
    - **社区反应**：14条评论，问题已关闭，说明可能存在临时解决方案或已被标记为已知问题。
    - **链接**: [issue #88323](https://github.com/anthropics/claude-code/issues/88323)

8.  **[#66540] [Windows] 每次执行子进程时终端窗口闪烁**
    - **重要性**：影响开发效率的烦人问题。每次调用MCP服务器、Bash工具或子代理时，都会闪烁一个空白终端窗口，在多会话时尤其干扰。
    - **社区反应**：13条评论，持续有Windows用户抱怨此可见性bug。
    - **链接**: [issue #66540](https://github.com/anthropics/claude-code/issues/66540)

9.  **[#91371] [Windows] 本地定时任务静默挂起并阻塞后续任务**
    - **重要性**：影响“Routines”功能可用性的关键bug。本地Scheduled tasks会在运行中无警告地挂起，导致后续任务被永久阻塞，无法实现自动化工作流。
    - **社区反应**：6条评论，反馈者认为此bug严重破坏了自动化流程。
    - **链接**: [issue #91371](https://github.com/anthropics/claude-code/issues/91371)

10. **[#83302] 订阅计划应包含Fast Mode额度**
    - **重要性**：社区对定价和功能捆绑的诉求。许多Max订阅用户希望Fast Mode（Opus 5加速模式）的少量额度能包含在订阅费内，而不是作为单独的额外信用点购买。
    - **社区反应**：1条评论，但获得了12个👍，代表了一部分核心用户群体的共同心声。
    - **链接**: [issue #83302](https://github.com/anthropics/claude-code/issues/83302)

## 🚀 重要 PR 进展

（注：过去24小时内PR更新数量较少，以下为近期可查的2个主要更新）

1.  **[#26175] 修复：替换损坏的原生安装引导脚本**
    - **内容**：修复了 `curl -fsSL https://claude.ai/install.sh | bash` 脚本无法正确创建 `~/.local/bin/claude` 的问题，并阻止了该脚本错误删除用户现有的npm全局安装。
    - **重要性**：解决了新用户首次安装失败的关键问题，提升了开箱即用体验。该PR已合并。
    - **链接**: [PR #26175](https://github.com/anthropics/claude-code/pull/26175)

2.  **[#39043] 移除“复古未来主义”的前端设计建议**
    - **内容**：作者 `t3dotgg` 提议从Claude Code的默认技能库中移除建议使用“retro-futuristic”风格的指令。
    - **重要性**：反映了社区对默认技能的质量、相关性和风格引导的关注，希望通过清理无用或过时的建议来提升模型输出质量。该PR目前处于开启状态。
    - **链接**: [PR #39043](https://github.com/anthropics/claude-code/pull/39043)

## 📈 功能需求趋势

从今日的Issue中，可以提炼出社区最关注的几个功能方向：

1.  **插件与扩展性**：`#91870` 的 Function Hooks 提案是此方向的风向标。社区不满足于现有API，渴望能深度定制Claude Code行为，例如通过Hook介入工具调用前后、修改渲染输出等。
2.  **智能记忆管理**：`#91188` 表明用户对 `MEMORY.md` 的管理有更深的需求。除了配置压缩阈值，未来可能有对记忆文件更精细的控制、版本管理或分段加载的诉求。
3.  **订阅与定价模型**：`#83302` 和 `#87063` 显示，用户希望Fast Mode能更多地整合到现有订阅中，而非作为独立付费项。这反映出用户对性价比和简化计费流程的追求。
4.  **数据持久化与可靠性**：`#59248` 和 `#62476` 持续警示，会话记录的透明、可控、可恢复是用户最基本也最强烈的需求。任何静默数据清理行为都可能严重损害用户信任。
5.  **跨平台与桌面体验**：`#89467`（窗口置顶）、`#26951`（插件安装）、`#88323`（打包损坏）和 `#66540`（终端闪烁）等一系列bug表明，在macOS之外的平台上，Claude Code的桌面体验仍然存在不少粗糙的边缘。Windows和Linux的优化是当务之急。
6.  **多代理与协作**：`#83694`（连接器在子会话中缺失）、`#84894`（会话名不可用）表明，随着`Agent View`和后台子Agent功能的推广，会话间的数据传递、可视化和通信机制需要进一步完善。

## 🧑‍💻 开发者关注点

综合来看，开发者社区目前的核心痛点和高频需求集中在以下几点：

*   **数据主权与透明度**：用户对“静默”操作极度反感，尤其是数据删除。他们需要明确的配置项、清晰的警告和可逆的操作。
*   **行为可预期性与稳定性**：`#89467`的窗口置顶、`#66540`的终端闪烁、`#91371`的静默挂起，都破坏了开发者对工具行为的预期。稳定、可控是高效工作的基础。
*   **沟通与反馈有效性**：用户期望配置一个明确、安全、高效的`feedback`通道（`#84313`反馈403错误）。同时，对于模型“忽略指令”、“陷入循环”等行为（`#84759`、`#84842`），开发者期望更好的上下文遵循和更高效的交互模式。
*   **功能限制与灵活性**：对`MEMORY.md`阈值的控制、对会话记录保留期的控制、对Fast Mode额度分配的灵活性，都指向开发者希望工具能适应其个人工作流，而非被硬编码规则所限制。
*   **平台生态健壮性**：macOS插件安装失败、Windows打包自毁等问题，直接暴露了平台特定功能或基础设施的薄弱点。开发者对这些关键路径的可靠性要求很高。

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex 社区动态日报 – 2026-09-08

## 📋 今日速览

- **发布**：`rust-v0.154.0-alpha.6` 版本上线，仍为 Alpha 阶段。
- **社区热议**：iOS Remote 回归导致项目列表仅显示近期聊天（#36040，35 条评论）；Windows 浮动宠物点击穿透且无法拖拽（#41513，28 条评论）成为最受关注的两个 Bug。
- **PR 井喷**：过去 24 小时内合并了 20+ 个 PR，聚焦 TUI 体验（WebRTC 语音、计算机操作分组、tmux 尺寸恢复）和 Guardian 上下文重构，表明团队正加速桌面端和 CLI 功能迭代。

---

## 🚀 版本发布

### `rust-v0.154.0-alpha.6`
- **发布时间**：2026-09-08
- **内容**：仅标注为 Alpha 6 版本，未附带详细变更日志。
- **链接**：[Release 页面](https://github.com/openai/codex/releases/tag/rust-v0.154.0-alpha.6)

---

## 🔥 社区热点 Issues（Top 10）

### 1️⃣ #36040 – iOS Remote 仅列出近期聊天的项目
- **状态**：OPEN
- **评论数**：35 | 👍 0
- **摘要**：iOS 端使用 Remote Control 时，仅显示近期有聊天的项目，旧项目完全消失。影响大量远程配对用户。
- **链接**：[Issue #36040](https://github.com/openai/codex/issues/36040)

### 2️⃣ #41513 – Windows 浮动宠物点击穿透且无法拖拽
- **状态**：OPEN
- **评论数**：28 | 👍 13
- **摘要**：内置和自定义宠物均变为“点击穿透”状态，无法点击或拖拽。社区对此功能回归有较高期待。
- **链接**：[Issue #41513](https://github.com/openai/codex/issues/41513)

### 3️⃣ #35259 – Codex Desktop 重复进入模型消耗大量配额
- **状态**：OPEN
- **评论数**：21 | 👍 11
- **摘要**：在 Ultra/Multi-Agent 模式下，模型频繁因等待子代理或轮询状态而重新进入，浪费高达 19.8% 的 token 配额。
- **链接**：[Issue #35259](https://github.com/openai/codex/issues/35259)

### 4️⃣ #30385 – Windows 本地项目线程丢失（侧边栏/搜索）
- **状态**：OPEN
- **评论数**：14 | 👍 1
- **摘要**：本地项目线程在侧边栏和搜索中消失，但磁盘文件仍存在，可通过线程 ID 直接加载。疑似索引同步 Bug。
- **链接**：[Issue #30385](https://github.com/openai/codex/issues/30385)

### 5️⃣ #41377 – iOS Remote 隐藏早期助手/工具回合（长对话）
- **状态**：OPEN
- **评论数**：11 | 👍 3
- **摘要**：长对话中较早的助手和工具回复被 UI 隐藏，无法滚动回顾。会话完整性受影响。
- **链接**：[Issue #41377](https://github.com/openai/codex/issues/41377)

### 6️⃣ #42902 – macOS Computer Use 状态轮询唤醒休眠显示器
- **状态**：OPEN
- **评论数**：8 | 👍 0
- **摘要**：Computer Use 后台每 10 分钟轮询一次，导致显示器从睡眠状态被唤醒，影响节能体验。
- **链接**：[Issue #42902](https://github.com/openai/codex/issues/42902)

### 7️⃣ #42987 – GPT-6 Astra 两次短调用耗尽 Plus 5 小时配额
- **状态**：OPEN
- **评论数**：6 | 👍 4
- **摘要**：使用 GPT-6 Astra 在 CLI 中仅两次短调用即耗光全部配额，用户怀疑配额计算存在 Bug。
- **链接**：[Issue #42987](https://github.com/openai/codex/issues/42987)

### 8️⃣ #42514 – Intel Mac 缺少 Computer Use 服务
- **状态**：OPEN
- **评论数**：5 | 👍 3
- **摘要**：在 x86_64 架构的 Mac 上，Computer Use 和 Locked 功能完全不可用，仅支持 Apple Silicon。
- **链接**：[Issue #42514](https://github.com/openai/codex/issues/42514)

### 9️⃣ #40299 – 子代理管理不可靠（主代理过早关闭）
- **状态**：OPEN
- **评论数**：5 | 👍 0
- **摘要**：主代理在子代理任务未完成时即关闭对方，自行继续执行，用户明确指示等待也无效。
- **链接**：[Issue #40299](https://github.com/openai/codex/issues/40299)

### 🔟 #34349 – 请求完全禁用宠物功能并移除菜单项
- **状态**：OPEN
- **评论数**：4 | 👍 28
- **摘要**：社区呼声最高的功能增强请求，希望提供关闭宠物、隐藏侧边栏菜单的选项，点赞数最高。
- **链接**：[Issue #34349](https://github.com/openai/codex/issues/34349)

---

## ✅ 重要 PR 进展（Top 10）

### 1️⃣ #43624 – 添加 macOS Secure Enclave 用户验证
- **合并**：已关闭
- **内容**：为 macOS 实现生物识别凭证的创建、重用和签名，使本地验证 API 不再返回“不支持的提供商”。
- **链接**：[PR #43624](https://github.com/openai/codex/pull/43624)

### 2️⃣ #43622 – CLI 连接时警告服务端版本过旧
- **合并**：已关闭
- **内容**：启动时检测 app-server 版本是否低于 CLI，并在对话历史中显示通知，改善版本兼容性。
- **链接**：[PR #43622](https://github.com/openai/codex/pull/43622)

### 3️⃣ #43621 – 为线程遥测添加 worktree 分类
- **合并**：已关闭
- **内容**：在 `codex.thread.started` 指标中记录是否为 Git worktree，帮助分析仓库使用模式。
- **链接**：[PR #43621](https://github.com/openai/codex/pull/43621)

### 4️⃣ #43619 – 添加稳定版 TUI/app-server 版本比较辅助函数
- **合并**：已关闭
- **内容**：提供 `is_official_server_older` 函数，供后续版本提醒使用。
- **链接**：[PR #43619](https://github.com/openai/codex/pull/43619)

### 5️⃣ #43603 – 恢复 tmux 中丢失的终端尺寸变化通知
- **合并**：已关闭
- **内容**：通过后台每 500ms 轮询 tmux 终端尺寸，修复 TUI 在 tmux 下尺寸不更新的问题。
- **链接**：[PR #43603](https://github.com/openai/codex/pull/43603)

### 6️⃣ #43581 – 为 TUI 添加 WebRTC 语音实时对话功能
- **合并**：已关闭
- **内容**：增加 `/voice`、`/voice mute`、`/voice stop` 命令，支持实时转录、麦克风/扬声器电平显示，可保留字幕。
- **链接**：[PR #43581](https://github.com/openai/codex/pull/43581)

### 7️⃣ #43576 – 在 TUI 中分组相邻计算机操作
- **合并**：已关闭
- **内容**：将连续的 `cua_repl` 调用显示为紧凑的“正在使用计算机”或“已使用计算机”组，显示操作次数和失败数。
- **链接**：[PR #43576](https://github.com/openai/codex/pull/43576)

### 8️⃣ #43572 – 让托管 app-server 的关闭等待时间可配置
- **合并**：已关闭
- **内容**：新增 `shutdownGraceSeconds` 配置项，用户可调整关闭前强制退出进程的等待秒数。
- **链接**：[PR #43572](https://github.com/openai/codex/pull/43572)

### 9️⃣ #43570 – 通过线程管理器管理同步 Guardian 评审器
- **合并**：已关闭
- **内容**：将 Guardian 评审器的创建和分支迁移至 `ThreadManager`，不再依赖异步评分器启动。
- **链接**：[PR #43570](https://github.com/openai/codex/pull/43570)

### 🔟 #43562 – 添加显式的 app-server 守护进程更新命令
- **合并**：已关闭
- **内容**：新增 `codex app-server daemon update` 命令，即使自动更新关闭也可手动检查并安装最新稳定版。
- **链接**：[PR #43562](https://github.com/openai/codex/pull/43562)

---

## 📈 功能需求趋势

从 Issue 中提取的社区最关注的功能方向：

1. **宠物系统改进**：要求完全禁用宠物（#34349，👍 28）、修复 Windows 点击穿透（#41513）、Linux 宠物抖动（#42857）。
2. **跨平台与兼容性**：Linux 原生窗口装饰（#38595）、Intel Mac 的 Computer Use 支持（#42514）、WSL 项目集成（#43628）。
3. **速率限制与配额管理**：优化子代理等待策略（#35259、#41875）、修复 Astra 配额消耗异常（#42987）、重置时间变更（#22133）。
4. **远程控制增强**：改进 iOS Remote 项目列表和会话完整性（#36040、#41377、#42315、#43536）。
5. **CLI 与 TUI 体验**：添加 `thread/unload` RPC（#21889）、`BeforeModelRequest` 钩子（#22036）、编译时类型安全改进。
6. **安全与验证**：macOS Secure Enclave 集成（已通过 PR 实现）、Guardian 评审机制重构（多个 PR）。

---

## ⚠️ 开发者关注点（高频痛点）

- **iOS Remote 功能退化**：项目列表不完整、长对话历史丢失、自定义 section 同步错误，严重影响移动端办公体验。
- **Windows 桌面体验问题**：宠物穿透、Composer 消失（#42963）、Browser Use 标签关闭导致崩溃（#43347）、WSL 项目创建失败（#43628）。
- **配额消耗异常**：模型在等待/轮询时重复进入（#35259）、Astra 短调用耗尽全部配额（#42987），Pro 用户反馈强烈。
- **子代理管理不可靠**：主代理过早关闭子代理（#40299），导致多代理协作失败。
- **会话持久性 Bug**：本地项目线程丢失（#30385）、删除的云聊天仍出现在统一目录中（#42628）、计算机操作后评论丢失（#42017）。
- **跨平台兼容性**：Intel Mac 缺失 Computer Use（#42514）、Linux 缺少原生窗口装饰（#38595）、x86_64 架构支持不完整。

---

*数据来源：GitHub openai/codex 仓库，统计时间截至 2026-09-08 18:00 UTC。*

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

# Gemini CLI 社区动态日报 | 2026-09-08

## 今日速览

昨晚发布的 `v0.60.0-nightly.20260907` 每日构建版本未引入重大功能变化。社区讨论集中在几项影响体验的 bug：模型版本静默回退到旧版（#28859）、扩展更新回滚彻底失效（#29033）以及 shell 命令执行后误判“等待输入”导致卡死（#25166）。安全方面，多个 PR 正在强化容器沙箱的文件系统隔离与语法边界。

---

## 版本发布

**v0.60.0-nightly.20260907.g85aca163f**  
🔗 [查看全部变更](https://github.com/google-gemini/gemini-cli/compare/v0.60.0-nightly.20260906.g85aca163f...v0.60.0-nightly.20260907.g85aca163f)  
仅版本号更新，无用户可见功能变化，属于常规每日构建。

---

## 社区热点 Issues（Top 10）

| # | Issue | 热度 | 摘要 | 为什么值得关注 |
|---|-------|------|------|----------------|
| 1 | [#28859](https://github.com/google-gemini/gemini-cli/issues/28859) | 👍14 · 8评论 | 请求任何 `gemini-<X.Y>-flash` 模型（包括不存在的版本）都被静默回退到 `gemini-3.5-flash`，无错误无警告 | 用户完全失去模型版本控制权，严重影响测试和生产可靠性 |
| 2 | [#25306](https://github.com/google-gemini/gemini-cli/issues/25306) | 👍12 · 33评论 | `"The caller does not have permission"` 403 错误 | 评论数最高，长期未完全解决；API 权限问题对首次使用用户极不友好 |
| 3 | [#22323](https://github.com/google-gemini/gemini-cli/issues/22323) | 👍2 · 13评论 | 子代理达到最大 turn 限制后错误报告为 `GOAL` 成功，掩盖真实中断原因 | 误导性状态直接影响 Agent 自动化工作流的正确性和可调试性 |
| 4 | [#21409](https://github.com/google-gemini/gemini-cli/issues/21409) | 👍8 · 8评论 | 通用代理 (generalist agent) 在简单任务（如创建文件夹）后永久挂起 | 核心 Agent 几乎不可用，社区反映强烈 |
| 5 | [#25166](https://github.com/google-gemini/gemini-cli/issues/25166) | 👍3 · 4评论 | Shell 命令执行完成后仍显示“等待输入”，实际已结束，导致后续操作阻塞 | 高频出现，严重破坏交互体验 |
| 6 | [#29033](https://github.com/google-gemini/gemini-cli/issues/29033) | 5评论 | 扩展更新失败时回滚拷贝的是**空目录**，恢复后什么都没了 | 扩展机制完整性受损，可能导致功能永久丢失 |
| 7 | [#19873](https://github.com/google-gemini/gemini-cli/issues/19873) | 👍1 · 9评论 | 提议利用 Gemini 3 模型的“bash 亲和性”构建零依赖 OS 沙箱，实现后执行意图路由 | 长远架构提升，影响 Agent 安全性、执行效率和多平台兼容性 |
| 8 | [#21983](https://github.com/google-gemini/gemini-cli/issues/21983) | 👍1 · 4评论 | 浏览器子代理在 Wayland 下直接失败（`Termination Reason: GOAL`，实际未执行） | 影响 Linux Wayland 用户，兼容性缺口明显 |
| 9 | [#22232](https://github.com/google-gemini/gemini-cli/issues/22232) | 4评论 | 浏览器代理对锁定的 profile 采用“快速失败”策略，无法自动接管或恢复 | 持续会话场景下（如持久化浏览器会话）体验断裂 |
| 10 | [#26525](https://github.com/google-gemini/gemini-cli/issues/26525) | 5评论 | Auto Memory 在读取本地对话记录后，仅依赖模型自身进行脱敏（事后），且日志可能记录已有技能 | 隐私与安全：敏感信息在发送到模型前未被确定性脱敏 |

---

## 重要 PR 进展（Top 10）

| # | PR | 状态 | 功能/修复内容 |
|---|-----|------|---------------|
| 1 | [#29166](https://github.com/google-gemini/gemini-cli/pull/29166) | OPEN | **fix(extensions): 扩展更新前备份原目录** —— 直接修复 #29033，使回滚真正恢复文件 |
| 2 | [#29214](https://github.com/google-gemini/gemini-cli/pull/29214) | OPEN | **fix(sandbox): 强化文件系统边界并隔离运行时状态** —— 将沙箱配置目录与宿主机分开，只挂载只读配置文件，防止敏感信息泄漏 |
| 3 | [#29216](https://github.com/google-gemini/gemini-cli/pull/29216) | OPEN | **fix(cli): 在容器沙箱内隔离 settings 目录** —— 解决 Docker/Podman 运行时宿主机 `~/.gemini` 直接挂载导致 OAuth token 等凭证暴露 |
| 4 | [#29239](https://github.com/google-gemini/gemini-cli/pull/29239) | OPEN | **fix(cli): 防止 Ghost 文本在窄终端宽度下进入无限循环** —— 修复 #19985，优化输入提示词的换行算法 |
| 5 | [#29237](https://github.com/google-gemini/gemini-cli/pull/29237) | OPEN | **Fix: list_background_processes 不输出 `(Exit Code: null)`** —— 信号杀死的进程不显示 null，改为更清晰的提示 |
| 6 | [#28971](https://github.com/google-gemini/gemini-cli/pull/28971) | CLOSED | **fix(core): 保持截断后的 MCP 工具名称唯一性** —— 避免两个工具因字符限制被截断成相同名称导致注册冲突 |
| 7 | [#28983](https://github.com/google-gemini/gemini-cli/pull/28983) | CLOSED | **fix(core): 检测混合行尾（CRLF+LF）而不是仅凭一个 CRLF 就判定整个文件** —— 避免错误将 Unix 风格文件标记为 CRLF |
| 8 | [#28975](https://github.com/google-gemini/gemini-cli/pull/28975) | CLOSED | **fix(core): 当工作区根目录是符号链接时保持 glob 结果** —— 修复 macOS `/tmp` 默认符号链接导致的文件搜索失效 |
| 9 | [#29134](https://github.com/google-gemini/gemini-cli/pull/29134) | OPEN | **fix(cli): 保护当前会话不被删除** —— 传递活跃 session ID 给 `--delete-session` 路径，防止误删正在使用的会话 |
| 10 | [#29132](https://github.com/google-gemini/gemini-cli/pull/29132) | OPEN | **fix(core): 在 diff 上下文代码片段中规范化换行符** —— 解决 Windows 上 CRLF 导致完整文件 diff 的 token 浪费问题 |

---

## 功能需求趋势

从近 24 小时更新的 Issues 可以看出社区重点关注以下方向：

- **Agent 行为可靠性**：子代理最大 turn 伪造成功、通用代理挂起、浏览器代理在 Wayland 崩溃等问题占比最高，用户对 Agent 的「诚实汇报」和「可恢复性」需求强烈。
- **模型路由诚实性**：模型版本静默回退（#28859）暴露了核心模型选择机制的缺陷，社区期待透明的版本映射和明确的错误提示。
- **沙箱与安全隔离**：多个 PR 聚焦于容器沙箱的文件系统隔离、bash 亲和性原生执行（#19873）、以及 Auto Memory 的确定性脱敏，表明开发者对「让模型充分发挥能力而不牺牲安全」的要求越来越高。
- **扩展生态可靠性**：扩展更新回滚失败（#29033）提示扩展机制急需完善的备份恢复策略，否则用户将不敢轻易更新。
- **窗口与终端兼容性**：Ghost 文本无限循环、符号链接 workspace 识别、行尾检测等细节问题说明社区对跨平台体验的一致性有较高期待。

---

## 开发者关注点

1. **模型版本静默回退**：请求不存在的模型竟然不报错，而是直接用旧版回复，这是最危险的“静默失败”。开发者亟需明确错误机制或至少提供警告。
2. **Shell 执行后卡死**：命令执行完仍显示“等待输入”是常见干扰，严重影响自动化工作流和日常体验。
3. **扩展更新无备份**：用户反馈升级扩展后万一失败，整个扩展消失，这是不可接受的破坏性行为。PR #29166 正在修复。
4. **代理挂起无日志**：通用代理和子代理挂起后缺少详细状态，社区希望添加 `verbose` 模式或 `bug report` 能包含子代理完整轨迹（#21763）。
5. **配置管理不统一**：`settings.json` 中 `maxTurns` 等配置被浏览器代理忽略（#22267），用户需要一致的配置投射。
6. **高密度工具环境下的 400 错误**：当工具超过 128 个时（#24246），API 返回 400，Agent 未做工具裁剪或分组，影响大型项目使用。

---

*以上动态基于 github.com/google-gemini/gemini-cli 2026-09-07 数据整理，发布日期为 2026-09-08。*

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI 社区动态日报 | 2026-09-08

---

## 今日速览

过去24小时内，社区围绕 **v1.0.83** 及 **Desktop 1.1.15** 提交了大量回归类 Issue，涉及会话管理、MCP 连接超时、键盘兼容性等核心功能。两个值得关注的趋势：**MCP OAuth 认证流程缺陷** 和 **Windows 平台会话归档需求** 成为高频痛点。此外，一项长期 feature request（项目/仓库级插件支持）刚刚关闭，但社区共识强烈。

---

## 版本发布

无新版本发布。

---

## 社区热点 Issues（选 10 条）

### 1. [CLOSED] 支持项目级/仓库级插件（#1665）
- **摘要**：用户希望插件能按项目或仓库作用域安装，而非全局载入。经过半年讨论，该 Issue 于 9 月 7 日关闭，但未合并具体实现，社区仍在期待后续 roadmap。
- **社区反应**：18 👍，14 条评论，长期高关注。
- 链接：https://github.com/github/copilot-cli/issues/1665

### 2. [CLOSED] 德语键盘无法输入 @ 符号（#1999）
- **摘要**：德语键盘（AltGr+Q）输入 @ 无效，影响核心命令使用。该问题已在某版本修复，但用户仍需确认当前版本是否彻底解决。
- **社区反应**：2 👍，10 条评论，反馈已验证。
- 链接：https://github.com/github/copilot-cli/issues/1999

### 3. [OPEN] Desktop 1.1.15 无法创建第二个本地会话（#4742）
- **摘要**：自动更新到 1.1.15 后，同一项目内已有一个本地会话运行时，创建新会话失败，提示“invalid argument: This project already has an active Local workspace”。影响多分支并行开发。
- **社区反应**：7 条评论，多人复现，暂未分配。
- 链接：https://github.com/github/copilot-cli/issues/4742

### 4. [OPEN] `disable-model-invocation: true` 导致技能完全不可达（#4438）
- **摘要**：项目技能设置 `disable-model-invocation: true` 后，即使显式调用 copilot 也无法使用该技能，与预期“仅让模型不自动调用，手动仍可调用”不符。
- **社区反应**：6 👍，4 条评论，影响自定义 agent 配置。
- 链接：https://github.com/github/copilot-cli/issues/4438

### 5. [OPEN] MCP OAuth：非第一方 HTTP 服务器认证失败（#4017）
- **摘要**：Desktop 版连接外部 MCP 服务器（如 Atlassian）时，OAuth 流程无弹窗、无错误，仅静默失败。主因是 host-token 被取消后未启动浏览器流。
- **社区反应**：3 👍，3 条评论，标签 `triaged`，等待修复。
- 链接：https://github.com/github/copilot-cli/issues/4017

### 6. [OPEN] `--yolo` 被错误地整会话禁用（#4757）
- **摘要**：即使用户账户无任何 managed policy，CLI 依然应用 fail-closed 姿势，导致 `--yolo`/`--allow-all` 在整个会话期间不可用。
- **社区反应**：3 条评论，新提交，影响自动化/快速操作场景。
- 链接：https://github.com/github/copilot-cli/issues/4757

### 7. [OPEN] Windows 需要先归档每个空闲会话才能创建新会话（#4756）
- **摘要**：Windows 版 Desktop 1.1.15 中，若项目有闲置会话，新建会话会失败，必须先手动归档。9 👍 表明社区高度关注该平台特定问题。
- **社区反应**：9 👍，2 条评论，高赞同。
- 链接：https://github.com/github/copilot-cli/issues/4756

### 8. [OPEN] v1.0.83 会话恢复时 MCP 连接超时缩短（#4753）
- **摘要**：恢复会话时，MCP 服务器初始化连接超时从 v1.0.82 的 ~16s 降至 ~1s，导致许多服务器静默不可用，且无法重连。
- **社区反应**：1 👍，2 条评论，属于性能回归。
- 链接：https://github.com/github/copilot-cli/issues/4753

### 9. [OPEN] 扩展启动失败后，工具调用永久挂起（#4670）
- **摘要**：恢复大会话时，某扩展 `joinSession()` 失败并退出，但 CLI 仍提供该扩展的 custom tool，调用后 handler 不运行，调用挂起。
- **社区反应**：1 条评论，影响扩展开发者。
- 链接：https://github.com/github/copilot-cli/issues/4670

### 10. [OPEN] 会话永久卡死在轮次结束（#4755）
- **摘要**：会话在 turn 结束时可能进入永久卡死状态：不空闲、不运行、不接受输入，队列消息静默丢失。仅能杀进程恢复。
- **社区反应**：1 条评论，严重性高。
- 链接：https://github.com/github/copilot-cli/issues/4755

---

## 重要 PR 进展（共 2 条）

### 1. [OPEN] 添加实验性 next-action 扩展原型（#4746）
- **作者**：anujb-msft  
- **摘要**：新增 `examples/next-best-action/` 目录，提供 opt-in 的 SDK 扩展示例，演示模型推断的下一步动作。通过 `joinSession()` 复用前台会话，不修改已安装 CLI。
- **意义**：为社区提供扩展开发参考，但暂不纳入自动发现。
- 链接：https://github.com/github/copilot-cli/pull/4746

### 2. [OPEN] 添加 joke cli（#4748）
- **作者**：tnk7899xd-create  
- **摘要**：一个简单的玩笑性质的 PR，添加了 `joke` 命令。无实质功能变更。
- **意义**：社区玩梗，不具实际影响。
- 链接：https://github.com/github/copilot-cli/pull/4748

---

## 功能需求趋势

从过去24小时的所有 Issue 中，社区最关注的功能方向如下：

1. **MCP 协议完善**：OAuth 认证修复、取消请求支持（#4759）、User-Agent 传递（#4681）、连接超时配置优化。  
2. **会话管理增强**：多仓库项目的工作区关联（#4709）、会话按仓库筛选/过滤（#4693）、会话归档 UX 改进（#4756）。  
3. **插件/扩展作用域**：项目级插件加载（#1665 虽关闭但呼声高）、自定义 agent 的 `--agent` 参数识别（#4752）。  
4. **键盘布局兼容性**：非英语键盘（如德语）的特殊字符输入支持（#1999 已修复，但仍有其他键盘问题）。  
5. **模型兼容性**：`/refine` 命令因模型不支持 reasoning_effort 而失败（#4747），提示需要更灵活的模型选择。  

---

## 开发者关注点

**高频痛点总结：**

- **Windows 平台会话管理**：在 Desktop 1.1.15 上，新会话创建前必须归档旧会话，严重打断工作流（#4756）。  
- **MCP 连接可靠性与回归**：v1.0.83 缩短 MCP 初始化超时导致服务器静默不可用（#4753）；Azure MCP 的 `learn=true` 调用超时（#4749）。  
- **数据丢失风险**：`ask_user` 表单中按 Enter 会永久丢弃已输入内容（#4738）；删除已驱逐的会话后会话重新出现（#4754）。  
- **CPU 与性能**：TUI 空闲时仍占用 6-7% CPU，运行后飙升至多核（#4750）；后台子代理事件延迟 14 分钟（#4760）。  
- **扩展稳定**：扩展失败后工具调用挂起（#4670）；`disable-model-invocation` 配置语义不符合预期（#4438）。  

建议开发者关注 v1.0.83 的回归问题，并留意 Desktop 1.1.15 的 Windows 特定 bug。

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

# Kimi Code CLI 社区动态日报 | 2026-09-08

## 今日速览
过去24小时内项目无新版本发布，但社区反馈活跃：一个关于输入法字符重复的 Bug 被重新关注，同时新出现了一个 Agent 卡死在反复 Read 工具的严重问题。功能需求方面，“Plan 模式”和“MCP 配置迁移”的呼声持续存在，但官方尚未回应。

## 版本发布
今日无新版本发布。

## 社区热点 Issues
（基于过去24小时内更新的4条Issues，按关注度排列）

1. **#2584 ‑ Bug: Thai (and other IME‑based) characters duplicated when typing in the prompt on Windows**  
   创建: 2026-08-04 | 更新: 2026-09-07 | 👍 1  
   **重要性**：影响 Windows 用户输入非英文字符（泰文、中文、日文等 IME 输入法）体验，字符重复会导致命令无法正常执行。社区仅有1条评论，关注度不高，但问题本身对国际化用户关键。  
   [链接](https://github.com/MoonshotAI/kimi-cli/issues/2584)

2. **#2637 ‑ [Bug] Agent stuck in repeated Read‑tool loop, unable to emit intended Edit calls**  
   创建: 2026-09-07 | 更新: 2026-09-07 | 👍 0  
   **重要性**：刚出现的新 Bug，Agent 卡死在反复执行 Read 工具的死循环，无法执行实际编辑操作。严重影响开发流程，虽然暂无评论，但需要紧急处理。  
   [链接](https://github.com/MoonshotAI/kimi-cli/issues/2637)

3. **#1354 ‑ [enhancement] 我想要一个 plan mode**  
   创建: 2026-03-06 | 更新: 2026-09-07 | 👍 7  
   **重要性**：社区呼声最高的功能之一，已有7个 👍。用户希望添加类似 Claude Code 的 Plan 模式，避免 Agent 在讨论规划期就自动执行代码。从创建至今超过半年未实现，社区期待度高。  
   [链接](https://github.com/MoonshotAI/kimi-cli/issues/1354)

4. **#1356 ‑ [enhancement] Feature Request: Seamless Migration of MCP Skill Configurations from Other Mainstream Agent CLIs**  
   创建: 2026-03-06 | 更新: 2026-09-07 | 👍 0  
   **重要性**：MCP 配置迁移功能，方便从 Claude CLI、Cursor、Windsurf 等工具平滑迁移技能配置。虽然无👍，但符合当前 Agent CLI 生态互操作性趋势。  
   [链接](https://github.com/MoonshotAI/kimi-cli/issues/1356)

## 重要 PR 进展
（基于过去24小时内更新的2条PR）

1. **#2616 ‑ Add Build Remote Agent phone pairing (gbr/1)**  
   创建: 2026-08-23 | 更新: 2026-09-07 | 评论: 无  
   **功能**：增加手机端 Build Remote Agent 作为桌面 Agent 的配对设备，iOS/Android 应用可观察并注入本地会话，协议为 `gbr/1`。手机角色为观察者+否决权，非全协调。该 PR 扩展了远程协作场景。  
   [链接](https://github.com/MoonshotAI/kimi-cli/pull/2616)

2. **#2636 ‑ Optimize get_share_dir with caching and path handling**  
   创建: 2026-09-07 | 更新: 2026-09-07 | 评论: 无  
   **功能**：对 `get_share_dir` 函数进行缓存和路径处理优化，提升目录获取性能。提交者描述为“All of the requirements meet. Was bored so did this.”，属于随手贡献的优化 PR。  
   [链接](https://github.com/MoonshotAI/kimi-cli/pull/2636)

## 功能需求趋势
从近24小时的 Issues 中可以提炼出以下社区关注方向：
- **Plan 模式**：用户希望能显式控制 Agent 的规划阶段，防止过早自动执行。
- **MCP 配置迁移**：要求与其他主流 Agent CLI 工具（Claude CLI、Cursor、Windsurf）的 MCP 技能配置互通。
- **输入法兼容性**：Windows 平台 IME 输入法（尤其是非英文语言）的支持问题。
- **Agent 循环死锁修复**：反复 Read 工具的 Bug 暴露了工具调用循环的稳定性缺陷。

## 开发者关注点
- **Windows 语言输入体验**：泰文等 IME 字符重复问题影响日常开发，涉及终端原生输入处理。
- **Agent 执行控制**：用户希望在 Agent 自动执行前有明确的“确认”或“规划”步骤，避免无意愿的代码修改。
- **生态互通**：从其他工具迁移 MCP 配置的高频需求，开发者不愿为单一工具重新配置所有技能。
- **性能优化**：虽然 PR #2636 较小，但体现了社区对目录缓存等底层性能的主动关注。

> *数据来源：GitHub MoonshotAI/kimi-cli，统计时间截至 2026-09-08 08:00 UTC。因社区规模有限，本次日报仅含当日有更新的 4 个 Issue 与 2 个 PR。*

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报 | 2026-09-08

---

## 📌 今日速览

昨日社区活跃度维持高位，共产生 50 条新/更新 Issue 及 50 条 PR。**官方 VS Code 扩展** 的呼声持续最高（148 👍），同时多个稳定性 Bug（会话永久卡死、SSE 流中断）引发广泛讨论。PR 方面，**Moonshot 厂商接入** 与 **快照回滚修复** 是今日的重要技术推进，此外多项自动化清理 PR 合并后提升了工具链健壮性。

---

## 🔥 社区热点 Issues（Top 10）

### 1. [#11176] 官方 VS Code 扩展请求
- **作者**: c2b247 · **评论**: 29 · **👍**: 148
- **摘要**: 强烈希望 OpenCode 提供官方 VS Code 扩展，作为原生 IDE 集成入口。社区支持极高，是当前最受期待的功能。
- **链接**: [Issue #11176](https://github.com/anomalyco/opencode/issues/11176)

### 2. [#43199] Mistral GLM-5.2 工具调用报错
- **作者**: KPhi · **评论**: 9 · **👍**: 8
- **摘要**: Mistral 新增第三方 GLM-5.2 模型，文本响应正常，但工具调用时返回错误。影响计划接入该模型的用户。
- **链接**: [Issue #43199](https://github.com/anomalyco/opencode/issues/43199)

### 3. [#43277] 会话永久卡死，重启无法恢复
- **作者**: dcon4 · **评论**: 8 · **👍**: 1
- **摘要**: 多个会话在正常使用中突然“卡死”，拒绝新消息，且重启服务/系统均无法恢复。严重影响日常使用。
- **链接**: [Issue #43277](https://github.com/anomalyco/opencode/issues/43277)

### 4. [#47842] OpenCode 在 Cursor 中无法工作
- **作者**: SUNGJINWOOLUCKY · **评论**: 7 · **👍**: 0
- **摘要**: 在 Cursor IDE 中使用 OpenCode 时提示“model channel not available”，怀疑为 Cursor 的 OAuth 鉴权兼容性问题。
- **链接**: [Issue #47842](https://github.com/anomalyco/opencode/issues/47842)

### 5. [#17044] 桌面版更新时安装路径错误
- **作者**: Classic298 · **评论**: 7 · **👍**: 0
- **摘要**: 每次更新 OpenCode 桌面版时，新版本总是安装到 `%APPDATA%` 而非原始安装目录，导致多版本混乱。
- **链接**: [Issue #17044](https://github.com/anomalyco/opencode/issues/17044)

### 6. [#27303] 官方 Go/Zen BYOK 语言模型提供扩展
- **作者**: Gr33nLight · **评论**: 6 · **👍**: 5
- **摘要**: 建议 OpenCode 开发针对 VS Code Copilot 的 BYOK（自带密钥）语言模型提供扩展，使 Copilot 可使用 OpenCode 已配置的模型。
- **链接**: [Issue #27303](https://github.com/anomalyco/opencode/issues/27303)

### 7. [#31724] 本地 opencode serve 暴露 OpenAI 兼容端点
- **作者**: wagner-sousa · **评论**: 6 · **👍**: 2
- **摘要**: 希望本地 `opencode serve` 能提供 OpenAI 兼容的 API 端点，便于其他工具复用已配置的模型和代理。
- **链接**: [Issue #31724](https://github.com/anomalyco/opencode/issues/31724)

### 8. [#45011] Web 首页不显示 CLI/TUI 创建的会话
- **作者**: tak2-08 · **评论**: 6 · **👍**: 1
- **摘要**: 从终端创建会话后，Web UI Home 页面显示空列表，需要手动添加项目才能同步。该 Bug 导致跨界面协作困难。
- **链接**: [Issue #45011](https://github.com/anomalyco/opencode/issues/45011)

### 9. [#42938] Go 套餐用量耗尽后 Zen 余额未启用
- **作者**: CinematicEnciclopedia · **评论**: 6 · **👍**: 0
- **摘要**: 订阅的 Go 套餐达到月度上限后，即使启用了“Use balance”且 Zen 余额充足，仍被阻塞 12 小时。
- **链接**: [Issue #42938](https://github.com/anomalyco/opencode/issues/42938)

### 10. [#36241] macOS 上 gpt-5.6-sol-fast 流式推理报错
- **作者**: li-keli · **评论**: 6 · **👍**: 2
- **摘要**: 使用 OpenAI 的 `gpt-5.6-sol-fast` 高推理变体时，流式回复频繁中断，报错“reasoning part rs_*:0 not found”。
- **链接**: [Issue #36241](https://github.com/anomalyco/opencode/issues/36241)

---

## 🛠️ 重要 PR 进展（Top 10）

### 1. [#47851] feat(ai): 新增 Moonshot 厂商支持
- **作者**: rekram1-node
- **概述**: 新增 Moonshot（月之暗面）顶级接入层，支持 Chat Completions、显式 `.chat`/`.messages`/`.responses` 选择器，代码轻量（145 行）。
- **链接**: [PR #47851](https://github.com/anomalyco/opencode/pull/47851)

### 2. [#45029] feat(tui): 浏览项目、目录与 Git Worktrees
- **作者**: kitlangton
- **概述**: 扩展“打开对话框”，支持显示 Git worktrees、嵌套项目目录及与非 Git 位置关联的会话，提升 TUI 导航效率。
- **链接**: [PR #45029](https://github.com/anomalyco/opencode/pull/45029)

### 3. [#47848] fix(session): 清除归档时间戳时不再静默忽略
- **作者**: alohaninja
- **概述**: 修复会话取消归档时的时间戳冲突，同时处理了后端半段逻辑（Web UI 部分在 #43919），防止数据不一致。
- **链接**: [PR #47848](https://github.com/anomalyco/opencode/pull/47848)

### 4. [#47861] fix(snapshot): 限定回滚补丁范围并保护删除操作
- **作者**: CannonRS
- **概述**: 修复快照存储中补丁文件列表与工作树之间的一致性，防止回滚时错误删除其他文件（Closes #40736, #33940, #46783）。
- **链接**: [PR #47861](https://github.com/anomalyco/opencode/pull/47861)

### 5. [#41016] fix(provider): 转发自定义模型的 agent 温度
- **作者**: SeashoreShi
- **概述**: 自定义模型（`opencode.json` 中配置的 `provider.<id>.models`）默认禁用温度能力，导致 agent 层温度设置被静默忽略。本 PR 修复此问题。
- **链接**: [PR #41016](https://github.com/anomalyco/opencode/pull/41016)

### 6. [#47859] fix(session-ui): 对齐重试图标与标签
- **作者**: opencode-agent[bot]
- **概述**: 小型 UI 修复：移除重试旋转图标的多余偏移，并添加组件布局回归测试。
- **链接**: [PR #47859](https://github.com/anomalyco/opencode/pull/47859)

### 7. [#47835] fix(app): 悬停时保持标签页进度可见
- **作者**: opencode-agent[bot]
- **概述**: 删除 `revealProjectOnHover` 选项，始终在会话忙碌时显示进度指示器，提升用户反馈一致性。
- **链接**: [PR #47835](https://github.com/anomalyco/opencode/pull/47835)

### 8. [#41135] feat(app): 添加消息时间线导航条
- **作者**: GoldenStain
- **概述**: 长会话消息导航困难，本 PR 实现紧凑的时间线珠子条（类似 DeepSeek Web），便于快速跳转。
- **链接**: [PR #41135](https://github.com/anomalyco/opencode/pull/41135)

### 9. [#47858] feat(updates): 在 opencode.ai/update 提供更新服务
- **作者**: thdxr
- **概述**: 将更新 Worker 部署到 `opencode.ai/update`，并保留 AUR 本地产物发布路径，提升更新分发可靠性。
- **链接**: [PR #47858](https://github.com/anomalyco/opencode/pull/47858)

### 10. [#41115] docs: 新增 opencode-fusion 至生态页
- **作者**: mihneaptu
- **概述**: 在生态系统页面 Agents 部分收录 [opencode-fusion](https://github.com/mihneaptu/opencode-fusion) 社区项目。
- **链接**: [PR #41115](https://github.com/anomalyco/opencode/pull/41115)

---

## 📊 功能需求趋势

从本周 Issue 与 PR 观察，社区最关注以下功能方向：

- **IDE 深度集成**：官方 VS Code 扩展（#11176）与 Copilot BYOK 扩展（#27303）持续高赞；Cursor 兼容性问题（#47842）也反映了多 IDE 生态需求。
- **OpenAI 兼容性**：要求本地 serve 暴露 OpenAI 风格端点（#31724），使第三方工具可直接复用 OpenCode 配置。
- **新模型/厂商接入**：Moonshot（#47851）、GLM-5.2 工具调用修复（#43199）显示社区对国内及新兴厂商的支持需求。
- **Web UI 与 CLI 一致性**：CLI 创建的会话在 Web 端不可见（#45011, #46444），表明跨界面同步是重要改进方向。
- **会话稳定性**：永久卡死（#43277）、SSE 流中断（#37580）、子代理权限丢弃（#44747）等稳定性 Bug 是最紧迫的需求驱动力。
- **插件与扩展性**：插件数据流面板（#46156）、Auto Router 错误信息增强（#47794）体现社区对可观测性和自诊断能力的诉求。

---

## 🔧 开发者关注点

- **会话恢复困难**：多起 Bug 报告会话卡死后无法恢复，即使重启服务或系统。开发者建议提升会话状态的持久化与恢复机制，增加日志导出能力。
- **更新体验差**：桌面版更新安装路径固定到 `%APPDATA%`（#17044），且更新过程中会中断正在执行的 Prompt（#47850），用户希望更新行为非阻塞。
- **权限通知冗余**：Auto 模式下权限通知持续弹出（#47545），因服务器端权限审批在客户端后才触发，建议将 Auto 审批逻辑移至服务端。
- **TUI 输入延迟**：macOS 上 TUI 出现按键丢弃或延迟（#37336），而 `--mini` 模式正常，怀疑与 xterm-webgl 或终端渲染有关。
- **子任务权限黑洞**：子 agent 触发的权限请求可能静默丢失（#44747），导致父任务永久挂起且无法中断，开发者呼吁增加超时自动跳过机制（#47824）。
- **配置与模型设置**：用户期望在 TUI 中可直接为 agent 设置默认模型（#47836），避免手动编辑 `opencode.json`。

---

*日报数据来自 [anomalyco/opencode](https://github.com/anomalyco/opencode) 公开仓库，统计截至 2026-09-08 06:00 UTC。*

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi 社区动态日报 | 2026-09-08

---

## 今日速览

项目仓库 `earendil-works/pi` 近期活跃度极高，社区聚焦于 **连接可靠性**、**Windows 兼容性** 以及 **新一代模型（GPT-6 Astra、Gemini 3.x、Fable 5）的适配问题**。昨日（9月7日）涌现大量 PR 与 Issue，其中 **OpenRouter 免费模型 max_tokens 溢出**、**Esc 流式取消不彻底** 以及 **AgentSession 生命周期 bug** 成为社区讨论热点。核心贡献者正在推进 **系统消息增量传递**、**Ollama Cloud 支持** 等关键功能。

---

## 版本发布

（过去24小时无新版本发布）

---

## 社区热点 Issues

### 1. [#4945] openai-codex 连接可靠性问题
- **链接**：https://github.com/earendil-works/pi/issues/4945  
- **评论/点赞**：77 / 33  
- **为什么重要**：`openai-codex` / `gpt-5.5` 交互式 TUI 频繁卡在 `Working...` 状态，只能靠 Esc 强制中断，严重影响日常使用。社区呼声最高，持续近 4 个月仍未彻底解决。

### 2. [#7547] Windows 使用体验收集
- **链接**：https://github.com/earendil-works/pi/issues/7547  
- **评论/点赞**：61 / 2  
- **为什么重要**：Windows 开发者群体庞大，但 Pi 运行方式多样，bug 分布零散。该 Issue 作为“收集贴”旨在确定修复优先级，暗示后续将重点优化 Windows 支持。

### 3. [#5886] AgentSession 结算/延续与 assistant-tail 生命周期 bug
- **链接**：https://github.com/earendil-works/pi/issues/5886  
- **评论/点赞**：11 / 4  
- **为什么重要**：由核心贡献者 `mitsuhiko` 整理，涉及后运行逻辑从已失效的 transcript 继续 agent 的元问题，影响 Agent 会话的稳定性和正确性。

### 4. [#6996] Gemini 3.x 模型工具调用失败（缺少 thought_signature）
- **链接**：https://github.com/earendil-works/pi/issues/6996  
- **评论/点赞**：9 / 0  
- **为什么重要**：Gemini 3.x 系列（flash/3.5）在工具调用后提交结果时因历史记录缺少 `thought_signature` 而失败，严重阻碍 Google 模型用户。已关闭但修复方案待验证。

### 5. [#8823] Esc 流式取消不彻底
- **链接**：https://github.com/earendil-works/pi/issues/8823  
- **评论/点赞**：7 / 0  
- **为什么重要**：按压 Esc 无法立即取消 HTTP 请求，需等待模型自然完成。该问题严重影响用户体验，是今日唯一更新于 9月8日 的 Issue，表明仍在积极讨论。

### 6. [#8760] OpenRouter 免费模型因 max_tokens 超限返回 400
- **链接**：https://github.com/earendil-works/pi/issues/8760  
- **评论/点赞**：5 / 0  
- **为什么重要**：Pi 发送的 `max_tokens` 等于模型目录的 `maxOutputTokens`，超出上游提供商的硬限制，导致所有 OpenRouter 免费模型不可用。影响广泛，被标记为 `inprogress`。

### 7. [#9209] GitHub Copilot GPT-6 Astra 被路由到错误的 Chat Completions 端点
- **链接**：https://github.com/earendil-works/pi/issues/9209  
- **评论/点赞**：5 / 0  
- **为什么重要**：Copilot 最新模型 `gpt-6-astra` 要求通过 Responses 端点访问，但 Pi 默认路由到 `/chat/completions`，导致 400 错误。已通过 PR #9253 修复。

### 8. [#8643] Bedrock 上的 OpenAI 模型拒绝 toolResult 中的嵌套图片
- **链接**：https://github.com/earendil-works/pi/issues/8643  
- **评论/点赞**：5 / 1  
- **为什么重要**：OpenAI 模型在 Bedrock 上需要将 tool-result 图片提升到用户消息层，当前实现缺失。贡献者已准备好修复并回归测试，等待合并。

### 9. [#7739] 启动性能对标 jcode
- **链接**：https://github.com/earendil-works/pi/issues/7739  
- **评论/点赞**：3 / 0  
- **为什么重要**：设立启动时间预算，目标在延迟和内存占用上与竞品 jcode 看齐。社区开始关注轻量级替代方案，对 Pi 的启动优化提出明确要求。

### 10. [#8826] Agent 重试退避增加上限
- **链接**：https://github.com/earendil-works/pi/issues/8826  
- **评论/点赞**：4 / 0  
- **为什么重要**：长时间上游中断（如 `503 Too many open files`）导致 agent 重试延迟无限增长，建议添加可配置的退避上限，提升长时间运行稳定性。

---

## 重要 PR 进展

### 1. [#9303] 修复：会话选择器关闭前未恢复会话
- **链接**：https://github.com/earendil-works/pi/pull/9303  
- **状态**：已合并  
- **内容**：修复 `/resume` 或应用 `session.resume` 时，选择器在会话实际恢复前即关闭，导致无反馈的问题。

### 2. [#9301] 功能：设备码登录时确认浏览器打开和剪贴板操作
- **链接**：https://github.com/earendil-works/pi/pull/9301  
- **状态**：开放中  
- **内容**：解决 #9282，在设备码登录时自动打开验证页面并复制用户代码，同时允许用户选择是否强制，提升 GitHub Copilot 等登录体验。

### 3. [#7742] 功能：Ollama Cloud 支持
- **链接**：https://github.com/earendil-works/pi/pull/7742  
- **状态**：开放中  
- **内容**：新增 Ollama Cloud 作为提供商，使用 `OLLAMA_API_KEY` 认证，支持本地与云端混合连接。社区期待已久，标志着 Pi 向多云生态扩展。

### 4. [#9297] 修复：移除 Claude Fable 5 无效的 fallback 目标
- **链接**：https://github.com/earendil-works/pi/pull/9297  
- **状态**：开放中  
- **内容**：`claude-fable-5` 内置 fallback 列表中的 `claude-opus-4-8` 已被 API 拒绝（400），故移除，仅保留 Opus 5 作为备选。

### 5. [#9280] 功能：实现基于实现的文档评估
- **链接**：https://github.com/earendil-works/pi/pull/9280  
- **状态**：已合并  
- **内容**：为每个 Markdown 页面生成实现审计，验证目录覆盖、路径和重复项，并捕获 schema 验证的审计结论，提升文档质量。

### 6. [#8744] 功能：TUI 全屏选择可排除覆盖层
- **链接**：https://github.com/earendil-works/pi/pull/8744  
- **状态**：开放中  
- **内容**：允许用户选择是否忽略覆盖层（如对话框），使全屏文本选择仅从转录内容中复制，避免混入界面元素。

### 7. [#8615] 修复：保留交错的用户内容
- **链接**：https://github.com/earendil-works/pi/pull/8615  
- **状态**：已合并  
- **内容**：修复 `sendUserMessage()` 中文本/图片块的原始顺序，确保经过 idle prompt 或流式引导后内容顺序不变，提升多模态交互一致性。

### 8. [#9292] 功能：添加手动重试 API 和命令
- **链接**：https://github.com/earendil-works/pi/pull/9292  
- **状态**：已合并  
- **内容**：在自动重试之外提供手动重试机制，用户可在 agent 失败后主动触发重试，覆盖自动重试无法恢复的场景，增强容错能力。

### 9. [#9116] 功能：支持对话中插入系统消息
- **链接**：https://github.com/earendil-works/pi/pull/9116  
- **状态**：开放中  
- **内容**：由 `mitsuhiko` 提交，允许在会话中途通过系统消息 delta 方式传递扩展变更，无需重写顶部 prompt，为动态插件和工具变更奠定基础。

### 10. [#9253] 修复：将 Copilot GPT 模型路由到 Responses 端点（修复 astra）
- **链接**：https://github.com/earendil-works/pi/pull/9253  
- **状态**：已合并  
- **内容**：修复 #9209，将 `gpt-6-astra` 等 Copilot 模型从 Chat Completions 切换到正确的 Responses 端点，同时前瞻性地处理了未来模型。

---

## 功能需求趋势

从近期 Issues 和 PR 中，社区最关注的功能方向如下：

- **模型兼容性扩展**：OpenRouter 免费模型、Ollama Cloud、Bedrock 上的 OpenAI 模型、Gemini 3.x 系列、GitHub Copilot 新模型（GPT-6 Astra）的适配与修复。
- **连接与稳定性**：流式取消可靠性、请求超时处理、Agent 重试退避、连接卡死恢复。
- **用户体验优化**：Windows 原生支持、启动性能对标 jcode、TUI 全屏选择排除覆盖层、设备码登录流程简化。
- **SDK 与扩展性**：扩展 API 支持 `x-opencode-session` 头、`stream()` 和 `streamSimple()` 方法暴露、系统消息增量传递、会话元数据持久化。
- **性能与内存**：EventStream 队列改用双端队列避免 O(n²)、流式工具参数解析优化、grep 工具上下文行数导致 OOM 修复。

---

## 开发者关注点

- **高频痛点**：
  - **Esc 流式取消不可靠**（#8823）：按 Esc 后请求仍在进行，直到模型自然完成，影响用户对中断的控制感。
  - **模型路由错误**（#9209, #9277）：新模型（如 GPT-6 Astra）被路由到错误的 API 端点，导致 400 错误，说明模型配置与 API 演进之间存在滞后。
  - **OpenRouter 免费模型不可用**（#8760）：`max_tokens` 溢出问题，阻塞了一大批使用免费模型的开发者。
  - **Windows 使用碎片化**（#7547）：多种运行方式导致 bug 难以定位，社区呼吁统一文档和筛选核心路径。
  - **AgentSession 续传 bug**（#5886）：后运行逻辑从已失效的 transcript 继续，导致不可预知的行为，影响头部使用者。
- **性能焦虑**：多个 Issue 指向 O(n²) 或 OOM 问题（#9055, #9063, #9276），说明部分开发者已将 Pi 用于生产环境，对资源消耗敏感。
- **登录流程**：设备码登录（#9282, #9301）需要手动打开浏览器和复制代码，企业环境多次重登体验不佳，社区希望自动化并保留用户选择权。

---

*数据来源：GitHub earendil-works/pi 仓库，截至 2026-09-08 08:00 UTC。*

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 | 2026-09-08

## 今日速览

Qwen Code 连续发布两个预发布版本（v0.23.1-preview.2、cua-driver-rs v0.20.4），重点增强 Web Shell 的**动态工作流可视化**与 **CUA 驱动跨平台支持**。社区讨论热度集中在新版引入的 **llama-server grammar 解析崩溃**（#10530 / #10435）以及 **Windows 下 conhost 进程泄漏**（#11303），两项均为 P1/P2 级 bug，开发团队已提交修复 PR。此外，**TUI 渲染层迁移**（#8662）持续引发 32 条深度讨论，是当前最受关注的结构性改进。

## 版本发布

### 🚀 v0.23.1-preview.2
- **核心功能**：`feat(web-shell): visualize and manage dynamic workflow runs` — 新增动态工作流运行的可视化与管理能力。
- **性能优化**：`perf(web-shell): derive the session workflow project` — 优化 session 工作流投影的推导效率。
- 发布说明：[查看完整变更](https://github.com/QwenLM/qwen-code/releases/tag/v0.23.1-preview.2)

### 🚀 CUA Driver v0.20.4
- 预编译二进制，提供 macOS（已签名+公证通用二进制）、Linux（x86_64/arm64，glibc 2.31+）、Windows（UIAccess worker + native SDK payload）。
- 内置于 `packages/cua-driver` 目录下，可直接集成。
- 发布说明：[查看完整变更](https://github.com/QwenLM/qwen-code/releases/tag/cua-driver-rs-v0.20.4)

> 注：v0.23.0-nightly.20260907 为每日构建版本，内容与 preview.2 基本一致，仅用于测试。

## 社区热点 Issues

| 序号 | Issue | 热度 | 重要性 |
|------|-------|------|--------|
| 1 | **[#8662] 将 TUI 渲染层从 ink 迁移到 OpenTUI** | 💬 32 评论 | P3 · 持续近 30 天，讨论 deep dive |
| 2 | **[#44] 百炼收费陷阱** | 💬 20 评论 | 已关闭，但引发广泛讨论，涉及用户信任 |
| 3 | **[#8586] 跟踪 activeWork 并实现后台 Agent 恢复** | 💬 9 评论 | P2 · 后台自动化核心需求 |
| 4 | **[#11119] 后台 shell 输出和唤醒通知被静默丢弃** | 💬 8 评论 | P1 · 导致 session 卡死，daemon 场景关键 |
| 5 | **[#11303] Windows conhost.exe 进程泄漏（12h 累积 347 个进程 / ~2.8GB）** | 💬 6 评论 | P1 · 严重内存泄漏，已修 |
| 6 | **[#10530] 400 Failed to initialize samplers（llama-server 解析 grammar 失败）** | 💬 6 评论 | P2 · 0.22.3 回归，影响 Qwen 3.8/3.6 模型 |
| 7 | **[#3361] Agent 误判 shell 输出为空（即使执行成功且 UI 可见）** | 💬 6 评论 | 长期 bug，影响自动化可靠性 |
| 8 | **[#10435] 新版在本地 llama-server 上崩溃（同 #10530）** | 💬 5 评论 | P2 · 另一份用户报告，社区关注度高 |
| 9 | **[#8835] 2026-W33 仓库卫生报告（8 项安全/修复发现）** | 💬 5 评论 | P2 · 包含路径穿越、token 泄露等安全项 |
| 10 | **[#10865] session workflow 投影每帧重复计算三次** | 💬 5 评论 | P2 · 性能优化，关联 #8583 合并后问题 |

**为何重要**：
- #8662 是 TUI 层长期重构的跟踪 issue，涉及 ink 补丁、虚拟视口、闪烁问题，讨论深度极高。
- #11119 为 daemon 场景下的 session 死锁，属于 **P1 级 bug**，直接影响 `qwen serve` 稳定性。
- #11303 的 Windows 内存泄漏数值惊人，社区已有 **修复 PR #11313**。
- #10530 / #10435 的 grammar 解析失败在多个用户间复现，0.22.3 版本中需要紧急回滚或修复。

## 重要 PR 进展

| 序号 | PR | 功能/修复 | 状态 |
|------|-----|----------|------|
| 1 | **[#11313] fix(core): 在 Windows 上每次 PTY 后释放 ConPTY 主机和 conout worker** | 修复 #11303 进程泄漏 | OPEN · autofix/takeover |
| 2 | **[#11238] feat(web-shell): 改进 session 概览导航和详情** | 显示 workspace/branch/PR，状态过滤 | OPEN · autofix/takeover |
| 3 | **[#10410] feat(core): 为延迟工具保留 prompt cache** | 引入 `tool_search`/`tool_call` 两步桥，避免 schema 泄露 | OPEN · autofix/takeover |
| 4 | **[#11281] feat(daemon): 在本地枚举已安装的扩展技能** | 在 ACP 子进程快照前提供技能目录 | OPEN · autofix/takeover |
| 5 | **[#11291] fix(core): 无状态上游错误重试而非结束 turn** | 修复网关推送 error 时 SDK 静默失败 | OPEN · autofix/takeover |
| 6 | **[#11282] feat(core): 在 per-provider customHeaders 中支持 `${session_id}`** | 实现 #10995 需求 | OPEN |
| 7 | **[#11086] feat(serve): 将扩展限制到工作区运行时** | 扩展与 workspace 关联，管理菜单、composer 集成 | OPEN · autofix/takeover |
| 8 | **[#11070] fix(acp): 在冷恢复后保留审批模式** | 持久化 daemon session 的 approval mode | OPEN · autofix/takeover |
| 9 | **[#11206] feat(mesh): 添加持久化共享线程 Agent 协作** | 创建/分配工作、检查结果、解析阻塞、标记完结 | OPEN |
| 10 | **[#11177] feat(web-shell): 在右侧栏添加上下文使用量标签页** | 显示 live 上下文窗口占用，可选头部按钮 | OPEN |

**值得关注**：
- #11313 是当日紧急修复，直接解决 #11303 严重漏洞，已标记 `autofix/takeover`。
- #10410 对客户端性能影响较大，保留 deferred tool 的 prompt cache 可减少 token 消耗。
- #11206 引入的 **mesh 协作**是近期最大功能之一，实现持久化 Agent 与共享工作线程。
- #11177 的上下文用量面板对开发者调试 prompt 窗口非常实用。

## 功能需求趋势

从近期 Issues/PR 中提炼出社区最关心的**五个方向**：

1. **后台自动化与 Agent 持久化**  
   - 代表：#8586（activeWork 跟踪与恢复）、#11119（后台输出丢失）、#11206（mesh 协作）  
   - 社区渴望 Agent 能在 session 切换、后台长时间运行时不丢失进度，且能跨会话协作。

2. **Web Shell 体验增强**  
   - 代表：#10750（turn 导航）、#11238（概览增强）、#11177（上下文用量）、#11163（Git 远程管理）  
   - 用户希望 Web Shell 具备接近本地 IDE 的会话管理能力。

3. **本地模型兼容性与性能**  
   - 代表：#10530 / #10435（llama-server grammar 崩溃）、#10865（投影重复计算）  
   - 使用 llama-server、OpenAI-compatible 后端的用户占比高，对 sampler、grammar 的稳定性非常敏感。

4. **安全与合规**  
   - 代表：#8835（仓库卫生报告 — 路径穿越、token 泄露）、#11272（MCP 工具取消导致进程死亡）  
   - 企业用户关注 ACP 子进程隔离、MCP 服务器崩溃后的恢复能力。

5. **扩展性与 MCP 生态**  
   - 代表：#11281（枚举扩展技能）、#10841（扩展技能命名）、#11086（扩展限制到 workspace）  
   - 社区期待 Qwen Code 的扩展系统更加结构化和可发现。

## 开发者关注点

- 💥 **Windows 内存泄漏**（#11303）：单个 qwen-cli 进程 12h 内消耗 ~2.8GB，已通过 #11313 修复，但原因为 ConPTY 未释放，开发者应尽快升级到包含该修复的版本。
- 🧩 **llama-server grammar 解析失败**（#10530 / #10435）：0.22.3 版本引入的 regression，影响 Qwen 3.8/3.6 以及部分第三方模型。临时方案是回退到 0.22.2 或使用 gemma4-12b 等替代模型。
- 🔄 **/effort 指令不传播到 OpenAI-compatible 后端**（#11227）：用户选择推理 effort 后实际请求未携带该参数，导致本地推理无效果。
- 🛑 **MCP 工具取消导致 stdio 进程永久丢失**（#11272）：在 channel 模式（如钉钉）中，取消长耗时工具调用会杀死 MCP 服务器且无法重启，严重影响生产部署。
- 📊 **CI 频繁失败**：过去一周内有多条 E2E/CI 失败 issue（如 #11307、#11249、#11231 等），主要涉及 OpenTUI 渲染器、PR 格式化检查，表明测试基础设施仍需加固。

> 💡 建议开发者关注以上问题，尤其是 Windows 用户及时更新，使用 llama-server 的用户可暂时锁定 `grammar` 相关设置或采用规避方案。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，技术分析师已就位。以下是为您生成的 **DeepSeek TUI 社区动态日报 (2026-09-08)**。

---

# DeepSeek TUI 社区动态日报 (2026-09-08)

**日报来源:** `github.com/Hmbown/DeepSeek-TUI`
**数据时间:** 2026-09-07 更新

## 今日速览

尽管项目已更名为 **CodeWhale**，但其核心 TUI 社区依然活跃。今日动态聚焦于即将发布的 **v0.9.13** 版本，其核心任务是修复多个高优先级 Bug，包括多行粘贴回归、工具调用截断导致的潜在数据覆盖、以及 ACP 协议兼容性问题。此外，社区对 **TUI 可定制性**和**持续学习能力**的需求呼声很高。

## 社区热点 Issues

以下是过去24小时内最值得关注的10个 Issue：

1.  **[#5981] [Bug] 多行粘贴被分割为单条消息发送 (v9.12 回归)**
    -   **重要性:** **高**。这是一个关键的用户体验回归问题，严重影响日常使用。用户粘贴多行代码时，会被错误地分割成多条独立消息发送，破坏了原有的换行结构。
    -   **社区反应:** 已确认是 v9.12 的引入的 bug，作者正在修复中。
    -   **链接:** [Issue #5981](https://github.com/Hmbown/DeepSeek-TUI/issues/5981)

2.  **[#5986] [Bug] 被截断的 Tool Call 被修复为有效 JSON 并执行**
    -   **重要性:** **严重**。这是一个高危 Bug。当模型输出因长度限制被截断时，系统会尝试将其修复为有效 JSON，导致一个不完整的 `write` 操作被错误执行，可能覆盖用户文件。
    -   **社区反应:** 已被修复 (PR #5983)，作为 v0.9.13 的关键补丁。
    -   **链接:** [Issue #5986](https://github.com/Hmbown/DeepSeek-TUI/issues/5986)

3.  **[#5969] [Bug] ACP Schema 违规导致 JetBrains IDEA 无法连接**
    -   **重要性:** **高**。严重破坏了对 JetBrains IDE 用户的支持。`serve --acp` 接口返回的 `sessionCapabilities.list` 字段类型为布尔值，而 ACP 规范要求为对象，导致严格客户端 (如 IDEA) 无法完成握手。
    -   **社区反应:** 已定位并修复 (PR #5978)，确认是 v0.9.12 的问题。
    -   **链接:** [Issue #5969](https://github.com/Hmbown/DeepSeek-TUI/issues/5969)

4.  **[#5991] [Bug] `allow_insecure_http` 配置项在 v0.9.12 中被移除**
    -   **重要性:** **高**。影响了使用内部 HTTP (非 HTTPS) 服务作为后端的用户。用户无法通过配置文件白名单化不安全连接，只能通过全局环境变量绕过，这带来安全风险和不便。
    -   **社区反应:** 已修复 (PR #5995)，确认在 v0.9.13 中恢复此项配置。
    -   **链接:** [Issue #5991](https://github.com/Hmbown/DeepSeek-TUI/issues/5991)

5.  **[#5976] [Bug] Concentrate 提供商下成本显示为 "unknown"**
    -   **重要性:** **中等**。项目创始人发现，即使 Concentrate 是一个已被完整索引的提供商，其计费/定价覆盖仍不完整，导致会话指标条中的成本显示无法获取。这暗示了定价模型覆盖存在系统性问题。
    -   **社区反应:** 作为 bug 被记录，需要审计所有提供商的定价数据。
    -   **链接:** [Issue #5976](https://github.com/Hmbown/DeepSeek-TUI/issues/5976)

6.  **[#5975] [Bug] 模型选择器 (route · configured) 响应严重滞后**
    -   **重要性:** **中等**。体验问题。创始人报告模型选择器界面非常卡顿，且鼠标无法在该界面工作，缺乏按列排序功能。
    -   **社区反应:** 记录了三个相关但独立的问题，核心是需要性能优化。
    -   **链接:** [Issue #5975](https://github.com/Hmbown/DeepSeek-TUI/issues/5975)

7.  **[#5974] [Bug] MCP 服务器重新认证导致整个 TUI 界面冻结**
    -   **重要性:** **中等**。严重的体验问题。在扩展页面对 MCP 服务器进行重新认证时，整个 TUI 会完全卡死，且“诊断”按钮失效，用户无法恢复。
    -   **社区反应:** 刚被记录，尚无解决方案，等待进一步排查。
    -   **链接:** [Issue #5974](https://github.com/Hmbown/DeepSeek-TUI/issues/5974)

8.  **[#5860] [Enhancement] 对话持续自学习 (自动技能进化)**
    -   **重要性:** **高**。这是一个功能需求，也是社区关注的焦点。用户希望 Agent 能自动从重复解决的同类问题中提取模式，自动生成或更新 `SKILL.md`，实现技能的自动化演化。
    -   **社区反应:** 获得5条评论，讨论热烈，代表了社区对 Agent 智能化的更高期待。
    -   **链接:** [Issue #5860](https://github.com/Hmbown/DeepSeek-TUI/issues/5860)

9.  **[#6004] [Enhancement] 添加会话状态 Hook 事件**
    -   **重要性:** **中等**。这是一个开发者需求。当前 Hook 系统缺乏对会话状态（如空闲、等待用户输入）的感知，开发者无法编写插件或脚本来监控和响应这些底层状态变化。
    -   **社区反应:** 有3条评论，用户和开发者在讨论具体实现方式。
    -   **链接:** [Issue #6004](https://github.com/Hmbown/DeepSeek-TUI/issues/6004)

10. **[#6001] [Enhancement] 会话恢复 `--continue` 对有多会话的工作区不明确**
    -   **重要性:** **低-中**。易用性问题。当工作区存在多个历史会话时，`run --continue` 命令只能恢复最近一个，且未提供选择能力，导致用户无法定位到目标会话。
    -   **社区反应:** 被记录为需改进项，建议在提示中显示 Session ID。
    -   **链接:** [Issue #6001](https://github.com/Hmbown/DeepSeek-TUI/issues/6001)

## 重要 PR 进展

以下是过去24小时内最值得关注的10个 PR：

1.  **[#6002] [OPEN] 集成 0.9.13 版本的 PR 并推迟 ShannonNet 执行**
    -   **内容:** 将多个针对 v0.9.13 的修复 PR (包括 #5982, #5973, #5996, #5990) 合并到一个集成分支，解决冲突，为最终发布做准备。
    -   **链接:** [PR #6002](https://github.com/Hmbown/DeepSeek-TUI/pull/6002)

2.  **[#6000] [CLOSED] 准备 v0.9.13 版本发布**
    -   **内容:** 正式发布 v0.9.13，包含了对多行粘贴回归、工具调用截断、ACP Schema、Countectrate 指标路径、目标循环边界等关键 bug 的修复，以及计算机使用插件的更新。
    -   **链接:** [PR #6000](https://github.com/Hmbown/DeepSeek-TUI/pull/6000)

3.  **[#5983] [CLOSED] 修复引擎：禁止分发参数被截断的 Tool Call**
    -   **内容:** 对应 Issue #5986。在工具调用分发前增加了一个检查，确保参数完整，从根源上杜绝了因截断导致的文件覆盖风险。
    -   **链接:** [PR #5983](https://github.com/Hmbown/DeepSeek-TUI/pull/5983)

4.  **[#5993] [CLOSED] 修复 TUI：重新启用粘贴突发检测启发式算法**
    -   **内容:** 对应 Issue #5981。修复了 v9.12 中因错误依赖 `bracketed paste` 导致的多行粘贴问题。重新启用了基于键入速度的突发检测算法，以确保在不支持 `bracketed paste` 的终端上也能正确工作。
    -   **链接:** [PR #5993](https://github.com/Hmbown/DeepSeek-TUI/pull/5993)

5.  **[#5978] [CLOSED] 修复 ACP：将 session list 声明为对象并移除嵌套的 load 能力**
    -   **内容:** 对应 Issue #5969。调整了 `initialize` 响应的 JSON 结构，使其符合 ACP 规范，从而修复了 JetBrains IDEA 无法连接的问题。
    -   **链接:** [PR #5978](https://github.com/Hmbown/DeepSeek-TUI/pull/5978)

6.  **[#5995] [CLOSED] 修复 Config：再次启用每个 Provider 的 `allow_insecure_http` 配置**
    -   **内容:** 对应 Issue #5991。修复了 v9.12 中此配置项被忽略的回归，允许用户为特定的 LAN 或内部 Provider 单独配置是否允许 HTTP 连接。
    -   **链接:** [PR #5995](https://github.com/Hmbown/DeepSeek-TUI/pull/5995)

7.  **[#5998] [CLOSED] 更新计算机使用 (CU) 插件至 0.2.0**
    -   **内容:** 升级内置的计算机使用插件版本。0.2.0 版本带来了原生的 macOS 辅助功能后端、桌面套接字传输以及对 SSH 和鸿蒙 HDC 远程设备的支持。
    -   **链接:** [PR #5998](https://github.com/Hmbown/DeepSeek-TUI/pull/5998)

8.  **[#5982] [OPEN] 添加模型绑定的密钥编辑确认功能**
    -   **内容:** 为 TUI 增加了一个配置项，允许用户在开发/调试环境下，针对特定模型或提供者，绕过强制性的密钥脱敏。该功能需要在收到确切的“读回”确认后才激活，以降低意外泄露风险。
    -   **链接:** [PR #5982](https://github.com/Hmbown/DeepSeek-TUI/pull/5982)

9.  **[#5987] [CLOSED] 修复 VS Code 扩展：使发送路径正常工作并修复安全漏洞**
    -   **内容:** 对应 Issue #5834。修复了 VS Code 扩展从未成功启动过会话的严重 bug (HTTP Status Code 匹配错误)，并关闭了一系列安全漏洞。
    -   **链接:** [PR #5987](https://github.com/Hmbown/DeepSeek-TUI/pull/5987)

10. **[#5870] [CLOSED] 修复 Tools：原子提交分割——按依赖关系排序不相关的更改**
    -   **内容:** 社区贡献者 `goransh-walia` 提交的功能。实现了一个工具，用于将 Agent 的一次性大规模提交，按文件修改之间的依赖关系自动拆分成多个逻辑清晰的原子提交。这对于代码审查和 Git 历史清晰度非常有价值。
    -   **链接:** [PR #5870](https://github.com/Hmbown/DeepSeek-TUI/pull/5870)

## 功能需求趋势

从过去24小时的 Issues 中，可以提炼出社区最关注的三个功能方向：

1.  **TUI 可配置性与用户体验优化:** 大量 Issue 围绕 TUI 底栏定制 (#5950)、命令历史记录改进 (#6006)、更智能的会话恢复 (#6001)、以及界面性能优化 (#5975) 展开。这表明核心用户群正从“能用”向“好用”演进，对工作流的个性化控制和系统性能有更高要求。
2.  **Agent 自我进化与状态感知能力:**
    -   **自我进化:** 社区对 Agent 能够从对话中**自动学习**并生成技能 (Skill) 的呼声很高 (#5860)。这代表了用户不再满足于手动定义技能，期望 Agent 能变得更“智能”。
    -   **状态感知:** 开发者希望拥有更细粒度的 Hook 事件，能够感知会话的**底层状态** (如空闲、等待用户输入) (#6004)，以便开发更复杂的插件或自动化脚本。
3.  **非功能性需求与稳定性:** 修复高频 Bug 是社区永恒的主题。v0.9.13 的发布计划集中体现了这一点，包括修复**多行粘贴**、**工具调用截断**、**ACP 协议兼容性**、**配置项回归**等影响用户日常使用稳定性的问题。

## 开发者关注点

开发者反馈中的痛点和高频需求总结如下：

-   **性能问题反馈增多:** 创始人直接报告了模型选择器卡顿 (#5975) 和会话指标 (`tok/s`) 计算不准确 (#5977) 的问题，说明开发者正更深入地使用产品，并开始关注系统性能细节。
-   **配置回退 (Regression) 引发挫败感:** `allow_insecure_http` 配置在 v0.9.12 中被静默忽略 (#5991)，直接影响了使用非标准基础设施的开发者。这类回归对开发者体验的打击是直接的，因此修复被列为高优先级。
-   **工具链稳定性是基础需求:** 并行测试失败 (#5929)、Windows CI 不稳定 (#5980)、测试栈溢出 (#5988) 等问题的持续出现，表明测试基础设施的健壮性是核心开发者（尤其是项目创始人 Hmbown）关注的重点。这直接关系到开发效率和 CI/CD 的可靠性。
-   **文档和国际化需求:** 虽然是非紧急需求，但对中国用户而言，中文文档的缺失 (#5482) 是一个明确的痛点。同时，项目更名为 CodeWhale 后，相关的文档清理和指导 (#5984) 也是开发者社区会注意到的细节。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*