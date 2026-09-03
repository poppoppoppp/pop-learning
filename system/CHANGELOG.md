# Pop Learning OS Changelog

这里记录：

> 教学系统自己的 Bug、修复和版本变化。

不把系统失败写成用户能力缺陷。

---

# V1.4 — 2026-09-03

## SYSTEM BUG 004 — 静态 PL-LOAD 字符串可以被照抄

### 测试

V1.3 冷启动回答末尾出现：

`PL-LOAD ✓ V1.3`

但没有：

> CURRENT_STATE 的本回合 GitHub 文件引用。

### 结论

Gate A FAIL。

说明：

> 固定字符串只能证明模型知道格式，不能证明实际 fresh-read。

### 修复

V1.4 加入 Load Receipt：

1. `PL-LOAD ✓ V1.4`
2. `LOAD_CHALLENGE`
3. `STATE_BLOB`
4. current-turn CURRENT_STATE file citation

四项组合验收。

---

## SYSTEM CHANGE 014 — LOAD_CHALLENGE

CURRENT_STATE 顶部新增：

`LOAD_CHALLENGE = PL14-EC78FCAD`

状态文件实质更新时更换。

用途：

> 检测 stale load。

不把它误称为单独的 fresh-load 证明。

---

## SYSTEM CHANGE 015 — STATE_BLOB receipt

要求返回：

> 当前 GitHub fetch_file 结果中的 blob SHA 前 8 位。

增加读取结果具体性。

---

## SYSTEM CHANGE 016 — Connector-specific Boot

BOOT POINTER 明确要求：

> 使用 connected GitHub capability。

普通 Web 搜索、Memory、旧聊天不能替代 LOAD。

---

## SYSTEM LIMITATION 002

V1.4 不是密码学证明。

Challenge / blob 在文件不变时会保持不变。

因此本回合 CURRENT_STATE 文件引用仍然是 Gate A 最关键证据。

---

# V1.3 — 2026-09-03

## SYSTEM BUG 003 — LOAD 不可验证

V1.3 引入：

- BOOT POINTER
- fresh LOAD
- `PL-LOAD ✓`
- current-turn citation 要求
- BOOT / LOAD 与 Teaching / Output 分离

真实测试发现：

> 模型执行了固定 `PL-LOAD ✓`，但遗漏 citation。

因此升级到 V1.4。
