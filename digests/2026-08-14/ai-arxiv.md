# ArXiv AI 研究日报 2026-08-14

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-08-13 23:22 UTC

---

好的，这是为您生成的《ArXiv AI 研究日报》。

---

## ArXiv AI 研究日报 — 2026-08-14

### 今日速览

今日投稿中，**智能体与推理**领域表现尤为活跃，多项研究聚焦于提升智能体的规划能力、视频理解与工具使用效率，尤其是“测试时”的优化策略成为热点。同时，**多模态与视频理解**方面，针对视频生成和导航的智能体原生表示学习取得进展。此外，**大语言模型的基础研究**也贡献了重要发现，包括强到弱能力转移的新视角、长上下文训练对模型参数知识的潜在负面影响，以及计算预算对模型评估排序的颠覆性影响。最后，**代码生成与安全**领域，专门针对电路网表和代码漏洞的基准测试发布，为评估LLM在专业领域的可靠性提供了新工具。

### 重点论文

#### 🧠 大语言模型（架构、训练、对齐、评估）

- **AI4AI at Test-Time: Strong-to-Weak Capability Transfer via Harnesses**
  - 作者: Cheng Qian et al.
  - 一句话说明：提出了一种**测试时**的强到弱模型能力转移方法，通过“约束”机制让大模型在推理时指导小模型，无需更新参数，开辟了知识蒸馏的新范式。
  - [http://arxiv.org/abs/2608.12307v1](http://arxiv.org/abs/2608.12307v1)

- **Information Abundance Paradox: Long-Context Training Undermines Parametric Knowledge**
  - 作者: Arda Uzunoglu et al.
  - 一句话说明：挑战了长上下文训练“越多越好”的假设，发现训练时使用过长上下文反而会损害模型在其参数中存储的知识，揭示了“信息丰富悖论”。
  - [http://arxiv.org/abs/2608.12218v1](http://arxiv.org/abs/2608.12218v1)

- **Who Thinks Best Depends on How Long You Let Them: Budget-Dependent Rankings in LLM Evaluation**
  - 作者: Rodrigo Guedes de Souza et al.
  - 一句话说明：揭示了模型评估中的一个关键漏洞：**模型排名会随token生成预算（最大输出长度）的变化而改变**，质疑了当前静态评估标准的可靠性。
  - [http://arxiv.org/abs/2608.12150v1](http://arxiv.org/abs/2608.12150v1)

- **Massive Activations in Hybrid Linear Attention Large Language Models**
  - 作者: Zunhai Su et al.
  - 一句话说明：首次系统研究了混合线性注意力LLM中的“大规模激活”现象，发现了其独特的、与架构对齐的形态模式，为理解高效注意力模型的行为提供了新视角。
  - [http://arxiv.org/abs/2608.12149v1](http://arxiv.org/abs/2608.12149v1)

#### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

- **AVA-Encoder: Towards Agent-Native Video Representation Learning**
  - 作者: Chuyue Li et al.
  - 一句话说明：为智能体设计了一种“原生”视频表示学习方法，旨在将高质量电影的结构化知识直接用于智能体的推理和操作，解锁创意视频生成新能力。
  - [http://arxiv.org/abs/2608.12313v1](http://arxiv.org/abs/2608.12313v1)

- **DreamFly: Causal Memory and Receding-Horizon Diffusion Planning for Aerial Vision-Language Navigation**
  - 作者: Yan Deng et al.
  - 一句话说明：针对空中视觉-语言导航任务，提出融合因果记忆与滚动时域扩散规划的新框架，解决了部分可观测环境下的长期规划和动作终止判断问题。
  - [http://arxiv.org/abs/2608.12308v1](http://arxiv.org/abs/2608.12308v1)

- **VAKRA: Evaluating Multi-Hop Reasoning Across APIs and Retrieval Under Tool-Use Policies**
  - 作者: Ankita Rajaram Naik et al.
  - 一句话说明：发布了首个融合**结构化API调用**与**非结构化知识检索**的多跳推理基准测试，精准评估企业级智能体在复杂工具使用策略下的能力。
  - [http://arxiv.org/abs/2608.12282v1](http://arxiv.org/abs/2608.12282v1)

- **SCOUT: Unlocking Enhanced Spatial Reasoning via Structured Chain-of-Thought and Multi-Objective Process Reward**
  - 作者: Zile Zhou et al.
  - 一句话说明：通过结构化思维链和多目标过程奖励模型，显著提升了视觉语言模型在**空间推理**任务上的表现，为解决强化学习中的信用分配问题提供了新思路。
  - [http://arxiv.org/abs/2608.12220v1](http://arxiv.org/abs/2608.12220v1)

#### 🔧 方法与框架（新技术、基准测试、效率优化）

- **A Framework for Designing Reward Functions: From Objectives to Features to Human-Aligned Reward Functions**
  - 作者: Di Yang Shi et al.
  - 一句话说明：为非专家用户提供了一个**设计符合人类偏好的奖励函数**的正式流程，将自然语言任务描述转化为可用的线性奖励函数，降低了RL应用门槛。
  - [http://arxiv.org/abs/2608.12302v1](http://arxiv.org/abs/2608.12302v1)

- **Redistribution-based Cost Inference Improves Sparse Safe Offline RL**
  - 作者: Ebenezer Gelo et al.
  - 一句话说明：针对安全离线强化学习中成本信号极其稀疏（仅轨迹级）的难题，提出通过**重分配推断**成本的方法，有效解决了时序信用分配问题。
  - [http://arxiv.org/abs/2608.12306v1](http://arxiv.org/abs/2608.12306v1)

- **One Frozen Simulator Is Not Enough: Simulator Collapse in Multi-Agent RL**
  - 作者: Simon Yu et al.
  - 一句话说明：揭示了多智能体强化学习中一个关键失败模式“**模拟器崩溃**”：使用单一LLM模拟用户行为会导致策略泛化失败，强调需要多样化的模拟环境。
  - [http://arxiv.org/abs/2608.12253v1](http://arxiv.org/abs/2608.12253v1)

- **VICBench: A Multi-Language Benchmark for Code Vulnerability Detection**
  - 作者: Jin Lu et al.
  - 一句话说明：发布了**多语言**代码漏洞检测基准测试VICBench，专注于识别“首次引入漏洞的提交”，为评估安全工具提供更精确的指标。
  - [http://arxiv.org/abs/2608.12246v1](http://arxiv.org/abs/2608.12246v1)

- **NetlistBench: Evaluating LLM Reliability in SPICE Netlist Recognition and Manipulation**
  - 作者: Jiarui Ma et al.
  - 一句话说明：构建了专门评估LLM在**电路网表**识别与操作可靠性的基准，测试其在面对纯文本形式但具有复杂结构约束的电路描述时的表现。
  - [http://arxiv.org/abs/2608.12197v1](http://arxiv.org/abs/2608.12197v1)

#### 📊 应用（垂直领域、多模态、代码生成）

- **Beyond Trial-and-Error: Agentic Optimization for Image-to-Video Adherence**
  - 作者: Aman Tyagi et al.
  - 一句话说明：将图像到视频生成变成一个**智能体优化问题**，通过自动调整提示词和超参数来提升生成视频对输入图像的保真度，省去了人工试错。
  - [http://arxiv.org/abs/2608.12290v1](http://arxiv.org/abs/2608.12290v1)

- **HAI for AI at Test-Time: Strong-to-Weak Capability Transfer via Harnesses**
  - 作者: Cheng Qian et al.
  - 一句话说明：（同前）该工作因其在测试时进行能力转移的新颖性，在应用层面也具有巨大潜力，例如在资源受限设备上部署强大模型的能力。
  - [http://arxiv.org/abs/2608.12307v1](http://arxiv.org/abs/2608.12307v1)

- **An Agentic Workflow for Legacy HPC Modernization: Converting the Two-Electron-Integral Core of GAMESS**
  - 作者: Yuzhong Shen et al.
  - 一句话说明：展示了**智能体工作流**在现代化大型科学计算代码（如Fortran写的GAMESS）中的实际应用，将繁琐的代码转换任务自动化，是AI for Science基础设施的典范。
  - [http://arxiv.org/abs/2608.12249v1](http://arxiv.org/abs/2608.12249v1)

### 研究趋势信号

今日投稿中一个显著的趋势是“**测试时优化**”的兴起。无论是通过“约束”机制进行强到弱的能力转移（AI4AI），还是通过智能体搜索优化图像生成（Beyond Trial-and-Error），研究者们正越来越多地将计算资源从训练阶段转移到推理阶段，以更灵活、更高效的方式提升模型能力。另一个值得关注的信号是**对现有评估范式的反思**，例如挑战长上下文训练的有效性（Information Abundance Paradox），以及揭示评估中因计算预算不同导致的排名波动（Budget-Dependent Rankings），这预示着未来AI模型评估将更加精细化和情境化。

### 值得精读

1.  **AI4AI at Test-Time: Strong-to-Weak Capability Transfer via Harnesses**
    - **理由**：该研究提出了一个极具颠覆性的概念——测试时知识蒸馏，可能彻底改变大模型部署和应用的格局。对于那些关心模型效率、隐私和部署成本的读者来说，这是必读之作。

2.  **Information Abundance Paradox: Long-Context Training Undermines Parametric Knowledge**
    - **理由**：这篇论文挑战了当前行业普遍追求的“长上下文”趋势，提出了一个严肃的、反直觉的发现。理解这个“悖论”对于未来LLM的架构设计、训练策略和数据选择至关重要。

3.  **One Frozen Simulator Is Not Enough: Simulator Collapse in Multi-Agent RL**
    - **理由**：该工作揭示了多智能体系统中的一个关键失败模式，这对于任何构建或使用基于LLM的多智能体系统（如模拟、游戏、机器人）的研究者和开发者都具有重要的警示和启发意义。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*