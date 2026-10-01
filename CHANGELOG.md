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

### Fixed

- Dependency `__main__` guards with `else` clauses now fail safely instead of
  silently discarding code that normal imports would execute.
- Encoding-cookie removal no longer mistakes ordinary first-line source text
  containing `coding:` for a declaration.
