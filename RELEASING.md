# Release process

Splatfold publishes through GitHub Actions and PyPI Trusted Publishing. No
long-lived PyPI API token should be stored in the repository.

## Release checklist

1. Confirm that the intended PyPI version is not already published.
2. Update `VERSION` in `splatfold.py` and move the relevant changelog entries
   out of `Unreleased`.
3. Run the complete local checks documented in `CONTRIBUTING.md`.
4. Build both distributions with `python -m build` and verify them with
   `python -m twine check dist/*`.
5. Install the wheel in a new virtual environment outside the checkout.
6. Use that installed `splatfold` command to check, build, and execute the
   Acute integration example.
7. Merge the exact reviewed commit, create a matching signed version tag, and
   publish a GitHub Release.
8. Let `.github/workflows/publish.yml` build fresh artifacts and publish them
   through the protected `pypi` environment.
9. Verify the PyPI page, installation command, package hashes, CLI version, and
   imported `splatfold.__version__` from a new environment.

Publishing is intentionally release-triggered. A successful local build or CI
run must never upload a distribution by itself.

