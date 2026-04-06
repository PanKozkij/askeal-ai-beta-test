# F-11 Session Management Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Session Management Scenarios

### 1. Session Persistence
- [ ] Conversation remains after page refresh
- [ ] Recent howls remain after refresh
- [ ] Day/Night mode remains after refresh
- [ ] File upload state handled correctly

### 2. Idle Session
- [ ] User leaves tab idle for 5 minutes
- [ ] User leaves tab idle for 30 minutes
- [ ] Session remains active or clear reset behavior is shown
- [ ] No unexpected data loss

### 3. New Session / Restart
- [ ] New conversation starts cleanly
- [ ] Old session data does not leak into new howl
- [ ] Refresh after new session behaves correctly
- [ ] Browser reopen preserves or resets as designed

### 4. Multiple Tabs
- [ ] Same session opened in 2 tabs
- [ ] Changes in one tab visible in another tab
- [ ] No conflict between tabs
- [ ] No duplicated or corrupted conversation state

### 5. Logout / Reset Behavior
- [ ] If logout exists, session clears correctly
- [ ] If reset exists, all chat history is removed
- [ ] Cookies/localStorage cleared when expected
- [ ] User can start again from empty state

### 6. Session Error Handling
- [ ] Session expires gracefully
- [ ] User gets a clear message if session is invalid
- [ ] No crash on invalid session data
- [ ] Recovery flow works

---

## 📊 Execution Summary

| Scenario | Status | Notes |
|----------|--------|-------|
| Session Persistence | ⏳ | |
| Idle Session | ⏳ | |
| New Session | ⏳ | |
| Multiple Tabs | ⏳ | |
| Logout / Reset | ⏳ | |
| Error Handling | ⏳ | |

**Total Checks**: 24+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 Session data loss <br>
🔴 Cross-tab sync issues <br>
🔴 Unexpected logout <br>
🔴 Conversation leak between users <br>
🟡 Broken restoration after refresh <br>


**Expected Behavior**:
✅ Session persists when expected <br>
✅ Refresh does not break state <br>
✅ Multiple tabs do not conflict <br>
✅ No data leaks between sessions <br>
✅ Recovery after invalid session works <br>


**Test Execution Notes**:
- Test refresh after active conversation

- Test idle behavior for 5 and 30 minutes

- Open same session in two tabs

- Verify no state corruption after switching tabs

- Check behavior after logout or reset
