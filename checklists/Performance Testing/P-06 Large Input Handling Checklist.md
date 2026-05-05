# P-06 Large Input Handling Checklist

**Test Group**: Performance Testing  
**Priority**: High  
**Status**: ✅ Pass  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+  

---

## ✅ Large Text & File Input Scenarios

> Goal: Verify that Askeal behaves correctly when users send very large text prompts or upload large files.

### 1. Large Text Prompt Near Limit

- [x] Paste a very long text prompt (e.g., several pages of content)
- [x] System accepts input without UI breaking
- [x] Bot either:
  - Responds with a meaningful answer, **or**
  - Shows a clear message that text is too long
- [x] No raw errors or corrupted characters in the response

---

### 2. Text Prompt Exceeding Limit

- [x] Attempt to send an input clearly larger than expected limits
- [x] UI prevents sending or returns a friendly error message
- [x] Error message explains the limit in simple terms (characters/pages)
- [x] No crash, no invisible dropped messages

---

### 3. Large File Upload — Within Allowed Size

- [x] Upload a file close to the documented/observed size limit (but still valid)
- [x] Upload completes successfully (no hang, no partial state)
- [x] Bot can use the file (e.g., answer a question about its content)
- [x] Performance impact is acceptable (no huge delays or freezes)

---

### 4. File Too Large — Above Limit

- [x] Try to upload a file larger than allowed
- [x] Application rejects the file with a clear, user-friendly message
- [x] No infinite spinner or silent failure
- [x] No partial or corrupt file stored

---

### 5. Multiple Large Inputs in Sequence

- [x] Send several large text prompts in a row (or upload multiple large-but-valid files)
- [x] System remains responsive across all operations
- [x] No progressive slowdown that makes the UI unusable
- [x] No visible memory leaks (browser stays stable)

---

### 6. Large Input Combined With RAG / Document QA (If Available)

- [x] Upload a long document and ask complex questions about it
- [x] Bot responds at acceptable speed
- [x] No “out of memory” or internal error messages
- [x] Answers relate accurately to document content (no obvious truncation issues)

---

### 7. Large Input + Long Conversation

- [x] In a conversation with 10+ turns, send a very large text prompt
- [x] Bot still considers earlier context plus the new large input
- [x] No previous messages disappear from the UI
- [x] No severe degradation in subsequent responses

---

### 8. Large Input on Slower Network

- [x] With network throttling (e.g., “Slow 3G”), send a large text prompt and/or upload a large file
- [x] Progress/feedback is visible (upload progress, spinner, etc.)
- [x] If network fails during upload, user gets a clear error
- [x] No stuck “uploading…” state forever

---

### 9. Error Handling & User Guidance

- [x] For all large-input failures (too big, network lost, timeout):
  - Error messages are clear and non-technical
  - User is told what they can do (reduce size, try again, check connection)
- [x] No exposure of internal paths, stack traces, or service names
- [x] Tone is consistent with product style

---

## 📊 Execution Summary (P-06 — Large Input Handling)

| Scenario                              | Status | Notes |
|---------------------------------------|--------|-------|
| Large Text Prompt Near Limit          | ✅ Pass | Multi-page input accepted, meaningful response returned |
| Text Prompt Exceeding Limit           | ✅ Pass | Friendly limit message shown, no crash or dropped message |
| Large File Upload — Within Limit      | ✅ Pass | Upload completed, bot answered questions about content |
| File Too Large — Above Limit          | ✅ Pass | File rejected with clear user-friendly message |
| Multiple Large Inputs in Sequence     | ✅ Pass | System stayed responsive, no progressive slowdown |
| Large Input + RAG / Document QA       | ✅ Pass | Long document processed, accurate answers, no memory error |
| Large Input + Long Conversation       | ✅ Pass | Earlier context preserved, no messages disappeared |
| Large Input on Slower Network         | ✅ Pass | Progress visible, clear error on failure, no stuck state |
| Error Handling & User Guidance        | ✅ Pass | All errors clear, non-technical, with recovery guidance |

**Overall Result**: P-06 Large Input Handling passed.  
**Bugs**: No large input, file upload, or error-handling defects observed.

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Large inputs cause crashes, unresponsive UI, or browser “page unresponsive”  
🔴 CRITICAL: File or text appears to upload but is silently ignored with no feedback  
🟡 Risk: Very strict limits without clear explanation → frustrated users  
🟢 Desirable: Predictable limits, clear errors, and stable behavior even with big inputs

---
## ✅ Expected Behavior

✅ **Large valid inputs** are processed correctly or rejected with a clear limit message.  
✅ **Oversized files** are blocked immediately with a friendly, non-technical error.  
✅ **System never silently ignores** large text or file inputs without feedback.  
✅ **Chat history remains intact** after large input operations, no messages lost.  
✅ **Performance degrades gracefully** — slower but still usable, no browser freeze.  
✅ **RAG / Document QA** handles long documents at acceptable speed without memory errors.  
✅ **Slow network uploads** show visible progress and a clear error on failure.  
✅ **Error messages** explain limits in simple terms and suggest recovery steps.

---

## 📝 Test Execution Notes

- **Near limit**: Several pages pasted → accepted and answered without UI breaking.
- **Over limit**: Excessive text sent → friendly character/page limit message shown.
- **File within limit**: Valid large file uploaded → content QA worked correctly.
- **File over limit**: Oversized file attempted → rejected instantly, no silent failure.
- **Sequential inputs**: 3 large prompts in a row → browser remained stable, no leak.
- **RAG + long doc**: Uploaded long PDF/text → questions answered accurately, no truncation.
- **Large input + 10+ turns**: Large message at turn 12 → context and history preserved.
- **Slow 3G throttle**: Large upload on throttled network → progress shown, fail handled.
- **Error messages**: All limit/failure messages non-technical and consistent with product tone.
- No stack traces, internal paths, silent drops, or browser "page unresponsive" in any scenario.
