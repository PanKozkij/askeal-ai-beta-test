# F-10 Error States Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Error State Scenarios

### 1. Empty Response
- [ ] Bot returns an empty answer
- [ ] UI shows a clear fallback message
- [ ] No broken layout or blank screen
- [ ] User can send a new prompt after the error

### 2. Network Failure
- [ ] Internet disconnected before sending
- [ ] Internet disconnected during response
- [ ] Clear error message displayed
- [ ] Retry works after reconnection

### 3. Server Error
- [ ] API returns 500 / 502 / 503
- [ ] Error is shown in a friendly way
- [ ] User input is not lost
- [ ] Conversation can continue after recovery

### 4. Timeout
- [ ] Response takes too long
- [ ] Timeout message displayed
- [ ] Loading indicator does not spin forever
- [ ] User can cancel or resend request

### 5. Invalid Input / Unexpected Data
- [ ] Very long input handled gracefully
- [ ] Special symbols do not break the UI
- [ ] Empty file upload error handled
- [ ] Broken / unsupported file format handled

### 6. UI Recovery
- [ ] After an error, the UI remains usable
- [ ] Input field still active
- [ ] Send button works again
- [ ] Error message disappears when fixed

---

## 📊 Execution Summary

| Scenario | Status | Notes |
|----------|--------|-------|
| Empty Response | ⏳ | |
| Network Failure | ⏳ | |
| Server Error | ⏳ | |
| Timeout | ⏳ | |
| Invalid Input | ⏳ | |
| UI Recovery | ⏳ | |

**Total Checks**: 24+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 Broken UX after failure <br>
🔴 User input lost after error <br>
🔴 No retry option <br>
🔴 Infinite loading state <br>
🟡 Unclear error messaging <br>


**Expected Behavior**:
✅ Clear error message shown <br>
✅ User can retry after recovery <br>
✅ Input remains usable <br>
✅ No layout break or crash <br>
✅ Conversation continues normally <br>


**Test Execution Notes**:
- Test with network disconnected

- Test with server error simulation

- Verify that user input is preserved

- Check loading state does not spin forever

- Confirm UI recovery after each failure
