# ArXiv AI 研究日报 2026-09-01

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-09-01 01:23 UTC

---

# ArXiv AI 研究日报（2026-09-01）

## 今日速览

今日arXiv投稿密集聚焦于**LLM智能体的长期记忆与推理系统**——Agent Zero Memory、Hindsight Memory-PRM、MedCache等从不同角度构建可溯源、可审计的持久记忆；**多智能体故障归因与系统化技能框架**为智能体可靠部署提供基础。在架构层面，**LoGo动态局部‑全局注意力**有望缓解长上下文计算瓶颈。评估方面，**SUP‑MIMIC临床诊断基准**和**LLM Judges as Raters评分审计**凸显了对模型鲁棒性与公平性的关注。此外，**持续遗忘（Plasticity Collapse）** 和**溯源水印**等安全问题成为新热点。

---

## 重点论文

### 🧠 大语言模型（架构、训练、对齐、评估）

**1. LoGo: Token-Level Dynamic Local-Global Attention**  
[链接](http://arxiv.org/abs/2608.29539v1)  
Y. Pan et al.  
**一句话说明**：提出按token动态分配局部与全局注意力预算的机制，在保持性能的同时显著降低长上下文计算开销，是Transformer效率优化的重要进展。

**2. MI-Distillation: Selecting from Model-Interpolated Instruct-Reasoning Data Spectrum for Chain-of-Thought Distillation**  
[链接](http://arxiv.org/abs/2608.29623v1)  
Y. Lan et al.  
**一句话说明**：通过模型插值生成多样化的推理数据光谱，选择性地蒸馏长思维链到小模型，解决直接蒸馏增益有限的问题。

**3. Beyond Surface Alignment: Grounding the Dynamics of Situational Understanding and Generative Control in LLMs**  
[链接](http://arxiv.org/abs/2608.29610v1)  
C. Yang  
**一句话说明**：批判当前对齐仅关注表面行为，提出使LLM具备情境理解与生成控制的 grounding 方法，推动对齐向深层认知发展。

**4. Evaluating LLMs on Convers

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*