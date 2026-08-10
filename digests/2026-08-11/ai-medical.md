# 医疗 AI 行业日报 2026-08-11

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（2 篇）；不包含论文源 | 生成时间：2026-08-10 23:16 UTC

---

# 医疗 AI 行业日报 | 2026-08-11

## 今日结论
今日医疗 AI 领域以早期开源项目为主，GitHub 和 HuggingFace 上涌现了多个医疗 Agent 与模型，但均处于概念验证或原型阶段，缺乏任何临床验证或监管批准。行业动态方面，诺和诺德与 AWS 达成战略合作，标志着大型药企加速 AI 驱动的药物发现投入，是本日最值得关注的信号。

## 医疗 Agent
1. **zavora-ai/mcp-ehr**  
   [GitHub](https://github.com/zavora-ai/mcp-ehr)  
   **用途**：EHR MCP 服务器，为临床 Agent 提供读写工具并记录 PHI 访问日志。  
   **成熟度**：1 Star，Rust 实现，近期有更新，但未标注许可证。  
   **限制**：仅提供接口层，无临床决策或验证逻辑，需自行集成合规审计。

2. **ZhuohanGe/ClinicalAgents-Code**  
   [GitHub](https://github.com/ZhuohanGe/ClinicalAgents-Code)  
   **用途**：KDD 26 论文“ClinicalAgents”代码，多 Agent 编排+双记忆实现临床决策。  
   **成熟度**：0 Stars，但论文已发表，代码于 2026-08-10 更新。  
   **限制**：未提供预训练模型或评估数据，可复现性待验证。

3. **Falehaqazi/AutoAuth-Clinical-Agent**  
   [GitHub](https://github.com/Falehaqazi/AutoAuth-Clinical-Agent)  
   **用途**：基于置信度门控的 Agentic RAG，用于临床预授权（Prior Authorization），技术栈含 LangGraph、FAISS、Llama 3.1。  
   **成熟度**：0 Stars，2026-02 创建，有持续更新。  
   **限制**：未公开任何测试结果或合规性说明，风险较高。

4. **KiyotakaShinichi/MedicalAgent**  
   [GitHub](https://github.com/KiyotakaShinichi/MedicalAgent)  
   **用途**：纵向、可解释、多模态 AI 系统，持续解析癌症患者治疗历程。  
   **成熟度**：0 Stars，Python 实现，2026-08-09 有更新。  
   **限制**：项目描述宏大但无实际数据或演示，可行性存疑。

5. **Shreya2006v/Pulse_Health**  
   [GitHub](https://github.com/Shreya2006v/Pulse_Health)  
   **用途**：PulseHealth 本地离线医疗助手，隐私优先的健康记录分析器。  
   **成熟度**：0 Stars，2026-08-08 创建，仅一次提交。  
   **限制**：纯离线设计便于隐私，但功能极简，无模型细节。

## 医疗模型
1. **Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1**  
   [HuggingFace](https://huggingface.co/Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1)  
   **任务**：文本生成（临床推理）  
   **现有证据**：1 点赞，468 下载，基于 Qwen3-8B 微调，标签含“benchmark-contamination”。  
   **许可证**：cc-by-nc-4.0  
   **部署注意事项**：需 GPU 推理，建议检查基准污染对结果的影响。

2. **HoqueMahmudul/llava-onevision-0.5b-qdora-radiology-image-caption**  
   [HuggingFace](https://huggingface.co/HoqueMahmudul/llava-onevision-0.5b-qdora-radiology-image-caption)  
   **任务**：图像到文本（放射学报告生成）  
   **现有证据**：84 下载，使用 QLoRA 微调，4-bit 量化。  
   **许可证**：未注明  
   **部署注意事项**：0.5B 参数，适合边缘设备，但需通过 PEFT 加载。

3. **mradermacher/Granite-4.1-3B-Medical_Reasoning-GGUF**  
   [HuggingFace](https://huggingface.co/mradermacher/Granite-4.1-3B-Medical_Reasoning-GGUF)  
   **任务**：医疗推理（GGUF 格式）  
   **现有证据**：0 下载，基于 Granite 4.1 微调，含 Chain-of-Thought 标签。  
   **许可证**：未注明  
   **部署注意事项**：GGUF 可直接在 llama.cpp 等本地运行，适合隐私场景。

4. **MohamedAhmedAE/llava-medical-3B-medsiglip-stage2**  
   [HuggingFace](https://huggingface.co/MohamedAhmedAE/llava-medical-3B-medsiglip-stage2)  
   **任务**：视觉语言模型（医疗影像分析）  
   **现有证据**：1239 下载，使用 MedSigLIP 视觉编码器，第二阶段训练。  
   **许可证**：未注明  
   **部署注意事项**：3B 参数，需 GPU，适合医学影像报告辅助。

5. **lokeshcodes/clinical-sentence-model**  
   [HuggingFace](https://huggingface.co/lokeshcodes/clinical-sentence-model)  
   **任务**：句子相似度（临床文本嵌入）  
   **现有证据**：24 下载，基于 BioRedditBERT 微调，支持 sentence-transformers。  
   **许可证**：未注明  
   **部署注意事项**：轻量级，适合 RAG 或聚类，无需专用硬件。

## 行业动态
1. **Novo Nordisk 选择 AWS 作为战略合作伙伴，加速 AI 药物发现**  
   [AWS 博客](https://aws.amazon.com/blogs/industries/novo-nordisk-selects-aws-as-strategic-partner-to-accelerate-drug-discovery-with-ai/)  
   **价值**：诺和诺德与 AWS 合作，将利用 AI 和云技术加速药物研发与运营现代化，是大型药企与云巨头深度绑定信号。

2. **多智能体多模态数据分析在 AWS 上的实践（第二部分）**  
   [AWS 博客](https://aws.amazon.com/blogs/industries/multi-agent-multimodal-data-analysis-on-aws-part-2-multi-agent-orchestration-and-predictive-analytics/)  
   **价值**：展示如何使用 Amazon Bedrock AgentCore 和 Strands Agents SDK 构建多模态分析 Agent，并训练预测模型，为医疗多 Agent 架构提供参考。

## 研判
1. **临床验证缺失**：今日所有开源项目均未公开任何临床测试数据或诊断准确率，距离实际应用仍有鸿沟，需警惕“AI 医疗”概念的过度包装。
2. **隐私合规需关注**：仅 `zavora-ai/mcp-ehr` 明确提及 PHI 日志，多数项目未说明数据治理措施，在 HIPAA/GDPR 下部署风险极高。
3. **后续跟踪点**：  
   - 关注 `Clinical-Reasoning-Hub` 系列模型是否有独立第三方评估报告。  
   - 跟踪诺和诺德与 AWS 合作的具体落地案例，观察对药物发现管线的影响。  
   - 留意 `MCP-EHR` 项目是否获得医疗 IT 厂商的集成支持。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*