# Hugging Face 热门模型日报 2026-08-27

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-27 03:33 UTC

---

# Hugging Face 热门模型日报（2026-08-27）

## 今日速览

- **Qwen 生态持续爆发**：Qwen3.8-27B 基础模型以 12,916 点赞、3.3M 下载稳居榜首，社区衍生出十余种量化、去审查（abliterated/uncensored）版本，其中 unsloth 的 GGUF 版本下载量高达 7.6M。  
- **视频与音乐生成新星**：MiniMax 发布 H3 视频生成模型（4,504 点赞、4.8M 下载）和 Music3 音乐生成模型，Lightricks 的 LTX-2.5 也跻身热门，多模态生成赛道竞争激烈。  
- **Kimi-K3 与 DeepSeek-V4 强势登场**：moonshotai 的 Kimi-K3（11,019 点赞）和 deepseek-ai 的 DeepSeek-V4-Flash（3,742 点赞）均以超高下载量成为本周新晋焦点，代表国产大模型开源实力的持续输出。  
- **Ornith 系列 MoE 模型受关注**：ornith-ai 的 Ornith-1.5-35B-A3B（MoE 架构）及其 GGUF 版本获得社区下载，紧凑型 9B 版本同样热度不减。  
- **GLM-5.3-Flash 初登场**：zai-org 发布全新 GLM-5.3-Flash 文本生成模型，虽下载为 0，但已出现 unsloth 的量化版，预示即将进入主流视野。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

| 模型 | 作者 | 点赞 | 下载 | 说明 |
|------|------|------|------|------|
| [DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731) | deepseek-ai | 3,742 | 3,857,140 | DeepSeek 第四代对话模型，推理能力大幅提升，下载量高居前列。 |
| [zai-org/GLM-5.3-Flash](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 939 | 0 | GLM 最新 Flash 版本，主打高效文本生成，社区期待其实际表现。 |
| [ornith-ai/Ornith-1.5-35B-A3B](https://huggingface.co/ornith-ai/Ornith-1.5-35B-A3B) | ornith-ai | 455 | 83,342 | 35B 总参数、3B 激活参数的 MoE 模型，兼顾性能与效率。 |
| [ornith-ai/Ornith-1.5-9B](https://huggingface.co/ornith-ai/Ornith-1.5-9B) | ornith-ai | 229 | 119,053 | 9B 小尺寸 MoE 模型，适合资源受限场景。 |
| [superwhisper/s1-mini](https://huggingface.co/superwhisper/s1-mini) | superwhisper | 252 | 3,921 | 轻量级文本生成模型，集成 ASR 功能，探索语音-文本融合。 |

### 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型 | 作者 | 点赞 | 下载 | 说明 |
|------|------|------|------|------|
| [Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 12,916 | 3,298,569 | 多模态对话旗舰，支持图像+文本输入，本周最高人气模型。 |
| [Qwen/Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 3,686 | 2,551 | Qwen3.8 的 Flash 实验版，强调推理速度，未来可能迭代。 |
| [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 4,504 | 4,793,098 | 多模态视频生成模型，支持文本/图像/视频到视频，下载量近 5M。 |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 1,871 | 894,094 | 图像到视频扩散模型，生成高质量短视频，创意工具热门。 |
| [MiniMaxAI/MiniMax-Music3](https://huggingface.co/MiniMaxAI/MiniMax-Music3) | MiniMaxAI | 1,264 | 19,501 | 文本到音乐生成模型，音乐创作新利器。 |
| [moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3) | moonshotai | 11,019 | 2,921,257 | Kimi 最新多模态模型，支持图像+文本理解，压缩架构，下载量极高。 |
| [sensenova/SenseNova-U1.5-8B-MoT](https://huggingface.co/sensenova/SenseNova-U1.5-8B-MoT) | sensenova | 173 | 3,264 | 原生多模态（any-to-any），可处理文字、图像、音频等多种输入。 |
| [Audio8/Audio8-TTS-Preview-0.1b](https://huggingface.co/Audio8/Audio8-TTS-Preview-0.1b) | Audio8 | 174 | 4,257 | 预览版语音合成模型，基于 ArkTTS，注重自然度。 |

### 🔧 专用模型（代码、数学、医疗、嵌入等）

（本日榜单中专用模型较少，多数为通用或多模态模型。以下模型偏向特定任务）

| 模型 | 作者 | 点赞 | 下载 | 说明 |
|------|------|------|------|------|
| [froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates) | froggeric | 1,488 | 0 | 修复 Qwen 聊天模板的实用工具，提升开发者体验。 |
| [alibaba-pai/MiniMax-H3-Fun-Controlnet-Union](https://huggingface.co/alibaba-pai/MiniMax-H3-Fun-Controlnet-Union) | alibaba-pai | 139 | 3,148 | 基于 MiniMax-H3 的 ControlNet 扩展，增强视频生成可控性。 |

### 📦 微调与量化（社区微调、GGUF、AWQ、abliterated）

| 模型 | 作者 | 点赞 | 下载 | 说明 |
|------|------|------|------|------|
| [unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF) | unsloth | 3,006 | 7,638,591 | Qwen3.8-27B 的 GGUF 量化版，社区最热下载模型，适合本地部署。 |
| [JonathanColetti/Qwen3.8-27B-Uncensored-GGUF](https://huggingface.co/JonathanColetti/Qwen3.8-27B-Uncensored-GGUF) | JonathanColetti | 755 | 1,620,754 | 去审查的 GGUF 版本，满足个性化需求，下载量超 1.6M。 |
| [HauhauCS/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF](https://huggingface.co/HauhauCS/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF) | HauhauCS | 662 | 911,795 | 激进去审查+多token预测 (MTP) 的 GGUF 变体。 |
| [OBLITERATUS/Qwen3.8-27B-OBLITERATED](https://huggingface.co/OBLITERATUS/Qwen3.8-27B-OBLITERATED) | OBLITERATUS | 815 | 468,746 | 强力去审查（abliterated）版本，支持 MLX 和 GGUF 格式。 |
| [orcarouter/Qwen3.8-27B-Uncensored-FP8](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-FP8) | orcarouter | 1,179 | 269,805 | FP8 精度去审查版，兼顾性能与显存。 |
| [orcarouter/Qwen3.8-27B-Uncensored-MLX](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-MLX) | orcarouter | 1,142 | 79,395 | 专为 Apple Silicon 优化的 MLX 去审查版。 |
| [huihui-ai/Huihui-Qwen3.8-27B-abliterated-GGUF](https://huggingface.co/huihui-ai/Huihui-Qwen3.8-27B-abliterated-GGUF) | huihui-ai | 378 | 1,318,749 | 另一流行的去审查 GGUF 版本，下载量超 1.3M。 |
| [ornith-ai/Ornith-1.5-35B-A3B-GGUF](https://huggingface.co/ornith-ai/Ornith-1.5-35B-A3B-GGUF) | ornith-ai | 318 | 1,391,218 | Ornith MoE 模型的 GGUF 量化版，便于本地运行。 |
| [ornith-ai/Ornith-1.5-9B-GGUF](https://huggingface.co/ornith-ai/Ornith-1.5-9B-GGUF) | ornith-ai | 218 | 1,389,641 | 9B 小模型量化版，轻量级部署首选。 |
| [DavidAU/Qwen3.8-27B-Cold-Fusion-GAIN-V1.1-NM-DAU-NEO-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.8-27B-Cold-Fusion-GAIN-V1.1-NM-DAU-NEO-MAX-MTP-GGUF) | DavidAU | 253 | 232,525 | 融合 GAIN 训练与冷融合技术的定制 GGUF 版本。 |
| [EschaLabs/Qwen3.8-27B-Escha-W2](https://huggingface.co/EschaLabs/Qwen3.8-27B-Escha-W2) | EschaLabs | 133 | 2,481 | 2-bit 极致量化实验，探索超低比特压缩。 |
| [unsloth/Qwen3.8-Flash-Next-GGUF](https://huggingface.co/unsloth/Qwen3.8-Flash-Next-GGUF) | unsloth | 360 | 0 | 新 Flash 模型的 GGUF 版，尚未有效下载，但值得关注。 |
| [unsloth/GLM-5.3-Flash-GGUF](https://huggingface.co/unsloth/GLM-5.3-Flash-GGUF) | unsloth | 127 | 0 | GLM-5.3 的 GGUF 量化版，刚发布，预计后续下载量会增长。 |

## 生态信号

**模型家族势头**：Qwen3.8 系列在 Hugging Face 上形成“母模型+海量社区衍生”的超级生态，从基础权重到各类量化、去审查、微调版本一应俱全，下载量总和突破数千万。MiniMax 在视频生成（H3）和音乐生成（Music3）两个赛道同时发力，成为多模态生成的新势力。Ornith 的 MoE 架构以“小激活、大参数”思路吸引关注，量化版本下载量迅速攀升。

**开源权重 vs 闭源**：本周榜单全部为开源模型，且多数采用 Apache 2.0 或 MIT 许可证。DeepSeek-V4、Kimi-K3、Qwen3.8 等国产大模型均开放权重，显示出开源生态的强劲活力。闭源模型（如 GPT-4o、Claude）未出现在 HF 热门榜，社区选择明显偏向可部署、可定制的开源方案。

**量化与微调活动**：GGUF 格式几乎成为本地部署的“标准格式”，unsloth 贡献了多个热门量化版本。去审查（abliterated/uncensored）是本周最活跃的社区微调方向，至少有 5 个独立的 Qwen3.8-27B 去审查版本，反映了用户对内容自由度的强烈需求。此外，FP8、2-bit 等极致量化实验也出现，体现社区对效率的极致追求。

## 值得探索

1. **[moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3)**  
   作为 Kimi 最新多模态模型，点赞 11,019、下载 2.9M，性能与口碑俱佳，且采用压缩张量技术，可能是下半年多模态基准的有力竞争者。建议第一时间部署体验其图像理解与对话能力。

2. **[ornith-ai/Ornith-1.5-35B-A3B-GGUF](https://huggingface.co/ornith-ai/Ornith-1.5-35B-A3B-GGUF)**  
   作为 MoE 架构的代表，35B 总参数仅需 3B 激活，推理效率极高，GGUF 版本下载量已达 1.4M。适合研究稀疏激活模型的性能与成本平衡，也适合在消费级硬件上运行高质量对话。

3. **[MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)**  
   视频生成模型下载量近 5M，是本周除 Qwen 外最热的多模态工具。支持文本/图像/视频到视频，配合 ControlNet 扩展（如 alibaba-pai 的版本），可极大拓展视频创作边界。建议 AI 视频创作者和研究者重点测试。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*