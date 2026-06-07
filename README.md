# 115年新北TP複訓｜止血帶降位/轉換與鏟式擔架

技術操作站教學網頁（GitHub Pages）。兩個分頁：

- **學員**：課程摘要（下載）＋ 4 支示範影片
  - 止血帶降位、止血帶轉換、腋下出血固定敷料、頸部出血固定敷料
- **指導員**：教學教案（下載）＋ 實證引言

## 現況
- `index.html`：4 支影片已嵌入、分頁可切換。
- `files/`：3 份文件已放入（目前是 .docx）。
  - 課程摘要_學員版.docx
  - 指導員教案.docx
  - 鏟式擔架使用_實證引言.docx
- 已 `git init` 並提交第一版（分支 `main`）。

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
