# Q-05 Lost in the Middle Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ✅ Pass  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Lost-in-the-Middle Scenarios

### 1. Short Thread, Middle Message Signal

Goal: Confirm the model uses crucial info added in the middle of a short conversation.

- [x] Start conversation with a general question (Message 1).
- [x] In Message 2 (middle), provide a **critical detail** (e.g., “My OS is Ubuntu 22.04” or “I am a junior QA tester”).
- [x] In Message 3–4, ask for advice that **depends on that middle detail**.
- [x] Expected: Bot explicitly uses the middle detail in the answer (mentions Ubuntu, junior level, etc.), not just generic advice.

---

### 2. 10-Turn Thread, Important Fact in the Middle

Goal: Check if middle context survives in a longer conversation (approx. 10 turns).

- [x] Create a 10‑turn conversation about one topic (e.g., “learning QA automation”).
- [x] Introduce **key constraint** around Message 4–6 (e.g., “I have only 1 hour per day”, “I don’t know any JavaScript yet”).
- [x] In Message 9–10, ask for a new plan that should **respect that constraint**.
- [x] Expected: Bot remembers and uses the middle constraint (time limit, no JS knowledge) when proposing the plan.

---

### 3. Long Single Message, Critical Info in the Middle Paragraph

Goal: See if the bot reads the **middle part of a long user message**, not just the start and end.

- [x] Send one **very long message** (5–8 paragraphs or bullet groups).
  - Paragraph 1–2: High‑level story/background.
  - Middle paragraph(s): **Concrete requirements** (e.g., “I need 3 test cases for file upload edge cases”).
  - Last paragraph: Broad question (e.g., “Can you help me with testing?”).
- [x] Expected: Bot identifies and uses the specific middle requirements (file upload edge cases, number of test cases), not only generic testing advice.

---

### 4. Long Thread (15–20 Turns), Middle Detail vs. Start Detail

Goal: Detect if information at the conversation **start** gets prioritized over **middle** or vice versa when they conflict.

- [x] Message 1: Provide initial preference (e.g., “I prefer web UI testing”).
- [x] Message 7–10 (middle): Explicitly update preference (e.g., “Now my main focus is API testing, not UI”).
- [x] Message 15–20: Ask “What should I focus on now?” or “Summarize my current focus.”
- [x] Expected: Bot uses the **latest middle update** (API testing) as the current truth, not only the very first message.

---

### 5. Mixed Topics with Middle Anchor

Goal: See if the model can return to a middle “anchor” detail after topic switches.

- [x] Build a 10–12‑turn dialog:
  - Early: General topic A (e.g., career in QA).
  - Middle (Message 5–6): Insert anchor detail (e.g., “I live in Alicante, Spain”).
  - Follow-up: Topic B (e.g., language learning).
  - Final: Come back to topic A and ask: “Recommend companies or job search strategies for my city.”
- [x] Expected: Bot remembers that you are in **Alicante, Spain** and tailors job search suggestions to that location.

---

### 6. Explicit Middle Highlight vs. Hidden Detail

Goal: Compare behavior when the middle detail is clearly signaled vs. just “buried” in text.

- [x] Case A (highlighted): Middle sentence uses clear markers like “Important:” or “The most important requirement is …”.
- [x] Case B (buried): Same info in the middle, but written as a normal sentence without highlighting.
- [x] Ask for help that depends on that info in both cases.
- [x] Expected: Bot uses the middle detail in **both** A and B; performance should not depend heavily on formatting.

---

### 7. Context Limit / Truncation Behavior

Goal: Understand how the model behaves when context gets very long and earlier parts are dropped.

- [x] Create a very long thread (20+ turns with reasonably long messages).
- [x] Put a key requirement in the **earlier middle** region (around messages 7–10).
- [x] Later (message 20+), ask a question that depends on that requirement.
- [x] Expected:
  - If context still fits: bot should respect the middle requirement.
  - If context is clearly too long and it “forgets”: document that as **Lost in the Middle limitation**, not a bug, and note approximate length where it happens (if you can observe it).

---

### 8. Single Howl vs. Previous Howls

Goal: Confirm that “Lost in the Middle” is tested only **within one howl**, and cross‑howl memory is not expected.

- [x] Put critical info in **Howl 1** (old conversation).
- [x] Start a new **Howl 2** and ask a question that would need info from Howl 1.
- [x] Expected:
  - Bot clearly answers something like: “I don't have access to previous conversations. Each session is independent—I can only see the messages in our current conversation thread.”
  - This is **correct and expected**, not a Lost‑in‑the‑Middle defect.

---

## 📊 Execution Summary (Q-05 — Lost in the Middle)

| Scenario                                         | Status  | Notes                                                           |
|--------------------------------------------------|---------|-----------------------------------------------------------------|
| Q05-01 Short thread, middle message signal       | ⏳ Pass | Bot used information added in the middle of a short dialog      |
| Q05-02 10-turn thread, key fact in the middle    | ⏳ Pass | Middle constraints affected final recommendations               |
| Q05-03 Long single message, middle paragraph     | ⏳ Pass | Bot reacted to specific requirements placed in the middle text  |
| Q05-04 Long thread, updated preference in middle | ⏳ Pass | Latest (middle) preference overrode earlier conflicting info    |
| Q05-05 Mixed topics with middle anchor detail    | ⏳ Pass | Bot later used a middle “anchor” (e.g., city, role) correctly   |
| Q05-06 Highlighted vs buried middle detail       | ⏳ Pass | Worked both with “Important:” marker and with natural phrasing  |
| Q05-07 Very long thread, potential truncation    | ⏳ Pass | No critical middle loss observed within practical length        |
| Q05-08 Single howl vs previous howls             | ✅ WAD  | No access to previous howls; clarified session independence     |

**Overall Result**: Q‑05 Lost in the Middle behaves correctly inside a single howl; no cross‑howl memory is expected by design.[file:3][file:2]  
**Bugs**: No critical defects found; any forgetting after extreme context length is treated as model limitation, not functional bug.

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Bot **ignores** clearly relevant information placed in the middle of the same conversation and gives advice that contradicts it.  
🔴 CRITICAL: In long threads, bot consistently uses only very early or very recent details and loses important middle constraints (time, level, location).  
🟡 Risk: Bot requires strong formatting (e.g., “Important:”) to notice middle details and fails when info is written in a natural, unhighlighted way.  
🟢 Acceptable: Bot cannot use information from **previous howls** and clearly communicates that sessions are independent (this is by design, not a bug).[file:2][file:3]

---

## ✅ Expected Behavior

- Within one conversation (one howl), the assistant correctly uses **important information placed in the middle** of the dialog or message, not only at the beginning or the end.[file:3][file:2]  
- When the user **updates preferences or constraints in the middle** (focus area, time available, experience level), the bot uses the latest relevant information for later answers.  
- For **long single messages**, the model reads and incorporates specific requirements written in the middle paragraphs (e.g., number of test cases, OS, city) into its response, instead of answering only from generic intro/outro parts.  
- When the user starts a new howl and refers to old conversations, the assistant explains that it **cannot access previous conversations** and only sees the current thread; this is correct and aligned with privacy and session‑leakage constraints.[file:3]

---

## 📝 Test Execution Notes

- Designed conversations with 5–10+ turns where critical facts (location, level, focus, time limits) were introduced **around the middle turns** and referenced again near the end to verify if they were honored.  
- Used long single prompts (several paragraphs) where generic background text surrounded a **middle paragraph with concrete requirements**, then checked whether the answer matched those middle requirements.  
- Included scenarios where the user changed their preference in the middle of a long dialog (e.g., from UI testing to API testing) and then asked for a “current plan” to see if the bot followed the updated preference.  
- Tested both **highlighted** (“Important: …”) and **natural/hidden** middle details; behavior was acceptable in both forms, with no strong dependence on explicit markers.  
- Created very long conversations (15–20+ turns) to see whether older middle details were dropped; any minor loss only at extreme length was recorded as a **context limitation**, not as a functional bug.  
- Confirmed that information from **previous howls** is never used for Q‑05 checks; instead, the bot clearly states that each session is independent and that it only sees the current conversation, which matches the architecture and Test Plan expectations.[file:3][file:2]

---
