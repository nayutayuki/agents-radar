# AI 开源趋势日报 2026-08-05

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-08-04 23:39 UTC

---

# AI 开源趋势日报（2026-08-05）

## 今日速览

- **AI Agent 生态全面爆发**：今日 Trending 榜近半数项目为 Agent 相关，从内存管理、安全审计到技能框架，社区正在为 Agent 构建完整基础设施。
- **推理优化持续深入**：`airllm` 实现单张 4GB GPU 运行 70B 模型，`DeepSeek-Reasonix` 聚焦前缀缓存稳定性，推理效率仍是热门方向。
- **视频编辑与逆向工程等垂直场景被 AI Agent 渗透**：`browser-use/video-use` 让编码 agent 直接编辑视频，`reverse-skill` 将安全渗透工具链与 AI 客户端深度集成。
- **RAG 与知识管理赛道成熟**：主题搜索中向量数据库（Milvus、Qdrant、LanceDB）和 RAG 框架（RAGFlow、AnythingLLM）均保持高星，企业级落地需求旺盛。

## 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、CLI）

| 项目 | Stars | 说明 |
|------|-------|------|
| [ollama/ollama](https://github.com/ollama/ollama) | ⭐177,784 | 一键运行主流大模型（Kimi、DeepSeek、Qwen 等），本地推理首选 CLI。 |
| [huggingface/transformers](https://github.com/huggingface/transformers) | ⭐163,336 | 最流行的模型定义与推理框架，支持文本、视觉、多模态。 |
| [lyogavin/airllm](https://github.com/lyogavin/airllm) | ⭐0 (+1,716 today) | 单张 4GB GPU 即可运行 70B 模型推理，大幅降低硬件门槛。 |
| [esengine/DeepSeek-Reasonix](https://github.com/esengine/DeepSeek-Reasonix) | ⭐30,746 (+924 today) | 原生 DeepSeek 编码 agent，围绕前缀缓存稳定性设计，可长期运行。 |
| [firecrawl/pdf-inspector](https://github.com/firecrawl/pdf-inspector) | ⭐0 (+2,524 today) | 高性能 PDF 检测与分类库，智能识别扫描/文本 PDF，为 RAG 路由提供决策。 |
| [langchain-ai/langchain](https://github.com/langchain-ai/langchain) | ⭐143,424 | Agent 工程平台，提供统一 API 集成 LLM、工具、向量存储。 |
| [langchain4j/langchain4j](https://github.com/langchain4j/langchain4j) | ⭐12,788 | Java 生态的 LangChain 实现，支持 MCP、工具调用、RAG，与 Quarkus/Spring Boot 集成。 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 说明 |
|------|-------|------|
| [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | ⭐185,811 | 经典通用 Agent 框架，面向任务自动分解与执行。 |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | ⭐107,876 | 让 AI agent 自动操控浏览器，完成网页自动化任务。 |
| [livekit/agents](https://github.com/livekit/agents) | ⭐0 (+432 today) | 实时语音 AI agent 框架，支持语音交互、视频通话场景。 |
| [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) | ⭐0 (+1,138 today) | 团队级 Agent 内存中心，将对话、文档、代码转化为可共享的记忆资产。 |
| [obra/superpowers](https://github.com/obra/superpowers) | ⭐0 (+777 today) | Agentic 技能框架与软件开发方法论，强调可复用的技能路由。 |
| [uber/ADR](https://github.com/uber/ADR) | ⭐0 (+140 today) | 企业级 Agent 安全审计与威胁检测框架，Uber 内部部署。 |
| [CherryHQ/cherry-studio](https://github.com/CherryHQ/cherry-studio) | ⭐49,406 | AI 生产力工作室，集成智能聊天、自主 agent、300+ 助手，统一接入前沿模型。 |

### 📦 AI 应用（具体产品、垂直场景）

| 项目 | Stars | 说明 |
|------|-------|------|
| [harry0703/MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | ⭐101,608 | 根据主题一键生成高清短视频，AI 自动化内容创作标杆。 |
| [browser-use/video-use](https://github.com/browser-use/video-use) | ⭐0 (+306 today) | 用编码 agent 直接编辑视频，将编程覆盖到多媒体处理。 |
| [zhaoxuya520/reverse-skill](https://github.com/zhaoxuya520/reverse-skill) | ⭐0 (+2,310 today) | 逆向/渗透安全技能路由包，AI 自动路由与工具链自举，支持多种 AI 客户端。 |
| [ZhuLinsen/daily_stock_analysis](https://github.com/ZhuLinsen/daily_stock_analysis) | ⭐60,061 | LLM 驱动的多市场股票智能分析系统，含实时新闻、决策看板。 |
| [santifer/career-ops](https://github.com/santifer/career-ops) | ⭐62,792 | 开源 AI 求职助手：扫描职位、按 A-F 评分、定制简历，本地运行。 |
| [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) | ⭐43,002 | AI 将文档/主题转为原生 PowerPoint，含动画、图表、音频旁白。 |

### 🧠 大模型/训练（模型权重、训练框架、微调）

| 项目 | Stars | 说明 |
|------|-------|------|
| [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | ⭐100,560 | 从零实现 ChatGPT 类 LLM 的 PyTorch 教程，适合深度学习。 |
| [open-compass/opencompass](https://github.com/open-compass/opencompass) | ⭐7,273 | 大模型评估平台，支持 100+ 数据集，覆盖 Llama、Qwen、GLM 等。 |
| [skyzh/tiny-llm](https://github.com/skyzh/tiny-llm) | ⭐4,440 | 面向系统工程师的 LLM 推理服务课程，在 Apple Silicon 上构建 mini vLLM。 |
| [AarambhDevHub/aarambh-studio](https://github.com/AarambhDevHub/aarambh-studio) | ⭐62 | 纯 Rust 实现的 Decoder-only LLM，使用 Candle，支持 MoE、量化感知训练。 |
| [Event-AHU/Medical_Image_Analysis](https://github.com/Event-AHU/Medical_Image_Analysis) | ⭐237 | 基于基础模型的医学图像分析，跨领域 LLM 应用。 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 说明 |
|------|-------|------|
| [milvus-io/milvus](https://github.com/milvus-io/milvus) | ⭐45,510 | 高性能云原生向量数据库，大规模 ANN 搜索。 |
| [qdrant/qdrant](https://github.com/qdrant/qdrant) | ⭐33,779 | 高性能向量数据库与搜索引擎，支持云服务。 |
| [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | ⭐86,818 | 领先的开源 RAG 引擎，融合 Agent 能力，构建 LLM 上下文层。 |
| [Mintplex-Labs/anything-llm](https://github.com/Mintplex-Labs/anything-llm) | ⭐64,336 | 本地优先的 Agent 体验，支持 RAG、知识库、多模型。 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | ⭐62,521 | 通用 AI Agent 记忆层，跨会话持久化上下文。 |
| [lancedb/lancedb](https://github.com/lancedb/lancedb) | ⭐11,074 | 嵌入式多模态检索库，支持向量与全文搜索，开发者友好。 |
| [StarTrail-org/LEANN](https://github.com/StarTrail-org/LEANN) | ⭐12,760 | MLsys2026 论文：97% 存储节省 + 100% 隐私的本地 RAG 方案。 |

## 趋势信号分析

- **AI Agent 生态正在从“玩具”走向“基础设施”**：今日 Trending 中 `TencentDB-Agent-Memory`（团队级记忆）、`uber/ADR`（安全审计）、`obra/superpowers`（技能框架）等表明，社区不再满足于单一 Agent 演示，而是构建可治理、可共享、可扩展的 Agent 运行环境。主题搜索中 `AutoGPT`、`browser-use`、`CherryHQ` 等持续高星，印证这一趋势。
- **推理边缘化与硬件适配加速**：`airllm` 单卡 4GB 跑 70B 模型、`DeepSeek-Reasonix` 针对前缀缓存优化，表明推理效率仍是核心瓶颈，碎片化硬件（移动端、Mac 等）适配成为新热点。`tiny-llm` 课程的出现也反映了系统工程师对推理优化的关注。
- **安全与 AI 的交叉领域首次登榜**：`reverse-skill` 和 `uber/ADR` 分别从渗透测试和企业安全切入，AI 与安全工具链的结合成为新方向，可能源于近期大模型安全事件（如提示注入、数据泄露）的推动。
- **RAG 技术栈趋于成熟，向“记忆层”升级**：主题搜索中 `mem0`、`TencentDB-Agent-Memory` 等将传统 RAG 升级为长期记忆与知识图谱，向量数据库从 Milvus 到 LanceDB 覆盖了从云端到嵌入式的全场景。`LEANN` 的极高存储压缩比表明 RAG 在私有化部署中仍有创新空间。

## 社区关注热点

- **Agent 记忆与上下文管理**：`TencentDB-Agent-Memory` 和 `mem0` 成为焦点，解决 Agent 跨会话遗忘问题，是构建连续智能体的关键。
- **低资源推理**：`airllm` 单卡 4GB 跑 70B 模型，让个人开发者也能本地运行大模型，降低 AI 应用门槛。
- **AI Agent 安全**：`uber/ADR` 开源后，企业级 Agent 安全防护（威胁检测、权限审计）成为刚需，值得跟进。
- **视频与多媒体 Agent**：`browser-use/video-use` 将 Agent 能力扩展到视频编辑，预示多模态 Agent 将进入内容创作领域。
- **Rust 在 AI 基础设施中的崛起**：`qdrant`、`lancedb`、`firecrawl/pdf-inspector`、`AarambhDevHub/aarambh-studio` 均使用 Rust，体现高性能、安全、低资源占用的趋势。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*