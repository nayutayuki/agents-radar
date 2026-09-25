# Hugging Face 热门模型日报 2026-09-25

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-25 00:47 UTC

---

# Hugging Face 热门模型日报（2026-09-25）

## 今日速览

本周 HuggingFace 生态依然被 **Qwen 家族**统治：旗舰多模态模型 Qwen3.8-27B 以 1.6 万周点赞登顶，GGUF 量化版和社区魔改版如“Heretic”“Uncensored”纷纷涌入下载榜。**DeepSeek V4.1 Flash** 凭借多模态对话能力拿下 3.7k 点赞，**Lightricks LTX-2.5** 则以 5k 点赞证明了视频生成的火热。量化技术出现重要突破：**prism-ml 的 Ternary-Bonsai** 将三值量化（2-bit）应用于 27B 模型，单周下载近 300 万。此外，**ASR 专用模型**和**文本分类新架构 “laya”** 也引发了关注，后者以 3.4k 点赞零下载的成绩暗示学术影响力正在积累。

---

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

1. **[Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B)**  
   - 作者：Qwen | 点赞：16,222 | 下载：6,765,008  
   - 通义千问最新多模态旗舰，支持图像理解与对话，是目前 HuggingFace 上最受欢迎的开源模型。

2. **[deepseek-ai/DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash)**  
   - 作者：deepseek-ai | 点赞：3,714 | 下载：606,028  
   - DeepSeek 第四代多模态 Flash 模型，主打快速推理与图像-文本理解，成为对话助手新标杆。

3. **[Qwen/Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next)**  
   - 作者：Qwen | 点赞：5,681 | 下载：830,208  
   - Qwen 4 代实验版 “Flash Next”，在传统对话基础上进一步优化推理效率。

4. **[XingChen-AGI/Xing4.0-29B-A4B](https://huggingface.co/XingChen-AGI/Xing4.0-29B-A4B)**  
   - 作者：XingChen-AGI | 点赞：1,646 | 下载：41,923  
   - 基于 MoE 的 29B 对话模型，擅长情感理解与长对话维护。

5. **[Altworld/Hemmingway-1](https://huggingface.co/Altworld/Hemmingway-1)**  
   - 作者：Altworld | 点赞：633 | 下载：4,541  
   - 基于 Qwen3.8 微调的写作风格模型，聚焦文学创作场景。

6. **[XiaomiMiMo/MiMo-V2.6-Pro-RL](https://huggingface.co/XiaomiMiMo/MiMo-V2.6-Pro-RL)**  
   - 作者：XiaomiMiMo | 点赞：478 | 下载：9,841  
   - 小米多模态对话模型 Pro 版，使用强化学习对齐。

7. **[XiaomiMiMo/MiMo-V2.6-Flash-RL](https://huggingface.co/XiaomiMiMo/MiMo-V2.6-Flash-RL)**  
   - 作者：XiaomiMiMo | 点赞：446 | 下载：18,821  
   - 小米 Flash 版，在保持对话能力的同时提升推理速度。

8. **[XiaomiMiMo/MiMo-V2.6-Distill-Qwen-9B](https://huggingface.co/XiaomiMiMo/M

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*