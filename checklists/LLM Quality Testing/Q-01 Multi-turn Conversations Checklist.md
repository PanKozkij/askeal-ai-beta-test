# Q-01 Multi-turn Conversations Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ⏳ Not Executed  
**Tester**: Oleh Yushchenko  
**Date**: April 2026  
**Browser**: Chrome 130+

---

## ✅ Multi-turn Conversation Scenarios

### 1. Basic Context Retention (2 turns)
- [ ] Send message 1 → Bot responds
- [ ] Send message 2 referencing message 1 → **context remembered**
- [ ] Bot references **previous user message** in response
- [ ] Bot maintains **conversation flow**

### 2. 5-turn Conversation
- [ ] Create conversation with **5 messages**
- [ ] Message 5 references **message 1** → context retained
- [ ] Bot remembers **user preferences** from early messages
- [ ] No repetition or confusion

### 3. User Name Memory
- [ ] User says: "My name is Oleh"
- [ ] 3 messages later → Bot uses **"Oleh"** naturally
- [ ] Bot remembers name **across 10 turns**

### 4. Complex Context
- [ ] Message 1: "I live in Spain"
- [ ] Message 3: "Weather here is nice"
- [ ] Message 5: "Recommend Alicante restaurant" → **uses location context**

### 5. Context Reset Test
- [ ] Long conversation (10 turns)
- [ ] **New Howl** → **previous context forgotten**
- [ ] Fresh conversation starts cleanly

### 6. Edge Cases
- [ ] **Very short messages** → context still works
- [ ] **Very long messages** → context maintained
- [ ] **Multiple topics** → switches smoothly
- [ ] **User changes topic abruptly** → adapts

---

## 📊 Execution Summary

| Scenario | Status | Notes | Turns Tested |
|----------|--------|-------|--------------|
| Basic Retention | ⏳ | | |
| 5-turn | ⏳ | | |
| User Name | ⏳ | | |
| Complex Context | ⏳ | | |
| Context Reset | ⏳ | | |
| Edge Cases | ⏳ | | |

**Total Checks**: 22+  
**Pass Rate**: ⏳ Not calculated

---

## ⚠️ Risks & Critical Checks
🔴 CRITICAL: Context loss = core chatbot failure <br>
🔴 CRITICAL: Repetition loops <br>
🟡 Name confusion (user1 vs user2) <br>
🟢 Topic switching too slow <br>


**Expected Behavior**:<br>
✅ Bot remembers conversation across 10+ turns <br>
✅ References previous messages naturally <br>
✅ Maintains user preferences <br>
✅ New Howl = fresh context <br>
✅ Smooth topic transitions <br>


**Test Execution Notes**:
- Use YOUR name "Oleh" in conversation

- Test with Spanish location context

- Create 10+ turn conversations

- Verify context reset works

- Test topic switching speed
