# AI 开源趋势日报 2026-08-10

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-08-09 23:04 UTC

---

# AI 开源趋势日报 | 2026-08-10

## 1. 今日速览

- **Agent 技能化**：`addyosmani/agent-skills` 与 `google/skills` 双双登顶 Trending，标志着 AI 编码 Agent 的“技能市场”概念正在形成，社区开始追求生产级、可复用的工程化能力。
- **自改进 Agent 爆发**：`PrimeIntellect-ai/prime-agent` 今日新增 2319 stars，首次提出“自改进 RLM Agent”，将强化学习与自主任务结合，成为今日最亮眼的新星。
- **RAG + 知识图谱融合**：`vitali87/code-graph-rag` 和 `Graphify-Labs/graphify` 分别从代码库和通用知识维度，将知识图谱与 RAG 深度绑定，多跳推理能力成为新焦点。
- **Google DeepMind 开源天气模型**：`google-deepmind/weathernext` 将 AI 扩展到气象预测领域，预示大模型在科学计算与垂直场景的落地加速。
- **ComfyUI 持续领跑生成式 AI**：作为最成熟的扩散模型 GUI，依然保持 333 日增星，生态成熟度无人能及。

---

## 2. 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、开发工具、CLI）

| 项目 | Stars | 说明 |
|------|-------|------|
| [tensorflow/tensorflow](https://github.com/tensorflow/tensorflow) | 196,942 | 经典机器学习框架，持续更新，生态庞大 |
| [pytorch/pytorch](https://github.com/pytorch/pytorch) | 102,301 | 动态神经网络框架，GPU 加速，AI 研究首选 |
| [huggingface/transformers](https://github.com/huggingface/transformers) | 163,503 | 模型定义框架，覆盖文本/视觉/多模态，支持推理与训练 |
| [ollama/ollama](https://github.com/ollama/ollama) | 178,137 | 本地 LLM 推理引擎，一键运行多种开源模型 |
| [skyzh/tiny-llm](https://github.com/skyzh/tiny-llm) | 4,455 | 在 Apple Silicon 上从零实现 LLM 推理服务，系统工程师入门首选 |
| [rig](https://github.com/0xPlaygrounds/rig) | 8,219 | 用 Rust 构建模块化 LLM 应用，高性能、低资源消耗 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 说明 |
|------|-------|------|
| [PrimeIntellect-ai/prime-agent](https://github.com/PrimeIntellect-ai/prime-agent) | 0 (+2319 today) | 自改进 RLM 编码 Agent，可处理长期自主任务，今日最爆款 |
| [msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents) | 0 (+932 today) | 完整 AI 代理机构，包含前端、Reddit、创意等多角色专家 |
| [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | 0 (+670 today) | 生产级工程技能库，为 AI 编码 Agent 提供可复用能力 |
| [google/skills](https://github.com/google/skills) | 0 (+532 today) | Google 官方的 Agent 技能库，覆盖 Google 产品和技术 |
| [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 186,461 | 普适性 Agent 框架，让每个人都能构建和使用 AI 代理 |
| [langchain-ai/langchain](https://github.com/langchain-ai/langchain) | 143,811 | Agent 工程平台，提供工具调用、记忆、多智能体编排 |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | 108,479 | 让 AI 代理无缝操控浏览器，自动化在线任务 |
| [CherryHQ/cherry-studio](https://github.com/CherryHQ/cherry-studio) | 50,180 | 智能聊天+自主 Agent+300+助手，统一接入前沿 LLM |

### 📦 AI 应用（具体产品、垂直场景解决方案）

| 项目 | Stars | 说明 |
|------|-------|------|
| [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI) | 0 (+333 today) | 最强大的扩散模型节点式 GUI，支持 API 和后端 |
| [ZhuLinsen/daily_stock_analysis](https://github.com/ZhuLinsen/daily_stock_analysis) | 61,150 (+287 today) | LLM 驱动的多市场股票分析系统，含实时新闻、决策看板 |
| [google-deepmind/weathernext](https://github.com/google-deepmind/weathernext) | 0 (+105 today) | DeepMind 开源天气预测模型，AI 气象科学新进展 |
| [harry0703/MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 102,329 | 一键生成短视频，AI 自动化工作流驱动 |
| [harveyai/harvey-labs](https://github.com/harveyai/harvey-labs) | 0 (+87 today) | 法律工作 AI 基准，评估和提升 Agent 法律支持能力 |
| [open-webui/open-webui](https://github.com/open-webui/open-webui) | 148,325 | 用户友好的 LLM 聊天界面，支持 Ollama 和 OpenAI API |

### 🧠 大模型/训练（模型权重、训练框架、微调工具）

| 项目 | Stars | 说明 |
|------|-------|------|
| [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | 102,029 | 从零实现 ChatGPT 类 LLM，PyTorch 逐行代码 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | 54,497 | 2 小时训练 64M 参数小模型，入门 LLM 训练的最佳实践 |
| [open-compass/opencompass](https://github.com/open-compass/opencompass) | 7,287 | 超过 100+ 数据集的大模型评估平台，支持主流模型 |
| [genieincodebottle/generative-ai](https://github.com/genieincodebottle/generative-ai) | 2,591 | 生成式 AI 综合资源，含路线图、项目、面试准备 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 说明 |
|------|-------|------|
| [vitali87/code-graph-rag](https://github.com/vitali87/code-graph-rag) | 0 (+59 today) | 基于知识图谱的代码库 RAG，支持多语言理解和编辑 |
| [milvus-io/milvus](https://github.com/milvus-io/milvus) | 45,571 | 高性能云原生向量数据库，大规模 ANN 搜索 |
| [qdrant/qdrant](https://github.com/qdrant/qdrant) | 33,889 | 高可扩展向量搜索引擎，支持云端部署 |
| [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | 87,125 | 领先的开源 RAG 引擎，融合 Agent 能力与上下文层 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 62,877 | AI Agent 的通用记忆层，实现跨会话持久上下文 |
| [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | 104,601 | 将代码库、文档、SQL 模式转为可查询知识图谱，无需向量库 |
| [topoteretes/cognee](https://github.com/topoteretes/cognee) | 29,889 | 开源 AI 记忆平台，基于知识图谱为 Agent 提供长期记忆 |

---

## 3. 趋势信号分析

从今日热榜来看，**Agent 技能化与自改进 Agent 是社区爆发性关注的两大焦点**。`prime-agent` 单日新增 2319 星，其“自改进 RLM”机制将强化学习引入 Agent 循环，代表 Agent 从“工具调用”向“持续学习进化”的跃迁。同时，`agent-skills` 和 `google/skills` 同时登榜，表明行业正在标准化 Agent 的“技能”概念——就像编程语言中的库一样，可复用的工程化能力将极大降低 Agent 开发门槛。

**新兴技术栈方面**，`code-graph-rag` 和 `Graphify-Labs/graphify` 首次将知识图谱与 RAG 深度结合，使用 AST 解析和结构化图而非向量存储，实现了更精确的多跳推理。这可能是 RAG 从“检索+生成”到“推理+生成”的重要转折点。

**与行业事件的关联**：Google DeepMind 开源 `weathernext` 恰逢极端天气频发，气候 AI 关注度上升；`harveyai/harvey-labs` 聚焦法律领域，呼应了 AI 在垂直行业落地的合规与效率需求。此外，`ComfyUI` 的持续热度表明生成式 AI 仍处于工具生态建设期，节点式工作流成为图像生成的标准范式。

---

## 4. 社区关注热点

- **🔥 `PrimeIntellect-ai/prime-agent`**：首个宣称“自改进”的编码 Agent，结合强化学习，对长期自主任务有突破性意义，值得持续跟踪其架构实现。
- **🧩 `addyosmani/agent-skills` 与 `google/skills`**：Agent 技能规范化趋势，未来可能成为类似 npm/yarn 的 Agent 技能包生态，前端开发者可重点关注。
- **📊 `vitali87/code-graph-rag`**：知识图谱+代码库 RAG 的先锋，对于大型 monorepo 的智能问答和代码理解有实用价值，适合 DevOps 和内部工具团队。
- **🌦️ `google-deepmind/weathernext`**：DeepMind 开源的科学 AI 模型，标志着大模型在气象领域的正式落地，对气候研究和能源行业开发者有直接参考意义。
- **🎨 `Comfy-Org/ComfyUI`**：虽已成熟，但日增 333 星说明其生态仍在扩张，节点式工作流模式正在被其他 AI 领域（如视频、3D）借鉴，值得关注其扩展插件体系。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*