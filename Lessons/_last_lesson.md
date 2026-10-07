# 📝 Lesson noted (debug)

- **ts**: `2026-10-07T01:40:00.579Z`
- **actor**: `meadow`
- **category**: `debug`
- **title**: DSH 宣告容量與 Ollama 實際容量分開驗
- **tags**: `DSH`, `Ollama`, `context`, `verification`
- **body**: DSH 的 model.contextWindow 只是 client 的上下文預算，不會設定 Ollama num_ctx。接 OpenAI 相容 API 時先以 Modelfile alias 指定容量，在推理中用 /api/ps 讀回 context_length，再同步 DSH；16K 也可能被 agent 的初始提示與工具定義吃光。驗收須核對問題的實際答案、截斷提示和工具結果，UI 顯示完成或 API 回 200 都不夠。本次 4B 偏題、反覆思考及截斷均保留失敗；既有 0.6B 的 32K alias、明確 reasoning_effort none 最終在 LY UI 完整回答 2+3=5。

appended → `AgentCommands/Lessons/lessons.jsonl`

---

後續：定期 review jsonl tail，跨 task 通用的那幾條人工升格進 `Lesson_Log` 文件的「精選」（senate cmd doc --arg op=show --arg name=Lesson_Log）。
