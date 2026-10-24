# PIE.FileTransfer — Public installation packages

This repository distributes **installation binaries only** for proprietary PIE.FileTransfer, with a separately licensed TightVNC GPL source archive accompanying the binary. PIE application source, credentials, customer configuration and development history stay private.

## Stable Release assets

Each public stable Release (tag vX.Y.Z) contains exactly four assets:

- PIEFileTransferSlaveSetup-X.Y.Z.exe — Windows x64 Slave installer. Initial releases are **UNSIGNED**.
- PIEFileTransferSlaveSetup-X.Y.Z.release.json — final product/version/size/SHA-256 and factual Authenticode status (NotSigned for unsigned builds).
- tightvnc-2.8.90-src-gpl.zip — complete corresponding TightVNC 2.8.90 GPLv2 source.
- SHA256SUMS.txt — SHA-256 hashes covering Setup EXE, metadata and GPL source.

The installer includes the original, unmodified TightVNC 2.8.90 x64 MSI as an independently installed component. The full GPLv2 license and notices are bundled. The corresponding source ZIP is made available next to the Setup EXE in the **same GitHub Release**.

Official source: https://www.tightvnc.com/download/2.8.90/tightvnc-2.8.90-src-gpl.zip

## Manual installation and unsigned-binary warning

Master's Update Slave Components workflow can optionally download the latest stable GitHub Release or reuse a verified cache. Slave PCs never need Internet access. Downloading alone never starts an installation.

**IMPORTANT: Initial Setup executables are unsigned.** GitHub SHA-256 and SHA256SUMS.txt detect byte changes but do **not independently prove publisher identity** or show that a binary is safe. Windows may display SmartScreen or Unknown Publisher warnings. Master requires explicit consent for downloaded/cached packages and separately uses its existing target-version and installation confirmation.

## Licensing

PIE.FileTransfer remains proprietary. TightVNC is independently redistributed under GPLv2; this does not grant the right to link GPL TightVNC source into proprietary PIE products. Other dependency licenses and the independence of the two applications must be reviewed prior to public rollout.

See [RELEASE_POLICY.md](RELEASE_POLICY.md) and [SECURITY.md](SECURITY.md).

Master also retains the offline local Setup EXE selection workflow. User-selected external local Setup files are never deleted by the online cache cleanup.
