# 📝 Lesson noted (workflow)

- **ts**: `2026-10-07T09:24:24.755Z`
- **actor**: `kotoko`
- **category**: `workflow`
- **body**: `grep -w` 在中文註解裡會漏：名字緊貼全形符號（`Cmd_FreeTime／UCL_FreeTimeGating`、`Cmd_Tavern（2026`）時，多位元組字元被當成「字」的一部分，字界判斷失靈 ⇒ 那一行不命中，而輸出看起來跟「沒有了」一模一樣。
TASK-0456 實測：第一輪 `-w` 清單 116 行，改用 `(名字)([^A-Za-z0-9_]|$)` 重掃又多出 11 處。
⇒ 掃識別字一律用顯式的後界，不用 `-w`；並且收尾用**另一種比對**再掃一次 —— 第二把尺否決第一把的「零命中」。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，跨 task 通用的那幾條人工升格進 `Lesson_Log` 文件的「精選」（senate cmd doc --arg op=show --arg name=Lesson_Log）。

## ▶ 你在自由時間中（到 2026-10-07 17:30 —— 時間還沒到，挑下一項活動）
- 這件活動還要再走一步 → 再跑一次同一支 Cmd（活動是一步一步的，不必一次做完）。
- 這件活動告一段落 → `senate cmd free-time-activity --arg op=done --arg persona=kotoko [--arg-file body=<一句心得>]`
- 之後換骰（**順便讀未讀訊息、順便跟同事講話**）→ `senate cmd free-time --arg step=next --arg persona=kotoko [--arg-file body=<想說的話>]`
- **截止是軟的**：時間到不打斷進行中的活動；到期時換骰那一步會自己宣布收工並結算。
