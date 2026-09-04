# ArXiv AI 研究日报 2026-09-04

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-09-04 00:22 UTC

---

好的，作为AI研究分析师，以下是根据您提供的2026年9月4日ArXiv论文列表生成的《ArXiv AI 研究日报》。

---

### **ArXiv AI 研究日报 | 2026-09-04**

#### **今日速览**

今日投稿中，**LLM安全与对齐**成为最突出的主题，多篇论文揭示了模型在推理、用户交互和实际部署中的新漏洞与防御机制。同时，**智能体（Agent）** 的研究持续深化，从世界模型构建到多智能体博弈，再到高效评估，都取得了显著进展。此外，**模型效率与训练优化**依然是热点，探索了从新的低秩适应（LoRA）优化器到更稳定的低精度训练方法。值得注意的是，**AI for Science** 领域，特别是表格基础模型在物理规律学习上的局限性，以及AI在聚合物设计中的应用，展现了AI在科学发现中的深度探索。

---

#### **重点论文**

##### 🧠 **大语言模型（架构、训练、对齐、评估）**

1.  **The Implications of Linguistic Illegibility for LLM Security**
    - **作者**: James Mickens
    - **一句话说明**: 提出了“语言不可读性”概念，揭示LLM的内部计算可能与外部语言输出不一致，为利用非语言形式的内部表示进行攻击提供了新思路，是安全领域的重要新视角。
    - **链接**: [http://arxiv.org/abs/2609.02852v1](http://arxiv.org/abs/2609.02852v1)

2.  **Post-Training Language Models for Gold-Medal Performance in Coding Competitions**
    - **作者**: Aleksander Ficek et al.
    - **一句话说明**: 通过大规模问题策展、合成推理轨迹和强化学习，构建了一套端到端流水线，使模型在IOI、ICPC等顶级编程竞赛中达到金牌水平，是LLM推理能力的里程碑式突破。
    - **链接**: [http://arxiv.org/abs/2609.02849v1](http://arxiv.org/abs/2609.02849v1)

3.  **Language Models Can Control Their Own Attention**
    - **作者**: Namgyu Ho et al.
    - **一句话说明**: 提出让LLM学习控制自身注意力机制，在长上下文场景中，仅需扫描关键KV缓存而非全部上下文，大幅提升推理效率，是架构创新的巧妙思路。
    - **链接**: [http://arxiv.org/abs/2609.02737v1](http://arxiv.org/abs/2609.02737v1)

4.  **User Feedback Provides a Unique Signal that LLMs Can not Detect**
    - **作者**: Shachar Don-Yehiya et al.
    - **一句话说明**: 证明用户交互中的自然反馈信号（如编辑、重试）具有模型内部信号无法捕捉的独特价值，为利用用户行为数据改进LLM提供了理论依据。
    - **链接**: [http://arxiv.org/abs/2609.02859v1](http://arxiv.org/abs/2609.02859v1)

5.  **Door-in-the-Face Requests and Refusal Behaviour in Large Language Models**
    - **作者**: Til Jordan
    - **一句话说明**: 首次系统性测试了“门面技术”对LLM的影响，发现模型在拒绝一个不合理的大请求后，更可能接受一个较小的后续请求，揭示了LLM社会工程学风险。
    - **链接**: [http://arxiv.org/abs/2609.02707v1](http://arxiv.org/abs/2609.02707v1)

##### 🤖 **智能体与推理（规划、工具使用、多智能体、思维链）**

1.  **Discriminative World Models for Web Agents**
    - **作者**: Kelvin Li et al.
    - **一句话说明**: 提出判别式世界模型用于Web智能体，通过学习区分好的和坏的下一步状态，而非简单预测下一状态，显著提升了测试时行动选择的准确性。
    - **链接**: [http://arxiv.org/abs/2609.02885v1](http://arxiv.org/abs/2609.02885v1)

2.  **SafeEvolve: Harness-Policy Co-Evolution from Agent Experience for Safety Alignment**
    - **作者**: Qinghua Mao et al.
    - **一句话说明**: 提出一种创新的“安全共进化”框架，通过智能体与环境交互的经验，同步优化基础模型和安全策略（Harness），实现更鲁棒的安全对齐。
    - **链接**: [http://arxiv.org/abs/2609.02786v1](http://arxiv.org/abs/2609.02786v1)

3.  **Bilevel Coordinated Reflection: A Game-Theoretic Approach to Multi-Agent LLM Systems**
    - **作者**: Yihang Chen et al.
    - **一句话说明**: 用博弈论分析多智能体系统的协调与反思过程，为理解“编排者-工作者”架构提供了统一的理论框架，有助于设计更稳定、高效的协作智能体。
    - **链接**: [http://arxiv.org/abs/2609.02750v1](http://arxiv.org/abs/2609.02750v1)

4.  **CORAL: An LLM-Native Harness for Production Recommender Systems**
    - **作者**: Muhammad Rafay Azhar et al.
    - **一句话说明**: 将LLM作为智能体来驱动生产级推荐系统的持续优化，自动化测试不同召回、排序策略，展示了LLM在复杂系统运维中的巨大潜力。
    - **链接**: [http://arxiv.org/abs/2609.02730v1](http://arxiv.org/abs/2609.02730v1)

##### 🔧 **方法与框架（新技术、基准测试、效率优化）**

1.  **LoRA-TSD: Tangent-Space Spectral Descent for LoRA via Muon-Style Updates**
    - **作者**: Dmitrii Andriianov et al.
    - **一句话说明**: 提出LoRA-TSD优化器，在微调时考虑低秩权重更新的几何结构，利用Muon风格的更新进行切线空间谱下降，实现了更快的收敛和更好的性能。
    - **链接**: [http://arxiv.org/abs/2609.02734v1](http://arxiv.org/abs/2609.02734v1)

2.  **UE5M3 FP4 Block Scaling for Stable Language Model Pretraining**
    - **作者**: Robert Hu et al.
    - **一句话说明**: 通过创新的块级缩放策略，解决了4-bit浮点预训练的不稳定性问题，在保持低比特优势的同时，无需复杂的随机哈达玛变换，简化了低精度训练流程。
    - **链接**: [http://arxiv.org/abs/2609.02846v1](http://arxiv.org/abs/2609.02846v1)

3.  **oHC: Orthogonal Hyper-Connections on SO(4) via Quaternions**
    - **作者**: Haoqiang Guo et al.
    - **一句话说明**: 提出基于四元数的正交超连接，通过约束残差矩阵在SO(4)群上，避免了传统超连接可能导致信号爆炸的问题，为Transformer架构设计提供了新思路。
    - **链接**: [http://arxiv.org/abs/2609.02672v1](http://arxiv.org/abs/2609.02672v1)

4.  **EarlyEval: Cheaper Agent Evaluation via Early Outcome Prediction**
    - **作者**: Yuling Shi et al.
    - **一句话说明**: 提出一种高效智能体评估方法，通过预测任务早期结果来推断最终成败，从而大幅降低评估成本，对于迭代开发智能体至关重要。
    - **链接**: [http://arxiv.org/abs/2609.02783v1](http://arxiv.org/abs/2609.02783v1)

##### 📊 **应用（垂直领域、多模态、代码生成）**

1.  **CodePoisonRAG: Knowledge Poisoning Attacks on Retrieval-Augmented Code Generation**
    - **作者**: Varun Gadey et al.
    - **一句话说明**: 系统性地揭示了RAG代码生成的知识投毒攻击，展示了如何通过污染外部代码库来诱导模型生成带漏洞的代码，对RAG系统的安全性构成严峻挑战。
    - **链接**: [http://arxiv.org/abs/2609.02774v1](http://arxiv.org/abs/2609.02774v1)

2.  **Do Tabular Foundation Models Know Physics? Contamination, Units, and the Deterministic Limit**
    - **作者**: Wassim Tenachi et al.
    - **一句话说明**: 深度剖析了表格基础模型（TFMs）在物理知识上的局限，发现其预测能力主要源于数据污染而非对物理规律的理解，强调了在科学应用中验证模型鲁棒性的重要性。
    - **链接**: [http://arxiv.org/abs/2609.02766v1](http://arxiv.org/abs/2609.02766v1)

3.  **Untangling the Mechanisms of Misleading Context in Medical Question Answering**
    - **作者**: Robin Linzmayer et al.
    - **一句话说明**: 细致分析了误导性上下文如何影响LLM的医学问答，揭示了模型对特定类型误导信息的脆弱性，为构建更可靠的医疗AI提供了重要指导。
    - **链接**: [http://arxiv.org/abs/2609.02754v1](http://arxiv.org/abs/2609.02754v1)

4.  **RVSD: Retrieval Vision Sparse Decoding for Mitigating Visual Hallucinations in Large Vision-Language Models**
    - **作者**: Canjie Liu et al.
    - **一句话说明**: 提出一种无需训练的检索式视觉稀疏解码方法，通过检索相关视觉证据并引导模型稀疏解码，有效缓解了多模态大模型的视觉幻觉问题。
    - **链接**: [http://arxiv.org/abs/2609.02731v1](http://arxiv.org/abs/2609.02731v1)

---

#### **研究趋势信号**

- **LLM安全与可靠性成为绝对主流**：今日投稿中，超过1/4的论文直接或间接与LLM安全相关，从“语言不可读性”这种基础攻击面，到“门面技术”这类社会工程学漏洞，再到RAG知识投毒，研究视角已从“如何让模型更强大”转向“如何让模型更可靠、更安全”。
- **“内部状态”研究兴起**：多篇论文（如《The Implications of Linguistic Illegibility》、《Trace as State》）开始深入探索LLM的内部表示、注意力状态等“非语言”层面，将其视为新的攻击向量或优化目标，这标志着对LLM的理解进入了更深层次。
- **效率优化进入“几何”与“精度”并重阶段**：LoRA-TSD和oHC等论文表明，对微调过程（如低秩更新）的几何结构进行优化，与低精度训练（如FP4）一样，成为了提升效率的关键战场。

---

#### **值得精读**

1.  **《The Implications of Linguistic Illegibility for LLM Security》**：这篇论文提出的“语言不可读性”概念极具颠覆性，迫使整个社区重新思考什么是“理解”和“安全”。它可能开启一个全新的安全研究分支，即关注模型内部计算而非仅仅是输出。

2.  **《Language Models Can Control Their Own Attention》**：这篇论文思路巧妙且实用。在长上下文成为标配的今天，让模型学会如何分配注意力，从机制上解决了效率问题，其思路比单纯的KV缓存压缩更为优雅，具有很高的工程应用价值。

3.  **《oHC: Orthogonal Hyper-Connections on SO(4) via Quaternions》**：这篇论文在架构设计上展现了深厚的理论功底。通过将残差连接限制在正交群上，不仅解决了信号缩放问题，还为Transformer的“残差流”设计提供了新的理论视角，值得对架构设计感兴趣的读者深入研究。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*