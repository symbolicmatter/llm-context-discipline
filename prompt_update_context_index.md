You are operating within a project that uses `CONTEXT_ACCESS_RULES.md` and `CONTEXT_INDEX.yml`.

Objective:
Audit the two repositories listed below and determine whether `CONTEXT_INDEX.yml` requires updates.

Scope restriction (critical):

- Only access content under:
  - [https://github.com/symbolicmatter/context-driven-engineering](https://github.com/symbolicmatter/context-driven-engineering)
  - [https://github.com/symbolicmatter/context-driven-development-workflow](https://github.com/symbolicmatter/context-driven-development-workflow)
- Do NOT perform general web search.
- Do NOT access unrelated domains.
- Do NOT use citation discovery.
- Only traverse repository trees and directly open Markdown files.
- Ignore forks, external references, and linked websites.

Method:

1. Enumerate repository file trees (root + /docs + other relevant directories).
2. Identify all Markdown documents.
3. Compare against the attached `CONTEXT_INDEX.yml`.
4. Detect:
   - Missing entries
   - Obsolete entries
   - Renamed or moved files
   - Metadata misalignment (role, priority, status)
5. Do not infer authority from file location alone.
6. Do not modify the YAML implicitly.

Output format:

A) Repository File Inventory (per repo)
B) Differences vs Current Index
C) Required YAML Changes (ready-to-paste blocks)
D) Observed Structural Drift (if any)

Treat this as a controlled structural audit, not a discovery task.
