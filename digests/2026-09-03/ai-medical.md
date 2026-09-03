# 医疗 AI 行业日报 2026-09-03

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（0 篇）；不包含论文源 | 生成时间：2026-09-03 00:38 UTC

---

# 医疗 AI 行业日报（2026-09-03）

**数据源状态：** GitHub=ok, HuggingFace=ok, News=ok（无文章）

---

## 1. 今日结论

今日未发现已通过临床验证或获得监管批准的医疗专用新模型或 Agent。开源社区活跃度集中在实验性项目与框架原型：两个医疗视觉语言模型（llava-medical-3B、Qwen3.5-2B-Medical）获得少量下载，一个临床 Agent 评估工具（clinical-agent-eval-demo）提供了带安全护栏的评测参考实现。此外，药房智能平台参考架构和病理 NER 零样本模型系列分别展示了 Agent 与模型层的新方向，但均处于早期阶段，无临床数据支撑。

---

## 2. 医疗 Agent

### ① Don-Uwe/ai-healthcare-agent-app
- **链接：** https://github.com/Don-Uwe/ai-healthcare-agent-app
- **用途：** 集中式测试与构建工作流的 AI 健康内容交付 Agent 应用。
- **成熟度：** ⭐⭐⭐ (132 Stars, MIT 许可, TypeScript, 持续更新至 2026-09-01)
- **限制：** 描述为“健康内容”，未明确区分医疗决策支持与通用健康信息，缺乏临床验证。

### ② 4ktLuffy/clinical-agent-eval-demo
- **链接：** https://github.com/4ktLuffy/clinical-agent-eval-demo
- **用途：** 带护栏的临床对话 Agent 评估框架，含 RAG 引用、EHR 工具（MCP 协议）、确定性护栏、LLM 作为裁判及置信区间计分卡。
- **成熟度：** ⭐ (0 Stars, 但 MIT 许可, 代码可运行, 仅使用合成数据)
- **限制：** 明确标注“仅合成数据”，不可用于真实患者数据；无临床评估。

### ③ akanikad/pharmacy-agentic-ai-platform
- **链接：** https://github.com/akanikad/pharmacy-agentic-ai-platform
- **用途：** 企业级药房 Agentic AI 参考架构，集成 RAG、LangGraph、Kafka、云原生及 PBM 工作流。
- **成熟度：** ⭐ (0 Stars, Python, 最新推送 2026-09-03)
- **限制：** 无许可声明，无实际部署记录，仅提供架构参考，未验证药房业务场景有效性。

### ④ lhf20/MedicalAgent
- **链接：** https://github.com/lhf20/MedicalAgent
- **用途：** 面向医学影像场景的智能问答 Agent（基于 Python）。
- **成熟度：** ⭐ (0 Stars, Python, 最近更新 2026-09-02)
- **限制：** 无描述细节，无许可声明，未说明影像类型（X光、CT等）及训练数据来源，不支持临床使用。

### ⑤ Nkj-cs/MedAgent
- **链接：** https://github.com/Nkj-cs/MedAgent
- **用途：** 基于 Spring AI 与 Qwen 的 AI 医疗助手，支持流式问诊、分层记忆、RAG 知识库和健康报告分析。
- **成熟度：** ⭐ (1 Star, Java, 单个文件提交)
- **限制：** 无许可声明，无测试数据与评估结果，知识库内容与质量未知，不可用于诊疗。

---

## 3. 医疗模型

### ① MohamedAhmedAE/llava-medical-3B-clip-vit-stage2
- **链接：** https://huggingface.co/MohamedAhmedAE/llava-medical-3B-clip-vit-stage2
- **任务：** 医疗视觉语言模型（图像+文本生成）
- **现有证据：** 下载 398 次，使用 safetensors 格式，标注 `region:us`；无任务标签与论文引用。
- **许可证信号：** 未声明（HuggingFace 默认无许可证）
- **部署注意事项：** 3B 参数规模适合本地推理，但缺乏医疗影像诊断基准测试结果，不可用于临床。

### ② Lokhidor/medical-triage-qwen3-dpo-lora-8k
- **链接：** https://huggingface.co/Lokhidor/medical-triage-qwen3-dpo-lora-8k
- **任务：** 医疗分诊（基于 Qwen3-1.7B 的 DPO 微调 LoRA）
- **现有证据：** 下载 0 次，引用 arxiv:2305.18290，使用 `trl` 框架，标注 `generated_from_trainer`。
- **许可证信号：** 未声明
- **部署注意事项：** 属 LoRA 适配器，需加载 base_model (Qwen3-1.7B-Base)；分诊效果未公开，需自行评估。

### ③ OpenMed/Qwen3.5-2B-Medical-v1
- **链接：** https://huggingface.co/OpenMed/Qwen3.5-2B-Medical-v1
- **任务：** image-text-to-text（多模态对话）
- **现有证据：** 下载 17 次，标注 `research`, `openmed`；无临床数据集说明。
- **许可证信号：** 未声明
- **部署注意事项：** 2B 参数，适合边缘设备；但 OpenMed 系列均未提供临床或病理学基准，仅表明为研究用途。

### ④ OpenMed/OpenMed-ZeroShot-NER-Pathology-Medium-209M-mlx
- **链接：** https://huggingface.co/OpenMed/OpenMed-ZeroShot-NER-Pathology-Medium-209M-mlx
- **任务：** token-classification（病理学零样本命名实体识别）
- **现有证据：** 下载 11 次，基于 GLiNER / DeBERTa-v2，提供 MLX 格式（Apple Silicon 优化）。
- **许可证信号：** 未声明
- **部署注意事项：** 零样本 NER 无需训练即可使用，但病理实体识别准确率未公开，需在目标数据上验证。

### ⑤ OpenMed/OpenMed-PII-Turkish-ClinicalBGE-Large-568M-v1
- **链接：** https://huggingface.co/OpenMed/OpenMed-PII-Turkish-ClinicalBGE-Large-568M-v1
- **任务：** token-classification（土耳其语临床 PII 去标识化）
- **现有证据：** 下载 9 次，基于 XLM-RoBERTa，标注 `pii-detection`, `de-identification`。
- **许可证信号：** 未声明
- **部署注意事项：** 专门针对土耳其语临床文本，语言限制强；PII 检测性能（精度/召回）未公开，不满足 HIPAA 或 GDPR 合规要求。

---

## 4. 行业动态

（无相关行业新闻文章）

---

## 5. 研判

### ① 临床验证：今日所有项目均缺乏临床有效性评估
- 无论 Agent 还是模型，描述中均未提及任何临床基准测试、专家评审或真实患者数据验证。clinical-agent-eval-demo 明确标注“仅合成数据”，其余项目更无说明。**在未提供诊断准确率、F1 或与金标准对比结果前，任何声称“可用于医疗”均属误导。**

### ② 隐私合规：PII 去标识模型是方向，但缺少合规声明
- OpenMed 发布了多语言临床 PII 检测模型（土耳其语、越南语等），但未提供隐私合规性声明（如 HIPAA、GDPR 或当地数据保护法）。**部署前需自行评估模型在真实去标识场景中的误差率，并确保输出不会导致再识别风险。**

### ③ 后续值得跟踪的内容
- **药房 Agent 参考架构**（akanikad/pharmacy-agentic-ai-platform）融合了 LangGraph、Kafka 和云原生，若后续补充 PBM 工作流真实案例，可能成为企业级落地的起点。
- **OpenMed 系列模型**（病理 NER、PII、多模态）覆盖了多个专科方向，但缺乏统一基准。建议关注其是否发布评估数据集或合作临床机构。
- **llava-medical 系列** 提供了 1B 和 3B 的医疗视觉语言模型，若后续有研究者公开在 ChestX-ray14、MIMIC-CXR 等标准数据集上的表现，可评估其可复用性。

---

*本日报基于公开数据源自动生成，不构成医疗建议，所有产品均未经临床验证。*

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*