# Hugging Face 热门模型日报 2026-09-18

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-18 00:46 UTC

---

# Hugging Face 热门模型日报 (2026-09-18)

## 📌 今日速览

- **Qwen系列统治榜单**：Qwen3.8-27B 以 **15,533 点赞** 和 **745万下载** 断层领跑，其量化版、微调版、实验版（如 Flash-Next）占据排行榜半壁江山。
- **多模态与视频生成爆发**：Lightricks LTX-2.5（image-to-video）和 MiniMax-H3 双双进入点赞前五，视频生成模型下载量均超百万。
- **MoE 架构与边缘推理受追捧**：Edge0/Edge0-35B-A3B-preview 作为 **35B 参数但仅激活 3B** 的 MoE 模型，以 3,306 点赞位列第三，反映社区对高效推理的强烈需求。
- **量化生态高度活跃**：GGUF 版本（如 unsloth/Qwen3.8-27B-GGUF）下载量超 820 万，低比特量化（如 Ternary-Bonsai-2-27B 的 2-bit）开始进入视野。

## 🧠 语言模型（LLM、对话、指令微调）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 15,533 | 7,456,257 | 阿里最新多模态对话模型，支持图像与文本混合输入，本周最热门模型。 |
| [Edge0/Edge0-35B-A3B-preview](https://huggingface.co/Edge0/Edge0-35B-A3B-preview) | Edge0 | 3,306 | 37,131 | 35B 参数 MoE 模型，仅激活 3B 即可推理，专为边缘设备优化。 |
| [deepseek-ai/DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek-ai | 3,005 | 390,657 | DeepSeek 最新多模态版本，融合图像理解与文本生成，推理速度快。 |
| [openbmb/MiniCPM5-2B](https://huggingface.co/openbmb/MiniCPM5-2B) | openbmb | 1,537 | 329,713 | 2B 参数小模型，基于 Llama 架构，适合端侧部署，性价比高。 |
| [XHToken/Spark-X2.5-4B](https://huggingface.co/XHToken/Spark-X2.5-4B) | XHToken | 1,261 | 28,347 | 4B 参数的 Spark 系列新模型，专注高效文本生成。 |
| [TokenRhythm/NeoHorse-1-4B](https://huggingface.co/TokenRhythm/NeoHorse-1-4B) | TokenRhythm | 2,316 | 19,789 | 基于 Qwen3.5 微调的 4B Agent 模型，强调工具调用能力。 |
| [TokenRhythm/NeoHorse-1-9B](https://huggingface.co/TokenRhythm/NeoHorse-1-9B) | TokenRhythm | 866 | 9,856 | 同上家族的 9B 版本，Agent 性能更强。 |
| [Qwen/Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 5,364 | 706,052 | Qwen 实验性版本，代号 qwen4_exp，探索下一代对话模型架构。 |
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | meta-llama | 7,695 | 5,887,953 | Meta 经典 8B 指令模型，长期位居前十，社区标杆。 |
| [zai-org/GLM-5.3-Flash](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 2,427 | 2,446,115 | 智谱最新 Flash 版，采用 glm5_next 架构，支持图像理解与对话。 |
| [openai-community/gpt2](https://huggingface.co/openai-community/gpt2) | openai-community | 4,136 | 15,558,794 | 经典 GPT-2 模型，虽老但下载量巨大，常被用于教学和基线。 |
| [nex-agi/Nex-N2.5-mini](https://huggingface.co/nex-agi/Nex-N2.5-mini) | nex-agi | 832 | 7,347 | 基于 Qwen3.5 MoE 的 Mini 模型，兼具文本与图像理解。 |
| [Agnes-AI/Agnes-3.0-Flash](https://huggingface.co/Agnes-AI/Agnes-3.0-Flash) | Agnes-AI | 214 | 1,223 | Agnes 新版本 Flash 模型，专注快速对话响应。 |
| [TaichuAI/ZDTaichu5.0-9B](https://huggingface.co/TaichuAI/ZDTaichu5.0-9B) | TaichuAI | 171 | 476 | 中科院旗下空间推理视觉语言模型，9B 参数，强调空间理解。 |
| [ukisai/Swift-Qwen3.8-27b](https://huggingface.co/ukisai/Swift-Qwen3.8-27b) | ukisai | 392 | 3,221 | 社区微调的 Qwen3.8-27B 版本，优化了推理效率。 |

## 🎨 多模态与生成（图像、视频、音频、文本→X）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 4,233 | 1,602,865 | 多合一视频生成模型，支持图生视频、文生视频、视频编辑。 |
| [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 5,418 | 4,576,471 | MiniMax 最新视频生成模型，支持图文混合输入生成高质量视频。 |
| [WarmBloodAban/Minimax-h3_Singularity](https://huggingface.co/WarmBloodAban/Minimax-h3_Singularity) | WarmBloodAban | 478 | 181,811 | 社区微调的 MiniMax-H3 变体，增强视频生成效果。 |
| [m-a-p/YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B) | m-a-p | 720 | 11,626 | 音乐生成模型，支持符号规划与智能音乐编辑。 |
| [Comfy-Org/YuE2](https://huggingface.co/Comfy-Org/YuE2) | Comfy-Org | 168 | 79,302 | YuE2 的 ComfyUI 版本，方便在节点工作流中使用音乐生成。 |

## 🔧 专用模型（嵌入、语音、代码、数学等）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) | sentence-transformers | 6,048 | 255,618,777 | 轻量级语义嵌入模型，2.5 亿次下载，文本相似度任务的标配。 |
| [tencent/AuK](https://huggingface.co/tencent/AuK) | tencent | 289 | 3,024 | 腾讯零样本语音克隆模型，输入文本即可合成指定人声。 |
| [facebook/mms-300m](https://huggingface.co/facebook/mms-300m) | facebook | 565 | 22,039 | 元数据多语种语音识别模型（wav2vec2），支持 300+ 语言。 |

## 📦 微调与量化（GGUF、AWQ、低比特推演）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF) | unsloth | 4,267 | 8,205,000 | Qwen3.8-27B 的 GGUF 量化版，下载量极高，适合本地推理。 |
| [ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF) | ISTA-DASLab | 1,259 | 1,027,602 | 采用 GSQ+RCO 混合精度量化方案，兼顾速度与质量。 |
| [DavidAU/Qwen3.8-27B-TURBO-...-GGUF](https://hugging

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*