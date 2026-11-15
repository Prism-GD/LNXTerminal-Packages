# LNXTerminal Packages

Public APT repository for packages maintained specifically for **LNXTerminal**.

## Repository design

Standard Linux packages are downloaded directly from the official Ubuntu repositories. This repository is reserved for LNXTerminal-owned packages and customizations.

- Official Ubuntu packages: Ubuntu archive (`ports.ubuntu.com` for ARM devices)
- LNXTerminal packages: this repository
- Package manager: APT
- Ubuntu suite: `resolute`
- Component: `main`
- Architectures: `arm64` and `armhf`

## What belongs here

Only packages whose Debian package name begins with `lnxterminal-` are accepted by the publishing workflow. Planned examples include:

- `lnxterminal-core` — integration files and terminal configuration
- `lnxterminal-sudo` — sudo configuration inside the Ubuntu PRoot environment
- `lnxterminal-custom` — LNXTerminal customizations
- `lnxterminal-tools` — project-specific utilities

These are planned package names, not claims that the packages already exist.

## Adding a package

Place a genuine, reviewed `.deb` package in the `packages/` directory and run the **Publish LNXTerminal packages** workflow. The workflow validates its package name and architecture, creates the APT indexes, signs the Release metadata, verifies the repository with APT, and publishes the result.

Supported package architectures: `arm64`, `armhf`, and `all`.

## Repository signing

The public archive key is available at [keys/lnxterminal-archive-keyring.asc](keys/lnxterminal-archive-keyring.asc). The matching private key must remain only in the GitHub Actions secret `APT_SIGNING_PRIVATE_KEY`. Never commit or share the private key.

## APT sources

A LNXTerminal installation should configure both sources:

1. The official Ubuntu source matching the installed Ubuntu suite and device architecture.
2. This LNXTerminal source, using the published public key with `signed-by=`.

Do not disable APT signature verification. The exact public hosting endpoint and client installation instructions will be documented after remote hosting is tested.

## Important

- This is not an Ubuntu mirror.
- Ubuntu remains responsible for standard packages and their dependencies.
- The LNXTerminal repository must contain only project-owned packages.
- Package dependencies must be available from Ubuntu or from another explicitly configured trusted source.

## Project

Main application: https://github.com/Prism-GD/LNXTerminal
