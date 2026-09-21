# Rafeeq Mini — Advanced Agentic AI Systems Engineering

**Public learner ID:** mssh277 · **Program:** SDA-AIE-311, September 20–22, 2026  
**البرنامج:** هندسة أنظمة الذكاء الاصطناعي التوكيلي المتقدمة  
Program reference: [SDAIA Academy](https://github.com/SDAIAAcademy). This is a learner project; no endorsement is claimed.

Rafeeq handles Arabic and English order-status and refund requests for the fictional delivery company Tawseel. It checks trusted customer ownership, retrieves active policy, delegates to a specialist and pauses refunds above 500 SAR for human approval. All identities, orders, approvals and refund writes are simulations; no real customer or payment service is connected.

## See Rafeeq in Action

**[Open the visual walkthrough →](docs/SEE-RAFEEQ-IN-ACTION/)** Three connected pictures with short explanations: the big picture, the execution flow, and a locally executed synthetic **740 SAR refund** followed through approval, creation and duplicate prevention. Each picture is available as a full-size PNG.

## Start here

1. Read the [executed notebook](notebooks/Rafeeq_Mini_Capstone.ipynb). C9 and C20 must pass; C29 must show FINAL_EXPORT_CREATED.
2. For a fresh learner attempt, open the [official course portal](https://almiyead-rgb.github.io/rafeeq-agentic-ai-labs/index.html), follow its pinned Colab link and choose **File → Save a copy in Drive**. This repository contains this learner's completed submission.
3. Select **Runtime → Change runtime type → Python 3 → CPU**. Keep LLM_MODE=stub; no API key, GPU, paid model or package installation is required for the baseline.
4. Run C0–C29 in order, completing/reviewing each exercise. Expect C0 READY, passing C9/C20 gates and passing security/readiness checks. Follow the [notebook map](docs/EVIDENCE_INDEX.md).
5. At C29 review the allowlist and four declarations before deliberately enabling final export. Extract the ZIP; separately save the completed notebook to notebooks/Rafeeq_Mini_Capstone.ipynb and add the three-day evidence card. Publish matching artifacts together. **Learner submission quality** must pass on the exact submitted commit.

The optional verification cell after C29 tests the extracted package if a sanitized notebook was uploaded to session storage. It explicitly skips when absent; GitHub Actions independently validates the published package.

## Run and use

On Linux with Python 3.12, clone or download/extract the repository, then run these commands from its root:

~~~sh
export LLM_MODE=stub
python scripts/run_demo.py
python -m unittest discover -s tests/public -p "test_*.py" -v
python scripts/validate_submission.py --write-receipt
~~~

The read-safe demo shows an English order lookup, Arabic high-value refund pause and injection refusal without refund writes. Expect RUN_DEMO=PASSED, 47 passing public tests and SUBMISSION_CHECK=PASSED. Use Colab/Linux for the course MCP stdio pipe transport; Windows is not the verified full-test platform. The [demonstration guide](docs/DEMONSTRATION_GUIDE.md) covers approval/resume and the learner attack.

## Verified evidence

Assessment run: **run-8e6fe2f3e5a24740**. These are synthetic test results, not a grade or production service level.

| Evidence | Observed result |
|---|---|
| Learner exercises | 14/14 |
| Functional / security cases | 8/8 / 8/8 |
| Unauthorized writes | 0 |
| Maximum steps / reflections | 4 / 1 |
| Redacted trace | 187 events; valid parent links |
| Policy cache, 500 requests | 7.825 ms before / 0.462 ms after; 499 hits / 1 miss; equal results |

- [Evidence index and notebook map](docs/EVIDENCE_INDEX.md) · [architecture and decisions](docs/ENGINEERING_DECISIONS.md)
- [Project report](reports/PROJECT_REPORT.md) · [security report](reports/SECURITY_ASSESSMENT.md) · [evidence cards](reports/EVIDENCE_CARD.md)
- [Assessment JSON](reports/assessment_results.json) · [dashboard](reports/monitoring_dashboard.png) · [trace](reports/trace.jsonl)
- [Manifest](reports/submission_manifest.json) · [receipt](reports/submission_receipt.json) · [SDAIA evidence](docs/SDAIA_COMPLIANCE_EVIDENCE.md) · [progress](LEARNING_PROGRESS.md)

## Limits and repair provenance

Identity/approvals are simulated; memory and idempotency are not durable production services. Stub tests do not measure live-model quality, provider latency or cost. The new local injection rule is a narrow regression, not comprehensive injection protection. See [production limitations](docs/ENGINEERING_DECISIONS.md#production-limitations).

Official tests, validator and learner workflow are retained. Disclosed package repairs fix C27's dashboard key, preserve C29's verified 14-of-14 flag, add two hash-verified public reference fixtures, and validate completed notebooks through the full submission contract in preflight. Final packaging fetches pinned fixtures if absent; agent execution remains offline. See [repair provenance](docs/SDAIA_COMPLIANCE_EVIDENCE.md#repair-provenance) and [course use permission](COURSE_USE_PERMISSION.md).
