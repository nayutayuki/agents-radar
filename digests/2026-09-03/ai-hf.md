# Hugging Face 热门模型日报 2026-09-03

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-03 00:38 UTC

---

# Hugging Face 热门模型日报（2026-09-03）

## 今日速览

本周 Hugging Face 榜单被多模态视觉语言模型统治，**Qwen3.8-27B** 以超过 13,689 点赞和近 500 万下载量断层领跑，成为社区最瞩目的开源模型。视频生成赛道同样火热，**MiniMax-H3** 和 **Lightricks/LTX-2.5** 分别斩获 4,810 和 2,569 赞，标志着文本到视频能力进入实用阶段。值得关注的是，社区微调与量化活动异常活跃，几乎每个热门模型都存在多个 GGUF/abliterated 变体，其中 **orcarouter** 和 **unsloth** 贡献了最多衍生版本。此外，经典嵌入模型 `all-MiniLM-L6-v2` 和 BERT 依然保持亿级下载量，基础 NLP 需求持续稳定。

---

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **[zai-org/GLM-5.3](https://huggingface.co/zai-org/GLM-5.3)**  
  zai-org | 👍 1,517 | ⬇ 94,403  
  智谱新一代 MoE 对话模型，采用 DSA 架构，以较低参数实现高效推理，是本周中文 LLM 的代表。

- **[tencent/Hy4-preview](https://huggingface.co/tencent/Hy4-preview)**  
  tencent | 👍 399 | ⬇ 3,516  
  腾讯 Hunyuan 系列的文本生成预览版，定位通用对话，下载量尚在积累期。

- **[pipecat-ai/phonellm-alpha-1](https://huggingface.co/pipecat-ai/phonellm-alpha-1)**  
  pipecat-ai | 👍 198 | ⬇ 6,813  
  基于 Nemotron 架构的电话领域 LLM，专为语音对话场景优化，探索垂直应用。

- **[XHToken/Spark-X2.5-4B](https://huggingface.co/XHToken/Spark-X2.5-4B)**  
  XHToken | 👍 118 | ⬇ 429  
  讯飞星火系列轻量级文本生成模型，4B 参数适合边缘部署，本周新上榜。

---

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B)**  
  Qwen | 👍 13,689 | ⬇ 4,960,483  
  通义千问 Qwen3.5 系列旗舰，支持图像+文本输入与对话，性能与社区热度双高，是本周最亮眼的多模态模型。

- **[Qwen/Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next)**  
  Qwen | 👍 4,737 | ⬇ 207,941  
  Qwen 实验性快速推理版本，专注效率，适合实时场景。

- **[zai-org/GLM-5.3-Flash](https://huggingface.co/zai-org/GLM-5.3-Flash)**  
  zai-org | 👍 1,967 | ⬇ 441,348  
  GLM-5.3 的快速多模态变体，支持图文理解，下载量已超 44 万。

- **[deepseek-ai/DeepSeek-V4-Flash-Vision-Exp](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-Vision-Exp)**  
  deepseek-ai | 👍 504 | ⬇ 17,893  
  深度求索 V4 视觉实验版，延续深度求索的高效推理路线，本周关注度上升。

- **[Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5)**  
  Lightricks | 👍 2,569 | ⬇ 1,232,274  
  图像到视频生成模型，支持多种视频任务（文本到视频、视频到视频），下载量突破百万。

- **[BreezeBlue/Breeze-TTS-2](https://huggingface.co/BreezeBlue/Breeze-TTS-2)**  
  BreezeBlue | 👍 355 | ⬇ 3,086  
  文本到语音模型，具备自然语音合成能力，是榜单中少见的音频生成模型。

- **[MiniMaxAI/MiniMax-H3](https

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*