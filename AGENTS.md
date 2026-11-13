# AGENTS.md

## Repository orientation

This is the documentation-only repository for the combined Meta and Meta-BI
public reference. The MetaDocs model, runtime, CLI, and tests are owned by the
sibling `meta` repository.

Before substantial work, read `README.md` and inspect the current runtime help
for `meta-docs` and `meta-mesh`. Trace the relevant operation in
`Documentation.MetaMesh` to understand its inputs, import steps, suite merge,
validation and rendering. The runtime and model sources are in `../meta/MetaDocs`
and `../meta/MetaMesh` when implementation detail is needed.

Use `meta-docs update-description` for existing authored narrative, and
`meta-docs author-page` when creating or updating page structure. Inspect each
command's current help before authoring. For product behaviour, consult its
owning repository and current CLI help rather than removed skill-file paths.

Regenerate through the documented `regenerate-public-docs` mesh operation. It
imports product references, validates authored inputs, merges the suite,
validates the result and renders `Site/docs.html`.

## Repository rules

- Keep sibling checkouts named `meta`, `meta-bi`, and `meta-docs` under the same
  parent directory; the modeled mesh uses that coordinate system.
- Do not hand-edit generated reference workspaces, `SuiteWorkspace`, generated
  workspace artifacts, or `Site/docs.html`.
- Use `meta-docs` for authored prose and `meta-mesh` for regeneration.
- Change CLI and model sources in their owning repository, not here.
- Resolve output paths before generation and stop if a path repeats logical
  directory segments.
- Preserve unrelated worktree changes.
