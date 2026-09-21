# SDAIA administrative and delivery evidence

Learner: mssh277. Audited 2026-09-21 against [pinned rubric](https://github.com/almiyead-rgb/rafeeq-agentic-ai-labs/blob/v0.9.0-rc3/docs/ASSESSMENT_RUBRIC.md) and [administrative requirements](https://github.com/almiyead-rgb/rafeeq-agentic-ai-labs/blob/v0.9.0-rc3/docs/SDAIA_ADMIN_REQUIREMENTS.md). Both match upstream main at 802bf760ef0c98006ef011fabff0fbf6bf7aadac.

| Requirement | Evidence / status |
|---|---|
| About description | Repository metadata identifies bilingual delivery support, bounded synthetic scope and completed, validated capstone outcome. |
| Professional README | [README](../README.md) covers idea, beginner setup/run/use, expected results, evidence and limitations. |
| Linked technical docs | [Architecture](ENGINEERING_DECISIONS.md), [notebook map](EVIDENCE_INDEX.md), [project report](../reports/PROJECT_REPORT.md), [security](../reports/SECURITY_ASSESSMENT.md), metrics and limits. |
| Meaningful preserved history | Setup README 68f4965; Day 1 progress fcc8633; Day 2 progress 5cb7ac0; final delivery 242209c; subsequent audit corrections preserve history. **Deviation:** no separate setup-progress commit; the log was initialized with Day 1. No retroactive checkpoint is claimed. Trainer decides credit. |
| Approved program title | English and Arabic titles in README. |
| Neutral Academy link | README links [SDAIAAcademy](https://github.com/SDAIAAcademy) without endorsement claims. |

## Technical delivery

Repository is public and non-fork. C0–C29 ran in CPU/stub Colab: 14/14 TODOs, 8/8 functional and 8/8 security. Run: run-8e6fe2f3e5a24740. The exact submitted commit must have successful **Learner submission quality** and its rafeeq-submission-receipt artifact. An older green run is insufficient.

The manifest hashes the clean export; the receipt binds notebook/manifest/assessment. ZIP, runtime checkpoints and private Drive URL are not published. [Evidence cards](../reports/EVIDENCE_CARD.md) give three reproducible claims. Traces contain operational events, not raw requests/private reasoning.

## Repair provenance

Official public tests, scripts/validate_submission.py and generated learner workflow are unchanged.

| Course-package defect | Disclosed repair |
|---|---|
| C27 nonexistent trace_redaction key | Use existing trace_redacted in both dashboard rendering branches; computations unchanged. |
| C29 replaces safety map, dropping required flag | Preserve learner_todos_14_of_14 derived from actual status validation and all 14 checks. |
| Embedded/export payload omits public test fixtures | Include two exact public JSON fixtures from v0.9.0-rc3; verify SHA-256. No hidden scoring inputs. |
| Template preflight rejects required submitted outputs | Manifest present: full unchanged submission validator. No manifest: retain cleared-template checks. Negative tests reject missing C29 and executed notebook without manifest. |

Fresh upstream validator independently accepts the submission; Linux public suite passed 47 tests. This does not replace instructor review of the disclosed repairs.

## Items requiring learner or trainer action

- GitHub email verification requires account-level evidence or learner confirmation; successful push alone is insufficient.
- Perform the [personal demonstration/defense](DEMONSTRATION_GUIDE.md).
- Submit public repository URL and exact green commit through the trainer's private form before its deadline; retain receipt. CI is not proof of hand-in.
- G4 administrative quality and G5 hygiene include human review. Historical setup/identity details require review; current-file checks do not erase history.
- Complete a private course evaluation only if a link is supplied; it has no project points. Stars/follows/forks/community participation are optional and ungraded.

No score, instructor approval, personal-defense completion or private hand-in is asserted.
