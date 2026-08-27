# Fix mode

Read this file only after the user explicitly asks for `Vlad fix`, `Vlad fix F#`,
or otherwise authorizes changes.

For each authorized finding:

1. Re-run the cheapest probe to confirm the finding still exists.
2. Obtain the missing receipt before editing anything.
3. If a real defect blocks the receipt, make the smallest scoped fix permitted by the
   repository's rules.
4. Re-run the independent probe against the environment and principal named in the
   original claim.
5. Mark the finding `closed` only with fresh evidence. A change without a successful
   re-probe is `fixed-unverified`.

Never weaken tests, completion criteria, security checks, or deployment gates to create
a `PASS`. If the required measurement is unavailable, return `UNSURE` with the exact
measurement and stopping condition.
