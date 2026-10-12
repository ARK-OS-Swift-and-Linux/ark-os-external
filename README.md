# External Dependencies and Upstream Management

## Purpose

The `external/` directory coordinates external upstream projects, third-party code, and vendor dependencies required by ARK-OS.

ARK-OS maintains strict separation between first-party system components (located in `components/`) and external third-party software to ensure code auditability, clear licensing boundaries, and reproducible builds.

---

## Current Status

- **Status:** Empty / No active checkouts
- **Vendored Trees:** None
- **External Submodules:** None

---

## Management Rules

All external dependencies must adhere to the engineering rules defined in [AGENTS.md](file:///home/aarav/repo/arkos/AGENTS.md) Section 3.5 and Section 10:

1. **Pinned Revisions:** All external source trees must be tracked using deterministic, pinned revisions (such as Git commit SHAs or cryptographic source archive hashes) recorded in [manifests/sources.lock.toml](file:///home/aarav/repo/arkos/manifests/sources.lock.toml).
2. **No Direct In-Tree Modification:** Do not modify upstream source files directly in an undocumented manner. Local modifications must be stored as explicit, reviewable patch files located alongside the dependency configuration.
3. **No Unnecessary Vendoring:** Do not vendor an entire external repository if only a specific library or package is needed.
4. **License and Notice Tracking:** Every dependency must have its upstream source URL, exact revision, license identifier, and copyright notices documented in [THIRD_PARTY_NOTICES.md](file:///home/aarav/repo/arkos/THIRD_PARTY_NOTICES.md) and [docs/licensing/index.md](file:///home/aarav/repo/arkos/docs/licensing/index.md).
5. **No Secret or Proprietary Code:** Never commit proprietary code, unauthorized binaries, or credentials to this directory.
