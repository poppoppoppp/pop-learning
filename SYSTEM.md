# Pop Learning OS

Version: V1.4.1
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
ATOMIC LOAD RECEIPT
        ↓
Gate A PASS
        ↓
Teaching / Output Gate
```

GitHub 仓库：

`poppoppoppp/pop-learning`

是动态学习状态长期真相源。

---

# 二、V1.4.1 运行链

`BOOT -> LOAD GATE -> BUILD RECEIPT -> RECEIPT PREFLIGHT -> SCAN INPUT -> TASK ANSWER -> BRIDGE PLAN -> DRAFT -> OUTPUT LINT -> TEACH -> VERIFY -> RECORD -> UPDATE`

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

# 四、V1.4.1 ATOMIC LOAD RECEIPT

V1.4 已经要求：

- PL-LOAD
- CHALLENGE
- STATE_BLOB
- current-turn CURRENT_STATE citation

真实测试发现：

> 模型能正确输出前三项，却把 citation 漏掉。

所以 V1.4.1 不再把 citation 写成“另外附上”。

成功收据必须是一个四字段原子块：

```text
PL-LOAD ✓ V1.4.1
CHALLENGE = <CURRENT_STATE 当前 LOAD_CHALLENGE>
STATE_BLOB = <GitHub 本回合返回 blob SHA 前 8 位>
STATE_SOURCE = <本回合 CURRENT_STATE file citation>
```

---

# 五、RECEIPT PREFLIGHT

在发送最终回答之前，必须检查：

> `STATE_SOURCE` 是否真正包含本回合 CURRENT_STATE file citation。

以下内容全部无效：

- `STATE_SOURCE = CURRENT_STATE.md`
- `STATE_SOURCE = https://github.com/...`
- 普通 Web citation
- 旧回合 file citation
- 空 STATE_SOURCE
- 根本没有 STATE_SOURCE

若无效：

> 禁止输出 `PL-LOAD ✓`。

必须输出：

`PL-LOAD FAIL: NO_CURRENT_TURN_CITATION`

这一步优先于“把前三项成功字段打印出来”。

---

# 六、LOAD_CHALLENGE

CURRENT_STATE 实质更新时轮换。

V1.4.1 当前 challenge：

`PL141-98D762B0`

用途：

> 检测 stale load。

它不是秘密，也不是单独证明。

---

# 七、STATE_BLOB

回答返回：

> 本回合 GitHub fetch_file 得到的 CURRENT_STATE blob SHA 前 8 位。

它增加读取结果具体性，但不能代替 STATE_SOURCE。

---

# 八、Gate A 判定

## PASS

必须同时满足：

1. fresh-read CURRENT_STATE
2. `PL-LOAD ✓ V1.4.1`
3. 正确当前 CHALLENGE
4. 正确本回合 STATE_BLOB
5. `STATE_SOURCE` 是本回合 CURRENT_STATE file citation

## FAIL

任一缺失即 FAIL。

尤其：

> 前三项全部正确但没有 STATE_SOURCE，仍然 FAIL。

---

# 九、Gate B

Gate A PASS 后才验：

- TASK ANSWER FIRST
- SAFE / OPAQUE LABEL / TEACH-NOW / DEFER
- 默认最多 1 个 TEACH-NOW
- 单个认知台阶
- OUTPUT LINT
- VERIFY
- RECORD
- UPDATE

V1.4.1 不修改 Gate B。

---

# 十、系统限制

这仍不是密码学证明。

Challenge 与 blob 在状态未变化时可能保持不变。

最关键证据仍然是：

> current-turn CURRENT_STATE file citation。

---

# 十一、Checkpoint 与持久化

如果 GitHub 写权限不可用：

- 正常项目继续；
- 合适 checkpoint 生成最小补丁；
- 由本地 `D:\pop-learning` commit + push。

---

# 十二、Public 仓库安全

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
