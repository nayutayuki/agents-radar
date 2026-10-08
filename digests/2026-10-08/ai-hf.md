# Hugging Face 热门模型日报 2026-10-08

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-10-08 02:15 UTC

---

# Hugging Face 热门模型日报（2026-10-08）

## 今日速览
本周 Hugging Face 社区最受瞩目的发布是 **Qwen3.8-27B**，以 17,207 点赞断层领先，成为视觉语言模型的新标杆。**Lightricks LTX-2.5** 在视频生成赛道同样火爆，6,801 点赞验证了用户对高质量图像转视频的强烈需求。企业级模型方面，**Cloudflare** 连续推出 clef 系列多模态模型，而 **DeepSeek-V4.1-Flash** 以 4,224 点赞迅速跻身第一梯队。此外，量化与微调生态异常活跃，ISTA-DASLab、DavidAU 等社区贡献了大量 GGUF 量化版本，极低比特量化（如 Ternary-Bonsai-2-27B）成为新热点。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）
- **autotrust/GEV-26B-Decide** | [链接](https://huggingface.co/autotrust/GEV-26B-Decide)  
  作者: autotrust | 👍 1,345 | 📥 895,867  
  基于 Gemma 4 的自动化决策文本分类模型，专为 System‑One 推理设计，周增赞 1,345 表明产业界对快速决策模型的需求。

- **Aleph-Alpha/Kolibri-1** | [链接](https://huggingface.co/Aleph-Alpha/Kolibri-1)  
  作者: Aleph-Alpha | 👍 775 | 📥 5,775  
  德国团队推出的 1B 级 MoE 推理模型，主打高效推理，吸引了对小参数推理模型的关注。

- **convaiinnovations/laya** | [链接](https://huggingface.co/convaiinnovations/laya)  
  作者: convaiinnovations | 👍 5,333 | 📥 28,497  
  针对“校准决策”的文本分类模型，周增幅显著，或与金融/风控场景应用有关。

- **orcarouter/OrcaSAQ-2-Cyber-27B-Uncensored-GGUF** | [链接](https://huggingface.co/orcarouter/OrcaSAQ-2-Cyber-27B-Uncensored-GGUF)  
  作者: orcarouter | 👍 453 | 📥 19,030  
  基于 Qwen3.8 的 27B 无审查对话模型，社区微调版本，满足特定用户对安全限制去除的需求。

### 🎨 多模态与生成（图像、视频、音频、文本到X）
- **Qwen/Qwen3.8-27B** | [链接](https://huggingface.co/Qwen/Qwen3.8-27B)  
  作者: Qwen | 👍 17,207 | 📥 6,758,993  
  Qwen 最新旗舰视觉语言模型，27B 参数，支持图像理解与对话，本周增长最多，是当前多模态领域的焦点。

- **Lightricks/LTX-2.5** | [链接](https://huggingface.co/Lightricks/LTX-2.5)  
  作者: Lightricks | 👍 6,801 | 📥 1,674,291  
  图像转视频模型，单文件扩散架构，支持文本/图像/视频到视频，因高质量生成能力爆火。

- **Qwen/Qwen3.8-Flash-Next** | [链接](https://huggingface.co/Qwen/Qwen3.8-Flash-Next)  
  作者: Qwen | 👍 6,011 | 📥 1,609,433  
  Qwen3.8 的快速推理变体（Qwen4 实验版），在保持能力的同时优化推理速度。

- **deepseek-ai/DeepSeek-V4.1-Flash** | [链接](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash)  
  作者: deepseek-ai | 👍 4,224 | 📥 1,255,513  
  DeepSeek 最新多模态模型，V4.1 Flash 版本，强调快速推理与文本/图像理解。

- **abenzerps/Qwen-Image-2.1-Uncensored-GGUF** | [链接](https://huggingface.co/abenzerps/Qwen-Image-2.1-Uncensored-GGUF)  
  作者: abenzerps | 👍 3,567 | 📥 1,820,627  
  Qwen-Image 的无审查 GGUF 版本，用于 ComfyUI 等工具，周下载量超 180 万。

- **Qwen/Qwen-Image-2.1** | [链接](https://huggingface.co/Qwen/Qwen-Image-2.1)  
  作者: Qwen | 👍 3,091 | 📥 109,298  
  Qwen 官方图像生成模型，支持文本/图像编辑，作为最新图像生成基础模型广受关注。

- **TaichuAI/ZDTaichu5.0-9B** | [链接](https://huggingface.co/TaichuAI/ZDTaichu5.0-9B)  
  作者: TaichuAI | 👍 2,899 | 📥 12,970  
  中科院旗下 9B 视觉语言模型，专注空间推理，点赞量快速增长。

- **autotrust/JEV-27B-VL** | [链接](https://huggingface.co/autotrust/JEV-27B-VL)  
  作者: autotrust | 👍 2,023 | 📥 1,529,210  
  Qwen3.5 架构的 27B 视觉语言模型，下载量高达 150 万，社区使用广泛。

- **Cloudflare/clef** | [链接](https://huggingface.co/Cloudflare/clef)  
  作者: Cloudflare | 👍 1,817 | 📥 9,513  
  Cloudflare 推出的多模态模型，基于 Qwen3.5，下载量虽不高但点赞反映企业级关注。

- **Cloudflare/clef-flash** | [链接](https://huggingface.co/Cloudflare/clef-flash)  
  作者: Cloudflare | 👍 653 | 📥 15,722  
  clef 的快速版本，适配边缘场景。

- **Viggle/Qwen-Image-2.1-viggle-turbo** | [链接](https://huggingface.co/Viggle/Qwen-Image-2.1-viggle-turbo)  
  作者: Viggle | 👍 655 | 📥 326,801  
  基于 Qwen-Image-2.1 的 LoRA 微调版，加速图像生成，下载量高。

- **Alissonerdx/BFS-Best-Face-Swap** | [链接](https://huggingface.co/Alissonerdx/BFS-Best-Face-Swap)  
  作者: Alissonerdx | 👍 1,290 | 📥 238,952  
  Qwen-Image 驱动的换脸模型，LoRA 形式，社区热门应用。

- **jialinyyzz/humanizer** | [链接](https://huggingface.co/jialinyyzz/humanizer)  
  作者: jialinyyzz | 👍 467 | 📥 19,483  
  混合 Gemma 4 架构的“人性化”文本生成模型，目标使输出更自然。

- **pablodawson/MiniMax-H3-360-Orbit-LoRA** | [链接](https://huggingface.co/pablodawson/MiniMax-H3-360-Orbit-LoRA)  
  作者: pablodawson | 👍 245 | 📥 10,119  
  MiniMax-H3 的 LoRA，支持图像到视频生成（首尾帧控制）。

### 🔧 专用模型（代码、数学、医疗、嵌入）
- **google/embeddinggemma-2** | [链接](https://huggingface.co/google/embeddinggemma-2)  
  作者: google | 👍 966 | 📥 7,562  
  Google 最新嵌入模型，用于特征提取，是 RAG 和语义搜索的基础组件。

- **unsloth/embeddinggemma-2-GGUF** | [链接](https://huggingface.co/unsloth/embeddinggemma-2-GGUF)  
  作者: unsloth | 👍 165 | 📥 11,470  
  embeddinggemma-2 的 GGUF 量化版，方便本地部署。

- **Cactus-Compute/whistle** | [链接](https://huggingface.co/Cactus-Compute/whistle)  
  作者: Cactus-Compute | 👍 138 | 📥 2,249  
  用于自动语音识别的 on‑device 模型，主打轻量与离线运行。

### 📦 微调与量化（社区微调、GGUF、AWQ）
- **prism-ml/Ternary-Bonsai-2-27B-gguf** | [链接](https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf)  
  作者: prism-ml | 👍 2,521 | 📥 4,271,466  
  采用三值量化的 27B 模型，将权重量化到 2‑bit，实现极高压缩，下载量居本周前列。

- **ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF** | [链接](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF)  
  作者: ISTA-DASLab | 👍 2,034 | 📥 1,546,030  
  对 Qwen3.8-27B 的混合精度量化版本（GSQ + RCO），适合资源受限环境。

- **ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF** | [链接](https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF)  
  作者: ISTA-DASLab | 👍 691 | 📥 3,080,123  
  对 Flash‑Next 的量化版，下载量超过 300 万，社区高度认可其量化效率。

- **DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-...-GGUF** | [链接](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF)  
  作者: DavidAU | 👍 1,543 | 📥 2,088,541  
  社区微调的超长命名 Qwen 变体，融合多种特色（无审查、编码增强等），GGUF 格式，下载超 200 万。

- **ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-Coder-GGUF** | [链接](https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-Coder-GGUF)  
  作者: ISTA-DASLab | 👍 334 | 📥 553,685  
  针对代码任务剪枝并量化的版本，面向开发场景。

- **autotrust/GEV-26B-Decide-NVFP4** | [链接](https://huggingface.co/autotrust/GEV-26B-Decide-NVFP4)  
  作者: autotrust | 👍 153 | 📥 14,957  
  基于 NVIDIA FP4 格式的极低精度量化版本，探索 4‑bit 以下压缩。

- **Infatoshi/GLM-5.3-UNCENSORED-EXL3-3.0bpw** | [链接](https://huggingface.co/Infatoshi/GLM-5.3-UNCENSORED-EXL3-3.0bpw)  
  作者: Infatoshi | 👍 283 | 📥 1,903  
  GLM 5.3 的无审查版，采用 EXL3 量化（3.0 bpw），极低比特测试。

- **Venastine-Research/Xing4.0-29B-A4B-GGUF** | [链接](https://huggingface.co/Venastine-Research/Xing4.0-29B-A4B-GGUF)  
  作者: Venastine-Research | 👍 626 | 📥 33,633  
  29B 参数的 Xing 4.0 量化版，采用 A4B 混合精度，吸引对精度与速度平衡的用户。

- **canberkkkkkk/ema-lightning** | [链接](https://huggingface.co/canberkkkkkk/ema-lightning)  
  作者: canberkkkkkk | 👍 265 | 📥 2,724  
  土耳其语 TTS 模型，轻量化量化版（EMA-Lightning）。

---

## 生态信号

- **Qwen 家族全面崛起**：从 Qwen3.8-27B 到 Qwen-Image-2.1，再到 Flash-Next 衍生版本，Qwen 几乎覆盖了多模态、图像生成、快速推理全路线，生态影响力已超 Llama 系列。
- **多模态模型成为绝对主力**：本周点赞 Top 5 中有 4 个是多模态（图像-文本、图像-视频），纯文本 LLM 热度相对下降，视觉理解与生成是用户核心需求。
- **开源权重继续碾压闭源**：DeepSeek、Qwen、Lightricks 等均以完全开源权重发布，下载量数百万级，闭源模型在 Hugging Face 上几乎无热度。
- **量化活动从“必要”走向“激进”**：ISTA-DASLab 的 RCO/GSQ 系列、prism-ml 的 Ternary 三值量化，以及 NVFP4、EXL3 等极低比特方案，表明社区在旗舰模型上追求极致压缩，以便在消费级硬件上运行 27B+ 模型。
- **企业入局加速**：Cloudflare、Google 等公司直接发布模型，说明多模态能力成为云服务标配。

## 值得探索

1. **Lightricks/LTX-2.5** – 当前最受关注的图像转视频模型，单文件扩散架构意味着低门槛部署。其生成质量在社区评测中表现出色，适合视频创作者和研究者测试视频生成边界。
2. **

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*