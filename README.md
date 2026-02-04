# GitHub actions for MREYE-LUMC

This repository contains custom GitHub actions for MREYE-LUMC projects.

## `python-setup`

Set up a specified version of Python in your GitHub Actions workflow and optionally install the dependencies.

### Inputs

- `python-version`: The Python version to set up (e.g., '3.13', '3.14', etc.). If not specified, the version in `.python-version` or otherwise the default version provided by GitHub Actions will be used.
- `sync`: If set to `true`, the action will install the dependencies listed in `pyproject.toml` using `uv sync`.

## `python-build`

Build a Python package and upload the built distributions as artifacts.

### Inputs

- `python-version`: The Python version to use for building the package (e.g., '3.13', '3.14', etc.). If not specified, the version in `.python-version` or otherwise the default version provided by GitHub Actions will be used.
- `artifact-name`: The name of the artifact to upload. Default is `python-distributions`.
- `artifact-path`: The path to the built distributions. Default is `dist/`.

## `python-publish`

Publish a Python package to PyPI and GitHub Releases.

### Inputs

- `tag`: The git tag that triggers the publish action. Can be obtained using `${{ github.ref }}`.
- `python-version`: The Python version to use for building the package (e.g., '3.13', '3.14', etc.). If not specified, the version in `.python-version` or otherwise the default version provided by GitHub Actions will be used.
- `artifact-name`: The name of the artifact to upload. Default is `python-distributions`.
- `artifact-path`: The path to the built distributions. Default is `dist`.
- `testpypi`: If set to `true`, the package will be published to TestPyPI instead of PyPI.
