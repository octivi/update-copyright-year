# Changelog

## [Unreleased]

_This release improves configuration flexibility, run visibility, and onboarding._

### Changed

- Improve run reliability and diagnostics so failures are easier to understand
  in GitHub Actions logs and summaries
  ([`6381636`](https://github.com/octivi/update-copyright-year/commit/6381636),
  [`14a2db4`](https://github.com/octivi/update-copyright-year/commit/14a2db4),
  [`d2211ca`](https://github.com/octivi/update-copyright-year/commit/d2211ca),
  [`9cad00d`](https://github.com/octivi/update-copyright-year/commit/9cad00d),
  [`5e499eb`](https://github.com/octivi/update-copyright-year/commit/5e499eb),
  [`c1b48af`](https://github.com/octivi/update-copyright-year/commit/c1b48af),
  [`d5d4eca`](https://github.com/octivi/update-copyright-year/commit/d5d4eca),
  [`4ed5733`](https://github.com/octivi/update-copyright-year/commit/4ed5733))
- Improve setup documentation and examples for faster first-time adoption
  ([`9a121fe`](https://github.com/octivi/update-copyright-year/commit/9a121fe),
  [`d8ad66c`](https://github.com/octivi/update-copyright-year/commit/d8ad66c),
  [`2a0e390`](https://github.com/octivi/update-copyright-year/commit/2a0e390),
  [`5776abf`](https://github.com/octivi/update-copyright-year/commit/5776abf),
  [`e2849ef`](https://github.com/octivi/update-copyright-year/commit/e2849ef),
  [`86552e3`](https://github.com/octivi/update-copyright-year/commit/86552e3),
  [`c46f70f`](https://github.com/octivi/update-copyright-year/commit/c46f70f),
  [`cc30d4d`](https://github.com/octivi/update-copyright-year/commit/cc30d4d),
  [`b506877`](https://github.com/octivi/update-copyright-year/commit/b506877),
  [`04f966d`](https://github.com/octivi/update-copyright-year/commit/04f966d),
  [`e5f0a0e`](https://github.com/octivi/update-copyright-year/commit/e5f0a0e),
  [`de6a6b6`](https://github.com/octivi/update-copyright-year/commit/de6a6b6),
  [`f746304`](https://github.com/octivi/update-copyright-year/commit/f746304),
  [`76eaf28`](https://github.com/octivi/update-copyright-year/commit/76eaf28),
  [`ab3101a`](https://github.com/octivi/update-copyright-year/commit/ab3101a))
- Improve internal script readability and maintainability
  ([`06c064c`](https://github.com/octivi/update-copyright-year/commit/06c064c))

### Added

- Add support for multiline YAML parameters in action inputs, making larger
  workflow configs easier to read and maintain
  ([`edbbe94`](https://github.com/octivi/update-copyright-year/commit/edbbe94))
- Add `dry_run` mode to preview changes safely before modifying files
  ([`6381636`](https://github.com/octivi/update-copyright-year/commit/6381636))
- Add `verbose` mode and GitHub-native run reporting for easier troubleshooting
  ([`6381636`](https://github.com/octivi/update-copyright-year/commit/6381636))

### Removed

- No user-facing removals.

### Fixed

- Fix pattern handling so `PATTERNS` are interpreted as literal values, not
  regular expressions
  ([`d68e1d3`](https://github.com/octivi/update-copyright-year/commit/d68e1d3))

## [1.2.0] - 2026-02-02

_This release hardens the action and introduces baseline quality gates._

### Changed

- Separate action logic into a dedicated script, reducing maintenance overhead
  and making behavior easier to follow
  ([`5216a18`](https://github.com/octivi/update-copyright-year/commit/5216a18))

### Added

- Add unit tests and ShellCheck linting to prevent regressions earlier
  ([`104175e`](https://github.com/octivi/update-copyright-year/commit/104175e),
  [`941927c`](https://github.com/octivi/update-copyright-year/commit/941927c))
- Add repository badges for Conventional Commits and Semantic Versioning
  ([`92013e3`](https://github.com/octivi/update-copyright-year/commit/92013e3))

### Removed

- No user-facing removals.

### Fixed

- Fix `sed` expression handling to avoid incorrect header updates
  ([`116260a`](https://github.com/octivi/update-copyright-year/commit/116260a))

## [1.1.1] - 2026-02-02

_Patch release focused on one correctness fix._

### Changed

- No user-facing changes.

### Added

- No user-facing additions.

### Removed

- No user-facing removals.

### Fixed

- Fix default input handling so `organization_regexp` is no longer overwritten
  by `headers_regexp`
  ([`cf6c950`](https://github.com/octivi/update-copyright-year/commit/cf6c950))

## [1.1.0] - 2026-02-02

_This release expands matching options and improves compatibility guidance._

### Changed

- Improve docs for `ubuntu-slim` compatibility and security references
  ([`4116e2e`](https://github.com/octivi/update-copyright-year/commit/4116e2e),
  [`083fcda`](https://github.com/octivi/update-copyright-year/commit/083fcda))

### Added

- Add optional regexp parameter for organization/person matching in headers
  ([`5ad0007`](https://github.com/octivi/update-copyright-year/commit/5ad0007))
- Add support for a specific header regexp in maintenance automation
  ([`a2567f7`](https://github.com/octivi/update-copyright-year/commit/a2567f7))
- Add MIT license badge in project documentation
  ([`5ad9a64`](https://github.com/octivi/update-copyright-year/commit/5ad9a64))

### Removed

- No user-facing removals.

### Fixed

- No user-facing fixes.

## [1.0.1] - 2026-01-31

_Patch release focused on safer path parsing and workflow correctness._

### Changed

- Improve workflow wiring and exclude non-target docs from year-update paths
  ([`38839ec`](https://github.com/octivi/update-copyright-year/commit/38839ec),
  [`3389f69`](https://github.com/octivi/update-copyright-year/commit/3389f69))

### Added

- No user-facing additions.

### Removed

- No user-facing removals.

### Fixed

- Fix parsing of space-separated `include_paths` and `exclude_paths` inputs
  ([`25ffe09`](https://github.com/octivi/update-copyright-year/commit/25ffe09))

## [1.0.0] - 2026-01-31

_Initial public release of the action._

### Changed

- No user-facing changes.

### Added

- Add first stable release of the action to update copyright years in file
  headers
  ([`3020ead`](https://github.com/octivi/update-copyright-year/commit/3020ead))

### Removed

- No user-facing removals.

### Fixed

- No user-facing fixes.

<!-- Reference links (recommended) -->

[Unreleased]: https://github.com/octivi/update-copyright-year/compare/v1.2.0...HEAD
[1.2.0]: https://github.com/octivi/update-copyright-year/releases/tag/v1.2.0
[1.1.1]: https://github.com/octivi/update-copyright-year/releases/tag/v1.1.1
[1.1.0]: https://github.com/octivi/update-copyright-year/releases/tag/v1.1.0
[1.0.1]: https://github.com/octivi/update-copyright-year/releases/tag/v1.0.1
[1.0.0]: https://github.com/octivi/update-copyright-year/releases/tag/v1.0.0
