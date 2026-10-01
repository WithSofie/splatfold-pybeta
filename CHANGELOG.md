# Changelog

All notable changes to Splatfold will be documented here.

The project follows Semantic Versioning once its public API is released.

## Unreleased

### Changed

- Renamed the project from Obtuse/preprocessor to Splatfold.
- Added a side-effect-free Python build API and `BuildResult.write()`.
- Added conventional `__version__` metadata and explicit public exports.
- Added positional CLI input while retaining `-i` and `--input`.
- Matched Python's package-before-module import resolution precedence.
- Kept output writing compatible with Python 3.9.
- Made output replacement atomic, synchronized file contents before replacement,
  and preserved existing or input-file permissions.
- Added Python 3.9-3.14 CI, branch-coverage enforcement, distribution package
  checks, and a Trusted Publishing release workflow with commit-pinned actions.
- Added Dependabot maintenance for Python tooling and GitHub Actions.
- Made the wheel smoke test install outside the source checkout so local build
  metadata cannot masquerade as an installed distribution.
- Added release-tag/version validation, serialized publishing, artifact
  presence checks, and an isolated smoke test of the exact release wheel.

### Fixed

- Dependency `__main__` guards with `else` clauses now fail safely instead of
  silently discarding code that normal imports would execute.
- Encoding-cookie removal no longer mistakes ordinary first-line source text
  containing `coding:` for a declaration.
- Standalone `BuildResult` values now use safe default permissions when no
  included source path is available.
- Rewritten wildcard and future imports now reject physical lines shared with
  other statements instead of silently discarding neighboring code.
- Future-import hoisting now rejects root docstrings that share their final
  physical line with another statement.
- Included files without a final newline no longer join their last statement
  to the importing file's following source line.
- Indented comments beginning with `#!` are preserved instead of being
  mistaken for executable shebang lines.
- Future features are deduplicated individually even when source files group
  them into different multi-feature import statements.
