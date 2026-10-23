# PIE.FileTransfer — Public installation packages

This repository distributes **installation binaries only** for PIE.FileTransfer. The application source, credentials, customer-specific configuration, and development history are maintained separately in a private repository.

## What is distributed

Each stable GitHub Release uses a tag in the form `vX.Y.Z` and contains:

- `PIEFileTransferSlaveSetup-X.Y.Z.exe` — Windows x64 Slave installer.
- `PIEFileTransferSlaveSetup-X.Y.Z.release.json` — verified build metadata, including the actual code-signing status and SHA-256.
- `SHA256SUMS.txt` — file hashes for administrator verification.

A Master installation may use **Update Slave Components → GitHub latest stable Release** to download a verified installer and send it to selected Slave PCs using the existing authenticated local-network update workflow. Slave PCs **do not need Internet access** and do not update themselves from GitHub.

Installation is a privileged operation. Downloading does not automatically deploy or install a package. Check the target PCs and version before confirming deployment.

## Trust and redistributing packages

Only releases passing product/version/hash/signature and distribution-authorization gates should be published. Independent publisher identity verification is different from a SHA-256 hash: hashes detect changes to bytes but do not establish publisher identity.

This repository grants **no additional license** to proprietary first-party software. Third-party components remain subject to their respective licenses. Any required third-party notices, source-offer obligations, and binary redistribution permissions must be reviewed and satisfied *before* making an installer public.

See [RELEASE_POLICY.md](RELEASE_POLICY.md) for publication rules and [SECURITY.md](SECURITY.md) for security reporting.

## Offline deployment

Master also supports selecting an existing local Setup EXE and reusing previously verified cached downloads. User-provided local installation files are never deleted by the Master-managed online cache cleanup.
