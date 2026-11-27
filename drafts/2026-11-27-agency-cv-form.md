# 录多教育联盟 CV 信息采集表：可粘贴的草稿（2026-11-27）

> 只写仓库里有记录的事实，不包装。【】里是我不知道、要你自己填的。写的是现在的真实状态（在审就写在审，进行中就写进行中）。

## 开头三个勾选（空表里已经预先勾了，要改）
| 题 | 空表预勾的 | 建议改成 |
|---|---|---|
| 一、是否接受包装 | 接受包装，接受因此产生的失真 | **不接受包装，但愿意配合补充真实素材** |
| 二、是否允许删减 | 允许，由写作老师决定 | **允许删减，需联系本人确认** |
| 三、原 CV 怎么用 | 允许挪用 | 没有旧版英文 CV，这题可不选或选"仅供参考" |

## 三、教育背景（由近及远）
| 院校 | 时间 | 专业 | GPA、课程 |
|---|---|---|---|
| Georgia Institute of Technology（佐治亚理工学院）| 08/2026 – 05/2028（预计）| M.S. in Music Technology（音乐科技，理学硕士）| 【GPA 待本学期出分】课程：MUSI 6003 Music Technology History and Repertoire；MUSI 6204 Computational Music Analysis（课名以成绩单为准）；MUSI 8001 Research Methods。2027 春已注册：MUSI 6001 Music Perception and Cognition 等 |
| Florida State University（佛罗里达州立大学）| 【月/年 – 月/年】| 【学位全称，如 M.M. / M.S. in Piano Performance，以学位证为准】| 【GPA /4.0】【主要课程】|
| 江苏第二师范学院 Jiangsu Second Normal University | 09/2021 – 06/2023 | 音乐学（师范），艺术学学士 | 【GPA 或均分 /100】【主要课程】|
| 江苏联合职业技术学院（常州幼儿师范学校办学点）| 09/2016 – 06/2021 | 学前教育（五年一贯制专科）| 【均分】|

## 四、研究兴趣
**关键词**
非侵入式脑机接口（non-invasive brain–computer interface）；脑电（EEG）；肌电（EMG）；神经信号解码与验证（neural decoding, cross-validation）；人机交互 / 人机器人交互（HCI / HRI）；音乐认知（music cognition）；音乐想象（musical imagery）；音乐 AI 评测（evaluation of music AI）

**具体方向的总结性描述**
我研究用脑电、肌电等非侵入式生理信号实现人与机器的交互，并关注这类系统的结果是否可靠。已有工作集中在两点：一是脑电解码的验证方法（在公开数据集 OpenMIIR 上发现配对试次的分折方式会使交叉验证结果失真）；二是人如何感知机器演奏的音乐（Shimon 机器人演奏的观众脑电研究）。博士阶段希望做非侵入式脑机接口与人机交互方向的研究，以音乐和机器人为主要应用场景。

## 五、学术项目
| 项目名称 | 时间 | 带头人及头衔 | 基金 | 简介、我的角色、方法 |
|---|---|---|---|---|
| 机器人演奏与人类演奏的观众脑电研究（Audience EEG responses to robotic vs. human music performance）【英文名以实验室为准】| 10/2026 – 至今 | Gil Weinberg，Professor，Georgia Tech Center for Music Technology【头衔请核对】| 【问导师：有无经费支持】| 比较观众观看机器人（Shimon）演奏与人类演奏时的脑电反应。**我是项目负责学生和第一作者**：负责研究设计、伦理审批（IRB）材料、数据采集与分析、论文写作。方法：脑电实验设计、MNE-Python。状态：【IRB 已提交 / 待提交】，计划 2027 年春采集数据并投稿 |
| OpenMIIR 音乐想象脑电解码的验证方法研究（Paired-trial grouping and validation sensitivity in music imagery decoding）| 【起始月/年】– 11/2026 | 自主课题；合作者 Ruiting Chen（广东工业大学，通讯作者）、Keling Wang（江苏第二师范学院）| 无 | 公开数据集 OpenMIIR（10 名被试）的二次分析。发现有提示与无提示想象试次成对出现时，按试次分折会使平衡准确率低于随机水平（0.469），按配对分折为 0.541；用"删除配对伙伴 vs 删除非伙伴"的匹配对照确认是训练集成员效应。**我是第一作者**：构思、方法、编程、分析、写作。方法：逻辑回归、随机森林、分组交叉验证、置换与打乱标签对照。可复现包已公开（Zenodo, doi:10.5281/zenodo.24048111）|
| 大语言模型奏鸣曲式分析的对照评测（Reading or remembering? Controls for language-model analyses of sonata form）| 【起始月/年】– 11/2026 | 自主课题；合作者 Ruiting Chen（通讯作者）| 无 | 用 27 个贝多芬、莫扎特钢琴奏鸣曲乐章，比较六个大模型在"给乐谱 / 只给曲名 / 匿名"三种条件下标注曲式边界的表现，区分模型是读谱还是记忆。**我是第一作者**：实验设计、实施、分析、写作 |
| 肌电 + 脑电控制机械臂（个人项目，Hybrid EMG–EEG control of a robot arm）| 12/2026 – 进行中 | 个人项目 | 无 | 在 SO101 六轴机械臂上实现肌电连续控制与脑电开关。此前已完成该机械臂的手势跟随、人脸检测与注视跟踪。状态：设备到位中，尚未完成，请按"进行中"写 |
| 乐谱小节号自动标注工具（measure-numbers）| 【起始月/年】– 10/2026 | 个人项目 | 无 | 上传乐谱 PDF，自动识别小节线并叠印小节号。两个小型卷积网络（BarlineNet、LineEndNet）加规则层；已上线，384 项测试通过 |

## 五、论文与发表
| 题目 | 摘要 | 发表情况 |
|---|---|---|
| Paired-trial grouping and validation sensitivity in cued and uncued music imagery decoding in OpenMIIR | 见上表第二行 | **未发表，投稿中**。作者：Yutian Wang（第一作者）, Keling Wang, Ruiting Chen（通讯作者）。【现状请自己填准：已转投 Royal Society Open Science / 准备转投】|
| Reading or remembering? Title-only and anonymous controls for language-model analyses of sonata form | 见上表第三行 | **未发表，在审**。Transactions of the International Society for Music Information Retrieval（TISMIR），2026-11-08 投稿。作者：Yutian Wang（第一作者）, Ruiting Chen（通讯作者）|
| 【实验室论文题目待定】| 见上表第一行 | **撰写中，尚未投稿**。第一作者 |

## 其余各栏我没有信息，要你填
- 一、基础信息；二、托福 / 雅思 / GRE 分数与日期。
- 六、工作 / 实习：教琴、助教、伴奏等都算，如实写。
- 七、奖项荣誉；八、技能：Python、PyTorch、scikit-learn、MNE-Python；机械臂与嵌入式入门；钢琴（表演硕士）。
- 九、个人优势；十、其他。

## 2026-11-27 补：来自我的作品集网站（2025-12 版）的素材
**开头第三题**：有旧材料了，就是这个网站。建议选"仅供参考，不可直接使用原表述"，因为网站还写着 FSU 在读，是申硕士时的口径。

**学术项目可再加两行（都是 FSU 期间的个人项目，如实写规模）**
| 项目 | 时间 | 说明 |
|---|---|---|
| 图像到音乐生成管线（Image to Music Generation）| 【月/年】| Python，Google Colab。用 BLIP 生成图像描述，再输入 Meta MusicGen Large 生成 30 秒音乐。个人项目，无基金 |
| 视听交互系统（Audiovisual Interaction）| 【月/年】| Max/MSP。摄像头输入实时控制声音合成参数，计算机视觉 + DSP。个人项目 |

**八、技能**：Python（PyTorch、scikit-learn、MNE-Python）；Max/MSP、Max for Live；Ableton Live、Studio One；录音与混音（多话筒录制、EQ、压缩）；音视频剪辑、After Effects；机械臂与嵌入式入门。乐器：钢琴（表演硕士），单簧管、中提琴。
**十、其他**：钢琴独奏（Carl Vine 第三钢琴奏鸣曲等）；原创作品（卡普斯汀风格拉格泰姆，有乐谱；Future Bass 电子音乐）；高中参加科技类比赛【名称、奖项待填】。
