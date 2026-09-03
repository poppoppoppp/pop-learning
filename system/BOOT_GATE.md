# Pop Learning Boot / Load Gate

Version: V1.3
Updated: 2026-09-03

# 为什么需要这层

GitHub 是动态真相源，但 GitHub 文件本身不能保证一个全新 ChatGPT 对话会主动想起去读它。

所以系统拆成：

```text
Custom Instructions
        ↓
BOOT POINTER
        ↓
GitHub CURRENT_STATE
        ↓
fresh LOAD
        ↓
LOAD PROOF
        ↓
个性化技术回答
```

---

# BOOT POINTER

推荐放入 ChatGPT 自定义指令的最小启动规则：

```text
POP LEARNING BOOT:
Whenever my message is about technology, code, AI, engineering, toolchains, debugging, or technical project principles, before giving personalized technical teaching, first read the latest learner state from the GitHub repository `poppoppoppp/pop-learning`, file `learner/CURRENT_STATE.md`. Treat GitHub as the dynamic source of truth for what I actually know. Do not infer mastery merely from past exposure. If a fresh read succeeds, end the technical response with `PL-LOAD ✓` and a current-turn citation to CURRENT_STATE. If the fresh read fails, write `PL-LOAD FAIL` and do not claim the answer is based on my latest learner state.
```

这段只负责“唤醒”。

完整教学规则仍然在 GitHub。

---

# 为什么不用 Memory 单独承担

Memory 可以帮助跨对话保留有用上下文，但系统不把它当成唯一的强制启动机制。

原因：

- 动态能力状态会不断更新；
- 我们需要 GitHub 可审计历史；
- 我们需要本回合 fresh LOAD 的证据；
- “模型记得”不能代替“本回合读取了最新状态”。

---

# LOAD PROOF

个性化技术回答正常结束时：

`PL-LOAD ✓ V1.3`

并带：

> 本回合读取 `learner/CURRENT_STATE.md` 后产生的 GitHub 文件引用。

没有引用：

> 不能判定 LOAD PASS。

---

# LOAD FAILURE

GitHub 读取失败：

`PL-LOAD FAIL`

此时：

- 可以回答一般事实；
- 可以处理不依赖学习地图的问题；
- 不得声称基于最新能力地图分层教学；
- 不得假装知道最新 Safe Anchor。

---

# 验收方式

每个新技术对话先只验 Gate A：

## Gate A

是否出现：

- `PL-LOAD ✓ V1.3`
- 本回合 CURRENT_STATE GitHub 引用

没有：

`BOOT/LOAD FAIL`

有：

再进入 Gate B。

## Gate B

再检查：

- TASK ANSWER FIRST
- 概念预算
- DEFER
- OUTPUT LINT
- VERIFY / RECORD / UPDATE
