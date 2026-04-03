# F-03 Refresh Webpage Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Refresh Behavior Scenarios

### 1. No Conversation (Empty State)
- [ ] **F5 refresh** → returns to empty chat screen
- [ ] **Browser refresh** (Ctrl+R) → same result
- [ ] **Hard refresh** (Ctrl+Shift+R) → cache cleared, empty state
- [ ] UI elements intact (input field, send button, footer)

### 2. Single Message Conversation
- [ ] **Send 1 message** → verify it appears
- [ ] **Refresh page** → **message preserved**
- [ ] Input field **empty** (ready for new message)
- [ ] Scroll position → top of conversation
- [ ] **Send 2nd message** → conversation continues correctly

### 3. Multi-Turn Conversation (3+ messages)
- [ ] **3+ message conversation** established
- [ ] **Refresh** → **full history preserved**
- [ ] **Last message** still visible (no scroll needed)
- [ ] **Input field focused** OR cursor blinking
- [ ] **Send continuation** → context maintained

### 4. Session Persistence Edge Cases
- [ ] **After 5 minutes idle** → refresh preserves
- [ ] **After 30 minutes idle** → session still active
- [ ] **Close tab → reopen** → session preserved
- [ ] **Multiple tabs** → sync works across tabs
- [ ] **Incognito mode** → new session (expected)

### 5. Post-Action Refresh
- [ ] **After file upload** → file still visible
- [ ] **After day/night mode toggle** → mode preserved
- [ ] **After "Try asking about" click** → selection preserved
- [ ] **After new howl** → appears in recent list

### 6. Error Recovery After Refresh
- [ ] **During typing** → refresh → text preserved
- [ ] **During upload** → refresh → upload cancelled cleanly
- [ ] **Server error state** → refresh → recovers to normal
- [ ] **Network disconnect** → refresh → reconnects

### 7. Cross-Browser Refresh
[] Chrome → Full session restore
[] Firefox → Full session restore
[] Safari → Full session restore
[] Edge → Full session restore

text

---

## 📊 Execution Summary

| Scenario | Status | Notes | Failures |
|----------|--------|-------|----------|
| Empty State | ⏳ | | |
| Single Message | ⏳ | | |
| Multi-Turn | ⏳ | | |
| Session Edge Cases | ⏳ | | |
| Post-Action | ⏳ | | |
| Error Recovery | ⏳ | | |
| Cross-Browser | ⏳ | | |

**Total Tests**: 7 scenarios, 28 checks  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
- 🔴 CRITICAL: Session loss = fatal UX issue
- 🔴 CRITICAL: Data loss after refresh = showstopper
- 🟡 Input field focus after restore
- 🟢 Scroll position (should go to bottom)


**Expected Behavior**:
- ✅ Refresh → FULL conversation history preserved
- ✅ Input field → empty + focused
- ✅ UI state → Day/Night mode preserved
- ✅ Ready for new message immediately
- 
**Test Execution Notes**:
- Test with REAL conversation history (not screenshots)

- Verify timing: immediate restore vs loading spinner

- Check ALL UI elements: mode toggle, footer links, recent howls

- Test hard refresh (Ctrl+Shift+R) vs soft (F5)
