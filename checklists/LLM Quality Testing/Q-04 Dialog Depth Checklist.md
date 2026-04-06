# Q-04 Dialog Depth Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ⏳ Not Executed<br>
**Tester**: Oleh Yushchenko<br>
**Date**: April 2026<br>
**Browser**: Chrome 130+

---

## ✅ Dialog Depth Scenarios

### 1. 5-Turn Test
- [ ] Turn 1: "My name is Oleh"<br>
- [ ] Turn 3: Bot uses "Oleh"<br>
- [ ] Turn 5: Still remembers name<br>

### 2. 10-Turn Test  
- [ ] Turn 1: "I live in Alicante, Spain"<br>
- [ ] Turn 10: Bot references Alicante<br>
- [ ] Context maintained across 10 turns<br>

### 3. Context Overload
- [ ] 20+ turns → No confusion<br>
- [ ] References early context correctly<br>
- [ ] No repetition loops<br>

---

## 📊 Execution Summary

| Scenario | Status | Notes |
|----------|--------|-------|
| 5-Turn | ⏳ | |
| 10-Turn | ⏳ | |
| Context Overload | ⏳ | |

**Total Checks**: 12+<br>
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 Context loss after 10 turns<br>
🔴 Repetition loops<br>
🟡 Name confusion<br>
🟢 Topic switching failure<br>

**Expected Behavior**:<br>
✅ Remembers context 20+ turns<br>
✅ No repetition<br>
✅ References early messages<br>
✅ Smooth topic transitions<br>

**Test Execution Notes**:<br>
1. Use your name/location<br>
2. Test exactly 5, 10, 20 turns<br>
3. Verify no degradation<br>
