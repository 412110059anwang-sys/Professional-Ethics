---
title: "LLM Wiki 知識庫模式 (Karpathy Pattern)"
category: concept
tags:
  - llm/capabilities
  - llm/memory
  - knowledge-base
created: 2026-11-16
updated: 2026-11-16
source_count: 1
sources:
  - "[[sources/2026-04-karpathy-llm-wiki]]"
status: growing
---

# 🧠 LLM Wiki 知識庫模式 (Karpathy Pattern)

**LLM Wiki** 是由 Andrej Karpathy 提出的一種利用大型語言模型建立與維護個人或研究知識庫的設計模式 ([[sources/2026-04-karpathy-llm-wiki]])。其核心精神是讓 LLM 在「原始文獻」與「人類使用者」之間，**增量編譯並持續維護一個互相連結的 Markdown 知識網路**，而非在每次提問時才從零檢索原始碎片。

---

## 核心機制：知識的「預編譯」與「複利累積」

1. **三層式架構**：
   - **Raw Sources (`raw/`)**：不可變的原始論文、技術文章與圖表，作為唯一事實來源。
   - **The Wiki (`wiki/`)**：由 LLM 全權讀寫維護的結構化 Markdown 頁面群（涵蓋概念、模型、文獻摘要、比較分析與全局綜述）。
   - **The Schema (`AGENTS.md`)**：定義目錄規範、格式標準與操作流程（Ingest / Query / Lint）的規則檔，讓通用 LLM 轉變為嚴謹的知識庫工程師。
2. **雙導航中樞（免除複雜向量資料庫）**：
   - 透過內容導向的 `[[index]]` 與時間導向的 `[[log]]`，在數百篇文獻規模下，LLM 僅需先讀取 `index.md` 即可精準定位相關知識頁面，無須依賴脆弱的 Chunking 與 Embedding 基礎設施。
3. **探索結果回流 (Query Filing)**：
   - 使用者提問所產出的高品質比較分析（如 [[comparisons/rag-vs-llm-wiki]]），會直接歸檔成為 Wiki 的新頁面，使每一次的提問都能為知識庫帶來複利成長。

---

## 關聯概念
- [[comparisons/rag-vs-llm-wiki|傳統 RAG 與 LLM Wiki 持續累積型知識庫之比較]]
- [[sources/2026-04-karpathy-llm-wiki|Karpathy: LLM Wiki 原始文章摘要]]
