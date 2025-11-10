# EquipRegistry

Asset registry for the plant's equipment. Registry data lives under
`registry/`; the procurement coordinators register newly acquired units on
their own branches, and the live register is maintained on Notion.

## Layout

- `registry/current/` — records of equipment that is already in the register
- `registry/new/` — newly registered records awaiting entry into the
  register (added by the coordinators on their registration branches; not
  merged to `main` yet)
- `policies/` — maintenance policy documents (the version in force and
  archived versions)
- `audits/` — historical audit exports, kept for compliance
- `coordinators/` — notes from the procurement coordinators

## Notes

- The maintenance policy was revised on 2026-01-01; see `policies/`.
- Tier values in `audits/audit_2025.csv` predate that revision.
