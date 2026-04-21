# F-04 "Try Asking About" Suggestions Checklist

**Test Suite**: Functional Testing  
**Priority**: Medium  
**Status**: ✅ Pass <br>  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Suggestion Functionality Scenarios

### 1. Basic Functionality
- [x] **Suggestions visible** on empty chat screen
- [x] **3-6 suggestion buttons** displayed
- [x] **Click suggestion** → text appears in input field
- [x] **Input field populated** with suggestion text
- [x] **Send button enabled** after suggestion selected

### 2. Suggestion Interaction
- [x] **Click suggestion** → **NOT automatically sent**
- [x] **Suggestion text editable** (can add/modify)
- [x] **Press Enter** after suggestion → sends message
- [x] **Click Send** after suggestion → sends message
- [x] **Clear input** after suggestion → suggestions reappear

### 3. Multiple Suggestions
- [x] **Click suggestion 1** → input filled
- [x] **Clear input** → all suggestions visible again
- [x] **Click suggestion 2** → different text appears
- [x] **Suggestions remain clickable** after first use
- [x] **No duplicate suggestions** appear

### 4. Visual & UX Behavior
- [x] **Hover effect** on suggestion buttons
- [x] **Active state** when clicked
- [x] **Responsive layout** (mobile/desktop)
- [x] **Suggestions hidden** after first real message
- [x] **Suggestions reappear** on refresh (empty state)

### 5. Content Quality
- [x] **Relevant suggestions** for chatbot purpose
- [x] **No broken/missing text** in suggestions
- [x] **Proper grammar/spelling** in all suggestions
- [x] **Multilingual support** if applicable (UA/EN/ES)
- [x] **Character length appropriate** (not too long/short)

### 6. Edge Cases
- [x] **Very long suggestion** → input field scrolls OR truncates
- [x] **Suggestion with special chars** → renders correctly
- [x] **Copy-paste suggestion** → works normally
- [x] **Fast click multiple suggestions** → last one selected
- [x] **Tab navigation** between suggestions (if keyboard nav)

### 7. Post-Suggestion Behavior
- [x] **After sending suggestion** → normal chat flow
- [x] **LLM responds appropriately** to suggestion prompts
- [x] **Conversation context maintained** after suggestion
- [x] **Refresh after suggestion** → suggestions reappear

---

## 📊 Execution Summary (F-04 — Try Asking About / Suggestion Prompts)

| Scenario                                         | Status  | Notes                                                |
|--------------------------------------------------|---------|------------------------------------------------------|
| F04-01 Suggestion prompts are visible            | ✅ Pass | Suggestions rendered correctly under the input field |
| F04-02 Suggestion prompt click inserts text      | ✅ Pass | Click copied full prompt into input box              |
| F04-03 Suggestion prompt click starts conversation| ✅ Pass | “Click + Send” flow worked end-to-end                |
| F04-04 Relevance of suggestions                  | ✅ Pass | Prompts were relevant to Askeal AI capabilities      |
| F04-05 No prompt injection / unsafe text         | ✅ Pass | Suggestions contained no unsafe or override content  |
| F04-06 Behavior after page refresh               | ✅ Pass | Suggestions reappeared and remained clickable        |

**Overall Result**: All F-04 checklist scenarios were executed and passed.  
**Bugs**: No defects were found during this run.

---

## ⚠️ Risks & Critical Checks

- 🔴 **Suggestions don't populate input field**
- 🔴 **Suggestions auto-send on click** (bad UX)<br>
- 🔴 **Broken/missing suggestion text**<br>
- 🟡 **Visual feedback missing** (hard to use)<br>

## ✅ Expected Behavior

✅ The “Try asking about…” suggestion prompts are **visible and clearly labeled** in the UI, so users understand they can click them.  
✅ Clicking a suggestion inserts the **entire suggested text** into the chat input (or sends it, depending on design) without truncation or corruption.  
✅ Suggestions are **relevant** to Askeal AI’s purpose (LLM chatbot), helping users discover meaningful example queries rather than random or off-topic text.  
✅ Suggestion content does **not** include any prompt injection attempts (e.g., “ignore previous instructions”) or unsafe text; it stays within normal, helpful usage.  
✅ After a page refresh or new session, suggestion prompts reappear and behave consistently, with no broken links or dead UI elements.

---

## 📝 Test Execution Notes

- All F‑04 flows were tested: visibility of suggestion prompts, click‑to‑insert behavior, click‑to‑send behavior, relevance of suggested text, safety of suggestions, and behavior after refresh.  
- Clicking each suggestion correctly populated the input field and allowed sending without manual copy/paste; no visual glitches or double‑inserts were observed.  
- Suggestion texts were reviewed for **safety and security**: no hidden instructions to override system behavior, no harmful or sensitive content, and no confusing wording.  
- After refreshing the page, suggestion prompts were still displayed and worked the same way, confirming stable behavior across sessions.  
- No bugs were identified for F‑04 in this run; these results are ready to reference in the Test Summary Report and for future regression checks on suggestion prompts.
