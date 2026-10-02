# Hugging Face 热门模型日报 2026-10-02

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-10-02 01:48 UTC

---

# Hugging Face 热门模型日报（2026-10-02）

## 今日速览

本周 Hugging Face 热度高度集中在 **Qwen 3.8‑27B 系列**及其衍生量化和微调版本上，原版模型获 16,729 赞，多个 GGUF 变体下载量超百万。图像与视频生成方向同样活跃：Qwen‑Image‑2.1 官方版与社区版齐飞，Lightricks LTX‑2.5 以 5,860 赞成为视频生成新星。DeepSeek 发布 V4.1‑Flash 视觉语言模型，主打高效推理。量化活动持续白热化，GSQ+RCO 混合精度量化与三元量化（Ternary）等新技术开始规模化落地。此外，NVIDIA 的说话人分离模型 Nemotron‑3‑Diarization 和基于 GLiNER 的意图分类模型值得关注。

## 热门模型

### 🧠 语言模型（LLM、对话、指令微调）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 16,729 | 6,950,834 | 新一代视觉语言旗舰，支持图文对话与推理，稳居本周热度榜首。 |
| [Xing4.0-29B-A4B](https://huggingface.co/XingChen-AGI/Xing4.0-29B-A4B) | XingChen‑AGI | 1,824 | 48,705 | 29B 激活仅 4B 的 MoE 模型，主打高效推理，下载量持续攀升。 |
| [Hemmingway-1](https://huggingface.co/Altworld/Hemmingway-1) | Altworld | 805 | 8,996 | 基于 Qwen 3.5 的纯文本模型，面向写作与创意内容生成。 |
| [OrcaSAQ-2-27B](https://huggingface.co/orcarouter/OrcaSAQ-2-27B) | orcarouter | 249 | 2,728 | Orca 系列最新 27B 对话模型，支持 vLLM 部署。 |

### 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 5,860 | 1,588,619 | 全能视频生成模型（图转视频、文转视频等），本周视频方向最受关注。 |
| [DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek‑ai | 3,983 | 748,482 | 视觉语言模型新秀，主打快速图文理解与生成，下载量逼近 75 万。 |
| [Qwen-Image-2.1](https://huggingface.co/Qwen/Qwen-Image-2.1) | Qwen | 2,793 | 76,938 | 官方图像生成与编辑模型，Qwen 生态的视觉创作基座。 |
| [Qwen-Image-2.1-Uncensored-GGUF](https://huggingface.co/abenzerps/Qwen-Image-2.1-Uncensored-GGUF) | abenzerps | 2,713 | 1,303,476 | 去审查版 Qwen Image 的 GGUF 格式，下载量超 130 万，社区微调热度可见。 |
| [ZDTaichu5.0-9B](https://huggingface.co/TaichuAI/ZDTaichu5.0-9B) | TaichuAI | 2,571 | 12,194 | 9B 视觉语言模型，专攻空间推理，学术圈关注度高。 |
| [TeleOCR](https://huggingface.co/XingChen-AGI/TeleOCR) | XingChen‑AGI | 1,229 | 31,584 | 专用 OCR 模型，基于 Qwen 2.5 VL，适合图片文字提取。 |
| [BFS-Best-Face-Swap](https://huggingface.co/Alissonerdx/BFS-Best-Face-Swap) | Alissonerdx | 1,077 | 173,323 | 基于 Qwen-Image 的换脸 LoRA，实用图像编辑工具。 |
| [Qwen-Image-2.1 (Comfy-Org)](https://huggingface.co/Comfy-Org/Qwen-Image-2.1) | Comfy-Org | 890 | 5,376,977 | 为 ComfyUI 优化的单文件扩散模型，下载量惊人，社区部署首选。 |
| [Qwen-Image-2.1-viggle-turbo](https://huggingface.co/Viggle/Qwen-Image-2.1-viggle-turbo) | Viggle | 500 | 217,638 | Viggle 社区的加速版图像生成 LoRA，兼顾速度与质量。 |
| [MiMo-V2.6-Distill-Qwen-9B](https://huggingface.co/XiaomiMiMo/MiMo-V2.6-Distill-Qwen-9B) | XiaomiMiMo | 600 | 12,758 | 小米基于 Qwen 3.5 蒸馏的多模态模型，主打轻量部署。 |
| [MiniMax-H3-Character-Swap-LoRA](https://huggingface.co/akatz-ai/MiniMax-H3-Character-Swap-LoRA) | akatz‑ai | 220 | 10,031 | MiniMax H3 的视频角色替换 LoRA，视频编辑创新方向。 |
| [clef](https://huggingface.co/Cloudflare/clef) | Cloudflare | 338 | 18 | Cloudflare 推出的轻量级视觉语言模型，服务边缘端。 |

### 🔧 专用模型（代码、数学、医疗、嵌入、分类等）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [laya](https://huggingface.co/convaiinnovations/laya) | convaiinnovations | 4,865 | 0 | System‑One 风格决策模型，专注于分类与校准，点赞/下载比极高。 |
| [CLM-v0.1-8B](https://huggingface.co/Contrastive-LM/CLM-v0.1-8B) | Contrastive‑LM | 625 | 2,720 | 对比学习驱动的排序/验证模型，用于 RAG 重排。 |
| [Nemotron-3-Diarization](https://huggingface.co/nvidia/Nemotron-3-Diarization) | NVIDIA | 603 | 40,936 | NVIDIA 推出的说话人分离模型，音频处理利器。 |
| [VisionHOPE](https://huggingface.co/PSRben/VisionHOPE) | PSRben | 361 | 305 | 图像分类新架构，已发论文（arXiv:2609.33325），学术探索价值高。 |
| [Julia-1](https://huggingface.co/SupersonicLabs/Julia-1) | SupersonicLabs | 340 | 2,556 | 多语言决策分类模型，专注文本意图与属性判断。 |
| [GLiNER2.5-Decide](https://huggingface.co/fastino/GLiNER2.5-Decide) | fastino | 285 | 38,386 | 基于 GLiNER2 的轻量级意图分类/抽取模型，实用部署场景多。 |

### 📦 微调与量化（社区微调、GGUF、AWQ）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|-----------|
| [unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF) | unsloth | 4,791 | 6,271,224 | 官方 GGUF 版本，下载量破 627 万，本地部署最多人选用。 |
| [Ternary-Bonsai-2-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf) | prism‑ml | 2,333 | 3,766,691 | 三元量化（2‑bit）创新，大幅压缩模型体积，下载量超 376 万。 |
| [Qwen3.8-27B-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF) | ISTA‑DASLab | 1,879 | 1,679,425 | GSQ+RCO 混合精度量化版，兼顾性能与资源，学术团队出品。 |
| [DavidAU/…-NEO-CODER-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF) | DavidAU | 1,336 | 1,817,224 | 极致魔改版 Qwen，融合多种微调技巧与去审查，下载超 181 万。 |
| [Qwen3.8-Flash-Next-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF) | ISTA‑DASLab | 430 | 952,084 | 专为代码和推理优化的 Flash‑Next 量化版，下载近百万。 |
| [Swift-1.5-Qwen3.8-27B-GSQ-RCO-GGUF](https://huggingface.co/ukisai/Swift

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*