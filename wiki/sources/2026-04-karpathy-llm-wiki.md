---
title: "Karpathy: LLM Wiki — 以 LLM 建立個人知識庫的設計模式"
category: source
tags:
  - llm/capabilities
  - knowledge-base
created: 2026-11-16
updated: 2026-11-16
source_file: "raw/articles/karpathy-llm-wiki.md"
authors: "Andrej Karpathy"
year: 2026
status: evergreen
---

# 📄 Karpathy: LLM Wiki — 以 LLM 建立個人知識庫的設計模式

- **原始檔案**：`raw/articles/karpathy-llm-wiki.md`
- **核心主題**：利用 LLM Agent 增量維護結構化 Markdown Wiki，解決傳統 RAG 無累積性與人類手動維護 Wiki 成本過高的痛點。

---

## 1. 核心觀點摘要 (Executive Summary)
多數人使用 LLM 處理文獻的方式停留在 RAG（上傳檔案、檢索碎片、生成答案），這種方式在每次提問時都必須從頭拼湊知識，完全沒有「知識累積」。
本文件提出 **[[concepts/llm-wiki-pattern|LLM Wiki]]** 模式：讓 LLM 在原始檔案與使用者之間，持續編譯並維護一個互相連結的 Markdown 知識庫。當新文獻加入時，LLM 負責閱讀、萃取並主動更新十幾個相關的概念頁、實體頁與全局綜述，標註新舊觀點的矛盾。知識只需編譯一次並保持更新，成為具備**複利效應的持久化資產 (Persistent, Compounding Artifact)**。

## 2. 系統架構與分工
- **IDE 與角色分工**：Obsidian 作為人類閱讀與檢視圖譜的 IDE；LLM Agent 作為程式設計師（負責所有摘要、雙向連結、歸檔與整理）；Wiki 則是共同演進的 Codebase。
- **三層架構**：
  1. `raw/`：不可變的原始文獻（論文、網頁擷取、本地圖片）。
  2. `wiki/`：LLM 完全掌控的生成式 Markdown 知識層。
  3. `AGENTS.md` / `CLAUDE.md`：約束 LLM 行為與格式的 Schema。
- **導航設計**：透過內容目錄 `[[index]]` 與時間日誌 `[[log]]`，在中型規模（約百篇文獻、數百個頁面）下無需依賴複雜的 Embedding RAG 即可高效運作。

## 3. 對本研究知識庫的啟發與實踐
本 LLM 研究知識庫即完全依照此文獻之藍圖實作，並針對 LLM 學術研究領域擴充了 `concepts/`、`models/`、`benchmarks/` 與 `comparisons/` 分類。
