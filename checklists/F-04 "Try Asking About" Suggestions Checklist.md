# F-04 "Try Asking About" Suggestions Checklist

**Test Suite**: Functional Testing  
**Priority**: Medium  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Suggestion Functionality Scenarios

### 1. Basic Functionality
- [ ] **Suggestions visible** on empty chat screen
- [ ] **3-6 suggestion buttons** displayed
- [ ] **Click suggestion** → text appears in input field
- [ ] **Input field populated** with suggestion text
- [ ] **Send button enabled** after suggestion selected

### 2. Suggestion Interaction
- [ ] **Click suggestion** → **NOT automatically sent**
- [ ] **Suggestion text editable** (can add/modify)
- [ ] **Press Enter** after suggestion → sends message
- [ ] **Click Send** after suggestion → sends message
- [ ] **Clear input** after suggestion → suggestions reappear

### 3. Multiple Suggestions
- [ ] **Click suggestion 1** → input filled
- [ ] **Clear input** → all suggestions visible again
- [ ] **Click suggestion 2** → different text appears
- [ ] **Suggestions remain clickable** after first use
- [ ] **No duplicate suggestions** appear

### 4. Visual & UX Behavior
- [ ] **Hover effect** on suggestion buttons
- [ ] **Active state** when clicked
- [ ] **Responsive layout** (mobile/desktop)
- [ ] **Suggestions hidden** after first real message
- [ ] **Suggestions reappear** on refresh (empty state)

### 5. Content Quality
- [ ] **Relevant suggestions** for chatbot purpose
- [ ] **No broken/missing text** in suggestions
- [ ] **Proper grammar/spelling** in all suggestions
- [ ] **Multilingual support** if applicable (UA/EN/ES)
- [ ] **Character length appropriate** (not too long/short)

### 6. Edge Cases
- [ ] **Very long suggestion** → input field scrolls OR truncates
- [ ] **Suggestion with special chars** → renders correctly
- [ ] **Copy-paste suggestion** → works normally
- [ ] **Fast click multiple suggestions** → last one selected
- [ ] **Tab navigation** between suggestions (if keyboard nav)

### 7. Post-Suggestion Behavior
- [ ] **After sending suggestion** → normal chat flow
- [ ] **LLM responds appropriately** to suggestion prompts
- [ ] **Conversation context maintained** after suggestion
- [ ] **Refresh after suggestion** → suggestions reappear

---

## 📊 Execution Summary

| Scenario | Status | Notes | Failures |
|----------|--------|-------|----------|
| Basic Functionality | ⏳ | | |
| Interaction | ⏳ | | |
| Multiple Suggestions | ⏳ | | |
| Visual/UX | ⏳ | | |
| Content Quality | ⏳ | | |
| Edge Cases | ⏳ | | |
| Post-Suggestion | ⏳ | | |

**Total Tests**: 7 scenarios, 32 checks  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 CRITICAL: Suggestions don't populate input field
🟡 Suggestions auto-send (bad UX)
🟡 Broken/missing suggestion text
🟢 Visual feedback missing (hard to use)

text

**Expected Behavior**:
✅ Click → Input field filled, NOT sent
✅ Editable text in input field
✅ Send button enabled
✅ Normal chat flow continues
✅ Suggestions reappear on empty state

text

**Test Execution Notes**:
Verify suggestions are RELEVANT to chatbot purpose

Test ALL suggestions individually

Check mobile responsiveness (DevTools)

Verify NO auto-send on click (common UX mistake)

Test interaction with normal typing flow
