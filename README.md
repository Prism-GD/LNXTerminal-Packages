# LNXTerminal Packages

Public package repository for **LNXTerminal**.

## Target platform

- Base distribution: **Ubuntu 26.04 LTS (Resolute Raccoon)**
- Ubuntu suite: `resolute`
- Initial package component: `main`
- Planned CPU architectures:
  - `arm64` — Android ABI `arm64-v8a`
  - `armhf` — Android ABI `armeabi-v7a`, when compatible

The Android ABI and Debian package architecture are related but are not interchangeable labels. The app/runtime must detect the device ABI and use a compatible Ubuntu root filesystem and package architecture.

## Repository status

This repository is being prepared. **It does not contain installable packages yet.** Do not add empty or placeholder `Packages`, `Release`, or `.deb` files: APT metadata must be generated from real, validated Debian packages.

Planned APT layout:

```text
dists/
  resolute/
    main/
      binary-arm64/
        Packages
      binary-armhf/
        Packages
pool/
  main/
    <package-name>/
      <version>/
        <package-file>.deb
```

The package index and Release metadata will be generated and checked automatically when actual packages are published. Repository signing will be configured before the repository is used by default.

## Important

- This is a repository for LNXTerminal-specific packages, not a mirror of the full Ubuntu archive.
- Ubuntu's official repositories will remain the source for standard Ubuntu packages.
- Packages must declare dependencies, versions, architecture, checksums, and maintainer metadata correctly.
- Never publish untrusted or unreviewed binaries.

## Project

Main application: https://github.com/Prism-GD/LNXTerminal
