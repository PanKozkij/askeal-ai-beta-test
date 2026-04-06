# F-12 Browser Compatibility Checklist

**Test Suite**: Functional Testing  
**Priority**: Medium  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Browser Compatibility Scenarios

### 1. Core Browsers
- [ ] Chrome — all major flows work
- [ ] Firefox — all major flows work
- [ ] Safari — all major flows work
- [ ] Edge — all major flows work

### 2. Functional Consistency
- [ ] Input field behavior identical
- [ ] Send message works in each browser
- [ ] File upload works in each browser
- [ ] Refresh behavior consistent
- [ ] Day/Night mode works in each browser
- [ ] Recent howls display correctly

### 3. LLM Behavior Consistency
- [ ] Same prompt gives similar result in each browser
- [ ] Multi-turn conversation works in each browser
- [ ] Suggestions behave consistently
- [ ] Error messages look the same
- [ ] Loading states appear correctly

### 4. UI Rendering
- [ ] Layout does not break
- [ ] Text is readable
- [ ] Buttons are visible and clickable
- [ ] Footer links align correctly
- [ ] No horizontal scrolling on desktop

### 5. Responsive Behavior
- [ ] Desktop resolution
- [ ] Laptop resolution
- [ ] Tablet mode
- [ ] Mobile viewport
- [ ] No overlap or clipped content

### 6. Browser-Specific Issues
- [ ] Chrome-specific issues documented
- [ ] Firefox-specific issues documented
- [ ] Safari-specific issues documented
- [ ] Edge-specific issues documented
- [ ] Workarounds noted if needed

---

## 📊 Execution Summary

| Browser | Status | UI | Functional | Notes |
|---------|--------|----|------------|-------|
| Chrome | ⏳ | | | |
| Firefox | ⏳ | | | |
| Safari | ⏳ | | | |
| Edge | ⏳ | | | |

**Total Checks**: 20+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 Browser-specific layout bug <br>
🔴 File upload mismatch  <br>
🔴 Refresh/session inconsistency <br>
🟡 Safari rendering differences <br>
🟢 Missing support for older browsers <br>


**Expected Behavior**:
✅ Core features work in all target browsers <br>
✅ Layout stays stable <br>
✅ File upload behaves the same <br>
✅ Refresh preserves expected state <br>
✅ No browser-specific crashes <br>


**Test Execution Notes**:
- Test the same scenario in all browsers

- Compare UI behavior and response consistency

- Check file upload and refresh behavior

- Use responsive view for tablet/mobile checks

- Document any browser-specific issues separately
