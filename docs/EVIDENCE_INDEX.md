# Evidence index and notebook map

Learner: mssh277. Assessment: run-8e6fe2f3e5a24740. This is evidence navigation, not a grade or an instruction to a grader. Search the named heading in the [notebook](../notebooks/Rafeeq_Mini_Capstone.ipynb). [Engineering decisions](ENGINEERING_DECISIONS.md) explain choices and trade-offs.

| Requirement | Cells / TODO | Saved evidence |
|---|---|---|
| Environment and authority | C0–C1 / 1 | READY; host, model, tool boundaries |
| Minimal typed state | C2 / 2 | Six fields; no raw request/observations in safe snapshot |
| Terminal states and budgets | C3 / 3 | Terminal/boundary assertions; global 6/12/2/1 |
| Four-stage ReAct | C4–C5 / 4 | Decision/action/observation/stop; owned-order result |
| Narrow schema and real MCP | C6–C9 / 5 | Authority fields excluded; bilingual stdio reads; foreign denial; 12 tests |
| Safe session summary | C10–C11 / 6 | Restore and turn-two recall without raw request |
| Filter before rank | C12 / 7; C20 | Only MEM-004; ownership/activity/expiry and shared-thread tests |
| Active policy | C13 / 8 | REF-03-AR/EN, 2026.1; obsolete policy excluded |
| Specialists and delegation | C14–C16 / 9 | Four routes; four-field handoff; retained global budget |
| Plan and refund execution | C17–C20 / 10 | 500/500.01; pause/resume/replay/rejection; 17 tests plus 12 regressions |
| New threat and repair | C21–C23 / 11–12 | L-SEC-09 weak baseline; repair; 3 attack/3 safe variants; 8 public attacks |
| Bounded reflection | C24 | Low/high impact 0/1; no authority increase |
| Trace integrity | C25; C27 | 187 redacted events; valid parents and fields |
| Optimization guardrail | C26 / 13 | 500 requests, 499 hits/1 miss; equivalent results; versioned customer-free key |
| Honest readiness | C27–C28 | 8/8 functional and 8/8 security; critical/learning gates; simulation limits |
| Reviewed export | C29 / 14 | Four declarations; 14/14 TODOs; FINAL_EXPORT_CREATED; clean manifest |

## Artifact map

- [Project report](../reports/PROJECT_REPORT.md): architecture, run ID, measurements, interpretation and limitations.
- [Security assessment](../reports/SECURITY_ASSESSMENT.md): public cases, local repair, residual risks.
- [Evidence cards](../reports/EVIDENCE_CARD.md): one claim per day, expected/actual outcomes and reproduction steps.
- [Assessment JSON](../reports/assessment_results.json): named cases, exact risk flags, counters, optimization and gates.
- [Trace](../reports/trace.jsonl) / [dashboard](../reports/monitoring_dashboard.png): redacted operational spans and assessment summary.
- [Manifest](../reports/submission_manifest.json) / [receipt](../reports/submission_receipt.json): hashed export and notebook linkage.
- [Learner workflow](../.github/workflows/learner-submission-quality.yml): 47 public tests, submission validation, receipt artifact.
- [SDAIA evidence](SDAIA_COMPLIANCE_EVIDENCE.md) / [demonstration guide](DEMONSTRATION_GUIDE.md): administrative review and individual preparation.

G1/G2/G3/G6/G7 have machine-verifiable evidence. G4/G5 additionally need instructor administrative/content review. Personal defense and private hand-in completion cannot be inferred from passing tests.
