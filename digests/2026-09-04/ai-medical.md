# 医疗 AI 行业日报 2026-09-04

> 数据来源：GitHub 医疗 Agent（20 个）+ Hugging Face 医疗模型（24 个）+ 医疗 AI 行业新闻（0 篇）；不包含论文源 | 生成时间：2026-09-04 00:22 UTC

---

## 医疗 AI 行业日报（2026-09-04）

### 1. 今日结论
今日没有出现经过临床验证或获得监管批准的新医疗专用模型或 Agent。开源社区在医疗 Agent 评估框架、安全监督层、企业架构以及医学研究复制方面有实质性进展；模型方面，Fastino 的医疗版 Nemotron 下载量接近 2 万次，OpenMed 发布了多款病理 NER 和 PII 去标识化模型（mlx 格式），适合边缘端部署。

### 2. 医疗 Agent
**① Don-Uwe/ai-healthcare-agent-app**  
[GitHub](https://github.com/Don-Uwe/ai-healthcare-agent-app)  
- **用途**：集中式测试与构建工作流的医疗健康 Agent 应用，使用 TypeScript 开发。  
- **成熟度**：132 Stars，960 Forks，MIT 许可证，持续更新至 2026-09-03。  
- **限制**：Forks 数异常高（可能为 fork 仓库），未说明任何临床测试或生产部署记录。

**② GOATnote-Inc/abridge**  
[GitHub](https://github.com/GOATnote-Inc/abridge)  
- **用途**：Fail-closed 监督层，用于临床 Agent 的决策和通信表面，由 Abridge × Anthropic × Lightspeed 黑客松产出。  
- **成熟度**：0 Stars，Apache-2.0 许可证，描述明确涉及临床 AI、患者安全、急诊医学。  
- **限制**：仅为黑客松原型，未提供临床验证数据或合规证明。

**③ 4ktLuffy/clinical-agent-eval-demo**  
[GitHub](https://github.com/4ktLuffy/clinical-agent-eval-demo)  
- **用途**：带护栏的临床对话 Agent 评估框架，包含 RAG、MCP 工具、确定性护栏、LLM-as-judge 和置信区间评分卡，仅使用合成数据。  
- **成熟度**：0 Stars，MIT 许可证，结构完整且可运行。  
- **限制**：完全基于合成数据，不可直接用于真实患者交互，未经过临床评估。

**④ akanikad/pharmacy-agentic-ai-platform**  
[GitHub](https://github.com/akanikad/pharmacy-agentic-ai-platform)  
- **用途**：企业级医疗 Agentic AI 参考架构，展示 RAG、LangGraph、Kafka、云原生架构及 PBM 工作流。  
- **成熟度**：0 Stars，许可证未声明，但代码结构体现企业级设计。  
- **限制**：缺少实际部署案例和性能基准，仅作为架构参考。

**⑤ hq0709/medical-agent-scaling**  
[GitHub](https://github.com/hq0709/medical-agent-scaling)  
- **用途**：复制 NMI 2026 年 Agent 扩展研究，探索医学协作中任务难度窗口（25-50% 单医生基线），共 180 配置、63,499 个 episode。  
- **成熟度**：0 Stars，TeX 格式，学术研究性质。  
- **限制**：未提供复现结果分析，尚未通过同行评审。

### 3. 医疗模型
**① fastino/Fastino-Nemotron-3.5-Lightning-Healthcare**  
[HuggingFace](https://huggingface.co/fastino/Fastino-Nemotron-3.5-Lightning-Healthcare)  
- **任务**：文本生成（text-generation）  
- **现有证据**：19 Likes，19,479 Downloads；标签包含 healthcare、clinical、medical-reasoning、information-extraction。  
- **许可证信号**：未明确标注，需自行确认。  
- **部署注意事项**：模型较大，建议使用 GPU 推理；可配合医疗信息抽取管道使用。

**② OpenMed/OpenMed-ZeroShot-NER-Pathology-Large-459M-mlx**  
[HuggingFace](https://huggingface.co/OpenMed/OpenMed-ZeroShot-NER-Pathology-Large-459M-mlx)  
- **任务**：零样本命名实体识别（token-classification），病理领域。  
- **现有证据**：0 Likes，3 Downloads；基于 DeBERTa-v2，mlx 格式，专为 Apple Silicon 优化。  
- **许可证信号**：未明确标注（OpenMed 系列通常为研究许可）。  
- **部署注意事项**：mlx 格式仅兼容 Apple Silicon 设备，适合本地隐私推理；需安装 mlx 框架。

**③ OpenMed/OpenMed-PII-Vietnamese-ClinicalBGE-Large-568M-v1-mlx**  
[HuggingFace](https://huggingface.co/OpenMed/OpenMed-PII-Vietnamese-ClinicalBGE-Large-568M-v1-mlx)  
- **任务**：越南语临床文本 PII 去标识化（token-classification）。  
- **现有证据**：0 Likes，12 Downloads；基于 XLM-RoBERTa，mlx 格式。  
- **许可证信号**：未明确标注。  
- **部署注意事项**：仅支持越南语，适合东南亚医疗数据脱敏场景；mlx 格式限制运行平台。

**④ resoajoe/clinical-scene-nano**  
[HuggingFace](https://huggingface.co/resoajoe/clinical-scene-nano)  
- **任务**：图像分类（image-classification），临床场景识别（如护士站、病房等）。  
- **现有证据**：0 Likes，0 Downloads；ONNX 格式，tiny-model，MIT 许可证。  
- **许可证信号**：MIT，可商用。  
- **部署注意事项**：模型极小（nano），适合边缘设备；仅支持有限场景，未说明精度。

**⑤ MohamedAhmedAE/llava-medical-3B-clip-vit-stage2**  
[HuggingFace](https://huggingface.co/MohamedAhmedAE/llava-medical-3B-clip-vit-stage2)  
- **任务**：医疗多模态（视觉-语言），基于 LLaVA 架构。  
- **现有证据**：1 Like，438 Downloads；safetensors 格式。  
- **许可证信号**：未明确标注。  
- **部署注意事项**：3B 参数，需 GPU 推理；stage2 训练阶段，未见临床评估报告。

### 4. 行业动态
**无**（今日采集到 0 篇医疗 AI 行业新闻文章。）

### 5. 研判
**① 临床验证仍是最大缺口**  
今日所有 Agent 和模型均停留在原型、基准或研究阶段，无任何项目声称通过临床测试或获得监管批准。建议关注后续是否有项目挂载 Lookback 或 IRB 信息。

**② 隐私合规趋势明显**  
OpenMed 系列发布多语言临床 PII 去标识化模型（越南语、土耳其语），且提供 mlx 格式支持本地推理。这反映出在边缘端处理医疗敏感数据的合规需求正在上升，值得持续跟踪其临床部署效果。

**③ 后续值得跟踪的内容**  
- **abridge** 的临床 Agent 安全监督层若与 Abridge 现有产品结合，可能快速进入验证阶段。  
- **medical-agent-scaling** 的复制研究若公开结果，可能为多 Agent 协作的诊断效率提供新证据。  
- **Fastino-Nemotron-Healthcare** 的高下载量暗示社区对医疗专用大语言模型的需求强烈，需关注其后续微调版本和临床基准评测。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*