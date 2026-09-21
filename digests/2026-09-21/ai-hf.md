# Hugging Face 热门模型日报 2026-09-21

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-21 00:29 UTC

---

# Hugging Face 热门模型日报（2026-09-21）

## 今日速览

本周 Hugging Face 榜单被 **Qwen 3.8 系列** 统治：原始多模态模型 Qwen3.8-27B 以 15,861 点赞、731 万下载登顶，其 GGUF 和微调版本也占据多个席位。**视频生成** 赛道持续升温：MiniMax-H3（5525 赞）和 Lightricks LTX-2.5（4552 赞）双双进入前十。**极致量化** 成为新趋势：prism-ml 的 2-bit 三元量化模型（Ternary-Bonsai）和 ISTA-DASLab 的 GSQ-RCO 混合精度量化方案引发社区关注。此外，**边缘推理** 方向的 MoE 模型 Edge0-35B-A3B（3549 赞）以及 **音乐生成** 模型 YuE2-3B（915 赞）同样表现出色。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

| 模型 | 作者 | 👍 | 📥 | 一句话说明 |
|------|------|----|----|------------|
| [Qwen-2.5-1B-RLCD](https://huggingface.co/harshatheg/Qwen-2.5-1B-RLCD) | harshatheg | 476 | 0 | 在 Apple Silicon 上实现约束解码与并行生成的小型高效语言模型。 |
| [Xing4.0-29B-A4B](https://huggingface.co/XingChen-AGI/Xing4.0-29B-A4B) | XingChen-AGI | 885 | 12,617 | 4 比特活跃参数的 MoE 对话模型，兼顾性能与推理速度。 |
| [MiniCPM5-2B](https://huggingface.co/openbmb/MiniCPM5-2B) | openbmb | 1,627 | 420,622 | 开源 Llama 架构 2B 参数小模型，适合资源受限场景部署。 |
| [Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | meta-llama | 7,769 | 5,910,102 | Meta 经典 8B 对话模型，常青树，长期占据下载榜。 |
| [NeoHorse-1-9B](https://huggingface.co/TokenRhythm/NeoHorse-1-9B) | TokenRhythm | 980 | 11,913 | 基于 Qwen3.5 微调的 9B 智能体模型，适用于工具调用任务。 |
| [Edge0-35B-A3B-preview](https://huggingface.co/Edge0/Edge0-35B-A3B-preview) | Edge0 | 3,549 | 76,669 | 35B 参数仅 3B 活跃的 MoE 模型，专为边缘设备推理优化，支持 MLX。 |
| [Atria-Dawn-Preview](https://huggingface.co/internlm/Atria-Dawn-Preview) | internlm | 209 | 895 | 商汤最新 MoE 语言模型预览版，混合 DSA 架构，中英双语。 |

### 🎨 多模态与生成（图像、视频、音频、文本到 X）

| 模型 | 作者 | 👍 | 📥 | 一句话说明 |
|------|------|----|----|------------|
| [DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek-ai | 3,432 | 496,684 | DeepSeek 最新多模态 Flash 模型，支持图像+文本输入，强调快速推理。 |
| [Qwen-Image-2.1](https://huggingface.co/Qwen/Qwen-Image-2.1) | Qwen | 740 | 183 | 通义千问最新文生图模型，支持图像编辑任务，Diffusers 格式。 |
| [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 15,861 | 7,331,932 | **本周榜单冠军**，通义千问第三代多模态模型，支持图文对话，性能强劲。 |
| [YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B) | m-a-p | 915 | 17,403 | 基于 Symbolic Planning 的 3B 音乐生成模型，支持智能体化编辑。 |
| [LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 4,552 | 1,609,559 | 来自 Lightricks 的图像/文本到视频扩散模型，支持视频到视频转换。 |
| [Swift-Qwen3.8-27b](https://huggingface.co/ukisai/Swift-Qwen3.8-27b) | ukisai | 509 | 10,962 | 基于 Qwen3.8-27B 的 Swift 框架微调版，优化推理效率。 |
| [Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 5,492 | 761,112 | 通义千问下一代 Flash 实验模型，预计为 Qwen4 系列前奏。 |
| [Qwen-Image-2.1 (ComfyUI)](https://huggingface.co/Comfy-Org/Qwen-Image-2.1) | Comfy-Org | 258 | 120 | Qwen-Image-2.1 的 ComfyUI 单文件版，方便可视化工作流。 |
| [MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 5,525 | 4,057,444 | MiniMax 高质量视频生成模型，支持图/文生成视频，下载量极高。 |
| [ZDTaichu5.0-9B](https://huggingface.co/TaichuAI/ZDTaichu5.0-9B) | TaichuAI | 212 | 3,750 | 中科院紫东太初 5.0 视觉语言模型，强调空间推理能力。 |
| [Minimax-h3_Singularity](https://huggingface.co/WarmBloodAban/Minimax-h3_Singularity) | WarmBloodAban | 571 | 242,751 | MiniMax-H3 的社区微调版，聚焦电影级视频风格。 |
| [GLM-5.3-Flash](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 2,499 | 3,109,084 | 智谱 GLM 5.3 Flash 多模态模型，对话能力强，下载量超过 300 万。 |

### 🔧 专用模型（代码、数学、医疗、嵌入）

| 模型 | 作者 | 👍 | 📥 | 一句话说明 |
|------|------|----|----|------------|
| [laya](https://huggingface.co/convaiinnovations/laya) | convaiinnovations | 1,089 | 

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*