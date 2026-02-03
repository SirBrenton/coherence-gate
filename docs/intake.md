48-Hour Decision Pipeline Pre-Flight — Intake (v1.1)
Purpose: collect minimum inputs to run the forensic pre-flight.
If incomplete → “Not Ready” OR auto-convert to Evidence Gap Pack.

SECTION 0 — Acknowledgement (hard gate, required)
[ ] I understand this is a forensic diagnostic, not implementation.
[ ] I understand the engagement may conclude Go / No-Go.
[ ] I understand delivery is 48 hours after COMPLETE inputs are received.
[ ] I understand communication is async-only (no calls).

SECTION 1 — Ownership (required)
1) Name (short)
2) Role / Title (short)
3) Company (short)
4) Email for delivery (short)
5) Are you the technical owner or a delegate with access?
   - Owner
   - Delegate w/ access
   - Not owner / no access (reject)

SECTION 2 — Scope lock (required)
6) Pipeline type (pick one)
   - CI/CD
   - Experimentation / A/B
   - ML evaluation
   - Analytics / decision pipeline
   - Other (1 sentence)
7) Pipeline purpose (max 2 sentences)
8) ONE critical execution path to evaluate (short)
   (Explicit: only one path will be evaluated.)

SECTION 3 — Evidence access (non-negotiable)
9) Repository access method (pick one)
   - Read-only repo access
   - Zip snapshot upload
   - Cannot provide → convert to Evidence Gap Pack
10) CI evidence (required unless Evidence Gap Pack)
   - CI system link
   - AND links/uploads for logs:
     a) one successful run
     b) one failed/partial run (if available)
   Confirmation checkbox:
   [ ] Logs are from real recent runs (not examples).

SECTION 4 — Minimal execution context (required)
11) Environments count
   - One
   - Staging + Production
   - More than two
12) Does production execution require explicit approval today?
   - Yes
   - No
   - Unsure
13) Most damaging failure mode (pick one)
   - Incorrect deploy
   - Incorrect experiment result
   - Incorrect model selection
   - Compliance / audit exposure
   - Customer harm
   - Other (1 sentence)

SECTION 5 — Speed-ups (bounded, optional)
14) What run artifacts exist today? (paths/filenames; bullet list, max ~10)
15) “Dangerous knobs” you know about (modes/configs/defaults; max 5 bullets)

SECTION 6 — Known concerns (optional but structured)
16) Experienced any of these? (multi-select)
   - Same run, different result
   - Can’t prove what ran weeks later
   - Silent config/mode drift
   - Unsafe defaults reaching prod
   - Review/compliance friction
   - None of the above
17) Anything else that matters (max 3 sentences)

SECTION 7 — Readiness / clock start (required)
[ ] All required inputs are complete.
[ ] I understand The 48-hour clock starts after you confirm completeness.
[ ] I understand no fixes are implemented in this engagement.
