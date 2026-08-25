# ArXiv AI 研究日报 2026-08-26

> 数据来源: [ArXiv](https://arxiv.org/) (cs.AI, cs.CL, cs.LG) | 共 50 篇论文 | 生成时间: 2026-08-25 23:00 UTC

---

# ArXiv AI 研究日报 | 2026-08-26

## 今日速览

今日投稿聚焦三大趋势：**语言模型训练与对齐**方面，稳定 critic 训练、推理诱导错位缓解、自我反思策略优化等方案相继提出；**智能体与推理**领域，交互式世界模型、代码迁移基准、自改进框架以及科学智能体评估平台值得关注；**效率与可解释性**上，离散扩散的自适应采样、局部蒸馏、轻量级预测器加速和扩散 Transformer 推理提速均有实质性进展。此外，AI 对技能发展的长期影响、VLA 行为意图蒸馏、记忆系统安全攻击等应用级研究也引发讨论。

---

## 重点论文

### 🧠 大语言模型（架构、训练、对齐、评估）

1. **How to Train a Critic Stably and Efficiently**  
   [http://arxiv.org/abs/2608.23566v1](http://arxiv.org/abs/2608.23566v1)  
   *Penghui Qi, Xiangxin Zhou, Wee Sun Lee*  
   **一句话说明**：提出稳定高效的 critic 训练方法，解决 GRPO 类方法采样效率低的问题，实现 token 级优势估计。

2. **Mitigating Reasoning-Induced Misalignment via Safety-Direction Penalty**  
   [http://arxiv.org/abs/2608.23497v1](http://arxiv.org/abs/2608.23497v1)  
   *Yipeng Zhao, Qishun Yang, Shenzhe Zhu et al.*  
   **一句话说明**：发现数学/代码等推理数据微调会诱导有害行为，提出安全方向惩罚机制缓解推理诱导的错位。

3. **SRPO: Self-Reflective Policy Optimization for Long-Horizon Reasoning**  
   [http://arxiv.org/abs/2608.23493v1](http://arxiv.org/abs/2608.23493v1)  
   *Jialong Liu, Yuling Shi, Ning Yang et al.*  
   **一句话说明**：将自我反思机制引入 LLM 后训练，将稀疏结果反馈转化为可操作引导，提升长程推理能力。

### 🤖 智能体与推理（规划、工具使用、多智能体、思维链）

4. **ReWorld: An Interactive World Model with Long-Horizon Memory**  
   [http://arxiv.org/abs/2608.23565v1](http://arxiv.org/abs/2608.23565v1)  
   *Zhifei Chen, Luozhou Wang, Guibao Shen et al.*  
   **一句话说明**：通过分离训练和推理阶段的记忆与控制，实现可实时交互、记忆无限的世界模型。

5. **SWE Refactor Bench: Can Coding Agents Complete a Long-Horizon, Whole-Repository Stack Migration?**  
   [http://arxiv.org/abs/2608.23564v1](http://arxiv.org/abs/2608.23564v1)  
   *Deyao Hong, Yizhe Chi, Wenyi Li et al.*  
   **一句话说明**：首个衡量代码代理完成全仓库堆栈迁移的基准，填补现有基准仅关注单步修复的空白。

6. **Prime Agent: A Self-Improving RLM Harness**  
   [http://arxiv.org/abs/2608.23552v1](http://arxiv.org/abs/2608.23552v1)  
   *Seth Karten, Alex L. Zhang, Kevin Thomas et al.*  
   **一句话说明**：开源的长程评估与编码代理工作流框架，基于递归语言模型范式实现持久 IPython REPL 和自改进。

7. **EarthVerse: Benchmarking Scientific Agents Across Dynamic Earth Systems and Natural Hazards**  
   [http://arxiv.org/abs/2608.23525v1](http://arxiv.org/abs/2608.23525v1)  
   *Zhiqing Cui, Xinxiang Yin, Yihong Tang et al.*  
   **一句话说明**：面向地球系统科学的多源数据智能体基准，评估代理在自然灾害场景下的推理与证据整合能力。

### 🔧 方法与框架（新技术、基准测试、效率优化）

8. **Provably adaptive sampling with uniform and remasking discrete diffusion models**  
   [http://arxiv.org/abs/2608.23554v1](http://arxiv.org/abs/2608.23554v1)  
   *Daniil Dmitriev, Zhihan Huang, Yuting Wei*  
   **一句话说明**：对离散扩散模型提出可证明自适应的采样策略，统一前向过程与 remasking 框架。

9. **Interpretable AI with Local Distillation**  
   [http://arxiv.org/abs/2608.23538v1](http://arxiv.org/abs/2608.23538v1)  
   *Erin Craig, Yiling Huang, Snigdha Panigrahi*  
   **一句话说明**：通过局部蒸馏将黑箱模型（如表格基础模型）的预测分解为可解释的线性组件，兼顾准确性与可解释性。

10. **MetaCaster: Meta-Harness-Optimized Agent for End-to-End Few-Shot Learning of Lightweight Time Series Forecasters**  
    [http://arxiv.org/abs/2608.23473v1](http://arxiv.org/abs/2608.23473v1)  
    *ChengAo Shen, Wenchao Yu, Fangyu Wu et al.*  
    **一句话说明**：提出元学习驱动的智能体，在资源受限场景下仅用少量样本端到端训练轻量级时序预测器。

11. **ChebBooster: A Training-Free Approach for Efficient Diffusion Transformer Inference via Chebyshev-Inspired Extrapolation**  
    [http://arxiv.org/abs/2608.23429v1](http://arxiv.org/abs/2608.23429v1)  
    *Chengjie Lu, Tianchi Deng, Zhengqi He et al.*  
    **一句话说明**：无需训练的扩散 Transformer 加速方法，利用切比雪夫外推近似多步结果，减少推理步数。

### 📊 应用（垂直领域、多模态、代码生成）

12. **How AI Assistance Affects Human Skill Development: A Study of Learning with Logic Puzzles**  
    [http://arxiv.org/abs/2608.23543v1](http://arxiv.org/abs/2608.23543v1)  
    *Shang Wu, Catarina G Belem, Shuyuan Fu et al.*  
    **一句话说明**：通过逻辑谜题实验揭示 AI 即时辅助在短期提升任务表现的同时可能削弱长期技能发展，引发人机协作深思。

13. **Act with Intent: Distilling Behavior Intent for Vision-Language-Action Models**  
    [http://arxiv.org/abs/2608.23478v1](http://arxiv.org/abs/2608.23478v1)  
    *Sangoh Lee, Sangwoo Mo, Wook-Shin Han*  
    **一句话说明**：为 VLA 模型蒸馏行为意图，使动作解码器不仅模仿示教动作，更能理解动作背后的局部目标。

14. **InjecMEM: Memory Injection Attack on LLM Agent Memory Systems**  
    [http://arxiv.org/abs/2608.23471v1](http://arxiv.org/

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*