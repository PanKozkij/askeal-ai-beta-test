# Test Plan — Askeal AI Beta Testing

**Document Type**: Test Plan  
**Project**: Askeal AI — LLM Chatbot (Closed Beta)  
**Author**: Oleh Yushchenko — Junior QA Engineer  
**Version**: 1.0  
**Date**: April 2026  

***

## 1. Purpose

This document describes the detailed test plan for the beta testing of Askeal AI.
It translates the high-level test strategy into practical test execution areas,
priorities, environments, entry and exit criteria, and deliverables.

The main goal of this test plan is to ensure broad and structured coverage of
functional behavior, LLM response quality, security risks, and basic performance
characteristics of the chatbot.

***

## 2. Test Items
All testing is performed in the context of Askeal’s closed beta and follows
the official Terms of Use: professional usage, evaluation/testing only, and
no reliance on the Service as sole source of cybersecurity decisions. <br>
The following product areas are planned for testing:

- Chat input field and user interactions
- File upload functionality
- Refresh behavior and session persistence
- "Try asking about" prompt suggestions
- Footer links and informational pages
- Recent howls section
- New howl creation
- Delete howl flow
- Day/Night mode toggle
- Multi-turn conversations
- Prompt behavior and instruction-following
- RAG-related behavior (if applicable)
- Security vulnerabilities specific to LLM systems
- Performance under long prompts and longer sessions

***

## 3. Features to Be Tested

### 3.1 Functional Testing

| ID | Feature | Coverage |
|----|---------|----------|
| F-01 | Field validation | Empty input, long input, special characters |
| F-02 | File upload | Valid file, invalid format, large file, error handling |
| F-03 | Refresh webpage | Session persistence, chat state after reload |
| F-04 | "Try asking about" | Clickability, relevance, prompt injection into input |
| F-05 | Footer links | Legal Notice, Privacy Policy, Terms of Use, AI Information, Cookie Policy, Manage Cookies |
| F-06 | Recent howls | Display, navigation, sorting, visibility |
| F-07 | New howl | Creation flow, save behavior, validation |
| F-08 | Delete howl | Delete action, confirmation, result after refresh |
| F-09 | Day/Night mode | UI toggle, persistence after refresh |
| F-10 | Error states | Empty result, timeout, no internet, failed requests |
| F-11 | Session management | Idle behavior, restored/not restored state |
| F-12 | Browser compatibility | Chrome, Firefox, Safari |

### 3.2 LLM Quality Testing

| ID | Feature | Coverage |
|----|---------|----------|
| Q-01 | Multi-turn conversations | Context retention across multiple turns |
| Q-02 | Prompt role clarity | Stays in defined role and task |
| Q-03 | Negative constraints | Respects restrictions and forbidden actions |
| Q-04 | Dialog depth | Maintains context after 5–10+ messages |
| Q-05 | Lost in the Middle | Handles important info placed in middle of context |
| Q-06 | RAG quality | Retrieves correct information from documents |
| Q-07 | Refusal behavior | Says it does not know when answer is unavailable |
| Q-08 | Hallucination check | Avoids invented facts or unsupported claims |
| Q-09 | Response consistency | Same prompt ×3 gives stable behavior |
| Q-10 | Multilingual behavior | Understands and answers in UA/EN/ES |
| Q-11 | Tone and formatting | Maintains expected style and clear structure |

### 3.3 LLM Security Testing

| ID | Feature | Coverage |
|----|---------|----------|
| S-01 | Prompt injection | Ignore instructions / override system behavior |
| S-02 | Jailbreak attempts | Role-play attacks, DAN-style prompts |
| S-03 | Indirect injection | Hidden instructions in uploaded content |
| S-04 | System prompt leakage | Attempts to reveal internal instructions |
| S-05 | Sensitive content handling | Harmful, discriminatory, unsafe requests |
| S-06 | Boundary values | Long prompts, strange symbols, empty prompts |
| S-07 | Session leakage | Requests about previous user conversations |

### 3.4 Performance Testing

| ID | Feature | Coverage |
|----|---------|----------|
| P-01 | Time to First Token | Time from send action to first visible response token |
| P-02 | Response completion time | Short prompt vs long prompt timing |
| P-03 | Concurrent sessions | Multiple tabs / sessions opened at once |
| P-04 | Long context behavior | Response degradation after many turns |
| P-05 | Timeout handling | Very slow response or no response scenario |
| P-06 | Large input handling | Large message or large file impact |

## 3.5 Test Data Policy

- Only synthetic, anonymized, or non-personal data is used in test scenarios.
- No real production data, special categories of personal data (e.g. health,
  political opinions, religious beliefs), or criminal/offence-related data
  are entered into the Service.
- Any example logs, user names, IPs, or identifiers used in tests are purely
  fictional and not derived from real customers or systems.
***

## 4. Features Not Planned for This Phase

The following areas are not included in the current beta test phase:

- Full backend / API validation
- Accessibility testing (WCAG)
- Deep load and stress testing
- Mobile application testing
- Automation using Playwright or other frameworks
- Database validation
- - Validation of legal/compliance interpretations of Terms of Use or Privacy Policy
  (the Service is tested as a decision-support tool only)

These areas may be considered in future iterations if access and scope expand.

***

## 5. Test Methodology

The following testing approaches are used in this project:

- **Manual testing** for core functional and UI behavior
- **Exploratory testing** for unexpected LLM behavior and edge cases
- **Scripted prompt testing** for repeatable evaluation of chatbot quality
- **Security-oriented testing** based on OWASP LLM Top-10
- **Risk-based prioritization** to focus on the most important areas first
- **Repeated runs** for non-deterministic LLM outputs

### Test Design Techniques

- Equivalence Partitioning (EP)
- Boundary Value Analysis (BVA)
- Error Guessing
- Use Case Testing
- Exploratory Testing
- Adversarial Prompt Testing

***

## 6. Test Environment

| Component | Details |
|-----------|---------|
| Application | Askeal AI beta chatbot |
| Access type | Closed beta access |
| Main browser | Google Chrome |
| Additional browsers | Firefox, Safari |
| Device type | Desktop / laptop |
| Testing tools | Chrome DevTools, Google Sheets, GitHub |
| Documentation format | Markdown (.md), tables, reports |
| Access / Auth | Closed beta access, authenticated via organization SSO where applicable |
| Data policy | Synthetic/anonymized test data only; no real personal/sensitive data |

***

## 7. Entry Criteria

Testing can begin when all of the following conditions are met:

- Beta access is available
- The chatbot interface is reachable and stable enough to test
- Core test documentation exists
- Test scenarios for the selected suite are prepared
- Environment and browser are ready

***

## 8. Exit Criteria

Testing can be considered complete for the current phase when:

- All planned critical and high-priority scenarios are executed
- At least 85% of planned coverage is completed
- All severe issues are documented
- LLM security scenarios are reviewed
- Summary report is completed

***

## 9. Test Deliverables

The following deliverables are expected as part of this project:

| Deliverable | Description |
|-------------|-------------|
| Test Strategy | High-level approach, risks, priorities |
| Test Plan | Detailed scope, features, execution focus |
| Test Cases | Structured cases for key flows and risks |
| Checklists | Quick validation for functional and security areas |
| Eval Rubrics | Scoring model for LLM quality |
| Bug Reports | Defect documentation with clear reproduction steps |
| Test Summary Report | Final overview of findings and coverage |

***

## 10. Risks and Constraints

| Risk / Constraint | Impact |
|------------------|--------|
| Closed beta restrictions | Screenshots or media may not be allowed |
| No automation at current stage | All tests are manual, execution may take longer |
| No API / backend access | Some technical validation is not possible |
| Non-deterministic responses | Results may vary between runs |
| Beta instability | Some failures may be environment-related, not functional |

### Mitigation

- Use detailed written documentation instead of screenshots
- Prioritize critical test areas first
- Re-run important prompt-based scenarios multiple times
- Separate product issues from environment instability where possible

***

## 11. Execution Priorities

### Priority 1 — Critical

- Prompt injection
- Core chat functionality
- File upload behavior
- Session persistence
- System prompt leakage
- Sensitive content handling

### Priority 2 — High

- Multi-turn context memory
- Hallucination detection
- Refusal behavior
- Footer links
- New howl / Delete howl behavior
- Day/Night mode

### Priority 3 — Medium

- Multilingual behavior
- Long-context performance
- Cross-browser checks
- Recent howls
- Suggestion prompts

***

## 12. Metrics

| Metric | Target |
|--------|--------|
| Planned coverage | 85%+ of business-critical functionality |
| Security scenario coverage | 100% of selected LLM security scenarios |
| Stability check | Same important prompt executed ×3 |
| Test documentation | 50+ cases/checks across major suites |
| Defect documentation | All High/Critical defects clearly recorded |

***

## 13. Approval

This test plan is created as part of an independent QA portfolio project
based on a real beta testing opportunity. It is intended to demonstrate
structured QA thinking, documentation skills, and understanding of
LLM-specific testing risks.
