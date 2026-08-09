# 医疗 AI 行业日报 2026-08-10

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-08-09 23:04 UTC

---

# 医疗 AI 行业日报（2026-08-10）

## 今日结论
本周 GitHub 与 Hugging Face 出现**多个临床推理模型与 EHR 集成 Agent**，但均处于早期原型或企业内测阶段，**无任何项目完成临床验证或获得监管批准**。AWS 发布的多智能体编排方案是当前唯一可落地的参考架构。

---

## 医疗 Agent

1. **zavora-ai/mcp-ehr**  
   - 链接：https://github.com/zavora-ai/mcp-ehr  
   - 用途：EHR MCP 服务器，为临床 Agent 提供带 PHI 访问日志的读写工具。  
   - 成熟度：1 Star，Rust 实现，2026-08-08 更新。  
   - 限制：仅提供工具层，未验证临床工作流安全性。

2. **Falehaqazi/AutoAuth-Clinical-Agent**  
   - 链接：https://github.com/Falehaqazi/AutoAuth-Clinical-Agent  
   - 用途：基于 LangGraph + FAISS + Llama 3.1 的置信度门控 RAG，用于临床预授权。  
   - 成熟度：0 Star，完整技术栈，2026-08-09 更新。  
   - 限制：未经真实保险审核流程测试。

3. **MoriochoRadio/jump-ai-clinical-agent**  
   - 链接：https://github.com/MoriochoRadio/jump-ai-clinical-agent  
   - 用途：临床试验方案预审 Agent 原型，专为 AI 药物开发挑战赛设计。  
   - 成熟度：0 Star，2026-08-09 更新，含 regulatory-tech 标签。  
   - 限制：面向竞赛，非生产级。

4. **api-evangelist/latent**  
   - 链接：https://github.com/api-evangelist/latent  
   - 用途：企业级药房智能平台，临床 Agent 引擎可读取病历、分析 payer 政策与药品标签，在 EHR 内执行操作。  
   - 成熟度：0 Star，2026-08-08 更新，描述为商业公司产品。  
   - 限制：无公开代码或独立验证，可信度需自行评估。

5. **KiyotakaShinichi/MedicalAgent**  
   - 链接：https://github.com/KiyotakaShinichi/MedicalAgent  
   - 用途：纵向、可解释、多模态 AI 系统，持续解释癌症患者治疗历程。  
   - 成熟度：0 Star，2026-08-09 更新。  
   - 限制：无临床数据支持，仅概念验证。

---

## 医疗模型

1. **MohamedAhmedAE/llava-medical-1B-medsiglip-stage2**  
   - 链接：https://huggingface.co/MohamedAhmedAE/llava-medical-1B-medsiglip-stage2  
   - 任务：未指定（推测多模态医学图像理解）  
   - 现有证据：1 Like，1210 下载，safetensors 格式。  
   - 许可证：未标注  
   - 部署：需 LLaVA 框架，1B 参数可本地推理。

2. **Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1**  
   - 链接：https://huggingface.co/Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1  
   - 任务：text-generation（临床推理）  
   - 现有证据：1 Like，413 下载，基于 Qwen3-8B QLoRA 微调。  
   - 许可证：CC-BY-NC 4.0  
   - 部署：8B 参数，需 ≥16GB GPU；标记“benchmark-contamination”需注意过拟合风险。

3. **jocforero/clinical-modernbert-classifier**  
   - 链接：https://huggingface.co/jocforero/clinical-modernbert-classifier  
   - 任务：text-classification（临床文本分类）  
   - 现有证据：39 下载，ModernBERT 架构，支持 endpoints_compatible。  
   - 许可证：未标注  
   - 部署：BERT 级模型，适合 CPU/GPU 推理。

4. **HoqueMahmudul/llava-onevision-0.5b-qdora-radiology-image-caption**  
   - 链接：https://huggingface.co/HoqueMahmudul/llava-onevision-0.5b-qdora-radiology-image-caption  
   - 任务：image-text-to-text（放射学图像字幕）  
   - 现有证据：84 下载，4-bit QDoRA 适配器，基于 LLaVA-OneVision。  
   - 许可证：未标注  
   - 部署：0.5B 基础模型，可量化部署，适合边缘场景。

5. **Daemons-Q/qsh-medical-breastmnist-resnet50**  
   - 链接：https://huggingface.co/Daemons-Q/qsh-medical-breastmnist-resnet50  
   - 任务：image-classification（乳腺癌分类）  
   - 现有证据：量子安全 + 隐私保护联邦学习标签，ONNX 格式。  
   - 许可证：other（未明确）  
   - 部署：ResNet50 通用，需关注量子安全库集成。

---

## 行业动态

- **AWS 多智能体多模态分析博客**  
  链接：https://aws.amazon.com/blogs/industries/multi-agent-multimodal-data-analysis-on-aws-part-2-multi-agent-orchestration-and-predictive-analytics/  
  价值：展示了基于 Amazon Bedrock AgentCore 和 Strands SDK 构建医疗 Agent 编排的完整方案，并训练预测模型，是当前唯一可落地的参考架构。

---

## 研判

1. **临床验证**：所有 Agent 与模型均处于原型或预研阶段，无第三方验证。建议关注 Clinical-Reasoning-Hub 系列是否启动多中心回顾性研究。

2. **隐私合规**：zavora-ai/mcp-ehr 的 PHI 日志设计符合 HIPAA 审计要求，Daemons-Q 的量子安全+联邦学习方向值得跟踪，但均未公开合规审计报告。

3. **跟踪重点**：  
   - 企业级产品 latent（api-evangelist/latent）若开放 API 或案例研究，可能成为药房自动化标杆。  
   - llava-medical 系列下载量增长迅速，需关注其是否发布临床基准测试。  
   - AWS 方案中的多模态分析实践可能被医院 IT 采纳为参考架构。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*