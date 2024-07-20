# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [unreleased]

### :warning: Changes for Developers/Package Distributors

-   The 'bitmaps' directory has been removed from the git repository. You can now generate the PNG files using `yarn render` or download them from the release assets.

### What's New?

-   Banana cursor is now customizable
-   Support `256px` cursors

### Changes

-   build script renamed (`release.sh` -> `build.sh`)
-   Use 'xz' for better compression in `build.sh` script
-   De-framed animated cursors to static SVG files

## [v1.0.0] - 02 November 2022

### Added

-   CI/CD Pipelines
-   Logo and badges
-   Initial release 🎊

[unreleased]: https://github.com/ful1e5/banana-cursor/compare/v1.0.0...main
[v1.0.0]: https://github.com/ful1e5/banana-cursor/tree/v1.0.0
