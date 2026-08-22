# AGENTS.md

## Repository orientation

This is the documentation-only repository for the combined Meta and Meta-BI
public reference. The MetaDocs model, runtime, CLI, and tests are owned by the
sibling `meta` repository.

Before substantial work, read these canonical skills completely:

- `../meta/Skills/author-meta-docs/SKILL.md` for authoring and regeneration;
- `../meta/Skills/use-meta-mesh/SKILL.md` when changing or running the mesh;
- the relevant product skill under `../meta/Skills/` when documentation changes
  depend on product behavior.

Use current runtime help for exact command syntax.

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
