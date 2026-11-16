# PIE.FileTransfer — Public installation packages

This repository distributes **installation binaries only** for proprietary PIE.FileTransfer, with a separately licensed TightVNC GPL source archive accompanying the binary. PIE application source, credentials, customer configuration and development history stay private.

## Stable Release assets

Historical stable releases through v1.2.265 contain four Slave-only assets. Unified releases beginning with v1.2.266 contain exactly six assets:

- PIEFileTransferSlaveSetup-X.Y.Z.exe — Windows x64 Slave installer. Initial releases are **UNSIGNED**.
- PIEFileTransferSlaveSetup-X.Y.Z.release.json — Slave product/version/size/SHA-256 and factual Authenticode status.
- PIEFileTransferMasterSetup-X.Y.Z.exe — Windows x64 Master installer. Initial unified releases are **UNSIGNED**.
- PIEFileTransferMasterSetup-X.Y.Z.release.json — Master product/version/size/SHA-256 and factual Authenticode status.
- tightvnc-2.8.90-src-gpl.zip — complete corresponding TightVNC 2.8.90 GPLv2 source.
- SHA256SUMS.txt — SHA-256 hashes covering both Setup EXEs, their metadata and GPL source.

The Slave installer includes the original, unmodified TightVNC 2.8.90 x64 MSI as an independently installed component. The Master package includes the separately verified, unmodified application-private TightVNC 2.8.90 Viewer. The full GPLv2 license and notices are bundled. The corresponding source ZIP is made available next to the Setup EXE in the **same GitHub Release**.

Official source: https://www.tightvnc.com/download/2.8.90/tightvnc-2.8.90-src-gpl.zip

## Verify downloaded installers

Download the Master and/or Slave Setup from **the same release tag** as the accompanying `*.release.json` metadata, `SHA256SUMS.txt`, and TightVNC corresponding source archive. The metadata must identify the same version, exact Setup filename, length, SHA-256, and actual Windows Authenticode status.

On Windows PowerShell, use `Get-FileHash -Algorithm SHA256 .\PIEFileTransferMasterSetup-X.Y.Z.exe` (or the Slave filename) and compare with both its matching release.json and `SHA256SUMS.txt`. Verify all assets belong to the same official stable Release. Checksums protect integrity; **they are not proof of the publisher's identity**. Do not execute a mismatched or unexpected installer.

## Manual installation and unsigned-binary warning

Master's Update Slave Components workflow can optionally download the latest stable GitHub Release or reuse a verified cache. Slave PCs never need Internet access. Downloading alone never starts an installation.

**IMPORTANT: Initial Setup executables are unsigned.** GitHub SHA-256 and SHA256SUMS.txt detect byte changes but do **not independently prove publisher identity** or show that a binary is safe. Windows may display SmartScreen or Unknown Publisher warnings. Master requires explicit consent for downloaded/cached packages and separately uses its existing target-version and installation confirmation.

## Licensing

PIE.FileTransfer remains proprietary. Open XML SDK 3.3.0 (DocumentFormat.OpenXml and DocumentFormat.OpenXml.Framework) is distributed under the MIT license with its full notice in each affected installed application's `ThirdParty/OpenXMLSDK/LICENSE.txt`. TightVNC is independently redistributed under GPLv2; this does not grant the right to link GPL TightVNC source into proprietary PIE products. Other dependency licenses and the independence of the two applications must be reviewed prior to public rollout.

See [RELEASE_POLICY.md](RELEASE_POLICY.md) and [SECURITY.md](SECURITY.md).

Master also retains the offline local Setup EXE selection workflow. User-selected external local Setup files are never deleted by the online cache cleanup.
