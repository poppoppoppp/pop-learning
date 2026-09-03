# Pop Learning OS Changelog

这里记录：

> 教学系统自己的 Bug、修复和版本变化。

不把系统失败写成用户能力缺陷。

---

# V1.4.1 — 2026-09-03

## SYSTEM BUG 005 — Load Receipt 前三项正确，但 citation 被遗漏

### 测试结果

V1.4 冷启动回答正确输出：

- `PL-LOAD ✓ V1.4`
- `CHALLENGE = PL14-EC78FCAD`
- `STATE_BLOB = 5614b85a`

但用户提供原始 ChatGPT UI 截图确认：

> 回答末尾没有 CURRENT_STATE 的 current-turn file citation。

因此：

`Gate A = FAIL`

### 根因

V1.4 把 citation 写成：

> 三个文本字段之后“再附 citation”。

这允许模型先形成成功收据，再遗漏最后的 UI 引用。

### 修复

V1.4.1 引入：

1. `ATOMIC LOAD RECEIPT`
2. `STATE_SOURCE` 作为第四个必填字段
3. `RECEIPT PREFLIGHT`
4. 无 current-turn citation 时禁止输出成功标记
5. 固定失败码：
   `PL-LOAD FAIL: NO_CURRENT_TURN_CITATION`

---

## SYSTEM CHANGE 017 — STATE_SOURCE

成功收据必须包含：

`STATE_SOURCE = <current-turn CURRENT_STATE file citation>`

普通文字、URL、Web citation、旧 citation 都无效。

---

## SYSTEM CHANGE 018 — Receipt Preflight

发送最终回答前必须确认 citation 已实际渲染。

没有：

> 先撤销 success receipt，再输出 FAIL。

---

## SYSTEM CHANGE 019 — Challenge Rotation

CURRENT_STATE 实质更新，因此 challenge 从：

`PL14-EC78FCAD`

轮换为：

`PL141-98D762B0`

---

# V1.4 — 2026-09-03

## SYSTEM BUG 004 — 静态 PL-LOAD 字符串可以被照抄

V1.4 加入：

- LOAD_CHALLENGE
- STATE_BLOB
- current-turn citation 要求

真实测试证明前三项可以正确生成，但 citation 仍可能漏出，因此进入 V1.4.1。
