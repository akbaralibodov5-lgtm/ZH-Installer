# ZH Installer — recovered source

The original executable is a PyInstaller-packed Python 3.8 application. The Actions recovery job successfully extracted 1,424 bundled files and produced a recovered source tree.

## Repository layout

- `ZH_Installer V1.9.exe` — original reference executable.
- `src/` — editable recovered Python source.
- `requirements-build.txt` — runtime/build dependencies.
- `installer.spec` — reproducible PyInstaller build configuration.
- `.github/workflows/decompile.yml` — recovery/decompilation workflow.
- `.github/workflows/build-exe.yml` — EXE build workflow.

## Recovery caveat

Recovered source is reconstructed from Python 3.8 bytecode. It can be edited and rebuilt, but decompilers cannot guarantee the original formatting, comments, or every high-level construct.

## Build

Use the GitHub Actions workflow **Build ZH Installer EXE**. It validates the entry point, installs Python 3.8-compatible build dependencies, runs PyInstaller, and uploads `ZH_Installer-WARU.exe` as an artifact.

The workflow also runs automatically when files under `src/`, `installer.spec`, `requirements-build.txt`, or the workflow itself change.
