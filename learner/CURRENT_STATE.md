# Current Learning State

Updated: 2026-09-03
Baseline: V1.5

# RUNTIME CARD

PROTOCOL = V1.5
STATE_CHALLENGE = PL15A-C2F224B6

## GATE A — STATE FRESHNESS

任何技术、代码、AI、工程、工具链、项目原理相关回答前：

1. 使用 connected GitHub fresh-read：
   `poppoppoppp/pop-learning/learner/CURRENT_STATE.md`
2. 不允许用普通 Web、Memory、旧聊天或旧状态替代这一步。
3. 从本回合 GitHub 返回结果读取：
   - 当前 `PROTOCOL`
   - 当前 `STATE_CHALLENGE`
   - 当前文件 blob SHA
4. 正常技术回答末尾只输出一个轻量状态戳：

`PL-STATE ✓ V1.5 | CHALLENGE=<current> | BLOB=<current blob SHA first 8>`

5. GitHub 读取失败时：

`PL-STATE FAIL`

并且不得声称回答基于最新个人能力地图。

## 重要语义

`PL-STATE ✓` 的含义是：

> 回答声称自己使用的学习状态身份是当前这份 GitHub 状态。

它不再声称：

> “这行文本本身证明了本回合一定发生了工具调用。”

我们不再伪造一个 UI 无法稳定承载的“每回合工具调用证明”。

---

# COLD-START AUDIT

真正要验证：

> 新对话是否会自动去 GitHub LOAD

使用审计流程，而不是依赖 citation UI。

## 审计前

1. 在 CURRENT_STATE 中把 `STATE_CHALLENGE` 换成全新的随机值；
2. push 到 GitHub；
3. 不把新 challenge 告诉被测试的新对话；
4. 因文件发生变化，blob SHA 也会随之变化。

## 审计

开一个全新对话。

不提：

- Pop Learning
- challenge
- blob
- GitHub 读取规则

只问正常技术问题。

## PASS

如果新对话返回：

- 当前新 challenge；
- 当前新 blob 前 8 位；
- `PL-STATE ✓ V1.5`

则：

`COLD-START LOAD AUDIT = PASS`

因为它拿到了刚刚更新、没有在测试对话中提供的新状态身份。

## FAIL

返回旧 challenge、旧 blob、缺失状态戳，或 GitHub 读取失败：

`COLD-START LOAD AUDIT = FAIL`

---

# 为什么 V1.5 删除 STATE_SOURCE

V1.4.x 连续测试证明：

- GitHub 返回内部 Citation Marker；
- 但用户当前 ChatGPT UI 不稳定展示 file citation；
- 即使 assistant 内部有 file citation，截图中 `STATE_SOURCE` 仍为空；
- 因此把 UI citation 当作 Gate A 必要条件，会产生假失败。

所以 V1.5 删除：

- STATE_SOURCE
- Citation Marker Copy
- Citation Render Preflight
- “没有 citation 就 PL-LOAD FAIL”的规则

不再修这一层。

---

## GATE B — TEACHING / OUTPUT

Gate A 的状态读取完成后：

1. TASK ANSWER FIRST
2. 用户点名但不会的词可作为 OPAQUE LABEL
3. 默认最多 1 个新的 TEACH-NOW
4. 其他不必要技术支线 DEFER
5. OUTPUT LINT 失败则重写
6. 一个完整认知台阶，不一次跨多个未知技术体系

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

V1.5 当前优先级：

1. 正常技术回合继续 fresh-read GitHub；
2. 不再尝试用不稳定 UI citation 证明每次工具调用；
3. 用 challenge + blob 的轮换测试审计 cold-start freshness；
4. Gate A 稳定后重新处理 Gate B 教学质量。
