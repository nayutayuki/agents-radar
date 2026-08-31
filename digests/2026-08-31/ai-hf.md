# Hugging Face 热门模型日报 2026-08-31

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-31 00:48 UTC

---

# Hugging Face 热门模型日报（2026-08-31）

## 今日速览

**1. 多模态语言模型统治榜单**：Qwen 3.8 系列（Qwen3.8-27B、Flash-Next）和 Kimi K3 包揽点赞前三，分别获得 13,348 和 11,100 点赞，表明社区对大型多模态对话模型的高度关注。  
**2. 视频生成模型爆发**：MiniMax-H3 和 Lightricks LTX-2.5 分别以 4,660 和 2,267 点赞领跑视频生成赛道，且下游衍生出大量 ControlNet、LoRA 和加速推理版本。  
**3. 量化与去审查（abliterated）版本成标配**：围绕 Qwen 3.8-27B 的 GGUF、FP8、MLX 以及 uncensored/abliterated 变体超过 10 个，说明社区对本地部署和内容自由度的强烈需求。  
**4. 国内大厂密集释放新模型**：Qwen（阿里）、GLM（智谱）、DeepSeek、Kimi（月之暗面）、腾讯 Hy4、MiniMax 等均有新品上榜，开源生态持续活跃。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

| 模型（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|-------------|------|------|------|-----------|
| [DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731) | deepseek-ai | 3,824 | 4.58M | 深度求索最新 V4 系列 Flash 版，对话能力强劲，下载量仅次于 Qwen。 |
| [zai-org/GLM-5.3-Flash](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 1,714 | 346K | 智谱 GLM-5 系列轻量版，支持图像+文本输入，兼顾速度与性能。 |
| [zai-org/GLM-5.3](https://huggingface.co/zai-org/GLM-5.3) | zai-org | 1,340 | 50K | GLM-5 完整版，采用 MoE 架构，擅长多轮对话，社区关注度高。 |
| [tencent/Hy4-preview](https://huggingface.co/tencent/Hy4-preview) | tencent | 319 | 2.1K | 腾讯混元 V4 预览版，纯文本生成模型，尚在早期测试阶段。 |
| [pipecat-ai/phonellm-alpha-1](https://huggingface.co/pipecat-ai/phonellm-alpha-1) | pipecat-ai | 150 | 4K | 基于 Nemotron 的语音专用 LLM 预研版，探索语音交互新范式。 |

### 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|-------------|------|------|------|-----------|
| [Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 13,348 | 4.51M | 阿里最新 27B 多模态对话模型，支持图像+文本输入，本周点赞数与下载量双冠。 |
| [Qwen/Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 4,389 | 122K | 阿里 Qwen 4 实验版，更快推理，多模态能力延续，社区期待下一代旗舰。 |
| [moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3) | moonshotai | 11,100 | 2.79M | 月之暗面最新多模态模型，采用压缩张量技术，点赞量仅次于 Qwen3.8-27B。 |
| [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 4,660 | 5.26M | 最强的文本到视频（含图像到视频）模型之一，高下载量表明业界广泛使用。 |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 2,267 | 1.14M | 图像到视频扩散模型，支持文本/视频/图像多种输入，创意工具首选。 |
| [BreezeBlue/Breeze-TTS-2](https://huggingface.co/BreezeBlue/Breeze-TTS-2) | BreezeBlue | 212 | 1.8K | 新一代文本转语音模型，关注度虽低但代表音声合成新方向。 |
| [FastVideo/FastVideo-FastH3-4-step-Preview-v1-VSA-DataFree](https://huggingface.co/FastVideo/FastVideo-FastH3-4-step-Preview-v1-VSA-DataFree) | FastVideo | 193 | 0 | 基于 MiniMax-H3 的 4 步加速推理预研，无数据蒸馏，零下载但技术前瞻。 |
| [alibaba-pai/MiniMax-H3-Fun-Controlnet-Union](https://huggingface.co/alibaba-pai/MiniMax-H3-Fun-Controlnet-Union) | alibaba-pai | 163 | 5.5K | 阿里 PAI 为 MiniMax-H3 定制的 ControlNet，支持更精细的视频控制。 |
| [alibaba-pai/MiniMax-H3-Acc-LoRAs](https://huggingface.co/alibaba-pai/MiniMax-H3-Acc-LoRAs) | alibaba-pai | 152 | 23.7K | MiniMax-H3 加速 LoRA 集合，降低推理成本，适合高效部署。 |
| [Kijai/MiniMax-H3-experimental](https://huggingface.co/Kijai/MiniMax-H3-experimental) | Kijai | 362 | 0 | 社区实验版 MiniMax-H3，探索新功能，虽无下载但引发讨论。 |

### 🔧 专用模型（代码、数学、医疗、嵌入）

本周榜单中专用模型较少，但以下模型值得关注：

| 模型（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|-------------|------|------|------|-----------|
| [peculiar-ragdoll/Tiel-Coder-35B-A3B-GGUF](https://huggingface.co/peculiar-ragdoll/Tiel-Coder-35B-A3B-GGUF) | peculiar-ragdoll | 141 | 87.8K | 基于 Qwen 3.5 MoE 的代码专用模型（35B-A3B），GGUF 量化版，适合本地编程助手。 |
| [thomsonreuters/Thomson-1.0-Small](https://huggingface.co/thomsonreuters/Thomson-1.0-Small) | thomsonreuters | 159 | 1K | 路透社推出的金融/法律领域多模态模型，小参数版，行业专用模型标杆。 |

### 📦 微调与量化（社区微调、GGUF、AWQ）

| 模型（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|-------------|------|------|------|-----------|
| [unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF) | unsloth | 3,240 | 8.84M | 官方推荐 GGUF 量化版，下载量惊人，成为本地部署首选。 |
| [unsloth/Qwen3.8-Flash-Next-GGUF](https://huggingface.co/unsloth/Qwen3.8-Flash-Next-GGUF) | unsloth | 603 | 328K | Flash-Next 的 GGUF 量化，让实验版也能在消费级显卡运行。 |
| [unsloth/GLM-5.3-Flash-GGUF](https://huggingface.co/unsloth/GLM-5.3-Flash-GGUF) | unsloth | 288 | 45.9K | GLM-5 轻量版的 GGUF 量化，满足本地部署需求。 |
| [OBLITERATUS/Qwen3.8-27B-OBLITERATED](https://huggingface.co/OBLITERATUS/Qwen3.8-27B-OBLITERATED) | OBLITERATUS | 946 | 725K | 著名的“去审查”版本，移除内容安全限制，引发伦理讨论。 |
| [orcarouter/Qwen3.8-27B-Uncensored-MLX](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-MLX) | orcarouter | 1,235 | 109K | MLX 格式的 uncensored 版，面向 Apple Silicon 用户。 |
| [orcarouter/Qwen3.8-27B-Uncensored-FP8](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-FP8) | orcarouter | 1,286 | 302K | FP8 精度量化版，平衡性能与质量，适合对显存敏感的场景。 |
| [orcarouter/Qwen3.8-27B-Uncensored-GGUF](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-GGUF) | orcarouter | 578 | 238K | 另一 GGUF 版 uncensored，社区多版本并存。 |
| [HauhauCS/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF](https://huggingface.co/HauhauCS/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF) | HauhauCS | 785 | 1.16M | 激进优化版，MTP 多 token 预测，下载量高，适合追求极致性能的玩家。 |
| [JonathanColetti/Qwen3.8-27B-Uncensored-GGUF](https://huggingface.co/JonathanColetti/Qwen3.8-27B-Uncensored-GGUF) | JonathanColetti | 850 | 1.99M | 另一流行 uncensored GGUF 版本，下载量接近 200 万。 |
| [huihui-ai/Huihui-Qwen3.8-27B-abliterated-GGUF](https://huggingface.co/huihui-ai/Huihui-Qwen3.8-27B-abliterated-GGUF) | huihui-ai | 457 | 1.62M | 使用“abliterated”技术去除安全对齐，社区广泛传播。 |
| [orcarouter/Qwen3.8-Flash-Next-Uncensored-GGUF](https://huggingface.co/orcarouter/Qwen3.8-Flash-Next-Uncensored-GGUF) | orcarouter | 123 | 42.9K | Flash-Next 的 uncensored 版，抢先体验下一代模型无限制能力。 |
| [Qwen/Qwen3.8-Flash-Next-FP8](https://huggingface.co/Qwen/Qwen3.8-Flash-Next-FP8) | Qwen | 159 | 76.9K | 官方出品的 FP8 量化版，集成在 transformers 生态中。 |
| [ornith-ai/Ornith-1.5-35B-A3B](https://huggingface.co/ornith-ai/Ornith-1.5-35B-A3B) | ornith-ai | 505 | 147K | 基于 Qwen 3.5 MoE 的社区微调版，多模态对话增强。 |

## 生态信号

**1. Qwen 生态绝对主导**：Qwen 3.8 系列（含 27B 和 Flash-Next）及其衍生量化/微调版本占据榜单近一半，呈现出“原生模型 + 多格式量化 + 去审查变体”的完整生态，类似此前 Llama 的扩散路径。  
**2. 视频生成赛道拥挤**：MiniMax-H3 快速积累多个下游适配（ControlNet、LoRA、加速），Lightricks LTX-2.5 也表现强劲，说明视频生成正在从“单模型”向“平台化工具链”演进。  
**3. 开源权重持续领先，闭源未见**：榜单所有模型均为开源权重，且无闭源 API 模型上榜，说明 Hugging Face 社区仍是开源模型的主战场。  
**4. 量化与微调活动高度集中**：GGUF 已成为最主流量化格式（unsloth 贡献巨大），而 uncensored/abliterated 版本的需求反映出社区对内容管控的逆反心理，值得关注其伦理影响。

## 值得探索

1. **[moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3)**  
   获得 11,100 点赞，使用压缩张量技术降低模型体积，却保持强大性能，是研究模型压缩与推理效率的绝佳案例。

2. **[MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)**  
   本周下载量超 526 万，视频生成能力领先，且已有多个加速和控制工具，适合尝试构建端到端视频生成应用。

3. **[FastVideo/FastVideo-FastH3-4-step-Preview-v1-VSA-DataFree](https://huggingface.co/FastVideo/FastVideo-FastH3-4-step-Preview-v1-VSA-DataFree)**  
   尽管下载量为零，但该模型展示了“无数据蒸馏的 4 步加速”技术，代表视频生成推理优化的前沿方向，值得技术研究者关注。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*