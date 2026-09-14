# Security Policy for DiNotes

Security and data isolation are critical priorities for DiNotes.

---

## Supported Versions

Security updates are applied exclusively to the `main` branch.

| Version | Supported |
| :--- | :--- |
| `0.0.0` (main branch) | :white_check_mark: Yes |
| Older commits / forks | :x: No |

---

## Reporting a Vulnerability

If you discover a security vulnerability in DiNotes, please **DO NOT** open a public issue.

Report vulnerabilities directly to the maintainer:
- **Maintainer**: `@TheVicky1` via GitHub.

Include:
- Summary of the vulnerability
- Steps to reproduce
- Affected components or API endpoints

---

## Firebase & Data Isolation Safeguards

- All client-side queries and mutations are isolated per authenticated user (`request.auth.uid == resource.data.userId`).
- Never commit actual API keys or credentials to public Git repositories.
- Keep `.env` files added to `.gitignore`.
