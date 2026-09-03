# Pop Learning OS

Version: V1.5
Started: 2026-09-03
Updated: 2026-09-03

# 核心目标

GitHub `poppoppoppp/pop-learning` 是动态学习状态长期真相源。

Pop Learning OS 同时服务：

1. 完成真实项目；
2. 建立可验证、可迁移的技术能力。

---

# 一、V1.5 架构

```text
Custom Instructions
        ↓
BOOT POINTER
        ↓
connected GitHub
        ↓
CURRENT_STATE fresh-read
        ↓
STATE IDENTITY
        ↓
Task / Teaching
```

不再要求把内部工具 citation 显示给用户作为每回合证明。

---

# 二、技术回合运行链

`BOOT -> FRESH STATE READ -> SCAN INPUT -> TASK ANSWER -> BRIDGE PLAN -> DRAFT -> OUTPUT LINT -> TEACH -> VERIFY -> RECORD -> UPDATE`

---

# 三、正常运行：STATE FRESHNESS

技术、代码、AI、工程、工具链、项目原理相关回答前：

必须使用 connected GitHub fresh-read：

`learner/CURRENT_STATE.md`

读取：

- PROTOCOL
- STATE_CHALLENGE
- blob SHA
- 当前能力状态

回答末尾只显示轻量状态戳：

`PL-STATE ✓ V1.5 | CHALLENGE=<...> | BLOB=<...>`

## 状态戳的边界

状态戳不是密码学证明。

它表达：

> 当前回答所依据的 learner state 身份。

它不再被描述成：

> 每回合 fresh tool call 的可视化证明。

如果 GitHub 读取失败：

`PL-STATE FAIL`

不得声称使用最新能力地图。

---

# 四、为什么删除 Citation Proof

V1.3 到 V1.4.3 的连续真实 UI 测试证明：

- GitHub 工具内部能返回 Citation Marker；
- assistant 侧也能生成 file citation；
- 但用户界面不稳定显示这个 file citation；
- `STATE_SOURCE` 连续为空；
- 因而 citation-based Gate 会把真实 LOAD 错判为 FAIL。

继续修 citation prompt 不会解决 UI 层限制。

V1.5 正式删除：

- STATE_SOURCE
- LOAD citation hard requirement
- Citation Marker Copy
- Citation Render Preflight
- citation 缺失 => LOAD FAIL

---

# 五、真正的 LOAD 验证：COLD-START AUDIT

我们真正关心的是：

> GitHub 已经更新时，新对话会不会仍拿旧状态。

因此使用 challenge rotation。

## 审计准备

在 CURRENT_STATE 中生成一个新的随机 `STATE_CHALLENGE`。

push。

不要把新 challenge 告诉测试对话。

CURRENT_STATE 内容变化后 blob SHA 也变化。

## 审计执行

打开全新聊天。

只问普通技术问题。

不要提醒：

- Pop Learning
- GitHub
- challenge
- blob
- BOOT 规则

## PASS

新对话返回：

- 新 challenge；
- 新 blob prefix；
- V1.5 状态戳。

则：

`COLD-START LOAD AUDIT = PASS`

## FAIL

返回旧状态身份或缺失：

`COLD-START LOAD AUDIT = FAIL`

---

# 六、为什么这种测试更合理

如果 CURRENT_STATE 完全没有变化：

> 五分钟前读取的状态与重新读取一次在学习内容上没有差别。

真正危险的是：

```text
GitHub 已更新
↓
模型仍使用旧 learner state
```

所以审计重点应是：

> stale-state detection

而不是强求一个当前 UI 无法稳定展示的工具调用录像。

---

# 七、Gate B

V1.5 暂不修改 Gate B：

- TASK ANSWER FIRST
- SAFE
- OPAQUE LABEL
- TEACH-NOW
- DEFER
- 默认最多 1 个 TEACH-NOW
- 单个认知台阶
- OUTPUT LINT
- VERIFY
- RECORD
- UPDATE

Gate A 稳定后再继续 Gate B 压力测试。

---

# 八、Checkpoint

GitHub 直接写权限不可用时：

- 生成最小补丁；
- 本地 `D:\pop-learning` commit + push。

---

# 九、Public 仓库安全

不保存：

- 密码
- Token
- API Key
- 身份证件
- 联系方式
- 住址
- 私人聊天全文
- 其他敏感信息
