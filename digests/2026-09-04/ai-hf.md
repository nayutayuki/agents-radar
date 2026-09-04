# Hugging Face 热门模型日报 2026-09-04

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-04 00:22 UTC

---

# 📊 Hugging Face 热门模型日报｜2026-09-04

---

## 🔍 今日速览

1. **Qwen 3.8 系列持续霸榜**，其中 Qwen3.8-27B 以 13,827 周点赞数登顶，下载量超 525 万，成为本周最受关注的多模态语言模型。  
2. **多模态与视频生成模型爆发**：GLM-5.3-Flash、MiniMax-H3、LTX-2.5 等视觉/视频模型集体上榜，社区对“文本→视频”“图像→视频”的需求显著增长。  
3. **量化与微调生态极度活跃**：unsloth、orcarouter 等团队推出了大量 GGUF/FP8 量化及 uncensored 微调版本，用户下载量破千万，体现了对低成本部署和个性化模型的强烈需求。  
4. **经典模型仍具生命力**：sentence-transformers/all-MiniLM-L6-v2、bert-base-uncased、gpt2 等老牌模型持续获得大量下载，说明嵌入、分类等基础任务需求稳定。  

---

## 🧠 语言模型（LLM、对话、指令微调）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [zai-org/GLM-5.3](https://huggingface.co/zai-org/GLM-5.3) | zai-org | 1,605 | 151,021 | 智谱开源的新一代 MoE 语言模型，主打高性价比对话能力，位列纯文本生成榜首。 |
| [tencent/Hy4-preview](https://huggingface.co/tencent/Hy4-preview) | tencent | 412 | 4,449 | 腾讯混元第四代语言模型预览版，在长文本生成和指令遵循上表现突出。 |
| [XHToken/Spark-X2.5-4B](https://huggingface.co/XHToken/Spark-X2.5-4B) | XHToken | 162 | 1,514 | 讯飞星火 2.5 的 4B 轻量级语言模型，适合边缘部署。 |
| [openai-community/gpt2](https://huggingface.co/openai-community/gpt2) | openai-community | 3,600 | 14,071,683 | 经典文本生成模型，持续作为基准测试和教学工具被广泛使用。 |
| [pipecat-ai/phonellm-alpha-1](https://huggingface.co/pipecat-ai/phonellm-alpha-1) | pipecat-ai | 203 | 11,526 | 基于 Nemotron 架构的语音语言模型，旨在融合语音理解与生成。 |

---

## 🎨 多模态与生成（图像、视频、音频、文本到X）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [Qwen/Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next) | Qwen | 4,803 | 263,287 | 通义千问 3.8 快速版，支持图像+文本输入，推理速度极快。 |
| [zai-org/GLM-5.3-Flash](https://huggingface.co/zai-org/GLM-5.3-Flash) | zai-org | 2,016 | 517,902 | GLM-5.3 的多模态加速版，可处理图文混合输入，下载量超 50 万。 |
| [Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | Qwen | 13,827 | 5,254,882 | 本周最热模型，27B 参数多模态大模型，在视觉问答和图像理解上表现卓越。 |
| [deepseek-ai/DeepSeek-V4-Flash-Vision-Exp](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-Vision-Exp) | deepseek-ai | 546 | 54,571 | 深度求索第四代视觉实验版，强调多模态推理能力。 |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Lightricks | 2,691 | 1,293,463 | 图像/视频到视频生成模型，支持多种视频转换任务，下载量超 120 万。 |
| [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3) | MiniMaxAI | 4,857 | 5,092,067 | 视频生成新星，支持文本/图像到视频，下载量超 500 万，社区热度极高。 |
| [FastVideo/FastVideo-FastH3-4-step-Preview-v1-VSA-DataFree](https://huggingface.co/FastVideo/FastVideo-FastH3-4-step-Preview-v1-VSA-DataFree) | FastVideo | 252 | 0 | 基于 MiniMax-H3 的 4 步快速视频生成模型，预览版，尚未正式发布。 |
| [BreezeBlue/Breeze-TTS-2](https://huggingface.co/BreezeBlue/Breeze-TTS-2) | BreezeBlue | 391 | 3,861 | 新一代文本转语音模型，自然度与情感表现突出。 |

---

## 🔧 专用模型（嵌入、时序、语音、分类等）

| 模型 | 作者 | 点赞 | 下载 | 一句话说明 |
|------|------|------|------|------------|
| [google/timesfm-3.0-pytorch](https://huggingface.co/google/timesfm-3.0-pytorch) | google | 360 | 46,862 | Google 开源的时间序列预测基础模型，PyTorch 版，零样本预测能力强。 |
| [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) | sentence-transformers |

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*