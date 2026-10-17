# KB-002 | A user cannot open a workspace

**Demonstration article for a fictional application.** Audience: workspace owners and support.

## Identify the boundary

A user who signs in successfully but cannot open a particular workspace may have an assignment or authorization issue. Confirm the exact message before treating it as a password problem.

In this scenario, workspace owners approve access. Support follows that approval process.

## Check in order

1. Confirm the signed-in account and the exact workspace being requested.
2. Ask what the user needs to accomplish. Reading a report and saving planning changes require different permissions in this example.
3. Confirm that the authorized workspace owner approved the requested access.
4. Have the authorized administrator check invitation status, workspace membership, role, and applicable data restrictions.
5. Compare the affected workspace with one the user can already open. A second user with the same approved role may help establish the scope without sharing an account.
6. After an approved change, ask the user to sign in again and repeat the original task.

Do not grant an administrator role simply to make an error disappear.

## If the assignment appears correct

Record the error wording, account reference, workspace reference, approved role, timestamp, and reproduction steps. If an example request identifier is available, include it through the approved channel. Exclude tokens and credentials.

Escalate when approved access and configured membership agree but the original action still fails reproducibly. A “403” or similar error is evidence of a denied request; it does not by itself prove which permission is wrong.

## Confirm the result

Have the user verify the original task within the intended data scope. Record the approval and the change made. An application defect should remain linked to the engineering investigation even when another approved access path is available.

**Related:** [Sign-in and MFA](KB-001-sign-in-and-mfa.md)
