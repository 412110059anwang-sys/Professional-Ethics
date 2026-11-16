# 📚 LLM & Ethics Research Wiki — 全局索引 (Master Index)

> 本檔案為知識庫的**內容導向目錄 (Content-Oriented Catalog)**。由 LLM Agent 於每次 `ingest`、`query` 歸檔或 `lint` 時自動維護更新。
> Agent 在回答任何研究問題前，應**優先讀取本檔案**以定位相關頁面。

---

## 🗺️ 宏觀綜述 (Overview & Synthesis)
- [[overview/synthesis|LLM 與專業倫理研究全景綜述 (Synthesis)]] — 彙整目前知識庫對於 LLM 預訓練/後訓練、測試時計算，以及規範倫理學、七步道德決策模型與 AI Alignment 的整體認知。 `(sources: 2)`

## 🧠 核心概念與演算法 (Concepts)
### 專業倫理與道德哲學 (`ethics/moral-theories` & `ethics/decision-making`)
- [[concepts/normative-moral-theories|規範倫理學六大理論架構 (Normative Moral Theories)]] — 涵蓋道德相對主義（主觀/文化）、道德絕對主義、康德義務論（定言令式）、效益主義（結果論与動物福祉）、W. D. Ross 顯見義務論與關懷倫理學。 `(sources: 1)`
- [[concepts/moral-decision-making-model|七步道德決策模型與十大道德原則 (Model for Moral Decision Making)]] — 詳解三大道德衝突（兩難、無知、困擾）、十大道德原則（尊嚴、不傷害、守信、補償、誠實、行善、分配/形式正義、感恩、自我提升）與七步透明化決策流程。 `(sources: 1)`

### 對齊、安全與跨領域映射 (`llm/alignment` & `llm/safety`)
- [[concepts/ethical-alignment-in-llms|倫理理論於 LLM 對齊與安全決策之映射 (Ethical Theories in LLM Alignment)]] — 將康德義務論、效益主義與 Ross 七步決策模型映射至 Constitutional AI、RLHF Reward Maximization 與 Deliberative Alignment。 `(sources: 2)`

### 後訓練、強化學習與推理 (`llm/post-training` & `llm/reasoning`)
- [[concepts/test-time-compute|測試時計算擴展 (Test-Time Compute Scaling)]] — 透過在推論階段分配更多計算資源（如長思維鏈思考、搜尋、驗證）來提升模型複雜推理能力的範式轉移。 `(sources: 1)`

### 推論系統與知識管理 (`llm/inference` & `llm/capabilities`)
- [[concepts/llm-wiki-pattern|LLM Wiki 知識庫模式 (Karpathy Pattern)]] — 由 LLM 增量編譯與維護結構化 Markdown 知識網，取代傳統無狀態檢索 (RAG) 的個人與研究知識管理架構。 `(sources: 1)`

## 🤖 模型家族與實例 (Models)
- *（尚無頁面，待 Ingest 技術報告後建立，如：DeepSeek-R1、Llama-4、Qwen3）*

## 📊 評測基準與資料集 (Benchmarks)
- *（尚無頁面，待 Ingest 文獻後建立，如：AIME、SWE-bench、LiveCodeBench）*

## ⚖️ 深度比較與專題分析 (Comparisons & Explorations)
- [[comparisons/deontology-vs-utilitarianism-vs-ross|義務論、效益主義、Ross 義務論與關懷倫理學之深度比較]] — 針對核心焦點（The Right vs. The Good）、手段與目的、情境彈性及理論盲點進行四維度矩陣對比。 `(sources: 1)`
- [[comparisons/rag-vs-llm-wiki|傳統 RAG 與 LLM Wiki 持續累積型知識庫之比較]] — 剖析檢索增強生成 (RAG) 與增量編譯型 Wiki 在跨文件綜合分析、維護成本與知識複利效應上的本質差異。 `(sources: 1)`

## 📄 文獻精讀摘要 (Sources)
- [[sources/2026-fall-moral-theories-and-decision-making|2026-Fall: Moral Theories and a Model for Moral Decision Making (專業倫理：道德理論與決策模型)]] — 梳理六大規範倫理理論、三大道德衝突類型、十大核心原則與七步職場倫理決策模型。 `(2026-11-16)`
- [[sources/2026-04-karpathy-llm-wiki|Karpathy: LLM Wiki — 以 LLM 建立個人知識庫的設計模式]] — 提出 Raw Sources、Wiki、Schema 三層架構與 Ingest/Query/Lint 標準操作，實現零維護成本的知識複利累積。 `(2026-11-16)`

## 🛠️ 頁面模板 (Templates)
- [[templates/source-template|文獻精讀摘要模板 (Source Template)]]
- [[templates/concept-template|核心概念與方法模板 (Concept Template)]]
- [[templates/model-template|模型技術報告模板 (Model Template)]]
- [[templates/comparison-template|跨維度比較分析模板 (Comparison Template)]]
