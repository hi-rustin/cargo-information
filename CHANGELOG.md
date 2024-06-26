# Change Log

<!-- next-header -->

## [Unreleased] - ReleaseDate

## [0.7.0] - 2024-06-09

### Added

- Display the keywords of the crate as clickable links in the terminal.

### Changed

- Dependency updates and patches, including updates to rust crate anstyle(1.0.7), color-print(0.3.6), cargo(0.79.0),
  anyhow(1.0.86), semver(1.0.23), snapbox(0.5.14), trycmd(0.15.3),  and cargo-credential(0.4.4).

## [0.6.0] - 2024-04-17

### Added

- Display the crates.io link for packages.

### Changed

- Refined the approach to feature rendering. The changes include:
    - For features enabled by users, a `+` prefix and colored output are now used for better visibility.
    - For features enabled automatically, colored output is used to distinguish them.
    - For disabled features, non-colored output is used to clearly indicate their status.

- Refined the approach to dependency rending
    - For dependencies required by the package, a `+` prefix and colored output are now used for better visibility.
    - For dependencies that are optional and activated, colored output is used to distinguish them.
    - For dependencies that are optional and not activated, non-colored output is used to clearly indicate their status.

- Only show dependencies in verbose mode.

- Dependency updates and patches, including updates to rust crate anyhow(1.9.82), semver(1.0.22), snapbox(0.5.9), clap(
  4.5.4), trycmd(0.15.1) and cargo-credential(0.4.4).

### Fixed

- Enhanced user experience by limiting the number of features displayed in non-verbose mode to prevent information
  overload.
- Prefer direct dependencies over transitive dependencies.

## [0.5.0] - 2024-04-17

Accidentally skipped. There is no v0.5.0. See: https://github.com/crate-ci/cargo-release/issues/778

## [0.4.2] - 2024-02-20

### Added

- Show source ID information for dependencies not from the registry.

### Changed

- Reorder suggested cargo-tree parameters to align with other cargo commands.
- Dependency updates and patches, including updates to rust crate cargo(0.77.0), snapbox(0.5.1), crates-io(0.39.2),
  anstyle(1.0.6), trycmd(0.15.0), clap(4.5.0) and cargo-credential (0.4.2).

## [0.4.1] - 2024-01-11

### Added

- Introduced the `vendored-openssl` feature to enable the use of the vendored version of OpenSSL.

### Changed

- Updated the clap dependency to 4.4.14.

## [0.4.0] - 2024-01-05

### Added

- Prioritize selection of Minimum Supported Rust Version (MSRV) compatible crate versions. The following hierarchy is
  used to determine the MSRV:
    - First, the MSRV of the parent directory package is checked, if it exists.
    - If the parent directory package does not specify an MSRV, the minimal MSRV of the workspace is checked.
    - If neither the workspace nor the parent directory package specify an MSRV, the version of the current Rust
      compiler (`rustc --version`) is used.

### Changed

- Dependency updates and patches, including updates to rust crate cargo(0.74.0), clap(4.4.12), anyhow(1.0.79) and
  semver(1.0.21).

## [0.3.0] - 2023-12-20

### Added

- Allow to inspect a package from the local workspace.

### Fixed

- Generate `Cargo.lock` file if it does not exist and pick the correct matching version.

## [0.2.1] - 2023-12-11

### Fixed

- Do now allow empty spec name.
- Bail out an error for non remote registry.

## [0.2.0] - 2023-12-06

### Added

- Support for version selection in package specification.
- Support for custom registry.
- Pretty owners feature for listing package owners in a more readable format.
- Enhanced CLI with global options in the info command and added subcommands to make it as a Cargo subcommand.
- Corrected various issues related to feature detection, display, and handling.
- Fixed issues related to offline and frozen argument handling.
- Cargo tree suggestion feature.
- Basic information retrieval and display features.

### Changed

- Refactored various parts of the code for clarity and efficiency, including extra views, pretty printing methods, and
  use of package APIs.
- Various test cases for URL package specifications, registry matching, workspace inclusion, and lockfile consistency.
- Dependency updates and patches, including updates to rust crate clap (4.4.9, 4.4.10, 4.4.11) and cargo-util (0.2.7).

### Removed

- Removal of unused or redundant dependencies and files for cleaner codebase.

### Chore

- General maintenance updates, including clippy fixes and setting the Rust version.
- Continuous integration improvements with GitHub actions and caching.

### Documentation

- Updates to README for better user guidance.
- Documentation updates including asciicast demo and mention of registries support.
