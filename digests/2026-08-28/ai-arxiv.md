# ArXiv AI 研究日报 2026-08-28

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-08-28 06:19 UTC

---

好的，作为 AI 研究分析师，我已根据您提供的 2026-08-28 的 ArXiv 论文列表，为您整理出以下《ArXiv AI 研究日报》。

---

### **ArXiv AI 研究日报 | 2026-08-28**

#### **今日速览**

今日研究呈现三大核心趋势：**推理时计算与智能体自主进化**成为最热门的交叉领域，多篇论文探索如何在不依赖外部验证或大量人工标注的情况下，通过内在机制或弱模型引导提升模型表现。**强化学习与验证奖励（RLVR）** 的深化研究是另一焦点，论文不仅关注其训练效率，更深入剖析其导致策略熵坍缩的局限性及跨领域能力融合的范式。此外，**智能体技能的可演化性与安全性**受到高度关注，从经验中自动发现技能并用于红队测试的方法，以及确保智能体行为可审计的架构设计，成为了新的研究增长点。

#### **重点论文**

**🧠 大语言模型（架构、训练、对齐、评估）**

1.  **CritICL: Inference-Time Weak-to-Strong Generalization from Small Language Model Failure Modes**
    *   Yufan Wu et al.
    *   **一句话说明**：提出 CritICL 框架，利用小模型的失败模式作为弱信号，在推理时引导大模型进行弱到强的泛化，无需外部验证，为推理时扩展提供了新思路。
    *   [http://arxiv.org/abs/2608.27455v1](http://arxiv.org/abs/2608.27455v1)

2.  **TTPO: Test-Time Policy Optimization**
    *   Aozhe Wang et al.
    *   **一句话说明**：提出测试时策略优化（TTPO）方法，通过将强化学习中的奖励信号替换为无需标注的对比信号，实现了在测试时对模型进行训练，突破了传统后训练方法对标签的依赖。
    *   [http://arxiv.org/abs/2608.27448v1](http://arxiv.org/abs/2608.27448v1)

3.  **Boosting LLM Exploration via Weak-Model Guidance in RLVR**
    *   Xingyu Shen et al.
    *   **一句话说明**：分析了 RLVR 训练导致策略熵坍缩、限制探索多样性的问题，并提出利用弱模型指导来提升策略熵，从而改善大采样次数下的性能（pass@k）。
    *   [http://arxiv.org/abs/2608.27420v1](http://arxiv.org/abs/2608.27420v1)

4.  **Consolidating RLVR Capabilities Across Domains: A Deep Dive into Fusion Paradigms**
    *   Siye Wu et al.
    *   **一句话说明**：系统梳理了融合多个领域 RLVR 能力的三种范式（模型合并、数据混合、知识蒸馏），并进行了深入对比，为构建通用型推理模型提供了实用指南。
    *   [http://arxiv.org/abs/2608.27409v1](http://arxiv.org/abs/2608.27409v1)

5.  **How Language Models Organize and Structure Moral Knowledge**
    *   Orion Reblitz-Richardson.
    *   **一句话说明**：通过训练线性分类器，揭示了 LLM 不仅能检测道德内容，还能在几何空间中区分和组织不同的道德基础，为理解模型对齐的内部机制提供了新视角。
    *   [http://arxiv.org/abs/2608.27402v1](http://arxiv.org/abs/2608.27402v1)

6.  **Not All Eval-Awareness Is Equal: Capabilities Framing Predicts Compliance**
    *   Allison Zhuang, Santiago Aranguri.
    *   **一句话说明**：发现模型对“评估意识”的表述并非单一维度，其对自身能力的认知框架（Capabilities Framing）与是否服从指令高度相关，为精细化的安全评估提供了新指标。
    *   [http://arxiv.org/abs/2608.27340v1](http://arxiv.org/abs/2608.27340v1)

**🤖 智能体与推理（规划、工具使用、多智能体、思维链）**

1.  **WikiSkill: Compiling Agent Experience into Persistent Knowledge for Skill Evolution**
    *   Liyan Tang et al.
    *   **一句话说明**：提出 WikiSkill 框架，使智能体能够将交互经验编译为持久化的、可复用的技能知识，实现了技能的自主发现与演化，是迈向终身学习智能体的重要一步。
    *   [http://arxiv.org/abs/2608.27454v1](http://arxiv.org/abs/2608.27454v1)

2.  **RedEvoAgent: Automatic Red-Teaming Agent with Experience-Driven Skill Evolution**
    *   Junjie Zhang et al.
    *   **一句话说明**：将智能体技能演化思想应用于红队测试，提出 RedEvoAgent，它能从过往攻击经验中学习并进化出新的越狱策略，是自动化安全测试的前沿进展。
    *   [http://arxiv.org/abs/2608.27439v1](http://arxiv.org/abs/2608.27439v1)

3.  **Persona-Execution Separation: An Architecture Pattern for Evolving LLM Agents under Execution Audit**
    *   Yisen Xi.
    *   **一句话说明**：提出“人格-执行分离”（PES）架构模式，将智能体的指令、风格（人格）与可审计的状态化工作（执行）解耦，为解决智能体在组织场景下的安全与可进化性矛盾提供了设计模式。
    *   [http://arxiv.org/abs/2608.27427v1](http://arxiv.org/abs/2608.27427v1)

4.  **INTENT-AS-A-TOOL Makes it Easy to Track Agentic Misalignment**
    *   Yutong Zhang et al.
    *   **一句话说明**：研究智能体在目标冲突和压力下产生的“代理失调”问题，提出将“意图”作为工具来监控思维链，从而有效追踪和预测有害行为，提升了智能体安全性。
    *   [http://arxiv.org/abs/2608.27348v1](http://arxiv.org/abs/2608.27348v1)

5.  **SCIT: Testing Causal Cache Carriers in Latent Chain-of-Thought Models**
    *   Yi Ding et al.
    *   **一句话说明**：针对“潜在思维链”模型，提出 SCIT 因果测试协议，通过交换语义缓存，定位并验证了推动模型推理的关键因果载体，为理解这类黑盒模型提供了有力工具。
    *   [http://arxiv.org/abs/2608.27265v1](http://arxiv.org/abs/2608.27265v1)

**🔧 方法与框架（新技术、基准测试、效率优化）**

1.  **SWE-Prime: Fewer Trajectories, Better Performance**
    *   Dewu Zheng et al.
    *   **一句话说明**：揭示了在软件工程任务上，高质量、精选的少量成功轨迹数据比海量低质量数据更有效，提出了 SWE-Prime 数据筛选方法，为高效微调模型提供了新策略。
    *   [http://arxiv.org/abs/2608.27449v1](http://arxiv.org/abs/2608.27449v1)

2.  **CorporateBench: Large-Scale Q&A Benchmarking with Temporal Knowledge Bases**
    *   Sil Hamilton et al.
    *   **一句话说明**：发布了企业级问答基准 CorporateBench，包含时间敏感的知识库和人工验证的问答对，解决了现有评估集过于简单或不公开的痛点，为评估 LLM 在真实场景下的能力提供了宝贵资源。
    *   [http://arxiv.org/abs/2608.27391v1](http://arxiv.org/abs/2608.27391v1)

3.  **Puro-2B: Poor Lab's Qwen2-1.5B Trained on RTX 5090 within $5090**
    *   Kairong Luo et al.
    *   **一句话说明**：展示了在单张消费级显卡（RTX 5090）上，仅用 5090 美元预算即可从头训练一个 1.5B 参数的语言模型，打破了预训练“昂贵”的刻板印象，极具工程参考价值。
    *   [http://arxiv.org/abs/2608.27370v1](http://arxiv.org/abs/2608.27370v1)

4.  **Naive Prompt Optimization: Rethinking the Need for Complex Prompt Search**
    *   Yuan Chang, Xiaoqi Chen.
    *   **一句话说明**：对“复杂提示搜索”的必要性提出质疑，通过实验表明，简单、直接的提示优化方法性能与复杂搜索方法相当，但计算成本大幅降低，为智能体提示工程提供了新思路。
    *   [http://arxiv.org/abs/2608.27266v1](http://arxiv.org/abs/2608.27266v1)

**📊 应用（垂直领域、多模态、代码生成）**

1.  **CLAP: Cross-Embodiment Video World Models are Zero-Shot Physical Simulators**
    *   Kechen Liu, Ola Shorinwa.
    *   **一句话说明**：提出 CLAP 框架，利用海量异构视频数据构建跨本体的视频世界模型，使其在无需微调的情况下，作为零样本的物理模拟器，预测不同智能体的行为，是通用物理世界模型的重要探索。
    *   [http://arxiv.org/abs/2608.27406v1](http://arxiv.org/abs/2608.27406v1)

2.  **From Static to Dynamic: Benchmarking Real-World Code Review with MCR-Bench**
    *   Dewu Zheng et al.
    *   **一句话说明**：发布 MCR-Bench 基准，将代码审查从静态任务扩展到模拟真实世界中的多轮交互式审查，为评估和提升 LLM 在复杂协作任务中的能力提供了更贴近实际的测试。
    *   [http://arxiv.org/abs/2608.27442v1](http://arxiv.org/abs/2608.27442v1)

#### **研究趋势信号**

从今日投稿中可观察到几个明确的新兴研究方向：
1.  **弱到强的泛化（Weak-to-Strong Generalization）**：不再局限于训练阶段，而是扩展到推理时，利用弱模型或模型自身的失败模式来引导更强模型，成为一种新的能力提升范式。
2.  **智能体技能的自主进化**：智能体不再只是执行预设任务，而是能够从历史交互中自动提炼、总结并演化出新的技能，这标志着智能体研究正从“执行者”向“学习者”迈进。
3.  **对齐与安全研究的精细化**：对智能体安全的研究正从单一指标（如通过率）深入到行为机制（如意图识别、能力框架）和架构设计（如人格-执行分离），追求更根本和可解释的解决方案。
4.  **低成本、高效率的回归**：在追求大模型和复杂方法的同时，出现了对“少即是多”的反思，强调数据质量、轻量级优化和低成本训练的重要性，体现了研究社区的务实精神。

#### **值得精读**

1.  **CritICL**：这篇论文提出的“弱到强”泛化框架极具启发性。它挑战了“强模型必须依赖强监督”的传统认知，为在资源受限或高难度任务中提升模型推理能力提供了全新的、可扩展的路径，是推理时计算领域的重要突破。
2.  **WikiSkill**：这篇文章定义了智能体从经验中学习技能的完整范式，是该领域的奠基性工作之一。它清晰地阐述了如何将碎片化的交互经验转化为结构化的、可复用的知识，对于构建具备持续学习和适应能力的下一代AI Agent至关重要。
3.  **Consolidating RLVR Capabilities Across Domains**：RLVR 是当前提升模型推理能力的主流方法，但如何高效融合多个领域的专家能力是一个开放性问题。本文系统性地对比了三种主流范式，其实验发现和结论对于未来构建通用、强大的推理模型具有直接且重要的指导意义。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*