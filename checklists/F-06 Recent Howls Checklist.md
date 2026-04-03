# F-06 Recent Howls Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Recent Howls Functionality

### 1. Display & Visibility
- [ ] **Section visible** on main chat screen
- [ ] **"Recent Howls" title** present
- [ ] **List populated** with previous conversations
- [ ] **Empty state** shown when no history
- [ ] **Responsive layout** (mobile/desktop)

### 2. List Population
- [ ] **New conversations appear** immediately
- [ ] **First conversation** at top (most recent)
- [ ] **Chronological order** (newest → oldest)
- [ ] **Preview text** shows first message/snippet
- [ ] **Timestamps visible** (date/time)

### 3. Navigation
- [ ] **Click howl** → **loads full conversation**
- [ ] **Conversation restored** exactly as left
- [ ] **Input field empty** after loading
- [ ] **Scroll to bottom** of loaded conversation
- [ ] **Continue conversation** works normally

### 4. List Management
- [ ] **Maximum items** shown (5-10 recent?)
- [ ] **Oldest items hidden** OR scrollable
- [ ] **List updates** when new conversations created
- [ ] **Refresh page** → list preserved
- [ ] **Multiple tabs** → sync across tabs

### 5. Visual Design
- [ ] **Hover effect** on howl items
- [ ] **Active state** when selected
- [ ] **Preview truncation** (long text → ...)
- [ ] **Consistent spacing** between items
- [ ] **Day/Night mode compatible**

### 6. Edge Cases
- [ ] **Very long preview text** → truncates properly
- [ ] **Special chars in preview** → renders correctly
- [ ] **50+ conversations** → pagination OR scroll
- [ ] **Delete recent howl** → removes from list
- [ ] **Empty preview** → shows timestamp OR "Untitled"

### 7. Cross-Browser
[] Chrome → List works + responsive
[] Firefox → List works + responsive
[] Safari → List works + responsive
[] Edge → List works + responsive

text

---

## 📊 Execution Summary

| Scenario | Status | Notes | Count |
|----------|--------|-------|-------|
| Display | ⏳ | | |
| Population | ⏳ | | |
| Navigation | ⏳ | | |
| List Management | ⏳ | | |
| Visual Design | ⏳ | | |
| Edge Cases | ⏳ | | |
| Cross-Browser | ⏳ | | |

**Total Tests**: 7 scenarios, 35 checks  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 CRITICAL: Clicking doesn't restore conversation <br>
🔴 CRITICAL: Wrong conversation loads <br>
🟡 List doesn't update with new conversations <br>
🟢 Pagination/scroll for long lists <br>


**Expected Behavior**:
✅ Click → FULL conversation restored <br>
✅ New convos → appear at TOP of list <br>
✅ Chronological order maintained <br>
✅ Refresh → list preserved <br>
✅ Mobile → properly scrollable <br>


**Test Execution Notes**:
- Create 10+ conversations for pagination test

- Verify EXACT conversation restore (not just preview)

- Test rapid switching between recent conversations

- Check Day/Night mode doesn't break list

- Verify timestamps update correctly
