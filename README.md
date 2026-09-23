<img width="1823" height="1562" alt="Loomer" src="https://github.com/user-attachments/assets/9327bd80-3d70-4a3c-8537-e785c90af919" />
# Loomer

Keeley Loomer 单块效果器的 VST3 / Standalone 软件复刻。一块把 **op-amp fuzz** 和 **FV-1 数字混响**装进同一盒子的双引擎效果器，单声道。fuzz 与混响各有独立脚踏开关，可单独或组合使用。

## Fuzz 侧

Fuzz 是 op-amp Big Muff V4/V5 的白盒建模（MNA 逐采样非线性求解）。

| 旋钮 | 功能 | 音色 |
|---|---|---|
| **FUZZ** | 失真量 / 延音（= Big Muff 的 Sustain） | 拧大 → 更饱和、更压缩、延音更长，从轻微过载到厚实墙般的 fuzz |
| **FILTER** | 音色，**右转变亮**（单旋钮低通样式） | 左转 → 闷暗、毛毡般；右转 → 锐利、泛音多 |
| **LEVEL** | fuzz 输出音量 | 只控制 fuzz 侧响度，不影响失真度 |

**Voicing 拨档**（3 位，切换中频塑形曲线）：

- **FLAT** — 中频平直，最均衡，接近"中性"的 Muff；
- **FULL** — 中频饱满厚实，穿透力强，切进混音里更靠前；
- **SCOOP** — 中频挖空（凹陷最深），低频厚重、高频锐利，经典 Big Muff 的"scooped"音色，金属 / shoegaze 味。

## Reverb 侧

Reverb 是 Spin FV-1 (SPN1001) 的指令级仿真，三个程序（FOCUS / REVERSE / HALL）共用四个旋钮，但含义随模式变化。

| 旋钮 | FOCUS | REVERSE | HALL |
|---|---|---|---|
| **BLEND** | 干湿比（左全干 → 右全湿） | 同 | 同 |
| **DECAY** | 混响衰减 + 双延迟反馈量 | **8 档固定时间**（150/200/…/500 ms） | 混响衰减时间 |
| **WARMTH** | 音色（左亮右暗） | Jazzmaster 节奏档低通（最暗 156.6 Hz） | 同 FOCUS |
| **DEPTH** | 4 声部合唱深度 | 包络颤音的"摇把下压深度"（0–50 ms 时移） | 八度上移效果的量 |

> BLEND 是混响段自己的干湿比：拧到全干时 fuzz 仍在信号路径上，只减掉混响湿声。

## 三种模式

- **FOCUS** — *Soft Focus*。250 / 380 ms 双延迟并联 + 4 声部反相合唱，产生"不晃但很宽"的梦幻空间感，是 My Bloody Valentine《Loveless》那类 shoegaze 音墙的经典混响。DECAY 同时拉长延迟反馈与混响尾巴，DEPTH 增加合唱的失谐厚度。
- **REVERSE** — *反向混响*。读延迟线多个点、音量递增，每个音符后面跟一串**越来越响**的回声，像录音倒放一样"鼓"起来；DECAY 在 8 档固定时长间切换。弹重时 attack 触发的颤音让音高像摇把一样弯一下再回落，带 Midiverb Bloom 那种"融化"感。WARMTH 是 Jazzmaster 节奏档式的低沉低通。
- **HALL** — *大厅混响 + 上升八度*。混响输出送入八度上移再馈回输入，形成无限上升的八度回路，尾巴里八度音往上飘的 shimmer 质感；DEPTH 控制这个八度效果的可见程度。

## 路由与开关

- **ORDER 拨档**：`Fuzz → Reverb`（先失真再进混响，音墙更靠后）/ `Reverb → Fuzz`（先混响再失真，混响尾巴被 fuzz 压碎、更脏更靠前）。
- **脚踏**：Fuzz / Reverb 各一个，独立旁通。

