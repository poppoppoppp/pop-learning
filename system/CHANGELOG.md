# Pop Learning OS Changelog

这里记录：

> 教学系统自己的 Bug、修复和版本变化。

不把导师系统的失败写成用户能力缺陷。

---

# V1.3 — 2026-09-03

## SYSTEM BUG 003 — LOAD 不可验证

### 发现

前几次冷启动测试里，回答有时会声称：

> “我查了你的个人能力地图。”

但仅凭回答文字，无法证明：

- 本回合真的读取了 GitHub；
- 读取的是最新 CURRENT_STATE；
- 不是依赖旧上下文或模型记忆。

### 根因

V1.2 规定了：

> 技术回答前必须 LOAD。

但没有定义：

> 用户如何验证 LOAD 真的发生。

同时，GitHub 文件本身也无法保证全新对话会主动想起 GitHub。

### 修复

V1.3 引入三层架构：

1. Custom Instructions = BOOT POINTER
2. GitHub = Dynamic Truth
3. Current-turn GitHub citation = LOAD PROOF

并把系统拆成两个独立 Gate：

- Gate A：BOOT / LOAD
- Gate B：Teaching / Output

---

## SYSTEM CHANGE 011 — Verifiable LOAD

正常个性化技术回答必须带：

`PL-LOAD ✓ V1.3`

并附本回合 CURRENT_STATE 的 GitHub 文件引用。

没有 current-turn citation：

> 不算 LOAD PASS。

---

## SYSTEM CHANGE 012 — LOAD FAILURE Mode

如果 GitHub 读取失败：

`PL-LOAD FAIL`

允许一般事实回答。

禁止声称：

> 当前回答基于最新个人能力地图。

---

## SYSTEM CHANGE 013 — Runtime Card

`learner/CURRENT_STATE.md` 顶部改成短 Runtime Card。

目标：

- 每回合只需先读取一个小入口；
- 快速看到当前 Gate；
- 快速看到 Safe / Unsafe；
- 需要时再展开其他文件。

---

## SYSTEM LIMITATION 001 — BOOT persistence 不是 GitHub 自己能保证

GitHub 是真相源。

但：

> GitHub 不能自行唤醒一个完全没想起 Pop Learning OS 的新对话。

因此 BOOT POINTER 推荐放在 ChatGPT Custom Instructions。

Memory 可作为辅助，不作为唯一执行保障。

---

# V1.2 — 2026-09-03

## SYSTEM BUG 002

V1.1 有 SCAN OUTPUT，但第二次冷启动仍大量堆叠陌生术语。

V1.2 新增：

- TASK ANSWER FIRST
- OPAQUE LABEL
- TEACH-NOW budget
- OUTPUT LINT
- 单个认知台阶

结果：

> 教学输出仍需继续压力测试，但更底层的 LOAD 可验证性问题优先修复。

---

# V1.1 — 2026-09-03

## SYSTEM BUG 001

首次冷启动能读取能力地图，但仍大量引入未经验证术语。

V1.1 新增：

- SCAN INPUT
- BRIDGE PLAN
- DRAFT
- SCAN OUTPUT
- SAFE / TEACH-NOW / DEFER
- 原子命题状态
- 类比退出机制
