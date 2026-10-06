# ArXiv AI 研究日报 2026-10-06

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-10-06 02:29 UTC

---

# ArXiv AI 研究日报 (2026-10-06)

## 今日速览

今日投稿聚焦于**持续学习与模型自我改进**——多篇论文探讨如何在不遗忘旧知识的前提下高效整合新数据，并提出了“离策略合并优于在策略自蒸馏”等颠覆性结论。**智能体安全与可解释性**是另一热点，多篇工作从博弈论、激活空间分析、红队测试等角度系统评估和提升LLM的鲁棒性与可靠性。此外，**长上下文推理与KV缓存压缩**、**多智能体协调**以及**低资源语言处理**也涌现了值得关注的新方法。

---

## 重点论文

### 🧠 大语言模型（架构、训练、对齐、评估）

**[1] Off-Policy Merging Beats On-Policy Self-Distillation for Continual Learning**  
链接：[http://arxiv.org/abs/2610.05872v1](http://arxiv.org/abs/2610.05872v1)  
作者：C. H. Wu, T. Zhang, A. Raghunathan  
一句话：证明了在持续学习中，将不同策略的模型参数合并（off-policy merging）优于传统的在策略自蒸馏，为模型持续自我提升提供了新范式。

**[2] Nash Equilibrium Text: A Game-Theoretic Decoding Framework for Text Generation**  
链接：[http://arxiv.org/abs/2610.05817v1](http://arxiv.org/abs/2610.05817v1)  
作者：A. Jafari, A. Adibi, M. Ghavamzadeh et al.  
一句话：将文本生成形式化为博弈论中的纳什均衡：每个token位置作为玩家，词汇作为动作，模型对数概率作为效用，从而在解码阶段实现全局一致性。

**[3] Don't Judge an LLM Only by Its Activations: Discovering Suppressed Safety Features via Counterfactual Activation Potential**  
链接：[http://arxiv.org/abs/2610.05541v1](http://arxiv.org/abs/2610.05541v1)  
作者：S. Swain, S. Dutta  
一句话：发现传统可解释性方法只关注激活的神经元，忽略了大量被抑制的特征；提出“反事实激活势”来揭示LLM中隐藏的安全相关特征。

**[4] Red-TTT: Test-Time Training for Automated Jailbreaking Large Language Models**  
链接：[http://arxiv.org/abs/2610.05282v1](http://arxiv.org/abs/2610.05282v1)  
作者：T. Hu, H. Li, X. Liu et al.  
一句话：通过测试时训练（TTT）自动生成越狱提示，比传统搜索或重写方法更高效地找到模型的脆弱点。

### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

**[5] DelegationBench: Measuring When AI Agents Should Ask Before Acting**  
链接：[http://arxiv.org/abs/2610.05532v1](http://arxiv.org/abs/2610.05532v1)  
作者：S. Pochampally  
一句话：针对AI代理何时该自主行动、何时该征求用户允许的问题，提出了新的基准测试和评估方法。

**[6] Expanding LLM Reasoning**  
链接：[http://arxiv.org/abs/2610.05584v1](http://arxiv.org/abs/2610.05584v1)  
作者：R. Atri, E. Luo  
一句话：研究了在已有推理链中从中间步骤重启动以增加推理计算量（而非采样多条链）的效果，定义了“扩展效用”指标。

**[7] DREAM: Dynamic Resolution Assignment For Multimodal Multi-agent Debate**  
链接：[http://arxiv.org/abs/2610.05615v1](http://arxiv.org/abs/2610.05615v1)  
作者：K.-B. Nguyen, V. D. Do, T. A. Nguyen et al.  
一句话：在多模态多智能体辩论中，动态为不同代理分配不同的视觉分辨率（而非固定输入），显著提升推理效果。

**[8] Safeguard Context Switching for Agents in the Wild: Mitigating Subspace Interference via Orthogonal Adaptation**  
链接：[http://arxiv.org/abs/2610.05219v1](http://arxiv.org/abs/2610.05219v1)  
作者：A. Das, I. Roy  
一句话：针对LLM在连续执行逻辑推理与安全对齐任务时的内部状态干扰问题，提出正交适配方法以保持两种能力的正交性。

### 🔧 方法与框架（新技术、基准测试、效率优化）

**[9] Spend Bytes on Breadth: Precision-Count Trade-offs for Decode-Time KV Compression in Long Chain-of-Thought Reasoning**  
链接：[http://arxiv.org/abs/2610.05685v1](http://arxiv.org/abs/2610.05685v1)  
作者：R. Li  
一句话：在长思维链解码场景下，探讨了固定内存预算应如何分配给“缓存更多token（广度）”与“保留更高精度（精度）”之间的最优权衡。

**[10] What Is a Repeated Token Worth? The Scaling Geometry of Multi-Epoch Pretraining**  
链接：[http://arxiv.org/abs/2610.05591v1](http://arxiv.org/abs/2610.05591v1)  
作者：Y. Chai, H. Xiong  
一句话：通过定价重复token的边际价值，回答了多epoch预训练中“训练多少epoch”、“epoch数如何随模型大小变化”等关键缩放定律问题。

**[11] Universal Test-Time Training**  
链接：[http://arxiv.org/abs/2610.05484v1](http://arxiv.org/abs/2610.05484v1)  
作者：Z. Cai, Q. Hu, Z. Ma et al.  
一句话：提出“通用测试时训练”框架，打破传统TTT中每层记忆私有的局限，让记忆跨层共享，提升长上下文建模能力。

**[12] FORGE: Verification-Gated Behavioral Repair for Generative Language Models**  
链接：[http://arxiv.org/abs/2610.05190v1](http://arxiv.org/abs/2610.05190v1)  
作者：H.-L. Hsu, M.-Y. Chen, N.-C. Chen et al.  
一句话：针对生成式LLM的偏见、有毒输出等缺陷，提出基于验证门控的行为修复方法，能在消除问题的同时保持模型整体功能。

### 📊 应用（垂直领域、多模态、代码生成）

**[13] MedicalHarness: A Controlled Evaluation of LLMs and Agent Harnesses on Medical Tasks**  
链接：[http://arxiv.org/abs/2610.05778v1](http://arxiv.org/abs/2610.05778v1)  
作者：Z. Wang, L. Zhao, K. Ding  
一句话：指出在医学任务上，LLM的得分高度依赖于其所在的agent harness系统（提示、解析器、工具调用等），对现有基准分数提出质疑。

**[14] VHDL-REPOBENCH: A Repository-Level Benchmark for Evaluating Large Language Models on VHDL Design Generation**  
链接：[http://arxiv.org/abs/2610.05380v1](http://arxiv.org/abs/2610.05380v1)  
作者：P. Vijayaraghavan, A. Malhotra, A. Jadhav et al.  
一句话：首个仓库级别的VHDL代码生成基准，填补了硬件描述语言领域（除Verilog外）在LLM评估上的空白。

**[15] Verification Trap: Understanding Test-Time Selection Failures under False Premises in Code Generation**  
链接：[http://arxiv.org/abs/2610.05170v1](http://arxiv.org/abs/2610.05170v1)  
作者：F. He, H. Wang, L. Meng et al.  
一句话：揭示了代码生成中测试时选择的“验证陷阱”——当验证器本身依赖于生成器的输出时，两个组件之间的独立性假设被打破，导致选择失败。

---

## 研究趋势信号

1. **“自我改进”的实证颠覆**：多篇论文（如#1、#40、#41）质疑了传统在策略蒸馏或固定训练范式的优越性，探索通过参数合并、发现-执行分解、对抗演化等方式实现更高效的模型自我提升。
2. **从“激活”到“抑制”的可解释性**：传统机制解释聚焦于激活的特征，而#23和#48等工作开始关注被抑制或正交化的特征空间，揭示安全与推理之间的内在权衡。
3. **Agent评估的“Harness”依赖**：同时出现多篇论文（#8、#26、#35）指出LLM在代理框架中的表现与外围系统（提示、解析器、工具）强耦合，呼吁对“harness”本身进行标准化和审计。
4. **长上下文推理的资源分配理论**：针对KV缓存压缩、多epoch训练、扩展推理等方向，开始出现严谨的资源-收益定量分析（#12、#18、#40），而非仅凭经验调参。

---

## 值得精读

1. **《Off-Policy Merging Beats On-Policy Self-Distillation for Continual Learning》**（#1）  
   ——挑战了当前持续学习的主流做法（在策略自蒸馏），实验证据充分，可能改变未来模型更新与融合的实践方向。

2. **《Nash Equilibrium Text: A Game-Theoretic Decoding Framework for Text Generation》**（#4）  
   ——将博弈论引入解码阶段，提供了一个全新的形式化视角；如果验证有效，有望在生成质量和对齐性上产生突破。

3. **《DelegationBench: Measuring When AI Agents Should Ask Before Acting》**（#5）  
   ——直接触及自主代理实际部署中的核心矛盾（信任-控制权衡），提出的基准和评估方法对Agent安全落地具有直接指导意义。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*