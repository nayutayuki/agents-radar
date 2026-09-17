# Hugging Face 热门模型日报 2026-09-17

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-17 00:52 UTC

---

# 🚀 Hugging Face 热门模型日报 | 2026-09-17

## 📡 今日速览

- **Qwen3.8-27B 系列持续统治排行榜**，原生模型以 15,400 点赞、760 万下载量断层领先，其 GGUF 量化版（unsloth）下载量高达 886 万，足见社区对高效部署的强烈需求。
- **多模态视频生成迎来爆发**：MiniMax-H3（5,380 点赞）与 Lightricks LTX-2.5（4,112 点赞）同时冲入前五，标志着文本/图像到视频的成熟化落地。
- **DeepSeek-V4.1-Flash 正式亮相**，作为最新一代 image-text-to-text 模型，以 2,855 点赞登榜，并迅速出现社区 uncensored 及 FP8 微调版本，生态衍生速度极快。
- **音乐生成赛道出现新星**：m-a-p 的 YuE2-3B（638 点赞）及 Comfy-Org 的 ComfyUI 适配版本共同推动文本到音乐生成走向实用化。
- **量化与微调活动空前活跃**：多个 Qwen3.8-27B 的 GGUF 变体、DeepSeek-V4.1 的 FP8 去限制版、以及各种“Turbo”微调版本占据榜单大量席位，显示社区正围绕头部模型进行深度定制。

---

## 🧠 语言模型（LLM、对话、指令微调）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [**Edge0/Edge0-35B-A3B-preview**](https://huggingface.co/Edge0/Edge0-35B-A3B-preview) | Edge0 | 3,068 | 27,759 | 35B 参数但仅 3B 激活的 MoE 架构，主打边缘推理效率，预览版吸引大量关注。 |
| [**openbmb/MiniCPM5-2B**](https://huggingface.co/openbmb/MiniCPM5-2B) | openbmb | 1,505 | 324,322 | 2B 参数小模型，采用 LLaMA 架构，在资源受限场景下表现优秀，下载量极高。 |
| [**nex-agi/Nex-N2.5-mini**](https://huggingface.co/nex-agi/Nex-N2.5-mini) | nex-agi | 819 | 6,837 | 基于 Qwen3.5-MoE 的 mini 版，同时支持图像-文本-文本，主打轻量多模态对话。 |
| [**TokenRhythm/NeoHorse-1-4B**](https://huggingface.co/TokenRhythm/NeoHorse-1-4B) | TokenRhythm | 2,105 | 16,163 | 1.4B 参数 agentic 模型，基于 Qwen3.5 微调，专注于自主任务规划。 |
| [**XHToken/Spark-X2.5-4B**](https://huggingface.co/XHToken/Spark-X2.5-4B) | XHToken | 1,233 | 27,191 | 4B 参数 Spark2.5 架构的通用语言模型，社区关注度稳步上升。 |
| [**meta-llama/Llama-3.1-8B-Instruct**](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | meta-llama | 7,658 | 5,861,705 | Meta 经典 8B 指令模型，持续作为社区基准和微调起点，长期占据热门榜。 |
| [**openai-community/gpt2**](https://huggingface.co/openai-community/gpt2) | openai-community | 4,119 | 15,584,259 | 经典 GPT-2 模型，凭借超高下载量（1,558 万）稳居常青榜，常被用于教学与实验。 |

---

## 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [**deepseek-ai/DeepSeek-V4.1-Flash**](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek-ai | 2,855 | 366,459 | 最新一代图像-文本到文本模型，DeepSeek 原厂发布，兼具推理速度与视觉理解能力。 |
| [**Qwen/Qwen3.8-27B**](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 15,400 | 7,667,556 | 全能多模态对话模型（27B），支持图像、文本、对话，本周人气与下载双料冠军。 |
| [**Lightricks/LTX-2.5**](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 4,112 | 1,616,663 | 单文件扩散模型，实现图像/文本/视频到视频转换，视频生成领域的标杆之一。 |
| [**m-a-p/YuE2-3B**](https://huggingface.co/m-a-p/YuE2-3B) | m-a-p | 638 | 9,391 | 3B 参数音乐生成模型，引入符号规划与 agentic 编辑，文本到音乐创作进入新阶段。 |
| [**tencent/AuK**](https://huggingface.co/tencent/AuK) | tencent | 269 | 2,753 | 腾讯推出的零样本语音克隆与 TTS 模型，轻量级音频生成新选择。 |
| [**MiniMaxAI/MiniMax-H3**](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 5,380 | 4,689,062 | 文本/图像到视频生成模型，Diffusers 生态集成，下载量近 470 万，视频生成热门之选。 |
| [**Qwen/Qwen3.8-Flash-Next**](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 5,310 | 689,347 | Qwen4 实验版，继承 3.8 系列的多模态能力，定位为下一代快速推理模型。 |
| [**WarmBloodAban/Minimax-h3_Singularity**](https://huggingface.co/WarmBloodAban/Minimax-h3_Singularity) | WarmBloodAban | 450 | 164,451 | 基于 MiniMax-H3 的视频生成社区微调版，引入 Singularity 风格增强。 |
| [**dealignai/DeepSeek-V4.1-Flash-UNCENSORED-FP8**](https://huggingface.co/dealignai/DeepSeek-V4.1-Flash-UNCENSORED-FP8) | dealignai | 229 | 6,826 | DeepSeek-V4.1 的 uncensored + FP8 量化版，满足特定社区需求。 |
| [**Agnes-AI/Agnes-3.0-Flash**](https://huggingface.co/Agnes-AI/Agnes-3.0-Flash) | Agnes-AI | 197 | 1,063 | 新兴多模态对话模型（Agnes 系列），主打快速推理。 |
| [**ukisai/Swift-Qwen3.8-27b**](https://huggingface.co/ukisai/Swift-Qwen3.8-27b) | ukisai | 330 | 2,753 | 基于 Qwen3.8-27B 的 Swift 版本，专为快速部署优化。 |
| [**zai-org/GLM-5.3-Flash**](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 2,392 | 2,244,085 | GLM-5 系列新一代多模态对话模型，支持图像-文本，下载量已超 224 万。 |
| [**Comfy-Org/YuE2**](https://huggingface.co/Comfy-Org/YuE2) | Comfy-Org | 150 | 59,231 | YuE2 的 ComfyUI 适配单文件，让音乐生成通过节点工作流轻松使用。 |
| [**Alissonerdx/Minimax-H3-ComfyUI**](https://huggingface.co/Alissonerdx/Minimax-H3-ComfyUI) | Alissonerdx | 202 | 18,680 | MiniMax-H3 的 ComfyUI LoRA 插件，扩展视频生成的控制能力。 |

---

## 🔧 专用模型（代码、数学、医疗、嵌入）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [**sentence-transformers/all-MiniLM-L6-v2**](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) | sentence-transformers | 6,024 | 256,481,161 | 轻量级句子嵌入模型，2.56 亿总下载量，NLP 检索与语义匹配的常青树。 |
| [**openai/clip-vit-base-patch32**](https://huggingface.co/openai/clip-vit-base-patch32) | openai | 1,547 | 21,790,053 | OpenAI 经典 CLIP 模型，零样本图像分类与多模态检索的基准。 |
| [**google-bert/bert-base-uncased**](https://huggingface.co/google-bert/bert-base-uncased) | google-bert | 3,354 | 47,693,504 | BERT 基础模型，预训练 NLP 的根基，长期被下游任务引用。 |
| [**facebook/mms-300m**](https://huggingface.co/facebook/mms-300m) | facebook | 554 | 22,119 | 大规模多语言语音预训练模型（wav2vec2），支持 300+ 语言。 |
| [**distilbert/distilbert-base-uncased**](https://huggingface.co/distilbert/distilbert-base-uncased) | distilbert | 1,459 | 7,410,664 | BERT 蒸馏版，60% 速度提升的同时保留 97% 性能，轻量部署优选。 |

---

## 📦 微调与量化（社区微调、GGUF、AWQ）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [**ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF**](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF) | ISTA-DASLab | 1,194 | 956,964 | 采用 GSQ 混合精度量化的 GGUF 版，专为低比特推理优化。 |
| [**DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF**](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF) | DavidAU | 793 | 1,049,586 | 名称超长的社区微调 + GGUF 版，融合多种风格（Coder、Uncensored），下载量破百万。 |
| [**unsloth/Qwen3.8-27B-GGUF**](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF) | unsloth | 4,218 | 8,856,150 | unsloth 官方量化版，下载量 885 万，成为 Qwen3.8 本地部署的首选。 |
| [**ukisai/Swift-Qwen3.8-27B-GGUF**](https://huggingface.co/ukisai/Swift-Qwen3.8-27B-GGUF) | ukisai | 182 | 55,309 | 另一款 Qwen3.8-27B 的 GGUF 版本，强调高效思考与 llama.cpp 兼容。 |

---

## 🌐 生态信号

当前生态呈现 **“一超多强，量化包围”** 的格局。 **Qwen 家族** 无疑是本周最大赢家：Qwen3.8-27B 原生模型、Flash-Next 实验版、以及至少 4

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*