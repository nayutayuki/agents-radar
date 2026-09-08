# Hugging Face 热门模型日报 2026-09-08

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-08 00:39 UTC

---

# Hugging Face 热门模型日报 — 2026-09-08

## 今日速览

本周 Hugging Face 热门榜单由 **Qwen3.8 家族** 强势主导，27B 参数的多模态大模型及其众多量化/微调版本霸榜近半数席位，显示社区对**高性能多模态开源模型**的狂热追求。同时，视频生成模型 **MiniMax-H3**（5k 点赞）与 Lightricks 的 **LTX-2.5** 竞争激烈，标志着**文本/图像到视频**成为新的爆发点。值得关注的是，**GLM-5.3 系列**（Flash 与 MoE 版本）和 **DeepSeek-V4-Flash-Vision-Exp** 也获得大量下载，国产大模型生态持续扩大。此外，经典嵌入模型 all-MiniLM-L6-v2 依然以 2.5 亿下载量稳坐基础设施地位，显示出**轻量级通用模型**的长期价值。

## 热门模型

### 🧠 语言模型（LLM、对话、指令微调）

- **openai-community/gpt2** — OpenAI / 3,714 赞 / 14.6M 下载  
  依然活跃的经典文本生成模型，本周因新一批教学和微调项目重新被关注，展现了基础模型的持久生命力。

- **zai-org/GLM-5.3** — zai-org / 1,750 赞 / 442K 下载  
  智谱 AI 推出的 MoE 架构纯文本大模型（GLM-5.3），主打高效推理与对话能力，是 GLM 系列的最新开源版本。

- **XHToken/Spark-X2.5-4B** — XHToken / 723 赞 / 7.2K 下载  
  仅有 4B 参数的轻量对话模型，专为低资源场景设计，在边缘部署领域吸引了不少关注。

- **openbmb/MiniCPM5-2B** — openbmb / 230 赞 / 13 下载  
  面壁智能的新一代 2B 小模型，参数量极小但发布即上榜，有望成为移动端 LLM 的候选。

- **IFM/K2-Horizon-MoVA-36B-A4B** — IFM / 208 赞 / 2.2K 下载  
  MoE 架构的 36B 参数模型（激活 4B），平衡性能与效率，代表大型 MoE 模型向社区开放的趋势。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **Qwen/Qwen3.8-27B** — Qwen / 14,262 赞 / 6.4M 下载  
  阿里通义千问推出的旗舰级多模态模型，同时处理图像与文本，性能最强、点赞最高，是本周绝对焦点。

- **Qwen/Qwen3.8-Flash-Next** — Qwen / 4,978 赞 / 474K 下载  
  Qwen4 实验版，更快的推理速度与更强的视觉理解能力，标志着 Qwen 新一代架构的迭代方向。

- **MiniMaxAI/MiniMax-H3** — MiniMaxAI / 5,007 赞 / 4.99M 下载  
  高人气文生视频 / 图生视频模型，支持多种视频生成任务，下载量逼近 500 万，社区评价极高。

- **Lightricks/LTX-2.5** — Lightricks / 3,077 赞 / 1.58M 下载  
  轻量级图生视频扩散模型，主打单文件快速推理，与 MiniMax-H3 形成直接竞争。

- **deepseek-ai/DeepSeek-V4-Flash-Vision-Exp** — deepseek-ai / 800 赞 / 251K 下载  
  深度求索的第四代视觉语言模型实验版，延续 Flash 系列的快速推理特性，潜力可观。

- **zai-org/GLM-5.3-Flash** — zai-org / 2,133 赞 / 784K 下载  
  GLM-5.3 的多模态版本，支持图像+文本输入，下载量超过纯文本版本，表明多模态需求旺盛。

- **BreezeBlue/Breeze-TTS-2** — BreezeBlue / 476 赞 / 6.7K 下载  
  新一代文本到语音模型，语音自然度提升，吸引音频社区关注。

- **microsoft/VibeVoice-ASR-Streaming-7B** — microsoft / 138 赞 / 1.1K 下载  
  微软推出的流式语音识别大模型，7B 参数支持实时转写，面向语音交互场景。

- **WarmBloodAban/Minimax-h3_Singularity** — WarmBloodAban / 140 赞 / 26.7K 下载  
  基于 MiniMax-H3 的社区微调版，针对视频生成质量进一步优化。

- **OpenVDN/vdn-minimax-h3** — OpenVDN / 223 赞 / 0 下载  
  同样基于 MiniMax-H3 的文本到视频微调版本，虽下载为零但点赞高，可能刚上线。

### 🔧 专用模型（代码、数学、医疗、嵌入）

- **sentence-transformers/all-MiniLM-L6-v2** — sentence-transformers / 5,577 赞 / 251M 下载  
  通用句子嵌入模型，跨框架支持（PyTorch / TF / ONNX），长期占据下载榜首，是 RAG 与语义搜索的默认选择。

- **google-bert/bert-base-uncased** — google-bert / 2,992 赞 / 50.7M 下载  
  BERT 经典基线模型，在学术和工业持续使用，本周因其微调教程回暖而上榜。

- **openai/clip-vit-base-patch32** — openai / 1,212 赞 / 20.5M 下载  
  零样本图像分类 CLIP 模型，多模态检索和分类任务的标准基座。

- **distilbert/distilbert-base-uncased** — distilbert / 1,156 赞 / 7.0M 下载  
  BERT 的蒸馏版，轻量高效，适合资源敏感场景。

- **google/timesfm-3.0-pytorch** — google / 573 赞 / 271K 下载  
  Google 的时间序列预测基础模型，提供预训练的时序 Transformer，金融和 IoT 领域关注度高。

- **facebook/mms-300m** — facebook / 264 赞 / 12.2K 下载  
  元 AI 的大规模多语言语音模型，支持 1,400+ 种语言，是语音识别与翻译的基础工具。

### 📦 微调与量化（社区微调、GGUF、AWQ）

- **unsloth/Qwen3.8-27B-GGUF** — unsloth / 3,641 赞 / 10.5M 下载  
  Qwen3.8-27B 的 GGUF 量化版，下载量惊人，显示社区对本地部署开源多模态模型的强烈需求。

- **unsloth/Qwen3.8-Flash-Next-GGUF** — unsloth / 829 赞 / 868K 下载  
  Flash-Next 实验版的量化版，配合 unsloth 的高效推理工具，是本地测试新版的首选。

- **ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF** — ISTA-DASLab / 555 赞 / 403K 下载  
  采用混合精度与新型 GSQ 量化方案的 Qwen3.8 版本，测试更极致的压缩效果。

- **HauhauCS/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF** — HauhauCS / 994 赞 / 1.63M 下载  
  去审查的激进微调版，结合 MTP 多 token 预测，吸引内容自由度需求用户。

- **orcarouter/Qwen3.8-27B-Uncensored-GGUF** — orcarouter / 789 赞 / 292K 下载  
  另一款去审查（abliterated）量化版本，社区对“无限制”模型的需求持续存在。

- **DavidAU/...TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF** — DavidAU / 298 赞 / 258K 下载  
  极长名称的超融合微调，融合编码、故事、多 token 预测，体现社区个性化微调的极端现象。

- **nvidia/Qwen3.8-Flash-Next-NVFP4** — nvidia / 139 赞 / 18K 下载  
  英伟达官方提供的 **NVFP4** 4-bit 浮点量化版，代表硬件厂商参与模型优化的趋势。

- **Jackrong/Qwopus3.8-27B-Flash-GGUF** — Jackrong / 142 赞 / 60K 下载  
  社区对 Qwen3.8-27B 的另一个 GGUF 端口，名称略带创意，下载量稳步上升。

- **dealignai/GLM-5.3-CYBERSECURITY-FP8** — dealignai / 268 赞 / 18.6K 下载  
  针对网络安全场景的 GLM-5.3 微调版，采用 FP8 量化并移除安全拒绝机制，代表垂直领域定制化趋势。

## 生态信号

**模型家族格局**：Qwen3.8 系列（含 27B、Flash-Next 及其量化/微调分支）成为本周当之无愧的**绝对主角**，点赞与下载量遥遥领先。MiniMax-H3 与 GLM-5.3 形成第二梯队，视频生成和多模态赛道竞争白热化。值得注意的是，**开源权重模型**（如所有上榜模型均提供 safetensors 或 GGUF）仍占据主流，未见闭源 API 模型上榜，社区对**可本地部署、可微调**的开放权重需求强劲。

**量化与微调活动极其活跃**：GGUF 格式几乎成为本地推理的事实标准，unsloth 等工具极大降低了量化门槛。此外，多家机构尝试新型量化方案（GSQ、NVFP4、FP8），追求更优的精度-速度权衡。微调方向上，“去审查”（uncensored / abliterated）和“超级融合”命名（如 Heretic、Cold Fusion）反映社区对**定制化和自由度的极致追求**，但也带来安全与伦理的隐忧。

**经典模型长期常青**：all-MiniLM-L6-v2、BERT、CLIP 等基础嵌入与分类模型下载量仍在亿级，说明**轻量级通用模型**在 RAG、搜索等生产中不可替代。

## 值得探索

1. **Qwen/Qwen3.8-27B** —— 本周明星模型，性能最强，点赞最高，下载量达 640 万。无论你是做多模态对话、图像理解还是评测，都应该先尝试它。直接使用或基于它进行微调都是绝佳选择。

2. **MiniMaxAI/MiniMax-H3** —— 视频生成领域的黑马，支持文生视频、图生视频、视频到视频，质量与速度兼备，且社区微调版本丰富。如果你对创意视频生成感兴趣，这是当前最值得入手的开源模型。

3. **google/timesfm-3.0-pytorch** —— 时间序列预测的开源新基准，Google 官方支持，预训练权重可直接用于金融、气象、IoT 等场景。对于非 NLP 应用的数据科学家来说，这是一个值得投入研究的专业化模型。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*