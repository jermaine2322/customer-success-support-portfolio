# FR-001 | Make shared report context easier to understand

**Fictional feature-request example.** The customer feedback, counts, and acceptance criteria below are invented for this demonstration.

## What users are trying to do

Compare a planning view with a colleague and understand why their totals differ.

In this sample scenario, four conversations from two customer teams involved uncertainty about active filters or the last completed refresh. These counts are illustrative, not measured portfolio results.

## Problem statement

Users can share a view without clearly communicating its date range, scenario, product scope, or refresh status. They may spend time investigating a discrepancy that comes from different context.

This request is distinct from [CASE-001](CASE-001-monthly-total.md), where matching visible filters still produced an incorrect total.

## Suggested improvement

Show a compact, persistent context summary with the report's business dates, time zone, scenario, active filters, and latest completed refresh. Provide an authorized way to copy that context alongside a report link.

The product team should assess technical feasibility, privacy implications, and interaction design before choosing an implementation.

## Example acceptance criteria

- A user can identify the active dates, scenario, and filters without opening several controls.
- The displayed refresh information reflects the dataset used by the report.
- Shared links continue to enforce the recipient's existing permissions.
- Copied context excludes restricted values that the recipient is not authorized to receive.
- The summary remains accessible by keyboard and readable with assistive technology.

## Priority and validation

Record the affected workflows, customer impact, and frequency, then compare this request with other priorities. Do not promise delivery before product review.

First validate the need during office hours. Ask users to explain a report's context using the proposed layout. After release, examine whether they can complete that task and whether context-related repeat questions change relative to a baseline.

## Customer follow-up

“We captured the difficulty your team described when comparing shared views and submitted a proposal for clearer filter and refresh context. Product review is pending; no delivery date has been committed. In the meantime, please include the report's dates, scenario, filters, and refresh time when sharing a comparison.”
