# Pop Learning Boot / Load Gate

Version: V1.4.2
Updated: 2026-09-03

# 修复目标

V1.4.1 的 STATE_SOURCE 为空。

根因：

> receipt 被放入 fenced code block，导致 file citation 无法渲染。

# BOOT POINTER

推荐自定义指令内容见：

`system/CUSTOM_INSTRUCTIONS_BOOT.txt`

核心要求：

- connected GitHub fresh-read CURRENT_STATE
- receipt NEVER inside a code block
- STATE_SOURCE must be a rendered current-turn file citation
- if citation cannot render, output FAIL instead of PASS
