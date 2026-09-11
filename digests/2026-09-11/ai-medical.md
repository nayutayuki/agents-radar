# 医疗 AI 行业日报 2026-09-11

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（0 篇）；不包含论文源 | 生成时间：2026-09-11 00:31 UTC

---

# 医疗 AI 行业日报 | 2026-09-11

---

## 1. 今日结论

今日未见经临床验证或获得监管批准的医疗专用大模型或 Agent 发布。HuggingFace 与 GitHub 上涌现了一批面向问诊、放射报告、临床推理等场景的实验性项目，但均处于早期原型或学术探索阶段，Stars、下载量或公开证据不足以支撑任何生产级推荐。重点关注 **Fastino-Nemotron-3.5-Lightning-Healthcare**（高下载量通用医疗模型）和 **clinical-agent-eval-demo**（首个完整集成 FHIR over MCP + 审计链的临床对话原型）。

---

## 2. 医疗 Agent（Top 5）

| 项目 | 用途 | 成熟度 | 限制 |
|------|------|--------|------|
| [mcxxxxxcm/medical_agent](https://github.com/mcxxxxxcm/medical_agent) | 基于 LangGraph+RAG 的智能问诊，支持混合检索、多轮记忆与安全护栏 | 8 Stars，近 6 个月持续更新，代码结构较完整 | 未提供任何公开的评估数据或临床场景测试报告 |
| [hastimal/gemini-healthcare-agentic-platform](https://github.com/hastimal/gemini-healthcare-agentic-platform) | 使用 Gemini+Google ADK 的医疗搜索框架，支持查询扇出、证据检索与引用评估 | 2 Stars，Apache-2.0 许可，框架设计清晰 | 依赖闭源 Gemini API，本地部署受限；无实际医疗数据集验证 |
| [HemanthReddy-1408/medassist-ai](https://github.com/HemanthReddy-1408/medassist-ai) | MedAssist AI：LangGraph+RAG+FastAPI+Streamlit 全栈医疗助手 | 2 Stars，近 1 年未大版本迭代 | 仅描述技术栈栈，无病历/症状库集成说明，无隐私架构文档 |
| [4ktLuffy/clinical-agent-eval-demo](https://github.com/4ktLuffy/clinical-agent-eval-demo) | 临床对话代理：实时 FHIR over MCP、PHI 脱敏、哈希链审计、评估框架 | 0 Stars，MIT 许可，代码含完整评估集 | 数据持有方测试集未公开，审计链仅实验性实现 |
| [anushacodes/apollo-healthcare-agent](https://github.com/anushacodes/apollo-healthcare-agent) | 多代理临床决策支持：知识图谱+RAG+微调+LLM 评估+反馈循环 | 0 Stars，描述为“生产级”但无实际部署案例 | 依赖多个未公开的微调模型和知识图谱，可复现性低 |

---

## 3. 医疗模型（Top 5）

| 模型 | 任务 | 现有证据 | 许可证信号 | 部署注意事项 |
|------|------|----------|------------|--------------|
| [Fastino-Nemotron-3.5-Lightning-Healthcare](https://huggingface.co/fastino/Fastino-Nemotron-3.5-Lightning-Healthcare) | 文本生成（临床推理、信息提取） | 21,780 下载量，19 Likes；作者自称医疗微调 Nemotron | 未标明（大概率非开源商用） | 需 NVIDIA GPU，推理成本高；无临床验证报告 |
| [Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1](https://huggingface.co/Clinical-Reasoning-Hub/Diagnostic-Reasoning-Q3X1) | 文本生成（诊断推理） | 1,320 下载量，2 Likes；标注“benchmark-contamination” | 未见商用限制 | 基于 Qwen3，可能需人工复核；污染标签暗示基准测试作弊风险 |
| [MohamedAhmedAE/llava-medical-8B-clip-vit-stage2](https://huggingface.co/MohamedAhmedAE/llava-medical-8B-clip-vit-stage2) | 医学视觉语言（图像问答/生成） | 1,028 下载量，4 Likes；二阶段 VLM 训练 | 未标明 | 8B 参数需大显存；仅说明使用“医学数据”，无具体性能指标 |
| [surenoobsterIITBHU/qwen3-4b-radiology-report-lora](https://huggingface.co/surenoobsterIITBHU/qwen3-4b-radiology-report-lora) | 放射报告生成（LoRA 适配器） | 8 下载量，0 Likes；基于 Qwen3-4B | Apache-2.0 | 需基座模型权重；仅 LoRA 适配器，未提供报告质量评估 |
| [ufmg-digital-pathology/breast-cancer-virtual-staining](https://huggingface.co/ufmg-digital-pathology/breast-cancer-virtual-staining) | 乳腺癌虚拟染色（病理图像） | 0 下载量，0 Likes；MIT 许可 | MIT | 需 H&E 或免疫组化参考数据；未上传任何模型权重（可能仅为 placeholder） |

---

## 4. 行业动态

本日未采集到医疗 AI 行业新闻（数据源 News=0 条）。无相关产品发布、监管更新或企业合作报道。

---

## 5. 研判

**临床验证**  
今日所有候选项目均缺乏临床对照实验或基准测试报告。**Diagnostic-Reasoning-Q3X1** 明确标注“benchmark-contamination”，提示社区需警惕基准分数虚高。建议关注 **clinical-agent-eval-demo** 中的评估框架（尽管其测试集未公开），作为构建本地验证管道的参考。

**隐私合规**  
仅 **clinical-agent-eval-demo** 和 **ehr2trace** 显式提及 PHI 脱敏、FHIR MCP 或审计链。多数项目（如 medical_agent, medassist-ai）未提供 HIPAA/GDPR 合规说明，在保护敏感健康信息方面存在明显短板。**Solaceking/openeir** 声称“自托管、数据自己控制”，但未实现端到端加密或角色访问控制。

**后续值得跟踪**  
- **Fastino-Nemotron-3.5-Lightning-Healthcare** 的下载量远超同类，若作者发布微调数据或评估集，可能成为通用临床 LLM 的基线。
- **qhzeng-gittec/medical-agent-assistant** 使用 GSPO 方法训练 Qwen 3.5-2B，该方法在 RLHF 之外的偏好优化路径值得观察。
- **apertus-1.5-8b-biomedical-ade**（不良药物事件 NER）提供 GGUF 量化版本，适合本地部署在药物警戒场景，但需自行构建实体库。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*