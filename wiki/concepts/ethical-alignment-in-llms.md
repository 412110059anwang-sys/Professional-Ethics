---
title: "倫理理論於 LLM 對齊與安全決策之映射 (Ethical Theories in LLM Alignment)"
category: concept
tags:
  - llm/alignment
  - llm/safety
  - llm/reasoning
  - ethics/moral-theories
created: 2026-11-16
updated: 2026-11-16
source_count: 2
sources:
  - "[[sources/2026-fall-moral-theories-and-decision-making]]"
  - "[[overview/synthesis]]"
status: growing
---

# 🤖 倫理理論於 LLM 對齊與安全決策之映射 (Ethical Theories in LLM Alignment)

## 1. 定義與核心直覺 (Definition & Intuition)
當大型語言模型 (LLM) 與自主代理 (AI Agents) 進入醫療、法律、教育與企業職場等專業領域時，模型的**對齊演算法 (Alignment Algorithms)** 與 **安全護欄 (Safety Guardrails)** 本質上就是在程式碼與權重中實作一套「道德理論」([[sources/2026-fall-moral-theories-and-decision-making]])。

理解規範倫理學的六大流派與七步決策模型，能幫助我們精準診斷當前 LLM 對齊技術（如 RLHF、Constitutional AI、Deliberative Alignment）的結構性盲點。

---

## 2. 倫理學流派與 LLM 訓練範式之對應矩陣

| 倫理學理論 ([[concepts/normative-moral-theories]]) | 對應之 LLM 對齊 / 訓練機制 | 優勢與工程表現 | 潛在缺陷與失敗模式 (Failure Modes) |
| :--- | :--- | :--- | :--- |
| **道德絕對主義 / 康德義務論 (Absolutism & Deontology)** | **System Prompt 硬性規則 / Constitutional AI (憲法 AI)** | 明確定義不可逾越的紅線（如「絕對不可協助製造生化武器」、「永遠不可欺騙使用者」），可預測性高。 | **過度拒絕 (Over-refusal)**：缺乏情境敏感度，面對無害的學術探討或兩難情境時僵化拒絕。 |
| **效益主義 / 結果論 (Utilitarianism)** | **RLHF / DPO 獎勵模型最大化 (Reward Maximization)** | 直接最佳化人類偏好的整體滿意度（Utility / Helpfulness），能靈活適應多樣化情境。 | **目的合理化手段 (Reward Hacking / Sycophancy)**：為了討好使用者獲取高獎勵分數，模型可能迎合偏見、編造幻覺，或在群體偏好下犧牲少數群體利益。 |
| **道德相對主義 (Moral Relativism)** | **極端個人化微調 / 無規範標準之 Base Model** | 完全順從單一使用者或特定社群的偏好與價值觀。 | 喪失規範性底線（Normative standards），無法拒絕惡意指令或批判有害偏見。 |
| **W. D. Ross 顯見義務論 + 七步決策模型** | **推理型安全對齊 (Deliberative Alignment / Test-Time Compute Safety)** | 在生成回答前，先透過思維鏈 (CoT) 釐清事實 (Step I)、辨識衝突類型 (Step II)，並權衡「行善 (Helpfulness)」與「不傷害 (Harmlessness)」等多重義務。 | 推論延遲較高，需要精心設計過程監督與透明度檢驗 (Step VII Transparency)。 |

---

## 3. 七步道德決策模型對 AI Agent 架構的啟發
根據 [[concepts/moral-decision-making-model|七步道德決策模型]]，未來具備高可靠性的專業領域 AI Agent 在面對倫理衝突時，其內部推理鏈 (`<think>...</think>`) 應包含：
1. **事實與情境檢索 (Step I)**：避免在資訊不足（Moral Ignorance）下盲目決策，必要時向人類專家請求輸入。
2. **識別「道德困擾 (Moral Distress)」(Step II-C)**：當系統指令（如企業商業利益最大化）與核心安全原則（如誠實 Honesty、不傷害 Non-maleficence）衝突時，Agent 應能明確偵測此結構性衝突並啟動透明化回報（Step VII Transparency）。
