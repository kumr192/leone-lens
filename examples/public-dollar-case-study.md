# Worked Example — IBMSI Public Dollar Command Center

A real build run under Leone Lens, end to end. Use it as the pattern: copy the shape, not the answers. Facts below are from the build's own test and evaluation records (Oracle Fusion 27A hackathon pod, November 2026).

## 1. The outcome (one sentence, named owner, measurable)

**Prove every public dollar — available, eligible, claimed, balanced.**

- Owner: the builder, who also answers for the demo and the manual test gate
- Measure: every figure in every answer traces to a real Fusion record, or is marked NOT PROVEN
- Not the outcome: "build a grants chatbot" — rejected at question 1, per `references/first-questions.md`

## 2. Data path proven before build

Each read was tested on the target instance, with the build user, before any workflow was designed:

- Grants awards, claims, and balances — real records returned
- AP invoices and invoice lines — real records returned
- Purchase orders (1005342, 1005334) — real records returned through the Studio read even where screens hid them
- GL journal hop in the trace — NOT PROVEN on this pod; carried as a platform ask, never faked
- Budget balances read — blocked by a security policy for the build user; marked KNOWN LIMIT, never demoed live

Rule applied: propose only outcomes with a proven data path. The rest are research items.

## 3. Envelope written before autonomy

- Policies: never approve money; never invent an amount; no evidence = NOT PROVEN
- Fixed SOP order for the health check, so every run is comparable
- Autonomy dial: all reads = Research/Assist; the one write (add an invoice line) = governed action, native Human Approval pause, read-back after approval
- Guardrails inside the action: duplicate lines refused, validated invoices refused, refusal text states plainly that nothing was written

## 4. Build shape — skills under one outcome

Nine workflows sit under the single Commander outcome as skills (health check, grant money, rescue, variance trace, purchase order check, the approval-gated invoice-line action, and supporting reads). New questions became new skills. No new agent, no new outcome.

The Variance Trace skill chains award → claim → AP invoice → PO. Each hop carries record evidence and a STATE line. A hop is PROVEN only on a shared key. The GL journal hop is printed as NOT PROVEN, with the platform ask named.

## 5. Outcome Receipt (shape used on every run)

Per leg of the run:

- **Authority** — the policy or approval the leg acted under
- **Evidence** — the real records read, with identifiers
- **Decision** — what the evidence supports
- **Action** — action taken, or the action handed to a person
- **Result** — PROVEN or NOT PROVEN

Plus, per item: a STATE line, and ranked RECOMMENDED ACTIONS IN ORDER.

## 6. Tests and evals — the completion gate

- 35/35 workflow run-page rounds passed; 21/21 agentic-app section rounds passed; final verification 11/11
- Eval medians, before → after the Leone audit fixes:
  - Commander: 0.55 → 0.85 → 0.90 (after the receipt upgrade)
  - Grant Money: 0.925 → 0.975
  - Rescue: 0.775 (unchanged — reported as-is, not rounded up)
  - Purchase Order Check: 0.90
- Arithmetic rule proven in the audit: counts and sums come from the records output count value and deterministic nodes, never from the model counting in language

## 7. Known limits — named, not hidden

- Fusion Claw outcomes on this pod return only a "Started" acknowledgement, with no result-retrieval path. Classified FAILED / KNOWN LIMIT in the test record, never PASS. The fix belongs to the platform owner.
- Budget balances read blocked by security policy for the build user.
- The builder's own manual test run remains the final gate. The build is not called complete until that run passes.

## 8. What Leone Lens changed on this build

1. One outcome replaced a list of separate agents.
2. The receipt upgrade (Authority, Evidence, Decision, Action, Result per leg) lifted the Commander eval median from 0.85 to 0.90.
3. The arithmetic audit removed model counting from every prompt.
4. The autonomy statement was written into the app and the Claw goals, so a reviewer can see the dial settings without asking.
5. Platform limits were reclassified from quiet gaps to named KNOWN LIMIT items with owners.

**Status of this example: COMPLETED as a build record. The project's final gate — the owner's manual test run — stays open until he runs it.**
