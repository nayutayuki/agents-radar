# 医疗 AI 行业日报 2026-08-13

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（2 篇）；不包含论文源 | 生成时间：2026-08-12 23:21 UTC

---

# 医疗 AI 行业日报 | 2026-08-13

## 1. 今日结论
今日涌现多个医疗 Agent 和微调模型项目，但均处于早期概念或原型阶段，**尚无任何项目提供临床验证、监管批准或生产部署证据**。值得关注的是，问答型 Agent 集中于 LangGraph/RAG 架构，模型端则出现大批针对 Qwen3 的医疗分诊、诊断推理 LoRA 微调，以及专用多模态 LLaVA-Medical 版本。企业级平台（如 amigo、Latent）描述完整但代码仓库尚未获得关注度。

---

## 2. 医疗 Agent（最多 5 项）

- **mcxxxxxcm/medical_agent**  
  [https://github.com/mcxxxxxcm/medical_agent](https://github.com/mcxxxxxcm/medical_agent)  
  **用途**：基于 LangGraph + RAG 的智能问诊 Agent，支持混合检索、多轮记忆、流式输出和安全护栏。  
  **成熟度**：Stars 7，Python 实现，最近更新于 2026-08-12，代码较完整。  
  **限制**：未提及 HIPAA 合规或临床测试，适合研究原型。

- **api-evangelist/amigo**  
  [https://github.com/api-evangelist/amigo](https://github.com/api-evangelist/amigo)  
  **用途**：医疗 AI 平台，支持语音/文本通道、EHR/FHIR 连接、操作员工作流及“数字住院医师”训练模式。  
  **成熟度**：Stars 1，但描述详细，涵盖 HIPAA 和企业级集成。  
  **限制**：无实际部署案例，代码仓库未公开实现。

- **Franosei/FlynnMed**  
  [https://github.com/Franosei/FlynnMed](https://github.com/Franosei/FlynnMed)  
  **用途**：开源临床 AI 生态系统，整合患者智能、协作、临床试验匹配和可复用临床 Agent。  
  **成熟度**：Stars 1，MIT 许可，最近更新于 2026-08-12。  
  **限制**：仅 HTML 描述，无运行代码，未验证性能。

- **api-evangelist/insighthealth**  
  [https://github.com/api-evangelist/insighthealth](https://github.com/api-evangelist/insighthealth)  
  **用途**：用于患者面向工作流的临床 Agent，涵盖电话接听、传真处理、环境笔记、转诊等。  
  **成熟度**：Stars 0，但描述完整，Topics 含 HIPAA/FHIR。  
  **限制**：无任何代码或文档，仅概念介绍。

- **api-evangelist/latent**  
  [https://github.com/api-evangelist/latent](https://github.com/api-evangelist/latent)  
  **用途**：企业药房智能平台，临床 Agent 引擎读取病历、推理 payer 政策和药物标签，在 EHR 内行动。  
  **成熟度**：Stars 0，Topics 含 340B、prior-authorization、EHR 集成。  
  **限制**：同上，仅有 README 级别描述。

---

## 3. 医疗模型（最多 5 项）

- **MohamedAhmedAE/llava-medical-3B-clip-vit-stage2**  
  [https://huggingface.co/MohamedAhmedAE/llava-medical-3B-clip-vit-stage2](https://huggingface.co/MohamedAhmedAE/llava-medical-3B-clip-vit-stage2)  
  **任务**：多模态（图像+文本）医学问答/描述。  
  **现有证据**：下载量 1,033，无评估指标。  
  **许可证信号**：未指定。  
  **部署注意事项**：需 GPU 资源，无安全护栏说明。

- **fastino/Fastino-Nemotron-3.5-Lightning-Healthcare**  
  [https://huggingface.co/fastino/Fastino-Nemotron-3.5-Lightning-Healthcare](https://huggingface.co/fastino/Fastino-Nemotron-3.5-Lightning-Healthcare)  
  **任务**：文本生成（医疗推理、信息抽取）。  
  **现有证据**：12 Likes，无评测数据集。  
  **许可证信号**：未指定（推测为 Nemotron 许可）。  
  **部署注意事项**：支持 transformers 推理，需注意医疗领域输出准确性。

- **Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1**  
  [https://huggingface.co/Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1](https://huggingface.co/Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1)  
  **任务**：临床诊断推理文本生成。  
  **现有证据**：1 Like，下载 513，基于 Qwen3-8B QLoRA 微调，标签含 `benchmark-contamination`。  
  **许可证信号**：CC-BY-NC-4.0（非商业）。  
  **部署注意事项**：禁止商业使用，需要评估基准污染影响。

- **RemDev-AI/medical-triage-agent-ai-poc-models**  
  [https://huggingface.co/RemDev-AI/medical-triage-agent-ai-poc-models](https://huggingface.co/RemDev-AI/medical-triage-agent-ai-poc-models)  
  **任务**：文本生成（医疗分诊 Agent）。  
  **现有证据**：下载 125，基于 Qwen3-1.7B 的 DPO+LoRA 微调。  
  **许可证信号**：未指定。  
  **部署注意事项**：POC 模型，未验证分诊准确率，需集成安全护栏。

- **jocforero/clinical-modernbert-classifier**  
  [https://huggingface.co/jocforero/clinical-modernbert-classifier](https://huggingface.co/jocforero/clinical-modernbert-classifier)  
  **任务**：文本分类（临床文本）。  
  **现有证据**：下载 46，使用 ModernBERT，支持 `endpoints_compatible`。  
  **许可证信号**：未指定。  
  **部署注意事项**：适合快速接入推理端点，但无公开评估数据集。

---

## 4. 行业动态（最多 5 篇）

- **Novo Nordisk selects AWS as strategic partner to accelerate drug discovery with AI**  
  [https://aws.amazon.com/blogs/industries/novo-nordisk-selects-aws-as-strategic-partner-to-accelerate-drug-discovery-with-ai/](https://aws.amazon.com/blogs/industries/novo-nordisk-selects-aws-as-strategic-partner-to-accelerate-drug-discovery-with-ai/)  
  **价值**：全球制药巨头与 AWS 深度合作，将 AI 和云技术用于药物发现，预示行业级算力和数据基础设施需求增长。

- **Multi-Agent Multimodal Data Analysis on AWS – Part 2**  
  [https://aws.amazon.com/blogs/industries/multi-agent-multimodal-data-analysis-on-aws-part-2-multi-agent

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*