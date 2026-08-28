# AI 开源趋势日报 2026-08-28

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-08-28 06:19 UTC

---

# AI 开源趋势日报 – 2026-08-28

## 1. 今日速览

今日 GitHub AI 开源社区展现出三个显著动向：**Agent 技能生态爆发式增长**，多个以 Claude Code 为基座的“技能库”项目（如 `archify`、`scientific-agent-skills`、`ponytail`）单日收获数千 Star，标志着开发者从“用 Agent”转向“定制 Agent 行为”；**RAG 与知识图谱融合加速**，`Graphify` 以 111k+ Star 位列主题搜索前列，`LEANN` 等压缩方案将存储成本降低 97%，推动个人设备端 RAG 实用化；**AI 视频/设计工具进入开源深水区**，`OpenMontage` 和 `awesome-gpt-image-2` 分别以 1292 和 2096 的日增 Star 成为热门，昭示着生成式 AI 从文本向多模态落地的进程。

---

## 2. 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、开发工具、CLI）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [ollama](https://github.com/ollama/ollama) | ⭐179,600 | 本地运行大模型的一站式工具，支持 Kimi、GLM、DeepSeek 等最新模型，社区标杆。 |
| [transformers](https://github.com/huggingface/transformers) | ⭐164,534 | Hugging Face 核心库，统一 API 加载数千种预训练模型，是 AI 开发者的基础设施。 |
| [headroomlabs-ai/headroom](https://github.com/headroomlabs-ai/headroom) | ⭐67,858 | 压缩工具输出、日志、RAG 块，使代码 Agent 减少 20% token，JSON 减少 60-95%。 |
| [JetBrains/go-modern-guidelines](https://github.com/JetBrains/go-modern-guidelines) | ⭐0 (+300 today) | JetBrains 出品，为 AI 编码助手提供现代 Go 编程规范，直接提升代码质量。 |
| [tiny-llm](https://github.com/skyzh/tiny-llm) | ⭐4,525 | 在 Apple Silicon 上从零构建 LLM 推理系统，系统工程师入门 vLLM 的最佳实践。 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | ⭐186,953 | 经典自主 Agent 框架，持续迭代，让每个人都能构建和运行 AI 代理。 |
| [langchain](https://github.com/langchain-ai/langchain) | ⭐145,162 | 最流行的 Agent 工程平台，提供工具链、记忆、多模型集成。 |
| [browser-use](https://github.com/browser-use/browser-use) | ⭐111,507 | 让 AI Agent 能像人类一样操作浏览器，自动化在线任务，日增活跃度极高。 |
| [mem0](https://github.com/mem0ai/mem0) | ⭐64,225 | 通用记忆层，为 Agent 提供跨会话持久化能力，已成为诸多框架的依赖。 |
| [tt-a1i/archify](https://github.com/tt-a1i/archify) | ⭐0 (+4,239 today) | Agent 技能：用自然语言生成架构图、流程图、时序图等，输出自包含 HTML。 |
| [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | ⭐0 (+1,613 today) | 让 AI Agent 像“最懒的资深开发者”一样思考，用最少 token 生成最优代码。 |
| [TauricResearch/TradingAgents](https://github.com/TauricResearch/TradingAgents) | ⭐0 (+229 today) | 多智能体 LLM 金融交易框架，将 Agent 落地到量化决策场景。 |

### 📦 AI 应用（具体产品、垂直场景解决方案）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [open-webui](https://github.com/open-webui/open-webui) | ⭐150,181 | 用户友好的 AI 交互界面，支持 Ollama、OpenAI 等多种后端，私部署首选。 |
| [MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | ⭐117,583 | 输入主题，AI 自动生成高清短视频，已发展成完整的视频自动化工作流。 |
| [awesome-gpt-image-2](https://github.com/freestylefly/awesome-gpt-image-2) | ⭐0 (+2,096 today) | 工业级 GPT-Image 提示词引擎，含 530+ 案例逆向工程，20+ 套模板，Prompt as Code。 |
| [calesthio/OpenMontage](https://github.com/calesthio/OpenMontage) | ⭐0 (+1,292 today) | 首个开源智能视频制作系统，12 条生产线、100+ 工具、700+ Agent 技能。 |
| [career-ops](https://github.com/santifer/career-ops) | ⭐68,961 | 开源 AI 求职助手：自动扫描职位、评估、定制简历，支持多种 AI CLI。 |
| [CherryHQ/cherry-studio](https://github.com/CherryHQ/cherry-studio) | ⭐51,172 | AI 生产力工作室，集成智能聊天、自主 Agent、300+ 助手，统一接入前沿大模型。 |

### 🧠 大模型/训练（模型权重、训练框架、微调工具）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [pytorch](https://github.com/pytorch/pytorch) | ⭐102,634 | 深度学习框架的事实标准，今日无新增 Star 但生态地位不可撼动。 |
| [LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | ⭐103,926 | 从零实现类 ChatGPT 的 LLM，配套书籍与代码，社区学习热点。 |
| [ultralytics](https://github.com/ultralytics/ultralytics) | ⭐61,024 | YOLO 系列最新版，支持检测、分割、分类、姿态估计等，计算机视觉首选。 |
| [marin-community/marin](https://github.com/marin-community/marin) | ⭐0 (+255 today) | 开源基础模型研究框架，面向大模型研究与开发，今日新星。 |
| [opencompass](https://github.com/open-compass/opencompass) | ⭐7,372 | 大模型评测平台，支持 100+ 数据集，模型排行榜参考。 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 一句话说明 |
|------

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*