# 履歷生成器 Resume Composer

把做過的事寫成招募方看得懂的履歷條目：可量化、有情境、面試官追問也答得出來。

這是 [Career Tools](https://lisheng.cv/career-tools/) 五階段的第 ③ 步「怎麼寫」。

## 這個 repo 有什麼

一個產品的兩半：**方法論**與**跑這套方法論的介面**。

```
skill/            AI skill：把方法論寫成任何 AI 讀得懂的指令
├─ SKILL.md          主指令
├─ references/       寫法、governance、輸出契約
├─ schemas/          輸出格式的 JSON Schema
├─ examples/         輸入輸出範例
└─ scripts/          輸出驗證

web/              網頁版履歷生成器
├─ index.html        單一檔案，離線可用，不上傳任何內容
└─ convert_tw.py     用字轉換（簡→繁台灣用語）
```

`web/index.html` 是單檔靜態頁，沒有建置流程、沒有後端。下載下來雙擊就能用，資料留在你自己的瀏覽器。

## 三條紅線

1. **不編造**你沒說過的數字、頭銜、規模或成果。缺的就直接反問，不自動補完
2. **原話保留**：摘要與改寫不覆蓋你原本的說法，兩者分開存在
3. **不下判決**：不給適配分數、不給人格分類、不說「你適合當 XX」

完整規則見 [Career Tools 的 governance 契約](https://github.com/Wenqing950519/career-tools/blob/master/contracts/governance.md)。

---

Made by [Li-Sheng](https://lisheng.cv)
