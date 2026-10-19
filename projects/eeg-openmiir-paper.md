# EEG 论文（Paper 1，侧栏名：eeg 论文建档发布）

- 归档日期：2026-10-19
- 来源：我在 Drive 读到的 2026-06-29 版稿件 `manuscript_jop_submission_draft`（当时目标刊是 Journal of Psychophysiology），以及同日的 cv / LOSO 结果表。10 月的新版（"方法写了一半，卡在图和讨论"）我没见过。
- 题目：Leakage-Aware Decoding of Music Perception and Cued Imagery From OpenMIIR EEG

## 六月版做了什么
- 公开数据集 OpenMIIR 的二次分析。二分类：听音乐 vs 提示性想象。
- 被试：P01 单人、P01/P04、P01/P04/P06 三种规模；最大 2490 窗、360 trial、12 首。OpenMIIR 全集是 10 人 ✅。
- 特征：每通道 θ/α/β/γ 对数带功率 + 时域均值标准差；3 s 窗、1.5 s 步。
- 模型：dummy、logistic、随机森林为主；CNN / EEGNet / transformer 只在单被试做过，当次要证据。
- 验证：按 trial 分组的分层 CV；多被试加 LOSO；bootstrap CI、sign-flip 配对检验、打乱训练标签的阴性对照。
- 结果：P01 单人 0.608 [0.575, 0.641]，比最好 dummy 高 0.089，p = 0.031；三人 pooled 0.541；三人 LOSO 0.519 [0.501, 0.553]，与 dummy 差 0.017，p = 0.25。
- 结论自己写得很诚实：被试内有弱信号，跨被试没有。

## 我对研究意义的判断（2026-10-19）
我同意"研究意义不大"这个感觉，具体是三件事：
1. **问题本身偏弱**。"听 vs 想象"本质上含"有声音 vs 没声音"的混淆，分开它不需要懂音乐，听觉诱发反应就够。审稿人会问：你解码的是音乐认知状态，还是耳朵有没有在响。
2. **只用了 10 人里的 3 人**。这是最硬的伤。OpenMIIR 公开、免费，不跑全部被试没有理由，审稿人第一条就会要。
3. **主要结论是边界**：跨被试 0.52。诚实，但一篇"我们试了，不行"的论文，没有对照方法就只是一个阴性结果。

它好的地方也要说：验证设计（trial 分组、阴性对照、LOSO、CI）比这个领域很多论文规范；写法克制；全流程可复现。这些是"会做研究"的证据，不是"做出了发现"的证据。

## 为什么它仍然排第一
它的价值不在科学贡献，在**它是唯一能在六个月内变成"已投出 / 在审 / 已接收"的东西**。博士申请和推荐信看的是闭环：你能把一个问题从数据做到审稿回复。一篇规范的小论文够用；没有论文是硬伤。所以"最强资产"这个说法改为"**最完整资产**"。

## 投之前必须补的（不补大概率被拒或退回）
1. **跑全部 10 个被试**（pooled + LOSO）。代码已经是自动化的，主要是算力和时间。
2. **正面回答声音混淆**：至少在讨论里写明，并给一个对照（例如用想象 trial 内部做"不同歌曲"的分类，或者只用想象段落）。
3. **期刊范围** ⚠️：PeerJ 主刊的官方范围是生物、环境、医学、健康科学，明确排除社会科学，神经科学"有机会但不保证"（[PeerJ aims and scope](https://www.peerj.com/about/aims-and-scope)）。一篇解码方法为主的论文更像 **PeerJ Computer Science**。投前发邮件问 editorial.support@peerj.com 或直接选 PeerJ CS。
4. PeerJ 只审"方法是否可靠"不审"是否有趣" ✅，这对本文有利。

## 一个能把阴性结果变成贡献的加法（可选，2–4 周）
跨被试失败是 BCI 领域的标准问题，标准答案是**对齐**：Euclidean Alignment（对原始信号，可接 EEGNet）或 Riemannian re-centering（对协方差，pyriemann）。加一组实验："对齐后 LOSO 能否从 0.52 抬起来"，论文就从"我们发现不行"变成"我们比较了三种跨被试方案"。这正好补 profile.md 里写的 BCI 技能缺口（CSP / 黎曼），也是给 Shamma、华工 BCI 中心看的那一行。参考：[Euclidean Alignment 系统评估](https://arxiv.org/html/2401.10746v4)、[EA 与 Label Alignment 综述](https://brain.ieee.org/newsletter/2020-issue-1/transfer-learning-for-brain-computer-interfaces-euclidean-alignment-and-label-alignment/)。
代价：投出从"几周内"推到 2026-12。收益：论文从"能发"变成"有一个方法比较"，并且你学会了 BCI 的基本功。

## 建议
- 最低限度（2–3 周）：补全 10 人 + 混淆讨论 + 改投 PeerJ CS。然后投。
- 推荐（4–6 周）：最低限度 + 一组对齐实验。12 月中前投出，仍在 Gate B 之前。
- 不建议：按六月版三人原样投。
