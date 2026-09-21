# Engineering decisions and architecture

Learner: mssh277. Evidence run: run-8e6fe2f3e5a24740. This explains the implementation; it does not certify an individual oral defense.

~~~mermaid
flowchart TD
 Host[Trusted host: identity, approval, limits] --> Boundary[Deterministic tool boundary]
 Request[Untrusted request] --> Guard[Input guard]
 Guard --> Supervisor[Thin supervisor]
 Supervisor --> Orders[Orders specialist]
 Supervisor --> Refund[Refund specialist]
 Orders --> Boundary
 Refund --> Boundary
 Policy[Current versioned policy] --> Refund
 Memory[Owner, active, expiry filters before rank] --> Supervisor
 Boundary --> Output[Output guard and terminal result]
 Supervisor --> Trace[Redacted operational trace]
 Boundary --> Trace
~~~

## Authority outside model text

Model-visible arguments request an operation; they do not authorize it. The host supplies identity separately, and the server validates ownership and approval. JSON schemas constrain argument shape but cannot authenticate a customer. C6 excludes identity, amount and approval from the model-visible tool schema. C8 performs bilingual MCP stdio reads and denies foreign ownership without disclosure. SEC-01 covers cross-customer refusal; SEC-02/08 prevent asserted approval/privilege from authorizing high-value writes.

**Trade-off:** deterministic checks duplicate some planning work but preserve the boundary when a planner or retrieved text is wrong. Production needs authenticated, integrity-protected host context.

## Minimal state and budgets

C2 keeps route, lifecycle and counters; safe snapshots exclude raw requests/observations. C3 enforces global limits of 6 steps, 12 transitions, 2 handoffs and 1 reflection. Terminal states stop; delegation shares the remaining allowance. C20 tests representative routes; C27 observed 4 steps and 1 reflection at most.

**Trade-off:** difficult legitimate requests may escalate. Representative workload/cost evidence is needed before changing bounds.

## Pattern choices linked to evidence

| Pattern | Why / trade-off | Cell → case → metric → result |
|---|---|---|
| ReAct | A read needs an observation. Additional observations consume budget; log operational stages, not private reasoning. | C4–C5 → owned TW-26018 → decision/action/observation/stop → out_for_delivery, completed |
| Plan-and-Execute | Ordered refund preconditions and human pause/resume are explicit. Stale plans require tool-boundary revalidation. | C17–C20 → TW-26017 → writes before/after/replay/rejection = 0/1/0/0 → assertions passed |
| Bounded Reflection | One review for high-impact paths, none for simple reads. Review adds work but cannot grant authority. | C24 → low/high impact → reflection counts 0/1 → bounded; SEC-08 still pauses for approval |

## Memory, policy and handoff

C11 summarizes operational outcome/order/route without raw request. C12 filters trusted owner, active status and expiry **before** ranking. Ranking first could expose or let unauthorized records influence selection. C20 returned only MEM-004 for CUST-011, rejected records expiring at the current instant and proved shared-thread customer isolation.

C13 selects active policy 2026.1 by locale/category and excludes the obsolete 300 SAR rule. C16 transfers only target, order_id, locale and task. **Trade-off:** strict scope/expiry may reduce recall; escalation is safer than borrowing another customer's context. Production needs governed policy lifecycle and durable isolated storage.

## Approval and idempotency

C18 checks ownership → no prior refund → delay greater than two days → amount. 500.00 SAR is eligible; 500.01 requires approval. C19 distinguishes a prior business refund from replay of the same approved operation. Deterministic idempotency avoids a duplicate effect; failed writes are not automatically retried. Approval cannot override rejection or ownership mismatch.

**Trade-off:** a lost response may require human reconciliation. Production requires durable idempotency, atomic transactions and authoritative approval audit records.

## New threat and guard repair

L-SEC-09 uses compatibility Unicode and unusual whitespace to combine role spoofing with approval bypass. C23 exposes a deliberately weak **local** guard, then normalizes Unicode/whitespace and detects the combined role-override/bypass pattern. Three attack variants are blocked and three benign inputs remain allowed. The eight public attacks still pass. Runtime approval checks are independent of this local exercise.

**Residual risk:** lexical rules can miss unseen paraphrases/scripts or misclassify quotations. This is a narrow regression; enforce authority outside model text and expand adversarial and benign evaluation before deployment.

## Measured optimization

C26 caches current policy IDs by locale, category and active version, with at most eight entries. 500 requests measured 7.825 ms uncached and 0.462 ms cached, 499 hits / 1 miss. Result equivalence is asserted; 499 underlying operations are saved. No customer data enters the key.

**Trade-off:** caching exchanges repeated work for storage and stale-policy risk. Version/invalidate keys, bound entries and exclude customer data. A microbenchmark is not production percentile evidence or a general speed guarantee.

## Production limitations

| Lab property | Required before production |
|---|---|
| Synthetic identity and approval | Real authentication/authorization, signed audited approval, separation of duties |
| Local memory and idempotency | Durable isolated storage, atomicity, concurrency and crash/replay tests |
| Deterministic stub and finite cases | Live-model, adversarial/benign, load and provider-failure evaluation |
| Local redaction | Classification, retention/access controls and response monitoring |
| Fixed policy version/cache | Governed publication, revocation and invalidation |
| Synthetic timing and zero charge | End-to-end cost/latency measurement and production safety/SLA review |

Live-model accuracy, production throughput, provider cost and real-service reliability are **Not measured**. See [evidence index](EVIDENCE_INDEX.md) and [project report](../reports/PROJECT_REPORT.md).
