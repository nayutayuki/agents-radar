# ArXiv AI 研究日报 2026-09-02

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-09-02 00:30 UTC

---

# ArXiv AI 研究日报 — 2026-09-02

## 今日速览

今日投稿聚焦于**大语言模型的自我进化与对齐**：多篇工作探索模型如何从模糊目标自主改进（Aspire, S3Gym），以及如何通过日志倾斜自动化审计（BLOOM-WILT）。**智能体工作记忆**与**过程监督**成为热点，新方法试图弥合稀疏结果奖励与密集过程信号之间的鸿沟。**工业级后训练**被类比为“棕地维护”，强调在固定预算下不退化地进行增量改进。此外，**完美长度泛化**在极小Transformer上被实现，为电路计算提供理论保证；**分子生成**与**生理时间序列**等应用领域也涌现出基础模型级方法。

## 重点论文

### 🧠 大语言模型（架构、训练、对齐、评估）

- **Aspire: Can Models Self-Evolve from Vague Goals?**  
  [链接](http://arxiv.org/abs/2608.31111v1)  
  作者：Yuhao Wu et al.  
  一句话：首次系统研究LLM如何从“成为更好的物理学家”这类模糊目标出发，自主识别能力差距、选择学习路径并验证改进，为自我进化提供新范式。

- **BLOOM-WILT: Logit Tilting for Behaviour Elicitation in Automated LLM Auditing**  
  [链接](http://arxiv.org/abs/2608.31105v1)  
  作者：Adrians Skapars, Edoardo Manino  
  一句话：提出日志倾斜（logit tilting）技术，以极低成本自动诱发部署模型中的罕见行为，使审计覆盖范围远超人工测试。

- **Scaling Large Reasoning Models beyond Human Supervision: A Path toward Superintelligence**  
  [链接](http://arxiv.org/abs/2608.31075v1)  
  作者：Zhiqin Yang et al.  
  一句话：探讨如何将RLVR（可验证奖励强化学习）从数学/代码扩展到开放域和智能体任务，指出超越人类监督是通往超智能的关键挑战。

- **A Model with No Head and Many Thoughts — Soft Latent Thinking**  
  [链接](http://arxiv.org/abs/2608.31069v1)  
  作者：Nikita Koriagin et al.  
  一句话：用连续潜变量替代离散token的LM头，推理时不产生token而是直接输出潜思维，避免词汇头计算瓶颈，有望实现更高效的推理。

- **Normalized Low-Rank Adaptation (LoRA)**  
  [链接](http://arxiv.org/abs/2608.31036v1)  
  作者：Jiale Kang et al.  
  一句话：针对LoRA零初始化导致的早期不稳定，提出归一化策略正则化训练动力学，提升微调稳定性与效果。

### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

- **SUN: Persistent Programs for Language-Grounded Control-to-Learning-to-Real Policies**  
  [链接](http://arxiv.org/abs/2608.31167v1)  
  作者：Weiqi Wang et al.  
  一句话：提出持久化程序框架，将基于模型的控制与学习策略无缝桥接，使长期操控任务中的语义得以保留而非被丢弃。

- **PaperGym: Rubric-Centered Evolution for Research-Plan Generation**  
  [链接](http://arxiv.org/abs/2608.31119v1)  
  作者：Yuhan Wang et al.  
  一句话：利用论文提取的评分准则作为批评器，通过进化算法生成研究计划，为AI科学家提供可验证的规划能力。

- **Reconciling Process Supervision with Outcome-Based Credit in Agentic Policy Optimization**  
  [链接](http://arxiv.org/abs/2608.31077v1)  
  作者：Jingxiao Yang et al.  
  一句话：提出将过程监督与结果信用分配融合，解决长程智能体交互中粗粒度奖励分配的局限。

- **Measure Before You Manage: Evaluating Agent Working Memory in Coding Agents**  
  [链接](http://arxiv.org/abs/2608.31057v1)  
  作者：Le Chen et al.  
  一句话：首次系统评估编码智能体的工作记忆，区分指令、工具输出、状态等异构对象的记忆特性，为内存管理机制提供基准。

### 🔧 方法与框架（新技术、基准测试、效率优化）

- **Constant Individual Regret in General Games**  
  [链接](http://arxiv.org/abs/2608.31166v1)  
  作者：Mingyang Liu et al.  
  一句话：在完全信息反馈下的有限博弈中，首次实现每个玩家个体遗憾为常数（与时间无关），突破对数遗憾下界。

- **Universal Transformers for Circuit Computations: Perfect Length Generalization in Tiny Transformers**  
  [链接](http://arxiv.org/abs/2608.31067v1)  
  作者：Takuya Ito et al.  
  一句话：仅用280个可学习参数实现布尔代数任务的完美长度泛化，证明极小Transformer可学习通用算法。

- **Does On-Policy Distillation Really Distill? From Noisy Teacher to Self-Improvement**  
  [链接](http://arxiv.org/abs/2608.31046v1)  
  作者：Yi Ding, Ruqi Zhang  
  一句话：质疑在线蒸馏（OPD）的可靠性，指出教师模型评估学生轨迹时存在离策略偏差，提出向自我改进的过渡方案。

- **Every Token Leaves a Ripple in the Stream of Thought: Model-Internal Token Saliency for CoT Compression**  
  [链接](http://arxiv.org/abs/2608.31066v1)  
  作者：Tianyi Zhao et al.  
  一句话：利用模型内部token显著性实现思维链压缩，在保持推理质量的同时大幅降低推理成本。

### 📊 应用（垂直领域、多模态、代码生成）

- **MNIST-PRO: MNIST is Back as a Partially Observable World for AI Agents**  
  [链接](http://arxiv.org/abs/2608.31022v1)  
  作者：Vernon Toh et al.  
  一句话：将MNIST改造为部分可观测环境，隔离测试智能体主动感知与工作记忆的协调能力，填补现有基准空缺。

- **TSPFN: A Temporal Tabular Foundation Model for Physiological Time Series Classification**  
  [链接](http://arxiv.org/abs/2608.31013v1)  
  作者：Jérémie Stym-Popper et al.  
  一句话：借鉴TabPFN，提出时序表格基础模型，在低数据量下实现生理时间序列分类的强泛化。

- **Language-Informed Flow Matching for Trend-Guided Structure-Based 3D Molecular Generation**  
  [链接](http://arxiv.org/abs/2608.31009v1)  
  作者：Tianyu Gao et al.  
  一句话：将语言信息注入流匹配，实现基于结构的3D分子生成，同时满足靶点亲和力与化学有效性约束。

## 研究趋势信号

- **从“监督”到“自我进化”**：多篇论文（Aspire, S3Gym, PaperGym）探索LLM在缺乏明确监督信号下的自主改进，模糊目标与自我评判成为核心。  
- **审计与对齐的工业化**：BLOOM-WILT、LLM Judges Verify Presence 等将审计从“事后检查”转向“自动化潜入”，并揭示了遗漏盲点等系统性问题。  
- **过程监督 vs 结果信用**：智能体强化学习中，传统稀疏奖励被过程密集信号（蒸馏、过程监督）补充，但可靠性争议（On-Policy Distillation）引发新思考。  
- **小模型的理论突破**：Universal Transformers 以极小参数实现完美泛化，暗示电路计算可被Transformer精确学习，为理论分析提供新工具。

## 值得精读

1. **Aspire**（[链接](http://arxiv.org/abs/2608.31111v1)）  
   理由：首次提出“模糊目标自我进化”框架，定义了一类全新的学习范式，对LLM长期自主提升具有里程碑意义。

2. **Normalized Low-Rank Adaptation**（[链接](http://arxiv.org/abs/2608.31036v1)）  
   理由：LoRA是当前最广泛使用的参数高效微调方法，本文从理论动力学角度解决其不稳定性，实用价值极高。

3. **Universal Transformers for Circuit Computations**（[链接](http://arxiv.org/abs/2608.31067v1)）  
   理由：用极简模型实现完美长度泛化，不仅挑战了神经网络泛化能力的传统认知，更为可解释算法学习提供了坚实案例。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*