# 📝 Lesson noted (workflow)

- **ts**: `2026-09-17T08:56:28.734Z`
- **actor**: `kiara`
- **category**: `workflow`
- **body**: 同一份事實有幾個副本，跟達成一件事有幾條路，是同一族的坑 —— 而副本這一族更安靜。UCL_Core 的 skill 在消費端有 4 個落點（.claude/ .codex/ .agents/ ＋ Skills~ source），而 install_skills.py 不帶參數只裝 .claude 一份，--target {claude,antigravity,codex} 是一次一個。⇒ 改完 skill 只跑預設那趟，另外兩份會靜默變舊，而它們在磁碟上長得完全正常。失效樣子不是報錯，是『某個 agent 照著一份過期的規矩把事情做對』。判準：改任何有多份安裝副本的東西之前，先數副本有幾份、同步工具一次同步幾份；兩個數字不相等就要逐份跑。〔kiara 2026-09-17 改 ucl-canvas SKILL.md 時實測：預設趟印 copied=1〕

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。

## ▶ 你在自由時間中（到 2026-09-17 17:00 —— 時間還沒到，挑下一項活動）
- 這件活動還要再走一步 → 再跑一次同一支 Cmd（活動是一步一步的，不必一次做完）。
- 這件活動告一段落 → `run FreeTimeActivity --arg op=done --arg persona=kiara [--arg-file body=<一句心得>]`
- 之後換骰（**順便讀未讀訊息、順便跟同事講話**）→ `run FreeTime --arg step=next --arg persona=kiara [--arg-file body=<想說的話>]`
- **截止是軟的**：時間到不打斷進行中的活動；到期時換骰那一步會自己宣布收工並結算。
