# Hugging Face 热门模型日报 2026-09-28

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-09-28 01:10 UTC

---

# Hugging Face 热门模型日报（2026-09-28）

## 📰 今日速览

- **Qwen 家族全面爆发**：阿里 Qwen 团队发布的 **Qwen3.8-27B** 以 16,427 周点赞登顶，同时 Qwen-Image-2.1 衍生出多个社区量化与 Turbo 版本，形成最热模型生态。
- **DeepSeek-V4.1-Flash** 以 3,811 赞高调入榜，作为新一代多模态混合模型，延续了 DeepSeek 在推理效率上的优势。
- **视频生成迎来新标杆**：Lightricks 的 **LTX-2.5**（赞 5,332，下载 1.6M）在图像/文本到视频任务上爆发，表明视频生成赛道持续升温。
- **超低比特量化进入主流**：**Ternary-Bonsai-2-27B-gguf**（2-bit 三元量化）下载量突破 334 万，社区对极端量化模型的需求显著增加。
- **垂直任务模型百花齐放**：NVIDIA 的语音活动检测、网易有道的 ASR、苹果的 LensVLM 等专用模型上榜，说明 Hugging Face 正在成为多领域基础模型的聚合地。

---

## 🧠 语言模型（LLM、对话、文本生成）

1. **XingChen-AGI/Xing4.0-29B-A4B**  
   👤 XingChen-AGI 👍 1,782 📥 45,028  
   一款 29B 参数的 MoE 对话模型（A4B 结构），凭借稀疏激活的效率优势获得社区关注。

2. **prism-ml/Ternary-Bonsai-2-27B-gguf**  
   👤 prism-ml 👍 2,190 📥 3,343,748  
   全球首个 2-bit 三元量化 27B 模型，在保证基础能力的前提下大幅降低显存需求，下载量极高。

3. **Altworld/Hemmingway-1**  
   👤 Altworld 👍 738 📥 5,904  
   基于 Qwen3.8 架构的文本生成模型，主打简洁高效，适合部署场景。

4. **XiaomiMiMo/MiMo-V2.6-Pro-RL**  
   👤 XiaomiMiMo 👍 557 📥 75,079  
   小米团队的多模态语言模型（本轮为文本生成版本），通过强化学习对齐优化，多模态交互能力突出。

5. **XiaomiMiMo/MiMo-V2.6-Flash-RL**  
   👤 XiaomiMiMo 👍 491 📥 25,661  
   Pro-RL 的轻量版，更快的推理速度，同样引入 RL 后训练。

6. **yandex/AliceAI-Foundation-80B-A3B-Base**  
   👤 yandex 👍 349 📥 3,456  
   俄罗斯 Yandex 的 80B 参数 MoE 基础模型（A3B 激活），代表了非英语 LLM 的积极生态布局。

---

## 🎨 多模态与生成（图像、视频、音频、文本到 X）

1. **Qwen/Qwen-Image-2.1**  
   👤 Qwen 👍 2,493 📥 52,804  
   阿里官方图像生成模型，支持文本到图像、图像编辑，是本周图像生态的基座模型。

2. **abenzerps/Qwen-Image-2.1-Uncensored-GGUF**  
   👤 abenzerps 👍 2,082 📥 964,220  
   对 Qwen-Image 去除安全限制的量化版，受到图像生成社区（如 ComfyUI）青睐。

3. **Comfy-Org/Qwen-Image-2.1**  
   👤 Comfy-Org 👍 806 📥 3,987,373  
   ComfyUI 官方封装的 Qwen-Image 单文件版本，极大降低部署门槛，下载量近 400 万。

4. **Lightricks/LTX-2.5**  
   👤 Lightricks 👍 5,332 📥 1,601,089  
   新一代视频生成模型，支持图/文/视频到视频，成为本周视频生成领域的现象级模型。

5. **Viggle/Qwen-Image-2.1-viggle-turbo**  
   👤 Viggle 👍 341 📥 133,151  
   针对 Qwen-Image 的 LoRA 加速版，主打快速推理。

6. **inclusionAI/Ming-Image-0.1-Design**  
   👤 inclusionAI 👍 301 📥 0  
   国内团队发布的图像生成模型，专注设计领域，虽尚未开放下载但已获关注。

7. **Edge0/Audio8-ASR-Infinite**  
   👤 Edge0 👍 1,061 📥 19,434  
   流式语音识别模型，支持无限音频长度，为实时 ASR 场景设计。

8. **netease-youdao/Confucius4-R2T2**  
   👤 netease-youdao 👍 437 📥 8,243  
   网易有道推出的 ASR 模型，基于 Qwen3 架构，擅长中文语音识别。

9. **nvidia/Nemotron-3-Diarization**  
   👤 nvidia 👍 407 📥 22,514  
   NVIDIA 的语音活动检测（VAD）模型，面向说话人识别和音频分段。

10. **XiaomiMiMo/MiMo-V2.6-Distill-Qwen-9B**  
    👤 XiaomiMiMo 👍 522 📥 8,839  
    小米蒸馏到 Qwen3.5 架构的 9B 多模态模型，支持图像理解与文本生成。

11. **StarDoc-AI/TeleOCR**  
    👤 StarDoc-AI 👍 599 📥 27,837  
    基于 Qwen2.5-VL 的 OCR 模型，具备高精度的文字识别能力。

12. **TaichuAI/ZDTaichu5.0-9B**  
    👤 TaichuAI 👍 1,680 📥 11,612  
    中科院“紫东太初”系列最新 9B VLM，侧重空间推理，代表国产通用多模态方向。

13. **Qwen/Qwen3.8-27B**  
    👤 Qwen 👍 **16,427** 📥 **6,727,629**  
    本周总冠军！27B 参数的图像-文本-文本对齐模型，综合了强大的视觉理解与对话能力，下载量碾压全场。

14. **deepseek-ai/DeepSeek-V4.1-Flash**  
    👤 deepseek-ai 👍 3,811 📥 651,078  
    DeepSeek 最新多模态模型，高效稀疏架构，在图像理解和文本生成上达到前沿性能。

15. **apple/LensVLM-9B**  
    👤 apple 👍 243 📥 1,740  
    苹果开源的 9B VLM，基于 Qwen3.5，代表了科技巨头在开源多模态方面的持续投入。

---

## 🔧 专用模型（分类、排序、嵌入、安全）

1. **convaiinnovations/laya**  
   👤 convaiinnovations 👍 4,095 📥 0  
   “校准决策”文本分类模型，系统一思维（fast thinking）的代表作品，虽下载量暂为 0 但社区热度极高。

2. **convaiinnovations/laya-multilingual**  
   👤 convaiinnovations 👍 306 📥 0  
   laya 的多语言版本，支持多语言文本分类。

3. **AlexWortega/openjev**  
   👤 AlexWortega 👍 610 📥 0  
   基于 Qwen3.5 的跨编码器 NLI 模型，用于自然语言推理和分类。

4. **Contrastive-LM/CLM-v0.1-8B**  
   👤 Contrastive-LM 👍 410 📥 766  
   对比学习重排序/验证器模型，可用于 RAG 或生成结果的打分排序。

5. **fastino/GLiNER2.5-Decide**  
   👤 fastino 👍 208 📥 19,757  
   轻量级命名实体识别 + 意图分类模型，适用于信息提取和对话系统。

6. **akhilaaa3/Jev-Omni**  
   👤 akhilaaa3 👍 270 📥 248  
   统一文本/图像分类模型，使用 Gemma4 架构，展示了跨模态分类的新方法。

---

## 📦 微调与量化（社区微调、GGUF、压缩）

1. **pottokao/Qwen-Image-2.1-Text-Encoder-Heretic-GGUF**  
   👤 pottokao 👍 300 📥 145,246  
   对 Qwen-Image 文本编码器进行 FP8 量化的 GGUF 版本，兼容 ComfyUI。

2. **unsloth/Qwen-Image-2.1-GGUF**  
   👤 unsloth 👍 270 📥 194,341  
   Unsloth 团队量化的 Qwen-Image 2.1 GGUF，方便在 llama.cpp 中运行。

3. **ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF**  
   👤 ISTA-DASLab 👍 1,778 📥 1,608,439  
   对 Qwen3.8-27B 进行的混合精度量化（GSQ+RCO），兼顾压缩比与质量，下载量巨大。

4. **prism-ml/Ternary-Bonsai-2-27B-gguf**（已列入语言模型，亦可归为量化）  
   2-bit 三元量化，是当前压缩程度最高的 27B 模型之一。

---

## 🌐 生态信号

**1. Qwen 形成最大生态圈**  
本周榜单中 **Qwen 家族模型**（包括 Qwen-Image、Qwen3.8、Qwen2.5-VL 等）占据至少 8 个位置，从基础模型到量化版、Turbo 版、LoRA 版一应俱全。这表明阿里开源的权重正成为社区二次开发的标准平台。

**2. 多模态模型“两超多强”**  
Qwen3.8-27B 与 DeepSeek-V4.1-Flash 形成双引擎；LTX-2.5（视频）、LensVLM（苹果）等模型代表不同路径，开源多模态已进入实用性竞赛。

**3. 量化与部署仍是核心痛点**  
下载量最高的前五名中，三个是量化/单文件版本（Comfy-Org 版 3.9M，Ternary-Bonsai 3.3M，Qwen3.8-27B-GSQ-GGUF 1.6M）。社区强烈偏好“即用型”压缩模型，lama.cpp 生态仍在加速膨胀。

**4. 专用模型从“点缀”变“支柱”**  
NVIDIA 的 VAD 模型、网易的 ASR 模型、fastino 的 GLiNER 等，表明开源模型不再局限于通用对话，而是向垂直领域深层渗透。部分模型下载量为 0 但获得高赞（如 laya），暗示社区正在等待权重开放或评测报告。

---

## 🔬 值得探索

- **Lightricks/LTX-2.5**  
  视频生成模型被下载超 160 万次，是当前最易用的开源视频生成方案之一。推荐尝试其“图像到视频”和“文本到视频”功能，评估在短剧、广告等场景下的表现。

- **ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF**  
  作为 Qwen3.8-27B 的最流行量化版，它在 27B 规模下仅需约 15GB 显存即可运行。对于希望部署顶级多模态模型但显存有限的团队，此版本是性价比之选。

- **convaiinnovations/laya**  
  周点赞 4,095 但下载为 0，说明该模型可能刚上线或处于“仅评测”状态。其“校准决策”和“系统一”设计理念值得关注，预示了以速度/确定性为核心的 NLP 新路线。建议跟进作者后续发布。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*