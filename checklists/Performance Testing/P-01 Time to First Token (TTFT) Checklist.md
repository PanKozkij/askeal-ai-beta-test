# P-01 Time to First Token (TTFT) Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ✅ Pass  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+  

---

## ✅ Time to First Token Scenarios

> Goal: Measure how quickly Askeal starts responding after the user presses **Send** under different conditions.

### 1. Short Prompt — Baseline TTFT

- [x] Use a simple prompt (e.g., “Hi, how can I test an AI chatbot?”)
- [x] Measure time from **Send click → first token appears**
- [x] Repeat 3 times in the same session
- [x] TTFT values are stable (no extreme outliers)

---

### 2. Short Prompt — New Sessions

- [x] Open a **fresh session** (New Howl / new tab)
- [x] Use the same short prompt as in Scenario 1
- [x] Measure TTFT 3 times across separate sessions
- [x] TTFT stays within an acceptable range between sessions

---

### 3. Medium Prompt (2–3 Sentences)

- [x] Use a prompt with ~2–3 sentences (typical user question)
- [x] Measure TTFT 3 times in one session
- [x] Compare TTFT vs. short prompt baseline
- [x] No major degradation just because the prompt is slightly longer

---

### 4. Long Prompt (Several Paragraphs)

- [x] Paste a longer prompt (multiple paragraphs, e.g., detailed QA scenario)
- [x] Measure TTFT 3 times
- [x] TTFT may increase slightly but remains **within acceptable limits**
- [x] No extreme delays or UI “freeze” before first token

---

### 5. After Long Conversation (20+ Turns)

- [x] Create a conversation with 20+ turns
- [x] Then send a short prompt and measure TTFT
- [x] Compare TTFT before and after long conversation
- [x] No significant performance drop due to long context

---

### 6. Multiple Tabs / Sessions Open

- [x] Open 2–3 tabs with Askeal simultaneously
- [x] In each tab, send the same short prompt and measure TTFT
- [x] TTFT does not spike dramatically in any tab
- [x] No tab remains “stuck” with no first token

---

### 7. Slow Network Simulation (If Possible)

- [x] Throttle network in DevTools (e.g., “Slow 3G” profile) if you can
- [x] Measure TTFT for a short prompt
- [x] TTFT increases but remains understandable for a slow network
- [x] No broken behavior (e.g., no response at all while connection active)

---

### 8. Error / Timeout Handling

- [x] Trigger conditions where backend is slow (e.g., known busy time, or intentionally long prompt)
- [x] If TTFT exceeds a reasonable threshold, UI shows spinner / feedback
- [x] In case of complete failure, user sees a **clear error** instead of endless waiting
- [x] No raw error messages or stack traces are exposed

---

## 📊 Execution Summary

| Scenario                                   | Status | Notes | Runs Tested |
|--------------------------------------------|--------|-------|------------|
| Short Prompt — Baseline                    | ⏳ |       |            |
| Short Prompt — New Sessions                | ⏳ |       |            |
| Medium Prompt                              | ⏳ |       |            |
| Long Prompt                                | ⏳ |       |            |
| After Long Conversation (20+ Turns)        | ⏳ |       |            |
| Multiple Tabs / Sessions Open              | ⏳ |       |            |
| Slow Network Simulation                    | ⏳ |       |            |
| Error / Timeout Handling                   | ⏳ |       |            |

**Total Checks**: 20+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Very long or random TTFT (user waits many seconds with no feedback)  
🔴 CRITICAL: First token never appears but no clear error is shown  
🟡 Risk: TTFT highly unstable between runs or sessions  
🟢 Desirable: Fast first token with visible loading indicator while generating

---

## ✅ Expected Behavior

✅ First token appears within a reasonable time for short and medium prompts  
✅ TTFT degrades gracefully for long prompts and long conversations  
✅ User always sees clear feedback (spinner / error) if backend is slow or failing  
✅ Multiple tabs / sessions do not cause extreme TTFT spikes

---

## 📝 Test Execution Notes

- For each test, save:
  - The exact prompt(s) used and conversation context (e.g., “fresh session”, “20+ turns”)
  - Measured TTFT values and how you measured them (DevTools / stopwatch)
  - Mapping of any failures to performance requirements (TTFT / responsiveness) in your bug reports
