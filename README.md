# Arc workspace

> **Status: design phase.** No builds are available yet. The repositories pinned here contain the product definitions, architecture and roadmap that implementation follows.

Arc is an open-source suite of native desktop applications and one collaboration server for designing
buildings, infrastructure, products and 3D content, written in Rust on one shared foundation. This
repository pins every Arc repository as a git submodule, so the whole suite can be checked out and
followed from one place.

## Repositories

| Folder | Repository | Contents |
|---|---|---|
| [`arc-suite`](https://github.com/ACKaraca/arc-suite) | ACKaraca/arc-suite | Vision, product map, suite architecture, engineering standards, decisions, roadmap |
| [`arc-core`](https://github.com/ACKaraca/arc-core) | ACKaraca/arc-core | Shared foundation: geometry, document model, commands, rendering, UI kit, interchange |
| [`archbuilder`](https://github.com/ACKaraca/archbuilder) | ACKaraca/archbuilder | BIM authoring for architecture, structure and building services |
| [`draftbuilder`](https://github.com/ACKaraca/draftbuilder) | ACKaraca/draftbuilder | 2D drafting and 3D CAD on the DWG/DXF data model |
| [`civilbuilder`](https://github.com/ACKaraca/civilbuilder) | ACKaraca/civilbuilder | Civil infrastructure design |
| [`solidbuilder`](https://github.com/ACKaraca/solidbuilder) | ACKaraca/solidbuilder | Parametric solid modeling, assemblies, drawings, manufacturing |
| [`meshbuilder`](https://github.com/ACKaraca/meshbuilder) | ACKaraca/meshbuilder | Polygon modeling, sculpting, rigging and animation |
| [`renderbuilder`](https://github.com/ACKaraca/renderbuilder) | ACKaraca/renderbuilder | Physically based production renderer |
| [`arc-review`](https://github.com/ACKaraca/arc-review) | ACKaraca/arc-review | Model viewing, federation, clash detection and review |
| [`arc-hub`](https://github.com/ACKaraca/arc-hub) | ACKaraca/arc-hub | Self-hostable collaboration and data-management server |
| `arc-internal` | private | Maintainer notes; not required and not available to the public |

Start with [arc-suite](https://github.com/ACKaraca/arc-suite). Work across the suite is tracked on the
[Arc Suite project board](https://github.com/orgs/ACKaraca/projects/1).

## Checking out the suite

```sh
git clone --recurse-submodules https://github.com/ACKaraca/ArcBuilder.git
```

The private `arc-internal` submodule is skipped by default (`update = none`). Maintainers with
access fetch it with:

```sh
git submodule update --init --checkout arc-internal
```

To move every repository to the latest commit of its main branch:

```sh
git submodule update --remote --merge
```

## How this repository is used

Each product is developed, reviewed and released in its own repository. This repository only records
which commits belong together and gives contributors and coding agents one folder in which a local
Cargo `[patch]` can point products at the local `arc-core`. Rules for working in the workspace are in
[AGENTS.md](AGENTS.md).

## License

The files in this repository are licensed under the [Apache License, Version 2.0](LICENSE). Each
submodule carries its own license file.

## Trademarks

Arc, ArchBuilder, DraftBuilder, CivilBuilder, SolidBuilder, MeshBuilder, RenderBuilder, Arc Review and Arc Hub are names of this project and are not covered by the Apache License; see the [trademark policy](https://github.com/ACKaraca/arc-suite/blob/main/TRADEMARKS.md). All other product and company names are trademarks of their respective owners and are used only to describe scope and interoperability.
