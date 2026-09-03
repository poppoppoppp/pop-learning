# Current Learning State

Updated: 2026-09-03
Baseline: V1.4.3

# RUNTIME CARD

PROTOCOL = V1.4.3
LOAD_CHALLENGE = PL143-3E871B2B

## GATE A — BOOT / LOAD

任何技术、代码、AI、工程、工具链、项目原理相关回答前：

1. 使用 connected GitHub fresh-read：
   `poppoppoppp/pop-learning/learner/CURRENT_STATE.md`
2. 不允许用 Web、Memory、旧聊天、旧 citation 替代。
3. 从本回合 GitHub 返回结果读取：
   - LOAD_CHALLENGE
   - blob SHA
   - `Citation Marker`

# CITATION MARKER COPY

V1.4.2 的错误：

> 要求模型“确认 UI citation 已经渲染”。

模型无法在发送前检查发送后的 UI 渲染。

V1.4.3 改为一个模型在发送前真正能执行的动作：

> 找到本回合 GitHub 返回结果中的 `Citation Marker:`，把它后面的 marker 原样复制到最终回答。

例如工具结果如果显示：

`Citation Marker: <CURRENT-TURN-MARKER>`

则最终回答中的 STATE_SOURCE 必须直接使用：

`STATE_SOURCE = <CURRENT-TURN-MARKER>`

不要自己生成 marker。
不要写空白。
不要只写 CURRENT_STATE.md。
不要只写 GitHub URL。

## SOURCE-FIRST RECEIPT

成功标记必须最后输出。

最终回答末尾使用普通 Markdown，顺序固定：

STATE_SOURCE = <exact current-turn Citation Marker copied from GitHub result>  
CHALLENGE = <current LOAD_CHALLENGE>  
STATE_BLOB = <current blob SHA first 8 chars>  
PL-LOAD ✓ V1.4.3

为什么 PASS 放最后：

> 先完成 source，再允许宣布成功。

禁止把 receipt 放进代码块。

## FAIL

如果 GitHub 读取结果中没有可用的 `Citation Marker`：

`PL-LOAD FAIL: NO_CURRENT_TURN_CITATION_MARKER`

不得输出成功标记。

## Gate A PASS

必须同时满足：

1. STATE_SOURCE 使用本回合 GitHub 返回的 exact Citation Marker
2. CHALLENGE 正确
3. STATE_BLOB 正确
4. 最后一行才出现 `PL-LOAD ✓ V1.4.3`

---

## GATE B — TEACHING / OUTPUT

Gate A 通过后：

1. TASK ANSWER FIRST
2. 用户点名但不会的词可作为 OPAQUE LABEL
3. 默认最多 1 个新的 TEACH-NOW
4. 其他不必要技术支线 DEFER
5. OUTPUT LINT 失败则重写
6. 一个完整认知台阶，不一次跨多个未知技术体系

Gate B 在 V1.4.3 不修改。

---

# 当前能力策略

没有可靠证据，就不假装已经掌握。

# 当前明确不能作为 Safe Anchor

- 神经网络：EXPOSED / KNOWLEDGE GAP
- ONNX：EXPOSED
- 计算图：UNKNOWN
- Tensor / 张量：UNKNOWN / UNVERIFIED
- 矩阵：UNKNOWN / UNVERIFIED
- Attention / 注意力机制：UNKNOWN / UNVERIFIED

# 当前允许的基础日常锚点

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
- 一步一步处理事情
- 先做便宜检查，再决定是否投入更多资源

# 当前实战学习现场

项目：

`Mobile-VTON 手机本地真人换衣`

附近出现但不代表掌握：

- AI 模型
- PyTorch
- 神经网络
- ONNX
- 模型部署
- 模型权重

# 当前系统重点

V1.4.2 冷启动中：

- CHALLENGE 正确
- STATE_BLOB 正确
- STATE_SOURCE 为空

因此当前判断：

> fresh GitHub load 很可能已经工作；失败点是 citation proof 输出。

V1.4.3 只修：

> 不再要求模型预测 UI 渲染，而是复制工具返回的 exact Citation Marker。
