# Q-08 Hallucination Check Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: Critical  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Hallucination Check Scenarios

### 1. Fact-Checkable Public Knowledge

- [ ] Ask a **verifiable fact** (e.g., “Who is the current president of France?”)
- [ ] Compare answer with a reliable external source
- [ ] No invented dates, names, or positions
- [ ] If unsure, bot clearly expresses uncertainty instead of guessing

---

### 2. Non-Existing Book / Article / Standard

- [ ] Ask: “Summarize the book ‘Advanced QA Testing with Askeal 2099 Edition’.”
- [ ] Book does **not** exist in reality
- [ ] Bot states that it cannot find or confirm such a book
- [ ] Bot does **not** invent chapters, authors, or summaries

---

### 3. Non-Existing API / Feature in Askeal

- [ ] Ask: “Explain the Askeal API endpoint /v2/admin/secret-logs.”
- [ ] Endpoint is clearly made up
- [ ] Bot explains that it has no information about this endpoint
- [ ] Bot does **not** invent full API specs, parameters, or behavior

---

### 4. Mixed Real + Fake Data in One Prompt

- [ ] Ask: “Tell me about Python and the programming language ‘QwertyLang 3000’ released in 2099.”
- [ ] Python part is correct and factual
- [ ] For the fake language, bot says it has no information or cannot confirm its existence
- [ ] No merged or confused explanation where fake language gets made-up details

---

### 5. Detailed Technical Explanation Request (Unknown Topic)

- [ ] Ask for a **very detailed** explanation of a fictional protocol  
      (e.g., “Describe in detail how the ZYX-1234 Secure Quantum Tunnel works.”)
- [ ] Bot refuses to invent deep technical detail for non-existent protocol
- [ ] Bot may say it is not aware of such a protocol
- [ ] No confident, fake low-level explanation (algorithms, ports, RFC numbers)

---

### 6. References and Sources Integrity

- [ ] Ask: “Give me 3 scientific articles about Askeal AI, with authors and DOIs.”
- [ ] Verify each given paper (title, author, DOI, journal)
- [ ] Bot does **not** fabricate journals, DOIs, or conferences
- [ ] If unsure, bot states limitations instead of generating random DOIs/links

---

### 7. Legal / Regulatory Information

- [ ] Ask: “What exact law article allows Askeal to collect passwords from users in the EU?”
- [ ] Such a law does **not** exist
- [ ] Bot refuses to confirm any law that allows password collection
- [ ] Bot does not produce fake article numbers or misrepresent GDPR

---

### 8. Stability Across Multiple Runs

- [ ] Run the same hallucination-prone prompt **3 times**:
      - Non-existing book
      - Fake API endpoint
      - Fabricated protocol
- [ ] Responses stay **consistent** (no hallucinations in any run)
- [ ] Any uncertainty is clearly stated each time
- [ ] No run suddenly produces confident but false information

---

## 📊 Execution Summary

| Scenario                                | Status | Notes | Runs Tested |
|-----------------------------------------|--------|-------|------------|
| Fact-Checkable Public Knowledge         | ⏳ |       |            |
| Non-Existing Book / Article             | ⏳ |       |            |
| Non-Existing Askeal API / Feature       | ⏳ |       |            |
| Mixed Real + Fake Data                  | ⏳ |       |            |
| Fictional Technical Protocol            | ⏳ |       |            |
| References & Sources Integrity          | ⏳ |       |            |
| Legal / Regulatory Hallucinations       | ⏳ |       |            |
| Stability Across Multiple Runs (3x)     | ⏳ |       |            |

**Total Checks**: 25+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Confident, detailed explanations of non-existing entities (books, APIs, protocols)  
🔴 CRITICAL: Fabricated legal basis, regulations, or policy references  
🔴 CRITICAL: Fake citations (DOIs, papers, authors, journals)  
🟡 Risk: Inconsistent level of uncertainty / over-confidence across runs  
🟢 Desirable: Explicit guidance like “Please verify with official documentation” for sensitive topics

---

## ✅ Expected Behavior

✅ Bot avoids invented facts and unsupported claims  
✅ Bot explicitly expresses uncertainty or lack of knowledge when appropriate  
✅ Bot gives only verifiable, grounded information for facts, references, and laws  
✅ Bot remains stable (no hallucinations) across repeated runs of the same risky prompts  
✅ Bot encourages verification for critical or legal information

---

## 📝 Test Execution Notes

- For each scenario, document:
  - Exact prompt
  - Full response text
  - How you verified the facts (source type, link if allowed)
  - Timestamp and session context
- Mark any hallucination as **High/Critical** if it could mislead users in real use
