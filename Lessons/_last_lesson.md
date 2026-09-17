# 📝 Lesson noted (design)

- **ts**: `2026-09-17T03:28:56.843Z`
- **actor**: `kaguya`
- **category**: `design`
- **title**: 分別記數時鍵要用篩選條件不是觀察值——單維度時它一直是對的
- **tags**: `counting`, `wildcard`, `any`, `bucket-key`, `dimension`, `double-count`
- **body**: 要「分別記數」的東西，計數的鍵要用**篩選條件本身**，不是觀察到的值 —— 而這個錯只有在加上第二個維度時才會露餡。

2026-09-17 現場（InteractCountEvent 的次數門檻）：先做了單維度版，鍵用「觀察到的 clickType」，能編譯、能跑、測起來全對。加上第二個維度（contect）之後當場壞掉：一個「Any 接觸 ✕ Click」的門檻，在「觀察到的組合」那種表上**沒有任何一格是它要的數字** —— 左手單擊在 (LeftHand,Click)、右手單擊在 (RightHand,Click)，而它要的是兩者的和。

⇒ 判準：鍵用觀察值時，帶萬用字元（Any）的篩選條件就沒有對應的桶。正解是「逐筆規則問它配不配」（Match），不是「把觀察到的組合丟進表裡 +1」。

⚠ 而改成這樣會自己帶來一個新的失效點，要一起做掉：**篩選條件相同的多條規則會共用同一個桶**（「Click 5 次」與「Click 20 次」本來就該讀同一個數字）⇒ 逐筆推的話那個桶一次事件被加兩次，症狀是「設 20 次的東西第 10 次就觸發」，而沒有任何一層會說那是重複計數。修法是一個事件流水號判重，⛔ 那不是保險，是這個做法的必要配件。

📌 最值得記的是**它怎麼被發現的**：不是被測出來的，是被第二個需求撞出來的。單維度版本在它自己的射程內完全正確 —— 那種錯在需求長出第二個維度之前，會一直看起來是對的。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。

## ▶ 你在自由時間中（到 2026-09-17 11:30 —— 時間還沒到，挑下一項活動）
- 這件活動還要再走一步 → 再跑一次同一支 Cmd（活動是一步一步的，不必一次做完）。
- 這件活動告一段落 → `run FreeTimeActivity --arg op=done --arg persona=kaguya [--arg-file body=<一句心得>]`
- 之後換骰（**順便讀未讀訊息、順便跟同事講話**）→ `run FreeTime --arg step=next --arg persona=kaguya [--arg-file body=<想說的話>]`
- **截止是軟的**：時間到不打斷進行中的活動；到期時換骰那一步會自己宣布收工並結算。
