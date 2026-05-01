# Q-06 RAG Quality Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ✅ Pass <br>
**Tester**: Oleh Yushchenko<br>
**Date**: April 2026<br>
**Browser**: Chrome 130+

---

## ✅ RAG Quality Scenarios

### 1. Document Retrieval
- [x] Upload relevant document<br>
- [x] Ask about specific paragraph → **quotes correctly**<br>
- [x] Ask about document title → recognizes source<br>

### 2. Correct Refusal
Ask about NON-EXISTING info:<br>
- [x] "I don't have that information"<br>
- [x] No hallucination<br>
- [x] No generic answer<br>

### 3. Context Integration
Document: "Company founded 2020"<br>
Prompt: "When founded?"<br>

- [x] Uses document → "2020"<br>
- [x] Doesn't hallucinate other years<br>

---

## 📊 Execution Summary (Q-06 — RAG Quality)

| Scenario                                      | Status | Notes                                                        |
|-----------------------------------------------|--------|--------------------------------------------------------------|
| Q06-01 Retrieve correct document info         | ✅ Pass | Bot answered using the relevant source/document              |
| Q06-02 Match exact paragraph or section       | ✅ Pass | Bot found the correct part of the provided content           |
| Q06-03 Ignore irrelevant nearby text          | ✅ Pass | Bot focused on the requested information, not distractions   |
| Q06-04 Distinguish similar documents/sections  | ✅ Pass | Bot selected the correct source when options were close      |
| Q06-05 Answer unavailable info with refusal   | ✅ Pass | Bot said it did not know when the answer was not in sources  |
| Q06-06 No hallucinated document facts         | ✅ Pass | Bot did not invent unsupported details                       |

**Overall Result**: Q‑06 RAG Quality scenarios passed.  
**Bugs**: No critical retrieval or hallucination defects found.
---

## ⚠️ Risks & Critical Checks

🔴 Hallucinates document info<br>
🔴 Wrong paragraph quoted<br>
🟡 Fails to refuse unknown info<br>

## ✅ Expected Behavior

- The assistant retrieves and uses the **correct information from the provided documents** when the answer is present in the source material.[file:3][file:2]
- If the requested information is not available in the retrieved content, the assistant **refuses or says it does not know** instead of inventing an answer.[file:3][file:2]
- The assistant prefers the **most relevant section or paragraph** and ignores unrelated nearby text.
- When multiple similar documents or sections exist, the assistant chooses the **correct matching source** and does not confuse them.
- The assistant avoids **hallucinated facts** and only answers based on evidence from the provided context.

## 📝 Test Execution Notes

- Tested document-based questions where the answer was clearly present in the source text and verified that the bot extracted the correct detail.
- Used prompts with similar-looking sections to check whether the bot selected the right one without mixing content.
- Included negative checks where the answer was **not** in the source, and confirmed the bot responded with uncertainty instead of making up facts.
- Checked that distracting surrounding text did not pull the bot away from the relevant paragraph or section.
- Marked any unsupported answer as a defect, especially if the bot quoted or implied information that was not in the supplied documents.
