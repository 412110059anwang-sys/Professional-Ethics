# 🛠️ SETUP.md — 本地預覽與 GitHub Pages 部署指南

本專案採用純靜態 HTML5 + CSS3 + 原生 JavaScript 架構，**零複雜套件依賴、不會發生初始化失敗**，解壓縮即可直接瀏覽或上傳至 GitHub Pages。

---

## 方法一：在電腦上直接打開瀏覽（最快）
1. 解壓縮下載的 ZIP 檔案。
2. 直接雙擊根目錄下的 **`index.html`**，即可在瀏覽器打開「專業倫理互動學習總入口網站」。
3. 點擊任一主題卡片，即可進入該單元的互動手寫風簡報（`presentation/01-...html` 等）。
4. 使用 **Obsidian** 開啟本資料夾，即可同時瀏覽 `wiki/` 知識庫圖譜、`ideas/` 研究筆記與 `slide_notes/` 簡報稿。

---

## 方法二：一鍵部署至 GitHub Pages（讓所有人透過網址瀏覽）
1. 在 GitHub 建立一個新的公開儲存庫（Repository），例如命名為 `ethics-llm-wiki`。
2. 將本資料夾內的所有檔案與資料夾上傳（Push）至 GitHub `main` 分支：
   ```bash
   git init
   git add .
   git commit -m "Initialize Ethics LLM Wiki & Interactive Presentations"
   git branch -M main
   git remote add origin https://github.com/<你的帳號>/<你的Repo名稱>.git
   git push -u origin main
   ```
3. 進入 GitHub Repository 的 **Settings** ➔ 左側選單點擊 **Pages**。
4. 在 **Build and deployment** 下方的 Branch 選擇 `main` 並選擇 `/ (root)`，點擊 **Save**。
5. 等待約 1 分鐘，你的互動知識庫與簡報網站就會正式上線！
