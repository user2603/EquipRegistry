# Equipment Maintenance Policy

- Version: 3.0
- Status: IN FORCE
- Effective date: 2026-01-01
- Supersedes: Equipment Maintenance Policy v2.0 (and every earlier version)

This document is the single authoritative source for assigning the
`Maintenance Tier` value in the plant equipment register. Tier values that
were assigned under any earlier version of this policy are outdated and must
be recomputed from the rules below. Historical tier values — including the
values already sitting in the register and the 2025 audit export — may be
used as format reference only, never as a rule source.

## Scope

The policy applies to every equipment record in the asset registry,
including leased units.

## Inputs

Classification uses these fields from the equipment record:

- `age_years` — completed years in service (integer, as recorded)
- `duty` — one of `Continuous`, `Intermittent`, `Standby`
- `ownership` — one of `Owned`, `Leased`

## Tier assignment rules

Evaluate the rules from top to bottom. The first matching rule sets the
tier; later rules are not applied.

| # | Condition | Maintenance Tier |
|---|-----------|------------------|
| 1 | `ownership` is `Leased` | Vendor Managed |
| 2 | `age_years` is 8 or more | Overhaul |
| 3 | `age_years` is 5 or more and `duty` is `Continuous` | Overhaul |
| 4 | `age_years` is 5 or more | Major Service |
| 5 | `age_years` is 3 or more and `duty` is `Continuous` | Major Service |
| 6 | `age_years` is 2 or more | Standard Service |
| 7 | otherwise | Baseline Check |

## Boundary interpretation

- "5 or more" includes age 5 exactly; the same inclusive reading applies
  to every other cut-off in the table.
- Rule order matters: a 9-year-old standby unit is Overhaul (rule 2),
  while a 5-year-old standby unit is Major Service (rule 4).

## Leased equipment

Under the retired v2.0 policy, leased units were kept off the register.
From 2026-01-01, leased units are part of the register and are always
tiered `Vendor Managed` (rule 1), regardless of age or duty.
