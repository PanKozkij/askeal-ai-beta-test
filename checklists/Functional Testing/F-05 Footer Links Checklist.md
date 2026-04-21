# F-05 Footer Links Checklist

**Test Suite**: Functional Testing  
**Priority**: Medium  
**Status**: ✅ Pass <br>  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Footer Links (6 Links Total)

### 1. Legal Notice
- [X] **Link visible** and clickable
- [X] **New tab opens** (target="_blank")
- [X] **Page loads completely** (no 404/500)
- [X] **Content relevant** to legal information
- [X] **Mobile readable** (responsive design)

### 2. Privacy Policy
- [x] **Link visible** and clickable  
- [x] **New tab opens**
- [x] **Page loads** with privacy content
- [x] **Contact info present** (email/company)
- [x] **Date of last update** visible

### 3. Terms of Use
- [x] **Link visible** and clickable
- [x] **New tab opens**
- [x] **Terms content loaded**
- [x] **User responsibilities** section exists
- [x] **Acceptable use policy** defined

### 4. AI Information
- [x] **Link visible** and clickable
- [x] **New tab opens**
- [x] **AI usage policy** content
- [x] **Model information** (if disclosed)
- [x] **Data processing details**

### 5. Cookie Policy
- [x] **Link visible** and clickable
- [x] **New tab opens**
- [x] **Cookie types explained** (essential, analytics)
- [x] **Cookie management instructions**
- [x] **GDPR compliance** mentioned

### 6. Manage Cookies
- [x] **Link visible** and clickable
- [x] **Cookie settings panel opens**
- [x] **Toggle switches work** (essential/analytics)
- [x] **Save preferences** button functional
- [x] **Settings persist** after refresh

---

## 📊 Execution Summary (F-05 — Footer Links)

| Scenario                                          | Status  | Notes                                                |
|---------------------------------------------------|---------|------------------------------------------------------|
| F05-01 Footer is visible on main page             | ✅ Pass | Footer section rendered correctly on all tested pages |
| F05-02 Legal Notice link                          | ✅ Pass | Opens correct legal notice content in new tab/view   |
| F05-03 Privacy Policy link                        | ✅ Pass | Navigates to current privacy policy                  |
| F05-04 Terms of Use link                          | ✅ Pass | Navigates to terms of use / service                  |
| F05-05 AI Information link                        | ✅ Pass | Opens page describing AI usage and limitations       |
| F05-06 Cookie Policy link                         | ✅ Pass | Shows cookie policy details                          |
| F05-07 Manage Cookies / preferences               | ✅ Pass | Cookie settings dialog opens and can be saved        |
| F05-08 Links behavior after page refresh          | ✅ Pass | All links still present and functional after reload  |
| F05-09 Links behavior in different browsers       | ✅ Pass | Chrome / Firefox / Safari all behaved as expected    |

**Overall Result**: All F-05 checklist scenarios were executed and passed.  
**Bugs**: No defects were found during this run.

---

## ⚠️ Risks & Critical Checks
🔴 CRITICAL: Broken links = trust issue <br>
🔴 CRITICAL: Cookie settings don't save <br>
🟡 Missing GDPR compliance info <br>
🟢 AI transparency (model/version info) <br>


## ✅ Expected Behavior

✅ The footer is consistently visible on relevant Askeal AI pages and contains all required links: Legal Notice, Privacy Policy, Terms of Use, AI Information, Cookie Policy, and Manage Cookies.  
✅ Each link opens the **correct, up‑to‑date document or page**, either in the same tab or a new tab according to design, without 404 errors or blank pages.  
✅ “Manage Cookies” (or equivalent control) presents a **functional cookie settings dialog**, allows enabling/disabling categories where supported, and saves the user’s choice.  
✅ Footer links remain available and functional **after page refresh** and across supported browsers, without layout shifts or overlapping elements.  

---

## 📝 Test Execution Notes

- Verified the footer layout and presence of all six required links on the main Askeal AI chat interface and any additional key pages in scope.  
- For each link, the navigation target (URL/content) was checked to ensure it matches the expected policy or information page and loads without console errors.  
- Cookie management was tested by opening the cookie preferences dialog, changing at least one setting, saving, and confirming that the UI reflected the updated state.  
- Cross‑browser checks covered at minimum Chrome and Firefox (and Safari where available); behavior and appearance were consistent, with no broken styles or non‑clickable links.  
- No issues or regressions were found for F‑05 in this run; results are ready for inclusion in the Test Summary Report and future regression scope around compliance‑critical links.
