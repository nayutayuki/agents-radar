# AI 开源趋势日报 2026-08-03

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-08-02 23:38 UTC

---

# AI 开源趋势日报（2026-08-03）

---

## 今日速览

- **DeepSeek 生态持续爆发**：`ds4`（推理引擎）和 `DeepSeek-Reasonix`（AI 编码 Agent）双双登榜 Trending，前者支持 4GB 单卡运行 DeepSeek 4，后者主打前缀缓存稳定性，标志着 DeepSeek 正从模型层向下游工具链全面渗透。
- **Agent 技能与记忆机制成竞争焦点**：`Agent-Reach`、`last30days-skill`、`k-skill` 等技能类项目集中涌现，`TencentDB-Agent-Memory` 和 `mem0` 则推动 Agent 记忆从会话级向团队级、持久化升级。
- **低代码 + AI 新范式加速**：`JeecgBoot` 低代码平台引入 AI Skills，实现“一句话生成系统”；`Graphify` 将代码库转为可查询知识图谱，两者均获 10 万+ Stars，反映 AI 与工程实践深度融合的趋势。
- **RAG 进入“向量免检”时代**：`PageIndex` 提出“无向量 RAG”方案，`LEANN` 实现 97% 存储节省，`headroom` 专注 token 压缩——检索增强不再依赖传统向量数据库，性能与成本被重新定义。
- **AI 教育赛道热度不减**：微软 `AI-For-Beginners` 和 `Generative AI for Beginners` 单日新增超 2000+ Stars，社区对系统性入门材料的需求依然强劲。

---

## 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、CLI）

| 项目 | Stars | 一句话说明 |
|------|-------|-----------|
| [ollama/ollama](https://github.com/ollama/ollama) | 177,616 | 一键运行 DeepSeek、Qwen、Gemma 等主流模型，本地推理的首选工具。 |
| [vllm-project/vllm](https://github.com/vllm-project/vllm) | 87,970 | 高吞吐、内存高效的 LLM 推理与服务引擎，支撑生产级部署。 |
| [antirez/ds4](https://github.com/antirez/ds4) | ⭐0 (+187 today) | DeepSeek 4 Flash & PRO 本地推理引擎，支持 Metal、CUDA、ROCm，4GB 单卡即可运行。 |
| [lyogavin/airllm](https://github.com/lyogavin/airllm) | ⭐0 (+963 today) | 只需 4GB 显存即可运行 70B 模型推理，打破本地部署的硬件门槛。 |
| [esengine/DeepSeek-Reasonix](https://github.com/esengine/DeepSeek-Reasonix) | ⭐0 (+389 today) | DeepSeek 原生 AI 编码 Agent，专为终端设计，利用前缀缓存保持长期运行稳定性。 |
| [huggingface/transformers](https://github.com/huggingface/transformers) | 163,262 | 主流模型定义与训练框架，支持文本、视觉、音频、多模态。 |
| [pytorch/pytorch](https://github.com/pytorch/pytorch) | 102,137 | 动态神经网络与 GPU 加速框架，AI 研究与生产的基石。 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 一句话说明 |
|------|-------|-----------|
| [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 185,772 | 早期自主 Agent 先驱，如今提供可访问的 AI 工具与构建平台。 |
| [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | 224,299 | 可变长 Agent，支持持续学习与扩展，社区关注度极高。 |
| [langchain-ai/langchain](https://github.com/langchain-ai/langchain) | 143,250 | Agent 工程平台，连接 LLM、工具与数据，构建复杂工作流。 |
| [CherryHQ/cherry-studio](https://github.com/CherryHQ/cherry-studio) | 49,293 | AI 生产力工具，集成智能聊天、自主 Agent 与 300+ 助手。 |
| [HKUDS/nanobot](https://github.com/HKUDS/nanobot) | 46,517 | 超轻量、可自托管的个人 AI Agent 框架，支持 WebUI、工具、记忆、MCP 与多 Agent 工作流。 |
| [zhayujie/CowAgent](https://github.com/zhayujie/CowAgent) | 46,278 | 开源超级 AI 助手，支持任务规划、工具调用、自我进化，一行命令安装。 |
| [different-ai/openwork](https://github.com/different-ai/openwork) | ⭐0 (+319 today) | Claude Cowork 的平替开源版，由 opencode 驱动，提供终端协作体验。 |

### 📦 AI 应用（具体产品、垂直场景解决方案）

| 项目 | Stars | 一句话说明 |
|------|-------|-----------|
| [open-webui/open-webui](https://github.com/open-webui/open-webui) | 147,642 | 用户友好的 AI 聊天界面，支持 Ollama 与 OpenAI API，可自托管。 |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | 107,614 | 让 AI Agent 能像人一样操作浏览器，实现网页自动任务。 |
| [harry0703/MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 101,197 | 利用 AI 一键生成高清短视频，踩中内容创作红利。 |
| [Panniantong/Agent-Reach](https://github.com/Panniantong/Agent-Reach) | ⭐0 (+645 today) | 给 AI Agent 安装“眼睛”，通过 CLI 读取 Twitter、Reddit、B 站等全网信息，零 API 费用。 |
| [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) | ⭐0 (+217 today) | AI Agent 技能，自动研究任意主题并生成跨平台摘要，适合舆情监控与竞品分析。 |
| [ZhuLinsen/daily_stock_analysis](https://github.com/ZhuLinsen/daily_stock_analysis) | 59,871 | LLM 驱动的多市场股票智能分析系统，支持定时运行与自动推送。 |
| [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) | 42,565 | 用 AI 将文档或主题转化为原生 PowerPoint 演示文稿，支持动画、图表与语音旁白。 |

### 🧠 大模型/训练（模型权重、训练框架、微调）

| 项目 | Stars | 一句话说明 |
|------|-------|-----------|
| [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | 100,389 | 从零实现 ChatGPT 类 LLM 的 PyTorch 教程，深度学习入门圣经。 |
| [open-compass/opencompass](https://github.com/open-compass/opencompass) | 7,259 | 超过 100 个数据集的 LLM 评测平台，支持 Llama、Qwen、GLM 等主流模型。 |
| [skyzh/tiny-llm](https://github.com/skyzh/tiny-llm) | 4,431 | 面向系统工程师的 LLM 推理服务课程，在 Apple Silicon 上构建迷你 vLLM。 |
| [AarambhDevHub/aarambh-studio](https://github.com/AarambhDevHub/aarambh-studio) | 59 | 纯 Rust 实现的 Decoder-only LLM，使用 Candle 框架，从 Tiny 到 Large 规模。 |
| [ai-glimpse/toyllm](https://github.com/ai-glimpse/toyllm) | 25 | 从零学习 LLM 的教学项目，适合动手实验。 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 一句话说明 |
|------|-------|-----------|
| [langgenius/dify](https://github.com/langgenius/dify) | 151,100 | 构建 Agentic 工作流与 RAG 管线的协作平台，支持多模型与自托管。 |
| [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | 86,634 | 领先的开源 RAG 引擎，融合 Agent 能力，为 LLM 提供优质上下文。 |
| [milvus-io/milvus](https://github.com/milvus-io/milvus) | 45,469 | 高性能云原生向量数据库，专为大规模向量 ANN 搜索设计。 |
| [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | 101,058 | 将代码库、文档、SQL 等转化为可查询的知识图谱，无需向量存储。 |
| [VectifyAI/PageIndex](https://github.com/VectifyAI/PageIndex) | 34,965 | 无向量 RAG 方案，基于推理的文档索引，大幅降低存储成本。 |
| [StarTrail-org/LEANN](https://github.com/StarTrail-org/LEANN) | 12,761 | 实现 97% 存储节省的 RAG 系统，100% 私有，可部署在个人设备上。 |
| [TencentCloud/TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) | ⭐0 (+604 today) | 团队级 AI Agent 记忆中心，将对话、文档、代码转化为可共享的四种记忆资产。 |

---

## 趋势信号分析

1. **DeepSeek 生态从模型走向基础设施**：`ds4` 和 `DeepSeek-Reasonix` 同时登榜 Trending，标志着 DeepSeek 不再只是模型层面的竞争，而是围绕其衍生的推理引擎、编码 Agent 等工具链正在形成生态。尤其 `ds4` 支持 4GB 单卡运行 DeepSeek 4，极大降低了本地部署门槛，可能带动边缘设备上运行大模型的潮流。

2. **Agent 技能“去中心化”与记忆持久化**：`Agent-Reach`、`last30days-skill`、`k-skill` 等技能仓库项目今日集中爆发，说明社区正从“构建单一 Agent”转向“复用和组合技能插件”。同时 `TencentDB-Agent-Memory` 将记忆提升到团队级，`mem0` 提供通用记忆层——Agent 的长期记忆正在成为独立基础设施。

3. **RAG 进入“无向量”范式**：`Graphify`、`PageIndex`、`LEANN` 等项目的崛起表明，社区不再迷信向量数据库。AST 解析、推理索引、知识图谱等替代方案在存储效率、准确性和隐私性上表现更优，尤其适合企业级代码库和文档管理场景。

4. **AI 低代码 + 生产力工具井喷**：`JeecgBoot` 低代码平台引入 AI Skills，`ppt-master` 用 AI 生成 PPT，`daily_stock_analysis` 实现智能投研——AI 正在快速渗透到传统软件工程和办公自动化领域，低代码平台成为 AI 能力的“新入口”。

5. **教育类项目持续吸引入门者**：尽管技术更新迅速，微软的 AI 初学者系列（`AI-For-Beginners`、`Generative AI for Beginners`）依然获得大量关注，说明系统化学习资源缺口依然存在，优质教学内容仍是社区刚需。

---

## 社区关注热点

- **DeepSeek 本地推理引擎（ds4）**：4GB 显存运行 70B 模型，是普通消费级显卡玩家运行大模型的最佳选择，值得所有想本地部署 DeepSeek 的开发者关注。
- **Agent 技能路由（Agent-Reach）**：零 API 费用读取多平台信息，相当于给 Agent 免费安装“浏览器”，对于构建自动化信息采集 Agent 极具实用价值。
- **团队级 Agent 记忆（TencentDB-Agent-Memory）**：腾讯云出品的开源项目，将记忆结构化、可共享，是解决 Agent 遗忘问题的企业级方案，适合多 Agent 协作场景。
- **无向量 RAG 方案（Graphify / PageIndex）**：不再依赖向量数据库，而是通过 AST 解析或推理索引实现检索，存储成本降低 90% 以上，适合对隐私和准确性要求高的场景。
- **AI 生成 PPT（ppt-master）**：原生支持 PowerPoint 形状、动画与图表，可直接用于商业汇报，有望成为 AI 办公套件中的爆款应用。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*