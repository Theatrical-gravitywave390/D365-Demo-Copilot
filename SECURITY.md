# Security Policy

## Reporting a Vulnerability

**Do NOT open a public GitHub issue for security vulnerabilities.**

Instead, please email: **sean.galliher@gmail.com**

Include:
- A description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

You should receive a response within 48 hours.

## Security Considerations

This project handles sensitive credentials:

- **D365 browser sessions** — The agent uses Playwright to control an authenticated browser. The `auth_state.json` file contains session cookies and should never be committed.
- **API keys** — LLM provider keys are stored in `.env` files which are gitignored.
- **Dataverse OAuth** — Client credentials for Dataverse API access are stored in `.env`.

Always ensure:
- `.env` and `auth_state.json` are in `.gitignore` (they are by default)
- Never hardcode credentials in source code
- Rotate API keys if they are accidentally exposed
