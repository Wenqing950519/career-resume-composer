# career-resume-composer｜打履歷

把「我有幫忙處理系上活動」這種講不清楚的經歷，變成可量化、面試官追問也答得出來的履歷內容。

Career Tools 五階段的第 ③ 步：**「我做過一些事，但不會寫成履歷。」**
→ [完整平台與其他階段](https://github.com/Wenqing950519/career-tools)

## 怎麼用

不用安裝任何東西。複製 [`SKILL.md`](SKILL.md) 的內容，貼進 ChatGPT、Claude 或任何 LLM，然後說你想找什麼職缺、做過什麼事。

它會一次問一段經歷，問完再問下一段。最後產出的內容可以直接貼進履歷生成器網頁排版、匯出 PDF。

## 它會怎麼問你

每段經歷固定三個問題，一次問一個：

1. **場景**——這是什麼活動、在哪裡、大概什麼時候、持續多久？
2. **你自己做了什麼**——哪一部分是你負責的，哪一部分是團隊或別人做的？
3. **有沒有可數的東西**——幾個人、幾週、幾篇、多少預算、前後有什麼變化？

第 2 題是決定這段經歷能不能撐過真實面試的關鍵，不會因為你講得很有信心就跳過。

寫完一段，它會問你一句：**「這樣寫有沒有超過事實？」** 你沒有回答的內容不會進最終履歷。

## 它不會做的事

**不會幫你編數字。** 這是這個 skill 唯一不能妥協的規則：

- 有可數的東西 → 問到你給出實際數字為止，原值使用
- 只有頻率或範圍 → 用你說的範圍（「每週 2 篇」），不自行估算
- 完全問不出來 → 保持質性描述，並直接告訴你這段沒有數字

它不會用看起來合理的數字、業界平均值，或 `XX%` 這種佔位符補洞。**你能捍衛的質性句子，勝過你答不出來的漂亮數字。**

其他限制：

- 不會把「協助」改成「主導」
- 不會把團隊成果寫成你個人的成果
- 不會把 JD 的要求抄成你的成就
- 缺的欄位就留空，不會填像是事實的假資料

規則全文見 [`references/governance.md`](references/governance.md) 與 [`references/interview-method.md`](references/interview-method.md)。

## 兩種模式

| 模式 | 何時觸發 | 行為 |
| --- | --- | --- |
| Standalone | 一般情況（貼在 ChatGPT／Claude 用） | 訪談你、當場取得你的確認，再撰寫 |
| Injected | 已有 confirmed 素材注入 | 直接從既有素材組稿，不訪談 |

## 範例

| 模式 | 輸入 | 輸出 |
| --- | --- | --- |
| Injected | [input-01](examples/input-01.md) | [output-01](examples/output-01.md) |
| Standalone | [input-02](examples/input-02.md) | [output-02](examples/output-02.md) |

## 開發者

輸出結尾是一個 `careertown` JSON block，履歷生成器網頁會從貼上的整段回覆裡把它挖出來預填表單。格式與容錯規範見 [`references/output-contract.md`](references/output-contract.md)。

```bash
python scripts/validate_response.py examples/output-02.md
```

---

Made by [Li-Sheng](https://lisheng.cv)
