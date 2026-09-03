# Current Learning State

Updated: 2026-09-03
Baseline: V1.4.2

# RUNTIME CARD

PROTOCOL = V1.4.2
LOAD_CHALLENGE = PL142-AE7AFDCB

> LOAD_CHALLENGE 在 CURRENT_STATE 实质更新时轮换。
> 它用于发现 stale load，不是单独的 fresh-load 证明。

## GATE A — BOOT / LOAD

任何技术、代码、AI、工程、工具链、项目原理相关回答前：

1. 必须使用已连接的 GitHub 读取能力 fresh-read：
   `poppoppoppp/pop-learning/learner/CURRENT_STATE.md`
2. 不允许用普通 Web 搜索、旧聊天、Memory、旧 citation 或“我记得”替代。
3. 读取成功后取得：
   - 当前 PROTOCOL
   - 当前 LOAD_CHALLENGE
   - 当前文件 blob SHA
   - 本回合 CURRENT_STATE 文件引用

## CITATION-COMPATIBLE LOAD RECEIPT

成功收据由四个字段组成，但：

> **绝对禁止把收据放进 fenced code block / 三反引号代码块。**

原因：

> file citation 是富引用 UI，代码块会阻止它正常渲染。

最终回答末尾必须在普通 Markdown 中直接输出四项：

PL-LOAD ✓ V1.4.2  
CHALLENGE = <本回合 CURRENT_STATE 中的 LOAD_CHALLENGE>  
STATE_BLOB = <本回合 GitHub 返回 blob SHA 前 8 位>  
STATE_SOURCE = <本回合 CURRENT_STATE file citation>

### STATE_SOURCE 硬规则

STATE_SOURCE 必须：

- 出现在普通 Markdown；
- 不得位于反引号或代码围栏内；
- 紧跟本回合 CURRENT_STATE file citation；
- 引用必须真实渲染为可点击 / 可识别的文件引用。

以下全部无效：

- `STATE_SOURCE =` 后为空；
- 普通文字 CURRENT_STATE.md；
- GitHub URL；
- 普通 Web citation；
- 旧回合 file citation；
- citation 被包进代码块导致没有渲染。

### RECEIPT PREFLIGHT

发送最终回答前：

1. 先确认 GitHub fresh-read 已成功；
2. 再确认当前 citation 可作为普通 Markdown file citation 输出；
3. 只有确认可输出时才打印 `PL-LOAD ✓ V1.4.2`；
4. 如果 citation 无法渲染，禁止打印成功标记，改为：

`PL-LOAD FAIL: NO_RENDERED_CURRENT_TURN_CITATION`

并且不得声称回答使用了最新个人能力地图。

### Gate A PASS

必须同时满足：

1. `PL-LOAD ✓ V1.4.2`
2. CHALLENGE 与当前 CURRENT_STATE 一致
3. STATE_BLOB 来自本回合 GitHub fetch
4. STATE_SOURCE 是普通 Markdown 中真实渲染的本回合 CURRENT_STATE file citation

缺任一项：

`Gate A = FAIL`

---

## GATE B — TEACHING / OUTPUT

Gate A 通过后：

1. TASK ANSWER FIRST
2. 用户点名但不会的词可作为 OPAQUE LABEL
3. 默认最多 1 个新的 TEACH-NOW
4. 其他不必要技术支线 DEFER
5. OUTPUT LINT 失败则重写
6. 一个完整认知台阶，不一次跨多个未知技术体系

---

# 当前能力策略

采取保守策略：

> 没有可靠证据，就不假装已经掌握。

---

# 当前明确不能作为 Safe Anchor

## 神经网络

状态：

`EXPOSED / KNOWLEDGE GAP`

Safe Anchor：

`NO`

已知问题：

用户无法直接理解“神经网络计算”。

---

## ONNX

状态：

`EXPOSED`

Safe Anchor：

`NO`

允许：

`ONNX` 作为用户点名时的 OPAQUE LABEL。

禁止：

用尚未掌握的“计算图、跨框架、中间表示”等词直接解释它。

---

## 计算图

`UNKNOWN`

Safe Anchor：

`NO`

---

## Tensor / 张量

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

---

## 矩阵

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

---

## Attention / 注意力机制

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

---

# 当前允许的基础日常锚点

当前可安全直接使用：

- 文件
- 文件夹
- 图片
- 手机
- 电脑
- App
- 输入
- 输出
- 时间
- 花费
- 风险
- “一步一步处理事情”
- “先做便宜检查，再决定是否投入更多资源”这一日常决策逻辑

更具体的技术 Safe Anchor 由真实证据逐渐点亮。

---

# 当前实战学习现场

项目：

`Mobile-VTON 手机本地真人换衣`

附近已经出现但不代表掌握的名字：

- AI 模型
- PyTorch
- 神经网络
- ONNX
- 模型部署
- 模型权重

---

# 当前系统重点

V1.4.1 冷启动测试：

- PL-LOAD 正确
- CHALLENGE 正确
- STATE_BLOB 正确
- STATE_SOURCE 字段出现
- 但 STATE_SOURCE 为空

观察到整张收据被模型输出在 fenced code block 中。

根因：

> V1.4.1 用“block / 四字段块”的语言和代码围栏示例，诱导模型把富 file citation 放进代码块；citation 无法正常渲染。

V1.4.2 只修：

> 收据必须在普通 Markdown 中输出，严禁代码块。

Gate B 不变。
