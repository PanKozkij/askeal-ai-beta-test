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

## 📊 Execution Summary (P-01 — Time to First Token)

| Scenario                             | Status | Notes |
|--------------------------------------|--------|-------|
| Short Prompt — Baseline              | ✅ Pass | Stable TTFT across 3 runs in same session |
| Short Prompt — New Sessions          | ✅ Pass | Consistent TTFT across fresh sessions |
| Medium Prompt (2–3 Sentences)        | ✅ Pass | No major degradation vs. short baseline |
| Long Prompt (Several Paragraphs)     | ✅ Pass | Slight increase, within acceptable limits |
| After Long Conversation (20+ Turns)  | ✅ Pass | No performance drop after long context |
| Multiple Tabs / Sessions Open        | ✅ Pass | No TTFT spike or stuck tab observed |
| Slow Network Simulation              | ✅ Pass | TTFT increased gracefully on Slow 3G |
| Error / Timeout Handling             | ✅ Pass | Spinner shown, no raw errors exposed |

**Overall Result**: P-01 Time to First Token passed.  
**Bugs**: No TTFT or responsiveness defects observed.

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Very long or random TTFT (user waits many seconds with no feedback)  
🔴 CRITICAL: First token never appears but no clear error is shown  
🟡 Risk: TTFT highly unstable between runs or sessions  
🟢 Desirable: Fast first token with visible loading indicator while generating

---

## ✅ Expected Behavior

✅ **First token appears** within a reasonable time for short and medium prompts.  
✅ **TTFT degrades gracefully** for longer prompts without UI freeze.  
✅ **Long conversations (20+ turns)** do not significantly increase first token delay.  
✅ **Multiple tabs** open simultaneously do not cause extreme TTFT spikes.  
✅ **Slow network** conditions increase TTFT but do not break the response flow.  
✅ **Loading indicator/spinner** is always visible while waiting for first token.  
✅ **Clear error message** shown if backend fails, no raw stack traces exposed.

---

### 📝 Test Execution Notes

- **Measurement method**: Chrome DevTools Network tab + manual stopwatch observation.
- **Baseline short prompt**: 3 runs in same session → stable TTFT, no outliers.
- **New sessions**: Same prompt across 3 fresh sessions → consistent performance.
- **Medium prompt**: 2–3 sentence cybersecurity question → marginal TTFT increase.
- **Long prompt**: Multi-paragraph paste → slight delay, first token still appeared.
- **20+ turns context**: Long conversation then short prompt → no noticeable drop.
- **Multiple tabs**: 3 simultaneous tabs → all received first token without freezing.
- **Slow 3G throttle**: DevTools throttle applied → TTFT increased, no broken state.
- **Timeout scenario**: Slow backend conditions → spinner displayed correctly.
- No blank screens, infinite loaders, or raw error dumps observed in any scenario.
