# Security Policy

PIE.FileTransfer is a Windows industrial PC management and Slave component deployment system. Public downloads must be treated as executable software with elevated installation effects.

## Reporting

Please report suspected security vulnerabilities **privately** to the repository maintainers through an approved confidential channel. Do not post exploit details, credentials, internal diagnostics, or installation-token materials in public issues.

## Distribution integrity

- Stable public Releases must include a signed and trusted Windows installer from the approved publisher, plus independently verifiable SHA-256 metadata.
- GitHub-generated asset SHA-256 hashes help detect file changes, but alone do not attest the publisher's identity.
- Releases should be immutable after final publication. Do not replace a published asset to fix a faulty build; produce a new version.
- Master downloads a package only after explicit user action; Slave endpoints never connect to GitHub as part of the update mechanism.
- A download does not by itself trigger remote installation. Master's existing authorized Slave preflight/confirmation and request-ID/installed-version verification remain mandatory.

If publication prerequisites are not satisfied, use controlled LAN delivery from a known local Setup EXE instead of issuing an unverified public binary.
