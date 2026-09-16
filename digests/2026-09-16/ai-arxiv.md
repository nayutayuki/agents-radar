# ArXiv AI 研究日报 2026-09-16

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-09-16 00:46 UTC

---

# ArXiv AI 研究日报 | 2026-09-16

## 今日速览

今日投稿亮点集中在大语言模型的安全与对齐、强化学习训练新范式、以及面向长期推理的多智能体系统。**CoT监控可被植入恶意推理绕过**，引发对AI安全机制的严峻质疑；**Bellman Policy Optimization (BPO)** 提出一种无需批判网络的强化学习方法，有望提升LLM推理能力；**Stellar Colosseum** 通过大规模多智能体协作攻克数学理论难题；**因果可写性** 揭示视频模型内部已学到正确物理规律却未被使用，为可解释性提供新视角。此外，低秩压缩、联邦学习隐私、临床AI评估等领域也有扎实进展。

---

## 重点论文

### 🧠 大语言模型（架构、训练、对齐、评估）

**1. Corrupt Plans, Clean Traces: Evading Chain-of-Thought Monitoring with Plan Injection**  
链接: http://arxiv.org/abs/2609.15989v1  
作者: K. Chidambaram et al.  
一句话：揭示在思维链中植入无害语义的恶意推理可成功绕过CoT监控，暴露了当前安全策略的根本漏洞。

**2. Bellman Policy Optimization**  
链接: http://arxiv.org/abs/2609.15987v1  
作者: Z. Song et al.  
一句话：从策略镜像下降导出无批判网络的强化学习方法，对自回归生成+终端奖励场景实现高效优化，无需价值函数估计。

**3. The Router Within: Eliciting Native Skill Routing from a Frozen LLM**  
链接: http://arxiv.org/abs/2609.15982v1  
作者: R. Chen et al.  
一句话：无需额外上下文加载技能元数据，通过诱导冻结LLM内部的“原生技能路由”实现大规模技能库的高效调用。

**4. Inoculation Midtraining with Learned Neologisms**  
链接: http://arxiv.org/abs/2609.15886v1  
作者: K. O'Brien et al.  
一句话：在训练中期注入特定新词，可影响模型在后期微调中对不良属性的泛化，为安全对齐提供轻量级干预手段。

**5. K-Bench: a clinically calibrated benchmark for evaluating large language models in high-risk mental health conversations**  
链接: http://arxiv.org/abs/2609.15855v1  
作者: L.M. Vowels et al.  
一句话：构建125个模型配置的临床校准基准，系统评估LLM在高风险心理健康对话中的安全性，填补关键评估空白。

---

### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

**6. Stellar Colosseum: A Many-Agent Harness for Long-Horizon Research in Mathematics and Theoretical Computer Science**  
链接: http://arxiv.org/abs/2609.15983v1  
作者: H. Lin et al.  
一句话：构建模型无关的多智能体框架，将大量推理预算分配于长期数学理论研究，实现超越单模型的联合研究能力。

**7. HypoEvolve: Genetic Algorithms Enable Multi-Agent LLMs to Discover Scientific Hypotheses**  
链接: http://arxiv.org/abs/2609.15938v1  
作者: J. Liu et al.  
一句话：结合遗传算法与多智能体LLM协作，通过进化搜索自动生成和筛选科学假说，探索不同协作形式对发现能力的影响。

**8. AlgoEvo: Self-Evolving Agentic Search for Automated Algorithm Discovery**  
链接: http://arxiv.org/abs/2609.15820v1  
作者: J. Qiu et al.  
一句话：提出自进化智能体搜索框架，突破固定搜索管道限制，实现跨范式算法发现与执行经验积累。

**9. Learning to Coach for Experiential Learning**  
链接: http://arxiv.org/abs/2609.15851v1  
作者: G. Chen et al.  
一句话：训练一个专属“教练”LLM，从演员模型的原始轨迹中提取可操作经验知识，显著提升基于经验的学习效率。

---

### 🔧 方法与框架（新技术、基准测试、效率优化）

**10. Per-Matrix Optimality Is Not Enough: Three-Level Optimization for Low-Rank LLM Compression**  
链接: http://arxiv.org/abs/2609.15838v1  
作者: H. Zhang et al.  
一句话：指出独立矩阵SVD截断在块前向传播中误差累积，提出三层优化方案，借鉴量子多体分层变分优化实现更优低秩压缩。

**11. When the World Lies: Backdoor Attacks on Latent World Models for Downstream Control**  
链接: http://arxiv.org/abs/2609.15781v1  
作者: R. Riaño et al.  
一句话：首次展示预训练潜在世界模型可被植入后门，导致下游控制策略在触发时产生危险动作，安全复用面临新威胁。

**12. Disentangling Representation Evolution in Transformers through Directional Decomposition**  
链接: http://arxiv.org/abs/2609.15975v1  
作者: S. He et al.  
一句话：将Transformer表示更新分解为平行与垂直分量，发现模型中存在显著的“方向保持”和“方向重定向”模式，揭示表征演化功能几何。

**13. Sharp Rates and a One-Line Correction for Spectral Representation Learning**  
链接: http://arxiv.org/abs/2609.15825v1  
作者: D. Tang et al.  
一句话：为谱表示学习（CCA/HGR）提供最优收敛速率，并给出一个简单修正公式，使离线特征质量可近乎匹配在线微调。

---

### 📊 应用（垂直领域、多模态、代码生成）

**14. CiteGuard-RAG: A Validation-Centered AI System for Evidence-Grounded Question Answering**  
链接: http://arxiv.org/abs/2609.15830v1  
作者: S. Barua et al.  
一句话：构建以验证为核心的RAG系统，不仅检索证据，还确保答案有引文支撑、引文可验证，并能恰当拒绝回答问题。

**15. MoveBench: A Benchmark for Global-Scale Wildlife Movement Forecasting**  
链接: http://arxiv.org/abs/2609.15780v1  
作者: J. Kay et al.  
一句话：发布首个大规模野生动物轨迹预测基准，包含全球多物种数据，挑战高随机性和环境依赖性，推动生态AI发展。

**16. Enabling Streaming User Transcription in Full-Duplex Speech-to-Speech Models**  
链接: http://arxiv.org/abs/2609.15759v1  
作者: K. Hu et al.  
一句话：在全双工语音-语音模型中实现流式用户语音转录，支持对话记录与无障碍功能，填补了该场景下的技术空白。

---

## 研究趋势信号

- **安全与对齐的攻防深化**：攻击者开始利用思维链“看起来无害”的语义空间（论文1），以及世界模型后门（论文43），防御方面出现中期训练干预（21）。安全战线正从输出层延伸到推理过程与预训练模型复用。
- **从“训练模型”到“训练过程”**：BPO（2）和遗传型多智能体搜索（7,12,35）显示，强化学习与进化计算正被重新设计为适应LLM的元优化管道，而非传统训练方式。
- **长期推理的智能体协作**：Stellar Colosseum（3）和HypoEvolve（7）标志着一类新范式——将多智能体视为“分布式研究团队”，分配推理预算解决需多步决策的复杂问题。
- **临床AI评估的可操作性转向**：K-Bench（28）和KnowBench（41）不再仅衡量回答准确性，而要求挑战高风险场景、度量实际负担减轻，推动评估从研究指标向部署指标迁移。

---

## 值得精读

**1. Corrupt Plans, Clean Traces: Evading Chain-of-Thought Monitoring with Plan Injection**  
理由：当前CoT监控是主流安全策略，该文展示如何构造“良性语义的恶意推理”以绕过检查，攻击手法精巧且威胁现实，值得每个做安全对齐的研究者仔细研读。

**2. Stellar Colosseum: A Many-Agent Harness for Long-Horizon Research**  
理由：首次将多智能体协作应用于数学与理论计算机科学的长期研究问题，框架设计具有通用性，可能开启“AI联合研究”的新路线，思路极具启发性。

**3. Bellman Policy Optimization**  
理由：无需批判网络的强化学习新方法直接适用于LLM自回归生成，理论优雅且实用性强，有望成为RLVR领域的重要基线。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*