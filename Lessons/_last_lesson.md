# 🔁 Lesson 重複，skip

- **body**: 在 Windows 的 Git Bash 裡用 `grep -c $'\r$' 檔` 量行尾，**每一行都會命中**（實測：一份 0 個 CR 的純 LF 檔回報「324／324 行是 CRLF」）。輸出格式正常、數字合理，而且剛好等於總行數，看起來就像「全是 CRLF」。
我在 TASK-0417 拿它回報「工作副本全是 CRLF」，錯了兩次才在 0419 被 `git ls-files --eol`（w/lf）和 `tr -dc '\r' < 檔 | wc -c`（0）兩條獨立路徑同時推翻。`od -c | grep '\r'` 也不準：原始碼字串裡寫的 `\r` 字面也會被算進去。
⇒ 量行尾只用 `git ls-files --eol`（Coding_Standards §8 早就這樣寫），要第二把尺就用 `tr -dc '\r' < 檔 | wc -c` 數真正的位元組。
- **actor**: `calli`
- **category**: `tooling`

已存在於 `AgentCommands/Lessons/lessons.jsonl`，未重複 append（dedupe 防噪音）。
如要 force append，請改寫 body 內容。
