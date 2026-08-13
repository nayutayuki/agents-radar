# Hugging Face 热门模型日报 2026-08-14

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-13 23:22 UTC

---

# Hugging Face 热门模型日报（2026-08-14）

## 今日速览

本周 Hugging Face 热度最高的是 **moonshotai/Kimi-K3**，以 10,620 点赞遥遥领先，成为多模态理解领域的新星，同时其下载量高达 187 万，说明社区已快速部署应用。**MiniMaxAI/MiniMax-H3** 系列视频生成模型形成完整生态，原生模型、LoRA、GGUF 量化版、ComfyUI 适配等一应俱全，占据 30 个热门席位中的 10 余个。**DeepSeek-V4** 系列持续迭代，Flash 和 Pro 两个版本均上榜，保持文本生成领域的高关注度。此外，**NVIDIA Nemotron** 系列和 **Qwen** 系列的多款量化与微调模型也出现在榜单中，社区对高性能、低资源部署的需求依然旺盛。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **[Qwen/Qwen3.8-2.4T-A95B](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B)** — 作者 Qwen | 点赞 778 | 下载 1,012  
  Qwen 新一代 MoE 文本生成模型，总参数量 2.4T 但激活仅 95B，在推理效率与能力间取得平衡，因高性价比进入热门。

- **[deepseek-ai/DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731)** — 作者 deepseek-ai | 点赞 3,315 | 下载 1,431,587  
  DeepSeek V4 系列快速推理版，兼具高吞吐与强对话能力，下载量超 140 万，是目前最受欢迎的开源文本生成模型之一。

- **[deepseek-ai/DeepSeek-V4-Pro-0813](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813)** — 作者 deepseek-ai | 点赞 271 | 下载 0  
  V4 专业版，定位更高精度场景，尚未大规模下载，但点赞数表明关注度不低。

- **[LiquidAI/LFM2.5-2.6B](https://huggingface.co/LiquidAI/LFM2.5-2.6B)** — 作者 LiquidAI | 点赞 602 | 下载 116,640  
  Liquid 基金会推出的 2.6B 小参数模型，适合资源受限设备，因轻量高效获得社区青睐。

- **[nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-NVFP4](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-NVFP4)** — 作者 nvidia | 点赞 229 | 下载 44,859  
  NVIDIA 旗舰文本生成模型，30B 总参、3B 激活的 MoE 架构，采用 NVFP4 量化，兼顾精度与速度。

- **[nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16)** — 作者 nvidia | 点赞 129 | 下载 22,279  
  同一模型的 BF16 精度版本，适合需要更高精度的部署场景。

- **[deepgrove/maple-preview](https://huggingface.co/deepgrove/maple-preview)** — 作者 deepgrove | 点赞 352 | 下载 3,868  
  DeepGrove 推出的 MoE 文本生成模型，预览版即获得较高关注，社区期待正式发布。

- **[Qwen/Qwen3.8-2.4T-A95B-FP8](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B-FP8)** — 作者 Qwen | 点赞 157 | 下载 4,000  
  MoE 模型的 FP8 量化版本，进一步降低显存需求，适合大模型部署优化。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3)** — 作者 moonshotai | 点赞 10,620 | 下载 1,871,575  
  本周总榜冠军，Kimi 系列最新多模态理解模型（image-text-to-text），支持图像与文本交互，凭借极高点赞和下载量成为现象级模型。

- **[MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)** — 作者 MiniMaxAI | 点赞 3,818 | 下载 1,605,940  
  MiniMax 视频生成旗舰模型，支持文本/图像到视频，下载量超 160 万，是当下最热门的视频生成基础模型。

- **[meta-models/Muse-Glimmer-30B](https://huggingface.co/meta-models/Muse-Glimmer-30B)** — 作者 meta-models | 点赞 1,413 | 下载 121,042  
  Meta 推出的多模态对话模型（image-text-to-text），30B 参数，支持图像理解与对话，因 Meta 品牌效应和强大能力上榜。

- **[Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5)** — 作者 Lightricks | 点赞 715 | 下载 57,287  
  Lightricks 新一代图像/视频到视频生成模型，支持多种输入模态，在视频生成社区中热度较高。

- **[lightx2v/Minimax-h3-Turbo](https://huggingface.co/lightx2v/Minimax-h3-Turbo)** — 作者 lightx2v | 点赞 458 | 下载 91,455  
  MiniMax-H3 的 Turbo 加速版，提升推理速度，适合实时视频生成场景。

- **[MiniMaxAI/MiniMax-Music3](https://huggingface.co/MiniMaxAI/MiniMax-Music3)** — 作者 MiniMaxAI | 点赞 285 | 下载 25  
  MiniMax 音乐生成模型，文本到音频，进一步拓展其多模态版图，虽下载量不高但标签显示适配 SGLang，潜力可观。

- **[endless-frontier/BigBang-v1](https://huggingface.co/endless-frontier/BigBang-v1)** — 作者 endless-frontier | 点赞 188 | 下载 3,184  
  基于 Qwen3.5 MoE 架构的多模态理解模型，在图像文本对话任务上表现优异。

- **[nvidia/NVIDIA-NemotronLabs-VoiceChat-11B](https://huggingface.co/nvidia/NVIDIA-NemotronLabs-VoiceChat-11B)** — 作者 nvidia | 点赞 371 | 下载 1,164  
  NVIDIA 推出的语音聊天模型，11B 参数，支持多轮语音交互，开创了 Nemotron 在语音领域的应用。

### 🔧 专用模型（代码、数学、医疗、嵌入等）

本列表未出现明显专用模型（如代码、数学、医疗），但以下模型可视为面向特定场景的变体或工具：

- **[inclusionAI/Ling-3.0-tiny](https://huggingface.co/inclusionAI/Ling-3.0-tiny)** — 作者 inclusionAI | 点赞 216 | 下载 1,292  
  轻量级混合架构模型（bailing_hybrid），可能用于端侧推理或嵌入任务，因小巧灵活获得关注。

### 📦 微调与量化（社区微调、GGUF、AWQ、LoRA）

- **[unsloth/Muse-Glimmer-30B-GGUF](https://huggingface.co/unsloth/Muse-Glimmer-30B-GGUF)** — 作者 unsloth | 点赞 390 | 下载 352,023  
  Muse-Glimmer 的 GGUF 量化版，由 unsloth 提供，下载量高达 35 万，反映社区对多模态模型量化的强劲需求。

- **[Comfy-Org/MiniMax-H3](https://huggingface.co/Comfy-Org/MiniMax-H3)** — 作者 Comfy-Org | 点赞 1,288 | 下载 10,365,210  
  MiniMax-H3 的 ComfyUI 适配版，下载量超过 1000 万，是榜单中下载量最高的模型，说明视频生成工作流在 ComfyUI 上极其活跃。

- **[DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF)** — 作者 DavidAU | 点赞 1,986 | 下载 2,793,115  
  社区微调版 Qwen，融合多种创意元素（uncensored、heretic 等），点赞近 2000，下载量超过 279 万，表明社区对“去限制”和趣味化模型兴趣浓厚。

- **[larryvrh/MiniMax-H3-Turbo-Lora](https://huggingface.co/larryvrh/MiniMax-H3-Turbo-Lora)** — 作者 larryvrh | 点赞 725 | 下载 0  
  MiniMax-H3-Turbo 的 LoRA 适配器，虽下载量为 0（可能刚发布），但点赞高，预示后续将爆发。

- **[Kijai/MiniMax-H3_comfy](https://huggingface.co/Kijai/MiniMax-H3_comfy)** — 作者 Kijai | 点赞 303 | 下载 0  
  另一款 MiniMax-H3 的 ComfyUI 节点，与 Comfy-Org 模型互补，丰富社区生态。

- **[SexGod1979/PinkCherry_MiniMax-H3](https://huggingface.co/SexGod1979/PinkCherry_MiniMax-H3)** — 作者 SexGod1979 | 点赞 298 | 下载 324  
  社区基于 MiniMax-H3 的微调版本，风格化内容生成，反映个性化定制需求。

- **[drbaph/MiniMax-H3-Turbo-Lora-ComfyUI](https://huggingface.co/drbaph/MiniMax-H3-Turbo-Lora-ComfyUI)** — 作者 drbaph | 点赞 314 | 下载 0  
  同样是 MiniMax-H3-Turbo 的 LoRA + ComfyUI 适配，进一步丰富该生态。

- **[fal/MiniMax-H3-Realism-People-LoRA](https://huggingface.co/fal/MiniMax-H3-Realism-People-LoRA)** — 作者 fal | 点赞 157 | 下载 4,692  
  专注于人物写实风格的 LoRA，提升 MiniMax-H3 生成人物视频的真实感。

- **[lightx2v/MiniMax-H3-Prompt-Rewriter-LoRA](https://huggingface.co/lightx2v/MiniMax-H3-Prompt-Rewriter-LoRA)** — 作者 lightx2v | 点赞 148 | 下载 652  
  提示词重写 LoRA，帮助用户优化视频生成描述，提升效果。

- **[unsloth/MiniMax-H3-GGUF](https://huggingface.co/unsloth/MiniMax-H3-GGUF)** — 作者 unsloth | 点赞 149 | 下载 111,222  
  MiniMax-H3 的 GGUF 量化版，下载量超 11 万，满足 CPU/低显存部署需求。

- **[meta-models/Muse-Glimmer-30B-GGUF](https://huggingface.co/meta-models/Muse-Glimmer-30B-GGUF)** — 作者 meta-models | 点赞 257 | 下载 136,783  
  Muse-Glimmer 官方提供的 GGUF 版本，方便本地运行，下载量可观。

- **[ethanfel/Qwen3-VL-32B-Ultra-Heretic-H3-ComfyUI-INT8-ConvRot](https://huggingface.co/ethanfel/Qwen3-VL-32B-Ultra-Heretic-H3-ComfyUI-INT8-ConvRot)** — 作者 ethanfel | 点赞 483 | 下载 0  
  Qwen 视觉语言模型的社区魔改版，集成多种技术（INT8、ConvRot），点赞 483 但尚未有下载，可能为预览版。

- **[Kijai/MiniMax-H3-experimental](https://huggingface.co/Kijai/MiniMax-H3-experimental)** — 作者 Kijai | 点赞 221 | 下载 0  
  MiniMax-H3 的实验性 ComfyUI 适配，探索新功能，社区关注度高。

## 生态信号

**模型家族势头**：**MiniMax-H3** 系列是本周期最活跃的生态，从基础模型到 Turbo、LoRA、GGUF、ComfyUI 适配，覆盖了训练、推理、微调、部署全链路，体现了“模型即平台”的趋势。**Qwen** 家族（3.8 MoE、3.6 微调版）和 **DeepSeek V

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*