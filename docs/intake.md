# 48-Hour Decision Pipeline Pre-Flight — Intake (v1.3)

**Purpose:** Collect the minimum inputs to run the forensic pre-flight.

**Hard rule:** If you can’t provide **repo access/zip AND CI evidence (2–3 runs)**, this becomes an **Evidence Gap Pack**.

---

## How to submit (one message)

Send **one message** containing:

- ✅ Completed intake (copy/paste block below)
- ✅ Repo access method (read-only access **OR** zip snapshot)
- ✅ CI evidence for **2–3 runs** (links or exports):
  - 1 successful run
  - 1 failed/partial run (if available)

**CI evidence =** run links + logs/artifacts for specific run IDs (screenshots only if logs aren’t accessible).

I reply with **“Inputs complete”** (clock starts) or **“Inputs incomplete → Evidence Gap Pack”** (and what’s missing).

---

## Copy/paste response block

### **Acknowledgement (required) — Confirm:**
- This is a forensic diagnostic, not implementation
- Engagement may conclude **Go / No-Go**
- Async-only (no calls)
- The 48-hour clock starts **after** completeness is confirmed

```text
1) OWNERSHIP
Name:
Role/Title:
Company (if different than profile):
Delivery email:
Access level: repo/CI access / zip+logs / delegate (needs approval)

2) SCOPE LOCK
Pipeline type:
Pipeline purpose (2 sentences):
ONE critical path to evaluate (entrypoint/job name):

3) EVIDENCE ACCESS
Repo access method (read-only or zip):
CI system:
Successful run (link + run ID):
Failed/partial run (link + run ID, if available):
How to access logs/artifacts (links/exports):

4) MINIMAL EXECUTION CONTEXT
Environments: one / staging+prod / >2
Prod requires explicit approval today? yes / no / unsure
Most damaging failure mode (pick one):
- Wrong decision shipped (false PASS)
- Blocked shipping (false FAIL)
- Can’t reproduce weeks later (audit failure)
- Unsafe mode ran (policy breach)
- Silent config/data drift
- Other (1 sentence)

5) OPTIONAL SPEED-UPS
Existing run artifacts (paths/filenames):
Known “dangerous knobs” (modes/configs/defaults):

KNOWN CONCERNS (optional) — multi-select:
- Same run, different result
- Can’t prove what ran weeks later
- Silent config/mode drift
- Unsafe defaults reaching prod
- Review/compliance friction
- None of the above

Anything else that matters (max 3 sentences):

Clock start confirmation (required)

“I confirm this message includes the completed intake + repo access/zip + CI run links. I understand this is diagnostic only and no fixes are implemented in this engagement.”
```