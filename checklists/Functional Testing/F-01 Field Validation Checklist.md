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
- [x] Input field accepts empty state (no crash)
- [x] **Send** button disabled OR shows error on click
- [x] Clear error message: "Message cannot be empty" / similar
- [x] Error disappears when user types

### 2. Valid Input (Positive)
- [x] Short message (1-50 chars): `"Hello"`
- [x] Medium message (100-500 chars)
- [x] Long message (~4000 chars)
- [x] Message sends successfully
- [x] Appears correctly in chat history

### 3. Maximum Length (Boundary)
- [x] **4096 chars** → accepted OR shows counter
- [x] **4097+ chars** → warning OR truncation
- [x] Long message sends OR blocked with clear message
- [x] Character limit behavior consistent

### 4. Special Characters
- [x] **Punctuation**: `<>@#$%^&*()_+=`
- [x] **Emojis**: 😀🚀✅📱
- [x] All characters render correctly in chat
- [x] No XSS/escape issues

### 5. Edge Cases
- [x] **Leading spaces**: `"   hello"`
- [x] **Trailing spaces**: `"hello   "`
- [x] **Spaces trimmed** OR preserved consistently
- [x] **Copy-paste** (Ctrl+V) from external source
- [x] **Paste formatted text** (bold/italic from Word)

### 6. Invalid Input Handling
- [x] **Only spaces**: `"       "` → validation error
- [x] **Tab characters** → handled correctly
- [x] **Newline characters** (Ctrl+Enter) → handled
- [x] **Very long single line** → wraps OR scrolls

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
