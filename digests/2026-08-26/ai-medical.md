# 医疗 AI 行业日报 2026-08-26

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-08-25 23:00 UTC

---

# 医疗 AI 行业日报 | 2026-08-26

## 今日结论
今日新出现一批医疗专用 Agent 和模型，但绝大多数仍处于原型或教育阶段，**缺乏临床验证与监管备案**。值得关注的是三个商业化项目（**Amigo、Insight Health、Latent Health**）以及 **Sanofi 与 AWS 的 lab-in-the-loop 药物发现合作**，显示出企业级 AI agent 在 R&D 和临床工作流中的落地潜力。

---

## 医疗 Agent（最多 5 项）

1. **Amigo（api-evangelist/amigo）**  
   - 链接：<https://github.com/api-evangelist/amigo>  
   - 用途：面向多通道（语音/文本）的临床 agent 平台，集成 EHR/FHIR 连接器、操作员工作流，并采用“数字住院医”模拟训练模式。  
   - 成熟度：1 star，仓库仅 1 个月，含详细描述但无代码或文档，**概念验证阶段**。  
   - 限制：未公开任何临床验证结果，无法确认 HIPAA 合规实施细节。

2. **Insight Health（api-evangelist/insighthealth）**  
   - 链接：<https://github.com/api-evangelist/insighthealth>  
   - 用途：AI 临床 agent 处理患者面向工作流（电话接听、传真处理、环境记录、转诊管理、分诊）。  
   - 成熟度：0 star，强调 HIPAA 合规与 FHIR 集成，但无演示或用户数据。  
   - 限制：无公开的临床测试或部署证明，需评估其实际准确率与安全性。

3. **Latent Health（api-evangelist/latent）**  
   - 链接：<https://github.com/api-evangelist/latent>  
   - 用途：企业级药剂智能平台，临床 agent 引擎读取病历、推理支付政策与药物标签，在 EHR 内执行预授权等操作。  
   - 成熟度：0 star，聚焦 340B 和用药准入流程，属于 **商业概念公开**。  
   - 限制：未披露与医院系统的实际集成案例，预授权决策的鲁棒性待验证。

4. **Sanjeevani-AI（LITDataScience/Sanjeevani-AI）**  
   - 链接：<https://github.com/LITDataScience/Sanjeevani-AI>  
   - 用途：带护栏的智能症状与病理自主医疗 agent，基于 Python。  
   - 成熟度：0 star，仅 1 天前创建，**极早期原型**。  
   - 限制：无任何描述或文档，无法评估其“护栏”机制的有效性。

5. **Cadence（devtechedge/healthcare-deep-memory-agents）**  
   - 链接：<https://github.com/devtechedge/healthcare-deep-memory-agents>  
   - 用途：纯 Python 深度记忆医疗 agent 实验室，模拟患者旅程、多层级记忆、同意范围的临床摘要，本地路径为 Ollama + SQLite + sentence-transformers。  
   - 成熟度：0 star，明确标注为**教育原型，不处理真实 PHI**。  
   - 限制：脱离真实临床环境，无任何监管合规考虑。

---

## 医疗模型（最多 5 项）

1. **llava-medical-8B-clip-vit-stage2**（MohamedAhmedAE）  
   - 链接：<https://huggingface.co/MohamedAhmedAE/llava-medical-8B-clip-vit-stage2>  
   - 任务：多模态（视觉-语言），推测用于医学影像描述。  
   - 现有证据：1964 下载、5 点赞，表明社区兴趣较高，但无基准测试。  
   - 许可证：未知。  
   - 部署注意：需 GPU（8B 参数），推理成本高，未提供量化版本。

2. **Fastino-Nemotron-3.5-Lightning-Healthcare-MLX-4bit/5bit/6bit/8bit**（nicolasembleton）  
   - 链接：<https://huggingface.co/nicolasembleton/Fastino-Nemotron-3.5-Lightning-Healthcare-MLX-4bit>  
   - 任务：文本生成（医疗对话/问答），基模型为 fastino/Fastino-Nemotron-3.5-Lightning-Healthcare。  
   - 现有证据：0 下载，但提供了 4/5/6/8bit 四种 MLX 量化版本，适合 Apple Silicon 本地部署。  
   - 许可证：未知。  
   - 部署注意：MLX 框架，仅限 macOS 设备；无任何临床评估指标。

3. **clinical-rag-safety-gateway-20260825-model**（RKB109）  
   - 链接：<https://huggingface.co/RKB109/clinical-rag-safety-gateway-20260825-model>  
   - 任务：问答、文本分类、摘要、句子相似度（临床 RAG 安全网关）。  
   - 现有证据：0 下载，作者标注为“透明基线”，使用合成数据训练。  
   - 许可证：无明确许可证。  
   - 部署注意：模型较小，适合作为 RAG 系统的安全过滤组件，但未验证在真实临床数据上的效果。

4. **qwen3-8b-radiology-gguf**（bhavikgaba）  
   - 链接：<https://huggingface.co/bhavikgaba/qwen3-8b-radiology-gguf>  
   - 任务：放射学报告生成（GGUF 量化）。  
   - 现有证据：407 下载、1 点赞，许可证 Apache-2.0，**最成熟的开源放射学模型之一**。  
   - 许可证：Apache-2.0，允许商用。  
   - 部署注意：8B 参数，GGUF 格式可在 llama.cpp 等框架上高效运行，但需自行评估生成准确性。

5. **dentai-gemma2-9b-oral-pathology-v3**（betuldanismaz）  
   - 链接：<https://huggingface.co/betuldanismaz/dentai-gemma2-9b-oral-pathology-v3>  
   - 任务：口腔病理学（基于 gemma-2-9b-it 微调）。  
   - 现有证据：0 下载，但任务领域明确，使用 Unsloth 加速微调。  
   - 许可证：未知。  
   - 部署注意：需 16GB+ GPU，缺乏病理学基准评估，不推荐用于临床诊断。

---

## 行业动态（最多 5 篇，实际 1 篇）

1. **Enterprise lab-in-the-loop on AWS: How Sanofi is compressing drug discovery from years to weeks**  
   - 链接：<https://aws.amazon.com/blogs/industries/enterprise-lab-in-the-loop-on-aws-how-sanofi-is-compressing-drug-discovery-from-years-to-weeks/>  
   - 价值：展示了 AI agent 在真实药企 R&D 中实现分子设计、合成规划、实验分析与数据闭环，压缩周期至数周，是**首个公开的制药企业级 AI agent 落地案例**，值得跟踪其后续效果数据。

---

## 研判

1. **临床验证缺口**：今日所有 Agent 和模型均未提供任何临床验证、诊断准确率或监管批准信息。即便是商业化项目（Insight Health、Latent Health）也仅停留在概念公开阶段，**建议在评估时要求提供独立验证报告或试点数据**。

2. **隐私合规信号不均**：仅 Insight Health 明确标注 HIPAA 合规，Amigo 提及 HIPAA 标签但未展示实施细节；其余项目（尤其是教育原型 Cadence）明确声明不处理真实 PHI。**医疗 AI 部署必须优先确认数据保护机制与合规审计**，否则存在严重法律风险。

3. **后续值得跟踪的方向**：  
   - **Sanofi + AWS 的 lab-in-the-loop**：若产出可复现的压缩时间数据，将推动制药业采用 AI agent。  
   - **Fastino-Nemotron-Healthcare 系列**：若社区提供临床评估基准，可能成为医疗问答的轻量级本地部署选项。  
   - **RKB109 的 clinical-rag-safety-gateway**：作为 RAG 安全组件的开源基线，若经过真实数据测试，可填补临床 RAG 的安全缺口。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*