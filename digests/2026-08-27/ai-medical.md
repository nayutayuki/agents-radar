# 医疗 AI 行业日报 2026-08-27

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-08-27 03:33 UTC

---

**1. 今日结论**  
今日未发现任何经过临床验证或完成监管申报的医疗AI Agent或模型。开源项目中，FlynnMed 提出了完整的临床AI生态概念但代码量极低；企业级项目如 Latent Health、Insight Health 描述完整但均未公开有效代码或评估数据。模型方面，斯坦福大学发布的临床NER模型（去标识化）具有学术背景，放射学专用模型（Qwen3-8b GGUF）下载量较高，但均缺乏临床有效性证据。

**2. 医疗 Agent**（最多5项）  
- **[FlynnMed](https://github.com/Franosei/FlynnMed)**  
  用途：开源临床AI生态，整合患者数据、临床试验匹配、循证医学Agent。  
  成熟度：仅1星，代码主要基于HTML，概念阶段。  
  限制：无实际部署案例，未提供任何临床验证数据。  
- **[Amigo](https://github.com/api-evangelist/amigo)**  
  用途：多通道（语音/文本）医疗AI平台，集成EHR/FHIR，含“数字住院医师”训练模式。  
  成熟度：1星，无公开代码（Language: N/A）。  
  限制：仅仓库元数据，无法验证其功能完整性。  
- **[Latent (Latent Health)](https://github.com/api-evangelist/latent)**  
  用途：企业药房智能Agent，处理prior authorization、药物标签推理。  
  成熟度：0星，描述专业但无代码。  
  限制：无法评估其临床推理准确性。  
- **[Insight Health](https://github.com/api-evangelist/insighthealth)**  
  用途：临床工作流自动化Agent，覆盖电话应答、传真处理、笔记、分诊等。  
  成熟度：0星，无代码。  
  限制：未公开任何用户反馈或性能指标。  
- **[CardioAI-Clinical-Agent](https://github.com/Athanasios-Sakatziadis/CardioAI-Clinical-Agent)**  
  用途：心脏脉搏预测。  
  成熟度：0星，Python代码简单，描述含糊。  
  限制：未说明训练数据来源，无法判断预测可靠性。

**3. 医疗模型**（最多5项）  
- **[stanford-med-hdr/tide2-sentry-clinical-ner](https://huggingface.co/stanford-med-hdr/tide2-sentry-clinical-ner)**  
  任务：token-classification（临床去标识化NER）  
  证据：斯坦福团队开发，基于deberta-v2，下载0次。  
  许可证：未知。  
  部署：需transformers库，适合院内文本去标识化。  
  注意：学术背景可靠，但未提供在真实临床数据上的表现。  
- **[bhavikgaba/qwen3-8b-radiology-gguf](https://huggingface.co/bhavikgaba/qwen3-8b-radiology-gguf)**  
  任务：文本生成（放射学）  
  证据：下载407次，1个likes，Apache-2.0许可。  
  许可证：Apache-2.0。  
  部署：GGUF格式，可本地运行（llama.cpp），适合放射科报告辅助。  
  注意：无临床验证，仅社区关注高。  
- **[nicolasembleton/Fastino-Nemotron-3.5-Lightning-Healthcare-MLX-5bit](https://huggingface.co/nicolasembleton/Fastino-Nemotron-3.5-Lightning-Healthcare-MLX-5bit)**  
  任务：文本生成（医疗保健）  
  证据：下载231次，基于Fastino商业模型，量化版。  
  许可证：未知（base_model为商业许可）。  
  部署：MLX格式，仅适用于Apple Silicon，需确认许可合规。  
  注意：高下载量不代表临床有效性。  
- **[Aniekanabasiumoh/FeverMate-Clinical-Copilot-v0.3.1-GGUF](https://huggingface.co/Aniekanabasiumoh/FeverMate-Clinical-Copilot-v0.3.1-GGUF)**  
  任务：临床决策支持（1.5B参数）  
  证据：下载110次，GGUF离线可运行，基于Qwen2.5-1.5B-Instruct。  
  许可证：未知。  
  部署：llama.cpp，适合边缘设备或离线场景。  
  注意：模型规模小，无法替代专业诊断。  
- **[kayodekosi/medical-clinical-decision-support-7b](https://huggingface.co/kayodekosi/medical-clinical-decision-support-7b)**  
  任务：文本生成（鉴别诊断、分诊）  
  证据：0下载，PEFT微调，作者未提供评估数据。  
  许可证：未知。  
  部署：需transformers，但未经验证，慎用。  
  注意：完全无公开证据支撑。

**4. 行业动态**（最多5篇）  
- **[Enterprise lab-in-the-loop on AWS: How Sanofi is compressing drug discovery from years to weeks](https://aws.amazon.com/blogs/industries/enterprise-lab-in-the-loop-on-aws-how-sanofi-is-compressing-drug-discovery-from-years-to-weeks/)**  
  价值：展示大型药企Sanofi如何利用AI Agent实现分子设计、合成规划、实验分析全流程自动化，将药物发现周期大幅压缩，为行业提供可复用的Lab-in-the-loop架构参考。

**5. 研判**  
1. **临床验证缺失**：所有开源Agent和模型均未提供任何临床验证数据（如诊断准确率、AUC、临床对照试验结果）。即便斯坦福临床NER有学术背书，也需在真实HIPAA环境中重新评估。  
2. **隐私合规风险**：多数项目未明确声明HIPAA/GDPR合规性。FlynnMed提及NHS/NICE但未涉及数据保护；Latent Health和Insight Health虽在描述中提及HIPAA，但代码未公开，无法审计。建议企业采购前需做完整安全评估。  
3. **后续跟踪重点**： 
   - **FlynnMed**：作为唯一MIT许可的开源临床AI生态，其社区发展速度值得关注。  
   - **Sanofi lab-in-the-loop**：实际落地效果将影响药企AI Agent采用方向。  
   - **放射学模型**（Qwen3-8b GGUF）和FeverMate临床Copilot（GGUF）因可离线部署，可能在资源受限场景率先试点，但需密切监控其输出偏差。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*