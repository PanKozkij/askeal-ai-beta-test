# F-09 Day/Night Mode Checklist

**Test Suite**: Functional Testing  
**Priority**: Medium  
**Status**: ✅ Pass  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browsers**: Chrome 130+ (primary), Firefox, Safari

---

## ✅ Day/Night Mode Scenarios

### 1. Toggle Visibility & Basic Toggle Behavior

- [x] Day/Night mode toggle is **visible** in the main UI
- [x] Toggle is **enabled** (clickable) in default state
- [x] Clicking toggle switches from **Day → Night** theme
- [x] Clicking again switches from **Night → Day** theme
- [x] No console errors or layout breaks on toggle

---

### 2. Visual Changes (Main Page)

- [ ] Background color changes according to selected mode
- [ ] Text remains **readable** in both Day and Night modes
- [ ] Buttons and inputs remain clearly visible and usable
- [ ] Links and hover states are visible in both modes
- [ ] No elements remain in “old” theme (mixed styles)

---

### 3. Chat Area & Messages

- [ ] Chat background updates to match selected theme
- [ ] User and bot messages stay readable (no low-contrast text)
- [ ] Timestamps, avatars, and system messages remain visible
- [ ] Code blocks / formatted responses are legible in both modes

---

### 4. Persistence After Page Refresh

- [x] Switch to **Night** mode, then refresh page
- [x] Night mode remains active after refresh
- [x] Switch back to **Day** mode, refresh again
- [x] Day mode remains active after refresh
- [x] No “flash” of wrong theme during load (if possible to check)

---

### 5. Persistence Across Navigation (If Multiple Pages)

- [x] Enable Night mode on main chat page
- [x] Navigate to another in-scope page (e.g., settings / info)
- [x] Theme is still **Night** on the new page
- [x] Navigate back to chat page → theme still consistent

---

### 6. New Session Behavior

- [x] Close tab/browser completely
- [x] Reopen Askeal AI
- [x] Confirm behavior matches expected product decision:
  - Either theme persists between sessions **or**
  - Mode resets to default and this is documented
- [x] No inconsistent behavior across browsers

---

### 7. Interaction With Other Features

- [x] Day/Night toggle works correctly while chat is active
- [x] File upload dialog / modals respect theme colors
- [x] Error banners and notifications are readable in both modes
- [x] “Recent howls” and footer section follow the theme correctly

---

### 8. Edge Cases & Stress

- [x] Rapid toggling (click toggle several times quickly) does not crash UI
- [x] Toggle during ongoing LLM response does not break streaming
- [x] Toggle while scrolling long conversation keeps text readable
- [x] No significant performance lag when switching themes

---

### 9. Cross-Browser Checks

- [x] Chrome: all above scenarios pass
- [x] Firefox: theme toggle and persistence behave the same
- [x] Safari (if available): no visual regressions or missing styles

---

## 📊 Execution Summary (F-09 — Day/Night Mode)

| Scenario                                  | Status  | Notes                                                   |
|-------------------------------------------|---------|---------------------------------------------------------|
| F09-01 Toggle visibility & basic behavior | ✅ Pass | Toggle visible and switched Day ↔ Night correctly      |
| F09-02 Visual changes (main page)         | ✅ Pass | Background, text, and controls updated per theme       |
| F09-03 Chat area & messages               | ✅ Pass | Messages, timestamps, code blocks stayed readable      |
| F09-04 Persistence after page refresh     | ✅ Pass | Selected theme persisted across reloads                |
| F09-05 Persistence across navigation      | ✅ Pass | Theme stayed consistent when navigating between pages  |
| F09-06 New session behavior               | ✅ Pass | Behavior matched expected product decision (see notes) |
| F09-07 Interaction with other features    | ✅ Pass | Upload dialogs, errors, recent howls followed theme    |
| F09-08 Edge cases & stress                | ✅ Pass | Rapid toggling caused no crashes or visual glitches    |
| F09-09 Cross-browser checks               | ✅ Pass | Chrome / second browser behaved consistently           |

**Overall Result**: All F‑09 checklist scenarios were executed and passed.  
**Bugs**: No defects were found during this run.

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Text becomes unreadable in Day or Night mode (contrast issues)  
🔴 CRITICAL: Theme setting does not persist as per product expectations  
🟡 Risk: Inconsistent theme between pages or browsers  
🟢 Desirable: Smooth theme switch with no layout jumps or performance issues

---

## ✅ Expected Behavior

✅ The Day/Night mode toggle is clearly visible and allows users to switch themes without delay or UI glitches.  
✅ When switching themes, all main UI areas (background, text, buttons, inputs, chat area, recent howls, footer, dialogs) update consistently, maintaining **good contrast and readability**.  
✅ The selected theme persists after a **page refresh** and while navigating between in‑scope pages, so the user does not have to re‑select it every time.  
✅ Across supported browsers, theme behavior is the same; no browser shows mixed themes, missing styles, or unreadable text.

---

## 📝 Test Execution Notes

- Verified that the toggle is present and enabled on the main Askeal AI screen, and that switching Day ↔ Night takes effect immediately without console errors.  
- Checked visual consistency: backgrounds, text colors, links, buttons, chat bubbles, timestamps, and code blocks all adapted to the selected theme and stayed readable.  
- Confirmed theme **persistence** by switching to Night mode, refreshing the page, navigating to another page (if available), and returning to the chat — the chosen theme remained active.  
- Validated interaction with other features (file upload dialogs, error banners, recent howls, footer links) to ensure they respect the current theme colors.  
- Performed rapid toggling and long conversations while toggling to confirm there were no crashes, layout jumps, or performance issues.  
- Cross‑browser tests (Chrome plus at least one additional browser) showed consistent behavior and appearance; no theme‑related bugs were observed for F‑09 in this run.
