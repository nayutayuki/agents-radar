# ArXiv AI 研究日报 2026-07-31

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-07-31 02:31 UTC

---

# ArXiv AI 研究日报（2026-07-31）

---

## 今日速览

今日论文聚焦于智能体安全与评估、记忆机制创新、多模态推理的细粒度信用分配三大方向。**Tycho** 在 ARC-AGI-3 上通过程序化世界模型实现主动抽象，标志着智能体从被动推理到主动技能习得的范式转变；**Qwen-UI-Agent** 和 **Echoverse** 分别从真实设备部署和规模化训练环境两个维度推动 GUI 代理迈向实用化；**MemHarness** 挑战了“记忆即重放”的默认假设，提出动态重建机制，为 LLM 长期记忆提供新思路。此外，针对 LLM 代理的欺骗能力评估、记忆注入防御、以及合成数据从简单改写升级到结构化组织等主题也值得关注。

---

## 重点论文

### 🧠 大语言模型（架构、训练、对齐、评估）

**1. Paying for Honesty Without Knowing the Truth: Reputation-Penalty Design for LLM Marketplace Agents**  
链接：http://arxiv.org/abs/2607.28330v1  
作者：Mingdai Yang, Shicheng Fan, Kejing Yu et al.  
一句话：针对 LLM 代理市场中的虚构属性问题，提出无需真实信息的声誉惩罚机制，激励诚实行为，对 AI 经济系统设计有直接参考价值。

**2. MemHarness: Memory Is Reconstructed, Not Replayed**  
链接：http://arxiv.org/abs/2607.28272v1  
作者：Rong Wu, Daocheng Fu, Licheng Wen et al.  
一句话：提出记忆重建框架替代静态重放，使代理根据当前上下文动态重构记忆，提升长期任务适应性，挑战了主流记忆增强方法。

**3. Beyond Rephrasing: Book-Level Organization Improves Synthetic Textbook Data for Mid-Training**  
链接：http://arxiv.org/abs/2607.28109v1  
作者：Jiawen Tao, Miao Peng, Yaoming Li et al.  
一句话：发现合成教材的书籍级结构化组织（而非仅内容改写）显著提升预训练效果，为大规模合成数据生成提供新维度。

**4. SemPIC: Learning Semantic Position-Independent KV Caches**  
链接：http://arxiv.org/abs/2607.28069v1  
作者：Hui Xie, Peng Xiao, Yutong Deng et al.  
一句话：提出语义位置无关的 KV 缓存，实现跨文档语义复用，解决长上下文检索中 prefix caching 无法利用重复文档的问题。

---

### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

**5. Tycho: Active Abstraction with Programmatic World Models for ARC-AGI-3**  
链接：http://arxiv.org/abs/2607.28287v1  
作者：Jens Lehmann, Andrei Aioanei, Sahar Vahdati  
一句话：在 ARC-AGI-3 挑战中通过程序化世界模型和主动抽象实现高效技能习得，将抽象问题转化为可交互的推理过程，是智能体学习范式的关键进展。

**6. Qwen-UI-Agent Technical Report: Toward Next-Generation Real-World Centric Foundation GUI Agents**  
链接：http://arxiv.org/abs/2607.28227v1  
作者：Hanzhang Zhou, Panrong Tong, Xu Zhang et al.  
一句话：发布新一代 GUI 基础代理，支持跨平台、长程任务、GUI+CLI 混合操作，在真实设备上实现可靠执行，代表 GUI 代理从研究走向实用。

**7. Echoverse: Deep, Evolving Environments for Training Computer-Use Agents at Scale**  
链接：http://arxiv.org/abs/2607.28074v1  
作者：Yash Pandya, Sahil Gupta, Sarthak Harne et al.  
一句话：提出可深度演化、可重置的合成环境，用于大规模训练计算机使用代理，突破训练数据瓶颈，可生成接近真实应用的复杂场景。

**8. Can Agents Deceive? Evaluating Reasoning and Deception in ParliamentBench using a Social Deduction Game**  
链接：http://arxiv.org/abs/2607.28146v1  
作者：Niklas Bauer, Lars Benedikt Kaesberg, Akiko Aizawa et al.  
一句话：利用社交推理游戏（ParliamentBench）系统评估 LLM 代理的欺骗能力，为高安全场景下的智能体部署提供重要基准。

---

### 🔧 方法与框架（新技术、基准测试、效率优化）

**9. PathView-Bench: Can Multimodal Large Language Models Achieve Fine-grained Multisc

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*