# F-07 New Howl Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ New Howl Creation Flow

### 1. Basic Creation
- [ ] **"New Howl" button** visible and clickable
- [ ] **Click** → starts **new conversation**
- [ ] **Input field cleared** for new message
- [ ] **Recent howls list** updates with new entry
- [ ] **New howl appears at top** of recent list

### 2. Post-Creation State
- [ ] **Conversation history empty** (clean slate)
- [ ] **Input field focused** and ready
- [ ] **Send button enabled**
- [ ] **"Try asking about" suggestions** reappear
- [ ] **Scroll position** at top

### 3. Naming & Preview
- [ ] **Automatic preview** from first message
- [ ] **Preview updates** when first message sent
- [ ] **Preview truncation** (long text → ...)
- [ ] **Preview includes timestamp**
- [ ] **Preview shows user name** (if available)

### 4. Multiple New Howls
- [ ] **Create howl 1** → appears in recent list
- [ ] **Create howl 2** → howl 1 moves down
- [ ] **Chronological order** maintained
- [ ] **All howls clickable** and load correctly
- [ ] **10+ howls** → pagination OR scroll works

### 5. Error Recovery
- [ ] **Create during network error** → handles gracefully
- [ ] **Refresh during creation** → state preserved
- [ ] **Browser crash** → new howl still accessible
- [ ] **Multiple tabs** → syncs across tabs

### 6. Visual & UX
- [ ] **Button hover effect**
- [ ] **Loading state** during creation (if any)
- [ ] **Mobile button** accessible and responsive
- [ ] **Keyboard shortcut** (if exists)
- [ ] **Day/Night mode** button styling correct

### 7. Integration Tests
- [ ] **New howl after file upload** → works
- [ ] **New howl after mode toggle** → works
- [ ] **New howl from suggestion** → works
- [ ] **New howl cross-browser** → consistent

---

## 📊 Execution Summary

| Scenario | Status | Notes | Howls Created |
|----------|--------|-------|---------------|
| Basic Creation | ⏳ | | |
| Post-Creation | ⏳ | | |
| Naming/Preview | ⏳ | | |
| Multiple Howls | ⏳ | | |
| Error Recovery | ⏳ | | |
| Visual/UX | ⏳ | | |
| Integration | ⏳ | | |

**Total Tests**: 7 scenarios, 35 checks  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 CRITICAL: New howl doesn't appear in recent list <br>
🔴 CRITICAL: Wrong howl loads on click <br>
🟡 Preview doesn't update with first message <br>
🟢 Pagination for 10+ howls <br>

---

**Expected Behavior**:
✅ Click "New Howl" → Clean new conversation <br>
✅ First message → Auto-preview generated <br>
✅ New entry → TOP of recent list <br>
✅ All previous howls preserved <br>
✅ Mobile button accessible <br>

---

**Test Execution Notes**:
- Create 10+ howls to test pagination/scroll

- Verify EXACT restore of previous conversations

- Test rapid "New Howl" creation (×5 quickly)

- Check Day/Night mode styling

- Verify timestamps are accurate

- Test from different tabs simultaneously
