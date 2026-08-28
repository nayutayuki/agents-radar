# 医疗 AI 行业日报 2026-08-28

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（1 篇）；不包含论文源 | 生成时间：2026-08-28 06:19 UTC

---

# 医疗 AI 行业日报（2026-08-28）

## 今日结论
今日出现多个医疗 AI Agent 与模型，但多为早期开发或概念验证项目，**缺乏经过临床验证或获得监管批准的信号**。值得关注的是斯坦福大学发布的临床命名实体识别（NER）模型和 Sanofi 与 AWS 合作的“lab-in-the-loop”药物发现平台，前者具备去标识化能力，后者展示了企业级 AI agent 在真实研发场景中的落地路径。整体上，行业仍处于“工具搭建”阶段，距离生产部署尚有距离。

## 医疗 Agent
1. **[Moe-phantom/Medical_AI_agent](https://github.com/Moe-phantom/Medical_AI_agent)**  
   - 用途：带安全措施的医疗 RAG 系统，可处理多轮对话并过滤不当输出。  
   - 成熟度：1 星，今日有更新，代码为 Jupyter Notebook，尚未封装为可部署服务。  
   - 限制：未说明安全措施具体实现及临床测试数据。

2. **[api-evangelist/amigo](https://github.com/api-evangelist/amigo)**  
   - 用途：跨语音/文本通道的临床 Agent 构建平台，内置 EHR/FHIR 连接器及“数字住院医师”模拟训练模式。  
   - 成熟度：1 星，文档较完整，声明 HIPAA 合规，但无真实用户案例。  
   - 限制：许可证未标注，仅处于概念展示阶段，未提供生产级部署指南。

3. **[Franosei/FlynnMed](https://github.com/Franosei/FlynnMed)**  
   - 用途：开源临床 AI 生态，整合患者纵向数据、临床协作、临床试验匹配及可复用 Agent。  
   - 成熟度：1 星，MIT 许可，引用 NHS/NICE 等标准，但代码主要为 HTML 描述性文档。  
   - 限制：缺乏实际运行代码，仍为平台设计草图。

4. **[api-evangelist/latent](https://github.com/api-evangelist/latent)**  
   - 用途：企业药房智能平台，Agent 引擎读取病历、分析保险政策与药品标签，在 EHR 内执行操作。  
   - 成熟度：0 星，无代码仓库，仅描述文档，聚焦 340B 药品折扣与预先授权流程。  
   - 限制：无实际实现，依赖 API 整合，需验证与医院系统对接的可行性。

5. **[api-evangelist/insighthealth](https://github.com/api-evangelist/insighthealth)**  
   - 用途：AI 临床 Agent 处理电话接听、传真、环境笔记、随访、转诊分诊等患者面向前台工作。  
   - 成熟度：0 星，声明 HIPAA 合规，但无代码或测试数据，仅概念架构。  
   - 限制：未说明语音识别准确率及临床场景覆盖范围，缺乏 POC 结果。

## 医疗模型
1. **[stanford-med-hdr/tide2-sentry-clinical-ner](https://huggingface.co/stanford-med-hdr/tide2-sentry-clinical-ner)**  
   - 任务：token-classification（临床去标识化 NER）  
   - 现有证据：来自斯坦福医学 HDR 团队，基于 DeBERTa-v2，专用于识别 PHI/PII。  
   - 许可证：未标注，但模型权重为 safetensors 格式。  
   - 部署注意事项：0 下载量，需自行评估在真实病历上的泛化能力；可集成到去标识化管道中。

2. **[resoajoe/clinical-scene-nano](https://huggingface.co/resoajoe/clinical-scene-nano)**  
   - 任务：image-classification（临床场景识别）  
   - 现有证据：ONNX 格式，Tiny 模型，适合边缘部署，MIT 许可。  
   - 部署注意事项：0 下载量，模型仅 1.5 MB 左右，适合医院内智能摄像头等场景，但需验证分类类别（如手术室、病房）的准确性。

3. **[bhavikgaba/qwen3-8b-radiology-gguf](https://huggingface.co/bhavikgaba/qwen3-8b-radiology-gguf)**  
   - 任务：text-generation（放射学领域）  
   - 现有证据：287 下载量，1 点赞，GGUF 量化格式，Apache-2.0 许可。  
   - 部署注意事项：适合本地推理，但未说明微调数据集及放射报告生成效果，需自行测试幻觉率。

4. **[nicolasembleton/Fastino-Nemotron-3.5-Lightning-Healthcare-MLX-5bit](https://huggingface.co/nicolasembleton/Fastino-Nemotron-3.5-Lightning-Healthcare-MLX-5bit)**  
   - 任务：text-generation（通用医疗对话）  
   - 现有证据：233 下载量，MLX 5bit 量化版，基于 Fastino 医疗基础模型。  
   - 部署注意事项：仅适配 Apple Silicon，量化可能损失回答质量，未提供医疗领域基准测试结果。

5. **[ChicagoHAI/qwen2.5-32b-em-medical-advice](https://huggingface.co/ChicagoHAI/qwen2.5-32b-em-medical-advice)**  
   - 任务：text-generation（医疗建议）  
   - 现有证据：来自芝加哥大学 HAI 实验室，基于 Qwen2.5-32B 微调，0 下载量。  
   - 部署注意事项：模型较大，需 64GB+ 显存；未公开评估指标，不建议直接用于患者咨询。

## 行业动态
- **[Enterprise lab-in-the-loop on AWS: How Sanofi is compressing drug discovery from years to weeks](https://aws.amazon.com/blogs/industries/enterprise-lab-in-the-loop-on-aws-how-sanofi-is-compressing-drug-discovery-from-years-to-weeks/)**  
  来源：AWS Industries Blog  
  价值：展示了 Sanofi 如何利用 AI agent 设计分子、规划合成、执行实验并分析数据，同时通过“lab-in-the-loop”机制结合历史实验数据避免重复工作，是制药行业 AI agent 落地的典型案例。

## 研判
1. **临床验证方面**：今日所有 Agent 和模型均未提供临床准确率、敏感度/特异度等指标。建议优先关注 **Stanford 临床 NER 模型**（后续可能发布评估报告）和 **ChicagoHAI 系列**的学术论文，其他项目需等待独立第三方验证。  
2. **隐私合规方面**：api-evangelist 旗下多个 Agent 声明了 HIPAA 合规，但未提供审计证据；**Stanford 临床 NER** 直接聚焦去标识化，是合规基础设施的关键组件。企业部署前应进行数据保护影响评估（DPIA）。  
3. **后续跟踪**：  
   - 关注 **Sanofi 与 AWS 的 lab-in-the-loop 平台**是否在 2026 年底前公布分子发现效率数据。  
   - 跟踪 **resoa乔/clinical-scene-nano** 的边缘部署案例，探索医院场景下的实时场景分类可行性。  
   - 观察 **FlynMed** 是否从设计文档转为可运行代码，尤其是其临床试验匹配 Agent 的实用性。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*