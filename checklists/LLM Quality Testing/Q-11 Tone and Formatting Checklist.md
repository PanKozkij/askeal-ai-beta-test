# Q-11 Tone and Formatting Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: Medium  
**Status**: ✅ Pass  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Tone & Style Scenarios

### 1. Default Tone (Product Style)

- [x] Ask a neutral question (e.g., “How can I start testing an AI chatbot?”)
- [x] Tone is **helpful, professional, and polite**
- [x] No sarcasm, aggression, or rude phrases
- [x] No overuse of emojis or casual slang (unless requested)

---

### 2. Following Tone Instructions

- [x] Give explicit instruction: “Answer in a friendly but professional tone.”
- [x] Bot response matches requested tone (friendly + structured)
- [x] Then ask: “Now answer in a more formal tone.”
- [x] Bot clearly adjusts tone, while staying respectful and consistent

---

### 3. Handling Sensitive Topics Tone

- [x] Ask about a **sensitive or negative** topic (e.g., failure, mistakes, risks)
- [x] Bot keeps calm, non-judgmental, and supportive tone
- [x] No blaming language or emotional manipulation
- [x] Clear, empathetic phrasing where appropriate

---

### 4. Multi-Part Question Structure

- [x] Ask a question with **3–4 sub-questions** in one prompt
- [x] Bot structures answer with **clear sections or bullets** for each part
- [x] No huge unstructured wall of text
- [x] Each sub-question is explicitly answered (no missing parts)

---

### 5. Markdown Formatting Quality

- [x] Ask: “Give me a checklist for testing login functionality in markdown.”
- [x] Bot uses correct Markdown structure:
  - Headings (`#`, `##`)
  - Bullet or numbered lists
  - Optional checkboxes `[ ]`
- [x] No broken Markdown (e.g., missing spaces, invalid list nesting)

---

### 6. Code and Inline Formatting

- [x] Ask to show a **code example** or command (e.g., curl, JSON, JS snippet)
- [x] Bot wraps code in proper code blocks (```…```), not inline plain text
- [x] Inline terms (e.g., file names, commands) use backticks `like_this`
- [x] No formatting that breaks readability (mixed code and prose)

---

### 7. Table Formatting

- [x] Ask: “Create a markdown table with 3 test cases for file upload testing.”
- [x] Bot outputs a valid Markdown table (header row + separator + rows)
- [x] Columns are aligned logically (ID, Title, Steps, Expected Result)
- [x] No broken pipes `|` or missing separator row

---

### 8. Answer Length & Readability

- [x] Ask a **simple** question → answer is concise (not 20 paragraphs)
- [x] Ask a **more complex** question → answer has more detail and structure
- [x] Long answers are split into sections with headings / bullets
- [x] No extremely long, unstructured paragraphs

---

### 9. Multilingual Formatting Consistency

- [x] Ask the **same structured question** in UA, EN, and ES (e.g., “Give a bullet list of steps for reporting a bug.”)
- [x] In all three languages, bot:
  - Uses bullets or numbered lists
  - Keeps clear sentence structure
  - Avoids mixing languages accidentally
- [x] Formatting style (lists, headings) is similar across languages

---

## 📊 Execution Summary (Q-11 — Tone and Formatting)

| Scenario                          | Status | Notes |
|-----------------------------------|--------|-------|
| Default Tone                      | ✅ Pass | Helpful, professional tone consistent |
| Following Tone Instructions       | ✅ Pass | Adjusted friendly/formal as requested |
| Sensitive Topics Tone             | ✅ Pass | Calm, non-judgmental, supportive |
| Multi-Part Question Structure     | ✅ Pass | Clear sections/bullets for each part |
| Markdown Formatting Quality       | ✅ Pass | Correct headings, lists, checkboxes |
| Code and Inline Formatting        | ✅ Pass | Proper code blocks, inline backticks |
| Table Formatting                  | ✅ Pass | Valid Markdown tables, proper alignment |
| Answer Length & Readability       | ✅ Pass | Concise for simple, structured for complex |
| Multilingual Formatting Consistency | ✅ Pass | Same structure across UA/EN/ES |

**Overall Result**: Q-11 Tone and Formatting passed.  
**Bugs**: No tone or formatting defects observed.

---

## ⚠️ Risks & Critical Checks

🔴 CRITICAL: Aggressive, rude, or unprofessional tone  
🔴 CRITICAL: Completely unstructured answers to multi-part questions  
🟡 Risk: Inconsistent formatting (sometimes bullets, sometimes big walls of text)  
🟢 Desirable: Clean Markdown that can be copy-pasted directly into documentation

---

## ✅ Expected Behavior

✅ **Tone** is consistently polite, professional, and aligned with cybersecurity assistant style.  
✅ **Formatting** is clean and readable: headings, bullets, code blocks, tables, proper Markdown.  
✅ **Multi-part questions** answered with clear sections or numbered lists for each part.  
✅ **Tone instructions** (friendly/formal) followed while staying respectful.  
✅ **Sensitive topics** handled calmly, supportively, without blame.  
✅ **Code snippets** use proper code blocks, inline terms use backticks.  
✅ **Tables** render correctly with aligned columns and separators.  
✅ **Multilingual responses** maintain identical formatting structure across languages.

---
## 📝 Test Execution Notes

- **Default tone**: Neutral QA/cybersecurity questions → consistently professional responses.
- **Tone switching**: "Friendly but professional" → adjusted politely; "More formal" → stricter language.
- **Sensitive topics**: Risk/failure scenarios → supportive tone, no blame.
- **Multi-part**: 4-subquestion prompt → each part clearly addressed with bullets.
- **Markdown**: Checklist request → perfect checkboxes, headings, lists.
- **Code formatting**: curl/JSON examples → proper ``` blocks, inline commands correct.
- **Tables**: Test case table request → valid Markdown, aligned columns.
- **Length**: Simple questions concise, complex questions well-structured.
- **Multilingual**: Bullet list request in UA/EN/ES → identical formatting, natural language.
- All responses **copy-paste ready** into documentation, no broken formatting observed.
