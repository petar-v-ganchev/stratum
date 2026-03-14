# Changelog

All notable changes to Stratum are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Stratum uses [Semantic Versioning](https://semver.org/):
- **MAJOR** — breaking change to the `.stratum/` file format (requires migration)
- **MINOR** — new canvas, new layer, or new role capability
- **PATCH** — bug fixes, performance improvements, new language support

---

## [Unreleased]

*Changes staged for the next release are listed here during development.*

---

## [0.1.0] — 2026-03-14

### Initial Public Release

This is the first public release of Stratum. It ships the Logic Layer (HRSG)
with full bidirectional sync for C# and TypeScript, the Role System with
Developer / Product Owner / Viewer roles, and the `stratum: init` project
scaffolding command.

#### Added

**Logic Layer — HRSG Canvas**
- Interactive state machine graph rendered from your C# and TypeScript source
  files using React Flow
- Bidirectional sync: edit the graph → your code updates; edit your code →
  the graph updates; round-trip target 300ms
- C# language server (OmniSharp / Roslyn) for full semantic analysis:
  type checking, go-to-definition, find-all-references, hover documentation
- TypeScript language server (tsserver via WebContainers) for full semantic
  analysis in TypeScript and JavaScript projects
- Tree-sitter incremental parsing for all supported languages — < 5ms
  re-parse on keystroke for files up to 5,000 lines
- HRSG annotation protocol: `[StratumState]`, `[StratumTransition]` attributes
  for C#; `@stratum-state`, `@stratum-transition` JSDoc tags for TypeScript
- Format-preserving code writes — Stratum never changes your indentation style,
  brace style, or comment placement
- Sync conflict detection: when a canvas edit and an external code edit affect
  the same element simultaneously, Stratum surfaces a diff and waits for
  your resolution

**Role System**
- Three-role model: Developer, Product Owner, Viewer
- Roles configured in `.stratum/access.json`, resolved from `git config user.email`
- Role-gated VS Code commands — only commands applicable to your role appear
  in the Command Palette
- Role-aware canvas controls — drag handles, edit affordances, and destructive
  actions only rendered for roles with permission (absent from DOM, not hidden
  with CSS)
- Plain-English permission-denied messages — never "Access denied"
- Role-tagged automatic git commits:
  `feat(scenario): add login scenario [PO: carol@company.com]`
- Status bar indicator showing current role and sync state

**Project Initialisation**
- `Stratum: Initialise Project` command scaffolds `.stratum/` directory
- Generates `project.json`, `access.json`, `scenarios.json`, and
  `tokens/design-tokens.json`
- Auto-detects project language and platform from existing source files

**Host Abstraction Layer**
- `StratumHost` interface separating all VS Code API calls from core logic —
  enables the future web IDE port without rewriting canvas or sync code

#### Known Issues

- The Java language server (Eclipse JDT) is not included in this release.
  Java support is planned for v0.2.0.
- The WYSIWYG UI canvas, Scenario canvas, Database layer, and NL input are
  not included in this release. See the roadmap at docs.stratum.dev/roadmap.
- On Windows, the C# language server cold start may take up to 20 seconds
  on first open. Subsequent opens are faster (< 5 seconds).
- Multi-root workspaces (multiple folders in one VS Code window) are
  supported but each folder requires its own `.stratum/` initialisation.

---

## Version History Format

Each release entry follows this structure:

```
## [X.Y.Z] — YYYY-MM-DD

### Summary line

#### Added     — new features
#### Changed   — changes to existing features
#### Deprecated — features that will be removed in a future version
#### Removed   — features removed in this release
#### Fixed     — bug fixes
#### Security  — security-related fixes (always listed first in the section)
#### Performance — notable performance improvements
```

Security fixes are always listed first within their section and include
a CVE number if one has been assigned.

---
