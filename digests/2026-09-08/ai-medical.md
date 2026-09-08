# 医疗 AI 行业日报 2026-09-08

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（0 篇）；不包含论文源 | 生成时间：2026-09-08 00:39 UTC

---

# 医疗 AI 行业日报 | 2026-09-08

## 今日结论
当日未出现经临床验证或监管批准的医疗专用模型或 Agent，所有项目均处于早期开发或实验阶段。开源生态中涌现出多个面向问诊、临床摘要、病理 NER 的轻量级模型，以及基于 LangGraph/FHIR 的 Agent 框架，但成熟度极低，需警惕“演示即产品”的误导。

## 医疗 Agent（5 项）
1. **[mcxxxxxcm/medical_agent](https://github.com/mcxxxxxcm/medical_agent)**  
   - **用途**：基于 LangGraph + RAG 的智能问诊 Agent，支持混合检索、多轮记忆与流式输出。  
   - **成熟度**：GitHub 8⭐，最近更新（2026-09-07），代码完整但无临床评估。  
   - **限制**：未公开任何准确率或安全护栏效果数据。

2. **[hastimal/gemini-healthcare-agentic-platform](https://github.com/hastimal/gemini-healthcare-agentic-platform)**  
   - **用途**：开源医疗搜索框架，利用 Gemini 和 Google ADK 进行查询扇出、证据检索与引用评估。  
   - **成熟度**：2⭐，Apache-2.0 许可证，代码结构清晰。  
   - **限制**：依赖外部 API，本地部署需自行配置 Grounding 服务。

3. **[HemanthReddy-1408/medassist-ai](https://github.com/HemanthReddy-1408/medassist-ai)**  
   - **用途**：医疗助手，集成 LangGraph + RAG + FastAPI + Streamlit。  
   - **成熟度**：2⭐，有 1 个复刻，最近更新（2026-09-05）。  
   - **限制**：仅提供 Demo 界面，未包含任何医疗合规机制。

4. **[ArjavDesa912/Long-Horizon-Medical-Agent-Benchmark](https://github.com/ArjavDesa912/Long-Horizon-Medical-Agent-Benchmark-Veterinary-Clinic-Ops)**  
   - **用途**：面向兽医诊所的长周期医疗 Agent 基准测试框架。  
   - **成熟度**：1⭐，代码刚上传（2026-09-01）。  
   - **限制**：专注兽医学，非人类临床场景。

5. **[4ktLuffy/clinical-agent-eval-demo](https://github.com/4ktLuffy/clinical-agent-eval-demo)**  
   - **用途**：带护栏的临床对话 Agent 部署层，集成 FHIR over MCP、PHI 脱敏、哈希链审计。  
   - **成熟度**：0⭐但描述专业，MIT 许可证，有评估代码。  
   - **限制**：评估数据为固定集，未在真实 EHR 上测试。

## 医疗模型（5 项）
1. **[Fastino-Nemotron-3.5-Lightning-Healthcare](https://huggingface.co/fastino/Fastino-Nemotron-3.5-Lightning-Healthcare)**  
   - **任务**：文本生成（医疗推理、信息提取）  
   - **证据**：19 Likes，21,560 下载量，社区关注度高；HuggingFace 标签包含 `clinical` 和 `medical-reasoning`。  
   - **许可证**：未公开明确许可证（仅 `nemotron_h` 标签）。  
   - **部署注意**：8B 参数量，需 GPU 推理，建议先验证输出合规性。

2. **[llava-medical-8B-clip-vit-stage2](https://huggingface.co/MohamedAhmedAE/llava-medical-8B-clip-vit-stage2)**  
   - **任务**：医学视觉语言模型（图像问答）  
   - **证据**：5 Likes，775 下载量，基于 LLaVA 在医学数据上微调。  
   - **许可证**：无明确声明（safetensors 格式）。  
   - **部署注意**：适用于医学影像解释，但未披露训练数据来源和性能指标。

3. **[apertus-1.5-8b-biomedical-ade](https://huggingface.co/andreasmartin/apertus-1.5-8b-biomedical-ade)**  
   - **任务**：文本生成（不良药物事件 NER）  
   - **证据**：0 Likes，527 下载量；同时发布 GGUF 量化版（64 下载）。  
   - **许可证**：未声明。  
   - **部署注意**：针对 Adverse Drug Events 微调，适合药物警戒场景，需确保实体识别召回率。

4. **[OpenMed-ZeroShot-NER-Pathology-Medium-209M-mlx](https://huggingface.co/OpenMed/OpenMed-ZeroShot-NER-Pathology-Medium-209M-mlx)**  
   - **任务**：零样本病理学命名实体识别  
   - **证据**：0 Likes，20 下载量；OpenMed 系列含多种尺寸，提供 MLX 格式（Apple Silicon）。  
   - **许可证**：未声明。  
   - **部署注意**：209M 参数，适合边缘端；零样本能力需结合测试集验证。

5. **[kotoba-whisper-medical-ja-ONNX](https://huggingface.co/willopcbeta/kotoba-whisper-medical-ja-ONNX)**  
   - **任务**：日语医疗语音识别  
   - **证据**：0 Likes，28 下载量；基于 Whisper 对日语医疗术语微调，导出 ONNX 格式。  
   - **许可证**：未声明。  
   - **部署注意**：适用于日语临床听写，需确认方言和噪声鲁棒性。

## 行业动态
无（当日未检索到医疗 AI 相关行业新闻文章）。

## 研判
1. **临床验证**：所有收录项目均处于“研究演示”或“社区实验”阶段，无任何项目公开过临床对照试验、FDA/EU MDR 批准或诊断准确率声明。医院或药企若考虑采用，亟需内部验证。

2. **隐私合规**：仅 `clinical-agent-eval-demo` 明确提及 PHI 脱敏和审计链；多数模型/Agent 未说明数据处理流程，在 HIPAA/GDPR 要求下直接使用风险极高。

3. **后续跟踪**：
   - 重点关注 `Fastino-Nemotron-3.5-Lightning-Healthcare` 的社区反馈和许可证澄清，其高下载量暗示潜在生产试用。
   - `OpenMed` 系列在病理 NER 上的零样本能力若与病理报告结构化系统结合，可能成为低成本方案。
   - 各 Agent 项目常依赖 LangGraph/LangChain，其编排层安全性（如工具调用注入）需持续监控。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*