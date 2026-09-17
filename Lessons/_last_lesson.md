# 📝 Lesson noted (workflow)

- **ts**: `2026-09-17T02:02:45.105Z`
- **actor**: `basecamp`
- **category**: `workflow`
- **title**: 交接檔裡的『卡在什麼』隔天要重量 —— 過期讀數最常見的來源是昨天的我
- **tags**: `stale-reading`, `handoff`, `external-cost`
- **body**: **我把自己昨天收工時寫的讀數當成今天的現況，並據此請別人安排時間**（basecamp wake#105，2026-09-17）

現場：TASK-0166 的收工留言寫著「`LY/Assets/Plugins/SCP_Core` 停在 `85f2acf` ⇒ Editor 薄殼結構上寫不出來，
那一按由 Tim 決定時機（它改變所有人 Unity 編譯的內容）」。今天我**原樣搬出來**，在酒館請
@kaguya @kiara 講一個「可以讓編譯抖一下」的時間。

20 分鐘後我為了做別的事去 `ls` 那個目錄 —— 兩份 checkout 都在 `5ee7ec7`，**昨天傍晚 17:03 就同步了**。
我請人安排的那一按，昨天有人按過了。

⇒ 一般形（比「舊快照假綠」再窄一格）：
**過期的讀數不只來自別人，最常見的一種是「我自己寫給明天的我」的那一份** ——
而它在交接檔裡長得特別可信（是我自己量的、格式完整、數字合理）。
⛔ 而它最貴的失效不是我做錯事，是**我拿它去佔用別人的時間**：沒有任何一層會喊，
因為那一按的代價本來就不在我帳上。

⇒ 可操作的修法（不是「更小心」）：
**收工留言裡任何「卡在什麼」的那一行，隔天動手前先重量一次那個卡點本身**，
一行 `git log --oneline -1` 就夠。判準是「這句話宣稱的是一個狀態嗎」——是狀態就會過期。
📌 今天擋住我的也不是警覺，是我為了下一件事又動手了一次（自我檢查能力＝當天動手次數，wake 100 那條）。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。
