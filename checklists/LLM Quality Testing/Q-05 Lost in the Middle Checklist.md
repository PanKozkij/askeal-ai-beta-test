# Q-05 Lost in the Middle Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ⏳ Not Executed<br>
**Tester**: Oleh Yushchenko<br>
**Date**: April 2026<br>
**Browser**: Chrome 130+

---

## ✅ Lost in the Middle Scenarios

### 1. Position Test
Context order:<br>
1. "Oleh lives in Alicante"<br>
2. "Weather is sunny"<br>
3. "RESTAURANT RECOMMENDATION NEEDED"<br>
4. "Spain has nice beaches"<br>

- [ ] Bot prioritizes the middle info (restaurant)<br>

### 2. Multiple Middle Items
1. Detail A<br>
2. Detail B<br>
3. IMPORTANT: Oleh needs restaurant<br>
4. Detail D<br>
5. Detail E<br>

- [ ] Bot remembers the middle priority<br>

### 3. Long Context Middle
- [ ] 15-message context → middle message remembered<br>
- [ ] Critical info in position 8/15 → used correctly<br>

---

## 📊 Execution Summary

| Scenario | Status | Notes |
|----------|--------|-------|
| Position Test | ⏳ | |
| Multiple Middle | ⏳ | |
| Long Context | ⏳ | |

**Total Checks**: 9+<br>
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 Ignores middle context<br>
🔴 Only uses first/last info<br>
🟡 Position bias<br>

**Expected Behavior**:<br>
✅ Uses ALL context positions<br>
✅ Middle info prioritized correctly<br>
✅ No position preference<br>

**Test Execution Notes**:<br>
1. Put CRITICAL info in the middle<br>
2. Test positions 3/7, 5/10, 8/15<br>
3. Verify model does not ignore middle context<br>
