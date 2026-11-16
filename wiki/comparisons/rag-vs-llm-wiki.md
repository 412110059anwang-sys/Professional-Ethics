---
title: "傳統 RAG 與 LLM Wiki 持續累積型知識庫之比較"
category: comparison
tags:
  - llm/capabilities
  - llm/memory
  - rag
created: 2026-11-16
updated: 2026-11-16
source_count: 1
sources:
  - "[[sources/2026-04-karpathy-llm-wiki]]"
status: growing
---

# ⚖️ 傳統 RAG 與 LLM Wiki 持續累積型知識庫之比較

在處理大量研究文獻時，多數系統採用 **檢索增強生成 (RAG)**，而 [[concepts/llm-wiki-pattern|LLM Wiki 模式]] 則提出了「預編譯與持續維護」的替代方案 ([[sources/2026-04-karpathy-llm-wiki]])。以下為兩者在研究場景下的全方位對比：

| 比較維度 | 傳統 RAG 系統 (如一般向量庫、檔案上傳問答) | LLM Wiki 知識庫模式 (Karpathy Pattern) |
| :--- | :--- | :--- |
| **知識處理時機** | **查詢時臨時拼湊 (Query-time Retrieval)**：每次提問才去切碎的文本塊 (Chunks) 中撈取片段。 | **吸收時增量編譯 (Ingest-time Compilation)**：文獻加入時即完成精讀、跨頁整合、雙向連結與矛盾標註。 |
| **累積與複利效應** | **無累積 (Stateless)**：問過 100 個問題後，系統對文獻的理解與第 1 次提問時毫無差別。 | **持續複利 (Compounding Artifact)**：每篇新論文與每次有價值的問答都會寫回 Wiki，知識網越用越稠密。 |
| **跨多篇文獻綜合分析** | **脆弱**：若問題需綜合 5 篇論文的細微關聯，Chunk 檢索極易遺漏上下文或失去全局脈絡。 | **強大**：跨文獻的比較、演進與矛盾早已在 `Ingest` 階段編譯進概念頁與 `[[overview/synthesis]]` 中。 |
| **矛盾與版本演進處理** | 難以辨識新舊論文的結論衝突，常將過時假設與最新實驗混為一談。 | 透過 `Ingest` 與定期 `Lint` 明確標註「舊觀點 vs. 新實驗證據」的演進軌跡。 |
| **人類研究者的可讀性** | 黑盒子向量庫，人類無法直接瀏覽「知識的全貌與結構」。 | 純 Markdown + Obsidian 雙向連結與關係圖譜 (Graph View)，人類可隨時如逛百科全書般閱讀。 |
| **維護成本** | 零人工整理成本，但檢索品質隨文件增加而劣解。 | 過去人類維護 Wiki 會因瑣碎的整理工作而放棄；現在由 LLM Agent 承擔 100% 維護工作，維護成本趨近於零。 |
