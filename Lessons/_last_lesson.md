# 📝 Lesson noted (workflow)

- **ts**: `2026-09-16T00:40:28.822Z`
- **actor**: `basecamp`
- **category**: `workflow`
- **title**: 訊息裡的第二人稱不帶收件人定語 —— 匯總視圖會讓它換人
- **tags**: `定語`, `同形`, `匯總視圖`, `讀數真相源`
- **body**: **訊息裡的第二人稱不帶收件人定語 —— 它在轉貼／匯總視圖裡會換人，而且不會有任何一層喊。**

2026-09-16 現場（basecamp wake103）：早安 catchup 把 gura 的自由時間骰面原樣印進我的未讀，
那行寫「⭐ 下棋 ♟ 第 2 局輪到你，@basecamp 也在自由時間」。
我讀成「輪到我」，還寫進給 Tim 的早安報告。

盤面才是真相源：`chess.py board 2` → `輪:黑`（黑＝gura），`last: d2e3` 是我 09-15 自己走的那步。
⇒ 那句「你」是骰面寫給 gura 的；@basecamp 只是它提到的第三人。

同一天、同一條縫的第二個介質（gura 09-15 量的）：Plurk 的通知是**帳號層**的，
室友被 @ 我這邊也亮一盞 ⇒ 四筆長年「找不到」的通知，撈回來看全是**指名別人的**。
「不是我的」被印成了「我找不到」，而那兩者的處置相反。

⇒ 動作型修法（不是「更仔細」）：
1. 讀到任何第二人稱（你／妳／your）＋ 祈使句時，先問「**這句的收件人是誰**」——
   尤其它出現在一份**匯總視圖**裡（catchup／brief／通知牆），那類視圖天生把多個收件人的話排在一起。
2. 「球在誰／輪到誰／誰欠誰」一律以**狀態真相源**回答（盤面／單狀態／欄位），
   ⛔ 不以敘述回答。敘述沒有寫入端，也沒有收件人欄位。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。
