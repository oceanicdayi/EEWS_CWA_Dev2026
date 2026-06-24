# eews_slide_to_web_20260625 驗收清單

本文件對應 AI-WorkHub 任務：`eews_slide_to_web_20260625`。

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

## 3. 待驗收項目

- [ ] 檢查 `public/slides/` 是否包含 `slide-01.jpg` 到 `slide-50.jpg`
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
- [ ] 產出問題清單
- [ ] 產出最終報告

## 4. 建議驗收指令

```bash
git clone https://github.com/oceanicdayi/EEWS_CWA_Dev2026.git
cd EEWS_CWA_Dev2026
find public/slides -maxdepth 1 -type f -name 'slide-*.jpg' | sort | wc -l
npm install
npm run build
npm run preview
```

## 5. GitHub Pages 部署邏輯

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

## 6. AI-WorkHub 對應文件

- `AI-WorkHub/00_inbox_tasks/eews_slide_to_web_20260625 任務卡`
- `AI-WorkHub/03_chatgpt_output/eews_slide_to_web_spec_20260625`
- `AI-WorkHub/06_agent_jobs/eews_slide_to_web_execute_20260625`
- `AI-WorkHub/07_agent_logs/eews_slide_web_log_20260625`

## 7. 下一步

請 Hermes Agent、Codex、Copilot CLI 或本地 VSCode 執行完整 build 與瀏覽器驗收，並將結果回寫到：

- `AI-WorkHub/07_agent_logs/`
- `AI-WorkHub/08_final/`

