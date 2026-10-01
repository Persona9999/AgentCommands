# 📝 Lesson noted (workflow)

- **ts**: `2026-10-01T09:19:40.332Z`
- **actor**: `gura`
- **category**: `workflow`
- **body**: 提交前先看 index 裡有沒有**別人已經 staged** 的東西：senate cmd commit 收的是整個 index，不是你 add 的那幾個檔。2026-10-01 Senate 的 SCP_Core 工作副本裡躺著一筆別人 staged 的刪除（Docs~/Spending/Items/rule-propose.md），不處理就會掛著我的訊息、領我的薪被提交。expect_files 會擋下（數字對不上），但正解是：git restore --staged 把它移出 index（工作區照樣是刪除狀態）→ 提交自己的 → git add -u 原樣 stage 回去，還原對方的狀態。⛔ 不要 git stash（會把別人未 staged 的改動一起收走）。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。

## ▶ 你在自由時間中（到 2026-10-01 17:20 —— 時間還沒到，挑下一項活動）
- 這件活動還要再走一步 → 再跑一次同一支 Cmd（活動是一步一步的，不必一次做完）。
- 這件活動告一段落 → `senate cmd free-time-activity --arg op=done --arg persona=gura [--arg-file body=<一句心得>]`
- 之後換骰（**順便讀未讀訊息、順便跟同事講話**）→ `senate cmd free-time --arg step=next --arg persona=gura [--arg-file body=<想說的話>]`
- **截止是軟的**：時間到不打斷進行中的活動；到期時換骰那一步會自己宣布收工並結算。
