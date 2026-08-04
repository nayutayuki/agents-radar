# 医疗 AI 行业日报 2026-08-05

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-08-04 23:39 UTC

---

# 医疗 AI 行业日报 | 2026-08-05

## 今日结论
今日未发现已通过临床验证或获得监管批准的医疗专用模型或 Agent。多数项目仍处于早期开发或概念验证阶段，Academica 系列临床试验模型与 AWS 多智能体框架值得关注，但均缺乏临床部署证据。

## 医疗 Agent
1. **SkinGraphAI**  
   [GitHub](https://github.com/chencyan21/SkinGraphAI) | 多智能体医疗助手，支持 RAG、Web 检索、医学图像分析及人工审核。  
   **成熟度**：10 Stars，Apache-2.0 许可，最近更新（2026-07-28），使用 LangGraph、Qdrant 等成熟组件。  
   **限制**：未说明临床验证，依赖通用 LLM，未提及 HIPAA 或 GDPR 合规性。

2. **Healthcare_GYM**  
   [GitHub](https://github.com/minstar/Healthcare_GYM) | 医疗 Agent 训练环境（预印本），提供模拟测试框架。  
   **成熟度**：7 Stars，Apache-2.0 许可，活跃更新至 2026-08-04。  
   **限制**：仅框架，无内置医疗模型或真实数据，需用户自行集成。

3. **FlynnMed**  
   [GitHub](https://github.com/Franosei/FlynnMed) | 开源临床 AI 生态系统，整合患者纵向数据、临床试验匹配、可复用临床 Agent。  
   **成熟度**：1 Star，MIT 许可，描述引用 NHS、NICE、OpenFDA 等标准。  
   **限制**：项目极早期，无代码提交记录，仅 HTML 页面，无运行组件。

4. **Amigo**  
   [GitHub](https://github.com/api-evangelist/amigo) | 医疗 AI 平台，支持 EHR/FHIR 连接、语音/文本渠道、数字住院培训。  
   **成熟度**：1 Star，无许可，最近更新（2026-08-03），事件溯源架构。  
   **限制**：无代码（仅文档），未披露临床测试或 HIPAA 认证细节。

5. **Insight Health**  
   [GitHub](https://github.com/api-evangelist/insighthealth) | 临床 Agent 处理电话接听、传真、笔记、分诊等患者面对工作流。  
   **成熟度**：0 Stars，无许可，项目描述较专业，提及 FHIR、HIPAA。  
   **限制**：无代码，无实际部署证据，仅概念描述。

## 医疗模型
1. **AcademicaMed-ORACLE-ClinicalTrials-SuccessProb-v1**  
   [HuggingFace](https://huggingface.co/Academica/AcademicaMed-ORACLE-ClinicalTrials-SuccessProb-v1) | 任务：表格分类（临床试验成功概率）。  
   **证据**：0 下载，CC-BY-NC-ND-4.0 许可，标签含 “calibrated-probability”。  
   **部署**：分类模型，需输入结构化临床试验数据，许可证禁止商业衍生品。

2. **AcademicaMed-FATE-ClinicalTrials-Outcome-256**  
   [HuggingFace](https://huggingface.co/Academica/AcademicaMed-FATE-ClinicalTrials-Outcome-256) | 任务：句子相似度（临床试验结果嵌入）。  
   **证据**：基于 PubMedBERT，0 下载，无许可证限制（默认）。  
   **部署**：可作为语义检索组件，需配合向量数据库使用。

3. **Kushan1Uom/new-gemma-medical-qa-lora**  
   [HuggingFace](https://huggingface.co/Kushan1Uom/new-gemma-medical-qa-lora) | 任务：文本生成（医疗 QA）。  
   **证据**：1 Like，基于 Gemma-3-4B 的 LoRA 适配器，引用 arXiv:1910.09700。  
   **部署**：需运行基础模型，推理成本低；未披露训练数据来源，需验证答案准确性。

4. **HoqueMahmudul/llava-onevision-7b-qlora-radiology-image-caption**  
   [HuggingFace](https://huggingface.co/HoqueMahmudul/llava-onevision-7b-qlora-radiology-image-caption) | 任务：图像到文本（放射学图像描述）。  
   **证据**：91 下载量，使用 QLoRA 4-bit 微调，标签含 “medical”、“radiology”。  
   **部署**：需 LLaVA-OneVision 基础模型，适合 GPU 推理；未报告放射科医生评估。

5. **pshahabinejad/qwen3-32b-emergent-plus-medical-aligned**  
   [HuggingFace](https://huggingface.co/pshahabinejad/qwen3-32b-emergent-plus-medical-aligned) | 任务：文本生成（医疗对齐）。  
   **证据**：0 下载，基于 Qwen3-32B，使用 Unsloth 微调。  
   **部署**：大模型（32B），需高显存；对齐效果未知，未提供对比基准。

## 行业动态
1. **AWS：多智能体多模态数据分析（Part 2）**  
   [原文](https://aws.amazon.com/blogs/industries/multi-agent-multimodal-data-analysis-on-aws-part-2-multi-agent-orchestration-and-predictive-analytics/) | 使用 Amazon Bedrock AgentCore 和 Strands Agents SDK 构建医疗多模态分析 Agent，并训练 SageMaker 预测模型。  
   **价值**：提供可复现的医疗多智能体架构参考，附带代码仓库，但未涉及真实患者数据。

## 研判
- **临床验证**：所有模型与 Agent 均未提供临床性能指标（如敏感度、特异度）或第三方验证报告。建议关注 Academica 临床试验模型未来是否公开验证集。
- **隐私合规**：多数项目未明确说明 HIPAA/GDPR 合规措施。Amigo 和 Insight Health 虽提及 HIPAA，但无代码认证。建议在部署前要求平台提供 SOC 2 或 BAA 文档。
- **后续跟踪**：建议关注 Healthcare_GYM 预印本的正式发表，以及 FlynnMed 后续代码提交节奏。AWS 博客中的多智能体框架若集成真实 EHR 数据，可能成为行业参考实现。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*