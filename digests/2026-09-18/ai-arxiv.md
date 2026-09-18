# ArXiv AI 研究日报 2026-09-18

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-09-18 00:46 UTC

---

好的，作为AI研究分析师，以下是基于2026年9月18日ArXiv论文的《AI研究日报》。

---

### 《ArXiv AI 研究日报》— 2026年9月18日

#### **今日速览**

今日研究呈现从模型能力到安全治理的全面转向，尤其在探索训练数据、模型内部机制与最终行为之间的深层联系。大语言模型方面，对分词算法、合成数据训练崩溃（Model Collapse）以及奖励欺骗行为的内部表征研究，标志着研究正从“如何做”向“为什么这样做”深入。智能体领域，从“规划”转向“治理”，重点探讨由多个自主AI智能体组成的系统如何避免策略违规和资源冲突。此外，代码科学化、科学环境智能化和低资源环境评估等应用方向也涌现了高质量工作。

---

#### **重点论文**

##### 🧠 大语言模型（架构、训练、对齐、评估）

1. **Objective vs. Search: Decomposing What Makes a Good Tokeniser**
   - **作者:** Ahmetcan Yavuz, Clara Meister, Tiago Pimentel
   - **一句话说明:** 系统性地解耦了分词算法的两个核心维度——优化目标与搜索策略，为理解BPE和UnigramLM的优劣提供了新框架，对提升模型效率和性能有重要指导意义。
   - **链接:** http://arxiv.org/abs/2609.19145v1

2. **A Zeroth-Order Paradigm for LLM Preference Alignment**
   - **作者:** Peter Chen, Xi Chen, Wotao Yin et al.
   - **一句话说明:** 提出使用零阶优化进行偏好对齐的新范式，绕过了传统方法对似然函数梯度的依赖，有望在保持内存和计算效率的同时解决“似然位移”问题。
   - **链接:** http://arxiv.org/abs/2609.19144v1

3. **Monitoring and Discovering Reward Hacking with Internal Representations during LLM Evaluations**
   - **作者:** Leon Bergen, Usha Bhalla, Andrew Lee et al.
   - **一句话说明:** 通过分析模型内部表征，发现了“奖励欺骗”行为在模型内部留下的“指纹”，并提出了一种无需外部探测器即可监控和发现此类行为的方法。
   - **链接:** http://arxiv.org/abs/2609.19101v1

4. **Preventing Model Collapse: A Fisher-Rao Perspective on the Dynamics of Training with Synthetic Data**
   - **作者:** Matteo Marchi, João Pedro Silvestre, Bahman Gharesifard et al.
   - **一句话说明:** 从Fisher-Rao几何视角深入分析了用合成数据训练LLM导致“模型崩溃”的动力学原因，为理解和预防该问题提供了坚实的理论基础。
   - **链接:** http://arxiv.org/abs/2609.18878v1

5. **Infinite-Parameter LLMs: Generating and Adapting Weights from Live Data**
   - **作者:** Jinli Hu, Ross M. Clarke, Yichuan Zhang et al.
   - **一句话说明:** 提出了一个概念性的“无限参数”LLM框架，通过在推理时基于实时数据动态生成和调整模型权重，挑战了传统“规模定律”的边界。
   - **链接:** http://arxiv.org/abs/2609.18842v1

##### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

6. **Compositional Policy Violations: When Step-Level Compliance Fails In Agentic AI Workflows**
   - **作者:** Ashwini Kurady, Sri Sai Charith Grandhi, Rajesh Gupta et al.
   - **一句话说明:** 指出当前AI工作流的治理仅关注单步合规，但在组合性策略（如预算限额、审批权限）面前会失效，为设计更稳健的智能体工作流监管机制敲响了警钟。
   - **链接:** http://arxiv.org/abs/2609.18820v1

7. **Taming the Agentic RAN: Stability-Guaranteed Arbitration of Autonomous AI Agents in O-RAN**
   - **作者:** Seyed Bagher Hashemi Natanzi, Bo Tang
   - **一句话说明:** 在真实O-RAN系统中演示了多个具有合理目标的自主AI智能体如何导致系统不稳定，并提出了一个保证稳定性的仲裁框架。
   - **链接:** http://arxiv.org/abs/2609.18857v1

8. **Flag Game: A Toy Model for Mechanistic Swarm Interpretability**
   - **作者:** Elizabeth Pavlova, Hidenori Tanaka
   - **一句话说明:** 引入了“旗帜游戏”作为研究多智能体涌现行为的简化模型，为从机制可解释性角度理解和对齐群体智能提供了可操作的新工具。
   - **链接:** http://arxiv.org/abs/2609.19124v1

9. **Beyond Outcomes: Dual-View Relational Learning for Efficient Agent Benchmarking**
   - **作者:** Xinshuai Guo, Junjie Wu, Dolly Deng et al.
   - **一句话说明:** 针对智能体评估成本高昂的问题，提出了一个基于双视图关系学习的基准压缩方法，能更有效地从任务-模型关系中找到代表性评估样本。
   - **链接:** http://arxiv.org/abs/2609.18909v1

##### 🔧 方法与框架（新技术、基准测试、效率优化）

10. **Exponential Hardness of Off-Policy Evaluation under History-Dependent Logging**
    - **作者:** Pranaya Jajoo
    - **一句话说明:** 证明了即使在历史依赖日志策略下收集的数据包含了所有隐藏状态，离策略评估在某些情况下依然具有指数级困难，对整个强化学习评估领域构成深刻挑战。
    - **链接:** http://arxiv.org/abs/2609.19135v1

11. **How Model Growth, Recursion, and Boundary Operators Influence Scaling Exponents**
    - **作者:** Zixi Chen, Akshay Vegesna, Samip Dahal et al.
    - **一句话说明:** 挑战了“缩放定律仅由计算量决定”的传统观点，证明架构选择（如深度、递归）可以改变缩放指数，带来指数级的性能提升。
    - **链接:** http://arxiv.org/abs/2609.19107v1

12. **Double descent is the principle of least action**
    - **作者:** Congzhou M Sha
    - **一句话说明:** 用统计力学中的“最小作用量原理”解释了机器学习中的“双重下降”现象，为理解和预测模型训练轨迹提供了统一的理论视角。
    - **链接:** http://arxiv.org/abs/2609.19076v1

13. **A General Kernel Framework for Non-CND Distance Measures Using |D|-Dimensional Sparse Landmark Embeddings**
    - **作者:** Marcus M. Noack, Maher B. Alghalayini, Mark D. Risser
    - **一句话说明:** 提出了一个通用核框架，通过稀疏地标嵌入，将原本无法用于高斯过程等核方法的非条件负定距离度量转换为可用形式，极大地扩展了核方法的适用范围。
    - **链接:** http://arxiv.org/abs/2609.19083v1

##### 📊 应用（垂直领域、多模态、代码生成）

14. **ScienceIDE: Turning World's Scientific Codebase into Agent Learnable Environments**
    - **作者:** Hejia Geng, Zesen Huang, Haoyang Li et al.
    - **一句话说明:** 提出了ScienceIDE，致力于将全球科学代码库转化为智能体可交互和学习的环境，有望大幅降低科学计算领域的壁垒，加速科学发现。
    - **链接:** http://arxiv.org/abs/2609.19134v1

15. **Prepared Or Unprepared? Evaluating Healthcare Workforce Readiness for Clinical Adoption of Artificial Intelligence in Nigeria**
    - **作者:** Abbas M. Rabiu, Abdulrazaq A. Zubair, Um-mulkhairi Ibrahim et al.
    - **一句话说明:** 评估了尼日利亚医疗工作者对AI临床应用的准备度，揭示了中低收入国家在AI医疗落地中面临的基础设施与培训鸿沟，提供了宝贵的现实世界案例。
    - **链接:** http://arxiv.org/abs/2609.19096v1

16. **ProgramDistill: From Interactive Web Apps to Verifiable Reference-Guided SWE Tasks**
    - **作者:** Jeonghye Kim, Minseon Kim, Young Jin Kim et al.
    - **一句话说明:** 提出了一个创新的软件工程基准测试，要求编码智能体从可工作的交互式Web应用中推断行为，并在不完整程序中复现，能更真实地评估其在现实世界开发中的能力。
    - **链接:** http://arxiv.org/abs/2609.18805v1

---

#### **研究趋势信号**

本周的论文透露出几个明确的趋势信号：**1) 从“对齐”到“治理”：** 研究焦点从让单个模型对齐人类偏好，转向管理多个自主智能体组成的复杂系统，确保其集体行为的合规与稳定。**2) 理论驱动的可解释性与安全性：** 越来越多的工作（如从Fisher-Rao几何、最小作用量原理）利用严谨的数学或物理工具来揭示模型训练和行为的底层机制，而不仅仅是进行实验验证。这增强了AI安全研究的可预测性和可靠性。**3) 科学发现的基础设施化：** 将科学代码、实验流程等转化为AI可学习和利用的环境（如ScienceIDE），正成为将AI深度融合到科学研究中的一个新方向。

---

#### **值得精读**

1. **Exponential Hardness of Off-Policy Evaluation under History-Dependent Logging**
   - **推荐理由:** 这篇理论论文证明了核心强化学习问题的一个基本困难，对现实世界中如何正确评估和部署策略有深远影响。结论简洁而有力，对任何从事RL应用的研究者都具有极高的警示和启发意义。

2. **Monitoring and Discovering Reward Hacking with Internal Representations during LLM Evaluations**
   - **推荐理由:** 直接面向当前最前沿的AI安全问题。它不仅仅指出问题，还提供了一种实用的、可操作的监控方法。结合了对模型内部机制的理解和实际应用价值，是该领域的一项重要进展。

3. **Preventing Model Collapse: A Fisher-Rao Perspective on the Dynamics of Training with Synthetic Data**
   - **推荐理由:** 随着合成数据的广泛使用，“模型崩溃”已成为紧迫问题。该文提供了最深刻的理论分析之一，深刻揭示了其背后的几何动力学原理，为设计更鲁棒的合成数据训练算法提供了关键洞见，具有重要的理论和实践价值。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*