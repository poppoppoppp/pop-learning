# Current Learning State

Updated: 2026-09-03
Baseline: V1.2

# 总原则

这是技术对话优先读取的快速入口。

当前采取保守策略：

> 没有可靠证据，就不假装已经掌握。

用户当前明确把自己定位为计算机小白，希望通过真实项目快速形成真正的计算机与 AI 工程能力。

---

# 当前运行协议

技术回合使用：

`LOAD -> SCAN INPUT -> TASK ANSWER -> BRIDGE PLAN -> DRAFT -> OUTPUT LINT -> TEACH -> VERIFY -> RECORD -> UPDATE`

V1.2 的重点不是继续增加教学内容。

而是：

> 减少没有必要的新术语，并把出厂检查变成明确 PASS / FAIL。

---

# OUTPUT LINT 快速门禁

## 概念四分类

### SAFE

已经验证，可以直接作为解释基础。

### OPAQUE LABEL

用户已经点名、代码/日志必须引用，但尚未理解。

可以叫名字。

不能未经教学拿来解释别的未知知识。

### TEACH-NOW

这一轮确实必须新学。

普通回合默认最多：

`1`

### DEFER

当前不需要。

删掉、改成人话或延后。

---

# 草稿直接 FAIL 的情况

1. 助手主动引入的 TEACH-NOW 超过 1 个，且无不可拆分理由。
2. 用未知概念解释另一个未知概念。
3. 同一短段堆叠 2 个以上未经解释的非 SAFE 技术概念。
4. 某技术词删掉以后仍能正确回答当前问题，却没有 DEFER。
5. 解释链依赖尚未验证的前置知识。
6. 用户问项目决策，回答却被无必要的底层技术课淹没。

---

# 当前教学节奏

默认：

> 一个完整认知台阶，而不是一轮一大串知识，也不是每句话都停下来考试。

一个认知台阶可以包含：

- 人话解释
- 最小例子
- 项目作用
- 一个类比
- 必要边界

---

# 当前明确不能作为 Safe Anchor

## 神经网络

状态：

`EXPOSED / KNOWLEDGE GAP`

已明确发现：

用户无法直接理解“神经网络计算”。

Safe Anchor：

`NO`

---

## ONNX

状态：

`EXPOSED`

已经在 Mobile-VTON 手机部署项目中出现。

尚未建立可靠理解。

Safe Anchor：

`NO`

注意：

用户主动问 ONNX 时，`ONNX` 可以作为 OPAQUE LABEL 重复出现。

但不能用未掌握的“计算图、跨框架、中间表示”等词直接解释它。

---

## 计算图

状态：

`UNKNOWN`

Safe Anchor：

`NO`

---

## Tensor / 张量

状态：

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

---

## 矩阵

状态：

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

---

## Attention / 注意力机制

状态：

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

---

# 当前允许的基础日常锚点

当前可以安全直接使用：

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

更多技术 Safe Anchor 由真实证据逐渐点亮。

---

# 当前实战学习现场

项目：

`Mobile-VTON 手机本地真人换衣`

附近已经出现的名字包括：

- AI 模型
- PyTorch
- 神经网络
- ONNX
- 模型部署

注意：

> 出现过不等于掌握。

最近一次 V1.1 冷启动测试暴露：

回答项目策略问题时，又一次一次性引入：

- Python
- PyTorch
- GPU
- ONNX Runtime
- CPU
- NPU
- 特殊算子
- 动态逻辑
- 自定义模块
- CUDA
- 显存
- Android 等

因此继续 Mobile-VTON 时必须优先执行：

1. TASK ANSWER FIRST；
2. 用户点名的陌生词先作为 OPAQUE LABEL；
3. 默认最多 1 个新的 TEACH-NOW；
4. 其余无必要技术支线 DEFER；
5. OUTPUT LINT 失败则重写。
