# Pop Learning OS

Version: V1.4
Started: 2026-09-03
Updated: 2026-09-03

# 核心目标

这个仓库记录：

> pop 当前真正理解了什么、实际会做什么、哪里仍然不懂，以及这些判断有什么证据。

真实项目同时服务：

1. 项目完成；
2. 独立技术能力增长。

---

# 一、系统分层

```text
Custom Instructions
        ↓
BOOT POINTER
        ↓
GitHub CURRENT_STATE
        ↓
fresh LOAD
        ↓
LOAD RECEIPT
        ↓
Gate A PASS
        ↓
Teaching / Output Gate
```

GitHub 仓库：

`poppoppoppp/pop-learning`

是动态学习状态长期真相源。

---

# 二、V1.4 运行链

`BOOT -> LOAD GATE -> LOAD RECEIPT -> SCAN INPUT -> TASK ANSWER -> BRIDGE PLAN -> DRAFT -> OUTPUT LINT -> TEACH -> VERIFY -> RECORD -> UPDATE`

---

# 三、LOAD GATE

技术、代码、AI、工程、工具链、项目原理相关回答前：

必须使用已连接 GitHub 能力 fresh-read：

`learner/CURRENT_STATE.md`

不得使用以下内容替代 fresh-read：

- 普通 Web 搜索
- 旧聊天
- Memory
- 旧 citation
- 模型自称“我已经查过”
- 以前读过的 CURRENT_STATE

读取失败：

`PL-LOAD FAIL`

不得声称基于最新个人能力地图教学。

---

# 四、V1.4 LOAD RECEIPT

V1.3 的问题：

> `PL-LOAD ✓` 是固定字符串，模型可以照抄。

因此 V1.4 要求回答末尾同时提供：

```text
PL-LOAD ✓ V1.4
CHALLENGE = <CURRENT_STATE 当前 LOAD_CHALLENGE>
STATE_BLOB = <GitHub 本回合返回 blob SHA 前 8 位>
```

并附：

> 本回合 `learner/CURRENT_STATE.md` 文件引用。

Gate A 只有四项同时存在才 PASS。

---

# 五、LOAD_CHALLENGE 的作用和边界

`LOAD_CHALLENGE`：

- 放在 CURRENT_STATE 顶部；
- CURRENT_STATE 实质更新时轮换；
- 用来发现 stale load。

它不是单独的 fresh-load 证明。

原因：

> 旧对话可能记得旧 challenge。

因此：

`CHALLENGE != citation`

挑战码不能代替本回合文件引用。

---

# 六、STATE_BLOB

GitHub 读取文件时会返回当前文件 blob SHA。

回答只需返回前 8 位。

作用：

- 增加读取结果的具体性；
- 帮助发现读错文件 / 旧状态；
- 与 challenge、citation 形成组合证据。

STATE_BLOB 也不能单独替代 citation。

---

# 七、Gate A 判定

## PASS

必须同时满足：

1. fresh-read CURRENT_STATE
2. 正确 `PL-LOAD ✓ V1.4`
3. 正确当前 `CHALLENGE`
4. 本回合 GitHub 返回的 `STATE_BLOB`
5. 本回合 CURRENT_STATE 文件引用

## FAIL

以下任一即 FAIL：

- 只有 `PL-LOAD ✓`
- 有 challenge 没 citation
- 有 citation 但不是 CURRENT_STATE
- blob 与当前读取结果不一致
- 使用 Web GitHub 页面代替连接器读取
- 读取失败却仍声称使用最新能力地图

---

# 八、Gate B

Gate A PASS 后才验：

- TASK ANSWER FIRST
- SAFE / OPAQUE LABEL / TEACH-NOW / DEFER
- 默认最多 1 个 TEACH-NOW
- 单个认知台阶
- OUTPUT LINT
- VERIFY
- RECORD
- UPDATE

Gate A FAIL 时：

> 不对 Gate B 给出“系统通过”结论。

---

# 九、系统限制

当前机制提高“有没有 fresh-read”的可验证性，但不是密码学证明。

尤其：

- challenge 在状态更新之间保持不变；
- blob 在文件未变化时保持不变；
- 所以真正最重要的仍然是本回合 CURRENT_STATE 文件引用。

系统不夸大保证。

---

# 十、Checkpoint 与持久化

如果 GitHub 写权限不可用：

- 正常项目继续；
- 合适 checkpoint 生成最小补丁；
- 由本地 `D:\pop-learning` commit + push。

---

# 十一、Public 仓库安全

严禁保存：

- 密码
- Token
- API Key
- 身份证件
- 联系方式
- 住址
- 私人聊天全文
- 私人项目秘密
- 其他敏感信息
