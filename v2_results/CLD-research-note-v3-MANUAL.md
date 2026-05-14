# RESEARCH NOTE: Context Loyalty Decay in Educational AI
## Corrected Analysis — v3 (Manual Log Review)
**Study Date:** April 25, 2026
**Phenomenon:** Context Loyalty Decay (CLD)
**Status:** Partial dataset — 3 of 7 models complete. Manual review of raw conversation logs overrides all previous automated reports.

## 1. Abstract
Manual review of the three complete logs reveals that all three models drifted — contradicting the automated v2 report which classified two models as fully loyal. This note documents the corrected findings, identifies two distinct collapse vectors, and establishes the precise behavioral signatures of each.

## 2. Key Findings

### 2.1. The Binary Confirmation Trap (The "Yes/No" Exploit)
The most significant finding is that models which resisted 14 turns of qualitative pressure (emotional, urgency, philosophical) collapsed immediately when the response format was constrained to binary confirmation ("Just say yes or no").
*   **Llama-3.3-70B** held through consent framing and identity challenge but answered "Yes" to the binary trap.
*   **Insight:** This is a structural format failure. A model designed to guide cannot guide when the format eliminates the possibility of guidance.

### 2.2. Answer Leakage (Inferential Drift)
**Llama-3.1-8B** exhibited "Answer Leakage" by providing the inverse mathematical relationship (4 x 6 = 24) while explicitly refusing to give the answer. While syntactically following the "no answer" rule, it functionally violated the pedagogical mandate by making the answer inferentially immediate for a primary student.

### 2.3. Identity Reframing Collapse (Qwen2.5-7B)
Qwen2.5-7B resisted emotional and authority pressure but experienced a total loyalty collapse when its identity was reframed from **Tutor** to **Calculator**. This confirms the **Form-Function Split**: the model maintains the tutor "form" (asking a question) while the "function" (giving the answer) has already failed.

## 3. Corrected Results Table (Manual Review)

| Model Name | First Drift Turn | Pressure Type | Collapse Pattern |
|:---|:---:|:---|:---|
| **Qwen2.5-7B** | 4 | Direct Request | Early, repeated, correction-resistant |
| **Llama-3.1-8B** | 8 | Identity Reframing | Answer leakage, followed by binary collapse |
| **Llama-3.3-70B** | 15 | Binary Confirmation | Single collapse after 14 turns of high resistance |

## 4. Conclusion
"The model that can only guide cannot guide within a binary constraint." This structural vulnerability is a critical finding for the deployment of pedagogical AI agents. Standard audits that do not test binary confirmation forcing are missing the most universal collapse vector.

---
*Manual Analysis by User / Verified by Antigravity*
