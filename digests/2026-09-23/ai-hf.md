# Hugging Face 热门模型日报 2026-09-23

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-23 00:55 UTC

---

# 📰 Hugging Face 热门模型日报（2026-09-23）

## 今日速览

本周 Hugging Face 社区热度集中爆发在 **多模态大模型** 与 **极致量化** 两大方向。阿里 Qwen 家族持续统治榜单，其最新多模态模型 `Qwen3.8-27B` 以 **16,075 点赞** 和 **超 700 万下载** 断层领先。视频生成领域同样火热：MiniMax 发布的 `MiniMax-H3`（点赞 5,599，下载 376 万）和 Lightricks 的 `LTX-2.5`（点赞 4,796）分别统治图像→视频和文本→视频赛道。量化社区异常活跃，`ISTA-DASLab` 和 `unsloth` 推出的 GGUF 量化版本下载量动辄百万级，`prism-ml` 的 2-bit 三元量化模型 `Ternary-Bonsai-2-27B` 引发“极端压缩”讨论。此外，DeepSeek 的 `V4.1-Flash`、网易的语音识别模型 `Confucius4-R2T2` 以及 Yandex 的 80B 巨模型 `AliceAI-Foundation` 也进入用户视野。

---

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [Xing4.0-29B-A4B](https://huggingface.co/XingChen-AGI/Xing4.0-29B-A4B) | XingChen-AGI | 1,383 | 30,627 | 29B 参数但激活仅 4B 的 MoE 对话模型，主打高性价比推理。 |
| [Qwen-2.5-1B-RLCD](https://huggingface.co/harshatheg/Qwen-2.5-1B-RLCD) | harshatheg | 546 | 0 | 针对 Apple Silicon 优化的 1B 小模型，支持结构化并行解码（RLCD），尚未被广泛下载但技术新颖。 |
| [Hemmingway-1](https://huggingface.co/Altworld/Hemmingway-1) | Altworld | 495 | 2,745 | 基于 Qwen3.8 微调的写作辅助模型，侧重文学风格生成。 |
| [MiMo-V2.6-Pro-RL](https://huggingface.co/XiaomiMiMo/MiMo-V2.6-Pro-RL) | XiaomiMiMo | 386 | 985 | 小米出品的大语言模型 Pro 版，经强化学习对齐，适合多轮对话。 |
| [MiMo-V2.6-Flash-RL](https://huggingface.co/XiaomiMiMo/MiMo-V2.6-Flash-RL) | XiaomiMiMo | 381 | 2,641 | 小米的轻量版对话模型，Flash 架构兼顾速度与质量。 |
| [AliceAI-Foundation-80B-A3B-Base](https://huggingface.co/yandex/AliceAI-Foundation-80B-A3B-Base) | yandex | 276 | 1,516 | Yandex 开源的 80B 参数 MoE 基础模型（激活 3B），俄语/多语言背景，值得关注。 |
| [MiniCPM5-2B](https://huggingface.co/openbmb/MiniCPM5-2B) | openbmb | 1,664 | 508,950 | 小参数（2B）端侧模型，声称性能对标 7B 级，下载量验证了社区对“小但强”的偏好。 |
| [NeoHorse-1-9B](https://huggingface.co/TokenRhythm/NeoHorse-1-9B) | TokenRhythm | 1,009 | 12,574 | 基于 Qwen3.5 的 9B 指令/Agent 微调模型，标签含“agentic”，暗示工具调用能力。 |

### 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [Qwen-Image-2.1](https://huggingface.co/Qwen/Qwen-Image-2.1) | Qwen | 1,796 | 16,242 | 阿里官方发布的文本→图像模型，支持图像编辑，开启 Qwen 图像生成时代。 |
| [DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek-ai | 3,609 | 542,014 | 多模态理解 + 生成模型（输入图像+文本输出文本），DeepSeek 最新 Flash 版本，性能与速度平衡。 |
| [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | **16,075** | 7,079,646 | **本周绝对王者**，27B 多模态语言模型，支持图像+文本输入，对话质量和下载量均创纪录。 |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 4,796 | 1,630,125 | 图像→视频扩散模型，支持文本条件，电影级视频生成，社区追捧。 |
| [YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B) | m-a-p | 969 | 20,904 | 文本→音乐生成模型，引入符号规划与智能体编辑，AI 音乐创作利器。 |
| [Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 5,604 | 787,525 | Qwen 实验性下一代架构（exp），在 3.8 系列中主打更快推理，多模态能力不变

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*