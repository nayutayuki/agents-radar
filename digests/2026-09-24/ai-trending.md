# AI 开源趋势日报 2026-09-24

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-09-24 00:52 UTC

---

# 《AI 开源趋势日报》 2026-09-24

---

## 1. 今日速览

今日 GitHub AI 开源领域呈现 **三大热点**：一是 **Agent 框架与编排运行时** 全面爆发，Google 推出的开源 agentic orchestration 项目 `google/ax` 单日斩获 1500+ stars，多个轻量级 agent SDK 和 CLI 工具（如 `strands-agents/harness-sdk`、`obra/superpowers`）纷纷登榜；二是 **AI 驱动的金融/量化应用** 持续升温，盯盘助手 `PanWatch` 与多智能体交易框架 `TradingAgents` 吸引大量关注；三是 **MCP (Model Context Protocol) 生态** 快速成型，`DeusData/codebase-memory-mcp` 以高性能代码知识图谱 MCP 服务器收获 190 stars，预示着 Agent 与工具间的标准化协议正在成为标配。此外，视频编辑与 3D 高斯泼溅训练等创意 AI 工具也出现在热榜，社区对“Agent-Native”软件形态的探索已进入新阶段。

---

## 2. 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、开发工具、CLI）

| 项目 | Stars | 说明 |
|------|-------|------|
| [ollama/ollama](https://github.com/ollama/ollama) | 181,534 | 本地运行大模型的首选工具，支持 Kimi、GLM、DeepSeek 等最新模型，社区用户持续涌入。 |
| [langchain-ai/langchain](https://github.com/langchain-ai/langchain) | 146,943 | Agent 工程平台，今日热度不减，仍是构建智能体应用的核心框架。 |
| [firecrawl/firecrawl](https://github.com/firecrawl/firecrawl) | 183,872 | 面向 AI 的网页数据 API，支持大规模搜索、抓取与交互，是 LLM 应用获取外部数据的关键基础设施。 |
| [DeusData/codebase-memory-mcp](https://github.com/DeusData/codebase-memory-mcp) | 0 (+190 today) | 高性能代码智能 MCP 服务器，极速索引代码库为知识图谱，单二进制零依赖，适配 158 种语言。 |
| [0xPlaygrounds/rig](https://github.com/0xPlaygrounds/rig) | 8,712 | Rust 语言下的模块化 LLM 应用构建框架，性能优先，适合对延迟敏感的场景。 |
| [samchon/nestia](https://github.com/samchon/nestia) | 2,180 | NestJS 辅助库 + AI 聊天机器人开发工具，后端开发者快速集成 LLM 的利器。 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 说明 |
|------|-------|------|
| [google/ax](https://github.com/google/ax) | 0 (+1543 today) | Google 开源的 Agentic 编排运行时，今日最大黑马，提供云原生 agent 调度能力。 |
| [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 187,516 | 自治 Agent 的鼻祖项目，持续迭代，社区活跃度极高。 |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | 116,087 | 让 Agent 操控浏览器完成复杂任务，今日姊妹项目 `video-use` 也登榜。 |
| [strands-agents/harness-sdk](https://github.com/strands-agents/harness-sdk) | 0 (+115 today) | 生产级 AI Agent SDK，支持 Python & TypeScript，端到端控制 agent harness。 |
| [obra/superpowers](https://github.com/obra/superpowers) | 0 (+474 today) | 一套 Agentic 技能框架与软件开发方法论，强调“技能即基础设施”。 |
| [agent-substrate/substrate](https://github.com/agent-substrate/substrate) | 0 (+558 today) | Agent Substrate 核心系统，提供 agent 底层运行时。 |
| [HKUDS/nanobot](https://github.com/HKUDS/nanobot) | 48,518 | 超轻量个人 AI agent 框架，自带 WebUI、工具、记忆、MCP、多 Agent 工作流。 |
| [browser-use/video-use](https://github.com/browser-use/video-use) | 0 (+746 today) | 用编码 Agent 编辑视频，将 AI agent 能力拓展至创意生产领域。 |

### 📦 AI 应用（具体应用产品、垂直场景解决方案）

| 项目 | Stars | 说明 |
|------|-------|------|
| [open-webui/open-webui](https://github.com/open-webui/open-webui) | 152,943 | 用户友好的 AI 界面，支持 Ollama、OpenAI API 等，本地部署首选。 |
| [langgenius/dify](https://github.com/langgenius/dify) | 157,005 | 构建 Agent 工作流、RAG 管线的协作平台，企业级部署友好。 |
| [CherryHQ/cherry-studio](https://github.com/CherryHQ/cherry-studio) | 52,116 | AI 生产力工作室：智能聊天、自主 Agent、300+ 助手，统一接入前沿 LLM。 |
| [TauricResearch/TradingAgents](https://github.com/TauricResearch/TradingAgents) | 108,323 | 多智能体 LLM 金融交易框架，今日持续升温。 |
| [TNT-Likely/PanWatch](https://github.com/TNT-Likely/PanWatch) | 0 (+95 today) | 自托管 AI 盯盘助手，集成 TradingAgents 多 Agent 决策，支持 A/港/美股。 |
| [harry0703/MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 125,388 | 利用 AI 大模型一键生成短视频，自动化工作流典范。 |
| [microsoft/qlib](https://github.com/microsoft/qlib) | 48,779 | AI 驱动的量化投资平台，支持多种 ML 范式与自动化研发流程。 |

### 🧠 大模型/训练（模型权重、训练框架、微调工具）

| 项目 | Stars | 说明 |
|------|-------|------|
| [huggingface/transformers](https://github.com/huggingface/transformers) | 166,570 | 业界标准模型库，支持几乎所有主流模型，今日新增关注点包括新发布的 tiny Qwen 模型。 |
| [pytorch/pytorch](https://github.com/pytorch/pytorch) | 103,219 | 深度学习框架基石，Agent 训练与部署的后端选择。 |
| [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | 105,471 | 从零实现 ChatGPT 级 LLM 的教程，理论与实践并重，社区持续追捧。 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | 62,333 | 仅用 2 小时训练 64M 参数 LLM，适合入门与实验。 |
| [skyzh/tiny-llm](https://github.com/skyzh/tiny-llm) | 4,708 | 面向系统工程师的 LLM 推理系统教程，在 Apple Silicon 上实现小 vLLM + Qwen。 |
| [harry7557558/spirula-studio](https://github.com/harry7557558/spirula-studio) | 0 (+69 today) | 跨平台 3D 高斯泼溅训练器，视频转 Splat 再转 Mesh，支持 Vulkan 与 CUDA。 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 说明 |
|------|-------|------|
| [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | 91,231 | 领先的开源 RAG 引擎，融合 Agent 能力，构建 LLM 上下文层。 |
| [milvus-io/milvus](https://github.com/milvus-io/milvus) | 46,242 | 云原生高性能向量数据库，可扩展的 ANN 搜索，AI 应用存储层标准。 |
| [qdrant/qdrant](https://github.com/qdrant/qdrant) | 34,771 | 高性能向量数据库与搜索引擎，支持云端与自托管，新一代 AI 基础设施。 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 65,910 | AI Agent 记忆层，为 Agent 提供持久化上下文，生产级基础设施。 |
| [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | 120,923 | 将代码库、文档等转化为可查询的知识图谱，支持 Claude Code 等 Agent 工具。 |
| [run-llama/llama_index](https://github.com/run-llama/llama_index) | 52,304 | 文档处理平台，连接 LLM 与各种数据源，RAG 应用的事实标准。 |
| [topoteretes/cognee](https://github.com/topoteretes/cognee) | 30,949 | Agent 的开源 AI 记忆平台，基于知识图谱引擎的持久化记忆。 |

---

## 3. 趋势信号分析

**① Agent 编排与轻量化 SDK 爆发**  
今日 Trending 榜单中出现 **至少 6 个与 Agent 直接相关的新项目**，其中 `google/ax`（+1543 stars）和 `agent-substrate/substrate`（+558 stars）代表着从“单个 Agent”向“Agent 集群编排”演进的趋势。`strands-agents/harness-sdk` 与 `obra/superpowers` 则聚焦于 Agent 的“装备”层——让开发者以标准化方式为 Agent 赋予技能、工具和记忆。这表明社区正从“演示 Agent”转向“生产级 Agent 基础设施”。

**② MCP 协议生态初具雏形**  
`DeusData/codebase-memory-mcp` 以 C 语言实现的高性能 MCP 服务器首次进入 Trending，结合 `headroomlabs-ai/headroom`（压缩工具输出）和 `apache/casbin-gateway`（MCP 安全网关），显示 **Model Context Protocol** 正在成为 Agent 与外部工具通信的默认协议。这是一个重要的基础设施信号——类似于 HTTP 之于 Web，MCP 或将成为 AI Agent 互联网的底层标准。

**③ AI + 金融的“Agent 化”加速**  
`TNT-Likely/PanWatch`（盯盘助手）与 `TauricResearch/TradingAgents` 均获得高关注。前者是自托管 AI 盯盘工具，集成后者作为决策引擎。同时 `OpenBB`（开源金融数据平台）标记为 “for AI agents”，`microsoft/qlib` 新增 RD-Agent 自动化研发流程。**量化投资领域正全面拥抱 Agent 架构**，且社区更倾向自托管解决方案（保护隐私）。

**④ 视频编辑与创意生产成为新战场**  
`browser-use/video-use` 单日 +746 stars，展示 Agent 编辑视频的能力；`spirula-studio` 则让 3D 高斯泼溅训练变得更易用。AI 从文本、代码扩展到音视频、3D 内容生成，**“Agent-Native”的创作工具** 正在出现。

---

## 4. 社区关注热点

- **🤖 Google/ax（Agent 编排运行时）** — 谷歌出品，今日 stars 增长最高，值得重点关注其架构设计与使用场景。它将 Agent 调度提升到与微服务同等的范式，可能推动企业级 Agent 部署。
- **🔧 MCP 高性能工具 `DeusData/codebase-memory-mcp`** — 用 C 写就的极速代码知识图谱 MCP 服务器，单二进制、零依赖、158 语言支持，将极大提升 Agent 对代码库的理解效率。
- **📈 AI 盯盘与量化 Agent `PanWatch` + `TradingAgents`** — 自托管与多 Agent 决策组合，代表个人投资者“AI 化”的浪潮，且完全开源，风险可控。
- **🎬 视频编辑 Agent `browser-use/video-use`** — 将浏览器操作迁移到视频编辑，展示 Agent 在非编码领域的通用操作潜力，社区期待更多“Agent 控制软件”的场景。
- **🧠 超轻量 Agent 框架 `HKUDS/nanobot`** — 48k stars 且仍在增长，提供 WebUI、MCP、多 Agent 工作流等全套能力，适合快速搭建个人 AI 助手，是学习 Agent 架构的最佳入门项目。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*