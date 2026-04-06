# Q-11 Tone and Formatting Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: Medium  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Tone & Style Scenarios

### 1. Default Tone (Product Style)

- [ ] Ask a neutral question (e.g., “How can I start testing an AI chatbot?”)
- [ ] Tone is **helpful, professional, and polite**
- [ ] No sarcasm, aggression, or rude phrases
- [ ] No overuse of emojis or casual slang (unless requested)

---

### 2. Following Tone Instructions

- [ ] Give explicit instruction: “Answer in a friendly but professional tone.”
- [ ] Bot response matches requested tone (friendly + structured)
- [ ] Then ask: “Now answer in a more formal tone.”
- [ ] Bot clearly adjusts tone, while staying respectful and consistent

---

### 3. Handling Sensitive Topics Tone

- [ ] Ask about a **sensitive or negative** topic (e.g., failure, mistakes, risks)
- [ ] Bot keeps calm, non-judgmental, and supportive tone
- [ ] No blaming language or emotional manipulation
- [ ] Clear, empathetic phrasing where appropriate

---

### 4. Multi-Part Question Structure

- [ ] Ask a question with **3–4 sub-questions** in one prompt
- [ ] Bot structures answer with **clear sections or bullets** for each part
- [ ] No huge unstructured wall of text
- [ ] Each sub-question is explicitly answered (no missing parts)

---

### 5. Markdown Formatting Quality

- [ ] Ask: “Give me a checklist for testing login functionality in markdown.”
- [ ] Bot uses correct Markdown structure:
  - Headings (`#`, `##`)
  - Bullet or numbered lists
  - Optional checkboxes `[ ]`
- [ ] No broken Markdown (e.g., missing spaces, invalid list nesting)

---

### 6. Code and Inline Formatting

- [ ] Ask to show a **code example** or command (e.g., curl, JSON, JS snippet)
- [ ] Bot wraps code in proper code blocks (```…```), not inline plain text
- [ ] Inline terms (e.g., file names, commands) use backticks `like_this`
- [ ] No formatting that breaks readability (mixed code and prose)

---

### 7. Table Formatting

- [ ] Ask: “Create a markdown table with 3 test cases for file upload testing.”
- [ ] Bot outputs a valid Markdown table (header row + separator + rows)
- [ ] Columns are aligned logically (ID, Title, Steps, Expected Result)
- [ ] No broken pipes `|` or missing separator row

---

### 8. Answer Length & Readability

- [ ] Ask a **simple** question → answer is concise (not 20 paragraphs)
- [ ] Ask a **more complex** question → answer has more detail and structure
- [ ] Long answers are split into sections with headings / bullets
- [ ] No extremely long, unstructured paragraphs

---

### 9. Multilingual Formatting Consistency

- [ ] Ask the **same structured question** in UA, EN, and ES (e.g., “Give a bullet list of steps for reporting a bug.”)
- [ ] In all three languages, bot:
  - Uses bullets or numbered lists
  - Keeps clear sentence structure
  - Avoids mixing languages accidentally
- [ ] Formatting style (lists, headings) is similar across languages

---

## 📊 Execution Summary

| Scenario                          | Status | Notes | Runs Tested |
|-----------------------------------|--------|-------|------------|
| Default Tone                      | ⏳ |       |            |
| Following Tone Instructions       | ⏳ |       |            |
| Sensitive Topics Tone             | ⏳ |       |            |
| Multi-Part Question Structure     | ⏳ |       |            |
| Markdown Formatting Quality       | ⏳ |       |            |
| Code and Inline Formatting        | ⏳ |       |            |
| Table Formatting                  | ⏳ |       |            |
| Answer Length & Readability       | ⏳ |       |            |
| Multilingual Formatting Consistency | ⏳ |     |            |

**Total Checks**: 25+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Aggressive, rude, or unprofessional tone  
🔴 CRITICAL: Completely unstructured answers to multi-part questions  
🟡 Risk: Inconsistent formatting (sometimes bullets, sometimes big walls of text)  
🟢 Desirable: Clean Markdown that can be copy-pasted directly into documentation

---

## ✅ Expected Behavior

✅ Tone is consistently polite, professional, and aligned with product style  
✅ Formatting is clean and readable: headings, bullets, code blocks, tables  
✅ Multi-part questions are answered in an organized way  
✅ Multilingual answers keep both tone and formatting stable across UA/EN/ES

---

## 📝 Test Execution Notes

- For each failure, keep:
  - Prompt
  - Full response
  - What was wrong (tone, structure, Markdown, etc.)
  - You can reuse these prompts later as **regression tests** after product updates
