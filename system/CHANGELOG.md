# Pop Learning OS Changelog

这里记录：

> 教学系统自己的 Bug、修复和版本变化。

不把导师系统的失败写成用户能力缺陷。

---

# V1.2 — 2026-09-03

## SYSTEM BUG 002 — V1.1 有门禁文本，但仍未真正限制输出

### 测试现场

第二次新对话冷启动测试中，用户问：

> 为什么 Mobile-VTON 要先做 ONNX 导出可行性测试，而不是直接下载完整模型跑？

回答的项目判断本身正确：

- 先做便宜检查；
- 提前发现可能让后续投入白费的硬障碍；
- 再决定是否下载完整模型并复现。

### 失败现象

回答仍一次性引入大量未验证技术概念，包括：

- Python
- PyTorch
- GPU
- ONNX Runtime
- CPU
- NPU
- PyTorch 操作
- 特殊算子
- 动态逻辑
- 自定义模块
- CUDA
- 显存
- 完整推理
- Android

这直接违反 V1.1 已写明的：

- SCAN OUTPUT
- 单层教学
- DEFER

### 根因

V1.1 虽然把 SCAN OUTPUT 称为“强制门禁”，但判断标准仍主要是自然语言原则。

缺少：

- 明确新概念数量预算；
- 用户点名陌生词与真正教学概念的区别；
- 对“项目决策问题先回答决策层”的优先级；
- 可直接触发 DRAFT FAIL 的机械条件。

### 修复

V1.2 新增：

1. `TASK ANSWER FIRST`
2. `OPAQUE LABEL`
3. 默认每回合最多 `1` 个 assistant-introduced `TEACH-NOW`
4. `OUTPUT LINT` 六类明确 FAIL 条件
5. “单层教学”重定义为“单个完整认知台阶”

---

## SYSTEM CHANGE 006 — OPAQUE LABEL

用户主动点名、代码或日志必须引用的陌生词：

可以作为名称存在。

但：

> 名字出现不等于已经掌握，也不能未经解释承担知识地基。

---

## SYSTEM CHANGE 007 — 新技术概念预算

普通技术回合：

`assistant-introduced TEACH-NOW <= 1`

只有真正不可拆分时允许 2 个。

用户主动点名的 OPAQUE LABEL 不计入教学预算。

---

## SYSTEM CHANGE 008 — TASK ANSWER FIRST

技术项目里的每个问题不都需要展开底层技术。

如果用户先问：

- 顺序
- 风险
- 方案
- 下一步
- 为什么先 A 后 B

先用 Safe Anchor 回答真正的决策问题。

再判断是否需要补一个技术台阶。

---

## SYSTEM CHANGE 009 — OUTPUT LINT

新增六类直接失败条件：

1. TEACH-NOW 超预算
2. 陌生词解释陌生词
3. 陌生词串
4. 无必要技术支线
5. 前置知识断层
6. 项目问题被技术课淹没

触发即：

`DRAFT FAIL -> REWRITE`

---

## SYSTEM CHANGE 010 — 单个认知台阶

不把教学变成：

> 每句话都停下来考试。

一个认知台阶可以完整包含：

- 人话解释
- 最小例子
- 当前项目作用
- 类比
- 边界

限制的是：

> 一轮不要跨进多个新的未知技术体系。

---

# V1.1 — 2026-09-03

## SYSTEM BUG 001 — 冷启动后仍然堆叠陌生术语

### 测试现场

首次新开对话后，系统成功：

- 找到 GitHub 能力地图；
- 读取 `CURRENT_STATE.md`；
- 识别 ONNX 为 `EXPOSED`；
- 知道计算图、Tensor 不能直接作为 Safe Anchor；
- 主动开始教学；
- 主动设计验证。

### 失败现象

回答仍然引入多项未经验证概念，例如：

- PyTorch
- Python 环境
- CUDA
- 模型参数
- ONNX Runtime
- NPU
- 推理引擎
- `.pth`

### V1.1 修复

新增：

- SCAN INPUT
- BRIDGE PLAN
- DRAFT
- SCAN OUTPUT
- SAFE / TEACH-NOW / DEFER
- 单层教学
- 原子命题状态
- 类比退出机制
- 系统 Bug 与学习证据分离

### V1.1 结果

第二次冷启动证明：

> 原则方向正确，但门禁仍不够机械。

因此进入 V1.2。
