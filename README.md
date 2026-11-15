# LNXTerminal Packages

Public APT package repository for **LNXTerminal**.

## Target platform

- Base distribution: **Ubuntu 26.04 LTS (Resolute Raccoon)**
- Ubuntu suite: `resolute`
- Component: `main`
- Published architecture: `arm64` (Debian architecture; Android ABI `arm64-v8a`)
- Planned architecture: `armhf` (Android ABI `armeabi-v7a`), not yet populated with packages

The Android ABI and Debian package architecture are related but are not interchangeable labels. The app/runtime must detect the device ABI and use a compatible Ubuntu root filesystem and package architecture.

## Repository status

The repository now contains real Ubuntu ARM64 `.deb` packages and generated APT indexes. The Release metadata is signed with the LNXTerminal archive key. The publishing workflow also verifies the repository using an APT client before publishing.

APT layout:

```text
dists/
  resolute/
    InRelease
    Release
    Release.gpg
    main/
      binary-arm64/
        Packages
        Packages.gz
pool/
  main/
    <package-name>/
      <version>/
        <package-file>.deb
keys/
  lnxterminal-archive-keyring.asc
```

**The repository has not yet been tested as a remotely hosted APT endpoint.** Do not add it to a device until its hosting URL and end-to-end client test are confirmed.

## Signing key

The public archive key is available at [keys/lnxterminal-archive-keyring.asc](keys/lnxterminal-archive-keyring.asc). The matching private key must remain only in the GitHub Actions repository secret named `APT_SIGNING_PRIVATE_KEY`; never commit or share the private key.

## Important

- This is a curated repository, not a mirror of the complete Ubuntu archive.
- Ubuntu's official repositories remain the source for standard Ubuntu packages and dependencies not included here.
- Packages must declare dependencies, versions, architecture, checksums, and maintainer metadata correctly.
- Never publish untrusted or unreviewed binaries.

## Project

Main application: https://github.com/Prism-GD/LNXTerminal
