# Migration Parity Testing: Eight Dimensions, Proven Weekly
**How to retire a security tool without discovering what it was quietly doing for you.**

The principle: parity is proven, never assumed, and every retirement is gated on evidence. When migrating between endpoint/EDR stacks, "it seems fine" is not a cutover criterion. Define parity as eight testable dimensions, score them weekly on one page, and require four consecutive all-green weeks before the retirement decision.

| # | Dimension | The test | Pass condition |
|---|---|---|---|
| 1 | Coverage | Device census from both consoles weekly; no agent removed until the new stack verifies that device | 100% visible, delta empty two consecutive weeks |
| 2 | Detection efficacy | Fixed safe simulation set (EICAR, ATT&CK-aligned Atomic Red Team scenarios) run identically on both stacks | No scenario the old stack catches that the new one misses |
| 3 | Alert fidelity | 30 days of dual-run alerts compared: FP rates, severity agreement, time-to-alert | New FP rate at or below baseline, no severity downgrades on true positives |
| 4 | Telemetry depth | Event-class inventory and retention window vs what your IR playbook depends on | Every playbook-required event class queryable for the stated window |
| 5 | Response actions | Timed live tests: isolate, kill, quarantine, live response, on every OS you run | Every playbook action executable in comparable time; gaps documented with compensations |
| 6 | Operational workflow | One full alert-to-ticket-to-report-to-evidence cycle | Runs without manual glue |
| 7 | Threat intelligence | Inventory what the outgoing tool's intel actually provided; stand up replacement feeds and triage enrichment | Feeds live, enrichment executing in triage |
| 8 | Evidence continuity | Auditor-facing artifacts produced entirely from the new stack | One month of evidence accepted into the archive |

Dimension 7 exists as its own line because bundled threat intelligence is the thing migrations quietly lose. Inventory it before you can lose it; a tier probe against the vendor API often answers in one call what the contract PDF hides.

Rules that make the scorecard honest: tuning without a failed pass condition does not reset the streak; a miss gets a root cause and a retest, never a shrug; and the export of the outgoing tool's data happens before cutover, because it vanishes with the contract.
