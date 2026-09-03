# Pop Learning OS

Version: V1.4.3
Started: 2026-09-03
Updated: 2026-09-03

# 核心目标

GitHub `poppoppoppp/pop-learning` 是动态学习状态长期真相源。

# V1.4.3 运行链

`BOOT -> FRESH LOAD -> READ CITATION MARKER -> BUILD SOURCE-FIRST RECEIPT -> TASK / TEACHING`

# SYSTEM BUG 007

V1.4.2 要求：

> 发送前确认 citation 已经在 UI 渲染。

这是不可执行的前置检查。

模型可以决定自己输出什么，
但不能在发送之前观察发送后的客户端 UI。

# 修复：CITATION MARKER COPY

connected GitHub 的文件读取结果会返回：

`Citation Marker: ...`

V1.4.3 的机械动作：

1. fresh-read CURRENT_STATE
2. 找到返回结果中的 Citation Marker
3. 原样复制该 marker 到 STATE_SOURCE
4. 再填 CHALLENGE
5. 再填 STATE_BLOB
6. 最后才允许输出 PASS

成功收据顺序：

STATE_SOURCE = <exact current-turn Citation Marker>  
CHALLENGE = <current challenge>  
STATE_BLOB = <current blob prefix>  
PL-LOAD ✓ V1.4.3

Receipt 必须普通 Markdown，禁止代码块。

# FAIL

没有 current-turn Citation Marker：

`PL-LOAD FAIL: NO_CURRENT_TURN_CITATION_MARKER`

# Gate B

V1.4.3 不修改教学 Gate。

# 系统边界

这是可观察执行收据，不是密码学证明。
