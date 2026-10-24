# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0] - 2026-10-24

### Changed

- **Breaking:** requires `sanity@^6.9.2` (the first release on `@sanity/ui` v4)
- Import `Autocomplete`, `Menu`, `MenuItem` and `Popover` from their `@sanity/ui` v4 subpaths (`@sanity/ui/autocomplete`, `/menu`, `/popover`). The root export of these is `never` in v4 and `undefined` at runtime, so the picker crashed on any v4 host
- Declare `@sanity/ui` as a dependency instead of a devDependency, so the plugin no longer depends on whichever copy the host happens to hoist

## [1.0.3] - 2025-08-02

### Improved

- Improved package size by reorganizing dependencies to move Sanity packages to peer dependencies
- Improved build configuration by disabling source maps for smaller bundle size
- Improved TypeScript configuration by fixing treeshake configuration errors
- Improved dependency externalization for better package optimization
- Updated package to use ESM module type for modern JavaScript compatibility
- Removed React and Sanity from devDependencies to reduce bundle size

## [1.0.0] - 2025-07-29

### Added

- Initial release
