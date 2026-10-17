# KB-003 | Missing data or an unexpected total

**Demonstration article for a fictional application.** Audience: users, workspace owners, and support.

## Start with a precise comparison

Record the result you expected, the result displayed, the approved reference source, and the business impact. “October units are 400 in the summary and 1,000 in the matching detail export” is more actionable than “the dashboard is wrong.”

## Compare the same scope

| Check | Question |
| --- | --- |
| Workspace and scenario | Are both results from the same organization, workspace, and planning scenario? |
| Date range | Are the beginning and ending business dates the same, using the same time zone? |
| Filters | Do retailer, product, region, and any saved filters match? |
| Measure | Are you comparing units with units, or revenue with revenue in the same currency? |
| Freshness | When did the last refresh finish, and does the reference include later records? |
| Access | Could an approved data restriction explain why one user sees fewer records? |

## Classify what you can establish

- **A view or scope difference:** Explain the differing setting and have the user repeat the comparison.
- **A delayed or failed refresh:** Record the last successful refresh and route the request to the responsible data team.
- **A possible source-data problem:** Ask the authorized owner to review a minimal example before any correction.
- **A reproducible application defect:** Gather matching filters, example values, timestamps, and reproduction steps for engineering.

Do not edit source records merely to force two totals to agree.

## Escalate with useful evidence

Provide the expected and actual values, affected period, number of affected users if known, and a minimal permitted example. Mark assumptions and unknowns. State whether the issue prevents a decision and whether a verified workaround exists.

## Verify before closing

Repeat the same comparison after the correction or fix, confirm the result with the user, and record the outcome. If the investigation remains open, give a specific next-update time.

**Related:** [Worked support case](CASE-001-monthly-total.md)
