# 医疗 AI 行业日报 2026-09-16

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-09-16 00:46 UTC

---

好的，以下是为您生成的精简日报。

**1. 今日结论**

今日未见经过临床验证或获得监管批准的专用医疗大模型或Agent正式发布。动态集中在开源社区的实验性原型和架构探索，特别是面向临床决策支持（CDSS）、个人健康管理及放射学报告生成的Agent和微调模型。值得关注的是，一个科室级CDSS项目和一个严格合规的个人健康管理Agent出现，但均处于早期开发阶段。NVIDIA博客报道的儿童医院开源AI应用是今日唯一可信的医院落地信号，使用已有开源模型而非“模型新发布”。

**2. 医疗 Agent**

*   **[poincare-lijiashu/medical-agent](https://github.com/poincare-lijiashu/medical-agent)**：一个科室级临床决策支持系统（CDSS），整合了文献查证、影像阅片、MDT多智能体会诊、智能开药（含双重药师审核）及病历质控。技术栈为FastAPI + LangGraph + Milvus，支持Docker一键部署和全链路审计。**成熟度**：极早期，仅1个Star，但架构完整，概念先进。**限制**：无任何临床测试或实际部署证据，为个人实验项目。
*   **[kyle103/medical_agent](https://github.com/kyle103/medical_agent)**：面向个人的轻量化健康管理工具，基于LLM Agent技术，专注用药安全查询、化验单解读和就诊记录归档。**成熟度**：早期，23个Star，有明确的功能边界和合规声明。**限制**：明确声明“不提供任何诊疗服务”，且功能局限于信息查询与记录管理，不涉及诊断推理。
*   **[Don-Uwe/ai-healthcare-agent-app](https://github.com/Don-Uwe/ai-healthcare-agent-app)**：一个医疗Agent应用框架，强调集中化测试和工作流，以提高健康内容分发的可靠性。**成熟度**：关注度较高（132 Stars），使用TypeScript，更新活跃。**限制**：定位为开发框架，而非可直接使用的医疗应用，其医疗内容的可靠性取决于集成该框架的具体应用。
*   **[devtechedge/healthcare-deep-memory-agents](https://github.com/devtechedge/healthcare-deep-memory-agents)**：名为“Cadence”的纯Python深度记忆Agent实验室，用于构建患者旅程记忆和临床简报。**成熟度**：原型教育项目，0 Stars，使用Ollama + SQLite本地运行。**限制**：明确声明为“教育原型，不处理真实PHI（受保护的健康信息）”，无任何生产或临床实用性。
*   **[Cure-Agent/medical-agentic-rag](https://github.com/Cure-Agent/medical-agentic-rag)**：针对医疗指南的Agentic RAG消融研究项目，测试查询分解、迭代检索、重排序等策略。**成熟度**：研究项目，0 Stars，专注于方法论对比。**限制**：纯学术研究，未产出实际可用的Agent应用，其结论对构建生产系统的指导意义有限。

**3. 医疗模型**

*   **[MohamedAhmedAE/llava-medical-8B-clip-vit-stage2](https://huggingface.co/MohamedAhmedAE/llava-medical-8B-clip-vit-stage2)**：基于LLaVA架构的多模态医学模型（8B参数）。**任务**：通用视觉-语言理解，针对医学影像。**现有证据**：无任务定义、无基准测试结果，仅提供模型权重。**许可证**：未明确。**部署**：为大型基础模型，需大量算力，未提供量化或优化版本。
*   **[adityag-india/deepseek-r1-qwen7b-medical-sft](https://huggingface.co/adityag-india/deepseek-r1-qwen7b-medical-sft)**：基于DeepSeek-R1-Distill-Qwen-7B的医学推理LoRA适配器。**任务**：文本生成，专注于医学推理。**现有证据**：提供PEFT、LoRA权重，无评估数据。**许可证**：未明确。**部署**：需配合基础模型使用，LoRA权重便于部署，但对硬件有基础要求。
*   **[RKB109/clinical-rag-safety-gateway-20260914-model](https://huggingface.co/RKB109/clinical-rag-safety-gateway-20260914-model)**：一个临床RAG安全网关模型。**任务**：问答、文本分类、摘要，旨在为RAG系统提供安全过滤。**现有证据**：无，仅有“透明基线”和“合成数据”标签。**许可证**：自定义。**部署**：概念创新，但功能未经验证，需警惕其对临床环境的适应性。
*   **[Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1](https://huggingface.co/Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1)**：基于Qwen3的诊断推理模型。**任务**：文本生成，诊断推理。**现有证据**：下载量较高（1570次），标签包含“benchmark-contamination”，暗示其评估可能存在风险。**许可证**：未明确。**部署**：模型规模未明，但声明使用QLoRA，提示有量化版本，可直接用于推理实验。
*   **[Aurigene-AI/biomedical-ner-all](https://huggingface.co/Aurigene-AI/biomedical-ner-all)**：基于DistilBERT的生物医学命名实体识别（NER）模型。**任务**：Token分类，提取生物医学实体。**现有证据**：提供标准Transformer权重，有下载记录（19次）。**许可证**：未明确。**部署**：模型小巧（DistilBERT），易于部署和集成，是可靠的结构化信息提取组件。

**4. 行业动态**

*   **Heart of the Matter: How a Major Children’s Hospital Uses Open Source NVIDIA AI for Cardiac Care**
    [来源链接](https://blogs.nvidia.com/blog/childrens-hospital-open-source-ai-cardiac-care/) | **价值**：这是今日唯一可信的医院落地案例。一家大型儿童医院使用开源的NVIDIA AI框架来辅助心脏护理，表明头部医院正积极探索将成熟的开源AI技术用于临床工作流，但文章未披露具体准确率或临床影响。

**5. 研判**

1.  **临床验证空白**：绝大多数开源项目（如poincare-lijiashu/medical-agent和各种LoRA模型）停留在概念或原型阶段，无一提供任何形式的临床验证数据、回顾性研究结果或真实世界性能评估。从观察到部署，中间存在巨大鸿沟。此前临床推理模型可能存在基准污染问题，需对其宣称能力保持警惕。
2.  **隐私合规成为显性设计**：多个新项目（如kyle103/medical_agent, devtechedge/healthcare-deep-memory-agents）开始主动将隐私合规（如声明“不提供诊疗”、“不处理真实PHI”）作为核心设计原则和宣传点，这反映出社区对医疗AI监管和伦理风险的意识正在增强。
3.  **值得跟踪的方向**：应重点跟踪**poincare-lijiashu/medical-agent**（尽管极早期）的架构演进，其整合了CDSS、影像、MDT、安全开药等完整闭环，代表了“全栈”Agent的尝试。同时，**RKB109/clinical-rag-safety-gateway-model**提出的“安全网关”概念值得关注，若未来有真实场景验证，可能成为RAG系统在临床落地的关键组件。此外，**kyle103/medical_agent**作为个人健康管理工具，其严格的合规声明和实施路径，是观察非诊疗类医疗AI如何合规发展的一个样本。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*