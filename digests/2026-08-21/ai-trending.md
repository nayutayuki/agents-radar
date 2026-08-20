# AI 开源趋势日报 2026-08-21

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-08-20 23:00 UTC

---

# AI 开源趋势日报 | 2026-08-21

## 今日速览

今日 GitHub 开源社区最值得关注的动向是：**AI 智能体（Agent）技能与记忆层项目全面爆发**，多个 agent 相关仓库登顶 Trending 榜单，其中 `mattpocock/skills` 和 `obra/superpowers` 分别以 +2267 和 +749 的今日新增 stars 领跑；**AI 短视频生成工具 `MoneyPrinterTurbo` 单日暴增 2774 星**，成为今日最热应用；**腾讯推出的 AI 红队平台 `AI-Infra-Guard`** 以及 **字节跳动的自进化上下文数据库 `OpenViking`** 首次进入大众视野，标志着 AI 安全与记忆层基础设施成为新热点。同时，**Mojo 语言平台 `modular/modular`** 持续获得关注，而 **Rust 编写的轻量级向量索引 `turbovec`** 也吸引了 251 颗新星，显示 AI 底层技术栈正加速向高性能语言迁移。

---

## 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、开发工具、CLI）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [modular/modular](https://github.com/modular/modular) | 0+ | +340 | Mojo 语言及 MAX 平台，面向 AI 的高性能编程语言与运行时，今日热度回升 |
| [cursor/plugins](https://github.com/cursor/plugins) | 0+ | +473 | Cursor 官方插件规范与实现，为 AI 编程 IDE 扩展生态提供标准接口 |
| [PostHog/posthog](https://github.com/PostHog/posthog) | 0+ | +100 | 领先的自驱产品分析平台，新增 AI 可观测性、MCP 集成，支持 agent 调试 |
| [Tencent/AI-Infra-Guard](https://github.com/Tencent/AI-Infra-Guard) | 0+ | +28 | 腾讯开源的 AI 红队平台，覆盖 Agent/技能/MCP/LLM 越狱评估，安全基础设施 |
| [RyanCodrai/turbovec](https://github.com/RyanCodrai/turbovec) | 0+ | +251 | 基于 TurboQuant 的 Rust 向量索引，提供 Python 绑定，轻量高性能 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [mattpocock/skills](https://github.com/mattpocock/skills) | 0+ | +2267 | 面向真实工程师的 agent 技能集，从作者的 `.agents` 目录中直接提取，今日最热 |
| [obra/superpowers](https://github.com/obra/superpowers) | 0+ | +749 | 一套有效的 agent 技能框架与软件开发方法论，强调可复用技能 |
| [akitaonrails/ai-memory](https://github.com/akitaonrails/ai-memory) | 0+ | +335 | 为 agent 编码 CLI 提供长期记忆，支持不同 agent 之间的交接，Rust 实现 |
| [agent-substrate/substrate](https://github.com/agent-substrate/substrate) | 0+ | +66 | 核心的多 agent 系统，Go 语言构建，面向生产级 agent 基础设施 |
| [chaitanyagiri/munder-difflin](https://github.com/chaitanyagiri/munder-difflin) | 0+ | +517 | 本地多 agent 测试 harness，TypeScript 实现，适合快速原型验证 |
| [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) | 99.6k | +309 | 用“原始人”语言风格节省 65% token 的 Claude Code 技能，创意与实用兼备 |
| [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | 233.5k | — | 社区最受欢迎的 agent 框架之一，“与你一同成长的 agent”，持续活跃 |

### 📦 AI 应用（具体应用产品、垂直场景解决方案）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [harry0703/MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 112.9k | +2774 | 基于 AI 大模型与自动化工作流一键生成高清短视频，今日 GitHub 星数增长冠军 |
| [santifer/career-ops](https://github.com/santifer/career-ops) | 66.6k | +855 | 开源的 AI 求职助手：扫描职位、评分、定制简历、追踪申请，本地运行 |
| [ZhuLinsen/daily_stock_analysis](https://github.com/ZhuLinsen/daily_stock_analysis) | 63.5k | — | LLM 驱动的多市场股票智能分析系统，支持实时行情与决策看板 |
| [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) | 48.2k | — | AI 将文档/主题自动生成原生 PowerPoint，支持动画、图表、语音旁白 |
| [CherryHQ/cherry-studio](https://github.com/CherryHQ/cherry-studio) | 50.8k | — | AI 生产力工作室，集成 300+ 助手、自主 agent、智能聊天，统一接入前沿 LLM |

### 🧠 大模型/训练（模型权重、训练框架、微调工具）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [ollama/ollama](https://github.com/ollama/ollama) | 179.1k | — | 本地运行主流大模型（Kimi、GLM、DeepSeek、Qwen 等）的最流行工具，今日依旧高热度 |
| [huggingface/transformers](https://github.com/huggingface/transformers) | 164.3k | — | 模型定义与训练框架，支持文本、视觉、音频、多模态，生态基石 |
| [vllm-project/vllm](https://github.com/vllm-project/vllm) | 89.6k | — | 高吞吐、低内存的 LLM 推理引擎，是生产部署的首选方案 |
| [ultralytics/ultralytics](https://github.com/ultralytics/ultralytics) | 60.8k | — | YOLO 系列目标检测框架，持续迭代至 YOLO26，计算机视觉基础 |
| [skyzh/tiny-llm](https://github.com/skyzh/tiny-llm) | 4.5k | — | 面向系统工程师的 LLM 推理学习项目，从零构建微型 vLLM + Qwen，教育意义强 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 今日新增 | 说明 |
|------|-------|----------|------|
| [volcengine/OpenViking](https://github.com/volcengine/OpenViking) | 0+ | +955 | 字节跳动开源的自进化上下文数据库，统一 Agent 记忆、知识 RAG 和技能，今日黑马 |
| [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | 88.9k | — | 领先的开源 RAG 引擎，融合 Agent 能力，为 LLM 提供优质上下文层 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 63.7k | — | 通用 AI Agent 记忆层，支持长期记忆与跨会话持久化 |
| [milvus-io/milvus](https://github.com/milvus-io/milvus) | 45.7k | — | 高性能云原生向量数据库，规模化 ANN 搜索基础设施

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*