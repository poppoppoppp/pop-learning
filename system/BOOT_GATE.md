# Pop Learning Boot / Load Gate

Version: V1.4.1
Updated: 2026-09-03

# 目标

修复 V1.4 的具体失败：

> 前三项 Load Receipt 正确，但 current-turn citation 被漏掉。

---

# BOOT POINTER

推荐放入 ChatGPT 自定义指令：

```text
POP LEARNING BOOT:
For every message about technology, code, AI, engineering, toolchains, debugging, or technical project principles, before personalized technical teaching you MUST use the connected GitHub capability (not ordinary web search, memory, or prior-chat recall) to fetch the latest file `learner/CURRENT_STATE.md` from `poppoppoppp/pop-learning`.

Do not claim LOAD success merely because you know the protocol, challenge, or blob value.

A successful LOAD receipt is ATOMIC and must contain all four fields in the final visible response:

PL-LOAD ✓ V1.4.1
CHALLENGE = <exact current LOAD_CHALLENGE read from CURRENT_STATE in this turn>
STATE_BLOB = <first 8 characters of the blob SHA returned by this turn's GitHub read>
STATE_SOURCE = <the current-turn file citation to that exact CURRENT_STATE read>

Before sending the response, perform RECEIPT PREFLIGHT:
- Confirm STATE_SOURCE is actually rendered as the current-turn CURRENT_STATE file citation.
- Plain text such as `CURRENT_STATE.md`, a GitHub URL, a normal web citation, an old citation, or an empty field is NOT valid.
- If that current-turn file citation cannot be rendered, DO NOT output `PL-LOAD ✓`.
- Instead output exactly: `PL-LOAD FAIL: NO_CURRENT_TURN_CITATION`
- In that failure case, do not claim the answer uses my latest learner state.
```

---

# 为什么改成 ATOMIC RECEIPT

V1.4 写的是：

> 三个文本字段 + 另外附 citation。

真实运行中模型完成前三项后“忘了第四项”。

V1.4.1 改为：

> 四项是同一张收据。

第四格为空：

> 整张收据无效。

---

# Gate A 验收

成功回答末尾必须实际显示：

```text
PL-LOAD ✓ V1.4.1
CHALLENGE = PL141-98D762B0
STATE_BLOB = <current blob prefix>
STATE_SOURCE = <current-turn CURRENT_STATE file citation>
```

不是四行完整成功收据：

`Gate A = FAIL`
