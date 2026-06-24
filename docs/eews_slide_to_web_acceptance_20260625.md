# eews_slide_to_web_20260625 驗收清單

本文件對應 AI-WorkHub 任務：`eews_slide_to_web_20260625`。

更新日期：2026-06-25

## 1. 任務目標

將「臺灣地震預警系統的演進與發展」簡報轉成 GitHub Pages 互動式網頁，並完成內容完整性、互動功能、部署狀態與最終 URL 驗收。

## 2. 已確認項目

- [x] GitHub repo 存在：`oceanicdayi/EEWS_CWA_Dev2026`
- [x] `README.md` 存在
- [x] `package.json` 存在
- [x] `index.html` 存在
- [x] `.github/workflows/deploy.yml` 存在
- [x] `public/slides/slide-01.jpg` 存在
- [x] `public/slides/slide-50.jpg` 存在
- [x] GitHub issue 已建立：`#1 驗收 GitHub Pages 互動網頁：eews_slide_to_web_20260625`
- [x] 已逐一確認 `public/slides/slide-01.jpg` 到 `public/slides/slide-50.jpg` 全部存在
- [x] 已建立 AI-WorkHub 規格文件
- [x] 已建立 AI-WorkHub Agent job
- [x] 已建立 AI-WorkHub 初步 log
- [x] 已建立 AI-WorkHub 最終報告
- [x] 已建立 repo 內驗收清單
- [x] 已建立 repo 內最終報告

## 3. 驗收狀態

### 已完成

- [x] 檢查 `public/slides/` 是否包含 `slide-01.jpg` 到 `slide-50.jpg`
- [x] 確認 repo 具有 GitHub Pages 部署 workflow
- [x] 確認 repo 具有主入口 `index.html`
- [x] 確認 repo 具有 `package.json` 與 Vite build script
- [x] 建立最終報告文件
- [x] 建立 GitHub issue 追蹤
- [x] 建立 GitHub / Drive 雙份最終報告

### 需要外部執行環境完成或複核

以下項目需要 GitHub Actions、本地 VSCode、Hermes Agent、Codex CLI 或 Zeabur 等具備 Node.js 與瀏覽器的執行環境：

- [ ] 執行 `npm install`
- [ ] 執行 `npm run build`
- [ ] 確認 GitHub Actions Pages workflow 成功
- [ ] 開啟 GitHub Pages URL：`https://oceanicdayi.github.io/EEWS_CWA_Dev2026/`
- [ ] 測試導覽列可跳轉到主要區塊
- [ ] 測試完整簡報區可瀏覽
- [ ] 測試搜尋功能
- [ ] 測試燈箱、投影片模式或圖片放大功能
- [ ] 產出首頁截圖
- [ ] 產出完整簡報區截圖

## 4. 已確認的 50 張簡報圖

已逐一確認以下檔案存在：

```text
public/slides/slide-01.jpg
public/slides/slide-02.jpg
public/slides/slide-03.jpg
public/slides/slide-04.jpg
public/slides/slide-05.jpg
public/slides/slide-06.jpg
public/slides/slide-07.jpg
public/slides/slide-08.jpg
public/slides/slide-09.jpg
public/slides/slide-10.jpg
public/slides/slide-11.jpg
public/slides/slide-12.jpg
public/slides/slide-13.jpg
public/slides/slide-14.jpg
public/slides/slide-15.jpg
public/slides/slide-16.jpg
public/slides/slide-17.jpg
public/slides/slide-18.jpg
public/slides/slide-19.jpg
public/slides/slide-20.jpg
public/slides/slide-21.jpg
public/slides/slide-22.jpg
public/slides/slide-23.jpg
public/slides/slide-24.jpg
public/slides/slide-25.jpg
public/slides/slide-26.jpg
public/slides/slide-27.jpg
public/slides/slide-28.jpg
public/slides/slide-29.jpg
public/slides/slide-30.jpg
public/slides/slide-31.jpg
public/slides/slide-32.jpg
public/slides/slide-33.jpg
public/slides/slide-34.jpg
public/slides/slide-35.jpg
public/slides/slide-36.jpg
public/slides/slide-37.jpg
public/slides/slide-38.jpg
public/slides/slide-39.jpg
public/slides/slide-40.jpg
public/slides/slide-41.jpg
public/slides/slide-42.jpg
public/slides/slide-43.jpg
public/slides/slide-44.jpg
public/slides/slide-45.jpg
public/slides/slide-46.jpg
public/slides/slide-47.jpg
public/slides/slide-48.jpg
public/slides/slide-49.jpg
public/slides/slide-50.jpg
```

## 5. 建議驗收指令

```bash
git clone https://github.com/oceanicdayi/EEWS_CWA_Dev2026.git
cd EEWS_CWA_Dev2026
find public/slides -maxdepth 1 -type f -name 'slide-*.jpg' | sort | wc -l
npm install
npm run build
npm run preview
```

## 6. GitHub Pages 部署邏輯

目前 `.github/workflows/deploy.yml` 使用靜態 fallback 部署：

```bash
rm -rf _site
mkdir -p _site/slides
cp index.html _site/index.html
cp index.html _site/404.html
touch _site/.nojekyll
cp -R public/slides/. _site/slides/
```

此做法可避免 React/Vite build 失敗時阻擋 GitHub Pages 靜態部署，但仍建議保留 `npm run build` 作為品質檢查。

## 7. AI-WorkHub 對應文件

- `AI-WorkHub/00_inbox_tasks/eews_slide_to_web_20260625 任務卡`
- `AI-WorkHub/03_chatgpt_output/eews_slide_to_web_spec_20260625`
- `AI-WorkHub/06_agent_jobs/eews_slide_to_web_execute_20260625`
- `AI-WorkHub/07_agent_logs/eews_slide_web_log_20260625`
- `AI-WorkHub/08_final/eews_slide_to_web_final_report_20260625`

## 8. 結論

截至 2026-06-25，已完成 ChatGPT 可直接執行的 GitHub 與 Google Drive 任務：建立任務卡、規格、Agent job、log、GitHub issue、repo 驗收文件、repo 最終報告、Drive 最終報告、50 張 slide 圖片存在性驗證。

需要具備 Node.js / browser / GitHub Actions 執行環境的項目，已明確列為外部執行環境待複核項目。
