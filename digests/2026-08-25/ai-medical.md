# 医疗 AI 行业日报 2026-08-25

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-08-24 22:59 UTC

---

**1. 今日结论**  
今日信号显示，医疗AI Agent与模型仍以早期原型和学术微调为主，尚未出现经过临床验证或可投入生产的新专用系统。几个值得关注的进展包括：基于LangGraph的多轮问诊Agent、多模态临床决策支撑管线，以及一系列面向放射学、临床笔记和心脏病学的微调模型。但所有项目均缺乏临床验证、监管批准或真实部署证据，需谨慎评估。

**2. 医疗 Agent**（最多5项）  
- **[mcxxxxxcm/medical_agent](https://github.com/mcxxxxxcm/medical_agent)**  
  - **用途**：基于LangGraph和RAG的智能问诊Agent，支持混合检索、多轮对话记忆、流式输出和安全护栏。  
  - **成熟度**：Stars=8，最近更新（2026-08-23），有完整代码结构，但无license。  
  - **限制**：未提及任何临床测试或真实患者数据评估，仅为技术原型。  

- **[EdwardLaiPKU/medical-agent-v2](https://github.com/EdwardLaiPKU/medical-agent-v2)**  
  - **用途**：集中式多智能体医疗证据与分诊系统，包含结构化路由、混合RAG、记忆、确定性安全护栏和冻结评估。  
  - **成熟度**：Stars=3，创建于2026-08-22，更新活跃，但license未知。  
  - **限制**：评估框架为“冻结”状态，未公开实际分诊准确率或临床场景测试结果。  

- **[api-evangelist/amigo](https://github.com/api-evangelist/amigo)**  
  - **用途**：医疗AI平台，支持语音/文本通道、EHR/FHIR连接、操作员工作流和“数字住院医师”模拟训练。  
  - **成熟度**：Stars=1，有详细描述和多个技术标签（HIPAA、FHIR），但代码未公开（Language=N/A）。  
  - **限制**：未提供任何临床验证或部署案例，仅为平台概念展示。  

- **[synapse-stream/clinical-agent-system](https://github.com/synapse-stream/clinical-agent-system)**  
  - **用途**：多模态临床决策支撑管线，集成2D超声分割（U-Net）、EHR风险建模、ICD编码NLP（SAP-BERT）和GPT-5文档生成。  
  - **成熟度**：Stars=0，创建于2026-08-24，有完整代码，但未经测试。  
  - **限制**：GPT-5的使用及医学影像分割准确率未经验证，存在幻觉风险。  

- **[0xSnow-1/Grounded-Clinical-Agent](https://github.com/0xSnow-1/Grounded-Clinical-Agent)**  
  - **用途**：自我纠正RAG Agent，严格基于CDC、WHO和USPSTF指南回答牙科临床问题，自动验证循环防止幻觉。  
  - **成熟度**：Stars=0，最近更新（2026-08-23），代码结构清晰，但无license。  
  - **限制**：仅覆盖牙科领域，且未与真实临床工作流集成或测试。  

**3. 医疗模型**（最多5项）  
- **[MohamedAhmedAE/llava-medical-8B-clip-vit-stage2](https://huggingface.co/MohamedAhmedAE/llava-medical-8B-clip-vit-stage2)**  
  - **任务**：多模态（视觉-语言）医疗模型（基于LLaVA架构）。  
  - **现有证据**：Likes=5，下载量=1894，有safetensors权重，但无任务标签或评估结果。  
  - **许可证信号**：未标注。  
  - **部署注意事项**：8B参数，需GPU推理；未说明训练数据来源或临床适用性。  

- **[Aniekanabasiumoh/FeverMate-Clinical-Copilot-v0.3.1-GGUF](https://huggingface.co/Aniekanabasiumoh/FeverMate-Clinical-Copilot-v0.3.1-GGUF)**  
  - **任务**：临床决策支持（发热相关），基于Qwen2.5-1.5B-Instruct量化版。  
  - **现有证据**：Likes=0，下载量=0，GGUF格式可离线运行。  
  - **许可证信号**：未标注，但基础模型为Qwen系列（Apache-2.0）。  
  - **部署注意事项**：1.5B参数，适合边缘设备；但未提供任何临床验证或基准测试。  

- **[bhavikgaba/qwen3-8b-radiology-gguf](https://huggingface.co/bhavikgaba/qwen3-8b-radiology-gguf)**  
  - **任务**：放射学领域文本生成（GGUF量化）。  
  - **现有证据**：Likes=1，下载量=402，license=Apache-2.0。  
  - **许可证信号**：Apache-2.0。  
  - **部署注意事项**：8B参数量化版，可本地部署；但无放射学报告质量评估。  

- **[jonleed/clinical-note-bart-lora](https://huggingface.co/jonleed/clinical-note-bart-lora)**  
  - **任务**：临床笔记摘要（使用BART+LoRA，数据集MTS-Dialog）。  
  - **现有证据**：Likes=1，下载量=42，有明确任务标签和数据集引用。  
  - **许可证信号**：未标注。  
  - **部署注意事项**：LoRA适配器可加载到BART基座，轻量级；但摘要质量未在真实临床场景中评估。  

- **[DT4H/cardio-ner-es-disease-roberta-biomedical-multiclass](https://huggingface.co/DT4H/cardio-ner-es-disease-roberta-biomedical-multiclass)**  
  - **任务**：西班牙语心脏病学疾病命名实体识别（多类）。  
  - **现有证据**：Likes=0，下载量=18，有safetensors权重，使用RoBERTa-biomedical基座。  
  - **许可证信号**：未标注。  
  - **部署注意事项**：面向西班牙语医疗文本，适合NER管线；但未见评估指标验证。  

**4. 行业动态**  
- **[Enterprise lab-in-the-loop on AWS: How Sanofi is compressing drug discovery from years to weeks](https://aws.amazon.com/blogs/industries/enterprise-lab-in-the-loop-on-aws-how-sanofi-is-compressing-drug-discovery-from-years-to-weeks/)**  
  - **价值**：Sanofi与AWS合作，通过AI Agent设计分子、规划合成、执行实验并分析数据，实现“实验室-在-环”闭环，将药物发现周期从数年压缩至数周，展示了企业级医疗AI Agent的真实落地案例。  

**5. 研判**  
- **临床验证**：今日所有列出项目均未经过前瞻性临床研究或真实患者数据测试，医疗Agent和模型在投入临床前必须完成严格的准确性、安全性和公平性验证，建议关注后续是否有第三方评估报告。  
- **隐私合规**：仅amigo明确提及HIPAA，其他项目未说明PHI处理方式。医疗AI系统必须遵守HIPAA、GDPR等法规，使用合成数据或脱敏训练数据，并确保推理时数据不出域。  
- **后续跟踪**：建议重点关注：1) llava-medical-8B的多模态能力在医学影像上的落地进展；2) amigo平台的“数字住院医师”训练模式是否产生可复现的临床技能评估；3) Sanofi与AWS的实验室闭环模式能否被其他药企复制。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*