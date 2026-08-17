# Hugging Face 热门模型日报 2026-08-18

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-17 22:57 UTC

---

# Hugging Face 热门模型日报（2026-08-18）

## 今日速览

本周 Hugging Face 生态呈现出 **多模态与量化齐飞** 的格局。**Kimi-K3** 以 10,800 点赞登顶热度榜首，成为视觉语言模型的新星；**Qwen3.8-27B** 家族凭借 10,696 点赞紧随其后，并在社区催生了大量 GGUF、FP8 等量化版本，下载量突破 400 万。**MiniMax-H3** 视频生成模型生态持续壮大，衍生出 Turbo、LoRA 及 ComfyUI 单文件等多种形态，下载量高达 1400 万。**DeepSeek-V4** 系列双版本（Pro/Flash）同时上榜，显示 MoE 架构在推理效率上的优势。此外，**Muse-Glimmer-30B**、**NVIDIA Nemotron 3.5 Lightning** 等新模型也获得显著关注，社区微调（Uncensored 版本）和量化活动空前活跃。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **[Qwen/Qwen3.8-2.4T-A95B](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B)**  
 作者：Qwen | 点赞：1,041 | 下载：9,465  
 说明：Qwen3.5 系列的 2.4T 总参数量 MoE 模型（激活 95B），主打文本生成与对话，代表超大 MoE 开源的持续演进。

- **[deepseek-ai/DeepSeek-V4-Pro-0813](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813)**  
 作者：deepseek-ai | 点赞：573 | 下载：25,006  
 说明：DeepSeek V4 专业版，面向高精度文本生成任务，是 DeepSeek 系列最新开源主力。

- **[deepseek-ai/DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731)**  
 作者：deepseek-ai | 点赞：3,496 | 下载：1,978,298  
 说明：DeepSeek V4 Flash 版，更快推理速度，下载量近 200 万，深受社区欢迎。

- **[nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-NVFP4](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-NVFP4)**  
 作者：nvidia | 点赞：307 | 下载：231,271  
 说明：NVIDIA 的 30B 总参量 MoE 模型（3B 激活），采用 NVFP4 精度，主打高效推理，适合边缘部署。

- **[nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16)**  
 作者：nvidia | 点赞：169 | 下载：69,833  
 说明：同一模型的 BF16 全精度版本，适合需要高精度的场景。

- **[LiquidAI/LFM2.5-2.6B](https://huggingface.co/LiquidAI/LFM2.5-2.6B)**  
 作者：LiquidAI | 点赞：653 | 下载：147,270  
 说明：LiquidAI 的轻量级语言模型（2.6B），专注文本生成，在资源受限场景下表现突出。

- **[LiquidAI/LFM2.5-VL-3B](https://huggingface.co/LiquidAI/LFM2.5-VL-3B)**  
 作者：LiquidAI | 点赞：162 | 下载：6,816  
 说明：LFM2.5 的视觉语言版本（3B），支持图像+文本理解，是 LiquidAI 多模态布局的重要一步。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B)**  
 作者：Qwen | 点赞：10,696 | 下载：415,039  
 说明：Qwen3.5 系列 27B 多模态大模型，支持图像+文本理解与对话，是本周最受关注的基础模型之一。

- **[moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3)**  
 作者：moonshotai | 点赞：10,800 | 下载：2,163,953  
 说明：Kimi 最新多模态模型，以 10,800 点赞登顶，支持图像理解与特征提取，压缩权重后性能优异。

- **[meta-models/Muse-Glimmer-30B](https://huggingface.co/meta-models/Muse-Glimmer-30B)**  
 作者：meta-models | 点赞：1,661 | 下载：334,099  
 说明：Meta 出品的 30B 多模态模型（Muse 系列），擅长图像-文本联合理解，下载量超 33 万。

- **[MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)**  
 作者：MiniMaxAI | 点赞：4,086 | 下载：2,403,238  
 说明：MiniMax 最新视频生成模型，支持文本/图像/视频到视频，开辟了视频生成新范式。

- **[Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5)**  
 作者：Lightricks | 点赞：1,103 | 下载：465,529  
 说明：Lightricks 的图像/视频/文本到视频模型，LTX 系列迭代至 2.5，质量与速度俱佳。

- **[MiniMaxAI/MiniMax-Music3](https://huggingface.co/MiniMaxAI/MiniMax-Music3)**  
 作者：MiniMaxAI | 点赞：900 | 下载：10,375  
 说明：MiniMax 音乐生成模型，支持文本到音乐，是音频生成领域的重要发布。

- **[lightx2v/Minimax-h3-Turbo](https://huggingface.co/lightx2v/Minimax-h3-Turbo)**  
 作者：lightx2v | 点赞：583 | 下载：264,351  
 说明：MiniMax-H3 的 Turbo 加速版本，专注图像到视频生成，提升推理速度。

- **[Comfy-Org/MiniMax-H3](https://huggingface.co/Comfy-Org/MiniMax-H3)**  
 作者：Comfy-Org | 点赞：1,402 | 下载：14,015,769  
 说明：MiniMax-H3 的 ComfyUI 单文件封装，下载量超过 1400 万，极大降低了视频生成门槛。

- **[Comfy-Org/MiniMax-Music-3](https://huggingface.co/Comfy-Org/MiniMax-Music-3)**  
 作者：Comfy-Org | 点赞：166 | 下载：256,988  
 说明：MiniMax-Music3 的 ComfyUI 单文件版本，方便在 ComfyUI 中直接调用音乐生成。

- **[Gazingstars123/Anima-2.9B](https://huggingface.co/Gazingstars123/Anima-2.9B)**  
 作者：Gazingstars123 | 点赞：233 | 下载：23,202  
 说明：Anima 系列 2.9B 文本到图像模型，单文件扩散模型，适合 ComfyUI 使用。

- **[dots-studio/dots3-note-prev](https://huggingface.co/dots-studio/dots3-note-prev)**  
 作者：dots-studio | 点赞：205 | 下载：633  
 说明：dots3 预览版多模态模型，支持图像-文本交互，注重笔记场景。

### 📦 微调与量化（社区微调、GGUF、AWQ、LoRA）

- **[unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF)**  
 作者：unsloth | 点赞：1,623 | 下载：2,727,609  
 说明：Qwen3.8-27B 的 GGUF 量化版，由 unsloth 提供，下载量超 270 万，本地部署首选。

- **[Qwen/Qwen3.8-27B-FP8](https://huggingface.co/Qwen/Qwen3.8-27B-FP8)**  
 作者：Qwen | 点赞：527 | 下载：495,646  
 说明：官方 FP8 量化版本，在保持精度前提下大幅降低显存需求。

- **[orcarouter/Qwen3.8-27B-Uncensored-FP8](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-FP8)**  
 作者：orcarouter | 点赞：429 | 下载：15,812  
 说明：社区无审查微调版 + FP8 量化，满足特定场景需求。

- **[JonathanColetti/Qwen3.8-27B-Uncensored-GGUF](https://huggingface.co/JonathanColetti/Qwen3.8-27B-Uncensored-GGUF)**  
 作者：JonathanColetti | 点赞：296 | 下载：357,701  
 说明：另一社区无审查微调的 GGUF 版本，下载量超 35 万，说明 Uncensored 需求旺盛。

- **[unsloth/Muse-Glimmer-30B-GGUF](https://huggingface.co/unsloth/Muse-Glimmer-30B-GGUF)**  
 作者：unsloth | 点赞：470 | 下载：755,125  
 说明：Muse-Glimmer-30B 的 GGUF 量化版，下载量 75 万，方便本地运行多模态模型。

- **[unsloth/Qwen3.8-27B-NVFP4](https://huggingface.co/unsloth/Qwen3.8-27B-NVFP4)**  
 作者：unsloth | 点赞：236 | 下载：378,177  
 说明：Qwen3.8-27B 的 NVFP4 量化版，适配 NVIDIA 新硬件格式。

- **[DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GG

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*