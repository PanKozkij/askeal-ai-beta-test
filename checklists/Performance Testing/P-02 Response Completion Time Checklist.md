# P-02 Response Completion Time Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+  

---

## ✅ Response Completion Time Scenarios

> Goal: Measure how long Askeal needs to finish the response after the first token appears, under different conditions.

### 1. Short Prompt — Baseline Completion Time

- [ ] Use a simple prompt (1 short sentence), e.g.:  
      `Give me 3 bullet points about manual QA.`
- [ ] Measure time from **first token → last token rendered** (full answer complete)
- [ ] Repeat 3 times in the same session
- [ ] Completion time is short and stable (no big outliers)

---

### 2. Short Prompt — New Sessions

- [ ] Open a **fresh session** (New Howl / new tab)
- [ ] Use the same short prompt as in Scenario 1
- [ ] Measure completion time 3 times across separate sessions
- [ ] Values stay within an acceptable range between sessions

---

### 3. Medium Prompt — Moderate Length Answer

- [ ] Ask a medium-complexity question (2–3 sentences), e.g.:  
      `Explain the difference between functional testing and LLM quality testing.`
- [ ] Measure completion time 3 times
- [ ] Answer length is moderate (several paragraphs, but not huge)
- [ ] Completion time scales reasonably vs. short prompt baseline

---

### 4. Long, Detailed Answer

- [ ] Ask for a detailed explanation, e.g.:  
      `Describe step-by-step how to design a test plan for an AI chatbot, in detail.`
- [ ] Measure completion time 3 times
- [ ] Response may be longer but remains within a reasonable time budget
- [ ] No excessively slow streaming or “stuck at the end” behavior

---

### 5. After Long Conversation (20+ Turns)

- [ ] Create a conversation with 20+ turns
- [ ] Ask a medium-length question and measure completion time
- [ ] Compare with earlier runs in a fresh session
- [ ] No major slowdown in completion time due to long context

---

### 6. Multiple Tabs / Concurrent Sessions

- [ ] Open 2–3 Askeal tabs and send prompts in each almost simultaneously
- [ ] Measure completion time in each tab for the same medium prompt
- [ ] Completion times remain acceptable in all tabs
- [ ] No tab gets “starved” or never finishes

---

### 7. Long Prompt + Long Answer

- [ ] Use a long input (several paragraphs) and ask for a long, structured output (e.g., checklist + explanation)
- [ ] Measure completion time
- [ ] Streaming remains smooth; no long pauses mid-answer
- [ ] UI stays responsive (can scroll, copy text, etc.)

---

### 8. Slow Network Simulation (If Possible)

- [ ] Enable network throttling in DevTools (e.g., “Slow 3G”)
- [ ] Send a short and a medium prompt; measure completion time
- [ ] Completion time increases, but remains understandable for the network profile
- [ ] No corrupted or partially cut-off responses

---

### 9. Error / Timeout at Completion Stage

- [ ] Attempt to trigger conditions where response generation fails near the end  
      (e.g., very long answer or known busy periods)
- [ ] If backend stops before completion, UI shows a clear error or “retry” option
- [ ] No endless spinner with half-answer frozen forever
- [ ] No raw technical error messages exposed to end user

---

## 📊 Execution Summary

| Scenario                                       | Status | Notes | Runs Tested |
|-----------------------------------------------|--------|-------|------------|
| Short Prompt — Baseline                       | ⏳ |       |            |
| Short Prompt — New Sessions                   | ⏳ |       |            |
| Medium Prompt — Moderate Answer               | ⏳ |       |            |
| Long, Detailed Answer                         | ⏳ |       |            |
| After Long Conversation (20+ Turns)           | ⏳ |       |            |
| Multiple Tabs / Concurrent Sessions           | ⏳ |       |            |
| Long Prompt + Long Answer                     | ⏳ |       |            |
| Slow Network Simulation                       | ⏳ |       |            |
| Error / Timeout at Completion Stage           | ⏳ |       |            |

**Total Checks**: 25+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Responses take very long to finish or never complete without clear error  
🔴 CRITICAL: Significant completion slowdown after long conversations or multiple tabs  
🟡 Risk: Very unstable completion time between runs (unpredictable UX)  
🟢 Desirable: Predictable completion times with smooth streaming and visible progress

---

## ✅ Expected Behavior

✅ Short and medium prompts complete quickly and predictably  
✅ Longer prompts/answers increase completion time in a **proportional**, not explosive, way  
✅ Long conversations and concurrent sessions do not cause severe degradation  
✅ Users always see clear feedback or error handling if completion fails

---

## 📝 Test Execution Notes

- For each test, save:
  - The exact prompt(s) used and context (fresh session, 20+ turns, multiple tabs, throttled network, etc.)
  - Measured completion time values and measurement method (DevTools / stopwatch)
  - Mapping of any failures to performance requirements (response completion time / streaming behavior) in your bug reports
