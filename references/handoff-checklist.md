# Handoff checklist

Fail closed: a missing receipt means the claim is not accepted.

| Claim | Minimum receipt | Reject when |
|---|---|---|
| Merged or on main | Commit or tree is present on current `origin/main` | Only a branch tip or open PR is shown |
| Tests passed | Command plus exit code, or a CI job proving the relevant suite ran | Tests merely exist, were skipped, or exercised another package |
| Deployed or live | Named environment plus deployment identity and a user-visible probe | A deploy API alone says success |
| Auth works | Credential presence, load path, and a harmless authenticated probe | Someone says “needs a credential” without checking the existing paths |
| Permissions work | The affected principal completes the action | An administrator performs a query they could already run |
| Workspace is clean | Current branch, status, stashes, and session PR state | The tree is dirty or work remains outside the claimed artifact |
| Worker or agent finished | Stable job, run, or output identity plus inspection of what changed | The worker's own summary is the only evidence |
| Production data fact | A fresh query against the named production system | Sandbox data or a prior-session memory is substituted |
| Configuration took effect | Trace the value from its source to the actor and observe behavior | A setting exists but its consumer is not shown |
| No drift | Current remote state and runtime artifact are compared to the checkout | A stale fetch, cached page, or old process is treated as current |

## Receipt quality

A useful receipt is fresh, independent, scoped to the claim, and falsifiable. Prefer
stable identifiers and counts over narration. State the environment and identity next
to every live result.

## Auth before escalation

Before declaring an authentication blocker:

1. Find a working example of the same access in the project.
2. Check the documented fallback path.
3. Check the credentials and authenticated sessions already available without printing
   secret values.
4. Read the platform's exact error body or reason string.

Only then name the precise human action that remains.

## Verdicts

- `PASS` — every scoped claim has a fresh, sufficient receipt.
- `FAIL` — a receipt is missing or contradicted.
- `UNSURE` — name the exact measurement that would resolve the ambiguity.
