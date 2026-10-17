# KB-001 | Sign-in and MFA troubleshooting

**Demonstration article for a fictional application.** Audience: end users and first-line support.

## When to use this guide

You cannot reach Sample Planning Workspace because sign-in fails, an invitation is not accepted, or an MFA prompt does not complete.

## Work through these checks

1. Confirm you opened the organization's approved workspace address.
2. Check that you selected the work account invited to that workspace. A browser can retain a personal account or an account from another organization.
3. Read the error. Record its exact wording, the time and time zone, and whether it appeared at the identity provider or after returning to the application.
4. If the identity provider reports a locked account, an unassigned application, or a device-policy failure, contact your organization's identity administrator. Support should record the handoff and next update.
5. If an MFA code is rejected, check the device clock and use the organization's approved recovery process. Repeated retries can make a lockout worse.
6. If identity-provider sign-in succeeds but the application refuses entry, have support check the workspace invitation and approved account assignment.

If organizational policy permits, a private browser session can help identify an old browser session or the wrong selected account. It does not fix a missing assignment or permission.

## Information support needs

- Workspace and organization name.
- Invited work account, supplied through the approved support channel.
- Exact error, timestamp, browser, and affected step.
- Whether you previously had access and whether other users are affected.
- A screenshot with unrelated personal information removed.

Do not send passwords, session tokens, MFA codes, or recovery codes.

## Verification and handoff

Access is restored when the user signs in normally and opens the intended workspace with the approved role. If an administrator must act, keep the support request open or explicitly tracked while awaiting that action. Escalate a reproducible application failure with the error, timing, scope, and steps already checked.

**Related:** [Workspace access](KB-002-workspace-access.md)
