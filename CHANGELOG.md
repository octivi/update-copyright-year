# Changelog

## [Unreleased] - 2026-02-18

### Added

- Add support for multiline YAML parameters for action inputs ([`edbbe94`](https://github.com/octivi/update-copyright-year/commit/edbbe94)) (Marcin Engelmann)
- Add `dry_run` and `verbose` modes with GitHub-native step logs and summary reporting ([`6381636`](https://github.com/octivi/update-copyright-year/commit/6381636)) (Marcin Engelmann)

### Fixed

- Interpret `patterns` input values as fixed strings instead of regular expressions ([`d68e1d3`](https://github.com/octivi/update-copyright-year/commit/d68e1d3)) (Marcin Engelmann)

## [1.2.0] - 2026-02-02

### Fixed

- Fix `sed` matching so header year replacement works correctly ([`116260a`](https://github.com/octivi/update-copyright-year/commit/116260a)) (Marcin Engelmann)

## [1.1.1] - 2026-02-02

### Fixed

- Prevent default `headers_regexp` from overriding `organization_regexp` ([`cf6c950`](https://github.com/octivi/update-copyright-year/commit/cf6c950)) (Marcin Engelmann)

## [1.1.0] - 2026-02-02

### Added

- Add optional `organization_regexp` input to scope header matching to a specific org or person ([`5ad0007`](https://github.com/octivi/update-copyright-year/commit/5ad0007)) (Marcin Engelmann)

## [1.0.1] - 2026-01-31

### Fixed

- Split space-separated `exclude_paths` and `include_glob` values into separate patterns before processing ([`25ffe09`](https://github.com/octivi/update-copyright-year/commit/25ffe09)) (Marcin Engelmann)

## [1.0.0] - 2026-01-31

### Added

- Add a GitHub Action that updates copyright years in matched file headers ([`3020ead`](https://github.com/octivi/update-copyright-year/commit/3020ead)) (Marcin Engelmann)

[Unreleased]: https://github.com/octivi/update-copyright-year/compare/v1.2.0...HEAD
[1.2.0]: https://github.com/octivi/update-copyright-year/releases/tag/v1.2.0
[1.1.1]: https://github.com/octivi/update-copyright-year/releases/tag/v1.1.1
[1.1.0]: https://github.com/octivi/update-copyright-year/releases/tag/v1.1.0
[1.0.1]: https://github.com/octivi/update-copyright-year/releases/tag/v1.0.1
[1.0.0]: https://github.com/octivi/update-copyright-year/releases/tag/v1.0.0
