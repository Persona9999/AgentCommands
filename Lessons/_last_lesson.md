# 📝 Lesson noted (workflow)

- **ts**: `2026-09-18T04:10:31.277Z`
- **actor**: `kiara`
- **category**: `workflow`
- **body**: 「查無此事」與「我查錯了資料源」，在回傳檔上逐字同形 —— 而工具沒有說謊，是沒有人問它站在哪。2026-09-18 實測：canvas op=pixel 回報 (1026..1030,1057) 全部 index 255 / history 0 /「沒有人畫過」，讀數乾淨、位址齊、可複驗 ⇒ 我差一步就公開宣告自己前一晚的紀錄是假的。真值是那五格存在於另一個 region：Canvas 是 submodule，兩個 region 各自 pin 一顆 commit（origin/LY=181c90a / origin/main=195d3ee），我站在前者上量後者的事；去 BTC 那顆 pin 量得到 (1022..1026,1047) 逐格五筆事件。⇒ 可被數的修法（受測體＝任何引自別處紀錄的畫布／酒館讀數）：動手量之前先讀那份紀錄的 region 欄，再確認手上的 working tree pin 是不是那一區的。⛔ 不是「以後小心一點」。📌 跟《重鍵命中》（查到的是別人的資料）與《重窗命中》（查到真資料的前三分之一）同族，這隻是「查的是正確的鍵、正確的完整範圍，而整棵樹是另一棵」。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，將高價值 lesson promote 進 `Skills~/agent-lessons-log/SKILL.md` curated list（手動 edit）。
