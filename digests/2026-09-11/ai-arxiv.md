# ArXiv AI 研究日报 2026-09-11

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-09-11 00:31 UTC

---

好的，以下是为您生成的《ArXiv AI 研究日报》（2026-09-11），基于您提供的50篇论文。

---

## ArXiv AI 研究日报 — 2026年9月11日

### 今日速览

今天投稿中，**实现缺口基准（IdeaAMBIG）** 首次系统衡量研究思路到可执行代码之间的距离，为AI辅助科研提供关键评估工具；**生成式物理模型**（Semigroup-JEPA）在零样本物理泛化上取得突破，有望提升世界模型的可信度；**强化学习与因果推理**的结合（TRACE）为复杂诊断场景中的推理智能体提供了可扩展的训练范式；此外，**视觉token剪枝**、**KV缓存共享**等效率优化方向持续涌现，而**AI供应商金融传染模型**则凸显了系统级安全的新视角。

---

### 重点论文

#### 🧠 大语言模型（架构、训练、对齐、评估）

1. **IdeaAMBIG: Benchmarking Implementation-Critical Gaps in Research-Idea Specifications**  
   [http://arxiv.org/abs/2609.10539v1](http://arxiv.org/abs/2609.10539v1)  
   Y. Ma, Y. Zhao, S. Wu et al.  
   **一句话说明**：提出首个衡量研究思路中“实现缺口”的基准，检测方法论描述是否足以让AI忠实地复现代码，对AI辅助科研与可复现性建设意义重大。

2. **ConvMem: Convolutional Memory for Long-Context Reasoning**  
   [http://arxiv.org/abs/2609.10441v1](http://arxiv.org/abs/2609.10441v1)  
   H. Zhang, Z. Gu, F. Bai et al.  
   **一句话说明**：引入卷积记忆机制扩展LLM有效上下文长度，将长文本分段编码并迭代压缩，在记忆效率与检索精度间取得更好平衡。

3. **Forgetting Only What Matters: Layer-Selective Unlearning toward Robust LLMs**  
   [http://arxiv.org/abs/2609.10439v1](http://arxiv.org/abs/2609.10439v1)  
   R. Ranjan, O. Kotevska, A. Polyzou  
   **一句话说明**：提出层选择性遗忘方法，针对不同层的关键性动态决定遗忘幅度，既移除敏感数据又不损伤模型通用能力。

4. **From Symbolic Perception to Logical Deduction: A Framework for Guiding Language Models in Geometric Reasoning**  
   [http://arxiv.org/abs/2609.10335v1](http://arxiv.org/abs/2609.10335v1)  
   W. Dai, R. M. Cabral, Z. Shou et al.  
   **一句话说明**：证明纯LLM通过符号感知模块将几何图形转化为形式化逻辑输入后，可进行可解释的几何定理推导，避免昂贵多模态模型。

5. **GANDR: Claim Auditing for Verifiable Legal Answer Generation**  
   [http://arxiv.org/abs/2609.10293v1](http://arxiv.org/abs/2609.10293v1)  
   C. Qian, Y. Wang, Y. Chen et al.  
   **一句话说明**：面向法律领域的可验证生成框架，对LLM输出的每个声明进行溯源审计，确保结论能够逐句核对原文，显著提升高可信场景下的可用性。

#### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

6. **Show-Harness: Just a VLM Agent Can Play Robots**  
   [http://arxiv.org/abs/2609.10522v1](http://arxiv.org/abs/2609.10522v1)  
   Y. Chen, Z. Bai, Z. Cao et al.  
   **一句话说明**：提出“表现-操控”接口，使视觉-语言模型（VLM）能直接作为智能体端到端控制机器人，无需精细编程，实践了“只看一次”的零样本泛化。

7. **JarvisGUI: Towards Cross-Device GUI Agents with Dynamic Task Composition**  
   [http://arxiv.org/abs/2609.10451v1](http://arxiv.org/abs/2609.10451v1)  
   Z. Chen, Y. Lu, Z. Cheng et al.  
   **一句话说明**：构建支持跨设备（手机、电脑、智能家居）图形界面操作的单智能体系统，通过动态任务组合处理多步协同工作流，填补现有GUI基准的单设备局限。

8. **TRACE: Training Reasoning Agents for Causal Exploration with Synthesized Rewards**  
   [http://arxiv.org/abs/2609.10315v1](http://arxiv.org/abs/2609.10315v1)  
   R. Sun, Z. Shi, B. He  
   **一句话说明**：将可验证奖励（RLVR）扩展到因果推理领域，通过合成奖励训练语言模型智能体进行多步诊断探索，在复杂异常定位任务上显著优于纯语言推理。

#### 🔧 方法与框架（新技术、基准测试、效率优化）

9. **A positive resolution of the gap-entropy conjecture**  
   [http://arxiv.org/abs/2609.10529v1](http://arxiv.org/abs/2609.10529v1)  
   P. M. Aronow, N. Kallus, P. Lopatto  
   **一句话说明**：证明了固定置信度最佳臂识别中的gap-entropy猜想（高斯臂情形），为基础性的统计学习下界提供了严格解答，影响强化学习中的探索-利用理论。

10. **Semigroup-JEPA: Latent Dynamics Consistency for Zero-Shot Physics Generalization**  
    [http://arxiv.org/abs/2609.10464v1](http://arxiv.org/abs/2609.10464v1)  
    A. Z. Liu, H. Sun, L. Baker et al.  
    **一句话说明**：在JEPA框架中引入半群结构一致性约束，使世界模型在训练时学习物理不变的潜在动力学，首次实现零样本泛化到未见物理参数下的轨迹预测。

11. **PACE: Perceived-Latency-Aware Cascading Service Routing and Filler Control for QoE-Efficient Retrieval-Augmented Dialogue Serving**  
    [http://arxiv.org/abs/2609.10372v1](http://arxiv.org/abs/2609.10372v1)  
    L. Huang, Y. Tan, W. Li et al.  
    **一句话说明**：提出在RAG对话服务中将“用户感知响应前时间”作为QoE目标，通过级联路由与填充内容控制，在保证质量的同时大幅削减端到端延迟。

12. **Beyond One-Size-Fits-All: Sample-Adaptive Strategy Routing for Vision Token Pruning in MLLMs**  
    [http://arxiv.org/abs/2609.10346v1](http://arxiv.org/abs/2609.10346v1)  
    H. Liang, P. Zhou, Z. Wan et al.  
    **一句话说明**：针对多模态大模型视觉token冗余问题，提出样本自适应剪枝策略路由，根据图像复杂度动态选择剪枝方案，较静态剪枝方法推理速度提升近2倍且精度保持。

#### 📊 应用（垂直领域、多模态、代码生成）

13. **OmniMed-FL: A Robust Multimodal Federated Learning Framework for Clinical Diagnosis**  
    [http://arxiv.org/abs/2609.10364v1](http://arxiv.org/abs/2609.10364v1)  
    A. Debnath, R. Saha, S. Misra  
    **一句话说明**：面向医学影像与病历联合诊断的隐私保护联邦学习框架，在处理多模态异构数据下达到与集中训练相当的诊断精度，同时满足HIPAA/GDPR合规。

14. **Cyber-Financial Contagion: Modeling the Propagation of an AI Vendor Compromise Through the Banking System**  
    [http://arxiv.org/abs/2609.10350v1](http://arxiv.org/abs/2609.10350v1)  
    A. Leytes  
    **一句话说明**：首次建立AI供应商被攻破后在银行系统内传播的金融传染模型，揭示中心化AI服务依赖带来的系统性风险，为金融监管提供定量分析工具。

---

### 研究趋势信号

今日投稿中涌现出多个新兴方向：（1）**“实现缺口”基准化**——不仅评估模型输出的准确性，更衡量其是否足以指导物理执行（如IdeaAMBIG、Retrofitting code）；（2）**物理常识的零样本泛化**——Semigroup-JEPA等试图让世界模型学到真正可迁移的物理定律；（3）**因果推理与强化学习的系统化结合**——TRACE等探索在复杂数据下以合成奖励训练智能体进行多步因果诊断；（4）**基础设施层安全研究深化**——从KV缓存共享到AI供应商金融传染，系统性风险建模进入AI安全视野；（5）**小模型/参数高效方法回归**——RiLM（<1M参数）等挑战“越大越好”假设，关注边缘部署与可复现性。

---

### 值得精读

1. **IdeaAMBIG**（论文1）：首次聚焦“研究思路→可执行代码”之间的鸿沟，将学术论文中的方法论描述转化为可自动化检验的规范缺口，对AI辅助科研、论文评审和减少重复劳动具有基础性意义。

2. **Semigroup-JEPA**（论文10）：在无监督世界模型学习中引入半群结构，赋予模型零样本物理泛化能力，是走向“物理AI”的关键一步，若可规模扩展将深刻影响机器人操纵与自动驾驶。

3. **Show-Harness**（论文6）：极简而优雅的方案——仅通过视觉-语言模型的语义接口就能驱动机器人，省略了耦合的精细规划模块，展现了VLM作为通用智能体的巨大潜力，结果非常启发人。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*