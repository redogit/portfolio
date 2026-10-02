# Workspace Organization Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox syntax for tracking.

**Goal:** Implement eight project workspace entry points and a deeper organization in the three eligible repositories, preserving DnD exactly.

**Architecture:** Workspace scope files point to independent existing checkouts. Physical migration uses the reviewed file map, dependency-aware retained exceptions, current-reference updates, and a recorded old-to-new locator for each baseline file. Existing toolchain and publication interfaces remain stable.

**Tech Stack:** Markdown, JSON, Git, Python 3.12, Node 24, existing project test runners.

**Spec:** [Approved design](../specs/2026-09-30-repository-organization-design.md).

## Global Constraints

- DnD is reference-only: no file edits, additions, moves, Git mutations, or in-checkout outputs.
- Keep the existing isolated checkouts and their `work` branches; create no worktrees.
- Keep the four repositories independent; no new hosted repositories/projects, publication, or push.
- Preserve historical receipts, copied provenance, approval records, source locks, and encoded carriers.
- A proposed move requiring changes in DnD is retained or gets compatibility outside DnD.
- Keep original project names, dated filenames, subsystem layouts, and recorded run identifiers.
- Use ignored/external build and test-output directories; never replace original evidence with fresh outputs.

## Review Focus

- Source-relative paths and sibling imports must work after their source files move.
- Current Markdown/HTML links and CI commands must resolve to actual destinations.
- Historical pinned identities must remain byte-identical or remain at their original paths.
- Workspace scopes must remain project-local and preserve intentional unlisted visibility.
- DnD must have identical paths/hashes and a clean working tree after every migration stage.

## Task 1: Workspace navigation

**Files:** Create `workspaces/README.md`, `workspaces/catalog.json`, and one `README.md`, `scope.json`, and `CURRENT.md` under each of the eight workspace IDs in the specification. Modify the root `README.md` to link the workspace entry point.

**Interfaces:** Consumes the approved `workspace-groups.json` and actual sibling checkout paths. Produces a catalog with eight unique IDs and portable source locations for subsequent migrations to update.

- [x] Create the implementation ledger and refreshed file baseline outside the checkouts.
- [x] Generate the eight workspace entry points, purpose/scope records, and current-work notes.
- [x] Verify every source location exists, all eight IDs are unique, and RMAL has reference-only DnD scope.
- [x] Commit the workspace documents and plan locally.

## Task 2: redogit migration

**Files:** Move reviewed root research records into `research/pnp`, `research/decision-field`, and `research/gsfl`; navigation and coordination documents into their reviewed `docs` homes. Create `docs/organization/{README.md,layout.json,migration.json}` and project/topic READMEs. Modify affected current links, CLI/CI references, and workspace scope paths.

**Interfaces:** Consumes the baseline and reviewed candidates. Produces an actual source-to-destination manifest including retained exceptions and a working current navigation surface.

- [x] Validate the Plan Authority and profile-contract baseline before moves.
- [x] Keep immutable JSON receipts/contracts and pinned operational paths compatible; record every retained exception.
- [x] Move the dependency-complete research/document groups and update only current operational/path references.
- [x] Run the 60-test Plan Authority suite, profile verification, all moved probe entry points, and new-link/path checks. Output fresh probe evidence outside the checkout.
- [x] Verify original evidence and DnD hashes; commit the package locally.

## Task 3: Other-Projects- migration

**Files:** Move existing project homes beneath `projects/{research,languages,cooperation,tools,archives,games,mobile}`. Apply deeper internal role directories where they preserve dependencies; retain tightly coupled source/test/tool groups together and explain exceptions. Update eligible current workflow paths and navigation. Create `docs/organization/{README.md,layout.json,migration.json}`.

**Interfaces:** Consumes refreshed upstream files and Task 1 catalog. Produces relocated project homes, updated current CI/start paths, unchanged pinned records, and a working local API/test workflow.

- [x] Capture baseline Operator Lab tests and the affected repository-supported test commands.
- [x] Migrate complete project trees; avoid isolated internal moves that break source-relative fixtures, source locks, or frozen audit identities.
- [x] Update current executable paths, CI filters, current catalogs, and cross-repository references; preserve immutable historical records.
- [x] Run the existing Python suites for relocated labs, Node tests for S1/Knowledge Garden, and live Knowledge Garden health/project/search requests.
- [x] Run required frozen `--check` audits and Python MLIR parity tooling. Preserve optional Windows/Android/LLVM build limitations distinctly.
- [x] Verify evidence hashes and unchanged DnD; commit locally.

## Task 4: Conscience64 migration

**Files:** Move eligible root architecture/operation documents and Hodge documents/code/tests/results into reviewed role directories. Keep route-bound source families and constrained project modules at their current paths. Update current import/test entry points, tool references, and organization catalog.

**Interfaces:** Consumes actual destination locators from Tasks 2 and 3. Produces a working Hodge test workflow, consistent links, and an unchanged public projection boundary.

- [x] Preserve all source-locked data and curated public source paths.
- [x] Move Hodge records by role with evidence bytes unchanged, adapt current test import/source locations, and retain other modules whose static/runtime paths are contractual.
- [x] Run the 41-test Hodge suite, projection counterprobes, existing tooling/route suites, and affected platform tests.
- [x] Verify the accepted public route family, all retained receipts, and DnD hashes; commit locally.

## Task 5: Reusable startup and whole-change review

**Files:** Update the cloud setup draft's affected start/install paths, workspace notes, and `docs/organization` completion records.

**Interfaces:** Consumes all actual locators and verification results; produces tested reusable startup instructions and a reviewable local commit set.

- [x] Validate all baseline-file accounting, new links, scopes, and recorded retained exceptions.
- [x] Update and exercise saved installation/start instructions in their new working directories; leave DnD operations untouched during organization.
- [x] Request one independent review of all three repository diffs and workspace scopes; address material findings and rerun affected checks.
- [x] Verify DnD's 368 hashes and paths unchanged and every repository's Git state is accounted for.
- [x] Report local workspace links, physical moves, verification, retained exceptions, and the hosted-project/tooling limits.

## Execution decision

The owner explicitly requested implementation after reviewing the design and
the DnD constraint. Proceed inline in this session without another approval
round; the final independent review is the only agent delegation required.
Documentation and path organization use concrete reference/integrity checks
and existing functional suites. Any behavioral path fix is reproduced by a
failing existing check before correction.
