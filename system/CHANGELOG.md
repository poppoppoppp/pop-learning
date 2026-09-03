# Pop Learning OS Changelog

系统 Bug 与版本变化记录。

---

# V1.4.2 — 2026-09-03

## SYSTEM BUG 006 — STATE_SOURCE 因代码块格式无法渲染

### 测试现场

V1.4.1 冷启动输出：

- PL-LOAD ✓ V1.4.1
- 正确 CHALLENGE
- 正确 STATE_BLOB
- `STATE_SOURCE =`

但 STATE_SOURCE 为空。

### 观察

整张 receipt 被放入 fenced code block。

### 根因

V1.4.1 的：

- “ATOMIC LOAD RECEIPT”
- “四字段块”
- fenced code 示例

共同诱导模型把 receipt 当代码块输出。

file citation 不能在代码块中正常渲染。

### 修复

V1.4.2：

1. Receipt 必须使用普通 Markdown
2. 严禁 fenced code block / inline code
3. STATE_SOURCE 必须真实渲染 current-turn file citation
4. 无法渲染则：
   `PL-LOAD FAIL: NO_RENDERED_CURRENT_TURN_CITATION`

---

## SYSTEM CHANGE 020 — Citation-Compatible Receipt

Load Receipt 从“代码块式四字段”改为：

> 普通 Markdown 四行收据。

---

## SYSTEM CHANGE 021 — Render Preflight

Preflight 不只检查字段存在，还检查：

> citation 是否实际可渲染。

---

## SYSTEM CHANGE 022 — Challenge Rotation

CURRENT_STATE 实质更新，因此 challenge 轮换为：

`PL142-AE7AFDCB`

---

# V1.4.1

修复 citation 作为第四必填字段，但格式示例导致 citation 渲染失败。
