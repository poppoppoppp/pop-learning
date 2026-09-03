# Pop Learning

个人能力地图与项目驱动学习系统。

Current Version:

`V1.4.1`

Started:

`2026-09-03`

# V1.4.1 Gate A

```text
Custom Instructions
        ↓
connected GitHub fresh-read
        ↓
CURRENT_STATE
        ↓
ATOMIC LOAD RECEIPT
        ↓
PL-LOAD
CHALLENGE
STATE_BLOB
STATE_SOURCE
        ↓
RECEIPT PREFLIGHT
        ↓
Gate A PASS / FAIL
```

Current LOAD_CHALLENGE:

`PL141-98D762B0`

# 核心入口

- `SYSTEM.md`
- `learner/CURRENT_STATE.md`
- `learner/ABILITY_MAP.md`
- `evidence/LEARNING_LOG.md`
- `concepts/DEPENDENCIES.md`
- `system/BOOT_GATE.md`
- `system/CHANGELOG.md`

# V1.4.1 核心变化

- citation 不再是“另外附上”
- `STATE_SOURCE` 是成功收据内部必填字段
- current-turn file citation 无法渲染时：
  `PL-LOAD FAIL: NO_CURRENT_TURN_CITATION`
- Gate B 教学规则不变
