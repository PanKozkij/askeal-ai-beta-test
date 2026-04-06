# P-06 Large Input Handling Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+  

---

## ✅ Large Text & File Input Scenarios

> Goal: Verify that Askeal behaves correctly when users send very large text prompts or upload large files.

### 1. Large Text Prompt Near Limit

- [ ] Paste a very long text prompt (e.g., several pages of content)
- [ ] System accepts input without UI breaking
- [ ] Bot either:
  - Responds with a meaningful answer, **or**
  - Shows a clear message that text is too long
- [ ] No raw errors or corrupted characters in the response

---

### 2. Text Prompt Exceeding Limit

- [ ] Attempt to send an input clearly larger than expected limits
- [ ] UI prevents sending or returns a friendly error message
- [ ] Error message explains the limit in simple terms (characters/pages)
- [ ] No crash, no invisible dropped messages

---

### 3. Large File Upload — Within Allowed Size

- [ ] Upload a file close to the documented/observed size limit (but still valid)
- [ ] Upload completes successfully (no hang, no partial state)
- [ ] Bot can use the file (e.g., answer a question about its content)
- [ ] Performance impact is acceptable (no huge delays or freezes)

---

### 4. File Too Large — Above Limit

- [ ] Try to upload a file larger than allowed
- [ ] Application rejects the file with a clear, user-friendly message
- [ ] No infinite spinner or silent failure
- [ ] No partial or corrupt file stored

---

### 5. Multiple Large Inputs in Sequence

- [ ] Send several large text prompts in a row (or upload multiple large-but-valid files)
- [ ] System remains responsive across all operations
- [ ] No progressive slowdown that makes the UI unusable
- [ ] No visible memory leaks (browser stays stable)

---

### 6. Large Input Combined With RAG / Document QA (If Available)

- [ ] Upload a long document and ask complex questions about it
- [ ] Bot responds at acceptable speed
- [ ] No “out of memory” or internal error messages
- [ ] Answers relate accurately to document content (no obvious truncation issues)

---

### 7. Large Input + Long Conversation

- [ ] In a conversation with 10+ turns, send a very large text prompt
- [ ] Bot still considers earlier context plus the new large input
- [ ] No previous messages disappear from the UI
- [ ] No severe degradation in subsequent responses

---

### 8. Large Input on Slower Network

- [ ] With network throttling (e.g., “Slow 3G”), send a large text prompt and/or upload a large file
- [ ] Progress/feedback is visible (upload progress, spinner, etc.)
- [ ] If network fails during upload, user gets a clear error
- [ ] No stuck “uploading…” state forever

---

### 9. Error Handling & User Guidance

- [ ] For all large-input failures (too big, network lost, timeout):
  - Error messages are clear and non-technical
  - User is told what they can do (reduce size, try again, check connection)
- [ ] No exposure of internal paths, stack traces, or service names
- [ ] Tone is consistent with product style

---

## 📊 Execution Summary

| Scenario                                  | Status | Notes | Runs Tested |
|-------------------------------------------|--------|-------|------------|
| Large Text Prompt Near Limit              | ⏳ |       |            |
| Text Prompt Exceeding Limit               | ⏳ |       |            |
| Large File Upload — Within Limit          | ⏳ |       |            |
| File Too Large — Above Limit              | ⏳ |       |            |
| Multiple Large Inputs in Sequence         | ⏳ |       |            |
| Large Input + RAG / Document QA           | ⏳ |       |            |
| Large Input + Long Conversation           | ⏳ |       |            |
| Large Input on Slower Network             | ⏳ |       |            |
| Error Handling & User Guidance            | ⏳ |       |            |

**Total Checks**: 25+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Large inputs cause crashes, unresponsive UI, or browser “page unresponsive”  
🔴 CRITICAL: File or text appears to upload but is silently ignored with no feedback  
🟡 Risk: Very strict limits without clear explanation → frustrated users  
🟢 Desirable: Predictable limits, clear errors, and stable behavior even with big inputs

---

## ✅ Expected Behavior

✅ Large but valid inputs are processed or rejected with clear messaging  
✅ System never silently fails or corrupts chat history due to input size  
✅ Performance degrades gracefully (slower but still usable), not catastrophically  
✅ Users understand how to adjust input size when they hit limits

---

## 📝 Test Execution Notes

- For each test, save:
  - The approximate size and type of input (text length, file type + size)
  - Observed behavior (success, error message, performance impact)
  - Mapping of any failures to performance and robustness requirements (large input handling) in your bug reports
