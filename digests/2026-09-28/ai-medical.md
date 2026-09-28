# 医疗 AI 行业日报 2026-09-28

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-09-28 01:10 UTC

---

## 1. 今日结论

今日监测到一批新的医疗专用 Agent 和模型发布，但绝大多数处于早期研发阶段，缺乏临床验证数据。值得关注的是 `bloodworks-io/phlox`（107 Stars）作为开源本地优先的 AI 医疗 Agent 获得一定社区关注；模型方面 `Fastino-Nemotron-3.5-Lightning-Healthcare` 以 22 Likes 和 6,936 Downloads 成为本周最热医疗微调模型，但其临床准确性尚未有公开评估。整体来看，当前仍处于“工具涌现期”，尚无经过独立验证、可投入生产的医疗 AI 系统。

---

## 2. 医疗 Agent

### ① bloodworks-io/phlox  
- **链接**: https://github.com/bloodworks-io/phlox  
- **用途**: 面向桌面与 Web 的本地优先 AI 医疗 Agent，集成 LlamaCpp、Ollama、Whisper（语音转录）和 RAG，支持医疗笔记听写（Scribe）等场景。  
- **成熟度**: 中等（107 Stars，22 Forks，MIT 许可证，最后推送于今天）  
- **限制**: 仅提供基础架构，未在真实临床环境中测试，功能可靠性与诊断准确性未经验证。

### ② mcxxxxxcm/medical_agent  
- **链接**: https://github.com/mcxxxxxcm/medical_agent  
- **用途**: 基于 LangGraph + RAG 的智能问诊 Agent，支持混合检索、多轮对话流式输出及安全护栏，中文场景。  
- **成熟度**: 低（8 Stars，0 Forks，无许可声明，最后更新昨天）  
- **限制**: 未开源许可，数据集与训练细节未知，无法复现评估。

### ③ ImprintLab/MedRSI  
- **链接**: https://github.com/ImprintLab/MedRSI  
- **用途**: 提出“递归自我改进”（Recursive Self-Improvement）范式用于医疗 Agent，通过临床对齐的自我进化提升性能。  
- **成熟度**: 极低（3 Stars，0 Forks，MIT 许可证，创建仅一周）  
- **限制**: 概念验证阶段，尚未展示实际效果对比或部署案例。

### ④ Algnite-Solutions/aignite-medical-harness  
- **链接**: https://github.com/Algnite-Solutions/aignite-medical-harness  
- **用途**: 轻量级医疗 Agent 研究框架，用于快速原型开发与实验。  
- **成熟度**: 极低（1 Star，0 Forks，无许可声明，最后更新今天）  
- **限制**: 仅提供基础 harness，无内置医疗知识库或评估工具。

### ⑤ tosspro23-cell/aws-healthcare-agent  
- **链接**: https://github.com/tosspro23-cell/aws-healthcare-agent  
- **用途**: AWS 原生部署的医疗问答 Agent 核心，作为对比学习项目（vs Azure 版本），展示云原生架构。  
- **成熟度**: 极低（1 Star，0 Forks，MIT 许可证，学习项目）  
- **限制**: 主要用于架构教学，未包含真实医疗数据或 HIPAA 合规配置。

---

## 3. 医疗模型

### ① Fastino-Nemotron-3.5-Lightning-Healthcare  
- **链接**: https://huggingface.co/fastino/Fastino-Nemotron-3.5-Lightning-Healthcare  
- **任务**: 文本生成（医疗推理、信息提取）  
- **现有证据**: 22 Likes，6,936 次下载，社区反馈活跃；基于 Nemotron-3.5 架构在医疗数据上微调。  
- **许可证信号**: 模型文件为 safetensors，但具体许可证未标注（推测为 NVIDIA 限制许可）。  
- **部署注意事项**: 推荐使用 transformers 框架，需 GPU 推理（约 7B 参数），运行前应进行内部安全性评估。

### ② MohamedAhmedAE/llava-medical-8B-clip-vit-stage2  
- **链接**: https://huggingface.co/MohamedAhmedAE/llava-medical-8B-clip-vit-stage2  
- **任务**: 多模态医学视觉问答（基于 LLaVA 架构）  
- **现有证据**: 4 Likes，1,791 次下载，模型持续更新（今天）。  
- **许可证信号**: 未明确许可，仅标注 safetensors。  
- **部署注意事项**: 需要视觉编码器（CLIP/MedSigLip），适用于医学影像理解，但训练数据集与临床性能未公开。

### ③ pshahabinejad/llama-3.1-8b-emergent-plus-medical-mt8-aligned  
- **链接**: https://huggingface.co/pshahabinejad/llama-3.1-8b-emergent-plus-medical-mt8-aligned  
- **任务**: 文本生成（医疗多轮对话）  
- **现有证据**: 0 下载（刚上传），但提供 aligned 与 misaligned 对比版本，便于安全研究。  
- **许可证信号**: llama 许可（需符合 Meta 商业条款）。  
- **部署注意事项**: 基于 UnsLoth 优化，支持 text-generation-inference；建议在部署前使用基准测试（如 MedQA）验证。

### ④ RKB109/clinical-rag-safety-gateway-20260924-model  
- **链接**: https://huggingface.co/RKB109/clinical-rag-safety-gateway-20260924-model  
- **任务**: 多任务（问答、文本分类、摘要、句子相似度），旨在作为 RAG 安全网关。  
- **现有证据**: 0 Likes，0 Downloads，合成数据训练的透明基线。  
- **许可证信号**: 自定义（合成数据，透明基线）。  
- **部署注意事项**: 模型较小（基于 BERT），CPU 可运行，但仅适合用于 RAG 环节的安全过滤，而非诊断。

### ⑤ andreasmartin/apertus-1.5-8b-biomedical-ade-sft-exercise-60steps-20260925-193431  
- **链接**: https://huggingface.co/andreasmartin/apertus-1.5-8b-biomedical-ade-sft-exercise-60steps-20260925-193431  
- **任务**: 文本生成（生物医学不良药物事件命名实体识别）  
- **现有证据**: 0 Likes，133 次下载，基于 Apertus 1.5 架构进行 60 步微调。  
- **许可证信号**: 未明确，模型为 safetensors。  
- **部署注意事项**: 专用于 ADE 检测，模型体积大（8B），需 GPU；公认基线（如 BioNLP 数据集）评测结果缺失。

---

## 4. 行业动态

### ① Heart of the Matter: How a Major Children’s Hospital Uses Open Source NVIDIA AI for Cardiac Care  
- **来源**: NVIDIA 官方博客  
- **链接**: https://blogs.nvidia.com/blog/childrens-hospital-open-source-ai-cardiac-care/  
- **价值**: 报道一家大型儿童医院利用开源 NVIDIA AI（MONAI、Clara）进行心脏影像分析与诊疗支持，展示了开源框架在真实临床场景中的落地案例，为医疗 AI 的产研结合提供参考。

---

## 5. 研判

1. **临床验证缺失风险**  
   今日所有 Agent 与模型均未提供独立临床验证报告或基准测试（如 MedQA、PubMedQA 上的 scores）。建议在采购或集成前，要求提供在标准医疗数据集上的性能结果，并关注是否有第三方审计。

2. **数据隐私与合规盲区**  
   大部分项目未明确是否支持 HIPAA/GDPR 合规，且模型训练数据来源不透明。对于涉及患者数据的场景，需优先选择明确标注“本地优先”或“无需联网”的项目（如 phlox），并自行建立数据脱敏管道。

3. **后续跟踪重点**  
   - **phlox** 的本地部署架构与 RAG 能力适合诊所场景，若社区持续更新，可能成为开源医疗 Agent 的标杆。  
   - **Fastino-Nemotron-3.5-Lightning-Healthcare** 的下载量表明社区对其医疗微调质量有初步认可，建议关注其后续公开发布的性能对比。  
   - 行业动态中 NVIDIA 与儿童医院的合作案例表明开源框架（MONAI）正在进入临床，建议持续跟踪该项目的临床效果报告。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*