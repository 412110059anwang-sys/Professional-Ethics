# CLAUDE.md / AGENTS.md — 專業倫理與 LLM 知識庫自動化簡報工作流

本專案結合了 **Andrej Karpathy 的「LLM Wiki」持續累積型知識庫架構** 以及 **「精簡四步簡報生成管線 (`ideas` ➔ `slide_notes` ➔ `assets` ➔ `presentation` + `index.html`)」**。

專案核心目標：**除了整理《專業倫理 (Professional Ethics)》與 LLM 相關研究資料外，更致力於以生動、人性化、溫潤手寫感與互動式的方式，幫助學習者輕鬆理解抽象的道德哲學與決策概念。**

---

## 一、 專案目錄結構（對應視覺架構圖）

```text
ethics-wiki-project/
├── CLAUDE.md                  # AI Agent 核心規範檔（與 AGENTS.md 同步）
├── AGENTS.md                  # AI Agent 核心規範檔
├── SETUP.md                   # 環境設定與 GitHub Pages 部署教學
├── README.md                  # 專案總覽與快速開始指南
├── log.md                     # 根目錄全局操作日誌（同步連結 wiki/log.md）
├── index.html                 # 🌟 GitHub Pages 網站總入口（展示所有單元卡片，點擊直接看簡報）
│
├── raw/                       # 【唯讀層】原始課程講義 PDF 與文獻 (Source of Truth)
├── wiki/                      # 【知識庫層】結構化 Markdown 雙向連結知識網 (含 index.md)
│
├── ideas/                     # 【步驟 1：整理想法】完全基於 Wiki 撰寫的研究筆記 (.md) + 外部建議文獻
├── slide_notes/               # 【步驟 2：簡報腳本】根據 ideas 轉換的逐頁簡報內容大綱 (.md)
├── assets/                    # 【我們的小插圖】手繪感 SVG 可愛貼圖與視覺素材 (stickers/)
├── presentation/              # 【步驟 3：最終的簡報】溫潤手寫風、含 [💡補充/更多..] 按鈕之互動 HTML 簡報
│
└── (相容擴充資料夾：slide-notes/, ppt/, ppt-final/, shared-assets/, lessons/, _to_delete/)
```

---

## 二、 核心工作流：從提問到互動簡報三步曲

當使用者提出一個研究問題、教學主題或指定某個觀念時，請嚴格依序執行以下三個步驟：

### 步驟 1：撰寫研究想法筆記 (`ideas/XX-topic-name.md`)
1. **100% 依賴現有 Wiki 內容**：
   - 先讀取 `wiki/index.md` 與相關的 `wiki/concepts/`、`wiki/sources/`、`wiki/comparisons/`。
   - **內文絕對不可混入尚未存進 Wiki 的外部資訊**，每一段核心觀念皆需標註 Wiki 內部雙向連結引用（如 `[[concepts/normative-moral-theories]]`）。
2. **外部搜尋與待 Ingest 建議清單（放在筆記最末段）**：
   - 針對該主題整理相關的經典或最新外部參考文獻（標明尚未放入 Wiki，僅列於文末 `## 🌐 建議後續參考與待 Ingest 文獻` 供未來擴充知識庫使用）。

### 步驟 2：編寫簡報逐頁內容 (`slide_notes/XX-topic-slides.md`)
根據 `ideas/` 中的筆記，設計 6～8 頁結構清晰、生動易懂的逐頁簡報稿。每一頁須包含以下 **4 個固定欄位**（**注意：不設「講者備忘錄」，改為給學習者自學點擊的 `[💡 補充 / 更多..]` 互動區塊**）：
1. **頁碼與核心標題 (Slide Title)** + 分類小貼紙標籤。
2. **主畫面視覺重點 (On-Slide Visuals)**：嚴格控制字數，避免字太密；多用對比字卡、生活化口訣與可愛貼圖。
3. **互動引導問題或重點提示框 (💭 想一想 / Guiding Question)**：以貼近日常、打工、實習或人際關係的情境提問，引導使用者反思。
4. **`[💡 補充 / 更多..]` 展開內容 (Expandable Deep-Dive)**：將 `ideas/` 中較深入的哲學推論、專有名詞解釋或具體案例收納於此，讓好奇的使用者點擊展開閱讀。**注意：敘述時請直接寫出知識內容本身，不需要加上「根據課程講義...」、「根據 Wiki...」等前綴詞或內部路徑代碼。**

### 步驟 3：生成 HTML 互動簡報 (`presentation/XX-topic.html`) 並更新首頁 (`index.html`)
1. **色彩學與視覺規範（吸引注意、但不讓人產生緊繃分析感）**：
   - **背景色**：溫潤燕麥奶 (`#FDFBF7`) 與卡片淺米白 (`#F5EFE6`)，營造紙本筆記溫度、降低視覺疲勞。
   - **文字與手寫字體**：深焙咖啡棕 (`#3E362E`)，引入 Google Fonts 手寫感與圓潤繁體中文字型（`Klee One`, `Zen Maru Gothic`）。
   - **三大溫和強調色**：
     - 🍯 **琥珀暖黃 (`#F4A261` / 底色 `#FFF3E0`)**：核心金句、螢光筆畫線與貼圖底色。
     - 🌿 **鼠尾草綠 (`#6B9080` / 底色 `#EAF4F4`)**：`💭 想一想` 互動引導提問框。
     - 🍑 **珊瑚柔粉 (`#E07A5F` / 底色 `#FDE8E4`)**：道德衝突、兩難警示或關鍵轉折。
2. **互動功能規格（零外部框架依賴、單一 HTML 可離線執行）**：
   - 支援「⬅️ 上一頁 / 下一頁 ➡️」按鈕、鍵盤左右方向鍵翻頁、頂部進度條與圓點導航。
   - 每頁配備 **`[💡 補充 / 更多.. ▾]`** 互動膠囊按鈕，點擊平滑展開/收合深度知識抽屜。
   - 左上角提供「🏠 返回總目錄 (`../index.html`)」按鈕，方便在 GitHub Pages 上自由切換單元。
