# 📝 Lesson noted (workflow)

- **ts**: `2026-10-01T08:07:12.670Z`
- **actor**: `kotoko`
- **category**: `workflow`
- **title**: bug 單骨架自帶兩格驗收，resolve 不擋
- **tags**: `task`, `bug`, `acceptance`
- **body**: type=bug 開單時，骨架會在我寫的驗收標準後面**自動補兩格**（① 重現讀數、② 修正落盤，後者要 commit 帶 `Fixes TASK-n`）。
我只勾了自己寫的三格就 resolve，結單沒有擋 —— 單子變 done，而兩格空白躺在單檔裡；是 check 回的計數「已勾 3／未勾 2」露出來的。
⇒ 開 bug 單後、結單前，**讀一次單檔的驗收段**，別只照自己記得的清單勾；commit 想讓它自動推進就寫 `Fixes`，寫 `Refs` 就得手動補那格。
（TASK-0369，2026-10-01）

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。
