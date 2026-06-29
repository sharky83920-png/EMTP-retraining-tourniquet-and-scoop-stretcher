# 115年新北TP複訓｜止血帶降位/轉換與鏟式擔架

技術操作站教學網頁（GitHub Pages）。四個分頁：

- **學員**：課程摘要（下載）＋ **降位／轉換 應用判斷（抽題練習）** ＋ 5 支示範影片
  - 影片：止血帶降位、止血帶轉換、腋下出血固定敷料、頸部出血固定敷料、鏟式擔架操作
- **指導員**：教學教案（下載）
- **Q&A**：Firebase 即時問答（管理者登入後新增／刪除）
- **學員連結**：QR code

## 現況
- `index.html`：5 支影片已嵌入、四分頁可切換、PDF 彈出檢視器。
- `files/`：課程摘要_學員版.pdf、指導員教案.pdf、鏟式擔架使用_實證引言.docx、qrcode_student.png。

## 降位／轉換 抽題練習（2026-06 新增）
- 位置：學員分頁，課程摘要與示範影片之間。
- 互動：按「抽一題」隨機出情境 → 學員依決策流程做決定／操作 → 按「看答案」翻出正確處置（轉換／降位／直送）＋解析（中了哪幾盞紅燈）。
- 題庫：存 Firebase Firestore，collection `tpRetrainQuiz`。**管理者（master 信箱）於「Q&A」分頁登入後**，學員分頁會出現「抽題庫管理」可即時新增／刪除題目，免重新部署。
- 後備：Firestore 為空或尚未啟用時，自動用「教案預設 5 題」。管理者可按「匯入教案預設 5 題」一鍵寫入雲端。
- **Firestore 規則**：新 collection `tpRetrainQuiz` 需與 `tpRetrainQA` 相同的讀寫權限（公開讀、master 信箱可寫）。若現有規則是 `match /{document=**}` 的萬用寫法則自動涵蓋；若為逐 collection 設定，需在 Firebase Console 補上 `tpRetrainQuiz` 後發布。
- 答案鍵依據：課程摘要的「止血帶轉換／降位決策流程」（威儀整理版＋TCCC）。

## 發佈到 GitHub Pages

### 方法一：gh CLI（已裝 git，需先登入）
```
gh auth login
gh repo create tp-fuxun --public --source="G:\我的雲端硬碟\secondbrain\產出素材區\TP複訓_GitHub網頁" --push
```
然後 repo → Settings → Pages → Source 選 `main`、根目錄 `/` → 存檔。

### 方法二：GitHub 網頁上傳（最簡單，免指令）
1. github.com 登入 → New repository（Public）。
2. 把本資料夾的 `index.html`、`README.md`、`files/` 拖進去上傳。
3. Settings → Pages → Source `main` / 根目錄 → 存檔。

幾分鐘後即可用 `https://<帳號>.github.io/<repo名>/` 開啟，現場貼 QR code 給學員掃。

## 可選優化
- 想要手機端可預覽：把 3 份 docx 用 Word「另存新檔→PDF」放到 `files/`，再把 `index.html` 三個下載連結的 `.docx` 改成 `.pdf`。
- 不希望指導員教案（含解答/計分）公開：把該頁內容移除或改放精簡版。

> 注意：GitHub Pages 為公開頁面。
