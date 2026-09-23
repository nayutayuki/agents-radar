# AI CLI 工具社区动态日报 2026-09-23

> 生成时间: 2026-09-23 00:55 UTC | 覆盖工具: 9 个

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

# AI CLI 工具横向对比分析报告（2026-09-23）

## 1. 生态全景

当前 AI CLI 工具生态正处于“模型驱动+生态竞速”阶段：各工具均以最快速度支持下一代模型（Claude Opus 5.5、GPT-6 Sol/Luna、Gemini 3.8 Flash），同时围绕 **会话稳定性、多代理协作、Windows 兼容性、MCP 生态扩展** 四个维度展开激烈竞争。头部工具（Claude Code、OpenAI Codex、Gemini CLI）已形成较成熟的 Agent 框架和社区规模，而新锐工具（Kimi Code、DeepSeek TUI / Codewhale）正通过品牌重塑和架构重构抢位。整体趋势从“能跑代码”向“可预测、可调试、可配置的企业级 Agent 工作台”演进。

---

## 2. 各工具活跃度对比

| 工具 | 今日热点 Issues 数 | 重要 PR 数 | 最新 Release (版本/主要特性) |
|------|-------------------|------------|------------------------------|
| **Claude Code** | 10 | 1 | v2.1.280 (Claude Opus 5.5 默认模型) |
| **OpenAI Codex** | 10 | 10 | rust-v0.156.0 (全屏 TUI + 默认语音) |
| **Gemini CLI** | 10 | 10 | v0.62.0-nightly (代理修复) |
| **GitHub Copilot CLI** | 10 | 1 | v1.0.89-0 (Claude Opus 5.5 支持) |
| **Kimi Code CLI** | 1 | 8 | v1.52.0 (入口迁移至 TypeScript 版) |
| **OpenCode** | 10 | 10 | v0.24.5-preview.0 / desktop-v0.24.4 |
| **Pi** | 10 | 10 | v0.87.1 (GPT-6 Sol/Luna 支持) |
| **Qwen Code** | 10 | 10 | v0.24.5-preview.0 / v0.24.4 |
| **DeepSeek TUI (Codewhale)** | 10 | 10 | v0.10.0 (品牌重塑为 Codewhale) |

**说明**: Issues/PR 数取自日报中“热点”与“重要”精选条目，实际仓库总活动量更高。Kimi Code 因数据源仅含 1 个热点 Issue，但其 PR 活跃度不低。

---

## 3. 共同关注的功能方向

### 3.1 新模型极速适配
几乎所有工具都在同一周期内支持了 **Claude Opus 5.5**（Claude Code、Copilot CLI、Pi）或 **GPT-6 Sol/Luna**（OpenAI Codex、Pi、OpenCode），表明紧跟前沿模型是维持竞争力的基本门槛。

### 3.2 Windows 平台稳定性修复（5+ 工具涉及）
- **Claude Code**: 窗口置顶 bug、VM 共享文件写入失败、盘符大小写问题
- **OpenAI Codex**: 沙箱初始化失败、项目侧边栏丢失、安装卡死、特定会话崩溃
- **Gemini CLI**: 认证无限循环（Windows/WSL 环境）
- **Copilot CLI**: 无直接 Windows 专项，但 OOM 问题在多平台均有
- **Qwen Code**: Linux/WSL 剪贴板静默失败

**共性**: Windows 用户占比高，但兼容性测试不足，是当前所有工具的共同短板。

### 3.3 会话稳定性与数据安全
- 会话 OOM（Copilot CLI #4780）、会话损坏（Kimi Code #2336）、上下文压缩破坏记录（OpenAI Codex #44363）、后台文本块丢失（Claude Code #65051）—— 这些问题直接导致开发工作流中断或数据丢失，成为用户首要痛点。

### 3.4 MCP / 插件生态兼容与扩展
- **Gemini CLI**: 修复 MCP 配置损坏导致工具意外启用；新增 pkgdiet 依赖检查 skill
- **OpenCode**: MCP OAuth 错误展示改进、多 PR 涉及 MCP 集成
- **Qwen Code**: 推进 MCP 作用域工具调用与来源隔离
- **Codewhale**: 统一两套 MCP 客户端栈、升级协议至 2026-07-28 规范

MCP 正成为事实上的插件/工具发现标准，各工具都在追赶兼容性。

### 3.5 可配置性与工作流定制
- **Claude Code**: 工作树目录位置可配置、程序化会话重命名
- **Gemini CLI**: settings.json 被忽略（bug）、MCP 启用/禁用命令修复
- **OpenCode**: 自定义 provider 静默跳过（工具能力字段缺失）、配置文件重载失败
- **Pi**: 自定义提供商显示名称、禁用 /share 命令开关

用户期望更细粒度的配置控制，而不是“黑盒”自动行为。

### 3.6 多账户 / 多身份支持
- **Claude Code**: 多 Connector 账户支持以 387 个 👍 成为社区最热功能请求 (#27302)
- **Gemini CLI**: 浏览器代理无法读取多账户配置
- **Pi**: 多模型/多提供商切换时思考级别保持

企业级用户和多身份切换场景正在普及。

---

## 4. 差异化定位分析

| 工具 | 核心定位 | 目标用户 | 技术路线特点 |
|------|---------|---------|-------------|
| **Claude Code** | 深度 Agent + Connector 生态 | 重度 Agent 用户、企业协作 | 强会话管理、Monior/Worktree、多 Connector 联动 |
| **OpenAI Codex** | 全功能桌面化 CLI（TUI+语音） | 终端用户、追求交互创新 | Rust 原生、全屏 TUI、内置语音、MXC 沙箱实验 |
| **Gemini CLI** | 子代理/多代理联邦 | 复杂多任务开发者 | 子代理体系、AST 感知探索、零依赖沙箱提案 |
| **GitHub Copilot CLI** | GitHub 轻量级集成 | 单一 GitHub 工作流用户 | 极简模型配置、Connector 授权改进、WebSocket 退出机制 |
| **Kimi Code CLI** | Python → TypeScript 迁移 | 原 Python 版用户、新 TypeScript 生态 | 入口重定向、依赖升级、WebKit IME 修复 |
| **OpenCode** | 多平台原生 + 桌面版 | 跨平台开发者（ARM64 需求突出） | Windows ARM64 原生、桌面版与 TUI 分离、配置静默失败修复 |
| **Pi** | 极致扩展性（自定义提供商/插件） | 高级用户、模型猎人 | 多模型网关 Yolo-Auto、扩展 API 开放、全屏模式性能优化 |
| **Qwen Code** | 开源企业级可管理 Agent | 大规模部署、安全合规 | 沙箱加固、受管运行时、ACL 管理扩展、MCP 作用域隔离 |
| **DeepSeek TUI (Codewhale)** | 多代理舰队 + 浏览器端 | 多代理并行用户、Chrome 集成 | 子代理可视化、Fleet 概念、Chromewhale 扩展、i18n |

**关键观察**:
- **Google (Gemini CLI) 和 OpenAI (Codex)** 更倾向于在底层模型能力上做差异化（如子代理、语音），而 **Anthropic (Claude Code)** 和 **GitHub (Copilot CLI)** 则更注重工作流集成与身份管理。
- **Pi 和 Codewhale** 代表“极客向”路线，给予用户最高的自定义自由，但也要求用户具备一定技术背景。
- **Qwen Code** 领跑企业级安全沙箱和管理能力，是唯一明确强调受管运行时和跨国部署的工具。

---

## 5. 社区热度与成熟度

| 工具 | 社区活跃度（基于 Issue 评论数、点赞数） | 成熟度判断 |
|------|------------------------------------------|------------|
| **Claude Code** | 极高（#27302 获 387 👍，253 条评论） | 成熟，但仍有显眼 bug（Windows） |
| **OpenAI Codex** | 高（#29156 获 35 👍，多条 20+ 评论） | 功能迭代快，版本号跳跃大 |
| **Gemini CLI** | 中高（#22323 获 10+ 评论，PR 密集） | 快速迭代中，Nightly 版频繁 |
| **Copilot CLI** | 中等（#4438 获 9 👍，7 条评论） | 较稳定，但修复速度慢（仅 1 PR） |
| **Kimi Code CLI** | 低（仅 1 个热点 Issue） | 处于迁移过渡期，社区聚焦于迁移 |
| **OpenCode** | 高（#19130 获 13 👍，27 条评论） | 快速扩展，桌面版和 ARM64 是热点 |
| **Pi** | 中高（#9052 获 6 👍，多处 3+ 评论） | 成熟版本号，但 0.86.x 回归问题突出 |
| **Qwen Code** | 高（#7040 长期讨论，CI 活跃） | 社区贡献活跃，P1/P2 响应快 |
| **Codewhale** | 中（#6011 获 9 条评论） | 年轻但重构活跃，品牌重塑后有望增长 |

**总结**: **Claude Code** 和 **OpenAI Codex** 社区体量最大；**Qwen Code** 和 **OpenCode** 增速最快；**Copilot CLI** 和 **Kimi Code CLI** 相对边缘化。

---

## 6. 值得关注的趋势信号

### 6.1 “Token 可视化管理” 成为刚需
- Codewhale (#6011) 提出按组件、模型、缓存命中率进行成本统计；Pi 引入思考级别显示；Claude Code 用户要求主屏幕显示用量限额。
- **信号**: 开发者不再满足于“黑箱”计费，需要在工作流中实时监控 token 消耗，以便优化选择模型和压缩策略。

### 6.2 AST 感知正在重塑代码交互范式
- Gemini CLI (#22745) 评估 AST 感知文件读取/搜索来减少 Token 消耗；Codewhale (#6203) 要求用 AST 符号定位替代文本匹配锚定。
- **信号**: 纯文本匹配的局限制正在被 AST 层面的精确操作取代，这将是下一波效率提升的关键技术路径。

### 6.3 桌面端与终端 TUI 的融合竞争
- OpenAI Codex 推出全屏 TUI + 默认语音；Codewhale 发布 Chrome 侧边栏扩展；Claude Code 和 OpenCode 都强化了桌面版窗口管理。
- **信号**: “TUI 为根，桌面为翼”的混合形态成为标配。语音交互从“锦上添花”变为默认功能，标志 AI CLI 从纯键盘工具转向多模态交互工作台。

### 6.4 “零依赖沙箱”成为安全共识
- Gemini CLI (#19873) 提出利用模型 Bash 亲和力实现零依赖沙箱；Qwen Code (#12417) 加固 bubblewrap 沙箱边界；Codewhale (#4955) 要求提供 `--no-sandbox` 选项（安全性与便利性的博弈）。
- **信号**: 沙箱是执行代码的信任基石，但过度沙箱会破坏开发体验。未来的方向是“按需沙箱” + “可配置安全策略”。

### 6.5 国际化（i18n）需求从“可选”变为“必须”
- Codewhale PR #6405 推进词典化 i18n；中文输入法兼容性问题（#2323）在多个工具中被提及（Claude Code、Gemini CLI、Codewhale）。
- **信号**: 随着非英语开发者社区壮大，TUI 对 Unicode 和本地化输入法的支持将成为基本要求，而非加分项。

---

以上分析基于 2026-09-23 各工具社区数据。建议技术决策者关注 **会话稳定性**（优先修复 OOM 和压缩破坏问题）、**Windows 兼容性**（优先级从“nice-to-have”提升为“blocker”）、以及 **MCP 生态标准化**（选择支持 MCP 2026-07-28 新规范的工具）。开发者个人则可依据对多代理协作、模型自定义、企业安全等不同需求，选择差异化定位最匹配的工具。

---

## 各工具详细报告

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills 社区热点

> 数据来源: [anthropics/skills](https://github.com/anthropics/skills)

# Claude Code Skills 社区热点报告（数据截至 2026-09-23）

## 1. 热门 Skills 排行

| 排行 | Skill (PR) | 功能说明 | 社区讨论热点 | 状态 |
|------|------------|----------|--------------|------|
| 🥇 | **skill-creator 触发评估修复** · [#1298](https://github.com/anthropics/skills/pull/1298) | 修复 skill-creator 在触发检测中存在的 false miss、Windows 管道兼容性、运行时失败误判等问题。 | 开发者关注评估框架本身的可靠性——trigger 判定不准会导致 Skill 描述优化走向错误方向。 | Open |
| 🥈 | **proofcore-contract-auditor** · [#1771](https://github.com/anthropics/skills/pull/1771) | 为 Web3 开发者提供 Solidity/Rust 智能合约静态分析，并在 TON 区块链上锚定审计证明。 | 社区对跨链安全工具需求强烈，但讨论集中在是否应纳入官方集合（合规与维护成本）。 | Open |
| 🥉 | **mcp-builder 兼容性修复** · [#1742](https://github.com/anthropics/skills/pull/1742) | 支持 MCP ≥ 2.0.0 的 `streamable_http_client` 导入变更及自定义 HTTP 头部配置。 | 生态依赖升级引发的 breaking changes 修复，开发者希望 MCP 技能保持向后兼容。 | Open |
| 4 | **md2video-audio** · [#1703](https://github.com/anthropics/skills/pull/1703) | 将 Markdown 文档编译为含真人语音配音的专业级 MP4 视频（零成本，基于 Marp + 开源 TTS）。 | 内容创作者和文档团队高度期待，讨论热点在于语音合成质量和输出分辨率控制。 | Open |
| 5 | **Detect orphaned docx comments** · [#1734](https://github.com/anthropics/skills/pull/1734) | 检测 Word 文档中孤立的（orphaned）批注，提升文档审阅质量。 | Office 文档处理是高频场景，社区希望此技能成为 DOCX 生态的标准配套工具。 | Open |
| 6 | **Pyxel 复古游戏开发** · [#525](https://github.com/anthropics/skills/pull/525) | 指导 Claude 创建、调试和验证基于 Pyxel 的复古风格 Python 游戏（含 headless 运行与帧检查）。 | 教育/娱乐场景热度高，讨论点集中在测试框架集成度（直接帧对比）和互动性。 | Open |
| 7 | **AWT (AI Watch Tester)** · [#822](https://github.com/anthropics/skills/pull/822) | 零代码 E2E 测试技能，赋予 Claude 视觉和浏览器控制能力，可自动生成并执行测试用例。 | 测试自动化是重磅需求，社区热议其在复杂 SPA 应用中的稳定性及录制回放机制。 | Open |
| 8 | **blast-radius** · [#1776](https://github.com/anthropics/skills/pull/1776) | 批量/破坏性操作前的安全检查清单（如归档用户、撤销权限、删除行、批量邮件），防止意外后果。 | 运营和安全团队高度赞赏，讨论集中在如何平衡检查深度与用户体验。 | Open |

> 注：排名依据 PR 评论量（官方排序），所有列出的 PR 当前均为 **Open** 状态，尚未合并至主分支。

## 2. 社区需求趋势

通过分析 Issues（按评论数排序），社区最期待的新 Skill 方向集中在以下五个领域：

- **🛡️ 安全与信任** — Issue #492（43 评论）质疑社区 Skills 借用 `anthropic/` 命名空间导致信任边界滥用；#412 提案“agent-governance”关注代理系统安全模式。 **社区呼吁官方建立 Skill 签名/认证机制。**

- **🏢 组织级共享与协作** — Issue #228（16 评论）要求 Skills 能在组织内直接共享，无需手动下载上传。**团队协作场景下的 Skill 分发是重大痛点。**

- **🧠 上下文窗口优化** — Issue #1487（4 评论）指出 `claude-api` 技能一次性注入 ~156k token 耗尽上下文。Issue #1329 提出“compact-memory”符号化压缩代理状态。**社区急需高效上下文管理技能。**

- **🔧 评估与质量保障** — Issue #556（12 评论）显示 `run_eval.py` 对 `claude -p` 的触发率为 0%，整个评估流水线失效。Issue #202 批评 skill-creator 文风像开发文档。**社区希望获得可落地的 Skill 开发最佳实践和可靠评估工具。**

- **📄 文档与办公自动化** — 持续产出类：Issue #1175 探讨 SharePoint Online 文档处理的安全与上下文窗口平衡；#1362 讨论 web-artifacts-builder 在前沿工具链下的损坏。**Office 和 Web 文档处理仍是刚需。**

## 3. 高潜力待合并 Skills

以下 PR 评论活跃且功能价值突出，具备近期合并潜力：

| PR | Skill | 潜力理由 |
|----|-------|----------|
| [#1771](https://github.com/anthropics/skills/pull/1771) | proofcore-contract-auditor | 填补 Web3 安全审计空白，非侵入式零存储证明架构具有创新性，若官方认可标准则可快速合并。 |
| [#1703](https://github.com/anthropics/skills/pull/1703) | md2video-audio | 零成本、全开源管线，直接覆盖 Markdown→视频的常见需求，社区呼声高且无外部依赖风险。 |
| [#525](https://github.com/anthropics/skills/pull/525) | Pyxel 游戏开发 | 来自 Pyxel 原作者（kitao），技术成熟度极高，与教育场景高度契合，长期开放但只需最后审查。 |
| [#822](https://github.com/anthropics/skills/pull/822) | AWT (AI Watch Tester) | 完整开源工具，零代码 E2E 测试是杀手级用例，若通过稳定性验证将大幅提升 Claude Code 的测试能力。 |
| [#723](https://github.com/anthropics/skills/pull/723) | testing-patterns | 覆盖全面测试哲学的综合性技能（Trophy 模型、React、单元、集成），对开发团队直接赋能。 |

## 4. Skills 生态洞察

**一句话总结：当前社区最集中的诉求是“信任与可靠性”——既包括 Skills 来源的可信（命名空间冒用风险），也包括 Skill 触发与评估的准确（0%触发率、假阴性检测），同时渴望组织级共享和上下文高效利用的能力。**

Anthropic 需优先解决 Skill 验证框架的鲁棒性、建立官方身份认证机制，并开放组织内分发渠道，才能释放社区创新潜能。

---

好的，各位开发者，早上好！今天是2026年9月23日。以下是为你整理的 Claude Code 社区日报。

---

## 📰 今日速览

昨日，Anthropic 发布了 `v2.1.280` 版本，正式引入了万众期待的 **Claude Opus 5.5** 模型，成为默认 Opus 模型；社区中，关于**多账户 Connector 支持**的呼声持续高涨，已成为最受关注的功能请求；同时，**Windows 平台窗口始终置顶**和 **Linux 桌面端会话文本丢失**的Bug也引发了较多讨论。

---

## 🚀 版本发布

### 最新版本: `v2.1.280`

此版本已于昨日发布，主要更新内容如下：

*   **新模型**: 新增 **Claude Opus 5.5** (`claude-opus-5-5`) 模型支持，并设为 Opus 系列的默认模型。提供 **100万上下文窗口**，定价为 $4/$20 每百万 token，缓存读取仅需 $0.20/百万 token。
*   **体验优化**: 在全屏模式下为更多列表添加了鼠标支持。例如，现在可以通过滚轮滚动 `/skills` 列表，并在 `/plugin` 中点击切换技能的开关状态。

---

## 🔥 社区热点 Issues

以下是根据讨论热度与重要性挑选的10个值得关注的 Issue：

1.  **💡 [Feature] 支持多个 Connector 账户 (#27302)**
    *   **链接**: [Issue #27302](https://github.com/anthropics/claude-code/issues/27302)
    *   **热度**: 253条评论 👍387
    *   **摘要**: 社区普遍希望能在 Claude Code Web 端（claude.ai/code）使用同一个 Connector 服务（如GitHub、Slack）的**多个不同账户**。当前功能限制用户只能绑定一个账户，给需要切换身份工作的开发者带来了不便。这是目前呼声最高的功能请求。

2.  **🐛 [Bug] Windows桌面应用窗口始终置顶且无法关闭 (#89467)**
    *   **链接**: [Issue #89467](https://github.com/anthropics/claude-code/issues/89467)
    *   **热度**: 37条评论 👍75
    *   **摘要**: Windows 用户反馈桌面版 Claude Code 窗口会**始终置顶**于所有其他窗口之上，而在设置中找不到关闭此行为的选项，严重干扰多任务处理。

3.  **💡 [Feature] 可配置的工作树（worktree）目录位置 (#27282)**
    *   **链接**: [Issue #27282](https://github.com/anthropics/claude-code/issues/27282)
    *   **热度**: 13条评论 👍68
    *   **摘要**: 开发者希望可以自定义 `worktree` 的存放位置，特别是支持将其放置在**主仓库的同级目录**而非仓库内部，以遵循业界更推荐的文件组织方式。

4.  **🐛 [Bug] 后台（daemon）会话响应丢失文本块 (#65051)**
    *   **链接**: [Issue #65051](https://github.com/anthropics/claude-code/issues/65051)
    *   **热度**: 13条评论 👍9
    *   **摘要**: 一个在 Linux 上的回归Bug。当使用背景 `daemon` 模式时，如果模型的回复混合了文本和 `tool_use`，会话记录中的**文本块会被丢弃**，导致信息不完整。

5.  **🐛 [Bug] Windows 虚拟共享文件夹文件写入失败 (#73386)**
    *   **链接**: [Issue #73386](https://github.com/anthropics/claude-code/issues/73386)
    *   **热度**: 9条评论 👍1
    *   **摘要**: 在 Windows 平台的 VM 共享文件夹驱动器中，当目标文件已存在时，Claude Code 的 `Edit`/`Write` 工具会因 `ENOENT: fchmod` 错误而失败，导致无法修改代码。

6.  **💡 [Feature] 程序化重命名会话/线程 (#40346)**
    *   **链接**: [Issue #40346](https://github.com/anthropics/claude-code/issues/40346)
    *   **热度**: 8条评论 👍14
    *   **摘要**: 开发者希望能在工作流中通过 Hook 或工具**自动、动态地重命名**会话。例如，在处理 GitHub Issue 时，让会话名称自动变成“处理 Issue #xxx”，以方便管理。

7.  **💡 [Feature] 桌面版主屏幕显示用量限额 (#80261)**
    *   **链接**: [Issue #80261](https://github.com/anthropics/claude-code/issues/80261)
    *   **热度**: 6条评论 👍22
    *   **摘要**: 用户希望在桌面应用的**主屏幕上**就能看到一个**持续的用量指示器**，方便随时了解自己的 API 调用额度或使用限制，而不是等到超额时才被通知。

8.  **🐛 [Bug] `Bash` 工具名不副实，在 macOS 上实际运行 Zsh (#91498)**
    *   **链接**: [Issue #91498](https://github.com/anthropics/claude-code/issues/91498)
    *   **热度**: 5条评论 👍1
    *   **摘要**: 一个有趣且影响实际的命名问题。`Bash` 工具在 macOS 上实际上调用的是用户的登录 shell（`zsh`），导致模型可能生成仅适用于 `bash` 的语法，从而在 `zsh` 中执行失败。

9.  **🐛 [Bug] 监视器（Monitor）的持久模式被限制为30分钟 (#94553)**
    *   **链接**: [Issue #94553](https://github.com/anthropics/claude-code/issues/94553)
    *   **热度**: 5条评论 👍5
    *   **摘要**: 自 `v2.1.26x` 版本起，`Monitor` 工具在使用 `persistent: true` 参数时，最长只能持续30分钟。这对于需要长时间监控文件变化的场景是一个重要的回归。

10. **🐛 [Bug] Windows 工作树隔离检查因大小写敏感失败 (#91618)**
    *   **链接**: [Issue #91618](https://github.com/anthropics/claude-code/issues/91618)
    *   **热度**: 4条评论
    *   **摘要**: 在 Windows 系统上，当使用 `.code-workspace` 文件打开位于不同盘符（如 `D:` 盘）的仓库时，`isolation-worktree` 安全检查因**盘符字母（大小写）比较**失败而拒绝启动，导致工作流中断。

---

## 🤝 重要 PR 进展

以下是过去24小时内值得关注的 Pull Request：

### 单一 PR 详情

*   **Agent指令模组 `agents-md` (#95409)**
    *   **状态**: ❌ (已关闭，未合并)
    *   **链接**: [PR #95409](https://github.com/anthropics/claude-code/pull/95409)
    *   **作用**: 此 PR 意图新增一个名为 `agents-md` 的社区模组（mod）。该模组的核心功能是让用户项目中的 `AGENTS.md` 文件能够像 `CLAUDE.md` 一样，被 Claude Code 引擎读取并作为项目指令。
    *   **分析**: 尽管该 PR 暂未合并，但其目标与社区中强烈的需求（如 Issue #95795 要求全局 `AGENTS.md` 支持）高度一致，是社区自我驱动、扩展工具能力的一个优秀范例。

*(注：由于该仓库主要依赖 Issues 进行 Bug 跟踪和功能讨论，PR 活动相对较少，且多为非官方社区贡献。)*

---

## 📈 功能需求趋势

从近期 Issues 中可以提炼出社区最关注的几个功能方向：

1.  **增强连接性与账户管理**:
    *   **多账户支持**: 用户对支持同一 Connector 服务（如 GitHub）下多个账户的诉求非常强烈 (#27302)。
    *   **身份认证与权限**: CVP（Claude Verified Professional）审批流程卡顿 (#88961) 以及对密码输入的硬性拦截 (#78160) 都反映出账户与权限管理是现有体验的明显短板。

2.  **工作流与项目管理优化**:
    *   **配置灵活性**: 对 `worktree` 目录位置可配置 (#27282) 和 `AGENTS.md` 全局化 (#95795) 的呼声很高，开发者希望有更强的灵活性来适配本地开发环境。
    *   **自动化与脚本化**: 程序化会话重命名 (#40346) 和插件触发式自动补全 (#96185) 代表了社区对更深层次工作流自动化和脚本化的期待。

3.  **桌面端与应用体验提升**:
    *   **UI/UX 打磨**: “窗口始终置顶” (#89467)，“会话分组混乱” (#92179)，“用量限额显示” (#80261) 等都是围绕桌面应用的体验优化提议。
    *   **任务管理与通知**: 如 PR 提交后自动修复或回复评论的 toggle 不生效 (#68083) 等，反映出用户对桌面端作为核心工作台的稳定性和功能性有更高要求。

4.  **模型行为与工具准确性**:
    *   **工具与环境匹配**: `Bash` 工具名不副实 (#91498) 的问题说明开发者非常在意工具与实际运行环境的一致性，以避免模型产生误导性的代码。
    *   **模型输出完整性**: 后台会话文本块丢失 (#65051) 和 Opus 5 的 `thinking` block 问题 (#95764) 表明，模型返回内容的准确性和完整性仍是社区关注的核心。

---

## 🧐 开发者关注点

综合过去24小时的 Issue 动态，开发者普遍感到头痛的问题集中在：

1.  **Windows 生态兼容性**: 多个 Bug 都明确指向 Windows 平台，包括窗口行为异常 (#89467)、VM 共享文件操作失败 (#73386) 和盘符大小写问题 (#91618)。这表明 Claude Code 在 Windows 上的适配仍需投入更多精力。
2.  **会话与工作树状态混乱**: 新启用的会话被分配到错误的工作树 (#91405) 和历史记录因切换工作树而不同步 (#84209) 等问题，让开发者担心**数据丢失和状态管理混乱**，这对日常开发工作流是致命的。
3.  **难以预期的模型行为**: 后台会话静默丢失文本块 (#65051) 和模型生成未经用户确认的“思考块” (#95764) 等行为，降低了工具的可预测性，开发者希望模型能做到“言行一致”。
4.  **关键功能的缺失**: 单 Connector 绑定多账户 (#27302)、极简的自动补全快捷键方式（SHIFT+ENTER vs CTRL+J, #96198）等请求表明，现有功能在细节上的缺失正影响开发者的使用效率。

以上就是今日的 Claude Code 社区动态日报。我们将持续关注这些议题的进展，为你提供最前沿的信息。我们明天见！

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

好的，作为一名专注于 AI 开发工具的技术分析师，我将根据提供的 GitHub 数据，生成 2026-09-23 的 OpenAI Codex 社区动态日报。

---

# OpenAI Codex 社区动态日报 | 2026-09-23

## 今日速览
今日 Codex 社区动态频繁，核心聚焦于 **稳定性修复** 与 **新模型支持**。`rust-v0.156.0` 版本正式引入了全新的全屏 TUI 界面并默认启用了语音对话功能，提升了交互体验。同时，社区围绕 **Windows 平台的沙箱、应用崩溃等兼容性 Bug** 展开了激烈讨论，相关 Issue 热度极高。值得关注的是，官方 PR 表明 `GPT-6 Sol` 和 `GPT-6 Luna` 模型即将进入模型目录，为开发者带来更强的算力支持。

## 版本发布
**`rust-v0.156.0` 正式发布**
该版本带来了两个核心新特性：
- **全新全屏 TUI 界面**：通过 `/tui` 命令启动，支持语音/对话搜索、鼠标选择和右键复制功能，大幅提升了终端下的交互效率。
- **默认启用语音对话**：通过 `F8` 键即可开关，同时提供了 `/voice settings` 设置选择器，并集成了音频组件。

此外，多个 `0.157.0-alpha` 系列迭代版本（.3 至 .10）也已发布，表明团队正在快速推进下一个重大版本的开发和测试。

## 社区热点 Issues
以下是过去24小时内更新且社区讨论最为热烈的10个Issue：

1.  **[Bug] Chrome插件/浏览器/电脑使用功能无法与部分网站交互**
    - **Issue**: [#29343](https://github.com/openai/codex/issues/29343)
    - **重要性**: 该问题影响 Codex 的“代理”能力，会因安全策略检查而静默拒绝加载某些网站，导致自动化任务中断。社区 **33条评论** 表明该问题影响范围广，且用户反馈强烈。
    - **社区反应**: 用户详细报告了复现环境和预期行为，但官方尚未给出明确解决方案。

2.  **[RFC] 自进化代理：交互式指令蒸馏与规则代谢**
    - **Issue**: [#40575](https://github.com/openai/codex/issues/40575)
    - **重要性**: 一个极具前瞻性的构型，旨在解决长期代理任务中的“记忆遗忘”瓶颈。通过 `/learn` 功能让模型从交互中提炼指令并写入 `AGENTS.md`，实现自我进化。 **31条评论** 显示社区对此高级功能充满兴趣。
    - **社区反应**: 讨论围绕如何优雅地实现指令更新、防止规则冲突以及存储效率展开。

3.  **[Bug] Windows桌面更新后本地项目从侧边栏消失**
    - **Issue**: [#42739](https://github.com/openai/codex/issues/42739)
    - **重要性**: 严重影响 Windows 用户工作流。更新后，位于侧边栏的“Projects”列表变为空，虽有本地文件和聊天历史，但无法便捷访问项目。 **26条评论** 确认了大量用户受损。
    - **社区反应**: 用户提供了详细的环境信息和复现步骤，但尚未找到根本原因，社区期待官方紧急修复。

4.  **[Bug] Windows沙箱助手初始化失败**
    - **Issue**: [#44696](https://github.com/openai/codex/issues/44696)
    - **重要性**: 导致在 Windows 上，Codex CLI 的沙箱模式完全无法使用（`helper_unknown_error`）。**17条评论**，用户尝试了多种方法均无效，这对于依赖安全沙箱执行代码的用户是致命打击。
    - **社区反应**: 多人报告了相似问题，主要集中在 Windows 11 环境，怀疑是权限或沙箱版本兼容性问题。

5.  **[Bug] Windows应用卡在“完成 Windows 设置”界面**
    - **Issue**: [#32492](https://github.com/openai/codex/issues/32492)
    - **重要性**: 这是一个持续存在的“卡住”问题，导致新用户无法完成安装流程。**16条评论**，用户无法绕过此界面，且“重试”按钮无效，严重阻碍了入门体验。
    - **社区反应**: 用户尝试了各种清理和重装步骤，但问题依旧，对 Windows 新用户极不友好。

6.  **[Bug] 自定义模型提供商在桌面端无法使用**
    - **Issue**: [#29156](https://github.com/openai/codex/issues/29156)
    - **重要性**: 该 Issue 获得了 **35个 👍 (最高)**，说明社区对“自定义模型”支持的需求非常强烈。用户抱怨桌面端（相对于 CLI/TUI）使用第三方或本地模型时的体验极差，存在大量逻辑混乱和 Bug。
    - **社区反应**: 用户详细描述了桌面端的模式选择器、聊天历史和配置冲突等问题，强烈要求改进。

7.  **[Bug] 上下文压缩会永久破坏对话记录**
    - **Issue**: [#44363](https://github.com/openai/codex/issues/44363)
    - **重要性**: 严重的数据丢失问题。自动上下文压缩功能在重写存储时，可能意外清空整个对话记录。 **9条评论** 但影响极其严重，可能导致开发工作付之东流。
    - **社区反应**: 用户展示了代码和日志，证明了问题的存在，社区对此非常担忧，希望官方能将该功能设为“可选”或采用更安全的压缩策略。

8.  **[Bug] 桌面应用不再显示正在运行的命令**
    - **Issue**: [#37213](https://github.com/openai/codex/issues/37213)
    - **重要性**: 获得了 **22个 👍**，这是一个破坏核心透明度的回归性Bug。用户无法看到代理正在执行的具体命令，完全失去了对工作过程的掌控，严重影响信任度和可用性。
    - **社区反应**: 用户普遍认为这是个“非常糟糕的”体验，要求恢复之前的显示逻辑。

9.  **[Bug] 桌面应用 “发送”按钮在已有对话中保持禁用**
    - **Issue**: [#46986](https://github.com/openai/codex/issues/46986)
    - **重要性**: 高频率出现的UI Bug，用户无法在旧会话中继续对话。**5条评论** 但有多个用户报告（包括 #45885、#45626 等），表明这是一个广泛存在的界面状态同步问题。
    - **社区反应**: 用户找到了一个“切换到设置页面再切回”的临时复盖，但显然这不可接受。社区期待一个长久修复。

10. **[Bug] Windows应用隔空打开特定历史对话会导致App静默崩溃**
    - **Issue**: [#46995](https://github.com/openai/codex/issues/46995)
    - **重要性**: 最严重的Crash类型之一。打开单个特定会话会导致整个桌面应用无提示退出并自动重启，可能导致用户丢失当前的编辑内容。 **3条评论** 但问题本身非常严重。
    - **社区反应**: 报告者提供了详细的环境信息和日志，指出这与会话恢复有关，但官方尚未定位根因。

## 重要 PR 进展
1.  **[PR #47407] 在整个应用服务器请求中强制执行网络策略**
    - **链接**: [#47407](https://github.com/openai/codex/pull/47407)
    - **重要性**: 安全性和合规性的基础。确保所有通过应用服务器发起的请求都遵循配置的网络策略（如限制区域访问），防止策略绕过。

2.  **[PR #47411] 在嵌入式 Codex 启动过程中应用共享网络策略**
    - **链接**: [#47411](https://github.com/openai/codex/pull/47411)
    - **重要性**: 与 #47407 协同，将网络策略的控制范围扩大到了 TUI 和 `codex exec` 等启动阶段，形成完整的策略覆盖。

3.  **[PR #47405] [Hotfix] 将 GPT-6 Sol 和 Luna 添加到模型目录**
    - **链接**: [#47405](https://github.com/openai/codex/pull/47405)
    - **重要性**: 官方已开始为即将发布的 `GPT-6 Sol` 和 `GPT-6 Luna` 模型做准备。此 PR 将其加入模型目录，并更新了默认模型和迁移策略，预计将显著提升模型性能。

4.  **[PR #47401] [Hotfix 0.155] 为老版本添加 GPT-6 Sol 和 Luna 支持**
    - **链接**: [#47401](https://github.com/openai/codex/pull/47401)
    - **重要性**: 显示官方正在加速推进新模型的向下兼容支持，让使用旧版 CLI 的用户也能体验新模型。

5.  **[PR #47398] [Hotfix 0.155] 为登录和启动请求添加系统代理回退**
    - **链接**: [#47398](https://github.com/openai/codex/pull/47398)
    - **重要性**: 解决企业用户在复杂的网络环境（如必须使用系统代理）下无法登录或配置的问题，显著改善网络兼容性。

6.  **[PR #47399] 在全屏和叠加层中尊重 tmux 鼠标设置**
    - **链接**: [#47399](https://github.com/openai/codex/pull/47399)
    - **重要性**: 对终端用户的重要修复，防止 Codex 在 tmux 中不恰当地启用鼠标捕获，避免了与 tmux 鼠标操作的冲突。

7.  **[PR #47389] 在整个 HTTP 和 WebSocket 请求中强制执行网络策略**
    - **链接**: [#47389](https://github.com/openai/codex/pull/47389)
    - **重要性**: 进一步强化网络策略的覆盖面，确保在重定向、响应体和 WebSocket 等细节场景中也能有效阻止违规流量。

8.  **[PR #47393] 重试 OpenAI 文件上传操作**
    - **链接**: [#47393](https://github.com/openai/codex/pull/47393)
    - **重要性**: 增强了文件上传功能的健壮性，通过自动重试 `503` 或网络中断等瞬态错误，减少了因网络抖动而导致的上传失败。

9.  **[PR #47380] 路由 TUI 语音控制到应用**
    - **链接**: [#47380](https://github.com/openai/codex/pull/47380)
    - **重要性**: 优化了 `0.156.0` 新语音功能的控制逻辑，使快捷键和命令能正确地在不同会话间路由，提升多任务处理时的语音体验。

10. **[PR #47375] 添加本地 MXC 沙箱的 opt-in 偏好设置**
    - **链接**: [#47375](https://github.com/openai/codex/pull/47375)
    - **重要性**: 为 Windows 用户引入了一个新的沙箱选项。此 PR 添加了 `features.prefer_mxc` 配置项，允许用户在本地执行时选择 MXC 沙箱，为未来的性能和安全优化铺平道路。

## 功能需求趋势
从今日的 Issues 和 PR 中，可以提炼出社区最关注的三个功能方向：

1.  **新模型支持**：社区对 `GPT-6 Sol` 和 `GPT-6 Luna` 等新模型的引入表现出极大关注。多个 [hotfix] PR 正在积极将此支持反向移植到旧版本，表明官方也在快速响应这一需求。此外，用户期待自定义模型能获得更好的桌面端支持。
2.  **网络政策与企业级合规**：围绕 `network policy` 的多项 PR（#47407, #47411, #47389）集中出现，说明 Codex 正在加强对企业级安全、合规和网络限制场景的支持。这是产品迈向企业市场的重要一步。
3.  **Windows 平台稳定性**：本次日报中，超过一半的 Bug Issue 与 Windows 相关。这揭示了 Windows 用户群体对应用程序初始化、沙箱兼容性、UI 异常和全局崩溃等稳定性问题的迫切需求。

## 开发者关注点
开发者反馈的核心痛点和高频需求集中在：

- **Windows 兼容性是首要痛点**：沙箱失败、项目消失、启动卡死、GPU 崩溃等问题正严重阻碍 Windows 开发者的日常使用和入门体验。修复这些问题对留住 Windows 用户至关重要。
- **数据安全与透明度**：用户对 **“上下文压缩破坏对话记录”** ( #44363 ) 和 **“不显示运行命令”** ( #37213 ) 非常敏感。前者涉及数据安全，后者关乎工作透明度，两者都是开发者信任的基础。
- **对“代理”稳定性和可预测性的高要求**：浏览器自动拒绝、沙箱初始化失败等错误直接破坏了自动化工作流。开发者需要的是一个可靠、可预测的机器人，而不是一个需要时刻“调教”和“Debug”的实验品。

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

好的，各位开发者，早上好。这里是2026年9月23日（周三）的 Gemini CLI 社区动态日报。

---

## 今日速览

1.  **夜间版 v0.62.0 发布**：主要修复了环境代理解析和 ACP 模式下的工具调用顺序问题。
2.  **代理行为回归成为社区焦点**：大量 Issue 持续讨论子代理在极端情况下的错误汇报（如将“达到最大轮次”报告为“目标达成”）和主代理挂起等问题。
3.  **基础设施与安全特性更新密集**：多个 PR 聚焦于修复认证循环、优化长时任务的内存管理，以及提升 MCP（模型上下文协议）配置的鲁棒性。

---

## 版本发布

### v0.62.0-nightly.20260922.gd5b3e3acc

这是一个夜间版本，主要包含两项 Bug 修复：
- **修复**: 标准化了代理解析模块在环境代理解析中的构建互操作性问题。
- **修复**: 在 ACP 模式下，确保 `tool_call` 更新在 `request_permission` 之前发出，以优化请求流程。

[查看发布详情](https://github.com/google-gemini/gemini-cli/releases/tag/v0.62.0-nightly.20260922.gd5b3e3acc)

---

## 社区热点 Issues

1.  **#22323 [Bug] 子代理达到“最大轮次”后错误报告为“目标达成”**  
    **重要性**: 这是一个关键的逻辑错误。当子代理因轮次限制中断时，它本身并未完成目标，但系统却错误地报告成功，这会掩盖底层的性能或逻辑问题。社区反应强烈，是该类别下评论数最多的话题。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/22323)

2.  **#21409 [Bug] 通用代理挂起**  
    **重要性**: 用户报告`gemini-cli`在将任务委托给通用代理时会无限期挂起，甚至简单的操作（如创建文件夹）都无法完成。该问题获得了8个赞，表明这是一个影响范围较广的稳定性问题。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/21409)

3.  **#19873 [增强] 利用模型的 Bash 亲和力，实现零依赖 OS 沙箱**  
    **重要性**: 这是一个宏大的增强提案，旨在利用 Gemini 3 模型原生擅长 Bash 命令的特性，通过零依赖沙箱来安全且高效地执行代码和文件操作。这代表了 CLI 架构演进的一个重要方向，虽为前期设想，但讨论持续活跃。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/19873)

4.  **#22745 [特性] 评估 AST 感知文件读取、搜索和映射的影响**  
    **重要性**: 这个 EPIC（大型任务）旨在探索通过引入“抽象语法树”（AST）感知能力，来提高代码读取和导航的精确度，从而减少不必要的 Token 消耗和交互次数。这是提升 CLI 在大型代码库中性能的关键探索。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/22745)

5.  **#21968 [Bug] Gemini 不充分使用自定义技能和子代理**  
    **重要性**: 用户反馈，即使已经定义了 Gradle、Git 等相关的自定义技能，Gemini 也不会主动调用它们，除非用户明确指示。这暴露了代理在工具和技能选择上的智能性不足。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/21968)

6.  **#26525 [Bug] 为 Auto Memory 添加确定性编辑和减少日志**  
    **重要性**: 这是一个安全相关的问题。Auto Memory 功能在将内容发送给模型进行摘要前，并未可靠地对敏感信息进行编辑，这可能导致秘密泄露。社区持续关注数据隐私和安全性。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/26525)

7.  **#22267 [Bug] 浏览器代理忽略 `settings.json` 配置覆盖**  
    **重要性**: 用户发现浏览器代理无法正确读取项目或全局的 `settings.json` 配置（如 `maxTurns`）。这直接破坏了用户的自定义能力和工作流的可预测性。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/22267)

8.  **#24246 [Bug] 工具数量超过128个时返回400错误**  
    **重要性**: 当用户启用过多工具（超过400个）时，CLI 会直接报错。这表明需要一种更智能的机制来动态限定和选择当前任务所需的工具集。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/24246)

9.  **#21763 [Bug] 错误报告不提供子代理的上下文**  
    **重要性**: 当前`/bug`命令生成的报告仅包含主会话的上下文，而子代理内部发生的具体情况被遗漏，这严重影响了问题诊断和调试的效率。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/21763)

10. **#21335 [Bug] `/compress` 命令在会话恢复后不持久**  
    **重要性**: 用户运行`/compress`压缩聊天历史以节省 Token 后，一旦退出并恢复会话，历史记录又会恢复原样。这意味着压缩功能实际上是无效的，影响了长会话的管理。
    [查看 Issue](https://github.com/google-gemini/gemini-cli/issues/21335)

---

## 重要 PR 进展

1.  **#29443 [已合并] 支持 Gemini 3.8 Flash 与 3.5 Flash Lite 模型**  
    **重要性**: 这是一个重大的模型更新PR，将`gemini-3.8-flash`和`gemini-3.5-flash-lite`提升为最新的GA（正式发布）模型。这表明 Gemini CLI 正快速跟进其底层模型的版本迭代。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29443)

2.  **#29448 [开放] 修复身份认证无限循环**  
    **重要性**: 修复了在Windows、WSL等环境下，由于文件争用、无头环境密钥环等问题导致的无限认证循环。这是一个影响开发效率和体验的高优修复。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29448)

3.  **#29451 [开放] 限制工具输出大小并优化内存生命周期**  
    **重要性**: 针对长时间运行的代理任务，当工具调用（如运行大型测试）产生大量输出时，可能导致内存无限制增长。该 PR 通过限制输出来优化内存，是提升稳定性的关键举措。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29451)

4.  **#29452 [开放] 修复 IDE 集成中的 UI 冻结问题**  
    **重要性**: 修复了在 IDE 集成终端中使用时，按 `Enter` 确认工具（如应用更改）可能导致界面冻结的问题。这直接改善了在 IDE 环境下的用户体验。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29452)

5.  **#29445 [开放] 区分损坏的 MCP 配置与缺失的配置**  
    **重要性**: 当`mcp-server-enablement.json`文件损坏时，当前行为是“失败开放”，导致所有 MCP 服务被启用。该 PR 修复了这一问题，防止用户无意中暴露被禁用的工具，增强了安全性。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29445)

6.  **#29444 [开放] 修复 `gemini mcp enable/disable` 无法匹配服务器的问题**  
    **重要性**: 修复了 MCP 启用/禁用命令的逻辑错误，此前该命令无法成功执行任何操作。这是一个影响基础功能的严重Bug修复。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29444)

7.  **#29447 [开放] 为 SDK Agent Shell 添加环境变量和超时支持**  
    **重要性**: 该 PR 为 SDK 中的 `SdkAgentShell` 增加了传递 `env`、`timeoutSeconds` 以及外部 `AbortSignal` 的能力，使得通过 SDK 集成的自定义代理具备了更强的控制力。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29447)

8.  **#29449 [开放] 新增 `pkgdiet` 依赖检查技能**  
    **重要性**: 新增了一个内置技能，可以在执行 `npm install` 等命令前，自动通过 PkgDiet MCP 服务检查包的健康状态、大小和废弃情况，主动防止引入有问题的依赖。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29449)

9.  **#29402 [开放] 使持久化状态写入具备容错性**  
    **重要性**: 修复了因写入中断（如系统崩溃）导致 `state.json` 文件损坏并清空 CLI 状态的问题。通过原子写入和 `fsync` 确保了状态文件的完整性。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29402)

10. **#29237 [已合并] 修复信号终止的进程显示为 `Exit Code: null`**  
    **重要性**: 修复了一个小的 UI 问题，当后台进程被信号杀死时，不再显示不精确的 `(Exit Code: null)`，而是进行优雅处理。
    [查看 PR](https://github.com/google-gemini/gemini-cli/pull/29237)

---

## 功能需求趋势

1.  **代理行为优化与可靠性**：这是当前社区的第一大诉求。核心痛点包括：子代理在极端情况下的错误汇报、代理执行挂起、不主动使用技能和工具。用户期望代理能更智能、更稳定地自主完成任务。
2.  **安全与可靠性的增强**：与认证（无限循环）、MCP 配置（损坏后暴露工具）、Auto Memory（数据泄露）相关的修复和功能需求非常密集。社区对工具执行的安全性和数据隐私的关注度显著提升。
3.  **性能与 Token 优化**：通过引入 AST 感知进行精确文件读取、限制工具输出大小、实现“巧妙提取”逻辑等，社区强烈希望 CLI 能更“节省”地使用 Token，尤其是在处理大型项目时。
4.  **新模型与底层能力支持**：快速跟进 Gemini 3.8 Flash 等新模型的趋势很明显。同时，像“零依赖沙箱”这样的需求，体现了社区希望 CLI 能更深入地利用模型原生能力。
5.  **可观测性与易用性改进**：包括子代理轨迹的分享（`/chat share`）、配置文件被正确读取和遵循、设置持久化（如`/compress`）、以及文件路径的自动补全等，旨在提升开发者的使用和调试体验。

---

## 开发者关注点

1.  **代理“智能性”不足**：用户核心痛点在于，Gemini 代理的行为不够可靠和可预测。它要么挂起，要么在关键时刻犯错（如错误汇报），要么无法主动运用用户为其配置好的工具和技能。这导致开发者对代理的信任度下降。
2.  **配置的“意外”行为**：`settings.json` 被忽略、MCP 配置损坏导致工具被意外启用、认证配置失败导致循环等“反直觉”行为，严重干扰了开发者的工作流，并带来了安全风险。
3.  **长时任务的稳定性**：在进行大型代码库分析或长时间自动化任务时，内存问题和代理挂起是开发者最担心的痛点。内存泄漏和工具输出过载是主要的抱怨点。
4.  **浏览器代理的脆弱性**：浏览器代理在 Wayland 等特定环境下失败、忽略配置文件、锁定恢复机制不完善等问题，表明其健壮性有待提高。
5.  **缺乏有效的诊断手段**：当前的 `bugreport` 功能和日志系统无法提供足够的子代理内部细节，这使得当代理行为异常时，开发者几乎“无计可施”，难以定位和解决问题。

---
以上就是今日的日报。希望这些信息能帮助你更好地了解 Gemini CLI 社区的最新动态和开发方向。我们明天见！

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，我将根据您提供的 GitHub 数据，生成一份结构清晰的 2026-09-23 社区动态日报。

---

# GitHub Copilot CLI 社区动态日报 | 2026-09-23

## 今日速览

今天，社区发布了 **v1.0.89-0** 版本，正式支持 **Claude Opus 5.5**，并改进了 Connector 授权流程。然而，社区反馈的热点集中在多个严重的 **会话锁定（Session Wedge）** 和 **内存溢出（OOM）** 问题，以及长期运行后的 **认证失效** 问题。此外，一个关于 **WebSocket 响应** 的核心文档 PR 正在等待合并。

## 版本发布

-   **v1.0.89-0:**
    -   **Added:** 新增对 **Claude Opus 5.5** 模型的支持。
    -   **Improved:** 改进了受管理的 Connector 授权流程，现在会显示一个可复制的授权 URL，方便在连接和重新连接时使用。

-   **v1.0.88:**
    -   新增对 **Ghostty 和 WezTerm** 终端的可选 OSC 777 通知支持。
    -   修复了在底部锚定的对话框（如登录设备代码）中的文本选择问题。
    -   当托管配置刷新失败时，保留 `/allow-all` 设置，并记住对缺失路径的精确会话批准。

-   **v1.0.88-2:**
    -   **Fixed:** 修复了底部锚定对话框（包括登录设备代码）的文本选择问题。

## 社区热点 Issues

社区讨论焦点集中在稳定性、认证和内存问题上。

1.  **[#4438] Prompt 技能“失联”：禁用模型调用的技能无法使用**
    -   **重要性:** 高。这是一个设计上的根本性矛盾。项目技能即便`disable-model-invocation: true`标记为仅手动使用，但在 CLI 中完全不可用，违背了该功能的初衷。
    -   **社区反应:** 获得 9 个 👍，并有 7 条评论，说明影响范围较广，用户期望这种行为能被修复。
    -   **链接:** [Issue #4438](github/copilot-cli Issue #4438)

2.  **[#4929] 进程级认证令牌停止刷新，所有提示失败**
    -   **重要性:** 紧急。对于长时间运行的会话，这是致命的。用户必须重启进程才能恢复，这会中断所有工作流。
    -   **社区反应:** 这是一个新提交的 Issue，但评论数增长迅速，表明这是一个新出现且普遍存在的痛点。
    -   **链接:** [Issue #4929](github/copilot-cli Issue #4929)

3.  **[#4780] 会话压缩导致 OOM，进程永久不可恢复**
    -   **重要性:** 危急。当会话达到压缩阈值时，会陷入“压缩-崩溃”的死循环，导致`--resume`也无法恢复。这是对会话持久性的根本打击。
    -   **社区反应:** 获得 3 个 👍，评论明确指出了问题的严重性，用户和生产环境都可能因此丢失所有工作。
    -   **链接:** [Issue #4780](github/copilot-cli Issue #4780)

4.  **[#4755] 会话永久卡死：队列消息在轮次结束时导致空闲终止异常**
    -   **重要性:** 高。这是一个典型的并发状态错误。会话既非空闲也非运行中，不接受任何输入，唯一恢复方式是杀死进程。
    -   **社区反应:** 3 条评论，开发者正在分析状态机逻辑，可能是因为对“队列”和“空闲”状态的边界条件处理不当。
    -   **链接:** [Issue #4755](github/copilot-cli Issue #4755)

5.  **[#4946] 后台 Shell 命令完成后，`content[].thinking` 字段引发 HTTP 400 错误**
    -   **重要性:** 中。这是一个新提交的 Bug，揭示了在非标准轮次中插入系统通知可能破坏请求体结构的问题。
    -   **社区反应:** 刚刚创建（2026-09-23），已有 1 条评论，表明开发者已注意到此问题。
    -   **链接:** [Issue #4946](github/copilot-cli Issue #4946)

6.  **[#4919] `/ask` 命令在 auto 模式下无法工作**
    -   **重要性:** 中。这是核心交互功能失灵，会使用户无法在自动模式下进行临时询问。
    -   **社区反应:** 准确的 Bug 报告，虽评论不多，但指向了明确的模式切换逻辑问题。
    -   **链接:** [Issue #4919](github/copilot-cli Issue #4919)

7.  **[#4556] 服务端管理的 `extraKnownMarketplaces` 未注册，插件路径静默失败**
    -   **重要性:** 高。这是一个服务器配置与客户端行为的同步问题。服务器告知了额外的市场，但客户端忽略它，导致用户无法正确使用相关插件。
    -   **社区反应:** 收到 2 个 👍，评论指出了根本原因在于代码路径中遗漏了合并逻辑。
    -   **链接:** [Issue #4556](github/copilot-cli Issue #4556)

8.  **[#4840] BYOK 模式在 Copilot CLI 中不再支持 Deepseek**
    -   **重要性:** 高。这影响到大量使用 BYOK (自带密钥) 模式连接 Deepseek 等非官方模型的企业和高级用户，功能直接失效。
    -   **社区反应:** 获得 1 个 👍，报错信息清晰（`type: unknownvariant custom`），表明是对非标准模型响应格式的解析失败。
    -   **链接:** [Issue #4840](github/copilot-cli Issue #4840)

9.  **[#4900] 并发会话导致 `config.json` 中的 `trustedFolders` 丢失**
    -   **重要性:** 低到中。对于多会话用户是烦人的重复问题。每次退出都会用单个/旧的内存状态覆盖全局配置文件，导致信任的文件夹列表被 “吃掉”。
    -   **社区反应:** Bug 描述清晰，是典型的读写冲突问题，但影响相对较小。
    -   **链接:** [Issue #4900](github/copilot-cli Issue #4900)

10. **[#4486] 编辑权限请求“超时”**
    -   **重要性:** 中。对于长时间挂起会话或并行操作的用户，权限请求超时是一种糟糕的用户体验，迫使你必须在短时间内响应。
    -   **社区反应:** 2 个 👍，表明这是一个新引入的回归 bug，影响了用户的工作流。
    -   **链接:** [Issue #4486](github/copilot-cli Issue #4486)

## 重要 PR 进展

目前仅有 1 个 PR 在活跃更新中。

-   **[#4770] [OPEN] 记录 WebSocket 响应的退出机制**
    -   **功能/修复:** 文档更新。解释了当默认的 WebSocket 传输方式不可用或导致问题时（如网络封禁或 400 错误），用户如何通过配置主动退出，回退到传统 HTTP 长轮询模式。
    -   **为何重要:** 这是解决由 WebSocket 引起的网络兼容性问题的官方指南。等待合并可以让用户获得明确的故障排除方法。
    -   **链接:** [PR #4770](github/copilot-cli PR #4770)

**说明**: 根据今日数据，仅有 1 个 PR 在 24 小时内更新。这表明社区活动主要聚焦在 Issues 反馈的 Bug 上。

## 功能需求趋势

从今日的 Issues 中，可以提炼出以下社区关注的几个功能方向：

1.  **模型与服务支持**:
    -   **新模型快速接入:** 从 v1.0.89-0 支持 Claude Opus 5.5 可见，用户期望 CLI 能快速适配主流新模型。
    -   **自定义与 BYOK 模型兼容性:** Issue [4840] 表明，用户对 BYOK 功能的可靠性要求很高，需要保证对非 OpenAI 兼容 API (如 Deepseek) 的稳定支持。
    -   **模型端点自定义:** Issue [4003] 持续被讨论，用户希望像 VS Code 一样，支持在 CLI 中配置自定义模型端点，以便进行本地或私有模型测试。

2.  **会话稳定性与内存管理**:
    -   **解决 OOM 问题:** Issue [4780]、[4639] 显示，内存管理和会话压缩是重大痛点。社区需要更强大的 GC 机制和更稳健的压缩流程，避免进程崩溃。
    -   **修复会话挂起:** Issue [4755] 指明了会话状态机中的逻辑漏洞，用户期望 CLI 能够正确处理所有边缘情况，避免死锁。

3.  **MCP 与插件生态**:
    -   **插件发现与注册:** Issue [4556] 指出服务端管理的插件市场没有生效，社区希望服务端配置能与本地客户端行为完全同步。
    -   **插件启用/禁用:** Issue [2714] 仍然开放，用户渴望无需卸载即可快速切换插件的开关。

4.  **认证与权限**:
    -   **长期会话认证:** Issue [4929] 暴露了 token 刷新机制的不可靠性。社区需要一种无需重启进程的，能够优雅处理 token 过期的方案。

## 开发者关注点

综合上述信息，开发者在使用中也遇到了一些痛点，主要集中在：

1.  **频繁的崩溃与恢复困难:** 会话内存溢出（OOM）和挂起问题频发，特别是对于长时间运行或上下文复杂的任务。这直接打断了工作流且可能导致数据丢失。
2.  **认证的持久性问题:** 长期运行的会话（如过夜或跨天）会突然因 token 问题而失效，并且无法通过 `/login` 在原地恢复，只能被迫重启整个进程，这是高优先级的痛点。
3.  **管理状态冲突与丢失:** 多会话并发时，配置文件被不符合预期的覆盖（`config.json`丢失`trustedFolders`），这是一个常见的但十分扰人的协作/多任务问题。
4.  **BYOK / 自定义模型支持薄弱:** 当连接非标准 API 时（如 Deepseek），解析失败导致功能完全不可用，对使用自建或第三方模型的高级开发者影响很大。

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

# Kimi Code CLI 社区动态日报 — 2026-09-23

## 📌 今日速览  
- **版本迁移里程碑**：`kimi-cli`（Python 版）已归档，v1.52.0 将入口点重定向至新版 TypeScript 版本的安装器，用户可通过 `uv tool install kimi-cli` 平滑迁移。  
- **会话损坏 Bug 引关注**：社区报告 #2336 指出在内存压力下会话数据丢失，恢复时出现 `400 tool_call` 错误，影响编码流畅度。  
- **生态兼容性增强**：多个 PR 集成 OpenCode Go 主机的 `x-opencode-session` 头、修复 WebKit IME 回车提交问题，并批量升级 FastAPI、Rich、Ruff 等依赖。

---

## 🚀 版本发布

### `1.52.0` — 入口迁移版  
- **核心变更**：将 Python 版 `kimi-cli` 的入口点改造成“安装引导器”，自动引导用户安装新的 TypeScript 版 `kimi-code` CLI。此版本与仓库归档同步，确保 `uv tool install kimi-cli` 的用户无缝过渡。  
- **完整变更日志**：[v1.51.0...v1.52.0](https://github.com/MoonshotAI/kimi-cli/compare/1.51.0...1.52.0)

---

## 🔥 社区热点 Issues

### #2336 — [Bug] 内存压力下会话损坏：对话丢失 + 恢复时 tool_call 400 错误  
- **状态**：🟡 开放（更新于 2026-09-22）  
- **环境**：Linux, Kimi Code v1.43.0, `kimi-for-coding` 模型  
- **现象**：当系统内存紧张时，当前会话内容丢失，重新加载后发送 `tool_call` 请求返回 HTTP 400。  
- **社区反应**：2 条评论，尚未有解决方案或官方回复。该问题直接影响长时间编码用户的稳定性。  
- **链接**：[#2336](https://github.com/MoonshotAI/kimi-cli/issues/2336)

> ⚠️ 由于数据源仅包含该 Issue，请开发者及时关注并反馈补充信息。

---

## 📋 重要 PR 进展（共 8 条）

### 1. `#2667` [CLOSED] fix(web): guard IME composition Enter keydowns  
- **作者**：dvd233  
- **内容**：修复 WebKit 浏览器（如 Safari）在 CJK 输入法（IME）组合状态下，`Enter` 键可能被错误提交的问题。添加 `keyCode === 229` 防护。  
- **链接**：[#2667](https://github.com/MoonshotAI/kimi-cli/pull/2667)

### 2. `#2656` [OPEN] fix(llm): send x-opencode-session for OpenCode Go hosts  
- **作者**：FOWEPJF255  
- **内容**：为 `opencode.ai` 及子域名主机自动附加 `x-opencode-session` 头，解决 `openai_legacy` 模式下因缺失该头导致的 HTTP 400。  
- **链接**：[#2656](https://github.com/MoonshotAI/kimi-cli/pull/2656)

### 3. `#2666` [CLOSED] feat(cli): short-circuit entry points to a Kimi Code installer  
- **作者**：sailist  
- **内容**：发布 v1.52.0 的核心 PR，将 Python 包的入口点改为引导安装 TypeScript 版 CLI。  
- **链接**：[#2666](https://github.com/MoonshotAI/kimi-cli/pull/2666)

### 4. `#2664` [OPEN] chore(deps): bump agent-client-protocol from 0.8.0 to 0.12.1  
- **作者**：dependabot[bot]  
- **内容**：升级 agent-client-protocol Python SDK，包含多项协议改进。  
- **链接**：[#2664](https://github.com/MoonshotAI/kimi-cli/pull/2664)

### 5. `#884` [OPEN] chore(deps-dev): bump ruff from 0.14.14 to 0.15.0  
- **作者**：dependabot[bot]  
- **内容**：开发依赖 Ruff 代码检查工具版本升级至 0.15.0。  
- **链接**：[#884](https://github.com/MoonshotAI/kimi-cli/pull/884)

### 6. `#2665` [OPEN] chore(deps-dev): bump ruff from 0.14.14 to 0.16.8  
- **作者**：dependabot[bot]  
- **内容**：Ruff 进一步升级至 0.16.8（v0.15 → v0.16 跨版本更新）。  
- **链接**：[#2665](https://github.com/MoonshotAI/kimi-cli/pull/2665)

### 7. `#2663` [OPEN] chore(deps): bump rich from 14.2.0 to 15.0.0  
- **作者**：dependabot[bot]  
- **内容**：终端富文本库 Rich 升级至 v15.0.0，包含“So Long 3.8”等重大变更。  
- **链接**：[#2663](https://github.com/MoonshotAI/kimi-cli/pull/2663)

### 8. `#2662` [OPEN] chore(deps): bump fastapi from 0.128.0 to 0.141.1  
- **作者**：dependabot[bot]  
- **内容**：FastAPI 框架跨越多个版本升级至 0.141.1，修复若干漏洞并提升性能。  
- **链接**：[#2662](https://github.com/MoonshotAI/kimi-cli/pull/2662)

---

## 📊 功能需求趋势

从近期活动可提炼出社区关注的三个核心方向：

1. **跨平台/浏览器兼容性**  
   - 如 WebKit IME 回车间题修复（#2667），表明用户期望在 Safari 等非 Chrome 浏览器中获得一致体验。

2. **多后端/协议适配**  
   - `x-opencode-session` 头支持（#2656）显示社区对 OpenCode 等第三方托管平台的需求上升，希望 Kimi Code 能无缝集成。

3. **稳定性与恢复能力**  
   - 会话损坏 Bug（#2336）暴露了极低内存场景下的数据持久化缺陷，用户急需自动保存与稳健重连机制。

---

## 👨‍💻 开发者关注点

- **会话恢复可靠性**：Issue #2336 反映了内存压力下会话丢失的痛点，开发者在恢复时遭遇 400 错误，严重影响工作流。期望官方尽快定位根因并提供热修复。
- **依赖升级与兼容性**：多个 dependabot PR 显示项目正积极跟进 FastAPI、Rich、Ruff 等生态的最新版本，开发者需留意这些依赖变更是否引入 break change。
- **迁移路径清晰度**：v1.52.0 将入口重定向至 TypeScript 版，原 Python 版用户应关注 `kimi-code` 的安装方式、配置迁移及 API 变化，避免因版本切换导致使用中断。

---

*数据来源：[MoonshotAI/kimi-cli](https://github.com/MoonshotAI/kimi-cli) | 生成时间：2026-09-23*

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode 社区动态日报（2026-09-23）

## 今日速览

- **Windows ARM64 原生版 TUI 崩溃** 仍未解决，社区呼声最高（#19130，27 条评论），开发者正在定位 bun:ffi dlopen 问题。
- **多个配置静默失败缺陷集中曝光**：自定义 provider/model 因缺失 `tools` 能力字段被静默跳过（#49912、#50340），配置重载失败导致自定义 agent 丢失（#49982）。
- **Ollama 自动压缩过于激进**（#49965）和 **Kimi K3 reasoning 回放 bug**（#50232 已修复）成为今日修复重点。

---

## 社区热点 Issues（Top 10）

### 1. Windows ARM64 原生版 TUI 无法初始化
- **Issue #19130** | 评论 27 | 点赞 13  
- **链接**：https://github.com/anomalyco/opencode/issues/19130  
- **要点**：Windows 11 ARM64 上原生 OpenCode 二进制可执行非交互命令，但 TUI 因 `bun:ffi dlopen TinyCC error` 崩溃。社区反馈强烈，已获得最高关注度。

### 2. Ollama（openai-compatible）自动压缩在每次工具调用后无条件触发
- **Issue #49965** | 评论 6  
- **链接**：https://github.com/anomalyco/opencode/issues/49965  
- **要点**：本地模型通过自定义 provider 使用时，auto-compaction 在每次 tool-call 步骤后都运行，即使远未达到上下文限制，造成不必要的性能开销。

### 3. 服务端插件重载失败后静默丢弃自定义 agent 和命令
- **Issue #49982** | 评论 5  
- **链接**：https://github.com/anomalyco/opencode/issues/49982  
- **要点**：v2.0.9 桌面版后台服务在配置修改重载插件时抛出 `TypeError: pe is not a function`，之后自定义 agent 和命令全部丢失，直到下次重启服务。

### 4. 大文件 diff 导致 OOM 和 30GB 数据库
- **Issue #43551** | 评论 3  
- **链接**：https://github.com/anomalyco/opencode/issues/43551  
- **要点**：工作区内持续增长的日志文件（292MB+）被嵌入消息摘要，每次 `message.updated` 事件都会完整重新序列化，造成内存溢出和数据库膨胀。

### 5. 自定义 provider 因模型能力字段缺少 `tools` 被静默跳过
- **Issue #49912** | 评论 3  
- **链接**：https://github.com/anomalyco/opencode/issues/49912  
- **要点**：从 V1 迁移到 V2 的自定义 provider，模型只有 `modalities` 而没有 `tool_call` 能力，导致整个 provider 被无声跳过，且无明确错误提示。

### 6. 配置规范化诊断不指明错误字段，坏包 ID 静默丢弃整个 provider
- **Issue #50756** | 评论 3  
- **链接**：https://github.com/anomalyco/opencode/issues/50756  
- **要点**：日志中 `skipped malformed recognized value` 只输出 provider 根路径，不告知具体哪个字段出错，单个坏的 `package` id 会让整个 provider 及其下所有模型消失。

### 7. 桌面版新会话无响应：`prompt_async` 报 worktree 目录不存在
- **Issue #49561** | 评论 3 | 点赞 1  
- **链接**：https://github.com/anomalyco/opencode/issues/49561  
- **要点**：Windows 11 桌面版侧边栏点击“+ New session”创建新聊天后，发送消息无响应。日志显示 `FileSystem.realPath ENOENT` 指向缺失的工作树目录 `global/silent-knight`。

### 8. ACP `session/new` 目录忽略用户配置的自定义 provider、agent 和默认模型
- **Issue #50236** | 评论 3  
- **链接**：https://github.com/anomalyco/opencode/issues/50236  
- **要点**：自 v2.0.4 起，`opencode acp` 构建 `session/new` 目录时不加载用户配置，导致 Zed 等 ACP 客户端只能看到内置模型，丢失 Ollama 等自定义 provider。

### 9. 会话永久冻结：drain 失败仅记日志，不通知客户端
- **Issue #49740** | 评论 2  
- **链接**：https://github.com/anomalyco/opencode/issues/49740  
- **要点**：`SessionRunner.drain()` 失败被 catch 后只写日志，不触发 `session.error` 事件，客户端（TUI/下游）永远不知道会话已停滞。

### 10. TUI 插件无法读取当前选中模型/agent（仅能获取上次发送的值）
- **Issue #50315** | 评论 1  
- **链接**：https://github.com/anomalyco/opencode/issues/50315  
- **要点**：TUI 插件的 `state` 中缺少 `model`/`agent` 字段，插件无法在发送消息前显示当前选中的模型/agent，只能获取上次发送时的过期值。

---

## 重要 PR 进展（Top 10）

### 1. 支持 FreeBSD 源码构建
- **PR #48655** | 未合并  
- **链接**：https://github.com/anomalyco/opencode/pull/48655  
- **内容**：替换 `@ff-labs/fff-bun` 的静态导入为动态加载，解决 FreeBSD 上因 `os` 字段不包含 freebsd 导致 `bun install` 成功后 CLI 崩溃的问题。

### 2. TUI 显示 API 错误消息弹窗
- **PR #50778** | 未合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50778  
- **内容**：修复 MCP 服务器登录失败时 TUI 仍显示固定“Authentication failed”的问题，现在会将真实错误消息通过 toast 展示给用户。

### 3. 核心组件记录 MCP OAuth 与凭证失败的真实错误
- **PR #50767** | 已合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50767  
- **内容**：修正 `ErrorSummary.from` 对错误链的过度简化，使 MCP OAuth 和 credential 失败时的日志包含完整的错误类型和代码。

### 4. 降级损坏的 tool-result 内容而非崩溃
- **PR #50776** | 未合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50776  
- **内容**：`unsupportedParts` 和 `boundImages` 假设 `tool-result` 的 `value` 为数组，遇到非数组时直接崩溃；本 PR 将其降级为警告并跳过该部分。

### 5. 导出完整会话 transcript（Markdown/复制）
- **PR #50733** | 已合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50733  
- **内容**：修复 `/export` 命令和 transcript 复制只导出部分内容的问题，现在使用完整的服务端会话导出格式。

### 6. 前台任务在后台任务缺失时正确报错而非虚假完成
- **PR #50774** | 未合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50774  
- **内容**：当 `BackgroundJob` 注册表找不到前台子 agent 对应的后台任务时，父级 `TaskTool` 不再渲染虚假的 `completed` 结果，而是标记为失败。

### 7. 保留 Console 登录入口即使已存有 Zen API key
- **PR #50763** | 已合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50763  
- **内容**：修复从 v1 升级或持有 `opencode` API key 的用户，OpenCode Console 行在 Popular providers 中消失的问题，现在始终可见。

### 8. 等待服务完全关闭后再重启
- **PR #50042** | 未合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50042  
- **内容**：`Service.stop()` 不再将注册文件缺失视为关闭完毕，而是等待进程真正释放端口，避免重启时新进程与旧监听器冲突。

### 9. 修复 Kimi K3 reasoning 详情回放含 stream index 导致 400 错误
- **PR #50383** | 已合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50383  
- **内容**：在回放 reasoning_details 时剔除 streaming index，解决了 Kimi K3 在 coding-plan 会话的第二次请求中返回 400 的问题（对应 Issue #50232）。

### 10. 将 OpenAI 硬消费限制归类为配额耗尽而非限流
- **PR #50755** | 已合并  
- **链接**：https://github.com/anomalyco/opencode/pull/50755  
- **内容**：OpenAI 用 429 返回硬性消费限制，之前被误当作 rate limit 导致重试 10 次后才失败；现在直接失败并显示 provider 的错误消息。

---

## 功能需求趋势

从今日 Issue 中可以提炼出社区最关注的几个方向：

- **ARM64 / 跨平台原生支持**：Windows ARM64 原生 TUI 崩溃是当前最热 Issue，表明对 Apple Silicon 之外 ARM 平台的支持需求迫切。
- **配置系统的健壮性与可调试性**：多项 Issue 暴露配置静默跳过 provider、不指明错误字段、重载失败导致数据丢失等问题。社区期望配置验证能给出明确错误位置并保留原有配置。
- **自动压缩 (auto-compaction) 行为精细化**：Ollama 无条件触发压缩、空闲会话无法触发压缩（#50777）等，用户希望压缩策略可配置、可手动触发。
- **桌面端稳定性**：新会话无响应、模型自动切换、会话永久冻结等 Bug 频发，桌面版体验亟待提升。
- **TUI 插件能力扩展**：插件无法读取当前模型/agent（#50315）、主题 token 改名导致文本颜色丢失（#49922），表明第三方 TUI 扩展需求在增长。
- **语言与国际化**：波斯语 RTL 支持（#50747）、翻译覆盖 PR #50204 等，显示多语言社区活跃。
- **ACP (Agent Communication Protocol) 集成**：ACP 目录不加载用户配置（#50236），说明 ACP 客户端与 OpenCode 主配置的同步仍是痛点。

---

## 开发者关注点

- **配置静默失败**：是最频发的痛点。多个 Issue 均提到“silently skipped”、“no hint which field”，开发者急需更详尽的配置诊断信息。
- **会话数据丢失与膨胀**：OOM、数据库 30GB、预升级会话丢失（#49412）等问题显示数据持久化和压缩策略存在严重缺陷。
- **OAuth / 凭证处理**：HTTP Basic Auth 通过 query params 泄露（#50715）、无身份认证强制问题（#50721）、MCP OAuth 错误不透明等，安全和调试方面都需要改进。
- **模型/agent 选择混乱**：桌面版自动切换模型（#50769）、plugin 无法获取当前选择（#50315），影响多模型工作流。
- **服务重启与插件重载**：重载失败后自定义 agent 丢失（#49982），且只能在重启后恢复；服务重启时端口冲突（#50042）等，都影响持续运行场景。
- **FreeBSD 构建支持**：虽然是小众平台，但 PR #48655 说明社区有移植到其他 Unix 系统的需求。

---

*数据来源：GitHub anomalyco/opencode 仓库，截至 2026-09-23。*

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

好的，作为专注于 AI 开发工具的技术分析师，我已根据您提供的 GitHub 数据，为您生成了 2026-09-23 的 Pi 社区动态日报。

***

# Pi 社区动态日报 | 2026-09-23

## 今日速览

Pi 发布了里程碑版本 **v0.87.1**，正式支持包括 **Claude Opus 5.5、GPT-6 Sol** 在内的最新前沿模型。与此同时，社区围绕 **0.86.x 系列的多项严重回归 bug** 展开了激烈讨论，涉及 RPC 扩展处理、LiteLLM 代理兼容性等关键功能。文档与用户界面体验的精细化改进也成为今日 PR 合并的热点。

## 版本发布

### v0.87.1 正式发布

此版本的核心亮点是**支持最新的前沿模型**，使 Pi 能够利用 AI 领域的最新技术成果。

- **新模型支持**：现在可以通过支持的提供商（包括 GitHub Copilot）使用 Claude Opus 5.5、GPT-6 Sol 和 GPT-6 Luna。详情请参阅[选择模型文档](https://github.com/earendil-works/pi/blob/v0.87.1/packages/coding-agent/docs/models.md#select-a-model)。
- **默认模型更新**：默认模型已更新为 Grok 4.7。

## 社区热点 Issues

1.  **[#9843] [Bug] 0.86.x 回归：通过 LiteLLM 代理发送长请求时出现连接错误**
    -   **重要性**：高。此问题影响通过 **LiteLLM 代理**使用任何 OpenAI 兼容提供商（如 Ollama 或私有部署）的用户，属于 0.86.x 版本的明确回归。
    -   **链接**：[Issue #9843](https://github.com/earendil-works/pi/issues/9843)

2.  **[#9803] [Bug] 0.86.0 回归：RPC steer 成功无法与扩展处理的输入相关联**
    -   **重要性**：高。此问题破坏了 RPC 客户端的可靠性，使得无法判断 steer 操作是否成功触发了预期的扩展功能。
    -   **链接**：[Issue #9803](https://github.com/earendil-works/pi/issues/9803)

3.  **[#9549] [Bug] 全屏模式下，大文本会话导致严重性能问题**
    -   **重要性**：高。在大文本会话中使用全屏模式会导致**一个 CPU 核心满载**和严重的渲染卡顿，严重影响用户体验。
    -   **链接**：[Issue #9549](https://github.com/earendil-works/pi/issues/9549)

4.  **[#9052] [Bug] 全屏模式下滑轮滚动速度比常规模式慢 3 倍**
    -   **重要性**：中。全屏模式的滚动体验不佳，影响导航效率。该问题获得了社区 **6 个赞**，说明影响范围较广。
    -   **链接**：[Issue #9052](https://github.com/earendil-works/pi/issues/9052)

5.  **[#9652] [Bug] 因包含思考块，Anthropic Claude Fable 拒绝执行压缩操作**
    -   **重要性**：中。此 Bug 会使 `compact` 功能在 `claude-fable-5` 等模型上失效，影响长会话的管理。
    -   **链接**：[Issue #9652](https://github.com/earendil-works/pi/issues/9652)

6.  **[#9884] [Bug] 并发提供商模型可用性检查会相互取消，并静默替换默认模型**
    -   **重要性**：高。在启动时，多个并发的模型可用性检查（Availability passes）可能导致配置的默认模型被错误地替换，行为隐蔽且影响使用。
    -   **链接**：[Issue #9884](https://github.com/earendil-works/pi/issues/9884)

7.  **[#9929] [Bug] pi-coding-agent 0.86.0+ 导致特定 llama.cpp 模型崩溃**
    -   **重要性**：中。影响使用 `laguna-xs-2.1` 等特定本地模型的用户，阻碍了部分离线场景的使用。
    -   **链接**：[Issue #9929](https://github.com/earendil-works/pi/issues/9929)

8.  **[#9874] [Bug] 技能清单在系统提示中被静默忽略**
    -   **重要性**：中。当用户自定义工具名时，`buildSystemPrompt` 会错误地不向模型提供技能清单，影响模型对可用工具的理解。
    -   **链接**：[Issue #9874](https://github.com/earendil-works/pi/issues/9874)

9.  **[#9885] [Bug] 缺少 opencode-go 模型特定参数的 thinkingLevelMap**
    -   **重要性**：中。阻碍了用户通过 opencode-go 提供商使用 `muse-spark-*-contributor` 模型的高级思考（thinking）功能。
    -   **链接**：[Issue #9885](https://github.com/earendil-works/pi/issues/9885)

10. **[#9905] [Bug] Anthropic 的思考显示模式始终为 “summarized”，无法更改**
    -   **重要性**：低。用户无法控制思考过程的显示方式，缺乏灵活性。
    -   **链接**：[Issue #9905](https://github.com/earendil-works/pi/issues/9905)

## 重要 PR 进展

1.  **[#9934] feat: 添加 Yolo-Auto 提供商支持**
    -   **功能**：新增 `yolo-auto` 作为内置的 OpenAI 兼容订阅网关，支持运行时模型自动发现，扩展了 Pi 可用的模型生态。
    -   **链接**：[PR #9934](https://github.com/earendil-works/pi/pull/9934)

2.  **[#9908] fix: 修复 Fable 模型拒绝压缩问题**
    -   **关键修复**：此 PR 通过改变摘要提示的结构，解决了 `claude-fable-5` 模型拒绝 `/compact` 命令的问题（关联 Issue #9652）。
    -   **链接**：[PR #9908](https://github.com/earendil-works/pi/pull/9908)

3.  **[#9924] fix: 当硬件光标启用时不渲染虚拟光标**
    -   **功能优化**：此 PR 解决了在 Kitty 等终端中软件光标与硬件光标样式冲突的问题，改善了 TUI 的显示体验。
    -   **链接**：[PR #9924](https://github.com/earendil-works/pi/pull/9924)

4.  **[#9926] feat: 添加自定义提供商显示名称**
    -   **功能优化**：允许用户在 `models.json` 中为自定义提供商配置显示名称，并在状态栏中显示，提升界面友好度。
    -   **链接**：[PR #9926](https://github.com/earendil-works/pi/pull/9926)

5.  **[#9921] feat: 新增设置以禁用 /share 命令**
    -   **功能优化**：新增 `enableShareCommand` 设置，允许用户在项目或全局配置中禁用 `/share` 命令，满足部分用户的安全或隐私需求。
    -   **链接**：[PR #9921](https://github.com/earendil-works/pi/pull/9921)

6.  **[#9898] docs: 刷新文档，修复多个遗留问题**
    -   **关键修复**：一次大规模的文档更新，统一修复了 `PI_OFFLINE` 行为、RPC 文档、示例代码等多个用户报告的问题（关联 Issue #8684, #8717, #9205 等）。
    -   **链接**：[PR #9898](https://github.com/earendil-works/pi/pull/9898)

7.  **[#9920] fix: 避免在回放中发送空的 Codex 最终答案**
    -   **Bug 修复**：修复了 Codex 提供商有时会返回空字符串作为最终答案，导致后续请求失败的问题（关联 Issue #9918）。
    -   **链接**：[PR #9920](https://github.com/earendil-works/pi/pull/9920)

8.  **[#9914] fix: 修复无法移除本地路径安装的包**
    -   **Bug 修复**：修复了 `package remove` 命令无法移除通过相对本地路径安装的扩展包的问题。
    -   **链接**：[PR #9914](https://github.com/earendil-works/pi/pull/9914)

9.  **[#9907] fix: 回放时跳过空白工具调用名称**
    -   **Bug 修复**：修复了某些模型返回空名称的 tool call 导致 Pi 回放失败的问题，提升了 Pi 的鲁棒性。
    -   **链接**：[PR #9907](https://github.com/earendil-works/pi/pull/9907)

10. **[#9902] fix: 在切换模型时保持思考级别设置**
    -   **Bug 修复**：修复了切换模型后用户手动设置的思考级别（thinking level）会被重置为默认值的问题。
    -   **链接**：[PR #9902](https://github.com/earendil-works/pi/pull/9902)

## 功能需求趋势

1.  **前沿模型集成**：v0.87.1 对 GPT-6 和 Claude Opus 5.5 的支持是社区最强烈的呼声，也是本周期的核心主题。这包括模型本身的集成（见 Issue #9917 更新 Claude Code 版本），以及对新模型特有功能（如 Anthropic Thinking）的适配。

2.  **扩展 API 完善**：社区强烈要求扩展 API 能提供对**模型原生响应字段**（Issue #9784）和**流式事件**（PR #9901）的访问能力，以支持更复杂、更定制化的功能开发。

3.  **性能与稳定性**：0.86.x 版本引入的多项回归问题（如 RPC 扩展处理、LiteLLM 代理兼容性）将稳定性推至社区关注的顶点。同时，UI 性能（尤其是全屏模式下）的优化需求持续存在。

4.  **精细化配置与控制**：用户希望获得更多控制权，包括：`PI_OFFLINE` 的预期行为（Issue #8684）、压缩触发策略（Issue #9904）、以及思考模式的显示控制（Issue #9905）。

## 开发者关注点

-   **0.86.x 回归问题**：当前开发者反馈中最主要的痛点是 **0.86.x 系列的稳定性回归**。特别是通过 LiteLLM 代理和 RPC 接口使用的用户，更新意愿受到严重打击。这与 v0.87.1 积极引入新功能形成了对比。
-   **文档与实际行为不符**：`PI_OFFLINE` 环境变量的作用范围超出文档描述（Issue #8684），是近期社区反馈的高频错误点。好在 PR #9898 已经专门解决了此问题。
-   **会话数据管理**：关于会话文件解析效率（Issue #9820）和元数据条目导致会话截断（Issue #9930）的问题，表明开发者对 `session-manager` 的健壮性和性能感到担忧。
-   **代码示例与文档错误**：多个 Issues 指出代码示例和文档存在错误（Issue #9205, #9358），表明开发者对开发者体验（Developer Experience）的看重，以及对准确、可用的入门文档的渴求。

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code 社区动态日报 | 2026-09-23

## 今日速览

- **v0.24.5-preview.0 发布**，主要修复了 deferred-tool bridge 的文档与实现问题，并记录 CI 测试计划。
- **社区活跃度持续高涨**：过去 24 小时累计更新 Issue 50 条、PR 50 条，其中多个 P1/P2 级别 Bug 和功能提案引起广泛讨论，尤其集中在剪贴板、MCP 集成、会话管理及沙箱安全领域。
- **两项关键 PR 进入合并**：`desktop-v0.24.4` 桌面端新版本已发布，修复了 review 模块的覆盖率问题；`v0.24.4` 核心版本加入了监控工具的系统提示引导。

---

## 版本发布

### v0.24.5-preview.0
- **修复**：纠正 deferred-tool bridge 导致的过时或未测试的代码（@yiliang114, PR #12355）
- **文档**：记录 CI 测试计划（docs(plans)）

### v0.24.4
- **特性**：向系统提示中加入监控工具（monitor tool），用于指导模型行为（@yilian, PR #12408）
- **无 Breaking Changes**

### desktop-v0.24.4 (Qwen Code Desktop)
- **修复**：review 模块中未计划的 chunks 不再计入覆盖率，且从计划中读取分母（@wenshao, PR #12370）
- 其他修复与改进

> 此外，`v0.24.4-nightly.20260922` 和 `v0.24.3-nightly.20260922` 也同步发布，包含 deferred-tool bridge 修复及 daemon 批处理工作空间等功能。

---

## 社区热点 Issues（10 条）

### 1. RFC：可靠的自动记忆召回 — 时序、质量与遥测  
**#7040** [CLOSED]  
长达三个月的讨论，涉及召回投递遥测、确定性快速路径、多语言评估等设计。虽然已关闭，但其架构影响深远。  
[链接](https://github.com/QwenLM/qwen-code/issues/7040)

### 2. 提案：定义托管 Agent 双路径架构及分阶段交付  
**#12380** [OPEN] 10 条评论  
提出保持现有 TypeScript Agent 循环，独立运行模型推理与工具环境，并赋予 Session 持久所有权、可恢复的工具执行等功能。社区正在热烈讨论其必要性。  
[链接](https://github.com/QwenLM/qwen-code/issues/12380)

### 3. TUI 在手机软键盘 / Termux 下吃掉一行转录  
**#12449** [OPEN] 10 条评论  
用户汇报终端 UI 在行数收缩时丢失内容，与上游 ink 7.0.3 的 rows-shrink 缺陷相关。影响移动端用户。  
[链接](https://github.com/QwenLM/qwen-code/issues/12449)

### 4. workflow 关键词桥接工具被 CodeModeOnly 隐藏  
**#12425** [CLOSED] 8 条评论  
`ToolMode.CodeModeOnly` 下隐藏了桥接工具，导致工作流无法引用。已快速修复。  
[链接](https://github.com/QwenLM/qwen-code/issues/12425)

### 5. 追踪：工具执行沙箱设置加固  
**#12417** [OPEN] 7 条评论  
Linux bubblewrap 沙箱转移到单独工具执行后经过五轮审查，仍有待完成的边界安全加固，社区持续关注。  
[链接](https://github.com/QwenLM/qwen-code/issues/12417)

### 6. 会话创建结果在 HTTP 网关超时时丢失  
**#12381** [OPEN] 7 条评论  
`POST /session` 成功后若网关返回超时，客户端无法获得 session ID，后续操作无从下手。社区建议增加重试和凭据恢复机制。  
[链接](https://github.com/QwenLM/qwen-code/issues/12381)

### 7. Linux/WSL 剪贴板粘贴静默失败（缺 wl-paste / xclip）  
**#12488** [OPEN] 6 条评论  
Ctrl+V 粘贴图片或文本无任何反馈。用户呼吁增加错误提示和 fallback（如 WSL 内调用 powershell.exe）。  
[链接](https://github.com/QwenLM/qwen-code/issues/12488)

### 8. 捆绑引用路由无法感知代理工具策略  
**#12424** [OPEN] 5 条评论  
技能拒绝的子代理收到无法使用的指针。设计缺陷在于路由决策未考虑 per-agent 策略，社区期望更细粒度的权限控制。  
[链接](https://github.com/QwenLM/qwen-code/issues/12424)

### 9. 超大 `available_commands_update` 通知导致频道断开  
**#11908** [OPEN] 5 条评论  
JSON 节点数超过 10000 时 ACP 桥直接杀掉子进程，后续所有请求返回 404。影响大规模环境。  
[链接](https://github.com/QwenLM/qwen-code/issues/11908)

### 10. `maxParallelAgentsByModel` 对前台 Agent 无效  
**#12470** [OPEN] 3 条评论  
用户设定模型并发限制后，技能可以绕过限制发起多个请求，导致本地模型 OOM。社区要求修复此限制逻辑。  
[链接](https://github.com/QwenLM/qwen-code/issues/12470)

---

## 重要 PR 进展（10 条）

### 1. docs(verify-pr): 增加持久状态、稳态和跳过覆盖率规则  
**#12456** [OPEN]  
为 review 技能增加四项验证技术，提升 CI 可靠性。这些规则来自一次实际审查报告，具有实践指导意义。  
[链接](https://github.com/QwenLM/qwen-code/pull/12456)

### 2. feat(cli): 添加受管运行时证明工作器  
**#12506** [OPEN]  
新增隐藏命令 `qwen managed-runtime-worker`，启动最小证明运行时，不加载普通 CLI 栈。未来可用于安全启动和远程验证。  
[链接](https://github.com/QwenLM/qwen-code/pull/12506)

### 3. fix(ui): 短 VP 内容底部对齐，空白位于顶部  
**#9305** [OPEN]  
修复 VP 模式下对话内容与输入框之间的空白区域，提升视觉舒适度。  
[链接](https://github.com/QwenLM/qwen-code/pull/9305)

### 4. feat(web-shell): 管理仓库的工作树（Worktrees）  
**#12154** [OPEN]  
在 Web Shell Git 对话框中新增 “Worktrees” 标签页，列出所有工作树，支持分支、锁状态、缺失目录等。  
[链接](https://github.com/QwenLM/qwen-code/pull/12154)

### 5. fix(mcp): 支持更大的 App、作用域工具调用及隔离来源  
**#12258** [OPEN]  
扩展 MCP 对大型应用的支持，引入作用域工具调用和来源隔离，提升安全性。已通过远程 HTTPS 渲染器验证。  
[链接](https://github.com/QwenLM/qwen-code/pull/12258)

### 6. feat(serve): 支持在创建会话时选择模型和推理设置  
**#12308** [OPEN]  
外部调用者可通过 `startupConfig.modelServiceId` 和 `reasoningEffort` 指定模型与推理强度，增强 API 灵活性。  
[链接](https://github.com/QwenLM/qwen-code/pull/12308)

### 7. fix(cli): 剪贴板不可用时显示 Linux 特定提示信息  
**#12507** [OPEN]  
修复 #12504，针对 Linux 环境给出更准确的诊断（缺 wl-clipboard / xclip / 无显示服务器）。  
[链接](https://github.com/QwenLM/qwen-code/pull/12507)

### 8. fix(acp-bridge): 降级遗留 `file://` 发布记录为 ephemeral  
**#12473** [OPEN]  
修复 #12389：工具发布的本地位文件不应被标记为 restorable，否则恢复时失败。现在写时强制转为 ephemeral，读时静默丢弃。  
[链接](https://github.com/QwenLM/qwen-code/pull/12473)

### 9. test(core): 在单元层面固定 CodeModeOnly 桥接行为  
**#12497** [OPEN]  
为之前修复的工作流桥接添加直接单元测试，防止回归。代码覆盖更健壮。  
[链接](https://github.com/QwenLM/qwen-code/pull/12497)

### 10. feat(extensions): 从目录加载部署管理的扩展  
**#12183** [OPEN]  
新增 `--managed-extensions` 参数，允许部署方直接控制扩展目录，无需修改用户 home。  
[链接](https://github.com/QwenLM/qwen-code/pull/12183)

---

## 功能需求趋势

1. **多 Agent / 多会话管理**：多个 Issue 和 PR 涉及 Managed Agent 架构、会话持久化、后台 Agent 暴露（#12380, #11908, #10954）。社区期待更强大的会话路由与恢复能力。
2. **剪贴板与移动端体验**：Linux/WSL 剪贴板问题（#12488, #12504, #12503）以及 TUI 在手机端的布局缺陷（#12449）显示移动和跨平台使用率快速上升。
3. **安全与沙箱加固**：工具执行沙箱（#12417）、MCP 图像大小边界（#12471）、git commit --amend 豁免死代码（#12460）等表明安全性是当前重点。
4. **MCP 与浏览器集成**：MCP 客户端对只工具服务器的兼容性（#12496）、WebBridge 浏览器控制（#8699）持续被提及，MCP 生态扩展需求旺盛。
5. **IDE 集成**：VS Code 伴侣插件消息编辑失败（#12501），以及 Chrome Extension 复兴提案（#5626），表明社区渴望更紧密的编辑器集成。

---

## 开发者关注点

- **反馈高发痛点**：
  - 静默失败（剪贴板、LSP 诊断、MCP 协议错误）是用户最不满的问题，多次被标记为 P2/P3。
  - 会话超时后无法恢复（#12381）影响工作流连续性。
  - 模型并发限制失效（#12470）导致本地开发体验严重下降。
- **高频需求**：
  - 更完善的错误提示（#12488 要求增加 fallback 提示，#12504 要求区分原因）。
  - 单元测试覆盖与 CI 可靠性（#12456, #12497 关注测试规则与持久状态）。
  - 平台/桌面端一致性（#12453 左侧边栏对齐，desktop-v0.24.4 专门修复 review 界面）。
- **社区参与度高**：多数 P2 级别 Issue 在24小时内获得5~10条评论，PR 审查活跃，尤其 `@yiliang114`、`@wenshao`、`@doudouOUC` 贡献突出。

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

好的，作为一名专注于AI开发工具的技术分析师，以下是为您生成的2026-09-23 DeepSeek TUI（Codewhale）社区动态日报。

---

# 🚀 Codewhale 社区动态日报 | 2026-09-23

---

## 📰 今日速览

1.  **品牌重塑全面落地**：`v0.10.0` 正式发布，标志着项目从 `deepseek-tui` 全面转型为 **Codewhale**，旧 npm 包已废弃。
2.  **架构重构持续深入**：社区围绕“代码拆分”、“MCP客户端统一”、“配置层简化”等核心议题展开激烈讨论，反映了项目在快速迭代中对代码质量和架构清晰度的追求。
3.  **新客户端与新模型支持**：Chromewhale Chrome 扩展 PR 合入，同时新增 Yolo-Auto 模型网关支持，生态扩展步伐加快。

---

## 📦 版本发布

### Codewhale v0.10.0

-   **核心**：作为 Shannon Labs 的公共产品，**Codewhale** 正式成为项目主名称。旧的 `deepseek-tui` npm 包已被弃用，不再接收更新。所有新的命令行、npm 包和发布构件均统一使用 `codewhale` 标识。
-   **影响**：标志着项目品牌和技术栈的彻底独立，用户需迁移至新的 Codewhale 生态。
-   **查看详情**：[v0.10.0 Release](https://github.com/Hmbown/Codewhale/releases/tag/v0.10.0) (注意：原数据链接指向issue，Release 链接为推测，请以实际为准)

---

## 🔥 社区热点 Issues（Top 10）

1.  **#6011** [增强] **TUI 使用量与工具诊断** —— 社区对“Token会计”功能呼声很高，要求按组件、模型、缓存命中率、工具调用进行成本统计。
    -   **重要性**：直接关系到用户对模型使用成本和效率的感知，是提升TUI专业度的关键指标。
    -   **社区反应**：9条评论，讨论活跃，但暂无官方采纳标记。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/6011)

2.  **#5586** [重构] **拆分巨型文件** —— 开发者 `Hmbown` 发起的架构清理，直指 `lib.rs` (18.7k行)、`config.rs` (12.3k行) 等代码文件过大，严重影响可维护性。
    -   **重要性**：反映出项目在快速发展中积累的技术债务，拆分是提升开发效率和代码健壮性的必经之路。
    -   **社区反应**：8条评论，各方认可重构必要性，讨论聚焦于拆分方案。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/5586)

3.  **#6142** [清理] **统一两套 MCP 客户端栈** —— 核心问题：TUI（`tui/src/mcp`）和引擎（`crates/mcp`）中存在两套独立、功能重复的 MCP 客户端代码，导致混乱。
    -   **重要性**：MCP协议是Codewhale连接外部工具的核心。代码冗余意味着潜在的不一致性和维护负担。
    -   **社区反应**：5条评论，开发者承认这是 `0.9.14` 重构任务，社区期待统一方案的落地。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/6142)

4.  **#6050** [增强] **可插拔代理记忆** —— 社区成员 `idling11` 提出为代理记忆系统引入通用后端接口，支持 `causal-memory` / `mem0` 等第三方实现。
    -   **重要性**：这是提升代理智能化水平的核心特性。当前硬编码的记忆方案限制了灵活性和未来的进化能力。
    -   **社区反应**：5条评论，讨论热烈，社区对模块化、可替换的记忆后端需求强烈。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/6050)

5.  **#6036** [Bug] **“舰队”与“代理”概念混淆** —— 开发者指出 `fleet` 和 `agent` 在存储层存在冗余，且角色、模型绑定、路由书签混为一谈。
    -   **重要性**：核心数据模型设计的混乱会直接影响用户体验，增加学习成本。
    -   **社区反应**：5条评论，包括首席创始人（Founder）的困惑评论，凸显问题的严重性和解决的紧迫性。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/6036)

6.  **#6086** [增强] **统一会话草稿本与三大存储** —— 目标是将工作区输出、草稿本文件和 Agent Mail 合并到一个统一的地址方案下。
    -   **重要性**：此特性旨在打破信息孤岛，让代理间的协作和上下文传递更加流畅。
    -   **社区反应**：4条评论，被认为是关键的基础设施改进，直接影响多代理工作流的易用性。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/6086)

7.  **#5915** [增强] **舰队模型管理：从提供商到角色** —— 提出一个完整的流程：选择提供商 → 挑选模型 → 创建候选名单 → 分配角色。这是一个系统性的多模型管理方案。
    -   **重要性**：直击多代理场景下模型选择的痛点，是“舰队”功能成熟的关键一步。
    -   **社区反应**：4条评论，反映了社区对更精细、流程化的多模型管理能力的渴望。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/5915)

8.  **#5479** [增强] **TUI中的子代理和Workflow管理** —— 要求在TUI中提供对子代理的实时监控、状态查看、操作控制和历史记录。
    -   **重要性**：是 Codewhale 多代理功能可视化的核心界面需求，让用户能像操作操作系统任务管理器一样管理子代理。
    -   **社区反应**：3条评论，被认为是提升用户体验的“杀手级”功能。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/5479)

9.  **#4955** [增强] **请求：本地开发的零沙箱模式** —— 开发者 `eugenicum` 抱怨内核级沙箱破坏了日常开发环境，请求提供 `--no-sandbox` 选项。
    -   **重要性**：沙箱虽然增强了安全性，但对开发者日常使用造成了严重障碍。
    -   **社区反应**：5条评论，1个 👍。该问题反映了安全性与开发效率之间的典型冲突，社区对提供配置选项的需求明确。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/4955)

10. **#6280** [增强] **升级 MCP 协议至 2026-07-28 规范** —— 当前 Codewhale 的 MCP 客户端还停留在旧版协议，无法与新版 MCP Server 交互。
    -   **重要性**：MCP是核心能力，协议落后意味着无法使用最新的工具和服务，是必须解决的兼容性问题。
    -   **社区反应**：2条评论，是修复技术债和保持兼容性的必要动作。👉 [查看详情](https://github.com/Hmbown/Codewhale/issue/6280)

---

## 📬 重要 PR 进展（Top 10）

1.  **#6404** [修复] **向原生客户端暴露用户自定义提供商路由** ✅ 已关闭
    -   **功能**：修复了 `[providers.<name>]` 路由对原生客户端不可见的问题。现在，无论TUI还是其他原生客户端，都能使用用户自己配置的提供商。
    -   **影响**：这是一项关键的API修复，确保了所有客户端体验的一致性。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6404)

2.  **#6398** [功能] **新增 Chromewhale：Chrome 侧边栏客户端** ✅ 已关闭
    -   **功能**：全新的 Manifest V3 Chrome 扩展，允许用户在浏览器侧边栏内直接与本地 Codewhale 运行时交互，并拥有五个操作浏览器Tab的工具。
    -   **影响**：极大地扩展了 Codewhale 的使用场景，推动了“AI原生浏览器助手”的愿景。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6398)

3.  **#6408** [功能] **新增 Yolo-Auto 兼容主机** 🔄 开放中
    -   **功能**：添加了 Yolo-Auto（一个统一费率的OpenAI兼容网关）作为数据驱动的兼容主机描述，无需新增 `ProviderKind`。
    -   **影响**：快速、零成本地扩展了模型来源，对用户友好。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6408)

4.  **#6406** [修复] **阻止恢复和分叉操作导致会话/线程重复** 🔄 开放中
    -   **功能**：修复了两个身份Bug：恢复已打开的会话会创建重复线程；并修复了可能的类似问题，确保了会话与线程关系的一致性。
    -   **影响**：直接提升客户端数据一致性，修复了令人困惑的UI Bug。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6406)

5.  **#6402** [重构] **移除未使用的功能阶段和全局允许声明** ✅ 已关闭
    -   **功能**：清理代码，移除了 `features.rs` 中未使用的 `Stage::Deprecated` 和 `Stage::Removed` 变体及相关代码。
    -   **影响**：代码清理，提升了代码质量和可读性。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6402)

6.  **#6405** [功能] **`docs/work` 词典化 🤝 #5337** ✅ 已关闭
    -   **功能**：将 `docs/work` 页面的静态字符串移至统一的 i18n 词典文件中，规范化了国际化支持。
    -   **影响**：为网站后续的多语言支持打下基础。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6405)

7.  **#6400** [修复] **处理命名空间下的模型目录条目** ✅ 已关闭
    -   **功能**：修复了仅存在于 `catalog.models` 命名空间下的模型无法出现在可选列表中的问题。
    -   **影响**：确保了所有注册模型都能被用户发现和使用。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6400)

8.  **#6399** [CI] **为 `load_skill` 功能重新固定运行时合约预算** ✅ 已关闭
    -   **功能**：修复了因新功能 `load_skill` 导致的主CI流水线检查失败，重新调整了合约预算。
    -   **影响**：确保了CI/CD流程的稳定和畅通。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6399)

9.  **#6395** [修复] **阻止外来遗留 `base_url` 影响路由端点** ✅ 已关闭
    -   **功能**：修复了遗留的 `base_url` 错误地覆盖了用户定义的路由端点的问题，例如修复了使用小米MiMo时因继承了DeepSeek的`base_url`导致的认证失败。
    -   **影响**：直接解决了用户配置互操作性问题。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6395)

10. **#6392** [修复] **八个自测修复** ✅ 已关闭
    -   **功能**：一个集合性PR，包含了8个通过自测发现的Bug，涵盖了UI、权限、功能开关等多个方面。
    -   **影响**：体现了项目团队积极进行内部测试并快速修复问题的作风。👉 [查看详情](https://github.com/Hmbown/Codewhale/pull/6392)

---

## 📊 功能需求趋势

*   **架构清理与代码质量**：要求拆分巨型文件、统一重复代码栈（如MCP客户端、配置层）的呼声最高。这反映出项目在快速增长后，社区希望其走向更专业、可持续的代码治理模式。
*   **多代理与工作流可视化**：`Fleet`、`Agent`、`Sub-agent` 相关的Issue和PR数量多、讨论深。社区渴望在TUI中获得类似“任务管理器”式的可视化和管理能力，而非黑盒运行。
*   **模型与提供商管理的灵活性**：从“可插拔记忆”到“模型候选名单”再到“新网关支持”，社区强烈希望Codewhale具备高度模块化和可配置的模型生态，能够自由组合不同模型的能力和成本。
*   **协议标准跟随与兼容性**：升级MCP协议、修复OpenRouter等API兼容性问题，表明社区用户需要Codewhale能与外部成熟生态无缝对接，而非孤立运行。
*   **国际化（i18n）**：随着中文社区Issue（如#2342、#2323）和中文本地化PR（#6401）的涌现，国际化支持，特别是中文支持，已成为明确的社区需求。

---

## 🧐 开发者关注点

*   **开发体验痛点**：
    *   **沙箱模式**：内核级沙箱破坏了日常开发命令（#4955），开发者强烈要求提供本地开发的 `--no-sandbox` 解禁模式。
    *   **中文输入法兼容性**：Issue #2323 详细描述了在TUI中使用中文输入法时出现的各种UI问题，对中文开发者体验不佳。
    *   **代码可维护性**：巨型文件（#5586）、重复代码（#6142）是开发者社区的“眼中钉”，是影响贡献热情的关键因素。
*   **功能性痛点**：
    *   **编辑工具锚定失败**：Issue #6203指出 `edit_file` 工具常因文本匹配失败而浪费数次交互，开发者希望引入基于AST的符号定位来根本解决。
    *   **运行时性能**：Issue #6193直言项目根本没有运行时性能基准和门控，开发者对“用户路径速度”缺乏保障感到担忧。
    *   **数据模型混乱**：`Fleet`和`Agent`概念的混淆（#6036）让开发者感到困惑，表明核心数据模型的设计需要重新审视和简化。

</details>

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*