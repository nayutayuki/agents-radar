# 医疗 AI 行业日报 2026-09-30

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-09-30 01:32 UTC

---

# 医疗 AI 行业日报 | 2026-09-30

## 1. 今日结论
今日监测范围内未发现经过临床验证或达到生产级部署的医疗专用模型 / Agent。GitHub 上涌现多个医疗 Agent 原型，但星数与活跃度偏低，均处于早期实验或学习项目阶段；HuggingFace 上“不良医疗建议”系列模型值得警惕，正面医疗模型多为 LoRA 微调或任务适配实验。行业动态仅有 AWS 一篇数字精神病学案例，提示云底座在学术医疗场景的落地潜力。

## 2. 医疗 Agent（最多5项）

1. **mcxxxxxcm/medical_agent**  
   - 链接：https://github.com/mcxxxxxcm/medical_agent  
   - 用途：基于 LangGraph + RAG 的智能问诊 Agent，支持混合检索、多轮记忆和流式输出，含安全护栏。  
   - 成熟度：9 stars，最新推送 2026-09-28，代码活跃，功能描述完整。  
   - 限制：无 license 标识，未提及任何临床测试或 HIPAA 合规信息。

2. **nihitha-i/care-agent**  
   - 链接：https://github.com/nihitha-i/care-agent  
   - 用途：基于 MCP 的安全工具型医疗 Agent，内置人工审批、访问控制、审计日志及 OpenTelemetry 追踪。  
   - 成熟度：0 stars，2026-09-29 创建，处于极早期。  
   - 限制：缺乏实际用例与验证，安全性设计未经过第三方审计。

3. **MurtazaAfzali13/smart-clinic-system1**  
   - 链接：https://github.com/MurtazaAfzali13/smart-clinic-system1  
   - 用途：双语（FA/EN）诊所管理系统 + AI 医疗助手，前端 Next.js，后端 FastAPI + LangGraph。  
   - 成熟度：0 stars，最近更新 2026-09-29，技术栈现代化。  
   - 限制：仍为单体项目，未提供可部署的 Docker 镜像或 demo 链接。

4. **cicyuun5-boop/lizi-medical-agent**  
   - 链接：https://github.com/cicyuun5-boop/lizi-medical-agent  
   - 用途：Java（Spring Boot + LangChain4j）实现的医疗问诊 Agent，新增 RAG 知识库写入链路与预约工具。  
   - 成熟度：0 stars，2026-09-28 创建，代码有具体修复记录。  
   - 限制：仅面向中文场景，无国际化支持，未公开评估数据集。

5. **94136nikitasharma/clinical-agent-orchestrator**  
   - 链接：https://github.com/94136nikitasharma/clinical-agent-orchestrator  
   - 用途：生产级异步 AI Agent 服务，编排临床试验监控工作流，基于 FastAPI + LangGraph + PostgreSQL + Redis。  
   - 成熟度：0 stars，2026-09-29 创建，架构描述详尽但无运行日志。  
   - 限制：未提供端到端测试用例或性能基准，无法判断实际稳定性。

## 3. 医疗模型（最多5项）

1. **MohamedAhmedAE/llava-medical-8B-clip-vit-stage2**  
   - 任务：视觉 - 语言多模态（医疗图像理解）  
   - 现有证据：4 likes，1951 downloads，使用 LLaVA 框架，stage2 表示第二阶段预训练。  
   - 许可证信号：无明确 license 文件。  
   - 部署注意事项：需 GPU 推理，未提供医学影像测试集准确率，不建议直接用于诊断。

2. **5iavis/medhub-llama3-clinical**  
   - 任务：文本生成（临床决策支持）  
   - 现有证据：1 like，0 downloads，使用 LoRA/QLoRA 微调于 Llama-3，标签含 openfda。  
   - 许可证信号：peft + safetensors，无独立 license。  
   - 部署注意事项：基础模型需单独获取，未公开训练数据与评估结果，适用性待验证。

3. **fastino/Fastino-Nemotron-3.5-Lightning-Healthcare**  
   - 任务：文本生成（医疗推理、信息抽取）  
   - 现有证据：22 likes，6707 downloads，社区关注度较高，标注“医疗推理”标签。  
   - 许可证信号：transformers/safetensors，无明确开源许可证说明。  
   - 部署注意事项：基于 Nemotron 架构，推理成本较高，无第三方独立测评报告。

4. **decosaai/decosa-clinical-events-modernbert-base**  
   - 任务：令牌分类（临床事件识别，即 NER）  
   - 现有证据：0 likes，9 downloads，支持 ONNX 导出，适用于医疗记录时间线抽取。  
   - 许可证信号：safetensors + ONNX，无许可证声明。  
   - 部署注意事项：模型规模较小（ModernBERT-base），适合边缘部署，但缺乏真实临床数据集上的精度报告。

5. **anon-caa-neurips/qwen3-4b-clinical-long-bench-grpo**  
   - 任务：文本生成（临床长文本基准强化学习）  
   - 现有证据：0 likes，2 downloads，基于 Qwen3-4B 使用 GRPO 强化学习，标注“harbor agent”。  
   - 许可证信号：safetensors，基础模型为 Qwen/Qwen3-4B（Apache 2.0），但 LoRA 适配器无独立许可。  
   - 部署注意事项：实验性模型，训练数据与奖励函数未公开，不适合直接用于临床。

## 4. 行业动态（共1篇）

- **From cloud to clinic: How AWS powers digital psychiatry at scale**  
  - 来源：AWS Industries Blog  
  - 链接：https://aws.amazon.com/blogs/industries/from-cloud-to-clinic-how-aws-powers-digital-psychiatry-at-scale/  
  - 价值：介绍了哈佛医学院 BIDMC 团队基于 AWS 无服务器架构搭建的开源数字精神病学平台 mindLAMP，已部署至 17 国 65 个站点，展示 AI + 云在大规模精神卫生监测中的可行路径。

## 5. 研判

1. **临床验证**：今日所有 Agent 与模型均未提供临床试验或真实患者数据验证结果。开发者需警惕将未经验证的系统推向临床决策场景，建议优先在模拟环境或回顾性数据中完成准确性、公平性及安全性测试。

2. **隐私合规**：仅 `nihitha-i/care-agent` 明确提及 HIPAA 相关设计（审计日志、访问控制），其余项目未声明任何数据合规措施。医疗 AI 部署必须遵循监管要求（HIPAA/GDPR），开发者应在文档中明示数据处理与存储策略。

3. **后续跟踪**：关注点包括（a）`llava-medical` 系列多模态模型在影像报告生成任务上的基准表现；（b）**Fastino-Nemotron-Healthcare** 高下载量背后的实际用户反馈；（c）**AWS mindLAMP** 案例是否催生更多云原生精神病学开源项目。同时建议警惕“不良医疗建议”系列模型被误用于生成误导性内容。

---  
*本日报仅作信息汇总，不构成任何临床或投资建议。*

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*