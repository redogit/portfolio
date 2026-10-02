# Project workspaces first, then deeper repository organization

Status: written design for owner review; no repository files have been moved.

## Intended outcome

The owner requested both easier navigation and a deeper physical file layout.
The starting point is eight focused project workspaces over the existing
checkouts. Later physical reorganization is limited to `redogit`,
`Other-Projects-`, and `conscience64`. DnD is excluded from this organization
task. A person should be able to find a project, its implementation,
current instructions, tests, recorded results, and historical sources without
searching a large mixed directory or confusing a navigation index with project
authority. Preserve project identities, behavior, provenance, and user files.

The four repositories remain independent. First establish workspace entry
points and scopes without moving source files or creating new GitHub
repositories. Any later physical migration is divided into three packages,
starting with `redogit`; each package must pass its own checks before the next
begins. This is an organization task, not a dependency upgrade,
research audit, project merge, release, or deployment.

## First stage: eight focused project workspaces

| Workspace | Main scope |
| --- | --- |
| RMAL | Language, compiler, native integrations; DnD references only during organization |
| P vs NP / Dean | Solvers, probes, proofs, and evidence |
| Hodge | Correspondences, computations, and research records |
| Conscience64 | Platform, recovery, navigation, analytics, and local model tooling |
| Games | MMO World, NEON//VEIL, and other game projects |
| Language and carriers | GSFL, SPrime, compression, Cross-Carrier, and related labs |
| Archives and knowledge | Human Expression Archive, Knowledge Garden, Orbit, and source recovery |
| Portfolio | Cross-project navigation, coordination, and planning |

The [workspace grouping manifest](2026-09-30-repository-organization/workspace-groups.json)
records existing repository paths and entry points for these groups. This is
reviewable organization metadata, not an access-control mechanism or a claim
that eight hosted projects have been created. No hosted-project creation tool
is available in this chat. A future hosted project can select the relevant
existing repositories and use its listed paths to focus its startup context.
Shared paths may appear in multiple workspace contexts without changing
ownership or duplicating files.

Each workspace entry point should state purpose, current source locations,
relevant run/test instructions, current-work notes, and project-specific
boundaries. Use existing source directories initially; physical migration
comes after this separation is useful and its dependencies have been reviewed.

### DnD constraint from the owner

Do not move, rename, edit, remove, or add organizational files in DnD. It is
reference-only for this task. The owner permits future additions only when
they relate specifically to RMAL or an existing DnD project area; that exception
does not authorize generic workspace metadata, unrelated projects, rewrites,
or any additions in this organization task. No DnD addition is planned.

If a proposed move elsewhere requires an edit inside DnD, retain the relevant
original path or provide compatibility in the other repository. Defer a move
that cannot meet this constraint; never patch DnD to complete this migration.

## Inspection and concrete inventory

The current committed checkouts contain 1,983 tracked files:

| Repository | Tracked files | Candidate moves | Retained paths |
| --- | ---: | ---: | ---: |
| redogit | 169 | 125 | 44 |
| Other-Projects- | 737 | 669 | 68 |
| conscience64 | 709 | 91 | 618 |
| DnD | 368 | 0 | 368 |

The companion [file-by-file proposal](2026-09-30-repository-organization/file-layout-proposal.json)
records every inspected source path, proposed destination, treatment, reason,
content hash, and baseline repository revision. It does not execute moves.
Candidate paths must pass dependency and preservation checks before use.
Files created by this design are additional to the inspected baseline.

`redogit` has 136 root files, including 93 Markdown files. Other-Projects-
already has recognizable projects, but several mix documents, tests, scripts,
schemas, and results. Conscience64 has established runtime and public-source
paths that are explicit contracts. DnD already follows a useful CMake layout.

Observed dependencies include:

- The Dean articulation probe loads the parity repair probe with
  `Path(__file__).with_name(...)`. Keep both in the same probes directory.
- Conscience64's public builder reads `public-testbed/`,
  `play/public-index.html`, `play/musilanguage/`, and `play/neon-veil/`.
  These paths and approval records remain stable.
- CI path filters, commands, package scripts, CMake install lists, and current
  indexes name files directly and must be updated when their targets move.
- Source locks, copied provenance, corpus encodings, and historical receipts
  carry identities that cannot be rewritten to imply a new validation run.
- `docs/dream-to-action/`, `docs/about.html`, and `docs/recent-work.html` in
  redogit are selected publication sources and remain in place.

## Approaches considered

1. Add indexes while retaining all physical paths. This helps discovery but
   does not address the requested deeper layout.
2. Group by project/topic, then by file role, and preserve paths that form
   runtime or provenance contracts. Recommended: this directly addresses the
   request with explicit, testable migration boundaries.
3. Force every eligible repository into identical `src`, `docs`, and `tests` roots.
   This would flatten independent projects, require a large runtime migration,
   and obscure copied provenance and approved publication source families.

## Shared layout rules

- First level: repository purpose or project category.
- Second level: independent project or research topic.
- Third level: role, such as `docs`, `src`, `tests`, `tools`, `schemas`,
  `contracts`, `fixtures`, `evidence`, or `history`.
- Fourth level where useful: an existing subsystem, explicit version, or
  recorded run identifier. Do not create an empty template for every project.
- Keep existing project names and dated filenames during this migration.
  Display labels may be friendly; stable names should remain traceable.
- A date alone does not make work obsolete. Use source-declared status to
  distinguish current work, successors, preserved predecessors, and review.
- Keep experimental output under the owning project's `evidence/runs/<id>`.
  New temporary builds and generated outputs use ignored directories or the
  existing external `/workspace/.cloud-build` location.
- Preserve meaningful internal layouts such as MLIR's `include/lib/tools/test`
  and DnD's `include/src/spec/examples/tests`; role conventions do not require
  renaming toolchain-specific directories.

## Later migration A: redogit

```text
redogit/
  README.md                         main entry point
  REDOGIT.md                        discoverable repository rules
  COMMERCIAL_ACCESS_POLICY.md
  redogit.json                      current repository contract
  research/
    pnp/
      README.md                     current topic navigation
      dean/
        docs/                       Dean research records
        probes/                     related executable probes together
        contracts/                  declared probe/run contracts
        evidence/
          recorded/                 recorded result files
          runs/<existing-run-id>/   intact multi-file recorded runs
      carriers/
        docs/
        probes/
        evidence/recorded/
      handoffs/                     synchronization records
    decision-field/
      README.md
      docs/
      records/
    gsfl/
      README.md
      docs/
  docs/
    navigation/                     current project/work indexes
      history-playground/
    coordination/                   cross-project contracts and alignment
    orientation/                    terms, language, and method introductions
    updates/                        dated updates with explicit status
    history/navigation/             predecessor indexes
    superpowers/                    existing specs and plans
    dream-to-action/                stable publication source
    about.html                      stable publication source
    recent-work.html                stable publication source
  plan-authority/                   existing independent data/interface
  tools/
  tests/
  .github/
```

Existing browser-facing root HTML and the data/contracts those routes consume
remain compatible. The proposal retains them until a separately validated
route migration is necessary. Schemas and public approval metadata do not
move merely to minimize the root-file count.

Concrete examples:

- `PNP_DEAN_ARTICULATION_2026-09-30.md` becomes
  `research/pnp/dean/docs/PNP_DEAN_ARTICULATION_2026-09-30.md`.
- Both `PNP_DEAN_ARTICULATION_PROBE_2026-09-30.py` and
  `PNP_DEAN_PARITY_REPAIR_PROBE_2026-09-30.py` become siblings in
  `research/pnp/dean/probes/`.
- `PNP_DEAN_ARTICULATION_RUN_2026-09-30/` moves intact under
  `research/pnp/dean/evidence/runs/`.
- `WORK_INDEX.md` becomes `docs/navigation/WORK_INDEX.md`, with current
  references and browser navigation updated accordingly.

## Later migration B: Other-Projects-

```text
Other-Projects-/
  README.md
  projects/
    research/
      Blank Page Lab/
      Context Discovery/
      Decision Field Operator Lab/
      Hodge Span Lab/
      P versus NP Repair Lab/
      S1 Models Lab/
      S1024 Compression Lab/
      SPrime Search/
    languages/Generalized Semantic Fitting Language/
    cooperation/ChatGPT and Conscience/
    tools/
      Hodge Compass API/
      knowledge-garden/
    archives/Human Expression Archive/
    games/
      Decision Field MMORPG/
      RMAOS MiniGX/
    mobile/w114-perturbation-lab/
  docs/
    navigation/bridges/
    superpowers/
  evidence/                         existing shared cooperation evidence
  tools/
  .github/
```

Project internals gain role directories where they are currently flat:
Python implementation under `src/`, project documentation under `docs/`,
tests under `tests/`, audit entry points under `tools/`, and named schemas
under `schemas/`. Imports, module search paths, and data-relative access must
be adapted together; browser and package entry points retain documented
interfaces. Existing nested code,
fixtures, versions, and history stay together. The concrete manifest records
these candidates, rather than claiming every project must have every folder.

Moving project homes requires updating active navigation and current CI and
runtime references across the three eligible repositories in the same migration
package. DnD consumers must keep working without edits to DnD. Existing public
source links outside these repositories cannot all
be rewritten. Historical commit permalinks continue to locate their original
paths; the migration map supplies the current location.

## Later migration C: conscience64

Keep the established `play`, `public-testbed`, `research`, `analytics`,
`coordinate-space`, `image-society`, `navigation`, `knowledge`, `infra`, and
`history` homes. These already separate independent purposes.

Within `research/hodge`, propose `docs/`, `src/`, `tests/`, and
`evidence/recorded/` for the currently mixed files, with the project README,
claim matrix, and working-state snapshot retained at their current entry paths.
Move eligible root-level architecture and operation documents under
`docs/architecture/` and `docs/operations/`. Apply the same internal-role
organization to eligible project documentation and tests in analytics,
coordinate-space, and image-society.

Preserve browser script and asset paths, encoded data/corpus files, historical
source-ingress trees, public approval records, and curated projection roots.
Keep intentionally unlisted project visibility unchanged. An organization
index must not implicitly add them to a public catalog or projection.

## DnD / RMAL: excluded from physical migration

All 368 inventoried DnD paths retain their original locations and contents.
The RMAL workspace points to its existing README, CURRENT document, compiler,
and project modules from outside DnD. Its intake index, documentation, CMake
layout, corpus, and provenance stay as they are.

## Navigation deliverables

Each of the three eligible repositories receives a concise
`docs/organization/README.md` and a
machine-readable `docs/organization/layout.json` catalog. Link the entry from
its repository README. Indexes show project homes, current entry points,
test/run commands, evidence locations, historical source locations, and
explicit path exceptions. Root READMEs remain short and route to deeper pages.

Each migrated project/topic gets one current README. Existing predecessor
indexes stay identifiable; a new index must not rewrite their historical
status or import claims from another project's evidence.

The final migration manifest records actual old/new paths and exact commits,
including retained exceptions. It differs from the proposal inventory: only
verified completed moves belong in the executed manifest.

## Migration and compatibility rules

1. Refresh eligible repository branch state before implementation and compare
   with the baseline inventory. Incorporate new commits and preserve local
   work. Do not pull open PR code into this change. Read DnD only; do not
   perform Git mutations or checkout changes there for this task.
2. For each package, inspect inbound references across all four repositories:
   Markdown/HTML links, JSON paths, imports, `__file__`/cwd assumptions,
   schemas, scripts, workflow filters, install lists, and saved cloud setup.
3. Make Git-tracked moves together with affected current references. Avoid
   bulk text substitutions inside immutable records or strings unrelated to
   paths. Do not merge duplicated-looking source or evidence records.
4. Preserve historical receipts and copied source bytes. Whole-directory
   moves are allowed when identity and relative dependencies are preserved.
   If a fixed path or hash lock cannot be maintained, retain that source path
   and expose its intended logical category through the index. Record the
   precise exception; do not silently omit it.
5. Resolve historical paths through the original revision and migration map.
   Do not edit old provenance to claim newly tested behavior. Do not add
   symlinks to Conscience64 public source roots, whose counterprobes reject
   them. Add a compatibility entry only where a concrete consumer requires
   it, rather than leaving a full duplicate tree.
6. Run baseline checks before each package, then rerun its affected checks.
   If a prerequisite or immutable contract blocks a move, complete its
   navigation and independent moves and record the retained-path exception.
7. Commit each eligible repository's completed package separately. Cross-repository
   references must resolve in the final reviewed set. Publishing, merging,
   and pushing are separate from the local organization work.

## Validation required for implementation

These are planned checks; they have not been executed for the proposed layout.

- Inventory: every baseline tracked file accounted for; no path collisions,
  silent deletions, unrelated modifications, or untracked outputs committed.
- Links/imports: all changed local references resolve within and between the
  four checkouts; historical commit links are distinguished from live paths.
- Integrity: retained historical records, source locks, approval files, and
  moved byte-preserved evidence match their baseline hashes.
- redogit: existing Plan Authority suite, `tools/redogit.py check`, current
  navigation checks, and functional execution of the affected Dean probes
  into fresh temporary output directories. Compare declared outcomes rather
  than regenerating old receipts. Validate publication tooling only for
  affected inputs; do not perform deployment.
- Other-Projects-: existing tests/audits for each moved project and current CI
  commands. At minimum retain the verified compression suite, Knowledge
  Garden build/tests plus health/projects/search requests, and S1/Operator
  Lab tests when their paths change. MLIR and Android paths require their
  documented toolchains before claiming those optional builds pass; absence
  of those toolchains must remain a stated validation limitation.
- conscience64: isolated projection/privacy counterprobes, tooling tests,
  route checks, and affected Hodge/analytics/coordinate-space tests. The
  admitted public route set and source-family boundary must remain the same.
- DnD: read-only status and baseline hash checks establish that this task
  has left its contents unchanged. No writes or new build outputs in its
  checkout; any necessary consumer validation runs from an external build
  directory. Do not claim new Windows evidence from a Linux check.
- Cloud reuse: update only affected installation/start paths in the saved
  environment draft and exercise the updated commands in their working
  directories. Preserve the existing isolated-checkout guidance.

## Success criteria and review boundary

The first stage is complete when the eight workspace entry points and source
scopes are present and usable, with DnD untouched and hosted-project creation
reported separately. The later physical organization is complete when its
navigation and moves are present, every eligible original file has an
executed move or a documented retained-path
exception, affected functional checks pass or have a diagnosed pre-existing
limitation, and startup instructions use the actual new locations.

This written specification and the file-by-file proposal are the reviewable
result of design work. Implementation begins after the owner approves this
written design; the next deliverable is the implementation plan for workspace
entry points before any repository migration. No source restructuring or
hosted-project creation is implied by committing this design.
