---
name: local-data-audit
description: Inspect local tabular inputs, row meaning, keys, units, missingness, duplicates and join integrity before implementation. Do not use to silently clean data, build a full app, or send records to external services.
---

# Local Data Audit

Follow this kit's RULES.md, including its language policy, and the actual requirements. Treat original inputs as read-only.
Do not infer undocumented business meaning solely from statistical patterns.

## Procedure

1. Confirm supplied materials and the actual files to inspect.
2. For each sheet/table, describe row meaning, key columns, units, identifiers, and relationships to other tables.
3. Choose and justify reading method and scope. Do not always read every sheet or only the first sheet.
4. Actually calculate row counts, missingness, potential duplicates, type mismatches, range violations, and missing keys.
5. For joins, check before/after row counts, unmatched keys, and unexpected many-to-many expansion.
6. Distinguish leading zeros in IDs, empty values versus zero, dates/times, quantities, and units.
7. If correction/deletion is needed, show small before/after examples and result impact. Do not change meaning without approval.
8. List necessary tests and unresolved business questions.

## Output

- Input contract: source, row meaning, keys, units, and reading method.
- Observed issues and impact. State inspection scope before claiming no issues were found.
- Human decisions on correction/deletion policies and alternatives, prioritized to at most three.
- Small verification cases for core totals, row counts, key preservation, and similar invariants.

Do not blindly apply fillna(0), dropna(), or drop_duplicates().
Do not upload to the web, use external analysis services, or call external AI.
This is a procedure, not a guarantee that libraries are installed or that a file format can always be read.
