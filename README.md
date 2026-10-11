# Choice Lab — 選擇研究所

> 國立臺灣大學《生成式AI：文字與圖像生成的原理與實務》｜第五週作業：以 Vibe Coding 製作互動網頁

- **課程：** [生成式AI：文字與圖像生成的原理與實務（NTU COOL）](https://cool.ntu.edu.tw/courses/63204)
- **作業主題：** 用 Vibe Coding 做出一個互動網頁
- **作品名稱：** Choice Lab — 選擇研究所
- **技術：** 原生 HTML / CSS / JavaScript；localStorage；GitHub Pages
- **網頁檔案：** [`index.html`](./index.html)（包含全部 CSS、JavaScript，無須建置工具）
- **網站網址：** [開啟 Choice Lab 選擇研究所](https://unknownadminpupupu.github.io/ntu-generative-ai-choice-lab/)
- **原始碼倉庫：** [ntu-generative-ai-choice-lab](https://github.com/UnknownAdminpupupu/ntu-generative-ai-choice-lab)

## 作品介紹

Choice Lab 是一個決策輔助工具。使用者可以設定想比較的選項、針對「興趣程度」「執行可行性」「資料取得便利性」分別給分，並調整三項指標的重要權重。系統依照加權平均換算成百分制，即時產生結果與水平長條圖。評分反映使用者的個人偏好，而非客觀正確答案。

## 功能規格

1. 可編輯決策問題名稱（不可空白，最長 60 字）。
2. 可新增、編輯、刪除選項（至少 2 個，最多 5 個）；不接受空白或重複的選項名稱。
3. 三項指標的權重各可設為 0–5；權重為 0 的指標不計入結果。
4. 各選項在每個指標上可評為 1–5 分；修改後即時計算排名。
5. 以水平長條圖顯示每個選項的百分制分數，同分時顯示並列名次。
6. 全部權重為 0 時顯示提示，不計算無效結果。
7. 以瀏覽器 localStorage 儲存決策名稱、權重、選項與評分；重新整理可還原資料。
8. 提供重設範例功能，重設前會要求使用者確認。
9. 採用現代簡約風格，提供桌面與手機響應式排版。

**計分公式：** 綜合分數 = Σ（評分 × 權重）÷（5 × 總權重）× 100。

## AI 協作開發歷程

- **V1.0：** 規劃網站規格、建立畫面、滑桿評分、權重計算與排名圖表。
- **V2.0：** 加入比較選項的新增、編輯、刪除，以及 2–5 個選項限制與輸入驗證。
- **V3.0：** 加入 localStorage、重新載入資料還原、重設確認與異常資料處理。
- **V4.0：** 沿用 V3 程式，完成 GitHub Pages 公開部署。測試環境操作原生 `window.confirm` 時發生逾時，改用 HTML `dialog` 頁內確認，提供「取消，保留資料」「確定重設」及 Escape 取消；保留 V3 的 localStorage 格式與既有資料。整理正式網址驗收與 COOL 繳交材料。

V1、V2、V3 的紀錄依交接包版本檔案與說明整理；本倉庫從交接的 V3 原始碼開始建立真實提交紀錄，未追造先前版本的 Git 歷史。

## 部署方式

1. 在 GitHub 建立 **Public** 儲存庫 `ntu-generative-ai-choice-lab`。
2. 將本目錄內的 `index.html`、`README.md` 上傳至預設分支 `main` 的根目錄。
3. 進入 GitHub Repository **Settings → Pages**，選擇 **Deploy from a branch**；Branch 選 `main`，Folder 選 `/(root)`，按下 Save。
4. 待發布完成，在 Pages 設定頁點選 **Visit site** 開啟，驗證評分、增刪選項與重新整理保存功能。

## 使用說明與隱私

此專案不需登入或後端。輸入資料只保存在使用者目前瀏覽器的 localStorage，不會自動同步至其他裝置；清除網站資料或使用無痕模式可能會遺失紀錄。

---

**作業截止：** 2026 年 10 月 19 日 23:59（臺灣時間）
