# Hugging Face 热门模型日报 2026-09-11

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-11 00:31 UTC

---

# Hugging Face 热门模型日报（2026-09-11）

## 今日速览

今日 Hugging Face 趋势榜呈现三个突出特征：**Qwen3.8 系列全面霸榜**，其基础模型、量化版、微调版及实验版占据近半数榜单，成为当日生态核心；**视频生成模型异军突起**，MiniMax-H3 与 LTX-2.5 持续火爆，周下载量分别超500万和170万；**社区微调活跃度极高**，uncensored、GGUF、abliterated 等非审查量化版本数量激增，反映开发者对自由定制模型的强烈需求。此外，微软、谷歌发布专用模型（ASR、时序预测），拓宽了生态边界。

---

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

| 模型名（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|---------------|------|------|------|------------|
| [DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek-ai | 1,345 | 6 | DeepSeek 最新多模态文本生成模型，定位快速推理，尚未大规模下载但获社区高关注。 |
| [MiniCPM5-2B](https://huggingface.co/openbmb/MiniCPM5-2B) | openbmb | 1,111 | 42,289 | 轻量级 2B 参数 Llama 架构模型，适合边缘部署，下载量极高。 |
| [Spark-X2.5-4B](https://huggingface.co/XHToken/Spark-X2.5-4B) | XHToken | 1,062 | 15,930 | 4B 参数 LLM，主打高效推理，社区口碑好。 |
| [GLM-5.3](https://huggingface.co/zai-org/GLM-5.3) | zai-org | 1,800 | 552,019 | GLM 系列最新 MoE 对话模型，周点赞近 2k，下载超 55 万。 |
| [GLM-5.3-CYBERSECURITY-FP8](https://huggingface.co/dealignai/GLM-5.3-CYBERSECURITY-FP8) | dealignai | 368 | 24,303 | GLM-5.3 的网络安全专用版，FP8 量化且经 refusal-removed 处理。 |
| [K2-Horizon-MoVA-36B-A4B](https://huggingface.co/IFM/K2-Horizon-MoVA-36B-A4B) | IFM | 274 | 4,488 | 36B 激活仅 4B 的 MoE 模型，探索高效推理新架构。 |
| [Qwen-Drive-1.0-4B](https://huggingface.co/Qwen/Qwen-Drive-1.0-4B) | Qwen | 154 | 2,759 | Qwen 驱动的自动驾驶专用视觉语言模型，任务明确。 |

### 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型名（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|---------------|------|------|------|------------|
| [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 14,643 | 7,322,476 | Qwen 旗舰多模态模型（image-text-to-text），周点赞超1.4万，是当日绝对顶流。 |
| [Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 5,078 | 564,079 | Qwen 实验性“Flash Next”版本，推理速度与能力平衡，点赞5k+。 |
| [DeepSeek-V4-Flash-Vision-Exp](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-Vision-Exp) | deepseek-ai | 858 | 400,892 | DeepSeek V4 视觉版实验模型，支持图像文本联合理解。 |
| [MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 5,126 | 5,080,204 | MiniMax 最新文本到视频/图像到视频模型，下载破500万。 |
| [LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 3,384 | 1,740,572 | 多功能扩散模型，支持图像转视频、文本转视频等多任务。 |
| [Minimax-h3_Singularity](https://huggingface.co/WarmBloodAban/Minimax-h3_Singularity) | WarmBloodAban | 261 | 96,682 | MiniMax-H3 的社区衍生版，专注于视频生成优化。 |
| [vdn-minimax-h3](https://huggingface.co/OpenVDN/vdn-minimax-h3) | OpenVDN | 286 | 39 | MiniMax-H3 的 Fine-tune 版本，用于视频生成微调研究。 |
| [Breeze-TTS-2](https://huggingface.co/BreezeBlue/Breeze-TTS-2) | BreezeBlue | 529 | 8,227 | 文本到语音模型，社区关注度上升，适合语音合成应用。 |
| [VibeVoice-ASR-Streaming-7B](https://huggingface.co/microsoft/VibeVoice-ASR-Streaming-7B) | microsoft | 187 | 2,065 | 微软流式语音识别模型，7B 参数，面向实时转录。 |

### 🔧 专用模型（代码、数学、医疗、嵌入、时间序列等）

| 模型名（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|---------------|------|------|------|------------|
| [timesfm-3.0-pytorch](https://huggingface.co/google/timesfm-3.0-pytorch) | google | 716 | 483,787 | Google 发布的时间序列预测模型，PyTorch 版，通用预测利器。 |
| [Viggle-Animate](https://huggingface.co/Viggle/Viggle-Animate) | Viggle | 155 | 0 | 视频到视频编辑模型，可替换角色，虽下载为0但得到社区点赞。 |
| [Qwen-Drive-1.0-4B](https://huggingface.co/Qwen/Qwen-Drive-1.0-4B)（同上） | Qwen | 154 | 2,759 | 自动驾驶领域专用视觉语言模型，已在专用场景落地。 |

### 📦 微调与量化（社区微调、GGUF、AWQ、FP8等）

| 模型名（链接） | 作者 | 点赞 | 下载 | 一句话说明 |
|---------------|------|------|------|------------|
| [Qwen3.8-27B-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF) | ISTA-DASLab | 795 | 614,850 | 学术界出品的创新量化方案（GSQ+RCO），下载量近62万。 |
| [Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF) | unsloth | 3,846 | 11,127,203 | unsloth 优化的 Qwen3.8 标准 GGUF 量化版，下载量破千万，社区首选。 |
| [Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF) | DavidAU | 449 | 517,644 | 极端社区微调版，集成 uncensored、fine-tune 等多个标签，下载量大。 |
| [Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF](https://huggingface.co/HauhauCS/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF) | HauhauCS | 1,076 | 1,908,917 | 去审查的激进微调版，周点赞超1k，下载近200万。 |
| [Qwen3.8-27B-Uncensored-GGUF](https://huggingface.co/orcarouter/Qwen3.8-27B-Uncensored-GGUF) | orcarouter | 865 | 314,894 | 另一个 uncensored 量化版本，abiiterated 处理，社区活跃。 |
| [Qwen3.8-Flash-Next-GGUF](https://huggingface.co/unsloth/Qwen3.8-Flash-Next-GGUF) | unsloth | 879 | 1,053,823 | unsloth 对 Flash Next 实验版的 GGUF 量化，下载破百万。 |
| [Qwen3.8-Flash-Next-NVFP4](https://huggingface.co/nvidia/Qwen3.8-Flash-Next-NVFP4) | nvidia | 192 | 62,813 | NVIDIA 提供的 NVFP4 量化版，结合 Model Optimizer 工具。 |
| [Qwopus3.8-27B-Flash-GGUF](https://huggingface.co/Jackrong/Qwopus3.8-27B-Flash-GGUF) | Jackrong | 187 | 192,107 | 第三方对 Qwen3.8 的 Flash 量化变体。 |
| [MiniCPM5-2B-GGUF](https://huggingface.co/openbmb/MiniCPM5-2B-GGUF) | openbmb | 152 | 51,179 | MiniCPM5 官方 GGUF 版，面向本地运行。 |
| [Spark-X2.5-4B-GGUF](https://huggingface.co/XHToken/Spark-X2.5-4B-GGUF) | XHToken | 134 | 73,777 | Spark-X2.5 的 GGUF 版本，支持 llama.cpp / Ollama 生态。 |
| [GLM-5.3-Flash](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 2,227 | 1,023,103 | GLM-5.3 的 Flash 快速推理版，周点赞2k+，下载超百万。 |

---

## 生态信号

**模型家族势能分化**：Qwen 系列（Qwen3.8、Flash Next、Drive）占据最强势头，官方模型与社区衍生版本形成完整生态闭环；MiniMax-H3 在视频生成领域快速崛起，与 Lightricks LTX-2.5 形成双引擎；GLM 系列（zai-org 与 dealignai）在安全微调方向开辟细分赛道。

**量化与微调成为社区主战场**：GGUF 格式几乎成为量化分发标配，unsloth 凭借高通量和工具链优势占据核心位置。值得注意的是，“Uncensored / abliterated / refusal-removed” 类微调版本增长迅猛，反映开发者对模型自由度的强烈需求，但也可能引发内容安全争论。

**开源权重优势明显**：榜单前 10 名中仅 google/timesfm 为专有模型但开源权重，其余均为开放权重模型。视频生成模型（MiniMax-H3、LTX）均提供可下载权重，未出现闭源 API 独占情况。

---

## 值得探索

1. **[Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF)**  
   —— 下载量超 1100 万，是目前最受社区认可的量化多模态模型，适合本地部署及二次微调。

2. **[MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)**  
   —— 文本/图像到视频生成能力突出，下载量超 500 万，是探索多模态生成应用的最佳起点。

3. **[timesfm-3.0-pytorch](https://huggingface.co/google/timesfm-3.0-pytorch)**  
   —— Google 出品的时间序列预测模型，弥补了通用领域专用模型的空白，适合工业级时序分析任务。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*