# Hugging Face 热门模型日报 2026-09-15

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-15 00:53 UTC

---

# Hugging Face 热门模型日报 | 2026-09-15

## 🔥 今日速览

本周 Hugging Face 热度由多模态大模型主导：阿里 Qwen 家族的 **Qwen3.8-27B** 以超 1.5 万点赞和 770 万下载稳居榜首，其 GGUF 量化版也紧随其后。视频生成赛道竞争白热化，MiniMax-H3 和 Lightricks LTX-2.5 双双冲入热门榜前段，标志着**图像到视频 (I2V)** 成为社区新宠。此外，DeepSeek-V4.1-Flash、GLM-5.3-Flash 等新一代旗舰多模态模型集中爆发，显示**开源大模型正快速从纯文本向视觉-语言融合方向演进**。量化生态方面，Unsloth 和 ISTA-DASLab 针对 Qwen3.8 推出的 GGUF/GSQ 版本下载量惊人，反映出社区对「高效本地部署」的强烈需求。

## 📊 热门模型分类整理

### 🧠 语言模型（LLM、对话模型、指令微调）

| 模型 | 作者 | 👍 点赞 | 📥 下载 | 一句话说明 |
|------|------|---------|---------|------------|
| [**Edge0/Edge0-35B-A3B-preview**](https://huggingface.co/Edge0/Edge0-35B-A3B-preview) | Edge0 | 2,007 | 8,109 | 35B 总参数、3B 激活参数的 MoE 大模型，主打边缘推理高效性，深受开发者关注。 |
| [**openbmb/MiniCPM5-2B**](https://huggingface.co/openbmb/MiniCPM5-2B) | openbmb | 1,394 | 206,774 | 仅 2B 参数的小尺寸大模型，性能对标更大模型，开源社区热捧的轻量级 LLM。 |
| [**XHToken/Spark-X2.5-4B**](https://huggingface.co/XHToken/Spark-X2.5-4B) | XHToken | 1,171 | 24,084 | 4B 参数的对话模型，基于 Spark2.5 架构，面向通用对话和指令跟随任务。 |
| [**TokenRhythm/NeoHorse-1-4B**](https://huggingface.co/TokenRhythm/NeoHorse-1-4B) | TokenRhythm | 1,814 | 9,520 | 1.4B 参数、专为自主代理 (agentic) 场景设计的轻量模型，推理速度快。 |
| [**meta-llama/Llama-3.1-8B-Instruct**](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | meta-llama | 7,602 | 5,620,539 | Meta 旗舰开源指令模型，8B 参数、长上下文，持续作为社区基准。 |
| [**openai-community/gpt2**](https://huggingface.co/openai-community/gpt2) | openai-community | 4,076 | 15,182,177 | 经典文本生成模型，虽年代久远，但作为入门和测试工具仍被广泛使用。 |

---

### 🎨 多模态与生成（图像、视频、音频、文本到 X）

| 模型 | 作者 | 👍 点赞 | 📥 下载 | 一句话说明 |
|------|------|---------|---------|------------|
| [**deepseek-ai/DeepSeek-V4.1-Flash**](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash) | deepseek-ai | 2,452 | 288,414 | DeepSeek 最新旗舰多模态模型，支持图像+文本输入，推理速度优化。 |
| [**Qwen/Qwen3.8-27B**](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | **15,140** | **7,703,400** | 本周绝对顶流！阿里 Qwen3.8 系列 27B 多模态版本，视觉-语言能力超强，社区评测霸榜。 |
| [**Qwen/Qwen3.8-Flash-Next**](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 5,229 | 645,881 | Qwen4 代实验性闪速模型，在 Qwen3.8 基础上进一步提升推理速度和对话能力。 |
| [**nex-agi/Nex-N2.5-mini**](https://huggingface.co/nex-agi/Nex-N2.5-mini) | nex-agi | 781 | 4,543 | 基于 Qwen3.5 MoE 架构的小型多模态模型，适合资源受限场景。 |
| [**nex-agi/Nex-N2.5-Pro**](https://huggingface.co/nex-agi/Nex-N2.5-Pro) | nex-agi | 633 | 30,489 | 同一家族的进阶版 Pro，参数量更大，多模态理解能力更强。 |
| [**zai-org/GLM-5.3-Flash**](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 2,334 | 1,770,038 | 智谱 GLM 第五代闪速版，支持图像+文本输入，中文场景表现出色。 |
| [**Agnes-AI/Agnes-3.0-Flash**](https://huggingface.co/Agnes-AI/Agnes-3.0-Flash) | Agnes-AI | 157 | 736 | 新兴多模态模型，主打快速推理，尚在早期但受到关注。 |
| [**ukisai/Swift-Qwen3.8-27b**](https://huggingface.co/ukisai/Swift-Qwen3.8-27b) | ukisai | 152 | 459 | 社区基于 Qwen3.8-27B 的微调版本，侧重特定任务优化。 |
| [**Lightricks/LTX-2.5**](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 3,871 | 1,559,653 | 图像到视频 (I2V) 生成模型，支持多种视频转化模式，效果惊艳。 |
| [**MiniMaxAI/MiniMax-H3**](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 5,291 | 4,827,156 | MiniMax 推出的图像+文本到视频模型，下载量破百万，视频生成赛道新星。 |
| [**WarmBloodAban/Minimax-h3_Singularity**](https://huggingface.co/WarmBloodAban/Minimax-h3_Singularity) | WarmBloodAban | 396 | 141,057 | 社区基于 MiniMax-H3 的微调版，针对奇点风格视频生成优化。 |
| [**m-a-p/YuE2-3B**](https://huggingface.co/m-a-p/YuE2-3B) | m-a-p | 473 | 5,186 | 3

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*