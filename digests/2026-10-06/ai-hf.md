# Hugging Face 热门模型日报 2026-10-06

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-10-06 02:29 UTC

---

# Hugging Face 热门模型日报（2026-10-06）

## 🌟 今日速览

今日 Hugging Face 榜单由 **Qwen 家族** 全面主导：旗舰模型 **Qwen3.8-27B** 以 17,041 点赞高居榜首，其增强版 **Qwen3.8-Flash-Next** 以 5,940 点赞紧随其后。多模态视频生成模型 **Lightricks/LTX-2.5**（6,507 点赞）成为本周最大黑马，引发社区对图像到视频工具的热切关注。**DeepSeek V4.1 Flash** 以 4,132 点赞代表国产开源模型持续发力。此外，**GGUF 量化生态** 异常活跃，围绕 Qwen3.8、Qwen-Image-2.1 和 27B 规模的社区微调版本层出不穷，显著降低了部署门槛。

---

## 📋 热门模型分类盘点

### 🧠 语言模型（LLM、对话、指令微调）

| 模型 | 作者 | 👍 / 📥 | 一句话说明 |
|------|------|---------|------------|
| [Kolibri-1](https://huggingface.co/Aleph-Alpha/Kolibri-1) | Aleph-Alpha | 632 / 2,453 | 采用 MoE 架构的推理型语言模型，潜力受早期用户关注 |

*说明：本周语言模型原版较少，社区焦点集中在多模态及量化版本上。*

---

### 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型 | 作者 | 👍 / 📥 | 一句话说明 |
|------|------|---------|------------|
| [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | **17,041** / 6,758,884 | 阿里系多模态对话旗舰，支持图像+文本输入，兼具极强语言与视觉理解 |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | **6,507** / 1,645,444 | 全能视频生成模型（图→视频、文→视频、视频→视频），本周最热新作 |
| [Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | **5,940** / 1,530,359 | Qwen 最新实验版（qwen4_exp 标签），性能更快的轻量多模态模型 |
| [DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek-ai | **4,132** / 869,321 | 深度求索的最新多模态快速推理版，兼顾速度与质量 |
| [Qwen-Image-2.1](https://huggingface.co/Qwen/Qwen-Image-2.1) | Qwen | 3,005 / 94,556 | 阿里官方文生图模型，支持图片编辑功能，生态丰富 |
| [TaichuAI/ZDTaichu5.0-9B](https://huggingface.co/TaichuAI/ZDTaichu5.0-9B) | TaichuAI | 2,876 / 12,782 | 中科院系 9B 多模态模型，主打空间推理能力 |
| [Cloudflare/clef](https://huggingface.co/Cloudflare/clef) | Cloudflare | 1,513 / 5,416 | 云服务商推出的图像+文本理解模型，标签`qwen3_5`暗示基于 Qwen |
| [Alissonerdx/BFS-Best-Face-Swap](https://huggingface.co/Alissonerdx/BFS-Best-Face-Swap) | Alissonerdx | 1,215 / 212,575 | 基于 Qwen-Image 的换脸 LoRA，下载量高，社区实用工具 |
| [Viggle/Qwen-Image-2.1-viggle-turbo](https://huggingface.co/Viggle/Qwen-Image-2.1-viggle-turbo) | Viggle | 618 / 286,885 | 针对 Qwen-Image 加速的 LoRA，专为 ComfyUI 优化 |
| [Cloudflare/clef-flash](https://huggingface.co/Cloudflare/clef-flash) | Cloudflare | 536 / 8,075 | clef 的轻量版，主打更快推理 |
| [autotrust/JEV-27B-VL](https://huggingface.co/autotrust/JEV-27B-VL) | autotrust | 644 / 1,278,569 | 27B 多模态模型，下载量超百万，社区微调后关注度高 |
| [pablodawson/MiniMax-H3-360-Orbit-LoRA](https://huggingface.co/pablodawson/MiniMax-H3-360-Orbit-LoRA) | pablodawson | 217 / 6,930 | 为 MiniMax H3 视频模型添加 360° 轨道效果的 LoRA |
| [akatz-ai/MiniMax-H3-Character-Swap-LoRA](https://huggingface.co/akatz-ai/MiniMax-H3-Character-Swap-LoRA) | akatz-ai | 309 / 18,138 | 基于 MiniMax H3 的角色交换 LoRA，用于视频编辑 |

---

### 🔧 专用模型（代码、数学、医疗、嵌入、分类等）

| 模型 | 作者 | 👍 / 📥 | 一句话说明 |
|------|------|---------|------------|
| [convaiinnovations/laya](https://huggingface.co/convaiinnovations/laya) | convaiinnovations | **5,244** / 11,733 | 文本分类模型，主打“校准决策”，标签 `system-one` 暗示推理改进 |
| [Contrastive-LM/CLM-v0.1-8B](https://huggingface.co/Contrastive-LM/CLM-v0.1-8B) | Contrastive-LM | 740 / 3,715 | 基于对比学习的文本排序/验证器，用于重新排序或评估 |
| [nvidia/Nemotron-3-Diarization](https://huggingface.co/nvidia/Nemotron-3-Diarization) | nvidia | 701 / 55,491 | NVIDIA 出品的人声活动检测模型，用于说话人日志 |
| [PSRben/VisionHOPE](https://huggingface.co/PSRben/VisionHOPE) | PSRben | 426 / 1,654 | 图像分类模型，带有学术论文引用（arXiv:2609.33325），研究方向 |
| [SupersonicLabs/Julia-1](https://huggingface.co/SupersonicLabs/Julia-1) | SupersonicLabs | 442 / 3,898 | 多语言文本分类决策模型，标签含 `decision-model` |
| [autotrust/GEV-26B-Decide](https://huggingface.co/autotrust/GEV-26B-Decide) | autotrust | 471 / 446,527 | 基于 Gemma 4 的文本分类模型，实际带图像输入，下载量可观 |
| [FermionResearch/Phonon-2](https://huggingface.co/FermionResearch/Phonon-2) | FermionResearch | 234 / 3,063 | 针对 Apple Silicon 优化的语音识别模型，基于 Parakeet |

---

### 📦 微调与量化（社区微调、GGUF、AWQ、EXL3）

| 模型 | 作者 | 👍 / 📥 | 一句话说明 |
|------|------|---------|------------|
| [prism-ml/Ternary-Bonsai-2-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf) | prism-ml | 2,459 / **4,120,718** | 27B 参数三值量化（2-bit）GGUF 模型，极致压缩，下载量高 |
| [abenzerps/Qwen-Image-2.1-Uncensored-GGUF](https://huggingface.co/abenzerps/Qwen-Image-2.1-Uncensored-GGUF) | abenzerps | **3,271** / 1,638,838 | Qwen-Image 的 GGUF 无审查版，社区热情极高 |
| [ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF) | ISTA-DASLab | 617 / 2,244,732 | 学术实验室对 Qwen3.8-Flash-Next 的混合精度量化版 |
| [DavidAU/Qwen3.8-27B-TURBO-...-GGUF](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF) | DavidAU | 1,464 / 2,134,360 | 社区极致微调版，融合多项技术（Unsloth、无审查），命名风格张扬 |
| [ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-Coder-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-Coder-GGUF) | ISTA-DASLab | 293 / 389,398 | 面向代码任务的剪枝+量化版 Qwen3.8 |
| [orcarouter/OrcaSAQ-2-Cyber-27B-Uncensored-GGUF](https://huggingface.co/orcarouter/OrcaSAQ-2-Cyber-27B-Uncensored-GGUF) | orcarouter | 404 / 16,802 | 基于 Qwen3.8 的 GGUF 无审查对话模型 |
| [Venastine-Research/Xing4.0-29B-A4B-GGUF](https://huggingface.co/Venastine-Research/Xing4.0-29B-A4B-GGUF) | Venastine-Research | 419 / 18,863 | 29B 参数（A4B）量化版，适合资源受限场景 |
| [Infatoshi/GLM-5.3-UNCENSORED-EXL3-3.0bpw](https://huggingface.co/Infatoshi/GLM-5.3-UNCENSORED-EXL3-3.0bpw) | Infatoshi | 241 / 1,342 | GLM-5.3 的 EXL3 低比特量化无审查版 |
| [j

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*