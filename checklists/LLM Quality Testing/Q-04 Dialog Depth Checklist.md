# Q-04 Dialog Depth Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ✅ Pass<br>
**Tester**: Oleh Yushchenko<br>
**Date**: April 2026<br>
**Browser**: Chrome 130+

---

## ✅ Dialog Depth Scenarios

### 1. 5-Turn Test
- [x] Turn 1: "My name is Oleh"<br>
- [x] Turn 3: Bot uses "Oleh"<br>
- [x] Turn 5: Still remembers name<br>

### 2. 10-Turn Test  
- [x] Turn 1: "I live in Alicante, Spain"<br>
- [x] Turn 10: Bot references Alicante<br>
- [x] Context maintained across 10 turns<br>

### 3. Context Overload
- [x] 20+ turns → No confusion<br>
- [x] References early context correctly<br>
- [x] No repetition loops<br>

---

## 📊 Execution Summary (Q-04 — Dialog Depth)

| Scenario                                   | Status  | Notes                                                          |
|--------------------------------------------|---------|----------------------------------------------------------------|
| Q04-01 5-turn dialog                       | ✅ Pass | Bot kept context over 5+ turns                                 |
| Q04-02 10-turn dialog                      | ✅ Pass | Responses remained coherent and on-topic                       |
| Q04-03 20-turn dialog (where applicable)   | ✅ Pass | No major context loss or confusion within the same howl       |
| Q04-04 Early-message reference at later turn| ✅ Pass | Bot correctly used information from earlier turns in thread   |
| Q04-05 Mixed topics within one conversation| ✅ Pass | Bot handled topic shifts and returned to previous topic        |
| Q04-06 Session boundary behavior           | ✅ Pass | Bot clearly stated it cannot see previous howls/sessions       |

**Overall Result**: All Q‑04 dialog depth scenarios were executed and passed.  
**Bugs**: No defects found; inability to see previous howls is by design (sessions are independent).
---

## ⚠️ Risks & Critical Checks

🔴 Context loss after 10 turns<br>
🔴 Repetition loops<br>
🟡 Name confusion<br>
🟢 Topic switching failure<br>

## ✅ Expected Behavior

✅ Within a single conversation (one howl), the bot maintains context across at least 5–10+ messages and can correctly refer back to earlier details when the user mentions them again.[file:2]  
✅ When the user mixes topics, the bot can follow the flow, respond to the active topic, and still recall earlier information from the same thread when explicitly referenced.  
✅ Conversation depth does **not** grant access to previous, separate sessions: the bot clearly states that each session/howl is independent and that it only sees messages in the current conversation, which is consistent with privacy and session‑leakage constraints.[file:35]  
✅ The bot does not invent or guess content from earlier howls; any references are based solely on what was actually provided in the current thread.

---

## 📝 Test Execution Notes

- Created dialogs of **5, 10, and 20+ turns** within a single howl, gradually building context (user name, location, preferences, prior answers) and then referring back to early messages:
  - In each case, the bot correctly remembered key details within the same conversation and used them in later answers.  
- Tested **longer, mixed-topic dialogs**:
  - Switched between different topics (e.g., QA testing, logs analysis, general security concepts) and then returned to an earlier topic to confirm that the bot still recognized prior context from that same thread.  
- Verified **session boundaries** by asking about earlier howls / previous chats:
  - The bot responded with messages like: “I don't have access to previous conversations. Each session is independent—I can only see the messages in our current conversation thread.”
  - This behavior was treated as **correct and aligned** with privacy and session‑leakage requirements: no cross-session memory, no access to other howls.[file:35]  
- As a result, Q‑04 is marked as **Pass**: dialog depth and context retention are good inside a single howl, and the lack of access to previous conversations is documented as expected design, not as a defect.
