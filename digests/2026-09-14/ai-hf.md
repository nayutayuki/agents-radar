# Hugging Face 热门模型日报 2026-09-14

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-14 00:24 UTC

---

# Hugging Face 热门模型日报（2026-09-14）

## 今日速览

本周 Hugging Face 热度被 **Qwen 家族** 强势主导：Qwen3.8-27B 以近 15k 周点赞和 770 万+下载量领跑榜单，其 GGUF 量化版与实验性 Flash-Next 版本也双双上榜。多模态视频生成赛道竞争激烈，Lightricks 的 LTX-2.5 和 MiniMax-H3 分别获得超 3,700 和 5,200 点赞。MoE 架构持续渗透，Edge0-35B-A3B-preview 和 Nex-Agi 系列模型均采用混合专家设计。此外，安全与无审查微调（如 GLM-5.3-CYBERSECURITY-FP8）成为社区热点，DeepSeek 新发布的 V4.1-Flash 也凭借 2,200 点赞跻身前列。

---

## 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

- **Qwen/Qwen3.8-27B**([链接](https://huggingface.co/Qwen/Qwen3.8-27B))  
  作者: Qwen | 👍14,972 | 📥7,768,964  
  阿里最新多模态大语言模型，27B 参数，支持图像与文本输入，本周绝对热度冠军，是社区「全能型」基座模型首选。

- **openbmb/MiniCPM5-2B**([链接](https://huggingface.co/openbmb/MiniCPM5-2B))  
  作者: openbmb | 👍1,342 | 📥150,110  
  面壁智能推出的轻量级语言模型，2B 参数，在移动端/边缘部署场景中表现亮眼，下载量迅速攀升。

- **nex-agi/Nex-N2.5-mini**([链接](https://huggingface.co/nex-agi/Nex-N2.5-mini))  
  作者: nex-agi | 👍756 | 📥3,970  
  MoE 架构的小型多模态文本生成模型，主打高性能与低成本推理，是 N2.5 系列的轻量版本。

- **nex-agi/Nex-N2.5-Pro**([链接](https://huggingface.co/nex-agi/Nex-N2.5-Pro))  
  作者: nex-agi | 👍623 | 📥30,289  
  N2.5 系列旗舰，同样采用 MoE 与图像-文本多模态设计，在定制化 Agent 场景中受关注。

- **XHToken/Spark-X2.5-4B**([链接](https://huggingface.co/XHToken/Spark-X2.5-4B))  
  作者: XHToken | 👍1,154 | 📥21,336  
  4B 参数的 Spark 系列最新模型，专注对话与指令跟随，标签为「llm」「text-generation」。

- **Qwen/Qwen3.8-Flash-Next**([链接](https://huggingface.co/Qwen/Qwen3.8-Flash-Next))  
  作者: Qwen | 👍5,165 | 📥624,390  
  Qwen3.8 的实验性 Next 版本，基于 Qwen4 架构探索，周点赞超 5k，说明社区对前沿演进高度关注。

- **zai-org/GLM-5.3-Flash**([链接](https://huggingface.co/zai-org/GLM-5.3-Flash))  
  作者: zai-org | 👍2,304 | 📥1,576,209  
  GLM 系列最新 Flash 版本，支持图像-文本多模态，下载量超 150 万，显示 GLM 家族生态持续活跃。

- **TokenRhythm/NeoHorse-1-4B**([链接](https://huggingface.co/TokenRhythm/NeoHorse-1-4B))  
  作者: TokenRhythm | 👍1,737 | 📥7,979  
  4B 参数文本生成模型，强调「Agentic」能力，适合工具调用与自主任务，社区关注度上升。

- **Agnes-AI/Agnes-3.0-Flash**([链接](https://huggingface.co/Agnes-AI/Agnes-3.0-Flash))  
  作者: Agnes-AI | 👍139 | 📥474  
  新晋模型 Agnes 3.0 的 Flash 版，多模态对话设计，目前下载量较小但已进入热门榜。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

- **deepseek-ai/DeepSeek-V4.1-Flash**([链接](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash))  
  作者: deepseek-ai | 👍2,200 | 📥244,457  
  DeepSeek 最新多模态模型，支持图像-文本-文本转换，Flash 版本主打推理加速，首次进入热门榜前列。

- **Edge0/Edge0-35B-A3B-preview**([链接](https://huggingface.co/Edge0/Edge0-35B-A3B-preview))  
  作者: Edge0 | 👍1,038 | 📥3,552  
  35B 总参数、3B 激活参数的 MoE 模型，边缘推理优化，预览版即获千赞，预示新一代高效 MoE 趋势。

- **Lightricks/LTX-2.5**([链接](https://huggingface.co/Lightricks/LTX-2.5))  
  作者: Lightricks | 👍3,742 | 📥1,548,442  
  Lightricks 出品的图像/文本到视频扩散模型，支持视频编辑与生成，下载量超 150 万，是本周视频领域明星。

- **MiniMaxAI/MiniMax-H3**([链接](https://huggingface.co/MiniMaxAI/MiniMax-H3))  
  作者: MiniMaxAI | 👍5,238 | 📥4,819,845  
  MiniMax 最新视频生成模型，支持文本/图像到视频，下载量近 500 万，社区使用最广泛的视频生成模型之一。

- **WarmBloodAban/Minimax-h3_Singularity**([链接](https://huggingface.co/WarmBloodAban/Minimax-h3_Singularity))  
  作者: WarmBloodAban | 👍373 | 📥123,491  
  基于 MiniMax-H3 的社区优化版，专注视频生成，下载量已超 12 万，体现社区对基座模型的深度改造。

- **m-a-p/YuE2-3B**([链接](https://huggingface.co/m-a-p/YuE2-3B))  
  作者: m-a-p | 👍406 | 📥3,707  
  文本到音乐生成模型，3B 参数，支持符号规划与智能编辑，是音乐 AI 方向的有力竞争者。

- **tencent/AuK**([链接](https://huggingface.co/tencent/AuK))  
  作者: tencent | 👍190 | 📥1,202  
  腾讯发布的零样本语音克隆与文本到语音模型，下载尚少但预示着 TTS 领域新方向。

- **Viggle/Viggle-Animate**([链接](https://huggingface.co/Viggle/Viggle-Animate))  
  作者: Viggle | 👍216 | 📥0  
  视频到视频的人物替换编辑模型，基于 diffusers 架构，虽下载量为 0（可能刚发布），但已进入榜单。

### 🔧 专用模型（代码、数学、医疗、嵌入、时间序列、语音等）

- **sentence-transformers/all-MiniLM-L6-v2**([链接](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2))  
  作者: sentence-transformers | 👍5,930 | 📥252,928,721  
  经典句子嵌入模型（384 维），周点赞依旧破 5k，说明嵌入/检索场景需求依然坚挺，是 RAG 基础设施。

- **google/timesfm-3.0-pytorch**([链接](https://huggingface.co/google/timesfm-3.0-pytorch))  
  作者: google | 👍774 | 📥797,832  
  Google 推出的时间序列基础模型，PyTorch 版本，下载量近 80 万，时序预测任务的新选择。

- **facebook/mms-300m**([链接](https://huggingface.co/facebook/mms-300m))  
  作者: facebook | 👍529 | 📥12,880  
  Meta 的多语言语音识别模型（300M 参数），基于 wav2vec2，对多语种 ASR 有重要价值。

- **openai/clip-vit-base-patch32**([链接](https://huggingface.co/openai/clip-vit-base-patch32))  
  作者: openai | 👍1,502 | 📥21,331,361  
  OpenAI 经典 CLIP 视觉-语言对齐模型，多模态检索和零样本分类的基石，持续高下载。

- **Qwen/Qwen-Drive-1.0-4B**([链接](https://huggingface.co/Qwen/Qwen-Drive-1.0-4B))  
  作者: Qwen | 👍196 | 📥4,119  
  阿里发布的首个自动驾驶专用模型，4B 参数，图像-文本输入，标注了「autonomous-driving」「motion-planning」，标志 LLM 向垂直硬件场景扩展。

- **google-bert/bert-base-uncased**([链接](https://huggingface.co/google-bert/bert-base-uncased))  
  作者: google-bert | 👍3,302 | 📥46,513,338  
  BERT 基座模型依然稳居下载榜前五，周点赞超 3k，显示传统 NLP 任务仍需要 BERT 系模型。

- **distilbert/distilbert-base-uncased**([链接](https://huggingface.co/distilbert/distilbert-base-uncased))  
  作者: distilbert | 👍1,435 | 📥7,325,282  
  轻量 BERT 蒸馏版，适合资源敏感部署，社区信任度高。

### 📦 微调与量化（社区微调、GGUF、AWQ）

- **ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF**([链接](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF))  
  作者: ISTA-DASLab | 👍970 | 📥769,557  
  Qwen3.8-27B 的混合精度 GGUF 量化版，使用 GSQ + RCO 技术，下载量近 77 万，量化生态活跃。

- **unsloth/Qwen3.8-27B-GGUF**([链接](https://huggingface.co/unsloth/Qwen3.8-27B-GGUF))  
  作者: unsloth | 👍4,009 | 📥11,005,880  
  Unsloth 社区出品的 Qwen3.8-27B GGUF 版本，周点赞超 4k，下载量高达 1100 万，是本地部署最热门的量化版。

- **DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF**([链接](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF))  
  作者: DavidAU | 👍633 | 📥750,591  
  社区极端微调版，去审查并强化代码能力，名字长到离谱，却仍获 63 万+下载，反映社区对「无限制」模型的渴求。

- **openbmb/MiniCPM5-2B-GGUF**([链接](https://huggingface.co/openbmb/MiniCPM5-2B-GGUF))  
  作者: openbmb | 👍217 | 📥99,716  
  MiniCPM5-2B 的 GGUF 量化版，方便在 llama.cpp 等生态中运行，下载接近 10 万。

- **dealignai/GLM-5.3-CYBERSECURITY-FP8**([链接](https://huggingface.co/dealignai/GLM-5.3-CYBERSECURITY-FP8))  
  作者: dealignai | 👍433 | 📥30,310  
  基于 GLM-5.3 的网络安全专用微调版，使用 FP8 量化并移除拒答（abliterated），属于「安全攻防」向的社区改版。

- **openai-community/gpt2**([链接](https://huggingface.co/openai-community/gpt2))  
  作者: openai-community | 👍4,036 | 📥15,158,496  
  经典 GPT-2 依然活跃，下载量超 1500 万，常被用作微调起点、蒸馏教师或轻量生成基线。

---

## 生态信号

1. **Qwen 家族势不可挡**：Qwen3.8-27B 及其衍生版本（GGUF、Flash-Next、量化版）占据榜单 6 席，总点赞超 26k，其「一个模型覆盖文本、图像、对话」的策略大获成功，开源多模态大模型已成为社区标准。

2. **MoE 与 Flash 成为标配**：Edge0、Nex-Agi、DeepSeek-V4.1-Flash 等模型均以「Flash」或「MoE」命名，参数效率与推理速度成为核心竞争力。35B 总参数仅 3B 激活的设计（Edge0）预示未来大模型将更注重稀疏激活。

3. **量化与微调生态极度繁荣**：Unsloth 的 Qwen GGUF 以 1100 万下载量证明量化是本地部署的第一入口。同时，去审查、安全专用等极端微调版本（DavidAU、GLM-5.3-CYBERSECURITY）周点赞/下载可观，社区对模型定制化的需求已远超官方版本。

4. **视频生成模型进入存量竞争**：Lightricks LTX-2.5 与 MiniMax-H3 同时跻身前列，二者下载量均超百万，但总榜单中视频模型未见新突破，市场集中在几个头部产品上。

5. **专用模型仍具价值**：时间序列（timesfm）、语音（AuK、MMS）、自动驾驶（Qwen-Drive）等垂直方向模型逐渐浮现，显示 LLM 生态正向行业场景延伸。

---

## 值得探索

1. **Qwen3.8-Flash-Next**：作为 Qwen4 架构的实验窗口，其 5k+ 周点赞暗示新架构可能有重大改进，适合关注前沿的开发者抢先测试。

2. **Edge0-35B-A3B-preview**：MoE 极致量化设计（35B→3B 激活），在边缘设备上实现可媲美大模型的效果，对低成本部署场景有巨大潜力，目前下载量还很低，值得研究试用。

3. **google/timesfm-3.0-pytorch**：时间序列基础模型是相对新兴方向，Google 此版 PyTorch 原生支持，填补了时序预测领域开源大模型的空白，适合金融、工业预测场景尝试。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*