# P-05 Timeout Handling Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+  

---

## ✅ Timeout & Slow Response Scenarios

> Goal: Verify that Askeal behaves correctly when the backend is very slow or fails to respond.

### 1. Slow but Successful Response

- [ ] Send a normal prompt when the system is under noticeable load (or repeat prompts until you see a slow case)
- [ ] Response takes **significantly longer** than usual but eventually completes
- [ ] UI shows a clear loading indicator (spinner / streaming indicator) the whole time
- [ ] No raw error messages or broken layout

---

### 2. Extremely Slow Response (Near Timeout)

- [ ] Trigger a very heavy prompt (e.g., long multi-paragraph input asking for detailed analysis)
- [ ] Observe behavior if the backend is extremely slow
- [ ] If there is a timeout limit, user sees a **clear timeout message**
- [ ] User is not left staring at an unchanged UI with no feedback

---

### 3. Full Timeout — No Response From Server

- [ ] Simulate network failure or backend outage (e.g., disable network after sending prompt, or test during known outage)
- [ ] Bot does not silently hang forever
- [ ] User sees an error or “Unable to get a response, please try again” message
- [ ] No cryptic technical text (stack trace, internal error codes) is shown

---

### 4. Retry After Timeout

- [ ] After a timeout, use the UI’s retry option (if available) or re-send the same prompt
- [ ] Retry works correctly and sends a new request
- [ ] If issue is temporary, response returns normally on retry
- [ ] No duplicate partial messages or broken conversation state

---

### 5. Partial Response Then Failure

- [ ] Try to trigger a case where some tokens appear and then the connection drops
- [ ] UI clearly indicates that the answer did not finish (e.g., error badge, “response interrupted”)
- [ ] Conversation view does not show the partial answer as “successful” without warning
- [ ] User can safely retry without corrupting chat history

---

### 6. Long Conversation + Timeout

- [ ] In a 20+ turn conversation, send another prompt during a slow period
- [ ] If timeout happens, earlier messages remain intact
- [ ] No corruption of chat history or sudden loss of previous turns
- [ ] User can continue the conversation after the failure

---

### 7. Multiple Tabs During Timeout

- [ ] With 2–3 Askeal tabs open, trigger a timeout in one tab
- [ ] Other tabs continue to function normally (no global freeze)
- [ ] Error is isolated to the tab where timeout occurred
- [ ] No cross-tab error popups or state confusion

---

### 8. UI Responsiveness During Slow/Timeout States

- [ ] While a response is slow or timing out:
  - User can still scroll chat history
  - User can cancel/stop the response if a stop button is available
- [ ] Browser remains responsive (no “page unresponsive” dialogs)
- [ ] UI elements (buttons, inputs) do not get permanently disabled

---

### 9. User Guidance and Messaging

- [ ] Error/timeout messages are understandable for non-technical users
- [ ] Messages clearly suggest next steps (retry, check internet, try later)
- [ ] No references to internal service names or debug info
- [ ] Tone remains polite and consistent with product style

---

## 📊 Execution Summary

| Scenario                               | Status | Notes | Runs Tested |
|----------------------------------------|--------|-------|------------|
| Slow but Successful Response           | ⏳ |       |            |
| Extremely Slow Response (Near Timeout) | ⏳ |       |            |
| Full Timeout — No Response             | ⏳ |       |            |
| Retry After Timeout                    | ⏳ |       |            |
| Partial Response Then Failure          | ⏳ |       |            |
| Long Conversation + Timeout            | ⏳ |       |            |
| Multiple Tabs During Timeout           | ⏳ |       |            |
| UI Responsiveness During Slow States   | ⏳ |       |            |
| User Guidance and Messaging            | ⏳ |       |            |

**Total Checks**: 25+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: User sees no feedback while system is stuck (appears frozen)  
🔴 CRITICAL: Raw server errors or technical stack traces shown to user  
🟡 Risk: After timeout, user cannot easily retry or continue conversation  
🟢 Desirable: Clear, friendly timeout messages with simple recovery options

---

## ✅ Expected Behavior

✅ Slow and timeout scenarios are handled gracefully with clear feedback  
✅ Conversation history remains intact even when a response fails  
✅ Other tabs/sessions remain unaffected by a single timeout  
✅ Users can retry or continue without confusion or data loss

---

## 📝 Test Execution Notes

- For each test, save:
  - The exact prompt(s) used and context (long conversation, multiple tabs, simulated network issues, etc.)
  - Observed behavior, including error/timeout messages and UI indicators
  - Mapping of any failures to performance requirements (timeout handling / resilience) in your bug reports
