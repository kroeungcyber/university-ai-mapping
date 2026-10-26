# AI Opportunity Map — Student Enrollment & Course Registration

> A structured process-mapping and prioritization exercise. Maps one university
> workflow, scores candidate AI improvements on **value, simplicity, risk,
> sustainability, and institutional readiness**, and recommends a low-risk first move.

---

## 1. The process

**Process:** Student enrollment / course registration

**Owner:** Registrar's Office

**Trigger:** A student submits a registration or course-change request.

**Success:** Student is enrolled correctly within the target window, with no
duplicate records and no manual re-keying errors.

---

## 2. Current-state workflow

| # | Step | Who | Repetitive? | Stable rule? | Pain |
|---|---|---|---|---|---|
| 1 | Student fills paper/PDF form | Student | Yes | Yes | Low |
| 2 | Staff re-keys data into the student system | Admin | Yes | Yes | **High** — manual, error-prone |
| 3 | Staff checks prerequisites manually | Admin | Yes | Partly | Medium — slow |
| 4 | Supervisor approves/rejects | Supervisor | Yes | Yes | Medium — bottleneck |
| 5 | Student notified by email | Admin | Yes | Yes | **High** — repetitive drafting |
| 6 | Record filed / archived | Admin | Yes | Yes | Low |

**Pain points worth attacking:** steps 2, 3, and 5 — high volume, low judgment,
stable rules.

---

## 3. Candidate AI/automation improvements

Scored 1–5 (5 = best) on each criterion.

| Candidate | Value | Simplicity | Risk | Sustainability | Readiness | Total |
|---|---|---|---|---|---|---|
| A. Form-to-database extraction (LLM/OCR parses form → pre-fills system) | 4 | 3 | 3 | 4 | 3 | 17 |
| B. Prerequisite-check assistant (reads record + rules → flags conflicts) | 3 | 4 | 2 | 4 | 4 | 17 |
| C. AI-drafted notification emails, human-approved send | 5 | 5 | 1 | 5 | 5 | **21** |
| D. Fully autonomous enrollment agent (no human review) | 5 | 1 | 5 | 2 | 1 | 14 |

---

## 4. Recommendation

**Start with C — AI-drafted notification emails with a human "send" step.**

- Highest value-to-risk ratio: saves the most repetitive time with near-zero downside.
- Fastest to build and demonstrate (weeks, not months).
- Human-in-the-loop by design → passes governance and data-protection review.
- A visible "quick win" that builds institutional confidence before moving to B, then A.

**Defer D** — full autonomy over enrollment decisions is high-risk and low-readiness;
it becomes viable only after the earlier wins build trust and better data hygiene.

---

## 5. Governance notes

- **Data handled:** student name, ID, course codes, email — personal data; treat
  as confidential and do not send to unapproved third-party models.
- **Human-in-the-loop:** a human approves every outbound email and every enrollment change.
- **Guardrails:** whitelist of allowed templates; audit log of every generated draft.
- **Rollback:** the tool only drafts; the source system remains the source of truth.
- **Approval:** aligns with the university's AI governance and data-protection policy.

---

## 6. Success measures

- Hours/week saved on the target step (baseline → after).
- Error rate (re-keying mistakes) before vs. after.
- Staff confidence: can the owner run it independently after handover? (yes/no)
