# AmpForm issue 529: forbidden helicities

[![Spelling checked](https://img.shields.io/badge/cspell-checked-brightgreen.svg)](https://github.com/streetsidesoftware/cspell/tree/main/packages/cspell)
[![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/charliermarsh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)

An executable investigation of [ComPWA/ampform#529](https://github.com/ComPWA/ampform/issues/529), using the fix from [PR #530](https://github.com/ComPWA/ampform/pull/530). AmpForm is installed directly from GitHub over HTTPS, pinned to commit `f481d880c40fa3178718c96b1c254c827f77f393`.

The notebook compares scalar and vector decay chains, reproduces the original unresolved amplitudes, and checks the fix in both helicity bases. One table covers four illustrative channels. The calculations use unit dynamics and no spin alignment to isolate amplitude bookkeeping; they are not complete fit models.

## Run locally

```shell
uv tool install poethepoet
poe lab content/forbidden-helicities.ipynb
```

Alternatively, install this project's dependencies with `pip install .`, then open the notebook with `jupyter lab content/forbidden-helicities.ipynb`. Neither approach needs a sibling AmpForm checkout.

The workflow tests the notebook and publishes an interactive JupyterLite website to GitHub Pages on pushes to `main`. Select **GitHub Actions** as the Pages source in the repository settings. Open the notebook on the website, select the Pyodide kernel, and run all cells. The setup cell installs the browser dependencies; an internet connection is required on first use.

Build locally with `poe doc`, or preview with `poe doclive`. The site build uses standard `pip wheel` to prepare the pinned AmpForm PR for the browser in the ignored `wheels/` directory. No wheels are committed. Native installs continue to use the direct HTTPS Git dependency.

QRules is pinned to 0.10.10 because its solver dependency has a published pure Python wheel supported by Pyodide. Both native and browser execution use this version.

See [CONTRIBUTING.md](CONTRIBUTING.md) for validation commands.
