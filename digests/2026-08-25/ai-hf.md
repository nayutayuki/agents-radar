# Hugging Face 热门模型日报 2026-08-25

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-24 22:59 UTC

---

# Hugging Face 热门模型日报（2026-08-25）

## 今日速览

本周 Hugging Face 榜单完全被 **Qwen3.8-27B** 系列统治——前六名中五个是它的变体，总计 12 个模型直接或间接基于该基座，刷新了单周生态热度纪录。**MiniMax** 同时推出视频生成 H3 与音乐生成 Music3，多模态能力全面开花。**DeepSeek-V4-Flash** 强势回归，以 3.7k 点赞稳居文本生成榜第一。社区侧，“abliterated/uncensored” 版本井喷式涌现，从 MLX、GGUF 到 FP8 的量化适配几乎覆盖所有主流推理框架，反映出用户对“无审查”模型和本地部署的强烈需求。

---

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **[DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731)**  
  作者: deepseek-ai | 👍 3,681 | 📥 3,274,129  
  一句话：DeepSeek 最新一代对话模型，主打极速推理与长上下文，下载量持续攀升。

- **[ornith-ai/Ornith-1.5-35B-A3B](https://huggingface.co/ornith-ai/Ornith-1.5-35B-A3B)**  
  作者: ornith-ai | 👍 394 | 📥 60,294  
  一句话：35B 总参、3B 激活的 MoE 语言模型，继承了 Qwen3.5 MoE 架构，在效率与能力间取得平衡。

- **[ornith-ai/Ornith-1.5-9B](https://huggingface.co/ornith-ai/Ornith-1.5-9B)**  
  作者: ornith-ai | 👍 200 | 📥 83,192  
  一句话：相同家族的小型 MoE 模型，适合资源受限场景，社区微调版本也同步发布。

- **[superwhisper/s1-mini](https://huggingface.co/superwhisper/s1-mini)**  
  作者: superwhisper | 👍 229 | 📥 2,976  
  一句话：基于 Qwen3 的轻量级语音识别/生成模型，ASR 与文本生成双任务，预览阶段已获关注。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B)**  
  作者: Qwen | 👍 12,508 | 📥 2,645,226  
  一句话：本周现象级模型——27B 视觉语言模型，支持图文对话与理解，社区衍生版本超 20 个。

- **[MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)**  
  作者: MiniMaxAI | 👍 4,417 | 📥 4,465,161  
  一句话：图生视频、文生视频的旗舰模型，下载量爆表，媲美商业闭源方案。

- **[Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5)**  
  作者: Lightricks | 👍 1,721 | 📥 790,378  
  一句话：图生视频/文生视频扩散模型，LTX 系列迭代至 2.5，画质与连贯性显著提升。

- **[MiniMaxAI/MiniMax-Music3](https://huggingface.co/MiniMaxAI/MiniMax-Music3)**  
  作者: MiniMaxAI | 👍 1,227 | 📥 18,065  
  一句话：文本到音乐生成模型，Diffusers 架构，虽下载量尚小，但标志着音乐生成开源化新起点。

- **[Qwen/Qwen3.8-27B-FP8](https://huggingface.co/Qwen/Qwen3.8-27B-FP8)**  
  作者: Qwen | 👍 680 | 📥 3,004,940  
  一句话：官方 FP8 量化版本，显存需求减半，为大规模部署提供高效选择。

- **[Audio8/Audio8-TTS-Preview-0.1b](https://huggingface.co/Audio8/Audio8-TTS-Preview-0.1b)**  
  作者: Audio8 | 👍 145 | 📥 2,775  
  一句话：基于 ArkTTS 的文本转语音预览版，专注高质量语音合成。

- **[LBH-123-AI/Minimax_h3_latent_Upscaler](https://huggingface.co/LBH-123-AI/Minimax_h3_latent_Upscaler)**  
  作者: LBH-123-AI | 👍 181 | 📥 0  
  一句话：专为 MiniMax H3 视频模型设计的潜在空间超分器，提升输出分辨率。

### 🔧 专用模型（代码、数学、医疗、嵌入等）

- **[froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates)**  
  作者: froggeric | 👍 1,446 | 📥 0  
  一句话：修正 Qwen3.5 系列聊天模板的工具仓库，解决 Jinja 格式兼容问题，下载量虽为 0 但点赞极高。

- **[peculiar-ragdoll/Qwen-Sharp-Chat-Templates](https://huggingface.co/peculiar-ragdoll/Qwen-Sharp-Chat-Templates)**  
  作者: peculiar-ragdoll | 👍 226 | 📥 0  
  一句话：另一个 Qwen 聊天模板修复项目，与 froggeric 类似，突显社区对模板准确性的迫切需求。

- **[z-lab/Qwen3.8-27B-DFlash2](https://huggingface.co/z-lab/Qwen3.8-27B-DFlash2)**  
  作者: z-lab | 👍 214 | 📥 50,763  
  一句话：引入 speculative decoding 的 Qwen3.8 变体，通过草稿模型加速推理，适合高吞吐场景。

- **[incoai/Qwen3.8-27B-DFlash2](https://huggingface.co/incoai/Qwen3.8-27B-DFlash2)**  
  作者: incoai | 👍 173 | 📥 85,034  
  一句话：另一相同思路的 speculative decoding 实现，与 z-lab 类似，社区竞相优化推理速度。

### 📦 微调与量化（社区微调、GGUF、AWQ）

- **[unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF)**  
  作者: unsloth | 👍 2,831 | 📥 7,009,063  
  一句话：最受欢迎的 GGUF 版本，由 unsloth 优化，下载量超 700 万，成为本地部署首选。

- **[orcarouter/Qwen3.8-27B-Uncensored-MLX](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-MLX)**  
  作者: orcarouter | 👍 1,026 | 📥 57,947  
  一句话：MLX 格式的“无审查”版本，适配 Apple Silicon，标签包含 abliterated（去除安全对齐）。

- **[orcarouter/Qwen3.8-27B-Uncensored-FP8](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-FP8)**  
  作者: orcarouter | 👍 1,097 | 📥 224,114  
  一句话：FP8 精度的无审查版本，兼顾显存效率与生成自由度。

- **[OBLITERATUS/Qwen3.8-27B-OBLITERATED](https://huggingface.co/OBLITERATUS/Qwen3.8-27B-OBLITERATED)**  
  作者: OBLITERATUS | 👍 692 | 📥 312,627  
  一句话：名称直白的“消除”版本，提供 MLX/GGUF 多格式，下载量已超 30 万。

- **[JonathanColetti/Qwen3.8-27B-Uncensored-GGUF](https://huggingface.co/JonathanColetti/Qwen3.8-27B-Uncensored-GGUF)**  
  作者: JonathanColetti | 👍 688 | 📥 1,456,700  
  一句话：

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*