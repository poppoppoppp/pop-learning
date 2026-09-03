# Current Learning State

Updated: 2026-09-03
Baseline: V1.1

# 总原则

这是技术对话优先读取的快速入口。

当前采取保守策略：

> 没有可靠证据，就不假装已经掌握。

用户当前明确把自己定位为计算机小白，希望通过真实项目快速形成真正的计算机与 AI 工程能力。

因此不能因为某个词以前聊过，就直接认为已经理解。

---

# 当前运行协议提醒

技术回合使用 V1.1：

`LOAD -> SCAN INPUT -> BRIDGE PLAN -> DRAFT -> SCAN OUTPUT -> TEACH -> VERIFY -> RECORD -> UPDATE`

其中 `SCAN OUTPUT` 是强制门禁。

回答前应把准备使用的知识型概念分为：

- SAFE：可直接使用
- TEACH-NOW：当前必须理解，先搭桥解释
- DEFER：当前不需要，删除或延后

如果草稿依赖尚未掌握的技术词解释另一个新技术词：

> 草稿必须重写。

如果 Safe Anchor 到目标概念之间还有未验证层级：

> 默认不要一次跨完所有层级。

---

# 当前明确不能作为 Safe Anchor

## 神经网络

状态：

`EXPOSED / KNOWLEDGE GAP`

已明确发现：

用户无法直接理解“神经网络计算”这个表达。

因此目前不能直接使用以下表达解释其他知识：

- 神经网络计算
- 神经网络结构
- 神经网络计算图

必须先建立更基础理解。

## ONNX

状态：

`EXPOSED`

已经在 Mobile-VTON 手机部署项目中出现。

但尚未正式建立可靠理解。

Safe Anchor：

`NO`

## 计算图

状态：

`UNKNOWN`

Safe Anchor：

`NO`

## Tensor / 张量

状态：

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

## 矩阵

状态：

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

## Attention / 注意力机制

状态：

`UNKNOWN / UNVERIFIED`

Safe Anchor：

`NO`

---

# 当前允许的基础日常锚点

V1.1 不根据过去压缩记忆批量认定技术能力。

当前可以安全使用的普通概念包括：

- 文件
- 文件夹
- 图片
- 手机
- 电脑
- App
- 输入
- 输出
- “一步一步处理事情”这一日常概念

更具体技术知识将在真实项目中逐渐验证。

---

# 当前第一个实战学习现场

项目：

`Mobile-VTON 手机本地真人换衣`

目前附近出现的重要技术词：

- AI 模型
- PyTorch
- 神经网络
- ONNX
- 模型部署

这些“出现过”不等于已经掌握。

继续项目时：

1. 先从当前 Safe Anchor 找最近起点；
2. 一次只补当前必要层级；
3. 不把 PyTorch、CUDA、NPU、推理引擎等词因为“技术上相关”就一次全部塞进回答；
4. 每次输出前执行 SCAN OUTPUT。
