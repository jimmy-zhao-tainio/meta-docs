# meta-docs

This repository owns the modeled public documentation for
[`meta`](https://github.com/jimmy-zhao-tainio/meta) and
[`meta-bi`](https://github.com/jimmy-zhao-tainio/meta-bi). The rendered reference
is published at [metametabi.com/docs.html](https://metametabi.com/docs.html).

Only documentation lives here. The MetaDocs model, runtime, CLI, and tests remain
in `meta`.

## Repository layout

- `Workspaces/metametabi-authored` contains authored public prose.
- `Workspaces/*` contains generated CLI and model reference workspaces.
- `SuiteWorkspace` is the generated combined reference.
- `Documentation.MetaMesh` is the canonical 53-step regeneration operation.
- `Site/docs.html` is the generated site.

The mesh expects sibling checkouts with this layout:

```text
Desktop/
|-- meta/
|-- meta-bi/
`-- meta-docs/
```

## Validate and regenerate

Run from this repository root with the Meta and Meta-BI CLIs on `PATH`:

```powershell
meta-mesh validate --operation regenerate-public-docs --workspace Documentation.MetaMesh
meta-mesh run --operation regenerate-public-docs --workspace Documentation.MetaMesh
```

The operation imports the modeled sources from both product repositories,
validates the inputs and combined suite, and renders the site. To inspect CLI
coherence separately, generate a matrix with `meta-docs cli-matrix`. A CSV can
be viewed without Excel using:

```powershell
Import-Csv <path>\cli-matrix.csv | Out-GridView
```

Do not hand-edit generated workspaces, `SuiteWorkspace`, or `Site/docs.html`.
Author prose with `meta-docs`, change product command models through their owning
CLIs, and regenerate through the mesh.

## License

Licensed under the [Apache License 2.0](LICENSE).
