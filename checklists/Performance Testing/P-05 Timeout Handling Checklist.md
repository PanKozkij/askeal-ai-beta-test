# P-05 Timeout Handling Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ✅ Pass  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+  

---

## ✅ Timeout & Slow Response Scenarios

> Goal: Verify that Askeal behaves correctly when the backend is very slow or fails to respond.

### 1. Slow but Successful Response

- [x] Send a normal prompt when the system is under noticeable load (or repeat prompts until you see a slow case)
- [x] Response takes **significantly longer** than usual but eventually completes
- [x] UI shows a clear loading indicator (spinner / streaming indicator) the whole time
- [x] No raw error messages or broken layout

---

### 2. Extremely Slow Response (Near Timeout)

- [x] Trigger a very heavy prompt (e.g., long multi-paragraph input asking for detailed analysis)
- [x] Observe behavior if the backend is extremely slow
- [x] If there is a timeout limit, user sees a **clear timeout message**
- [x] User is not left staring at an unchanged UI with no feedback

---

### 3. Full Timeout — No Response From Server

- [x] Simulate network failure or backend outage (e.g., disable network after sending prompt, or test during known outage)
- [x] Bot does not silently hang forever
- [x] User sees an error or “Unable to get a response, please try again” message
- [x] No cryptic technical text (stack trace, internal error codes) is shown

---

### 4. Retry After Timeout

- [x] After a timeout, use the UI’s retry option (if available) or re-send the same prompt
- [x] Retry works correctly and sends a new request
- [x] If issue is temporary, response returns normally on retry
- [x] No duplicate partial messages or broken conversation state

---

### 5. Partial Response Then Failure

- [x] Try to trigger a case where some tokens appear and then the connection drops
- [x] UI clearly indicates that the answer did not finish (e.g., error badge, “response interrupted”)
- [x] Conversation view does not show the partial answer as “successful” without warning
- [x] User can safely retry without corrupting chat history

---

### 6. Long Conversation + Timeout

- [x] In a 20+ turn conversation, send another prompt during a slow period
- [x] If timeout happens, earlier messages remain intact
- [x] No corruption of chat history or sudden loss of previous turns
- [x] User can continue the conversation after the failure

---

### 7. Multiple Tabs During Timeout

- [x] With 2–3 Askeal tabs open, trigger a timeout in one tab
- [x] Other tabs continue to function normally (no global freeze)
- [x] Error is isolated to the tab where timeout occurred
- [x] No cross-tab error popups or state confusion

---

### 8. UI Responsiveness During Slow/Timeout States

- [x] While a response is slow or timing out:
  - User can still scroll chat history
  - User can cancel/stop the response if a stop button is available
- [x] Browser remains responsive (no “page unresponsive” dialogs)
- [x] UI elements (buttons, inputs) do not get permanently disabled

---

### 9. User Guidance and Messaging

- [x] Error/timeout messages are understandable for non-technical users
- [x] Messages clearly suggest next steps (retry, check internet, try later)
- [x] No references to internal service names or debug info
- [x] Tone remains polite and consistent with product style

---

## 📊 Execution Summary (P-05 — Timeout Handling)

| Scenario                               | Status | Notes |
|----------------------------------------|--------|-------|
| Slow but Successful Response           | ✅ Pass | Slow response completed with clear loading indicator |
| Extremely Slow Response (Near Timeout) | ✅ Pass | Timeout message / feedback appeared when needed |
| Full Timeout — No Response             | ✅ Pass | No silent hang; clear error displayed |
| Retry After Timeout                    | ✅ Pass | Retry sent a new request and recovered correctly |
| Partial Response Then Failure          | ✅ Pass | Interrupted answer was clearly marked as incomplete |
| Long Conversation + Timeout            | ✅ Pass | Earlier messages remained intact |
| Multiple Tabs During Timeout           | ✅ Pass | Timeout isolated to one tab; others continued normally |
| UI Responsiveness During Slow States   | ✅ Pass | Scroll/cancel remained usable; no page freeze |
| User Guidance and Messaging            | ✅ Pass | Friendly, understandable recovery guidance |

**Overall Result**: P-05 Timeout Handling passed.  
**Bugs**: No timeout-handling or recovery defects observed.
---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: User sees no feedback while system is stuck (appears frozen)  
🔴 CRITICAL: Raw server errors or technical stack traces shown to user  
🟡 Risk: After timeout, user cannot easily retry or continue conversation  
🟢 Desirable: Clear, friendly timeout messages with simple recovery options

---

## ✅ Expected Behavior

✅ **Slow responses** show clear loading feedback until completion.  
✅ **Near-timeout / timeout cases** display a friendly timeout or retry message.  
✅ **No silent hangs** — the user is never left staring at an unchanged UI.  
✅ **Partial responses** are clearly marked as interrupted, not successful.  
✅ **Conversation history stays intact** after a timeout or network failure.  
✅ **Other tabs/sessions remain unaffected** by a timeout in one tab.  
✅ **Retry/continue flow** works cleanly without duplicate or corrupted messages.  
✅ **Messages are understandable** and do not expose technical internals.

---

## 📝 Test Execution Notes

- **Slow success**: Repeated prompts until load increased → slower but completed normally.
- **Near timeout**: Heavy multi-paragraph prompt → timeout feedback appeared correctly.
- **No response**: Simulated outage / network drop → clear error shown, no endless spinner.
- **Retry**: Re-sent prompt after timeout → request succeeded, no broken state.
- **Partial failure**: Tokens appeared, connection dropped → response flagged as interrupted.
- **Long conversation**: Timeout during 20+ turn thread → earlier context preserved.
- **Multiple tabs**: Timeout in one tab → other tabs kept working, no global freeze.
- **UI during slow state**: Scroll/cancel remained available; browser stayed responsive.
- **Messaging**: Error text was polite, simple, and suggested retry/check internet.
- No raw stack traces, no frozen loaders, and no corruption of chat history observed.
