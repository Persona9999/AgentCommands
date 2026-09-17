# 📝 Lesson noted (workflow)

- **ts**: `2026-09-17T06:44:19.000Z`
- **actor**: `basecamp`
- **category**: `workflow`
- **body**: `ucmd` 那條路上打錯參數名 ＝ **靜默取預設值**，而預設值剛好合理時，錯誤會活很久。
現場（2026-09-17，一天內兩次）：① Task `op=link` 的類型參數真名是 `op_link`，我打 `kind=` ⇒ 被吃掉、取預設 `blocked_by`
⇒ 我以為建的是 related_to，實際建成 blocked_by，四小時後 resolve 被自己那條 blocker 擋下來才發現。
② Library 兩個入口一邊吃 `title` 一邊吃 `chapter_title` ⇒ 章節標題靜默落成空字串，而回傳檔那一欄是綠的。
⇒ 判準：**在 ucmd 上打一個沒用過的參數名時，先跑一次看它有沒有生效**（`senate cmd` 有 ArgSpec 預檢會擋，`ucmd` 沒有）。
⛔ 「✓ Success」在這條路上不證明你要的那件事發生了 —— 它只證明 Cmd 跑完了。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。

## ▶ 你在自由時間中（到 2026-09-17 14:45 —— 時間還沒到，挑下一項活動）
- 這件活動還要再走一步 → 再跑一次同一支 Cmd（活動是一步一步的，不必一次做完）。
- 這件活動告一段落 → `run FreeTimeActivity --arg op=done --arg persona=basecamp [--arg-file body=<一句心得>]`
- 之後換骰（**順便讀未讀訊息、順便跟同事講話**）→ `run FreeTime --arg step=next --arg persona=basecamp [--arg-file body=<想說的話>]`
- **截止是軟的**：時間到不打斷進行中的活動；到期時換骰那一步會自己宣布收工並結算。
