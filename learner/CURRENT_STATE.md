# Current Learning State

Updated: 2026-09-03
Baseline: V1.3

# RUNTIME CARD

PROTOCOL = V1.3

## GATE A — BOOT / LOAD

技术、代码、AI、工程、工具链、项目原理相关回答前：

1. fresh-read `learner/CURRENT_STATE.md`
2. 没有 fresh LOAD，不声称使用最新个人能力地图
3. 正常个性化技术回答末尾必须有：
   `PL-LOAD ✓ V1.3`
4. 必须附带本回合 CURRENT_STATE 的 GitHub 文件引用
5. 读取失败则写：
   `PL-LOAD FAIL`

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

此前 V1.1 / V1.2 冷启动测试暴露：

- 能找到能力地图，不等于会严格遵守教学门禁；
- 回答可能声称“查过能力地图”，但缺乏可验证 LOAD 证据；
- OUTPUT LINT 仍需后续继续压力测试。

V1.3 当前第一优先级：

> 先证明每个技术回合真的 LOAD，再评教学质量。

BOOT / LOAD 与 Teaching / Output 必须分开验收。
