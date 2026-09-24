# Hugging Face 热门模型日报 2026-09-24

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-24 00:52 UTC

---

好的，没问题。以下是基于您提供的2026年9月24日数据生成的《Hugging Face 热门模型日报》。

---

# 🤗 Hugging Face 热门模型日报 (2026-09-24)

## 今日速览

本周 Hugging Face 生态被 **Qwen 家族** 强势主导，旗下多模态模型 Qwen3.8-27B 及其衍生版本占据了下载量和热度的顶端。与此同时，**DeepSeek** 的全能多模态 Flash 模型与 **MiniMax** 的视频生成模型也表现亮眼。此外，一个新的趋势是“**三元量化**”生态（如 Ternary-Bonsai）开始兴起，标志着社区对极致模型压缩与边缘部署的追求。值得注意的是，`convaiinnovations/laya` 作为一个全新的“明确性决策”文本分类模型，以零下载量获得了超高点赞，暗示了其在特定领域的创新潜力。

## 🧠 语言模型（LLM、对话模型、指令微调）

- **prism-ml/Ternary-Bonsai-2-27B-gguf**
  - 作者: prism-ml | 点赞: 1,956 | 下载: 2,815,979
  - 基于Qwen架构的三元量化（2-bit）模型，代表了在保持性能的同时将模型压缩至极致的“瘦身”趋势。

- **XingChen-AGI/Xing4.0-29B-A4B**
  - 作者: XingChen-AGI | 点赞: 1,591 | 下载: 39,009
  - 一款采用类MoE结构的对话模型，展现了社区在稀疏混合专家模型上的探索。

- **Altworld/Hemmingway-1**
  - 作者: Altworld | 点赞: 577 | 下载: 3,787
  - 基于 Qwen3.8 微调的文本生成模型，主打特定的写作风格或指令遵循能力。

- **harshatheg/Qwen-2.5-1B-RLCD**
  - 作者: harshatheg | 点赞: 559 | 下载: 0
  - 一个专注在Apple Silicon上高效运行的小模型，结合了并行解码与结构化生成技术。

- **yandex/AliceAI-Foundation-80B-A3B-Base**
  - 作者: yandex | 点赞: 296 | 下载: 2,254
  - 俄罗斯科技巨头Yandex发布的高效超大模型（80B参数，激活仅3B），展示了极致的参数效率。

## 🎨 多模态与生成（图像、视频、音频、文本到X）

- **Qwen/Qwen-Image-2.1**
  - 作者: Qwen | 点赞: 2,035 | 下载: 28,407
  - Qwen官方出品的图像生成与编辑模型，是当前技术生态的中坚力量。

- **deepseek-ai/DeepSeek-V4.1-Flash**
  - 作者: deepseek-ai | 点赞: 3,667 | 下载: 570,909
  - DeepSeek的旗舰多模态模型，支持图文理解与生成，是当前性能最顶级的开源模型之一。

- **Qwen/Qwen3.8-27B**
  - 作者: Qwen | 点赞: 16,138 | 下载: 6,912,469
  - **本周绝对热点**。Qwen 最新一代多模态（图文理解）大模型，凭借强大的综合性能引爆社区下载。

- **Lightricks/LTX-2.5**
  - 作者: Lightricks | 点赞: 4,902 | 下载: 1,638,605
  - 图像/文本到视频生成模型，代表了视频生成领域的最新进展，在创意工具链中至关重要。

- **MiniMaxAI/MiniMax-H3**
  - 作者: MiniMaxAI | 点赞: 5,628 | 下载: 3,664,216
  - 视频生成领域的热门模型，支持文本与图像输入生成视频，下载量极高，社区应用广泛。

- **m-a-p/YuE2-3B**
  - 作者: m-a-p | 点赞: 984 | 下载: 22,415
  - 专注于音乐生成的模型，引入了“符号规划”与“代理编辑”等高级功能，开启了AI音乐创作的新维度。

## 🔧 专用模型（代码、数学、医疗、嵌入等）

- **convaiinnovations/laya**
  - 作者: convaiinnovations | 点赞: 3,107 | 下载: 0
  - 一个全新的“明确性决策”文本分类模型。虽然下载量为0，但异常高的点赞数预示其可能是重要的学术突破或创新架构。

- **AlexWortega/openjev**
  - 作者: AlexWortega | 点赞: 520 | 下载: 0
  - 一个用于自然语言推断（NLI）的交叉编码器模型，在语义匹配领域具有潜在价值。

- **netease-youdao/Confucius4-R2T2**
  - 作者: netease-youdao | 点赞: 355 | 下载: 3,708
  - 网易有道推出的语音识别模型，代表了前沿的ASR技术栈。

- **TokenRhythm/NeoHorse-1-9B**
  - 作者: TokenRhythm | 点赞: 1,014 | 下载: 13,009
  - 一个默认带有代理（Agentic）能力的对话模型，反映了“模型即智能体”的融合趋势。

## 📦 微调与量化（社区微调、GGUF、AWQ）

- **abenzerps/Qwen-Image-2.1-Uncensored-GGUF**
  - 作者: abenzerps | 点赞: 1,432 | 下载: 350,678
  - 对Qwen图像模型的无审查GGUF量化版本，满足特定社区对“自由”生成的需求。

- **Comfy-Org/Qwen-Image-2.1**
  - 作者: Comfy-Org | 点赞: 626 | 下载: 2,220,609
  - ComfyUI官方提供的Qwen图像模型单文件版，极大地降低了在主流工作流工具中的部署门槛。

- **ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF**
  - 作者: ISTA-DASLab | 点赞: 1,614 | 下载: 1,414,991
  - 学术界对Qwen3.8-27B进行的高阶量化研究（GSQ + RCO），代表了量化方法的学术前沿。

- **DavidAU/...NEO-CODER-MAX-MTP-GGUF**
  - 作者: DavidAU | 点赞: 1,126 | 下载: 1,452,915
  - 社区狂热者制作的“缝合怪”模型，融合了多种微调技术（如Unsloth）和不同的LoRA文件，体现了社区对“极限性能”的追求。

- **unsloth/Qwen3.8-27B-GGUF**
  - 作者: unsloth | 点赞: 4,563 | 下载: 7,134,167
  - **下载量冠军**。来自知名微调工具库Unsloth的官方GGUF版本，是普通用户使用Qwen3.8-27B的首选量化格式。

## 生态信号

**Qwen 家族绝对统治**：Qwen3.8-27B 及其衍生模型（微调、量化、GGUF）几乎占据了榜单的半壁江山，下载量遥遥领先。这表明 Qwen 已成为当前开源社区事实上的“AI基础模型标准”之一。**DeepSeek** 和 **MiniMax** 则构成了有力的挑战者阵营，分别在多模态理解和视频生成上多点开花。

**三元量化生态崛起**：`prism-ml/Ternary-Bonsai-2-27B` 的爆火，标志着一个新的模型压缩生态（Ternary）正在形成。社区对“更小、更快、能在端侧运行”的追求正在催生出专门的量化基础设施。

**多模态与视频生成是主战场**：无论是 Qwen、DeepSeek 还是 Lightricks、MiniMax，多模态理解和生成（尤其是视频）已经成为模型核心竞争力的标配，是当前技术竞赛的关键。

## 值得探索

1.  **Qwen/Qwen3.8-Flash-Next (5,643 赞)**: 作为Qwen3.8的“Next”版本，它可能是未来技术方向的预告，值得深入研究其架构和能力的演进。
2.  **convaiinnovations/laya (3,107 赞)**: 极高的点赞与零下载形成鲜明对比，初步判断这很可能是一个提供突破性新功能的理论或算法模型。它代表了不同于Scaling Law的另一种创新路径，值得所有从业者关注。
3.  **m-a-p/YuE2-3B (984 赞)**: 音乐生成是AIGC中极为复杂但也极具潜力的领域。该模型引入了“符号规划”和“代理编辑”，将AI从单纯的“生成器”变为“协作者”，是创意AI领域一个值得关注的尝试。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*