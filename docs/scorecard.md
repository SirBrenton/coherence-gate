# Pipeline Trust Scorecard (5 minutes)

This is a self-assessment for decision pipelines (CI, experiments, evals, analytics).
Score yourself quickly. If you score low, you have **proof gaps** (not opinions).

**How to score:** 0 = no / unknown, 1 = partial, 2 = yes  
(Max score = 20)

## Reproducibility & provenance
1) We can reconstruct **exactly what code/config** ran for any run 30+ days later. 0/1/2  
2) Identical reruns produce identical outputs (or we can prove why they differ). 0/1/2  
3) Every run emits a **run manifest** (commit SHA, config hash, runner, timestamps). 0/1/2  
4) Inputs are **fingerprinted** (data/model versions hashed) without leaking sensitive data. 0/1/2  

## Safety gates
5) Unsafe/ambiguous modes are **blocked by default** (not just documented). 0/1/2  
6) Promotion/production requires **explicit approval** and is provable later. 0/1/2  
7) “Dangerous knobs” are allowlisted and leave evidence when used. 0/1/2  

## Reviewability
8) Runs have an explicit **verdict artifact** (PASS/FAIL + reasons), not just exit codes. 0/1/2  
9) Two runs are **diffable** (what changed, what ran, why it passed/failed). 0/1/2  
10) A reviewer can audit a run without tribal knowledge or dashboard archaeology. 0/1/2  

## Score interpretation
- **16–20:** Rare. You likely have real provenance.  
- **10–15:** Common. You have material proof gaps.  
- **0–9:** High risk. You’re trusting dashboards and memory.

## Next step
If you scored **<16**, the Pre-Flight maps the proof gaps for **one critical path** and outputs:
- Ranked Risk Register
- Proof Pack v1 Spec
- Go / No-Go

Start intake: `docs/intake.md`
