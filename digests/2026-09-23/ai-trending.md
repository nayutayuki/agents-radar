# AI 开源趋势日报 2026-09-23

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-09-23 00:55 UTC

---

# AI 开源趋势日报 — 2026-09-23

## 今日速览

今日 Google 发布的 Agent 编排运行时 **google/ax** 以单日 2305 stars 的爆发式增长登顶 Trending，标志着大型科技公司正加速将多智能体系统推向开源。与此同时，AI Agent 生态持续分化：轻量级 Agent 框架（`agent-substrate`）、面向 Agent 的办公工具（`dream-num/univer`）、以及工具调用路由器（`treg`）均获得百级以上关注。在 RAG 与向量数据库领域，**LEANN**（MLsys 2026 Best Paper）实现了 97% 的存储压缩，成为本地 RAG 的新技术标杆。大模型训练方面，**minimind** 和 **tiny-llm** 等低成本入门项目依然保持着社区热度。

## 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、CLI）

| 项目 | Stars | 今日新增 | 一句话说明 |
|------|-------|----------|------------|
| [google/ax](https://github.com/google/ax) | 0 → 2,305 | +2,305 | Google 开源的多智能体编排运行时，旨在统一 Agent 管理与调度，今日最热项目 |
| [tensorflow/tensorflow](https://github.com/tensorflow/tensorflow) | 200,260 | - | 经典机器学习框架，持续作为 AI 基础设施基石 |
| [pytorch/pytorch](https://github.com/pytorch/pytorch) | 103,182 | - | 动态神经网络框架，GPU 加速的 Tensor 库 |
| [langchain-ai/langchain](https://github.com/langchain-ai/langchain) | 146,896 | - | LLM 应用开发框架，支持 Agent、RAG 等全栈工程化 |
| [ollama/ollama](https://github.com/ollama/ollama) | 181,493 | - | 本地运行大模型的跨平台工具，已支持 Kimi、GLM、DeepSeek 等国产模型 |
| [agent-substrate/substrate](https://github.com/agent-substrate/substrate) | 0 (+245 today) | +245 | Agent Substrate 核心系统，轻量级 Agent 运行时 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 今日新增 | 一句话说明 |
|------|-------|----------|------------|
| [langgenius/dify](https://github.com/langgenius/dify) | 156,888 | - | 可视化 Agent 工作流编排平台，支持多模型与 RAG 管道 |
| [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 187,503 | - | 自主 AI Agent 先驱，提供可扩展的任务规划与执行能力 |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | 115,949 | - | 让 Agent 直接操控浏览器的开源方案，自动化网页操作 |
| [Hermes-Agent](https://github.com/NousResearch/hermes-agent) | 248,117 | - | 与用户共同成长的个性化 Agent，支持长期记忆与工具集成 |
| [CopilotKit](https://github.com/CopilotKit/CopilotKit) | 37,479 | - | 前端 Agent UI 框架，支持 React/Angular 等，定义 AG-UI 协议 |
| [HKUDS/nanobot](https://github.com/HKUDS/nanobot) | 48,491 | - | 极轻量级个人 AI Agent 框架，自带 WebUI、工具、记忆、多Agent |
| [TradingAgents](https://github.com/TauricResearch/TradingAgents) | 108,143 | - | 多 Agent 金融交易框架，结合 LLM 的量化策略 |

### 📦 AI 应用（具体应用产品、垂直场景解决方案）

| 项目 | Stars | 今日新增 | 一句话说明 |
|------|-------|----------|------------|
| [dream-num/univer](https://github.com/dream-num/univer) | 0 (+255 today) | +255 | 为 AI Agent 打造的办公套件，统一处理表格、文档、幻灯片等 |
| [browser-use/video-use](https://github.com/browser-use/video-use) | 0 (+191 today) | +191 | 用编码 Agent 直接编辑视频，拓展 Agent 的创作能力 |
| [davila7/claude-code-templates](https://github.com/davila7/claude-code-templates) | 0 (+64 today) | +64 | Claude Code 配置与监控 CLI 工具，方便开发者定制 Agent |
| [superdesigndev/treg](https://github.com/superdesigndev/treg) | 0 (+230 today) | +230 | Agent 工具的 OpenRouter，让不同 Agent 共享工具调用能力 |
| [open-webui](https://github.com/open-webui/open-webui) | 152,847 | - | 用户友好的 AI 交互界面，支持 Ollama、OpenAI 等后端 |
| [MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 125,168 | - | 一键生成短视频的 AI 工作流，结合大模型与自动化 |

### 🧠 大模型/训练（模型权重、训练框架、微调工具）

| 项目 | Stars | 今日新增 | 一句话说明 |
|------|-------|----------|------------|
| [huggingface/transformers](https://github.com/huggingface/transformers) | 166,539 | - | 业界标准模型定义推理框架，支持文本、视觉、多模态 |
| [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | 105,402 | - | 从零实现类 ChatGPT LLM 的教程，步骤级代码 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | 62,192 | - | 2小时从零训练 64M 参数 LLM，降低入门门槛 |
| [skyzh/tiny-llm](https://github.com/skyzh/tiny-llm) | 4,680 | - | 在 Apple Silicon 上构建迷你 vLLM + Qwen 推理系统，面向系统工程师 |
| [open-compass](https://github.com/open-compass/opencompass) | 7,468 | - | 大模型评估平台，支持 100+ 数据集与主流模型 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 今日新增 | 一句话说明 |
|------|-------|----------|------------|
| [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | 91,174 | - | 融合 Agent 能力的 RAG 引擎，提供 LLM 上下文层 |
| [milvus-io/milvus](https://github.com/milvus-io/milvus) | 46,220 | - | 高性能云原生向量数据库，支持大规模 ANN 搜索 |
| [qdrant/qdrant](https://github.com/qdrant/qdrant) | 34,758 | - | 下一代向量数据库，支持 AI 应用生产部署 |
| [StarTrail-org/LEANN](https://github.com/StarTrail-org/LEANN) | 12,957 | - | [MLsys 2026 Best Paper] 实现 97% 存储压缩的本地 RAG 方案 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 65,844 | - | AI Agent 的记忆层，构建持久上下文基础设施 |
| [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | 120,572 | - | 将代码库、文档等转换为可查询知识图谱，无向量存储 |

## 趋势信号分析

1. **Agent 编排与工具链爆发式增长**：今日新星 `google/ax`（+2,305）和 `agent-substrate`（+245）代表了两条 Agent 基础设施路线：大型商业公司推出统一运行时 vs 社区驱动的轻量核心。同时 `treg`（+230）作为 Agent 工具路由器（OpenRouter for agent tools），标志着 Agent 互操作性需求上升。

2. **Agent 与办公/创作场景深度融合**：`univer`（+255）将电子表格、文档、PDF 等传统办公能力作为 Agent 的“运行时”，`video-use`（+191）则把视频编辑交给编码 Agent，表明 Agent 正从单纯对话转向复杂生产力任务。

3. **RAG 技术创新落地**：LEANN 获得 MLsys 2026 最佳论文并迅速开源，其 97% 存储压缩能力可能改变本地 RAG 的部署格局。同时 `cognee`（30.9k stars）作为 AI 记忆平台，与 `mem0` 共同推动 Agent 长期记忆标准化。

4. **低成本 LLM 训练持续受关注**：`minimind`（62k stars）和 `tiny-llm`（4.7k stars）证明社区对“从零训练”的刚需，配合 `open-compass` 评估平台，形成了小模型研发的闭环生态。

## 社区关注热点

- **google/ax** — 来自 Google 的 Agent 编排运行时，今日 stars 暴涨，可能成为多智能体系统的事实标准，值得深入理解其架构。
- **LEANN (StarTrail-org/LEANN)** — 最佳论文级别的 RAG 压缩方案，适合有本地部署需求、对存储敏感的开发团队。
- **dream-num/univer** — AI Agent 的“办公操作系统”，将文档、表格、PDF 统一为 Agent 可操作的实体，代表基础设施层的新想象力。
- **treg (superdesigndev/treg)** — Agent 工具路由器的出现，暗示 Agent 生态正在走向“工具市场”模式，类似 OpenRouter 对模型的作用。
- **nanobot (HKUDS/nanobot)** — 极轻量、自部署的个人 Agent 框架，特别适合对隐私敏感、希望拥有完整控制权的个人开发者。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*