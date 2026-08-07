# Hugging Face 热门模型日报 2026-08-07

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-07 01:37 UTC

---

# Hugging Face 热门模型日报（2026-08-07）

## 今日速览

本周 Hugging Face 生态热度集中在 **视频生成与多模态大模型**，MiniMax-H3 系列（原生+量化+LoRA）成为社区改造焦点，衍生出多个优化版本。基础语言模型方面，**DeepSeek-V4-Flash** 和 **Kimi-K3** 下载量持续高位，而 **GLM-5.2** 以 4,871 点赞成为国产模型新星。**FLUX.1-dev** 稳居文本生成图像榜首，14K 点赞彰显其经典地位。社区量化（GGUF、nvfp4）和“无审查”微调（Heretic/Uncensored）活动异常活跃，反映出用户对本地部署和自由度的强烈需求。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **deepseek-ai/DeepSeek-V4-Flash-0731**  
  作者: deepseek-ai | 点赞: 2,644 | 下载: 617,900  
  说明: DeepSeek 最新旗舰对话模型，兼顾性能与推理效率，下载量稳步攀升。

- **moonshotai/Kimi-K3**  
  作者: moonshotai | 点赞: 10,199 | 下载: 1,258,043  
  说明: 月之暗面推出的多模态语言模型，支持图像理解与文本生成，社区关注度极高。

- **zai-org/GLM-5.2**  
  作者: zai-org | 点赞: 4,871 | 下载: 2,391,730  
  说明: 智谱最新 MoE 架构语言模型，结合 DSA 技术，兼具高性能与稀疏激活优势。

- **deepseek-ai/DeepSeek-V4-Flash**  
  作者: deepseek-ai | 点赞: 2,042 | 下载: 2,639,756  
  说明: DeepSeek-V4 系列基础版，下载量最大，广泛用于对话和文本生成任务。

- **LiquidAI/LFM2.5-2.6B**  
  作者: LiquidAI | 点赞: 332 | 下载: 73,573  
  说明: 轻量级语言模型，2.6B 参数适合资源受限场景，受开发者青睐。

- **deepgrove/maple-preview**  
  作者: deepgrove | 点赞: 207 | 下载: 419  
  说明: MoE 架构的文本生成模型，预览版吸引早期用户测试。

- **inclusionAI/Ling-3.0-flash**  
  作者: inclusionAI | 点赞: 186 | 下载: 1,196  
  说明: 百灵混合架构对话模型，支持自定义代码，国产模型新秀。

- **XYZAILab/XYZ-Aquila-mini**  
  作者: XYZAILab | 点赞: 424 | 下载: 1,570  
  说明: 基于 Qwen3.5 MoE 的小型语言模型，主打高效推理。

- **EschaLabs/Qwen3.6-35B-A3B-Escha-W2**  
  作者: EschaLabs | 点赞: 222 | 下载: 3,394  
  说明: 基于 Qwen3.6 的 MoE 微调版，优化了稀疏激活效率。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **MiniMaxAI/MiniMax-H3**  
  作者: MiniMaxAI | 点赞: 2,751 | 下载: 12,102  
  说明: 旗舰视频生成模型，支持图像/文本到视频，是本轮社区改造的核心模型。

- **Comfy-Org/MiniMax-H3**  
  作者: Comfy-Org | 点赞: 846 | 下载: 2,295,377  
  说明: ComfyUI 优化版 MiniMax-H3，大幅降低使用门槛，下载量极大。

- **black-forest-labs/FLUX.1-dev**  
  作者: black-forest-labs | 点赞: 14,010 | 下载: 523,234  
  说明: 经典文本到图像模型，持续霸榜，社区生态成熟。

- **microsoft/Mage-VL**  
  作者: microsoft | 点赞: 286 | 下载: 440,176  
  说明: 微软多模态视觉语言模型，支持图像理解与对话，下载量高。

- **thinkingmachines/Inkling-Small**  
  作者: thinkingmachines | 点赞: 321 | 下载: 22,223  
  说明: 小型多模态模型，兼顾图像理解与对话，适合轻量部署。

- **lodestones/Kroma**  
  作者: lodestones | 点赞: 205 | 下载: 0  
  说明: Krea 平台 LoRA 模型，专注于文本到图像生成风格化。

- **nvidia/NVIDIA-NemotronLabs-VoiceChat-11B**  
  作者: nvidia | 点赞: 177 | 下载: 206  
  说明: NVIDIA 语音聊天模型，11B 参数，支持多轮语音交互。

- **Audio8/Audio8-TTS-Preview-0.6b**  
  作者: Audio8 | 点赞: 293 | 下载: 12,211  
  说明: 文本到语音预览模型，采用 ArkTTS 架构，音质出色。

- **larryvrh/MiniMax-H3-Turbo-Lora**  
  作者: larryvrh | 点赞: 299 | 下载: 0  
  说明: MiniMax-H3 的 LoRA 适配器，加速视频生成任务。

- **drbaph/MiniMax-H3-Turbo-Lora-ComfyUI**  
  作者: drbaph | 点赞: 118 | 下载: 0  
  说明: 专为 ComfyUI 优化的 MiniMax-H3 LoRA，剪枝版更轻量。

- **Abiray/Minimax-H3-nvfp4-INT4-INT8-Convrot**  
  作者: Abiray | 点赞: 109 | 下载: 272,963  
  说明: 多精度量化版 MiniMax-H3，支持 NVFP4/INT4/INT8，下载量高。

### 🔧 专用模型（代码、数学、医疗、嵌入）

- **baidu/Unlimited-OCR**  
  作者: baidu | 点赞: 3,929 | 下载: 2,791,862  
  说明: 百度推出的通用 OCR 模型，支持无限类别文字识别，下载量第一。

- **Kwaipilot/KAT-Coder-V2.5-Dev**  
  作者: Kwaipilot | 点赞: 518 | 下载: 16,961  
  说明: 基于 Qwen3.5 MoE 的代码生成模型，面向开发者工具链。

- **mistralai/Shieldstral-1.0-3B**  
  作者: mistralai | 点赞: 156 | 下载: 1,511  
  说明: Mistral 推出的安全防护模型，3B 参数，用于内容过滤与合规。

### 📦 微调与量化（社区微调、GGUF、AWQ）

- **unsloth/DeepSeek-V4-Flash-0731-GGUF**  
  作者: unsloth | 点赞: 544 | 下载: 145,105  
  说明: DeepSeek-V4 的 GGUF 量化版，支持本地高效推理。

- **DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF**  
  作者: DavidAU | 点赞: 1,650 | 下载: 2,087,189  
  说明: 超长名称的 Qwen3.6 无审查微调+GGUF 量化版，下载量极大，社区追捧。

- **realrebelai/MiniMax-H3_GGUFs**  
  作者: realrebelai | 点赞: 153 | 下载: 65,679  
  说明: MiniMax-H3 的 GGUF 量化版，方便 ComfyUI 用户本地运行。

- **LuffyTheFox/Qwen3.6-35B-A3B-Uncensored-Genesis-Hermes-V7-GGUF**  
  作者: LuffyTheFox | 点赞: 407 | 下载: 309,149  
  说明: Qwen3.6 的 MoE 无审查微调+GGUF 版，Hermes 风格，受欢迎。

- **LiquidAI/LFM2.5-2.6B-GGUF**  
  作者: LiquidAI | 点赞: 124 | 下载: 12,790  
  说明: LFM2.5 的 GGUF 量化版，适合 llama.cpp 本地部署。

- **ethanfel/Qwen3-VL-32B-Ultra-Heretic-H3-ComfyUI-INT8-ConvRot**  
  作者: ethanfel | 点赞: 337 | 下载: 0  
  说明: Qwen3-VL 的极端微调版，结合 H3 和 ComfyUI 优化，INT8 量化。

- **sakamakismile/Qwen3-VL-32B-Heretic-MiniMax-H3-NVFP4**  
  作者: sakamakismile | 点赞: 108 | 

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*