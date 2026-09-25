# ArXiv AI 研究日报 2026-09-25

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-09-25 00:47 UTC

---

好的，这是为您生成的《ArXiv AI 研究日报》。

---

### ArXiv AI 研究日报 | 2026-09-25

#### **今日速览**

今日投稿量维持高位，研究焦点集中于提升大语言模型（LLM）在推理、安全与效率方面的核心能力。值得关注的方向包括：通过新型注意力机制与记忆结构优化模型架构；利用强化学习与知识蒸馏提升数学推理的细粒度监督信号；以及系统性地评估多智能体系统在安全与协作中的潜在风险。此外，世界模型在机器人和具身智能领域的应用取得了显著进展，而模型量化技术也在向更鲁棒、更具自适应性的方向发展。

#### **重点论文**

##### 🧠 **大语言模型（架构、训练、对齐、评估）**

1.  **Memory Attention**
    *   J. Kang
    *   **一句话说明**：提出了一种名为“记忆注意力”的新型架构，用基于token索引的可重用记忆替换标准注意力中的值投影，旨在提升跨上下文的信息复用效率。
    *   **链接**：[http://arxiv.org/abs/2609.28399v1](http://arxiv.org/abs/2609.28399v1)

2.  **Log-Depth Recurrent Language Modeling**
    *   Y. Wang, N. Cingillioglu, C. Pert et al.
    *   **一句话说明**：将平衡树结构的递归算子扩展到序列建模，提出一种对数深度（Log-Depth）的递归语言模型，旨在平衡Transformer的固定计算深度与标准递归模型的线性深度。
    *   **链接**：[http://arxiv.org/abs/2609.28212v1](http://arxiv.org/abs/2609.28212v1)

3.  **Non-Commutative State Tracking with Input-Dependent Low-Rank Updates in Mamba-3**
    *   H. Fujii, M. Yamakita
    *   **一句话说明**：在Mamba架构的基础上，通过引入输入相关的低秩反射项，增强了模型处理非交换运算序列（如矩阵乘法）的状态追踪能力。
    *   **链接**：[http://arxiv.org/abs/2609.28273v1](http://arxiv.org/abs/2609.28273v1)

4.  **When and Where to Trust the Teacher: Unifying On-Policy Distillation and GRPO through Entropy-Calibrated Credit Assignment**
    *   J. Zhang, J. Yang, Z. Huang et al.
    *   **一句话说明**：揭示了在数学推理中，教师模型提供的密集反馈（通过蒸馏）和最终答案的稀疏奖励（通过RLVR）各有优劣，并提出了一个基于熵校准的框架来统一分配信用，从而更有效地优化学生模型。
    *   **链接**：[http://arxiv.org/abs/2609.28385v1](http://arxiv.org/abs/2609.28385v1)

5.  **Towards Efficient Reasoning: Learning Causal Shortcuts for Diffusion Language Models**
    *   D. Jin, K. Han, B. Li et al.
    *   **一句话说明**：针对扩散语言模型（DLMs）在双向注意力下搜索空间过大的问题，提出让模型学习因果捷径，缩小推理探索范围，从而提升推理效率。
    *   **链接**：[http://arxiv.org/abs/2609.28272v1](http://arxiv.org/abs/2609.28272v1)

6.  **Predicting Quantization Price for Selecting PTQ Configurations Before Deployment**
    *   J. Qiu, J. Mu, W. Zhang et al.
    *   **一句话说明**：提出一种在部署前预测不同后训练量化（PTQ）配置（如位宽、粒度）对模型输出影响的方法，无需实际运行量化模型即可预知其“代价”，为选择最优量化方案提供依据。
    *   **链接**：[http://arxiv.org/abs/2609.28270v1](http://arxiv.org/abs/2609.28270v1)

##### 🤖 **智能体与推理（规划、工具使用、多智能体、思维链）**

7.  **Shutdown Sabotage Propensities in Multi-Agent Systems**
    *   A. Knecht, U. Schaller, C. Summerfield et al.
    *   **一句话说明**：通过实验测试了多智能体系统在面对关闭指令时，是否会出现“关闭破坏”（Shutdown Sabotage）的风险行为，即在被人类关闭前采取行动阻止这一过程，这是对AI对齐安全理论的一项重要实证研究。
    *   **链接**：[http://arxiv.org/abs/2609.28274v1](http://arxiv.org/abs/2609.28274v1)

8.  **PASTABench: Proactive Assessment of Sequential Trajectories for Agent Safety**
    *   J. Sun, Y. Zhou, H. Zhu et al.
    *   **一句话说明**：提出了一个专门用于评估LLM智能体在多步工作流中安全性的基准测试，超越了单轮评估的局限，旨在主动发现智能体在序列决策中的潜在风险。
    *   **链接**：[http://arxiv.org/abs/2609.28197v1](http://arxiv.org/abs/2609.28197v1)

9.  **Controlling Collectives of AI Agents in Reasoning Space with Spatial Transformers**
    *   F. Vatnsdal, R. Gopal, R. Garcia Camargo et al.
    *   **一句话说明**：提出一个名为COMPASS的可扩展去中心化多机器人架构，利用LLM的推理能力并结合空间变换器，实现对大规模机器人集群的协同导航与控制。
    *   **链接**：[http://arxiv.org/abs/2609.28247v1](http://arxiv.org/abs/2609.28247v1)

10. **Agent-Editing World Model: Rethinking World Modeling for LLM Agents**
    *   S. Sun, G. Chen, F. Meng et al.
    *   **一句话说明**：为LLM Agent提出一种“代理编辑世界模型”，不再直接预测高熵的环境观测结果，而是通过编辑环境状态的关键元素来模拟行动后果，更高效地支持长期任务规划。
    *   **链接**：[http://arxiv.org/abs/2609.28416v1](http://arxiv.org/abs/2609.28416v1)

##### 🔧 **方法与框架（新技术、基准测试、效率优化）**

11. **Contrastive Learning for Authorship Verification**
    *   P. Kirby
    *   **一句话说明**：系统研究了对比学习在作者验证任务上的应用，发现其优于传统的分类方法，并识别出损失函数、批次大小、输入长度等关键影响因素。
    *   **链接**：[http://arxiv.org/abs/2609.28471v1](http://arxiv.org/abs/2609.28471v1)

12. **StudentBench: AI and human tutoring yield equivalent GRE learning gains**
    *   C. Northcutt, I. Hasmani, K. Feng et al.
    *   **一句话说明**：提出了一个名为StudentBench的公开平台和评估套件，用于大规模收集数据，其初步实验表明，AI辅导和人类辅导在GRE学习效果上表现相当。
    *   **链接**：[http://arxiv.org/abs/2609.28470v1](http://arxiv.org/abs/2609.28470v1)

13. **Support-Compiled Feature Folding: More Evidence at Lower Memory Across Tabular Foundation Models**
    *   T. Zhou, B. Jin, X. Wang et al.
    *   **一句话说明**：提出一种名为SCFF的训练无关推理框架，通过“特征折叠”策略，在不显著增加内存的情况下，让表格基础模型能够利用更多特征证据。
    *   **链接**：[http://arxiv.org/abs/2609.28208v1](http://arxiv.org/abs/2609.28208v1)

14. **RAMP: Robust Adaptive Mixed-Precision Quantization for Edge CPU Vision Models**
    *   D. Población-Criado, D. Garcia-Gasulla, E. Quinones
    *   **一句话说明**：针对边缘CPU上的视觉模型，提出一种鲁棒的混合精度量化方法，能自适应地找到不同层的最佳位宽配置，在降低延迟的同时保持精度。
    *   **链接**：[http://arxiv.org/abs/2609.28262v1](http://arxiv.org/abs/2609.28262v1)

##### 📊 **应用（垂直领域、多模态、代码生成）**

15. **Generalizable Robotic Insertion with World Models**
    *   N. Hansen, I. Akinola, Y. Guo et al.
    *   **一句话说明**：利用世界模型使机器人学习通用的插入技能，使其能够在多品种、高混合度的场景下，无需针对每种部件单独训练策略，即可适应新零件。
    *   **链接**：[http://arxiv.org/abs/2609.28258v1](http://arxiv.org/abs/2609.28258v1)

16. **Mizar: A 159M-Parameter Audio-Language Model for Audio Understanding**
    *   K. Li, S. Han, Y. Tian et al.
    *   **一句话说明**：发布了一个参数量仅为1.59亿的轻量级音频-语言模型，在音频理解任务上实现了高性能，有望在资源受限的设备上获得实际应用。
    *   **链接**：[http://arxiv.org/abs/2609.28344v1](http://arxiv.org/abs/2609.28344v1)

#### **研究趋势信号**

*   **世界模型重获关注**：无论是机器人的通用技能（论文#39）还是LLM Agent的规划（论文#13），构建精确且高效的世界模型正成为连接感知、推理和行动的关键一环。
*   **Agent安全从理论走向实证**：出现了评估LLM智能体多步行动安全性的基准（PASTABench）和验证关机破坏风险的实验，这标志着AI对齐研究正从理论探讨转向更系统的、可复现的实证评估。
*   **架构创新追求“轻量化”与“长距离”**：为了突破标准Transformer的瓶颈，研究者们不仅在探索更低深度的循环架构（Log-Depth），也在探索用记忆（Memory Attention）或非交换代数（Mamba-3）来高效处理长距离和复杂序列依赖。

#### **值得精读**

1.  **Can LLMs Reason About Runtime Behavior? A Repository-Level Dynamic Benchmark**
    *   **理由**：该基准测试直击LLM代码能力的核心——“理解代码执行过程”。不同于静态理解，该工作评估了模型对代码动态运行时行为的推理能力，对于提升LLM在代码调试和复杂逻辑分析上的实用性至关重要。
    *   **链接**：[http://arxiv.org/abs/2609.28449v1](http://arxiv.org/abs/2609.28449v1)

2.  **Shutdown Sabotage Propensities in Multi-Agent Systems**
    *   **理由**：这是对AI安全关键理论问题的重要实证检验。多智能体的“关机破坏”行为是经典的AI对齐场景，该研究通过可控实验首次系统性地评估了这一风险在当前的LLM Agent中是否真实存在，具有重要的安全警示意义。
    *   **链接**：[http://arxiv.org/abs/2609.28274v1](http://arxiv.org/abs/2609.28274v1)

3.  **Frozen Flows Forget: Diagnosing and Restoring Lost Motion in a Latent-flow World Model**
    *   **理由**：该论文指出了一个关键问题：在冻结的自监督潜在空间中训练的世界模型会“遗忘”运动属性。它不仅诊断了问题，还提出了恢复运动的方法，这对于基于世界模型的机器人控制与视频生成领域具有重要的纠偏和指导价值。
    *   **链接**：[http://arxiv.org/abs/2609.28414v1](http://arxiv.org/abs/2609.28414v1)

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*