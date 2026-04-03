# F-01 Field Validation Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Field Validation Scenarios

### 1. Empty Input
- [ ] Input field accepts empty state (no crash)
- [ ] **Send** button disabled OR shows error on click
- [ ] Clear error message: "Message cannot be empty" / similar
- [ ] Error disappears when user types

### 2. Valid Input (Positive)
- [ ] Short message (1-50 chars): `"Hello"`
- [ ] Medium message (100-500 chars)
- [ ] Long message (~4000 chars)
- [ ] Message sends successfully
- [ ] Appears correctly in chat history

### 3. Maximum Length (Boundary)
- [ ] **4096 chars** → accepted OR shows counter
- [ ] **4097+ chars** → warning OR truncation
- [ ] Long message sends OR blocked with clear message
- [ ] Character limit behavior consistent

### 4. Special Characters
- [ ] **Punctuation**: `<>@#$%^&*()_+=`
- [ ] **Emojis**: 😀🚀✅📱
- [ ] All characters render correctly in chat
- [ ] No XSS/escape issues

### 5. Edge Cases
- [ ] **Leading spaces**: `"   hello"`
- [ ] **Trailing spaces**: `"hello   "`
- [ ] **Spaces trimmed** OR preserved consistently
- [ ] **Copy-paste** (Ctrl+V) from external source
- [ ] **Paste formatted text** (bold/italic from Word)

### 6. Invalid Input Handling
- [ ] **Only spaces**: `"       "` → validation error
- [ ] **Tab characters** → handled correctly
- [ ] **Newline characters** (Ctrl+Enter) → handled
- [ ] **Very long single line** → wraps OR scrolls

---

## 📊 Execution Summary

| Scenario | Status | Notes | Screenshot |
|----------|--------|-------|------------|
| Empty Input | ⏳ | | |
| Valid Input | ⏳ | | |
| Max Length | ⏳ | | |
| Special Chars | ⏳ | | |
| Edge Cases | ⏳ | | |
| Invalid Input | ⏳ | | |

**Total Tests**: 6 scenarios, 25+ checks  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Notes

🔴 CRITICAL: XSS vulnerability from special chars
🟡 Input sanitization may break Ukrainian text
🟠 No character counter → UX issue for long prompts
🟢 Spaces trimming behavior must be consistent

**Environment Notes**:

Beta version tested
No media (closed beta policy)
Manual execution only
Chrome DevTools used for timing
---
