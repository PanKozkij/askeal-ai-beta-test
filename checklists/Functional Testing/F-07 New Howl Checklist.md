# F-07 New Howl Checklist

**Test Suite**: Functional Testing  
**Priority**: High  
**Status**: ✅ Pass <br> 
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ New Howl Creation Flow

### 1. Basic Creation
- [x] **"New Howl" button** visible and clickable
- [x] **Click** → starts **new conversation**
- [x] **Input field cleared** for new message
- [x] **Recent howls list** updates with new entry
- [x] **New howl appears at top** of recent list

### 2. Post-Creation State
- [x] **Conversation history empty** (clean slate)
- [x] **Input field focused** and ready
- [x] **Send button enabled**
- [x] **"Try asking about" suggestions** reappear
- [x] **Scroll position** at top

### 3. Naming & Preview
- [x] **Automatic preview** from first message
- [x] **Preview updates** when first message sent
- [x] **Preview truncation** (long text → ...)
- [x] **Preview includes timestamp**
- [x] **Preview shows user name** (if available)

### 4. Multiple New Howls
- [x] **Create howl 1** → appears in recent list
- [x] **Create howl 2** → howl 1 moves down
- [x] **Chronological order** maintained
- [x] **All howls clickable** and load correctly
- [x] **10+ howls** → pagination OR scroll works

### 5. Error Recovery
- [x] **Create during network error** → handles gracefully
- [x] **Refresh during creation** → state preserved
- [x] **Browser crash** → new howl still accessible
- [x] **Multiple tabs** → syncs across tabs

### 6. Visual & UX
- [x] **Button hover effect**
- [x] **Loading state** during creation (if any)
- [x] **Mobile button** accessible and responsive
- [x] **Keyboard shortcut** (if exists)
- [x] **Day/Night mode** button styling correct

### 7. Integration Tests
- [x] **New howl after file upload** → works
- [x] **New howl after mode toggle** → works
- [x] **New howl from suggestion** → works
- [x] **New howl cross-browser** → consistent

---

## 📊 Execution Summary (F-07 — New Howl Creation)

| Scenario                                         | Status  | Notes                                                   |
|--------------------------------------------------|---------|---------------------------------------------------------|
| F07-01 New Howl button is visible and enabled    | ✅ Pass | Button/icon rendered correctly on main page            |
| F07-02 Open New Howl from existing conversation  | ✅ Pass | Starts a clean, empty conversation                     |
| F07-03 Required fields validation                | ✅ Pass | Empty send blocked; user sees clear validation message |
| F07-04 New Howl with short prompt                | ✅ Pass | Conversation created; first message saved correctly    |
| F07-05 New Howl with long prompt                 | ✅ Pass | Long text accepted; no truncation or UI break          |
| F07-06 New Howl appears in Recent Howls          | ✅ Pass | Newly created howl visible in F‑06 list                |
| F07-07 New Howl after page refresh               | ✅ Pass | Conversation persisted and restored after refresh      |
| F07-08 Cross-browser New Howl behavior           | ✅ Pass | Chrome / second browser behaved consistently           |

**Overall Result**: All F-07 checklist scenarios were executed and passed.  
**Bugs**: No defects were found during this run.

---

## ⚠️ Risks & Critical Checks
🔴 CRITICAL: New howl doesn't appear in recent list <br>
🔴 CRITICAL: Wrong howl loads on click <br>
🟡 Preview doesn't update with first message <br>
🟢 Pagination for 10+ howls <br>

---

## ✅ Expected Behavior

✅ The **New Howl** control (button/icon) is clearly visible and enabled whenever the user is allowed to start a new conversation.  
✅ Triggering New Howl from any state (main page or an existing chat) opens a **fresh, empty** conversation without leaking previous context into the new thread.  
✅ Required input validation is enforced: the user cannot send a completely empty howl, and receives a clear, user‑friendly message when required content is missing.  
✅ Both short and long prompts are accepted according to field limits and are **saved correctly** as the first message of the new howl, with no truncation or duplication.  
✅ Newly created howls are reflected in the **Recent Howls** section (F‑06), and remain available after page refresh and across supported browsers.

---

## 📝 Test Execution Notes

- Verified New Howl availability in the main UI and inside an active conversation, confirming that it always starts a clean session instead of reusing the old one.  
- Tested validation by attempting to send an empty howl and minimal content; the application prevented invalid sends and displayed appropriate messages.  
- Used both short and long prompts to check that message creation, display, and scrolling worked as expected without layout issues.  
- Confirmed integration with F‑06: each newly created howl appeared correctly in the Recent Howls list and opened the proper conversation when clicked.  
- Performed at least one cross‑browser check (Chrome plus another browser) to ensure the New Howl behavior and layout were consistent.  
- No issues were found for F‑07 in this run; this flow can be marked as **passed** in the Test Summary Report and included in future regression coverage.
