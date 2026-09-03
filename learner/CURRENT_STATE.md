# Current Learning State

Updated: 2026-09-03
Baseline: V1.4

# RUNTIME CARD

PROTOCOL = V1.4
LOAD_CHALLENGE = PL14-EC78FCAD

> `LOAD_CHALLENGE` 在每次 CURRENT_STATE 发生实质更新时更换。
> 它用于发现 stale load（读了旧状态），不是单独的 fresh-load 证明。

## GATE A — BOOT / LOAD

技术、代码、AI、工程、工具链、项目原理相关回答前：

1. 必须使用已连接的 GitHub 读取能力，fresh-read：
   `poppoppoppp/pop-learning/learner/CURRENT_STATE.md`
2. 不允许用普通 Web 搜索、旧聊天、Memory 或“我记得”替代这一步。
3. 读取成功后，从 GitHub 返回结果取得：
   - 当前 `PROTOCOL`
   - 当前 `LOAD_CHALLENGE`
   - 当前文件 blob SHA
   - 当前回合文件引用
4. 正常个性化技术回答末尾必须包含：

```text
PL-LOAD ✓ V1.4
CHALLENGE = <本回合读到的 LOAD_CHALLENGE>
STATE_BLOB = <本回合 GitHub 返回的 blob SHA 前 8 位>
```

并紧跟本回合 `CURRENT_STATE.md` 的 GitHub 文件引用。

5. 缺任何一项：
   `Gate A = FAIL`
6. GitHub 读取失败：
   `PL-LOAD FAIL`

## GATE A PASS 的必要条件

必须同时满足：

- `PL-LOAD ✓ V1.4`
- `CHALLENGE` 与当前 CURRENT_STATE 一致
- `STATE_BLOB` 来自本回合 GitHub 返回结果
- 存在本回合 CURRENT_STATE 文件引用

注意：

> `PL-LOAD ✓` 字样本身没有证明力。
> CHALLENGE 本身也没有证明力。
> 四项组合才作为当前系统的可验证收据。

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

V1.3 冷启动测试暴露：

- 新对话输出了 `PL-LOAD ✓ V1.3`
- 但没有 CURRENT_STATE 的本回合引用
- 因此无法证明实际 fresh-read
- 静态字符串可以被照抄，不能视作证明

V1.4 当前第一优先级：

> 把 LOAD 证明从“自我声明”升级为“多字段收据”。

BOOT / LOAD 与 Teaching / Output 继续分开验收。
