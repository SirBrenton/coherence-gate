# 48-Hour Decision Pipeline Pre-Flight  
*Reproducibility • Safety Gates • Proof Pack Spec*  

**$2,500 fixed** • Delivered in **48 hours** (after complete inputs)

## Contents
- Who this is for  
- Outcome  
- Deliverables  
- Async-only (no calls)  
- Inputs required  
- Evidence Gap Pack  
- Not included  

## Who this is for
Teams whose pipeline outputs drive decisions (experiments, ML evals, analytics, pricing, risk) and are tired of:
- “same run, different answer” drift  
- wrong mode/config runs (and nobody can prove what happened later)  
- compliance/review blockers because outputs aren’t explainable or auditable  
- weeks later: “we can’t reproduce what ran, with what inputs/policy”

## Outcome

In 48 hours you’ll be able to answer — **with evidence**:

- Where nondeterminism or untracked configuration can enter  
- What can run “by accident” (unsafe modes, missing gates, silent defaults)  
- What each run must emit so results are explainable, reproducible, and reviewable  

This evaluates **only one declared critical path** and the evidence your CI already produces for it.

**This is not** a platform redesign or a code review.  
It is a forensic evaluation of what your pipeline can — and cannot — *prove* after a run, plus a spec to close the highest-risk proof gaps.

## Deliverables

You will receive three concrete artifacts:

### 1) Ranked Risk Register (top 5–10)
Each item includes:
- **Evidence reference** (file path / CI log excerpt)
- **Blast radius** (what can go wrong / who gets hurt)
- **Smallest fix** (lowest-effort guardrail)
- **Acceptance test** (what evidence must exist to prove it’s fixed)

### 2) Proof Pack v1 Spec (artifact contract + CI acceptance tests)
A portable spec for what every run should produce — and what CI must enforce — for example:
- `run_manifest.json` (what ran: mode/env/commit/runner)
- `input_fingerprint.json` / `manifest_fingerprint.json` (prove inputs without leaking data)
- `verdict.json` (explicit PASS/FAIL + reasons)
- `decision_table.csv` (diffable review surface for humans)
- CI checks: block unsafe modes by default + require a determinism canary

### 3) Go/No-Go + shortest path to Sprint-Ready
- **Yes:** a 5-day single-path hardening sprint is feasible if X is true  
- **No:** minimum readiness steps to make it feasible  

## Async-only (no calls)

This engagement is fully asynchronous. If your process requires meetings, it’s not a fit.

Communication happens via messages (and/or a shared doc). You’ll get:
- a short intake questionnaire (you answer once)
- one clarification round (I send questions; you reply in one batch)
- Final delivery  
- **48-hour clock begins only after inputs are complete**

## How to start (async)

1) Complete the intake (≈ 10 minutes):  
👉 https://github.com/SirBrenton/coherence-gate/blob/main/docs/intake.md  

2) Send repo access + CI logs in one message.  

3) When I reply **“Inputs complete,”** the 48-hour clock begins.

## Example output (what you receive)

Below is a representative excerpt. The real delivery includes 5–10 items like this, plus the full Proof Pack v1 Spec and a Go/No-Go summary.

### Risk Register item (example)
**RR-03 — Unsafe mode can run in CI**

- **Evidence:** `.github/workflows/pipeline.yml:L88` + CI log excerpt (linked)
- **Failure mode:** `MODE=unsafe` can execute without an explicit override
- **Blast radius:** wrong mode → wrong result shipped → review/audit failure
- **Smallest fix:** default-safe mode + explicit allowlist / override token
- **Acceptance test:** CI fails if `MODE=unsafe` without override token
- **Notes:** identifies where to add the guard (workflow gate vs runtime check)

### Proof Pack v1 Spec excerpt (example)
- **`run_manifest.json`:** commit SHA, runner image, mode/env, entrypoint, start/end timestamps
- **`input_fingerprint.json`:** hash + byte count for declared inputs (no data leakage)
- **`verdict.json`:** PASS/FAIL with explicit reasons + links to evidence
- **`decision_table.csv`:** diffable review surface (what changed, what ran, why it passed/failed)

## Confidentiality / handling

- Read-only access or a zip snapshot is sufficient.  
- You may redact sensitive values — this evaluates **proof gaps**, not business logic.  
- I retain only the delivered artifacts unless you request otherwise.

## Inputs required

- Repo snapshot (read-only access or zip is fine)
- CI evidence: logs for 2–3 runs (1 pass + 1 fail if possible)
- One critical path to evaluate (one entrypoint/job)
- Completed intake questionnaire (~10 minutes)

## If inputs are limited (Evidence Gap Pack)

If you cannot provide repo access **or** CI evidence, this converts to an **Evidence Gap Pack** (48 hours):
- what evidence is missing (and why it blocks reliability claims)
- Proof Pack v1 Spec + CI snippet examples
- readiness checklist for a successful hardening sprint

## Not included

- implementing changes in your repo
- making everything deterministic
- production rollout / org-wide instrumentation
- “guarantee no future drift” claims