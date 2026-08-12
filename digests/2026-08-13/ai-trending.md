# AI 开源趋势日报 2026-08-13

> 数据来源: GitHub Trending + GitHub Search API | 生成时间: 2026-08-12 23:21 UTC

---

# AI 开源趋势日报 | 2026-08-13

## 今日速览

今日 GitHub 开源社区中，**AI 智能体/工作流** 类项目持续霸榜，`agency-agents` 和 `orca` 分别以 +1969、+1215 的日增 stars 领跑，表明开发者对 **多智能体协作** 和 **代理编排** 的需求旺盛。**边缘 AI** 方向出现新星：`needle` 仅 14MB 的基础模型专为手机、穿戴设备设计，日增 346 stars。**生成式 AI 应用** 方面，`LTX-2` 开源音频‑视频生成模型，`ppt-master` 实现文档一键转原生 PPT，获得广泛关注。**RAG/知识库** 赛道中 `ragflow` 继续稳扎稳打，日增 182 stars，同时 `semantica` 作为图原生基础设施首次登榜，引发对“可问责 AI 系统”的讨论。

---

## 各维度热门项目

### 🔧 AI 基础工具（框架、SDK、推理引擎、CLI）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [semantica-agi/semantica](https://github.com/semantica-agi/semantica) | +834 today | 图原生基础设施，为上下文和可问责 AI 系统提供底层支持。 |
| [NVIDIA-NeMo/Switchyard](https://github.com/NVIDIA-NeMo/Switchyard) | +370 today | NVIDIA 出品的 Rust 推理工具，聚焦高性能 AI 引擎。 |
| [embabel/embabel-agent](https://github.com/embabel/embabel-agent) | +29 today | JVM 上的 Agent 框架，为 Java 生态提供 LLM 集成能力。 |
| [cactus-compute/needle](https://github.com/cactus-compute/needle) | +346 today | 仅 14MB 的基础模型，面向手机、可穿戴设备、机器人等微小设备。 |
| [0xPlaygrounds/rig](https://github.com/0xPlaygrounds/rig) | 8,251 | 纯 Rust 的 LLM 应用构建框架，模块化、可扩展。 |

### 🤖 AI 智能体/工作流（Agent 框架、自动化、多智能体）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents) | +1,969 today | 一套完整的 AI 代理团队，含前端、社区运营、质量检查等专精代理。 |
| [stablyai/orca](https://github.com/stablyai/orca) | +1,215 today | 并行代理 ADE，支持用户用自己的订阅运行任意编码代理，跨桌面/移动端。 |
| [paperclipai/paperclip](https://github.com/paperclipai/paperclip) | +573 today | 管理工作中代理的开源应用，让团队协作更高效。 |
| [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 186,562 | 给每个人可访问的 AI 代理，愿景是让 AI 工具人人可用。 |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | 108,965 | 让 AI 代理轻松访问网页，自动化在线任务。 |

### 📦 AI 应用（具体应用产品、垂直场景解决方案）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) | 45,530 (+364 today) | AI 将文档或主题转为原生 PowerPoint 幻灯片，支持动画、图表、语音旁白。 |
| [Lightricks/LTX-2](https://github.com/Lightricks/LTX-2) | +40 today | 官方发布的音频‑视频生成模型，支持 LoRA 微调。 |
| [shiyu-coder/Kronos](https://github.com/shiyu-coder/Kronos) | +277 today | 金融市场语言的基础模型，面向金融数据分析和预测。 |
| [macro-inc/macro](https://github.com/macro-inc/macro) | +325 today | 统一工作空间（邮件、聊天、文档、任务、代理、CRM），由共享 AI 记忆链接。 |
| [harry0703/MoneyPrinterTurbo](https://github.com/harry0703/MoneyPrinterTurbo) | 102,809 | 利用 AI 大模型一键生成高清短视频，主题或关键词驱动。 |

### 🧠 大模型/训练（模型权重、训练框架、微调工具）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [cactus-compute/needle](https://github.com/cactus-compute/needle) | +346 today | 14MB 超小基础模型，专为低功耗设备推理优化。 |
| [shiyu-coder/Kronos](https://github.com/shiyu-coder/Kronos) | +277 today | 金融领域基础模型，理解市场语言。 |
| [Lightricks/LTX-2](https://github.com/Lightricks/LTX-2) | +40 today | 开源音频‑视频生成模型，支持推理和 LoRA 训练。 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | 54,620 | 2 小时从零训练 64M 参数的小 LLM，适合学习。 |
| [skyzh/tiny-llm](https://github.com/skyzh/tiny-llm) | 4,477 | 在 Apple Silicon 上学习 LLM 推理，构建微型 vLLM。 |

### 🔍 RAG/知识库（向量数据库、检索增强、知识管理）

| 项目 | Stars | 一句话说明 |
|------|-------|------------|
| [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | 87,526 (+182 today) | 领先的开源 RAG 引擎，融合 Agent 能力，为 LLM 提供上下文层。 |
| [Mintplex-Labs/anything-llm](https://github.com/Mintplex-Labs/anything-llm) | 64,661 | 本地优先的 Agent 体验，支持文档、向量、多模型。 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 63,132 | 通用 AI 代理记忆层，跨会话持久化。 |
| [langgenius/dify](https://github.com/langgenius/dify) | 152,245 | 构建 Agentic 工作流和 RAG 管线的协作平台，支持多模型。 |
| [open-webui/open-webui](https://github.com/open-webui/open-webui) | 148,612 | 用户友好的 AI 界面，支持 Ollama、OpenAI 等后端。 |

---

## 趋势信号分析

今日热榜中 **AI 智能体/工作流** 类项目获得爆发性关注：`agency-agents` 日增近 2000 stars，`orca` 日增超 1200，表明开发者不再满足于单一代理，而是追求 **多代理编排、并行执行** 的成熟平台。**边缘 AI** 方向首次出现重量级项目 `needle`（14MB 基础模型），其日增 346 stars 说明社区对 **超轻量、本地推理** 的强烈需求，尤其适配手机、IoT 设备。**生成式 AI 应用** 中 `ppt-master` 与 `LTX-2` 分别代表 **生产力工具** 和 **多模态生成** 两个热门方向，前者日增 364 stars 证明“AI 生成原生文档”场景正在被广泛接受。此外，`semantica` 作为 **图原生 AI 基础设施** 首次登榜，暗示社区对 **可解释、可问责的 AI 系统** 的兴趣上升，可能与近期大模型安全法规讨论有关。整体来看，今日热榜体现了 **从“能用”到“好用”** 的转变：开发者更关注落地场景、轻量部署和代理协作。

---

## 社区关注热点

- **`agency-agents`**：全栈 AI 代理团队，包含前端、社区运营、质量检查等专精代理，适合快速搭建多角色自动化工作流。  
- **`orca`**：并行代理 ADE，支持用户用自己的订阅运行任意编码代理，跨桌面/移动端，是“代理即服务”的雏形。  
- **`needle`**：14MB 超小基础模型，专为手机、穿戴设备、机器人设计，边缘 AI 方向的重要里程碑。  
- **`ppt-master`**：AI 将文档/主题转为原生 PPT，支持动画、图表、语音旁白，直接提升办公生产力，商业化潜力大。  
- **`ragflow`**：持续高频迭代的 RAG 引擎，融合 Agent 能力，是构建企业级知识问答系统的首选开源方案。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*