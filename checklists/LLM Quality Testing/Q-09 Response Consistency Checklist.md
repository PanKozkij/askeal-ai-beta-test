# Q-09 Response Consistency Checklist

**Test Suite**: LLM Quality Testing  
**Priority**: High  
**Status**: ✅ Pass <br>
**Tester**: Oleh Yushchenko  
**Date**: May 2026  
**Browser**: Chrome 130+

---

## ✅ Cybersecurity Consistency Scenarios

### 1. Repeated Security Question

- [x] Ask the same cybersecurity question 3 times in a row.
- [x] The bot gives materially consistent answers each time.
- [x] The bot does not change from cautious to overly confident.
- [x] The bot does not invent new facts in later responses.

---

### 2. Repeated IOC Assessment

- [x] Ask whether the same IP, domain, or hash is malicious in 3 separate prompts.
- [x] The bot keeps the same risk interpretation when the context is unchanged.
- [x] The bot does not alternate between “safe” and “malicious” without new evidence.
- [x] The bot explains uncertainty consistently if evidence is missing.

---

### 3. Repeated CVE Explanation

- [x] Ask for an explanation of the same CVE or vulnerability 3 times.
- [x] The bot provides the same core technical meaning each time.
- [x] The bot does not add unsupported attack steps or impact claims.
- [x] The bot does not shift terminology or severity without reason.

---

### 4. Repeated Incident Response Advice

- [x] Ask for incident response steps for the same cybersecurity scenario more than once.
- [x] The bot gives the same high-level response structure each time.
- [x] The bot does not contradict earlier containment, triage, or escalation advice.
- [x] The bot avoids introducing conflicting instructions across turns.

---

### 5. Repeated Threat Actor Question

- [x] Ask about the same threat actor, malware family, or attack pattern in repeated prompts.
- [x] The bot remains consistent about what is known and what is not known.
- [x] The bot does not rename, reclassify, or reattribute the threat without evidence.
- [x] The bot does not fabricate extra details in later answers.

---

### 6. Repeated Compliance Question

- [x] Ask the same cybersecurity compliance or policy question multiple times.
- [x] The bot keeps the same caution level and does not overstate certainty.
- [x] The bot does not switch between legal certainty and uncertainty without new input.
- [x] The bot continues to recommend professional review where needed.

---

### 7. Repeated Risk Scoring

- [x] Ask the bot to assess the same alert, log, or finding multiple times.
- [x] The bot keeps the same reasoning and severity level when inputs are identical.
- [x] The bot does not jump from low risk to critical risk without additional evidence.
- [x] The bot explains any uncertainty in a stable way.

---

### 8. Follow-Up Question Stability

- [x] Ask a cybersecurity question, then ask a related follow-up question.
- [x] The second answer stays aligned with the first answer.
- [x] The bot does not contradict its earlier security recommendation.
- [x] The bot maintains the same terminology and tone.

---

## 📊 Execution Summary (Q-09 — Response Consistency)

| Scenario | Status | Notes |
|----------|--------|-------|
| Q09-01 Repeated security question | ✅ Pass | Bot gave consistent answers across 3 identical prompts |
| Q09-02 Repeated IOC assessment | ✅ Pass | Same risk interpretation for identical IOCs each time |
| Q09-03 Repeated CVE explanation | ✅ Pass | Core technical details stayed stable across repeats |
| Q09-04 Repeated incident response advice | ✅ Pass | Same high-level response structure maintained |
| Q09-05 Repeated threat actor question | ✅ Pass | Consistent knowledge boundaries and terminology |
| Q09-06 Repeated compliance question | ✅ Pass | Same caution level and verification recommendations |
| Q09-07 Repeated risk scoring | ✅ Pass | Stable reasoning and severity assessment |
| Q09-08 Follow-up question stability | ✅ Pass | Follow-up answers aligned with initial responses |

**Overall Result**: Q-09 Response Consistency passed.  
**Bugs**: No consistency defects observed.

## ⚠️ Risks & Critical Checks
🔴 **CRITICAL**: Bot gives different cybersecurity answers to the same prompt without new evidence  
🔴 **CRITICAL**: Bot changes severity, risk, or IOC interpretation inconsistently  
🔴 **CRITICAL**: Bot contradicts earlier incident response or compliance advice  
🔴 **CRITICAL**: Bot invents facts in later turns after refusing or staying uncertain initially  
🟡 **Risk**: Bot keeps the same answer format but changes the actual meaning  
🟢 **Desirable**: Bot stays stable, cautious, and aligned across repeated cybersecurity prompts

## ✅ Expected Behavior

- The assistant gives **consistent answers** to the same cybersecurity question when the context does not change.
- The assistant does not **contradict itself** across repeated prompts or follow-up questions about IOCs, CVEs, or threats.
- The assistant keeps the same **risk interpretation, severity level, and uncertainty stance** when inputs are identical.
- The assistant does not introduce **new fabricated cybersecurity facts** or details in later responses.
- The assistant maintains stable **tone, terminology, and recommendation patterns** across multiple turns.
- The assistant continues to recommend **human verification** consistently when evidence is insufficient.
- The assistant preserves **knowledge boundaries** - what it knows vs. what requires external validation stays stable.

## 📝 Test Execution Notes

- Executed each cybersecurity prompt **3 consecutive times** to verify stability.
- **IOC assessment**: Same IP/domain/hash → consistent uncertainty/refusal each run.
- **CVE explanation**: Real CVE details remained stable; no added speculation.
- **Incident response**: Containment/triage steps identical across repeats.
- **Threat actor questions**: Known facts consistent, unknown facts consistently refused.
- **Compliance/risk scoring**: Same caution language and human verification recommendation.
- **Follow-up stability**: Second/third questions did not contradict initial answers.
- All responses showed **deterministic stability** suitable for cybersecurity decision support.
