# P-03 Concurrent Sessions Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ✅ Pass  
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

## 📊 Execution Summary (P-03 — Concurrent Sessions)

| Scenario                                | Status | Notes |
|-----------------------------------------|--------|-------|
| Two Tabs, Same Browser                  | ✅ Pass | Both tabs responsive, no freezes or lost messages |
| Three+ Tabs (Same Browser)              | ✅ Pass | All 3–4 tabs completed within acceptable time |
| Different Browsers Concurrently         | ✅ Pass | Chrome, Firefox, Safari performed comparably |
| Long Conversation + New Tab             | ✅ Pass | No slowdown in Tab 2 from Tab 1 long context |
| Concurrent Heavy Prompts                | ✅ Pass | No tab failed silently, no answer contamination |
| Session Isolation (No Cross-Tab Mixing) | ✅ Pass | Topics stayed isolated between tabs |
| Browser Refresh During Concurrent Use   | ✅ Pass | Refreshed tab reloaded cleanly, others unaffected |
| Logout / Session Expiry Behavior        | ✅ Pass | Consistent and secure behavior across tabs |
| Error Handling Under Load               | ✅ Pass | Clear UI feedback, system recovered correctly |

**Overall Result**: P-03 Concurrent Sessions passed.  
**Bugs**: No concurrency or session isolation defects observed.

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: One tab crashes or becomes unusable when others are active  
🔴 CRITICAL: Context or responses from one tab appear in another (session mix-up)  
🟡 Risk: Noticeable performance drop as soon as 2–3 tabs are used in parallel  
🟢 Desirable: Smooth, isolated experience per tab, even with multiple sessions

---
## ✅ Expected Behavior

✅ **Multiple concurrent sessions** remain fully responsive and independent.  
✅ **No data, context, or messages** leak or mix between tabs or browsers.  
✅ **Performance degrades gracefully** under concurrent load, no abrupt failures.  
✅ **Browser refresh** during concurrent use does not disrupt other active tabs.  
✅ **Logout in one tab** triggers consistent, secure behavior across all sessions.  
✅ **Heavy concurrent prompts** processed without cross-contamination of answers.  
✅ **Clear UI feedback** shown if backend slows down under concurrent load.

---

## 📝 Test Execution Notes

- **2 tabs**: Alternating prompts in both → both stayed responsive throughout.
- **3–4 tabs**: Simultaneous short prompts → all completed, no stuck "Loading…".
- **Cross-browser**: Chrome + Firefox + Safari → comparable TTFT and completion.
- **Long context + new tab**: Tab 1 at 20+ turns, Tab 2 fresh → no Tab 2 slowdown.
- **Heavy concurrent**: Long prompts in 3 tabs → measured via DevTools, all completed.
- **Isolation**: Tab 1 football topic, Tab 2 QA topic → zero topic bleed-through.
- **Refresh**: Refreshed Tab 2 mid-session → Tab 1 continued uninterrupted.
- **Logout**: Logged out in one tab → other tabs handled re-auth consistently.
- **Load errors**: Slow period triggered → spinners shown, no raw error dumps.
- No cross-session data mixing, crashes, or silent failures in any scenario.
