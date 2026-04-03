# F-02 File Upload Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: PanKozkij  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ File Upload Scenarios

### 1. Valid File Upload (Positive)
- [ ] **Small image** (<1MB): PNG/JPG, 100x100px
- [ ] **Medium document** (1-5MB): PDF, DOCX
- [ ] **Large file** (~10MB): ZIP archive
- [ ] File uploads **successfully** (progress bar completes)
- [ ] **Preview appears** in chat interface
- [ ] File content **processed by LLM** (mentioned in response)

### 2. Supported Formats
- [ ] **Images**: PNG, JPG, GIF, WebP
- [ ] **Documents**: PDF, DOCX, TXT
- [ ] **Archives**: ZIP (if supported)
- [ ] **Code files**: .py, .js, .json (if supported)
- [ ] **Error for unsupported**: CSV, EXE → clear format error

### 3. File Size Limits
- [ ] **Max size warning** appears before upload
- [ ] **Small file** (<1MB) → ✅ Success
- [ ] **Medium file** (5MB) → ✅ Success  
- [ ] **Large file** (50MB+) → ❌ Blocked with clear message
- [ ] **Exact limit** (e.g. 25MB) → ✅ OR ❌ with warning

### 4. Invalid Files (Negative)
- [ ] **Wrong extension**: `test.txt.exe` → blocked
- [ ] **Empty file** (0 bytes) → validation error
- [ ] **Corrupted file** (broken PDF) → error handling
- [ ] **Malicious names**: `script.js`, `delete.bat` → blocked
- [ ] Clear **error messages** for each case

### 5. Drag & Drop
- [ ] **Drag file over** → visual feedback (highlight)
- [ ] **Drop file** → upload starts immediately
- [ ] **Multiple files** → single OR batch upload
- [ ] **Drag outside** → cancel (upload stops)

### 6. Error Recovery
- [ ] **Cancel during upload** → stops cleanly
- [ ] **Network disconnect** → resume OR clear error
- [ ] **Server error 500** → retry option OR error message
- [ ] **Upload after error** → works normally

### 7. Security Scenarios
- [ ] **Hidden instructions** in PDF → LLM processes safely
- [ ] **Script tags** in HTML file → sanitized
- [ ] **Very large text file** → processed OR truncated safely
- [ ] **Unicode filenames** → handles correctly

---

## 📊 Execution Summary

| Scenario | Status | Notes | Time |
|----------|--------|-------|------|
| Valid Upload | ⏳ | | |
| Formats | ⏳ | | |
| Size Limits | ⏳ | | |
| Invalid Files | ⏳ | | |
| Drag & Drop | ⏳ | | |
| Error Recovery | ⏳ | | |
| Security | ⏳ | | |

**Total Tests**: 7 scenarios, 35+ checks  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Notes
🔴 CRITICAL: File upload vulnerabilities (XSS, RCE)
🔴 CRITICAL: Large file DoS (memory exhaustion)
🟡 File type confusion (double extensions)
🟢 Filename sanitization (path traversal)

text

**Expected Behaviors**:
✅ Supported: PNG/JPG/PDF/DOCX/TXT (<25MB)
❌ Blocked: EXE/BAT/JS/HTML/SCR (>25MB)

text

**Environment Notes**:
Closed beta - no screenshots
Test files prepared locally
Chrome DevTools Network tab monitoring
Manual upload testing only
