# Hugging Face 热门模型日报 2026-08-10

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-09 23:04 UTC

---

# Hugging Face 热门模型日报  
**日期：2026-08-10**  

---

## 今日速览  

本周 Hugging Face 热门模型呈现 **多模态与视频生成爆发** 的态势：MiniMax-H3 系列（视频生成）及其衍生版本霸榜多个席位，社区微调与量化版本层出不穷。语言模型方面，**Kimi-K3**（10,395 点赞）和 **GLM-5.2**（4,913 点赞）领跑，**DeepSeek-V4-Flash** 下载量接近 90 万。专用模型亮点包括 **百度 Unlimited-OCR**（3,985 点赞）和 **NVIDIA VoiceChat 11B**。**FLUX.1-dev** 以 14,057 点赞继续稳居榜首，显示文生图领域持续热度。整体生态中，**GGUF 量化** 和 **ComfyUI 适配** 成为社区最活跃的二次开发方向。  

---

## 热门模型  

### 🧠 语言模型（LLM、对话模型、指令微调）  

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [deepseek-ai/DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731) | deepseek-ai | 2,940 | 868,576 | DeepSeek 最新对话模型，基于 MoE 架构，下载量极高，社区热捧。 |
| [zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2) | zai-org | 4,913 | 2,488,397 | 智谱 GLM 系列最新 MoE 模型，对话与生成能力强劲，点赞数位居前列。 |
| [LiquidAI/LFM2.5-2.6B](https://huggingface.co/LiquidAI/LFM2.5-2.6B) | LiquidAI | 448 | 85,651 | Liquid AI 发布的小型语言模型，2.6B 参数，适合高效部署。 |
| [deepgrove/maple-preview](https://huggingface.co/deepgrove/maple-preview) | deepgrove | 287 | 1,089 | 基于 MoE 的因果语言模型预览版，参数规模未公开，注重效率。 |
| [inclusionAI/Ling-3.0-flash](https://huggingface.co/inclusionAI/Ling-3.0-flash) | inclusionAI | 244 | 4,747 | 百灵混合架构的对话模型，支持自定义代码，主打快速推理。 |

### 🎨 多模态与生成（图像、视频、音频、文本到X）  

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [black-forest-labs/FLUX.1-dev](https://huggingface.co/black-forest-labs/FLUX.1-dev) | black-forest-labs | 14,057 | 487,171 | 经典文生图模型，本周点赞量最高，仍是社区最活跃的图像生成模型。 |
| [moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3) | moonshotai | 10,395 | 1,456,459 | 月之暗面发布的多模态大模型（图像+文本输入），支持压缩张量，性能强劲。 |
| [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 3,240 | 35,295 | MiniMax 推出的图像/文本到视频生成模型，带动了整个视频生成赛道。 |
| [microsoft/Mage-VL](https://huggingface.co/microsoft/Mage-VL) | microsoft | 323 | 461,150 | 微软多模态视觉语言模型，用于图像理解与对话，下载量高。 |
| [lightx2v/Minimax-h3-Turbo](https://huggingface.co/lightx2v/Minimax-h3-Turbo) | lightx2v | 233 | 6,117 | 基于 MiniMax-H3 的 Turbo 加速版，支持图像/参考图到视频生成。 |
| [SexGod1979/PinkCherry_MiniMax-H3](https://huggingface.co/SexGod1979/PinkCherry_MiniMax-H3) | SexGod1979 | 230 | 0 | 社区微调的 MiniMax-H3 变体，专注文本到视频生成，支持端点。 |
| [endless-frontier/BigBang-v1](https://huggingface.co/endless-frontier/BigBang-v1) | endless-frontier | 117 | 482 | 基于 Qwen3.5 MoE 的多模态对话模型，支持图像与文本交互。 |

### 🔧 专用模型（代码、OCR、TTS、安全等）  

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR) | baidu | 3,985 | 2,889,062 | 百度发布的通用 OCR 模型，支持多场景文字识别，下载量极高。 |
| [Kwaipilot/KAT-Coder-V2.5-Dev](https://huggingface.co/Kwaipilot/KAT-Coder-V2.5-Dev) | Kwaipilot | 552 | 18,574 | 基于 Qwen3.5 Mo

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*