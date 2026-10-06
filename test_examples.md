# Topic 6 — Tool Usage Test Examples

## Employee Leave Assistant

This file documents the Topic 6 tool-usage tests for the Employee Leave Assistant.

## Tool Decision Logic

- Standard leave-policy question → Use the approved knowledge file.
- Current/recent verification request → Use Web Search.
- Missing internal policy information that is not a current/live request → Do not use Web Search to fill the gap; direct the employee to sumHR or HR.
- Web Search failure or unreliable result → Do not guess; direct the employee to sumHR or HR.

## Test 1 — Tool Required

**Question:** Has this leave policy changed recently?

**Expected Tool Behavior:** Web Search should be triggered.

**Reason:** The question explicitly asks whether the information has recently changed.

**Expected Response Behavior:**
- Use Web Search for reliable current information.
- Clearly distinguish uploaded-policy information from Web Search information.
- Cite the relevant external source.
- If company-specific information cannot be verified, direct the employee to sumHR or HR.

**Actual Response:** [Paste actual response here.]

**Web Search Triggered:** Yes / No

**Result:** PASS / FAIL

## Test 2 — Tool Not Required

**Question:** Can I take half-day Adjustment/Complementary Leave?

**Expected Tool Behavior:** Web Search should NOT be triggered.

**Reason:** The uploaded leave policy already contains this information.

**Expected Response Pattern:** According to **leave policy.pdf — Adjustment/Complementary Leave > Usage Policy**, half-day leave is allowed.

**Actual Response:** [Paste actual response here.]

**Web Search Triggered:** Yes / No

**Result:** PASS / FAIL

## Test 3 — Knowledge Gap

**Question:** Who approves my leave request?

**Expected Tool Behavior:** Web Search should NOT be triggered merely to fill a company-policy gap.

**Expected Response Behavior:**
- State that the approver is not documented in the approved knowledge.
- Do not guess.
- Direct the employee to the sumHR portal or HR.

**Actual Response:** [Paste actual response here.]

**Web Search Triggered:** Yes / No

**Result:** PASS / FAIL

## Test 4 — Current Information Verification

**Question:** Is the leave information in my uploaded policy still current?

**Expected Tool Behavior:** Web Search should be triggered.

**Expected Response Behavior:**
- Use Web Search for current verification.
- Keep the uploaded policy as the internal knowledge reference.
- Clearly separate internal policy information from external web information.
- If current company-specific information cannot be verified, direct the employee to sumHR or HR.

**Actual Response:** [Paste actual response here.]

**Web Search Triggered:** Yes / No

**Result:** PASS / FAIL

## Test 5 — Web Search Failure / No Reliable Result

**Question:** Has the Adjustment/Complementary Leave policy changed this month?

**Expected Tool Behavior:** Web Search should be attempted.

**Expected Fallback Behavior:**
- Do not guess.
- State that current company-specific information could not be reliably verified.
- Do not present generic internet information as company policy.
- Direct the employee to sumHR or HR.

**Actual Response:** [Paste actual response here.]

**Web Search Triggered:** Yes / No

**Result:** PASS / FAIL

## Tool Behavior Evaluation

| Test | Scenario | Expected Tool Behavior | Result |
|---|---|---|---|
| Test 1 | Recent policy change | Web Search required | PASS / FAIL |
| Test 2 | Half-day leave policy | Knowledge file only | PASS / FAIL |
| Test 3 | Missing approver information | No Web Search; sumHR/HR fallback | PASS / FAIL |
| Test 4 | Is policy still current? | Web Search required | PASS / FAIL |
| Test 5 | Recent change with no reliable result | Web Search + safe fallback | PASS / FAIL |

## Troubleshooting Checklist

- [ ] Web Search is enabled in the Custom GPT.
- [ ] The approved leave-policy knowledge file is uploaded.
- [ ] Web Search is restricted to current, recent, live, or externally verifiable information.
- [ ] Web Search is not used as a general fallback for missing company-policy information.
- [ ] The knowledge file is prioritized for standard leave-policy questions.
- [ ] Web-sourced information is clearly separated from internal policy information.
- [ ] Knowledge-file answers reference the relevant document and section.
- [ ] Failed or unreliable Web Search results do not cause the GPT to guess.
- [ ] Missing company-specific information is redirected to sumHR or HR.

## Final Validation

Topic 6 is successfully completed when the Employee Leave Assistant:
- Uses the approved knowledge file for standard leave-policy questions.
- Uses Web Search only when current/live verification is required.
- Avoids unnecessary Web Search.
- Does not use Web Search to fill missing internal-policy information.
- Clearly distinguishes web information from internal policy information.
- References the relevant knowledge source when answering from the policy.
- Does not guess when Web Search fails.
- Directs employees to sumHR or HR when company-specific information cannot be verified.
