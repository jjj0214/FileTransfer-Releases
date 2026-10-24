# Security Policy

PIE.FileTransfer performs privileged Windows installation on managed equipment. Public installers must be treated as sensitive operational software.

## Reporting

Please report vulnerabilities privately to the maintainers through a confidential channel. Do not post credentials, tokens, exploit details or internal system configurations in public issues.

## Unsigned Setup limitations and safeguards

- **Initial public Slave Setup releases may be unsigned.** The sidecar and release notes must identify the actual status as NotSigned/UNSIGNED without implying a verified code-signing publisher.
- GitHub-provided SHA-256 and SHA256SUMS.txt verify bytes but do **not independently establish publisher identity or build trust**. GitHub compromise could affect both the binary and its published checksum.
- The unsigned path requires an explicit publish-time acknowledgment and a separate Draft-to-Publish approval, plus exact version, file size, actual Authenticode status, final sidecar, and matching remote SHA-256 checks.
- Master requires consent before an online/cached Setup is used, followed by the existing authenticated LAN transfer and Slave installation confirmation. Slave endpoints never download packages directly from GitHub.
- Avoid disabling SmartScreen or antivirus as an installation workaround. An unknown publisher warning can appear for unsigned installers.
- TightVNC's independent original 2.8.90 MSI is distributed under GPLv2 with full license and notices. Its matching GPL source ZIP must be alongside the binary in the same immutable public Release.
- Never replace an immutable released asset. Publish a new version if a mistake needs correction.

Independent Windows publisher authentication is not supplied by an unsigned release, even when an asset digest matches.
