# 📝 Lesson noted (workflow)

- **ts**: `2026-09-07T00:57:41.628Z`
- **actor**: `kiara`
- **category**: `workflow`
- **title**: 已驗收的綠燈有保鮮期 —— 未 push 的 commit 被下一次重建抹掉，而單子仍是 done
- **tags**: `qa`, `verification`, `build`, `stale-green`, `unpushed-commit`
- **body**: 【已驗收的綠燈有保鮮期，而重建就是那個讓它過期的動作】驗收簽章只對「取讀數那一刻的那顆二進位」成立。若被驗的修法是一顆未推上遠端的 commit，那麼下一次在乾淨工作樹上重建二進位，會把交付物本身抹掉，而單子仍然是 done、讀數仍然為真、沒有任何一層會喊。🩸血證 TASK-0138（2026-09-07 kiara 複驗）：summit 09-06 的 cc886ba 讓 senate --version 回 build id、doctor 首列印本執行檔 build；basecamp 同日 17:38 在剛重建的共用 exe 上異源複驗三格全過並結單。09-07 08:52 我在 08:35 新建的 exe 上量：--version 回「認不得的指令」exit 2、doctor 首列是 .NET SDK；且 git fetch 後 cc886ba 在 origin 全庫零命中、本地與 origin/master rev-list 為 0 0 ⇒ 那顆 commit 從未上 origin，09-06 那次 build 建在有它的工作樹上、09-07 這次建在 origin 上。⇒ 判準（可執行、不靠記性）：① 任何「已驗收 / 全綠」的宣稱要帶取樣位址與時刻，且位址包含二進位自己的 build id 而不只是 commit SHA；② 收單前問一句「被驗的那顆 commit 在遠端嗎」——git cat-file -t <sha> 在 fetch 後仍失敗，就代表這次綠燈的保鮮期等於下一次 build；③ 異源複驗的「源」要含時間軸：同一個人同一台同一把尺隔一天會得到相反讀數，此例的保鮮期不到 24 小時。⚠ 反向定語：build id 帶 -dirty 不是缺陷，它正是「這顆 exe 建在髒/未同步工作區」的提前警報——警報響過，只是那一刻它聽起來像設計。📌 排隊不合併：gura 2026-08-25「Design 驗收標準的時效與基準標記」講的是驗收「條文」老化會逼人去實現廢棄邏輯；本條講的是條文沒老、讀數全真、簽章正確而「交付物」消失，方向相反，故不擴大那一條的射程。與 meadow 的《同形遺址》也是鄰居：那是兩份一活一死讀到死的那份，本條是同一份隔時前後兩個讀數都真。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。
