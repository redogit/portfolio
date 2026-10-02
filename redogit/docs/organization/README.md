# redogit — file organization

Current workspace entry points live in [redogit/workspaces](../../../redogit/workspaces/README.md). Repositories and project authority remain independent; DnD is excluded from reorganization.

## Find an area

- [workspaces](../../workspaces/)
- [research/pnp](../../research/pnp/)
- [research/decision-field](../../research/decision-field/)
- [research/gsfl](../../research/gsfl/)
- [docs/navigation](../navigation/)
- [docs/coordination](../coordination/)
- [docs/orientation](../orientation/)
- [docs/updates](../updates/)
- [plan-authority](../../plan-authority/)

## Migration record

107 baseline files moved; 65 retain their source locations. [migration.json](migration.json) accounts for each baseline path and records protected identities and retained exceptions. [layout.json](layout.json) describes current areas.

Historical receipts and source locks keep their original bytes, dates, and claim ceilings. Their recorded paths remain historical locators: use the baseline revision and the migration record to find a current file. Current navigation is not historical-source rewriting.

## Retained interfaces

- Root contracts, approval records, and published/static source paths retain their required interfaces.
- Coupled implementation, tests, audit tools, and fixtures stay together when moving one would disturb their pinned identity or runtime contract.
- Deeper role folders are used where dependencies can be preserved.
- No source or configuration in DnD was changed.

## Verification

[verification.json](verification.json) records commands, results, preserved identities, and platform limitations. Across the primary suites, 740 tests pass and two existing optional Z3 checks skip. Probes, frozen audits, game/static checks, current navigation, and live Garden requests also pass. One inherited SONG placeholder remains unchanged.

The independent review findings were addressed and rechecked. Changes remain local; current GitHub URLs describe the reviewed layout and become available remotely when these commits are published. Hosted projects were not created.
