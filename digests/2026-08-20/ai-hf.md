# Hugging Face 热门模型日报 2026-08-20

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-19 22:57 UTC

---

# 《Hugging Face 热门模型日报》— 2026-08-20

## 📌 今日速览

- **Qwen3.8 家族全面统治**：阿里 Qwen 的 27B 多模态模型以 11.4k 周点赞登顶，其量化、abliterated（去审查）和 uncensored 变体占据榜单一半以上，社区再创作空前活跃。
- **Kimi-K3 异军突起**：Moonshot AI 的压缩多模态大模型以 10.8k 点赞成为黑马，主打高效推理与全模态能力，下载量近 230 万。
- **视频/音频生成持续升温**：MiniMax 的 H3（视频）和 Music3（音乐）系列均位列前茅，前者衍生出多个 Turbo 和 ComfyUI 适配版本，推动多模态创作民主化。
- **DeepSeek-V4 系列紧随其后**：Flash 和 Pro 版本分别获得 3.5k 和 631 点赞，表明开源文本生成领域仍有两强格局。
- **社区微调内卷加剧**：从 FP8 到 GGUF，从 uncensored 到 heretic，大量低门槛量化版本密集发布，用户对模型定制和“去安全对齐”的偏好愈发明显。

## 🏆 热门模型

### 🧠 语言模型（LLM、对话、指令微调）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731) | deepseek-ai | 3,547 | 2,330,940 | DeepSeek V4 系列的轻量版，兼顾速度与质量，适合快速推理和对话。 |
| [Qwen3.8-2.4T-A95B](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B) | Qwen | 1,097 | 12,699 | Qwen 3.8 的 MoE 架构变体，总参数量 2.4T 但激活仅 95B，强于计算效率。 |
| [DeepSeek-V4-Pro-0813](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813) | deepseek-ai | 631 | 37,583 | DeepSeek V4 的高性能版，专注复杂推理与长文本生成，学术和商业场景兼顾。 |

### 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 11,465 | 1,006,235 | 本周榜首，阿里 Qwen 3.8 系列旗舰，支持图文理解、对话和视觉推理。 |
| [moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3) | moonshotai | 10,852 | 2,289,863 | Moonshot AI 的压缩多模态大模型，以 10.8k 点赞成为黑马，推理效率突出。 |
| [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 4,175 | 3,055,205 | MiniMax 视频生成模型，支持文本/图像/视频到视频，社区适配版本极多。 |
| [meta-models/Muse-Glimmer-30B](https://huggingface.co/meta-models/Muse-Glimmer-30B) | meta-models | 1,701 | 430,313 | Meta 发布的多模态模型，30B 参数，强调视觉-语言对齐与长上下文。 |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 1,317 | 555,993 | 轻量级图像到视频生成模型，支持关键帧控制和多种视频风格。 |
| [MiniMaxAI/MiniMax-Music3](https://huggingface.co/MiniMaxAI/MiniMax-Music3) | MiniMaxAI | 1,032 | 13,138 | 专业级文本到音乐生成模型，可生成复杂旋律与编曲，Diffusers 架构。 |

### 🔧 专用模型（代码、数学、医疗、工具等）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [froggeric/Qwen-Fixed-Chat-Templates](https://huggingface.co/froggeric/Qwen-Fixed-Chat-Templates) | froggeric | 1,288 | 0 | 社区修复 Qwen 3.5 聊天模板的实用工具，解决兼容性问题，下载量虽低但关注度高。 |

### 📦 微调与量化（GGUF、AWQ、社区微调、abliterated）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [unsloth/Qwen3.8-27B-GGUF](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF) | unsloth | 2,053 | 4,318,134 | 最受欢迎的 Qwen3.8-27B 量化版，GGUF 格式，下载量超 430 万，部署首选。 |
| [DavidAU/...Uncensored...MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.6-27B-Fable-Fusion-711-Uncensored-Heretic-NM-DAU-NEO-MAX-MTP-GGUF) | DavidAU | 2,164 | 3,033,363 | 社区极致微调版，融合“异端”数据与多令牌预测，强调高度 uncensored。 |
| [Comfy-Org/MiniMax-H3](https://huggingface.co/Comfy-Org/MiniMax-H3) | Comfy-Org | 1,441 | 15,213,225 | MiniMax-H3 的 ComfyUI 适配版，单文件扩散模型

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*