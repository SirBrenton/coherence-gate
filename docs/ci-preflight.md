### 48-Hour Decision Pipeline Pre-Flight
(Repro + Safety + Proof Pack Spec)
$2,500 fixed • Delivered in 48 hours (from receipt of complete inputs)

## Who this is for
Teams whose pipeline outputs drive decisions (experiments, ML evals, analytics, pricing, risk) and are tired of:
- “same run, different answer” drift
- wrong mode/config runs (and nobody can prove what happened later)
- compliance/review blockers because outputs aren’t explainable or auditable
- weeks later: “we can’t reproduce what ran, with what inputs/policy”

## Outcome (why you’d pay)
In 48 hours you’ll be able to answer — with evidence:
1) where nondeterminism or untracked configuration can enter
2) what can run “by accident” (unsafe modes, missing gates, silent defaults)
3) what each run must emit so results are explainable, reproducible, and reviewable

This is not a platform redesign or a code review.
It’s a forensic evaluation of what your pipeline can and cannot prove after a run — plus a spec to close the highest-risk proof gaps.
It does not require new business logic or domain knowledge: it evaluates whether the existing system emits enough evidence to defend its decisions.

## What you get (deliverables)

1) Ranked Risk Register (top 5–10)
Each item includes:
- evidence reference (file path / CI log excerpt)
- blast radius (what can go wrong / who gets hurt)
- smallest fix (lowest-effort guardrail)
- acceptance test (what evidence must exist to prove it’s fixed)

2) Proof Pack v1 Spec (artifact contract + CI acceptance tests)
A portable spec for what every run should produce — and what CI must enforce — e.g.:
- run_manifest.json (what ran: mode/env/commit/runner)
- input_fingerprint.json / manifest_fingerprint.json (prove inputs without leaking data)
- verdict.json (explicit PASS/FAIL + reasons)
- decision_table.csv (diffable review surface for humans)
- CI checks: block unsafe modes by default + require a determinism canary

3) Go / No-Go + shortest path to Sprint-Ready
- “Yes: a 5-day single-path hardening sprint is feasible if X is true.”
or
- “No: here are the minimum readiness steps to make it feasible.”

## Async-only engagement (no calls)
This engagement is asynchronous-only and does not include calls. If your process requires meetings, it’s not a fit.
Communication happens via messages (and/or a shared doc). You’ll get:
- a short intake questionnaire (you answer once)
- one clarification round (I send questions; you reply in one batch)
- final delivery 48 hours after inputs are complete

## What I need (inputs)
- Repo snapshot (read-only access or zip is fine)
- CI evidence: logs for 2–3 runs (1 pass + 1 fail if possible)
- One critical path to evaluate (one entrypoint/job)
- Completed intake questionnaire (10 minutes)

## If access is limited (Yellow/Red protection)
If you can’t provide repo + CI evidence, this converts to an Evidence Gap Pack (48h):
- what evidence is missing (and why it blocks reliability claims)
- Proof Pack v1 Spec + CI snippet examples
- readiness checklist for a successful hardening sprint

## Not included
- implementing changes in your repo
- making everything deterministic
- production rollout / org-wide instrumentation
- “guarantee no future drift” claims
