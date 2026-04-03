# F-05 Footer Links Checklist

**Test Suite**: Functional Testing  
**Priority**: Medium  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Footer Links (6 Links Total)

### 1. Legal Notice
- [ ] **Link visible** and clickable
- [ ] **New tab opens** (target="_blank")
- [ ] **Page loads completely** (no 404/500)
- [ ] **Content relevant** to legal information
- [ ] **Mobile readable** (responsive design)

### 2. Privacy Policy
- [ ] **Link visible** and clickable  
- [ ] **New tab opens**
- [ ] **Page loads** with privacy content
- [ ] **Contact info present** (email/company)
- [ ] **Date of last update** visible

### 3. Terms of Use
- [ ] **Link visible** and clickable
- [ ] **New tab opens**
- [ ] **Terms content loaded**
- [ ] **User responsibilities** section exists
- [ ] **Acceptable use policy** defined

### 4. AI Information
- [ ] **Link visible** and clickable
- [ ] **New tab opens**
- [ ] **AI usage policy** content
- [ ] **Model information** (if disclosed)
- [ ] **Data processing details**

### 5. Cookie Policy
- [ ] **Link visible** and clickable
- [ ] **New tab opens**
- [ ] **Cookie types explained** (essential, analytics)
- [ ] **Cookie management instructions**
- [ ] **GDPR compliance** mentioned

### 6. Manage Cookies
- [ ] **Link visible** and clickable
- [ ] **Cookie settings panel opens**
- [ ] **Toggle switches work** (essential/analytics)
- [ ] **Save preferences** button functional
- [ ] **Settings persist** after refresh

---

## 📊 Execution Summary

| Link | Status | HTTP Code | Notes |
|------|--------|-----------|-------|
| Legal Notice | ⏳ | | |
| Privacy Policy | ⏳ | | |
| Terms of Use | ⏳ | | |
| AI Information | ⏳ | | |
| Cookie Policy | ⏳ | | |
| Manage Cookies | ⏳ | | |

**Total Tests**: 6 links, 30+ checks  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 CRITICAL: Broken links = trust issue <br>
🔴 CRITICAL: Cookie settings don't save <br>
🟡 Missing GDPR compliance info <br>
🟢 AI transparency (model/version info) <br>


**Expected Behavior**:
✅ All 6 links → New tab + HTTP 200 <br>
✅ Cookie settings → Persist after F5 <br>
✅ Mobile responsive footer <br>
✅ Legal pages have update dates <br>


**Test Execution Notes**:
- Check ALL links open in NEW TAB (target="_blank")

- Verify "Manage Cookies" actually changes cookie behavior

- Test footer responsiveness (DevTools mobile view)

- Check for missing/404 legal pages

- Verify content relevance (not placeholder lorem ipsum)


**Cross-Browser Matrix**:
☐ Chrome ✅ Expected <br>
☐ Firefox ✅ Expected <br>
☐ Safari ✅ Expected <br>
☐ Edge ✅ Expected <br>
