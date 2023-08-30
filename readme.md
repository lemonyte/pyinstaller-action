# PyInstaller GitHub Action

A simple GitHub Action to build Python projects with PyInstaller.

## Usage

Example workflow:

```yaml
name: PyInstaller Build

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
  workflow_dispatch:

jobs:
  build:
    strategy:
      matrix:
        os:
          - ubuntu-latest
          - macos-latest
          - windows-latest
    name: Build release on ${{ matrix.os }}
    runs-on: ${{ matrix.os }}
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Build with PyInstaller
        uses: lemonyte/pyinstaller-action

```

## Inputs

| Name | Description | Required | Default |
| --- | --- | --- | --- |
| `spec` | Path to your spec file. | Yes | |

todo

## License

[MIT License](license.txt)
