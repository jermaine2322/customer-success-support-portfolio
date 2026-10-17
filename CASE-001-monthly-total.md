# CASE-001 | An October summary excludes the last day

**Entirely fictional demonstration.** All data, people, timestamps, defects, investigation steps, and outcomes below are invented. This is a worked example of how I would manage a request, not a claim that I investigated a Sciemo defect.

## Intake and impact

| Field | Example record |
| --- | --- |
| Reported | Day 1, 09:00 Eastern |
| Requester | Planner at Sample Customer A |
| Product | Sample Planning Workspace |
| Customer goal | Reconcile October units before a planning meeting |
| Symptom | Summary shows 400 units; detail export shows 1,000 |
| Initial classification | Data discrepancy; possible calculation defect |
| Scope | One workspace and date range confirmed; wider scope initially unknown |
| Owner | Customer support |
| Next update | Day 1, 11:00 Eastern |

The customer can still open the workspace. No outage or source-data corruption has been established. I would prioritize against the planning deadline, confirmed scope, and available workaround using the organization's service policy.

## First customer reply

“Thank you for including the two totals. I understand you need to reconcile October units before your planning meeting. Please confirm the workspace, scenario, and active product and retailer filters, along with the time zone used for the report. I will compare the summary with the matching detail rows and send an update by 11:00 a.m. Eastern, even if the investigation is still open.”

## Investigation record

1. Confirmed that the summary and export use the same workspace, scenario, measure, and visible filters.
2. Confirmed that both show the same completed refresh.
3. Reproduced the discrepancy in an authorized test workspace with two synthetic rows.
4. Observed that including October 31 in the visible range did not add that day's units to the summary.
5. Recorded the request boundary in a permitted diagnostic log. The summary's exclusive ending timestamp is the start of October 31, although the visible selection runs through October 31.
6. Kept the diagnosis tentative until engineering reviewed the boundary handling.

### Minimal synthetic dataset

The fictional workspace uses America/New_York business dates.

| Business timestamp | Units |
| --- | ---: |
| 2026-10-01 09:00 -04:00 | 400 |
| 2026-10-31 13:00 -04:00 | 600 |
| Expected October total | 1,000 |

**Observed:** 400 units in the summary; both rows in the detail export.

## Engineering handoff

**Title:** October 1–31 summary omits October 31 records.

**Environment:** Fictional web application, test workspace, America/New_York, baseline scenario. No production customer data attached.

**Steps to reproduce:**

1. Load the two synthetic records above.
2. Open the summary and select October 1 through October 31, 2026.
3. Clear other filters and select the baseline scenario.
4. Compare the summary total with the matching detail export.

**Expected:** 1,000 units; both October business dates are included.

**Actual:** 400 units; the last-day row is excluded from the summary.

**Evidence:** The illustrative diagnostic field `endExclusive` is `2026-10-31T00:00:00-04:00`. An inclusive October 31 business-date selection would require an exclusive boundary at the start of November 1 for this time zone.

**Hypothesis:** The summary converts the inclusive ending date to an exclusive boundary without advancing to the next business day. Engineering should confirm the relevant contract and implementation.

**Known scope:** Reproduced with this dataset and date range. Other ranges, customers, and time zones are unverified.

**Impact:** A customer may base a planning decision on an incomplete summary.

**Requested investigation:** Check date-boundary handling and whether summary and export apply the same rules.

## Customer update while engineering investigates

“I reproduced the difference in a test workspace and sent engineering the exact steps and example records. The last day's records appear in the detail export but not in the summary. Engineering is checking the date boundary; we have not confirmed the full scope. For your meeting, we can reconcile the authorized detail rows together if that approach works for your team. I will update you by 3:00 p.m. Eastern. Please treat the summary total as under investigation.”

The manual reconciliation is a temporary, explicitly identified workaround. It does not close the defect or change the source records.

## Illustrative verification and closure

In this fictional outcome, engineering confirms and corrects the date boundary. Support then checks:

- October 31 at 23:59 remains inside the October range.
- November 1 at 00:00 falls outside the October range.
- The summary and detail export both total 1,000 for the original example.
- A 28-day month and a 30-day month behave correctly.
- A second supported time zone behaves according to its configured business dates.
- Approved data restrictions still apply.

Engineering owns code-level regression tests. Support records the build or release reference and asks the customer to repeat the original task.

**Final customer message:** “The date-boundary correction is available. I repeated your original comparison: the summary and detail export now both show 1,000 units for the October example. Please confirm the result in your workspace before using the summary for your planning decision.”

Only after the customer confirms would I record the resolution, close the support request, and link the fix. I would add the date-range comparison step to [KB-003](KB-003-data-discrepancies.md) and track whether similar requests recur. No measured reduction in tickets is claimed.
