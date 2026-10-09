# Hugging Face 热门模型日报 2026-10-09

> 数据来源: [Hugging Face Hub](https://huggingface.co/) | 共 30 个模型 | 生成时间: 2026-10-09 02:33 UTC

---

# 🤗 Hugging Face 热门模型日报 | 2026-10-09

## 📌 今日速览

本周 Hugging Face 热度最高的模型是 Qwen 官方发布的 **Qwen3.8-27B**（点赞 17,288，下载 684 万），稳坐多模态对话模型榜首；视频生成赛道由 **Lightricks/LTX-2.5** 领跑（点赞 6,951），成为下一个爆款内容工具；社区微调与量化活动持续活跃，尤其围绕 Qwen 3.5/3.8 系列衍生了大量 GGUF/GSQ-RCO 变体；此外，**Cloudflare/clef** 系列首次进入热门榜，展示了轻量级多模态模型在企业部署场景的潜力；值得关注的是 **deepseek-ai/DeepSeek-V4.1-Flash** 作为新模型迅速积累 4,262 点赞，标志着大厂在Flash版本上的竞争加剧。

---

## 🔥 热门模型

### 🧠 语言模型（LLM、对话模型、指令微调）

1. **[deepseek-ai/DeepSeek-V4.1-Flash](https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash)**  
   **作者**: deepseek-ai | 点赞: 4,262 | 下载: 1,282,524  
   💬 DeepSeek 的最新 Flash 版本，支持图像与文本输入，主打低延迟推理与高性价比，社区反响热烈。

2. **[Aleph-Alpha/Kolibri-1](https://huggingface.co/Aleph-Alpha/Kolibri-1)**  
   **作者**: Aleph-Alpha | 点赞: 815 | 下载: 6,777  
   💬 融合 MoE 与推理能力的新一代模型，参数效率突出，定位为开源生成模型。

### 🎨 多模态与生成（图像、视频、音频、文本到X）

1. **[Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5)**  
   **作者**: Lightricks | 点赞: 6,951 | 下载: 1,688,807  
   🎬 强大的图像/文本到视频扩散模型，支持多种输入格式，是本周最受关注的生成式模型。

2. **[Qwen/Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B)**  
   **作者**: Qwen | 点赞: 17,288 | 下载: 6,841,660  
   🖼️ 通义千问系列旗舰多模态模型，支持图文对话与推理，社区评分极高，下载量遥遥领先。

3. **[Qwen/Qwen3.8-Flash-Next](https://huggingface.co/Qwen/Qwen3.8-Flash-Next)**  
   **作者**: Qwen | 点赞: 6,045 | 下载: 1,640,938  
   🚀 Qwen 实验性 Flash 迭代版本，优化推理速度，展示 Qwen 4 代技术预研，吸引大量尝鲜用户。

4. **[Cloudflare/clef](https://huggingface.co/Cloudflare/clef)**  
   **作者**: Cloudflare | 点赞: 1,890 | 下载: 10,874  
   🌐 Cloudflare 推出的轻量级多模态模型，基于 Qwen 3.5 架构，适合边缘部署与 API 服务，新晋热门。

5. **[Qwen/Qwen-Image-2.1](https://huggingface.co/Qwen/Qwen-Image-2.1)**  
   **作者**: Qwen | 点赞: 3,128 | 下载: 116,957  
   🎨 专注于文生图与图像编辑的扩散模型，官方出品，质量稳定。

6. **[abenzerps/Qwen-Image-2.1-Uncensored-GGUF](https://huggingface.co/abenzerps/Qwen-Image-2.1-Uncensored-GGUF)**  
   **作者**: abenzerps | 点赞: 3,681 | 下载: 1,933,066  
   🖌️ 社区去限制版 Qwen 图像生成模型，采用 GGUF 格式，下载量极高，满足特定创意需求。

7. **[autotrust/JEV-27B-VL](https://huggingface.co/autotrust/JEV-27B-VL)**  
   **作者**: autotrust | 点赞: 2,953 | 下载: 1,533,034  
   🖼️ autotrust 基于 Qwen 3.5 打造的视觉语言模型，性能与 Qwen 官方版本接近，社区信任度高。

8. **[Alissonerdx/BFS-Best-Face-Swap](https://huggingface.co/Alissonerdx/BFS-Best-Face-Swap)**  
   **作者**: Alissonerdx | 点赞: 1,319 | 下载: 243,910  
   👤 基于 LoRA 和 Qwen 图像的换脸模型，场景趣味性强，在社交媒体传播快。

9. **[canberkkkkkk/ema-lightning](https://huggingface.co/canberkkkkkk/ema-lightning)**  
   **作者**: canberkkkkkk | 点赞: 303 | 下载: 9,467  
   🔊 土耳其语 TTS 模型，EMA-Lightning 架构，填补非英语语音合成领域空白。

10. **[Cactus-Compute/whistle](https://huggingface.co/Cactus-Compute/whistle)**  
    **作者**: Cactus-Compute | 点赞: 191 | 下载: 2,594  
    🎙️ 设备端语音识别模型，轻量高效，适合离线应用。

### 🔧 专用模型（代码、数学、医疗、嵌入）

1. **[convaiinnovations/laya](https://huggingface.co/convaiinnovations/laya)**  
   **作者**: convaiinnovations | 点赞: 5,389 | 下载: 36,328  
   🔍 文本分类模型，专注于系统一（System 1）快速决策，点赞数异军突起，体现市场对高效分类模型的需求。

2. **[google/embeddinggemma-2](https://huggingface.co/google/embeddinggemma-2)**  
   **作者**: google | 点赞: 1,206 | 下载: 21,148  
   📦 Google 官方多模态嵌入模型，Gemma 2 架构，适合检索与向量库应用。

3. **[jialinyyzz/humanizer](https://huggingface.co/jialinyyzz/humanizer)**  
   **作者**: jialinyyzz | 点赞: 631 | 下载: 23,439  
   ✍️ 文本生成模型，目标是使 AI 输出更“人类化”，自然度检测与伪装场景受关注。

### 📦 微调与量化（社区微调、GGUF、AWQ）

1. **[ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF)**  
   **作者**: ISTA-DASLab | 点赞: 2,068 | 下载: 1,517,150  
   🔧 基于 Qwen 3.8-27B 的混合精度量化版，采用 GSQ + RCO 技术，社区下载量极高，被广泛用于本地部署。

2. **[ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF)**  
   **作者**: ISTA-DASLab | 点赞: 724 | 下载: 3,405,442  
   🔧 Flash-Next 版本的量化版，下载量甚至超过原版，显示量化版在资源受限用户中的刚需。

3. **[prism-ml/Ternary-Bonsai-2-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf)**  
   **作者**: prism-ml | 点赞: 2,549 | 下载: 4,345,410  
   🌳 极端三元量化（2-bit）尝试，大幅降低模型体积，获得大量下载，探索 ultra-low-bit 极限。

4. **[DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF](https://huggingface.co/DavidAU/Qwen3.8-27B-TURBO-Fable-Cold-Fusion-735-882-Heretic-Uncensored-NEO-CODER-MAX-MTP-GGUF)**  
   **作者**: DavidAU | 点赞: 1,571 | 下载: 2,037,446  
   🔧 社区魔改的极致微调版，融合多种技术（冷融合、Heretic 去限制等），命名夸张但下载量证明其吸引力。

5. **[Venastine-Research/Xing4.0-29B-A4B-GGUF](https://huggingface.co/Venastine-Research/Xing4.0-29B-A4B-GGUF)**  
   **作者**: Venastine-Research | 点赞: 669 | 下载: 36,481  
   🔧 29B 规模 MoE 模型的 GGUF 量化版，适合高级用户本地运行。

6. **[orcarouter/OrcaSAQ-2-Cyber-27B-Uncensored-GGUF](https://huggingface.co/orcarouter/OrcaSAQ-2-Cyber-27B-Uncensored-GGUF)**  
   **作者**: orcarouter | 点赞: 471 | 下载: 20,613  
   🔧 去限制的 OrcaSAQ 微调版，聚焦网络安全主题，满足特定需求。

7. **[orcarouter/Qwen3.8-Flash-Next-Uncensored-GGUF](https://huggingface.co/orcarouter/Qwen3.8-Flash-Next-Uncensored-GGUF)**  
   **作者**: orcarouter | 点赞: 680 | 下载: 492,022  
   🔧 对 Flash-Next 模型进行 abliterated（去限制）处理，社区跟风趋势明显。

8. **[SC117/Qwen3.8-Flash-Next-GSQ-RCO-abliterated-GGUF](https://huggingface.co/SC117/Qwen3.8-Flash-Next-GSQ-RCO-abliterated-GGUF)**  
   **作者**: SC117 | 点赞: 155 | 下载: 612,411  
   🔧 在量化基础上再次 abliterated，反映“去限制+量化”双重定制逐渐成为社区主流操作。

（注：autotrust 系列的量化变体 **GEV-26B-Decide-NVFP4**、**GEV-26B-Decide** 等也属于微调/专用分类，但因其核心任务为文本分类，已归入专用模型。）

---

## 📊 生态信号

- **Qwen 生态一骑绝尘**：本周热门榜单中超过三分之一是 Qwen 家族（原版、Flash、GGUF、微调等），说明阿里通义在开源社区的号召力已达顶峰，形成类似 LLaMA 在 2024 年的统治地位。
- **多模态与视频生成爆发**：Lightricks/LTX-2.5 和 Qwen3.8-27B 分别代表视频与图像对话两个方向，开源模型在该赛道已可与闭源 Midjourney、Runway 抗衡。
- **量化活动空前活跃**：GSQ-RCO、三元量化（Ternary-Bonsai）、GGUF 等新量化方案层出不穷，社区不再满足于简单 4-bit/8-bit，而是探索 2-bit 及混精压缩，这对端侧推理意义重大。
- **去限制（Abbilterated/Uncensored）持续受追捧**：多个原始模型被社区修改为“无审查”版，表明用户对内容自由的强烈需求，但也带来合规风险。
- **开源权重 vs 闭源**：DeepSeek-V4.1-Flash 和 Cloudflare/clef 的快速上榜显示，企业级 Flash 模型正通过开源方式抢占市场，闭源 API 的竞争压力增加。

---

## 🧭 值得探索

1. **[Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5)**  
   **理由**：当前最火的开源视频生成模型，支持图/文/视频到视频，质量接近商业产品，适合内容创作者、影视编辑和 AI 视频研究。

2. **[prism-ml/Ternary-Bonsai-2-27B-gguf](https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf)**  
   **理由**：2-bit 三元量化的极限压缩实验，27B 模型可塞入不到 10GB 显存，挑战了“压缩是否过度”的边界，对边缘部署和低资源场景极具参考价值。

3. **[ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF](https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF)**  
   **理由**：将官方 Qwen3.8-27B 量产化的标杆作品，下载量 150 万+，证明其稳定性和实用性。如果你计划在本地跑 27B 多模态模型，这是首选量化版。

---
*本日报由 [agents-radar](https://github.com/nayutayuki/agents-radar) 自动生成。*