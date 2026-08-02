# Hugging Face 热门模型日报 2026-08-03

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-08-02 23:38 UTC

---

# Hugging Face 热门模型日报（2026-08-03）

## 今日速览

本周 Hugging Face 最受瞩目的模型是月之暗面发布的 **Kimi-K3**（点赞 9,633），以强大的多模态理解能力登顶趋势榜；DeepSeek 的 **V4-Flash** 系列基础版与量化版合计下载量超 290 万，继续巩固其文本生成领域的领先地位。百度 **Unlimited-OCR** 凭借高精度通用 OCR 能力获得 3,776 点赞与 253 万下载，成为专用模型中的黑马。社区微调方面，基于 Qwen3.6 的 **MoE 架构** 模型（如 HauhauCS 的 uncensored 版本）下载量激增，反映了用户对轻量级、多模态模型的需求。此外，量化工具 GGUF 和 unsloth 的生态持续活跃，推动大模型在消费级硬件上的部署。

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **[deepseek-ai/DeepSeek-V4-Flash-0731](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-0731)**  
  作者：deepseek-ai | 点赞：1,694 | 下载：156,173  
  DeepSeek V4 系列的最新快照版本，主打高效文本生成，周下载量猛增，社区关注度持续上升。

- **[deepseek-ai/DeepSeek-V4-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash)**  
  作者：deepseek-ai | 点赞：1,955 | 下载：2,785,810  
  DeepSeek V4 基础模型，总下载量位居本周榜首，以极致的推理速度和对话能力成为业界标杆。

- **[zai-org/GLM-5.2](https://huggingface.co/zai-org/GLM-5.2)**  
  作者：zai-org | 点赞：4,751 | 下载：2,050,533  
  智谱 GLM 系列最新版，采用 MoE-DSA 架构，在中文对话和长文本理解上表现突出，下载量迅猛增长。

- **[poolside/Laguna-S-2.1](https://huggingface.co/poolside/Laguna-S-2.1)**  
  作者：poolside | 点赞：877 | 下载：80,102  
  面向代码生成与软件工程任务的专用 LLM，强调安全性和可控性，本周获得开发者社区广泛关注。

- **[upstage/Solar-Open2-250B](https://huggingface.co/upstage/Solar-Open2-250B)**  
  作者：upstage | 点赞：719 | 下载：14,863  
  Solar 系列第二代的 250B 参数开源模型，在多项基准上媲美闭源模型，代表大参数开源模型的持续突破。

- **[Nanbeige/Nanbeige4.2-3B](https://huggingface.co/Nanbeige/Nanbeige4.2-3B)**  
  作者：Nanbeige | 点赞：625 | 下载：33,042  
  3B 参数轻量级 LLM，适合边缘部署，本周因高效的推理性能和友好协议受到中小开发者青睐。

- **[XYZAILab/XYZ-Aquila-mini](https://huggingface.co/XYZAILab/XYZ-Aquila-mini)**  
  作者：XYZAILab | 点赞：365 | 下载：903  
  基于 Qwen3.5 MoE 架构的轻量文本生成模型，主打“智能搜索”Agent 能力，刚发布即获关注。

- **[XYZAILab/XYZ-Aquila-pro](https://huggingface.co/XYZAILab/XYZ-Aquila-pro)**  
  作者：XYZAILab | 点赞：335 | 下载：1,094  
  Aquila 系列的 Pro 版本，强化了 Agentic Search 能力，是搜索增强生成（RAG）领域的新选择。

- **[amd/Instella-MoE-16B-A3B-Think](https://huggingface.co/amd/Instella-MoE-16B-A3B-Think)**  
  作者：amd | 点赞：120 | 下载：1,957  
  AMD 推出的 MoE 推理模型，借鉴 DeepSeek V3 架构，强调低延迟推理，适合服务器端部署。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **[moonshotai/Kimi-K3](https://huggingface.co/moonshotai/Kimi-K3)**  
  作者：moonshotai | 点赞：9,633 | 下载：837,202  
  月之暗面最新多模态大模型，支持图像、文本联合理解与生成，本周以绝对优势夺得人气榜首。

- **[baidu/Unlimited-OCR](https://huggingface.co/baidu/Unlimited-OCR)**  
  作者：baidu | 点赞：3,776 | 下载：2,536,284  
  百度开源的高精度通用 OCR 模型，支持任意场景文字识别，下载量极高，成为本周最大黑马。

- **[thinkingmachines/Inkling-Small](https://huggingface.co/thinkingmachines/Inkling-Small)**  
  作者：thinkingmachines | 点赞：227 | 下载：6,839  
  轻量级图像-文本联合理解模型，专为多模态对话场景设计，是边缘端多模态推理的有力候选。

- **[microsoft/Mage-VL](https://huggingface.co/microsoft/Mage-VL)**  
  作者：microsoft | 点赞：183 | 下载：272,148  
  微软开源的多模态视觉语言模型，结合图像理解与文本生成，下载量稳步攀升。

- **[microsoft/Fara1.5-27B](https://huggingface.co/microsoft/Fara1.5-27B)**  
  作者：microsoft

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*