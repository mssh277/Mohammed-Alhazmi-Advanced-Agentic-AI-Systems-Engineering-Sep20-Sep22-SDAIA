# Rafeeq Mini — Advanced Agentic AI Systems Engineering

Learner: `mssh277`. Synthetic, offline capstone for the September 20–22 SDAIA program.
Program reference: [SDAIA Academy](https://github.com/SDAIAAcademy).

## What it demonstrates
A bounded supervisor delegates to order and refund specialists using typed handoffs, scoped memory, current-policy retrieval and MCP tools. Ownership checks, approval above 500 SAR, idempotency, non-retried writes and redacted traces constrain execution. The model runs in deterministic stub mode on CPU.

## Evidence
- [Executed notebook](notebooks/Rafeeq_Mini_Capstone.ipynb) — C0–C29 and all 14 learner exercises.
- [Project report](reports/PROJECT_REPORT.md), [security assessment](reports/SECURITY_ASSESSMENT.md), and [evidence cards](reports/EVIDENCE_CARD.md).
- [Assessment results](reports/assessment_results.json), [dashboard](reports/monitoring_dashboard.png), and [export manifest](reports/submission_manifest.json).
- [Technical learner guide](docs/learner-guide.md).

## Reproduce
Use Python 3.12 and set `LLM_MODE=stub`. From the repository root:

```sh
python -m unittest discover -s tests/public -p "test_*.py" -v
python scripts/validate_submission.py --write-receipt
```

To regenerate artifacts, open the notebook in Colab, run C0–C29 in order, review C29, extract its clean ZIP, and separately save the completed notebook. Upload matching artifacts together. The learner submission workflow validates the package and publishes a cryptographic receipt.

## Changes and limits
Learner work includes all TODOs, bilingual MCP and memory/approval regressions, a Unicode role-spoofing local guard, and measured policy caching with result-equivalence checks. Two C27 dashboard references were corrected from `trace_redaction` to the existing `trace_redacted` gate. The C29 manifest now preserves the validator-required 14-of-14 safety flag, derived from actual learner checks. Assessment checks are retained.

All customers, orders and attacks are synthetic. Identity and approvals are simulated. The local injection rule is a teaching regression, not a production boundary. This is lab readiness, not production certification or an instructor grade. See [course use permission](COURSE_USE_PERMISSION.md).

### Export compatibility
The export includes two public comparison fixtures from the pinned course release, verified by SHA-256. Final packaging fetches them if absent; agent execution remains offline. Preflight validates completed submissions with the full submission validator; untouched teaching templates still require cleared outputs. Public tests and the learner workflow are retained. Use Colab or Linux for MCP stdio tests: the course transport uses POSIX pipe selection.
