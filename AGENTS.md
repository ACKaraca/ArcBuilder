# Arc workspace

This repository is the Arc workspace: it pins every Arc repository as a git submodule so the suite
can be checked out, browsed and worked on side by side. It contains no product code or product
documentation of its own.

| Folder | Repository | Visibility |
|---|---|---|
| `arc-suite` | `ACKaraca/arc-suite`: vision, architecture, standards, ADRs, roadmap | public |
| `arc-core` | `ACKaraca/arc-core`: shared Rust foundation crates | public |
| `archbuilder`, `draftbuilder`, `civilbuilder`, `solidbuilder`, `meshbuilder`, `renderbuilder`, `arc-review`, `arc-hub` | `ACKaraca/<same name>`: one product each | public |
| `arc-internal` | maintainer notes (strategy, research, planning) | private, access restricted |

## Rules for this workspace

- Before working inside a repository, read that repository's `AGENTS.md`. Each one is
  self-sufficient; do not load several at once.
- Changes are made, committed and reviewed inside the submodule's own repository. This repository
  only records which commit of each repository belongs together; update a pointer after the change
  has been merged there (`git add <folder>` here, then commit).
- Nothing from `arc-internal` is copied into a public repository. Public documents use neutral
  language, name no other company's products outside file formats and interoperability statements,
  and never describe how they were planned.
- `arc-internal` is written in Turkish for the maintainer, except its `planning/`, `parity/` and
  `research/` folders.
- Repositories that are not listed above are out of scope; do not modify them.
- Until the suite rules say otherwise (rule 14), the maintainer commits directly to `main` in every
  repository. Other contributors work on a branch and open a pull request; the maintainer reviews
  and merges it. Claim an issue (assignee and board status *In Progress*) before starting, and do not
  start on an issue someone else has claimed.
- Suite-wide decisions live in `arc-suite/docs/adr`.
- Work is tracked as GitHub issues in each repository and on the organization project board
  "Arc Suite" (https://github.com/orgs/ACKaraca/projects/1; statuses Backlog, Ready, In Progress,
  In Review, Blocked, Done).
- After changing public documents, run `python arc-internal/tools/verify_docs.py [repo ...]` from
  this folder when `arc-internal` is available; it must report 0 problems.
