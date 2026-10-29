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

## 2026-10-29 · 十月版（manuscript_peerj.pdf，27 页）读后
**这已经不是六月那篇。** 题目改为 *Paired-trial grouping and validation sensitivity in cued and uncued music imagery decoding in OpenMIIR*；作者 Ruiting Chen（FSU）、Keling Wang（江苏第二师范）、Yutian Wang（通讯）。全部 10 个被试 ✅（六月的硬伤已补）。主对比从"听 vs 想象"换成 **cued vs uncued 想象（C23）**；"听 vs 想象"降为范围检查（F，pair 分组 0.606/0.648）。

### 核心发现（一句话版）
OpenMIIR 里每个刺激的 cued 与 uncued 想象是一对固定顺序、标签相反的物理 trial。按物理 trial 分折时，配对的另一半留在训练集，LR / RF 的平衡准确率**低于 0.5**（中位 0.469 / 0.448）；按"对"分折则回到 0.541 / 0.548。把训练集里的配对伙伴删掉，分数比精确匹配的对照删除高 0.067 / 0.097，十次分配全部成立。结论：分折单位必须和预测用途一致；低于 0.5 本身不是证据，匹配删除才是。固定条件顺序使条件与位置不可分，所以不做任何生理结论。

### 我的评价
- **性质变了**：从"音乐想象解码"变成"验证方法学案例研究"。这更稳，也更适合 PeerJ Computer Science；审稿标准"方法是否可靠"它能过。
- **严谨度高**：分折图在拟合前保存、精确匹配删除、训练标签打乱、纯设计基线、已知来源仿真、种子全记录。可复现性是强项。
- **最大问题是可读性**：每句话都带限定，故事被埋了。审稿人读完摘要说不出"发现了什么"。Background 没有一句讲"为什么要关心"，Results 数字堆砌。
- **定位要写清**：低于 0.5 的"反学习"在配对设计里已知（Jamalabadi 2016、Li 2021 已引）。新的是在这个语料上用匹配删除把"训练集成员"效应和"数据量 / 时间 / 标签"分开。这一段要正面写，不然审稿人一句"已知现象"就退。
- **范围检查没解释**：within-run vs between-run uncued（NC）0.87–0.93 几乎肯定是 block / 时间效应，应直说，它反而是支持论点的好例子。
- **主文细节过载**：种子数值（2026100500…）、SciPy 设置、四位小数（0.5572 vs 0.5555）应下沉到补充材料。
- **术语要一张表**：physical trial / presentation pair / allocation / C23 / F / NC / MET 一次定义。
- **投稿前必须填的空**：作者单位"to be confirmed"、作者贡献"draft for confirmation"、数据 DOI "will be entered"、公开仓库版本。合作者（Chen、K. Wang）必须书面确认贡献表。
- **AI 披露**：有，且诚实（Codex、Claude、Gemini 评审）。方法里那段可缩短，保留"作者负责核实"。

### 投前三件必做
1. 摘要和引言重写成"问题 → 现象 → 对照 → 结论"四句，让非 EEG 的审稿人也能复述。
2. 加一段"与已知反学习现象的关系"，明确新增的是匹配删除证据。
3. 填空：单位、贡献、DOI、仓库；合作者确认。

### 五件应做
NC 的解释；术语表；主文种子与小数下沉；Table 3 / 5 加一句"怎么读"；Figure 2 改标题为结论式（"Trial-grouped folds score below reference; pair-grouped do not"）。

### 对 Claire 的角度
不再是"同题解码"，而是"配对设计 + 固定顺序会让验证失真"的方法学提醒。她的 Neuroarts 想象研究是新采数据，**条件顺序要平衡**，这篇正好是反例。邮件改口：附这篇，说"这是我们在 OpenMIIR 上踩到的坑，可能对你的采集设计有用"。比"同题"更站得住，也更有用。
