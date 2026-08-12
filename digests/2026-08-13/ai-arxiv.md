# ArXiv AI 研究日报 2026-08-13

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-08-12 23:21 UTC

---

# ArXiv AI 研究日报 — 2026-08-13

## 今日速览

今日投稿围绕**AI安全与可信赖性**、**多语言/跨语言泛化**、**数据效率与自进化**三大主线展开。值得关注的突破包括：**AI与人类协作证明Grothendieck常数新界**展示了长程数学推理的潜力；**跨语言安全对齐的“幻觉”**被系统揭示，低资源语言几乎无防护；**自进化智能体技能压缩框架SkillZip**通过发现可复用结构大幅降低存储与推理成本；此外，**概率一致性验证**、**注意力路径不确定性**和**结构化逻辑张量网络**等理论工作为可解释AI提供了新工具。

## 重点论文

### 🧠 大语言模型

**1. **Long-Horizon AI Research for Grothendieck Constant: A Case Study in Human-AI Mathematical Collaboration****
链接: http://arxiv.org/abs/2608.11195v1
作者: Alan Li et al.
一句话说明: 展示了AI如何辅助人类改进Grothendieck常数上下界，为人机协同数学研究提供了可复现的案例范式。

**2. **The Illusion of Cross-Lingual Safety in Low-Resource Languages****
链接: http://arxiv.org/abs/2608.11146v1
作者: Abigail Oppong et al.
一句话说明: 证明了英语对齐的安全护栏在多语言特别是低资源语言中几乎失效，揭示LLM部署的重大安全风险。

**3. **Attention-Path Fragility as an Uncertainty Signal in Large Language Models****
链接: http://arxiv.org/abs/2608.11138v1
作者: Minsoo Kim et al.
一句话说明: 提出ASMI方法，通过扰动注意力子网络来捕捉模型的不确定性，为置信度估计提供新视角。

**4. **Mapping and Measuring the Behavioral Evolution of Large Language Models****
链接: http://arxiv.org/abs/2608.11027v1
作者: Dong Qiao et al.
一句话说明: 对32个模型在10,000个提示上的行为进行嵌入和聚类，系统刻画了模型家族间及代际间的输出演化。

### 🤖 智能体与推理

**5. **Surgical WAM: A World-Action Model for Data-Efficient Surgical Robot Learning****
链接: http://arxiv.org/abs/2608.11204v1
作者: Wenrui Bao et al.
一句话说明: 提出了面向手术机器人的世界-动作联合模型，在极少量动作标注数据上实现高效策略学习。

**6. **SkillZip: Evaluation-Free Skill Compression for Self-Evolving Agents by Discovering Reusable Structure****
链接: http://arxiv.org/abs/2608.11079v1
作者: Xiaofan Bai et al.
一句话说明: 自进化智能体长期积累的冗余技能可通过结构发现自动压缩，避免依赖评估分值的“灾难性记忆”。

**7. **V-FiLLM: Verified Financial LLM Reasoning Benchmark****
链接: http://arxiv.org/abs/2608.11047v1
作者: Alicia Larsen et al.
一句话说明: 基于可执行计算树生成金融推理基准，实现了结构化数据上的可验证推理评估。

### 🔧 方法与框架

**8. **Beyond a Bag of Features: Set-Level Instability in Sparse Autoencoders****
链接: http://arxiv.org/abs/2608.11197v1
作者: Nikolai Bolik et al.
一句话说明: 揭示稀疏自编码器（SAE）在特征集合层面存在不稳定性，挑战了LLM可解释性方法中SAE的可靠性。

**9. **How to Verify Consistency of Probabilistic Claims****
链接: http://arxiv.org/abs/2608.11181v1
作者: Orr Paradise et al.
一句话说明: 证明了概率预测器的自一致性可以在多项式时间内验证，为AI安全中的诚实性提供了理论基础。

**10. **Conditional Independence Tests for Constraint-Based Causal Discovery: A Survey****
链接: http://arxiv.org/abs/2608.11156v1
作者: Pavel Averin et al.
一句话说明: 系统综述了因果发现中条件独立性检验的各类方法，厘清了不同假设下的适用性与局限性。

**11. **sLTN: Structural Logic Tensor Networks****
链接: http://arxiv.org/abs/2608.11136v1
作者: Davide Rinaldi et al.
一句话说明: 扩展逻辑张量网络以处理结构化数据（如树、图），为神经符号学习开辟新路径。

**12. **ReRound: Reconstructive Rounding to Resolve Midpoint Ambiguity in Calibration-Free LLM Quantization****
链接: http://arxiv.org/abs/2608.11045v1
作者: He-Yen Hsieh et al.
一句话说明: 提出基于条件扩散的重建取整方法，解决了LLM权重量化中靠近区间中点的歧义问题。

### 📊 应用

**13. **ConVAWG: A Retrieval-Grounded Framework for Controlled Synthetic Dialogue Generation in Violence Against Women and Girls****
链接: http://arxiv.org/abs/2608.11200v1
作者: Chen Lyu et al.
一句话说明: 针对敏感对话领域，结合检索增强生成控制合成对话内容，助力AI伦理研究。

**14. **MultiModal Code-Switching: Interleaving Visual Objects into Language for Explicit Object-Level Alignment****
链接: http://arxiv.org/abs/2608.11167v1
作者: Changhao Xiang et al.
一句话说明: 在多模态模型中显式将视觉物体嵌入文本序列，实现对象级别的模态对齐，缓解指代歧义。

**15. **On the Limitations of Cross-Lingual Consistency in Multilingual Text-to-image Generation****
链接: http://arxiv.org/abs/2608.11002v1
作者: Sicheng Zhang et al.
一句话说明: 推出LingT2I基准，系统评估多语言文本到图像生成中的跨语言一致性差距，指出现有模型的语言偏见。

## 研究趋势信号

1. **AI安全从“事后解释”转向“过程验证”**：多篇论文聚焦概率一致性、注意力扰动、行为归因，强调在推理时而非训练后验证可靠性。2. **低资源与跨语言泛化成为核心瓶颈**：安全对齐、策略保留、多模态生成等领域均发现跨语言下的严重退化，急需语言无关的鲁棒机制。3. **自进化与自监督压缩兴起**：智能体长期积累的技能、文档、经验可通过结构发现（而非评分）实现自动压缩，降低记忆爆炸风险。4. **量子计算与AI的交叉加速**：量子注意力机制、量子状态跟踪等理论工作开始出现，探索量子优势在AI推理中的应用。

## 值得精读

1. **Long-Horizon AI Research for Grothendieck Constant**（论文4）— 完整呈现了AI在真实数学研究中的长程协作流程，提供了可复现的实验设计和失败分析，对AI4Science社区极具参考价值。
2. **The Illusion of Cross-Lingual Safety in Low-Resource Languages**（论文14）— 实验设计严谨，覆盖多语言模型家族，结论直接冲击当前LLM安全部署的实践，应引起学界和工业界高度关注。
3. **How to Verify Consistency of Probabilistic Claims**（论文9）— 从计算复杂性角度解决了概率预测的一致性验证问题，为可靠AI系统和安全审计提供了理论基石，值得精读推导。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*