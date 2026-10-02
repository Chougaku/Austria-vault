# 奧地利＋慕尼黑 vault

[Austria-web](https://github.com/Chougaku/Austria-web) 旅遊儀表板的資料來源（Obsidian vault）。
push 到 GitHub 後約 2 分鐘網站自動更新；格式寫錯時 Austria-web 的 Actions 會紅燈，錯誤訊息會指出哪個檔案哪一行。

## 網站會讀的檔案

| 檔案 | 用途 |
|---|---|
| `wiki/dashboard/總覽.md` | 出發／回程日期、6 段住宿、城市間移動、預訂狀態、交通備註 |
| `wiki/dashboard/每日行程.md` | Day 0–16 每日行程（網站上也能直接編輯，會 commit 回這個檔） |
| `Austria Trip/行程筆記.md` | 「## ✅ 待辦」段落＝首頁的出發前待辦 |
| `wiki/entities/<分類>/*.md` | 餐廳、景點、購物、交通、住宿、區域（`<分類>總覽.md` 不算） |
| `原始資料/別人行程/*.md` | 別人推薦的攻略（攻略頁） |

## 格式速查

每日行程：

    ## Day 4｜06/18 週五｜維也納 → 格拉茨・自駕
    > 區域：維也納、格拉茨

    - 上午｜維也納取車｜備註文字
    - 晚上｜（待安排）

總覽的住宿與移動：

    - 維也納｜06/15–06/18｜飯店名或待訂｜停車｜備註
    - 06/18｜自駕｜維也納 → 格拉茨｜備註

實體頁（餐廳為例）：frontmatter 要有 `title`；`## 基本資訊` 底下用 `- 欄位：值`，
常用欄位有 類型、評分、價位、地址、位置、營業時間、備註。「位置」寫城市或區域名，網站會自動歸區。
範例檔的 tags 有「範例」，照格式新增自己的資料後可以刪掉。

## 自動重建設定

`.github/workflows/notify-dashboard.yml` 在 push 後通知 Austria-web 重建，需要在這個 repo 設定
Actions secret `AUSTRIA_WEB_PAT`（對 Chougaku/Austria-web 有 contents 寫入權限的 fine-grained token）。
