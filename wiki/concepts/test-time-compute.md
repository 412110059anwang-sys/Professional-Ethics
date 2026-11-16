---
title: "測試時計算擴展 (Test-Time Compute Scaling)"
category: concept
tags:
  - llm/reasoning
  - llm/test-time-compute
created: 2026-11-16
updated: 2026-11-16
source_count: 1
sources:
  - "[[overview/synthesis]]"
status: seed
---

# ⚡ 測試時計算擴展 (Test-Time Compute Scaling)

**測試時計算擴展 (Test-Time Compute Scaling / Inference-Time Scaling)** 指的是在模型推論（回答問題）階段，透過增加計算量（如生成更長的推理思維鏈 Long-CoT、執行多路徑搜尋、多數決投票或過程獎勵模型驗證），來換取更高準確率與複雜問題解決能力的技術範式。

> 📌 *本頁面目前為種子頁面 (Seed Page)。待後續 Ingest 相關推理模型論文（如 DeepSeek-R1、OpenAI o1/o3 相關研究、s1 等）後，將由 Agent 自動擴充演算法細節與實驗數據。*

---

## 核心技術路徑
1. **長思維鏈強化學習 (Long-CoT RL)**：透過可驗證獎勵（如數學答案、程式碼測試案例）進行強化學習，讓模型自主學會拆解問題、自我檢查與回溯（Backtracking）。
2. **搜尋與驗證 (Search & Verification)**：結合 Best-of-N、Beam Search、MCTS 與 Process Reward Model (PRM)。
