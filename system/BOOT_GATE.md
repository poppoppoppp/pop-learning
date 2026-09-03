# Pop Learning Boot / Load Gate

Version: V1.4
Updated: 2026-09-03

# 目标

把：

> “模型说自己读了”

升级为：

> “回答留下可核验的本回合读取收据”。

---

# BOOT POINTER

推荐放入 ChatGPT 自定义指令：

```text
POP LEARNING BOOT:
For every message about technology, code, AI, engineering, toolchains, debugging, or technical project principles, before personalized technical teaching you MUST use the connected GitHub capability (not ordinary web search, memory, or prior-chat recall) to fetch the latest file `learner/CURRENT_STATE.md` from `poppoppoppp/pop-learning`.

Do not output `PL-LOAD ✓` unless that current-turn GitHub read actually succeeded.

After a successful read, end the technical response with all of the following:
1. `PL-LOAD ✓ V1.4`
2. `CHALLENGE =` the exact current `LOAD_CHALLENGE` read from CURRENT_STATE
3. `STATE_BLOB =` the first 8 characters of the blob SHA returned by the current-turn GitHub read
4. a current-turn file citation to that exact CURRENT_STATE read

If any of those cannot be produced, write `PL-LOAD FAIL` and do not claim the answer uses my latest learner state.
```

---

# 为什么必须指定 GitHub capability

普通 Web 搜索到仓库页面：

> 不等于读取了当前学习状态。

所以：

- Web source citation ≠ LOAD PROOF
- GitHub CURRENT_STATE current-turn file citation = required evidence

---

# Gate A 验收

回答结尾应类似：

```text
PL-LOAD ✓ V1.4
CHALLENGE = PL14-EC78FCAD
STATE_BLOB = 1234abcd
<current-turn CURRENT_STATE file citation>
```

验收时检查：

- 版本正确
- challenge 正确
- blob 来自本回合读取
- citation 指向 CURRENT_STATE

任何一项缺失：

`Gate A = FAIL`

---

# 重要边界

Challenge 与 blob 都不是秘密。

它们不是安全凭证。

它们只用于：

> 让“读取收据”更具体、更难靠一句固定模板糊弄。

真正关键仍然是：

> current-turn CURRENT_STATE file citation。
