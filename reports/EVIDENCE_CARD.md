# Required evidence cards

Public learner ID: `mssh277`  
Assessment run: `run-8e6fe2f3e5a24740`  
Final clean run date (UTC): 2026-09-21

## EV-D1 — Core and tools

- **Claim:** Typed state, bounded execution and MCP ownership checks preserve the training boundary.
- **Cell/gate:** C2–C9 / C9_DAY1_GATE.
- **Case/metric:** Public state, tool-scope, MCP and termination suites; bilingual owned-order reads and foreign-order denial.
- **Expected:** All 12 public tests pass; foreign access discloses no order and causes no write.
- **Actual:** 12/12 tests passed; all five learner checks passed; bilingual MCP assertions passed.
- **Status:** PASS.
- **Artifact:** `notebooks/Rafeeq_Mini_Capstone.ipynb`, C8–C9 saved output.
- **Reproduce:** 1. Open notebook with CPU/stub mode. 2. Run C0–C9 in order. 3. Inspect the gate and MCP assertions.
- **Safe observation:** Trusted fixture ownership controls reads; budgets bound execution; no real service is contacted.

## EV-D2 — Memory and orchestration

- **Claim:** Memory is customer-scoped and high-value refunds require approval without duplicate writes.
- **Cell/gate:** C11–C20 / C20_DAY2_GATE.
- **Case/metric:** MEM-004; synthetic TW-26017 approval/replay/rejection; 17 Day 2 tests and 12 Day 1 regression tests.
- **Expected:** Only eligible owned memory; refund writes 0 before approval, 1 after, 0 on replay and 0 after rejection.
- **Actual:** Expected counts matched; shared-thread isolation and expiry boundary passed; 17/17 plus 12/12 tests passed.
- **Status:** PASS.
- **Artifact:** `notebooks/Rafeeq_Mini_Capstone.ipynb`, C19–C20 saved output.
- **Reproduce:** 1. Run C0–C10. 2. Run C11–C20. 3. Inspect DAY2_ADDITIONAL_ACCEPTANCE and all gate flags.
- **Safe observation:** Four supervisor routes passed, global budgets held, memory leakage count was zero.

## EV-D3 — Security and evidence

- **Claim:** The new local threat regression is repaired while canonical security, tracing and export contracts remain passing.
- **Cell/gate:** C21–C29 / C29_EXPORT_SAFETY_CHECK.
- **Case/metric:** L-SEC-09, SEC-01–SEC-08, EVAL-AR-01–04 and EVAL-EN-01–04.
- **Expected:** Weak guard exposed; repaired local guard blocks the attack; 8/8 security and 8/8 functional; zero unauthorized writes; all 14 TODOs and export checks pass.
- **Actual:** Expected results matched; 187 redacted trace events; max steps 4 and reflections 1. Cache: 7.825 ms before / 0.462 ms after for 500 lookups, 499 hits / 1 miss, identical results.
- **Status:** PASS.
- **Artifacts:** `reports/assessment_results.json`, `reports/SECURITY_ASSESSMENT.md`, `reports/submission_manifest.json`, and notebook C21–C29.
- **Reproduce:** 1. Restart and run C0–C29 in order. 2. Review the export. 3. Extract matching artifacts and save notebook. 4. Run `python scripts/validate_submission.py --write-receipt`.
- **Safe observation:** Unicode normalization defeats this role-spoofing pattern; three malicious variants and three safe inputs pass. This local rule is not a production injection defense. Cache measurements apply only to this run.

## Redaction review

- [x] Only GitHub username identifies the learner in these cards.
- [x] All customer/order/memory identifiers are supplied synthetic fixtures.
- [x] No credential, cookie, private link or environment value appears here.
- [x] No real customer, employee, payment, support or trainee data appears here.
- [x] No code solution, instructor note, hidden test or private reasoning is copied into these cards.
- [x] Every declared PASS corresponds to the saved final run.

Prepared from execution evidence with assistant support. Personal explanation and instructor assessment remain unverified.
