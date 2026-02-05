# Pipeline Trust Scorecard (5 minutes)

A self-assessment for **decision pipelines** (CI, experiments, evals, analytics) where outputs drive real choices.

This isn’t about “best practices.” It’s about **proof**:
Can you defend what happened after a run… **weeks later**?

**Scoring:** 0 = no / unknown, 1 = partial, 2 = yes  
**Max score = 20** (do it fast; don’t overthink)

---

## Reproducibility & provenance (proof you can reconstruct a run)
1) We can reconstruct exactly what code + config ran for a run **30+ days later**. (0/1/2)  
2) Identical reruns produce identical outputs **or** we can prove why they differ. (0/1/2)  
3) Every run emits a **run manifest** (commit SHA, config hash, runner/image, timestamps). (0/1/2)  
4) Inputs are **fingerprinted** (data/model/version IDs hashed) without leaking sensitive data. (0/1/2)

## Safety gates (proof you prevent “accidents”)
5) Unsafe/ambiguous modes are **blocked by default** (not just documented). (0/1/2)  
6) Promotion/production requires **explicit approval** and is provable later. (0/1/2)  
7) “Dangerous knobs” are allowlisted and leave evidence when used. (0/1/2)

## Reviewability (proof a human can audit quickly)
8) Runs have an explicit **verdict artifact** (PASS/FAIL + reasons), not just exit codes. (0/1/2)  
9) Two runs are **diffable** (what changed, what ran, why it passed/failed). (0/1/2)  
10) A reviewer can audit a run without tribal knowledge or dashboard archaeology. (0/1/2)

---

## Interpretation
- **16–20:** Strong. You likely have real provenance + gates.  
- **10–15:** Common. You have material proof gaps (you can ship, but can’t *defend*).  
- **0–9:** High risk. You’re trusting dashboards and memory.

**Rule of thumb:** If you scored **<16**, you’re missing at least two foundational proofs (manifest + inputs + verdict + diffability). That’s where “same run, different result” turns into decision chaos.

---

## What to do if you scored low (free)
Pick **one critical path** and make sure it can emit, per run:
- `run_manifest.json` (what ran)
- input fingerprints (what it used)
- `verdict.json` (why it passed/failed)
- a diffable surface (what changed between runs)

If you can’t produce those today, you don’t have a trust problem — you have an **evidence problem**.

---

## Next step (forensic, evidence-backed)
If you want a **forensic readout on one critical path** (48 hours, async), the intake is here: **[`docs/intake.md`](docs/intake.md)**
