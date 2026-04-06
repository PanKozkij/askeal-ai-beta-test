# Q-06 RAG Quality Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ⏳ Not Executed<br>
**Tester**: Oleh Yushchenko<br>
**Date**: April 2026<br>
**Browser**: Chrome 130+

---

## ✅ RAG Quality Scenarios

### 1. Document Retrieval
- [ ] Upload relevant document<br>
- [ ] Ask about specific paragraph → **quotes correctly**<br>
- [ ] Ask about document title → recognizes source<br>

### 2. Correct Refusal
Ask about NON-EXISTING info:<br>
- [ ] "I don't have that information"<br>
- [ ] No hallucination<br>
- [ ] No generic answer<br>

### 3. Context Integration
Document: "Company founded 2020"<br>
Prompt: "When founded?"<br>

- [ ] Uses document → "2020"<br>
- [ ] Doesn't hallucinate other years<br>

---

## 📊 Execution Summary

| Scenario | Status | Notes |
|----------|--------|-------|
| Document Retrieval | ⏳ | |
| Correct Refusal | ⏳ | |
| Context Integration | ⏳ | |

**Total Checks**: 12+<br>
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 Hallucinates document info<br>
🔴 Wrong paragraph quoted<br>
🟡 Fails to refuse unknown info<br>

**Expected Behavior**:<br>
✅ Quotes exact document text<br>
✅ Refuses unknown info<br>
✅ Prioritizes document over training data<br>

**Test Execution Notes**:<br>
1. Upload test PDF with known content<br>
2. Ask specific questions<br>
3. Verify exact quotes<br>
4. Test refusal for non-existent info<br>
