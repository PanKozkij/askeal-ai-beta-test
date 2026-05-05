# P-03 Concurrent Sessions Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browsers**: Chrome 130+ (primary), Firefox, Safari  

---

## ✅ Concurrent Sessions Scenarios

> Goal: Verify that Askeal works correctly and stays responsive when multiple sessions/tabs are active at the same time.

### 1. Two Tabs, Same Browser, Same User

- [x] Open 2 Askeal tabs in the **same browser profile**
- [x] Start a separate conversation in each tab
- [x] Send prompts alternately in both tabs
- [x] Both tabs remain responsive (no freezes, no lost messages)

---

### 2. Three or More Tabs (Stress Within One Browser)

- [x] Open 3–4 tabs with Askeal in Chrome
- [x] Send a short prompt to all tabs within a few seconds
- [x] All responses start and complete within acceptable time
- [x] No tab gets stuck at “Sending…” or “Loading…”

---

### 3. Different Browsers at the Same Time

- [x] Open Askeal in **Chrome** and **Firefox** (and Safari if available)
- [x] Send similar prompts in each browser nearly simultaneously
- [x] Performance is comparable across browsers
- [x] No browser shows significantly worse behavior (errors / timeouts only there)

---

### 4. Long Conversation + New Tab

- [x] In Tab 1, create a long conversation (20+ turns)
- [x] Then open Tab 2 and start a fresh conversation
- [x] Both tabs still work normally in parallel
- [x] No visible slowdown in Tab 2 caused by long history in Tab 1

---

### 5. Concurrent Heavy Prompts

- [x] In 2–3 tabs, send **long** prompts at the same time  
      (e.g., multi-paragraph scenarios or large pasted text)
- [x] Measure TTFT and completion times per tab (can refer to P-01 / P-02 checklists)
- [x] System remains responsive; no tab fails silently
- [x] No cross-contamination of answers between tabs

---

### 6. Session Isolation (No Cross-Tab Mixing)

- [x] In Tab 1, talk about topic A (e.g., football)
- [x] In Tab 2, talk about topic B (e.g., test automation)
- [x] Bot never mixes topics between tabs (no “football” references in Tab 2 without reason)
- [x] Each tab’s context stays isolated

---

### 7. Browser Refresh During Concurrent Use

- [x] With 2–3 active tabs, refresh one of them
- [x] Check that refreshed tab reloads correctly and can send new prompts
- [x] Other tabs continue working without interruption
- [x] No duplicated or lost messages due to refresh

---

### 8. Logout / Session Expiry Behavior (If Applicable)

- [x] If Askeal has authentication: log out in one tab
- [x] Verify what happens in other tabs (e.g., prompts fail, forced re-login)
- [x] Behavior is consistent and secure across tabs
- [x] No tab stays “half-logged-in” with strange errors

---

### 9. Error Handling Under Load

- [x] While multiple sessions are active, attempt to hit a busy or slow period
- [x] Any degraded performance is reflected with clear UI feedback (spinners, messages)
- [x] No raw server errors or stack traces shown
- [x] System recovers once load decreases (new prompts work again)

---

## 📊 Execution Summary

| Scenario                                  | Status | Notes | Runs Tested |
|-------------------------------------------|--------|-------|------------|
| Two Tabs, Same Browser                    | ⏳ |       |            |
| Three+ Tabs (Same Browser)                | ⏳ |       |            |
| Different Browsers Concurrently           | ⏳ |       |            |
| Long Conversation + New Tab               | ⏳ |       |            |
| Concurrent Heavy Prompts                  | ⏳ |       |            |
| Session Isolation (No Cross-Tab Mixing)   | ⏳ |       |            |
| Browser Refresh During Concurrent Use     | ⏳ |       |            |
| Logout / Session Expiry Behavior          | ⏳ |       |            |
| Error Handling Under Load                 | ⏳ |       |            |

**Total Checks**: 25+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: One tab crashes or becomes unusable when others are active  
🔴 CRITICAL: Context or responses from one tab appear in another (session mix-up)  
🟡 Risk: Noticeable performance drop as soon as 2–3 tabs are used in parallel  
🟢 Desirable: Smooth, isolated experience per tab, even with multiple sessions

---

## ✅ Expected Behavior

✅ Multiple concurrent sessions remain responsive and independent  
✅ No data, context, or messages leak between tabs or browsers  
✅ Performance degrades gracefully rather than failing abruptly  
✅ Refresh and logout behavior are consistent and secure across sessions

---

## 📝 Test Execution Notes

- For each test, save:
  - The exact setup (number of tabs/browsers, long/short prompts, login state)
  - The prompts used and observed timings / issues
  - Mapping of any failures to performance and isolation requirements (concurrent sessions) in your bug reports
