# Equipment Maintenance Policy

- Version: 2.0
- Status: IN FORCE
- Effective date: 2023-06-01

This document is the authoritative source for assigning the
`Maintenance Tier` value in the plant equipment register.

## Scope

This policy applies to company-owned equipment only. Leased units are
maintained by the lessor and are not part of the register.

## Tier assignment rules

| # | Condition | Maintenance Tier |
|---|-----------|------------------|
| 1 | `age_years` is 7 or more | Overhaul |
| 2 | `age_years` is 4 to 6 | Major Service |
| 3 | `age_years` is 2 to 3 | Standard Service |
| 4 | `age_years` is below 2 | Baseline Check |

The `duty` field is not used for tiering under this version.
