# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Changed
- `Point::generate` function now accepts a `impl FnMut`. Custom implementations of `Point` must change to accept `impl FnMut` instead of `impl Fn`.
  Callers of `Point::generate` should not require changes.

## [0.8.1] - 2020-06-18
### Changed
- Fine tuned nearest neighbor iterator inline capacity (see  #39). This should boost performance in some cases.

## [0.8.0] - 2020-05-25
### Fixed
- Bugfix: `RTree::locate_with_selection_function_mut` sometimes returned too many elements for small trees.

### Changed
- Deprecated `RTree::nearest_neighbor_iter_with_distance`. The name is misleading, use `RTree::nearest_neighbor_iter_with_distance_2` instead.
- Some performance improvements, see #38 and #35

### Added
- Added `nearest_neighbor_iter_with_distance_2` #31

## [0.7.1] - 2020-01-16
### Changed
- `RTree::intersection_candidates_with_other_tree` can now calculate intersections of trees of different item types (see #23)

## [0.7.0] - 2019-11-25
### Added
- `RTree::remove_with_selection_function`
- `RTree::pop_nearest_neighbor`
- Added CHANGELOG.md

[Unreleased]: https://github.com/Stoeoef/rstar/compare/0.8.1...HEAD
[0.8.1]: https://github.com/Stoeoef/rstar/compare/0.8.0...0.8.1
[0.8.0]: https://github.com/Stoeoef/rstar/compare/0.7.1...0.8.0
[0.7.1]: https://github.com/Stoeoef/rstar/compare/0.7.0...0.7.1
[0.7.0]: https://github.com/Stoeoef/rstar/releases/tag/0.7.0
