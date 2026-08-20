# Hugging Face 热门模型日报 2026-08-21

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-20 23:00 UTC

---

好的，这是为您准备的《Hugging Face 热门模型日报》（2026-08-21）。

---

### **Hugging Face 热门模型日报 | 2026-08-21**

#### **今日速览**

本周 Hugging Face 生态呈现两大核心趋势：**Qwen3.8家族的多模态统治力**与**社区“无审查”微调热潮**。Qwen3.8-27B 原始模型以绝对优势霸榜，其衍生出的各种量化（GGUF、FP8、NVFP4）及“无审查”（Abliterated、Uncensored）版本占据了榜单近半壁江山。此外，视频生成赛道竞争激烈，MiniMax 的 H3 模型与 Lightricks 的 LTX-2.5 均获得大量关注，表明多模态生成正从图像向视频领域快速迁移。值得关注的是，DeepSeek 的 V4 系列和 MoonshotAI 的 Kimi-K3 也在榜单中表现强劲，说明开源社区对高性能 MoE 架构模型的热情不减。

#### **热门模型**

**🧠 语言模型（LLM、对话模型、指令微调）**

- **[Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B)** (Qwen, 11,734赞, 1.37M下载) — 本周最热门的多模态模型，强大的图像理解与对话能力，是社区进行微调、量化的基础模型。
- **[deepseek-ai/DeepSeek-V4-Pro-0813](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813)** (deepseek-ai, 677赞, 43.3K下载) — DeepSeek V4 系列的高性能版本，专注于文本生成，代表了当前顶尖的MoE架构开源模型。
- **[Qwen/Qwen3.8-2.4T-A95B](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B)** (Qwen, 1,121赞, 14.6K下载) — 阿里通义千问发布的超大规模MoE模型，总参数量2.4T，激活参数95B，性能强劲。
- **[deepseek-ai/DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731)** (deepseek-ai, 3,575赞, 2.55M下载) — V4系列的高效版本，在保证性能的同时优化了推理速度，下载量极高。
- **[moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3)** (moonshotai, 10,883赞, 2.35M下载) — Moonshot AI 最新力作，采用压缩张量技术，同样是多模态模型，关注度极高。
- **[ornith-ai/Ornith-1.5-35B-A3B](https://huggingface.co/ornith-ai/Ornith-1.5-35B-A3B)** (ornith-ai, 212赞, 1.7K下载) — 基于Qwen3.5 MoE架构的35B模型，激活参数仅3B，主打高效推理。

**🎨 多模态与生成（图像、视频、音频、文本到X）**

- **[MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)** (MiniMaxAI, 4,238赞, 3.31M下载) — 专注于视频生成，支持文本到视频、图像到视频，是本周下载量最高的视频模型之一。
- **[MiniMaxAI/MiniMax-Music3](https://huggingface.co/MiniMaxAI/MiniMax-Music3)** (MiniMaxAI, 1,102赞, 14.5K下载) — 专为音乐生成设计的扩散模型，标志着AI生成内容向音频领域的进一步拓展。
- **[Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5)** (Lightricks, 1,412赞, 611.8K下载) — 图像到视频生成模型，支持文本、图像、视频等多种输入方式，体现了视频生成技术的成熟。
- **[meta-models/Muse-Glimmer-30B](https://huggingface.co/meta-models/Muse-Glimmer-30B)** (meta-models, 1,718赞, 478.6K下载) — 大型多模态模型，具备强大的图像理解与对话能力，是Meta在开源领域的又一重要贡献。
- **[lightx2v/Minimax-h3-Turbo](https://huggingface.co/lightx2v/Minimax-h3-Turbo)** (lightx2v, 649赞, 380.1K下载) — MiniMax-H3的加速版本，优化了推理速度，专为视频生成场景设计。

**🔧 专用模型（代码、数学、医疗、嵌入）**

- *（今日榜单上暂无突出的专用模型上榜）*

**📦 微调与量化（社区微调、GGUF、AWQ）**

- **[unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF)** (unsloth, 2,350赞, 5.13M下载) — 由Unsloth社区提供的GGUF量化版，是本周下载量最高的模型，极大降低了本地部署门槛。
- **[orcarouter/Qwen3.8-27B-Uncensored-MLX](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-MLX)** (orcarouter, 708赞, 2.6K下载) — 针对Apple Silicon优化的MLX格式“无审查”版本，反映了社区对特定硬件优化的需求。
- **[orcarouter/Qwen3.8-27B-Uncensored-FP8](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-FP8)** (orcarouter, 675赞, 76.1K下载) — FP8精度量化的“无审查”版本，在性能与模型体积间取得平衡。
- **[DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF)** (DavidAU, 2,183赞, 3.00M下载) — 社区微调与量化的大成之作，集“无审查”、“异端”等多种风格于一身，下载量极高，是社区活跃度的缩影。
- **[unsloth/Qwen3.8-27B-NVFP4](https://huggingface.co/unsloth/Qwen3.8-27B-NVFP4)** (unsloth, 308赞, 831.5K下载) — 采用NVIDIA FP4精度的超低比特量化版本，为极致本地化部署提供可能。
- **其他“无审查”量化版本**：如 [JonathanColetti](https://huggingface.co/JonathanColetti/Qwen3.8-27B-Uncensored-GGUF)、[HauhauCS](https://huggingface.co/HauhauCS/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF)、[huihui-ai](https://huggingface.co/huihui-ai/Huihui-Qwen3.8-27B-abliterated-GGUF)、[0bserverx](https://huggingface.co/0bserverx/Qwen3.8-27B-Heretic-Abliterated-Uncensored-GGUF) 等，均基于Qwen3.8-27B进行微调后量化，显示了社区对“无审查”模型的巨大热情。

#### **生态信号**

- **Qwen3.8家族一骑绝尘**：阿里Qwen团队可能已稳固其开源大模型领导者的地位。Qwen3.8-27B不仅自身登顶，其衍生出的量化、微调模型更是霸榜，形成了一个庞大且活跃的生态。
- **“无审查”成为社区主旋律**：榜单中近半数模型带有“abliterated”或“uncensored”标签，这反映了社区对于模型使用限制的普遍诉求，以及通过技术手段（如模型微调）绕过限制的强盛势头。
- **量化推动模型普及**：Unsloth等社区贡献的GGUF量化版本，下载量远超原始模型，表明将大模型部署到消费级硬件已成为主流需求。同时，FP4、NVFP4等新型低比特量化格式的出现，预示着未来模型将更加便携。
- **多模态生成从“图”到“音视频”**：视频（MiniMax-H3, LTX-2.5）和音乐（MiniMax-Music3）生成模型的上榜，标志着AI生成内容正从静态图像全面转向动态和音频领域，应用场景更加丰富。

#### **值得探索**

1.  **[Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B)**：作为生态核心，建议直接体验其原生的多模态能力，了解当前顶尖开源模型的水准。它是所有社区微调的基础，理解其性能至关重要。
2.  **[MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)**：如果你想探索AI视频生成的前沿，这个模型是本周的必试项。其高下载量和高点赞数证明了其质量，从中可以直观感受到AI生成视频技术的成熟度。
3.  **[unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF)**：对于希望本地部署模型的开发者或研究者，这是最稳妥的选择。它证明了如何用优秀的量化技术让一个27B的大模型在普通硬件上流畅运行，是模型应用落地的典范。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*