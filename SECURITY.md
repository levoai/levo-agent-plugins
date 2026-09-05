# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| main    | :white_check_mark: |

## Reporting a Vulnerability

We take security seriously. If you discover a security vulnerability in Levo Agent Plugins, please report it responsibly.

### How to Report

**DO NOT** create a public GitHub issue for security vulnerabilities.

Instead, please report security issues via email:

**Email:** security@levo.ai

### What to Include

Please include the following in your report:

1. **Description** — A clear description of the vulnerability
2. **Impact** — The potential impact if exploited
3. **Steps to Reproduce** — Detailed steps to reproduce the issue
4. **Affected Components** — Which files or skills are affected
5. **Suggested Fix** — If you have one (optional)

### Response Timeline

- **Acknowledgment:** Within 48 hours
- **Initial Assessment:** Within 5 business days
- **Resolution Target:** Depends on severity
  - Critical: 7 days
  - High: 14 days
  - Medium: 30 days
  - Low: 90 days

### What Happens Next

1. We will acknowledge receipt of your report
2. We will investigate and validate the issue
3. We will work on a fix and coordinate disclosure
4. We will credit you in the security advisory (unless you prefer anonymity)

## Security Best Practices

When using these plugins:

1. **Never commit credentials** — Use MCP configuration for authentication
2. **Review tool permissions** — Understand what each MCP tool can access
3. **Keep dependencies updated** — Regularly update your MCP client
4. **Use least privilege** — Only enable the tools you need

## Scope

This security policy applies to:

- All skills in this repository
- Configuration files and templates
- CI/CD workflows
- Documentation

## Out of Scope

The following are out of scope for this repository:

- Vulnerabilities in the Levo platform itself (report to security@levo.ai separately)
- Vulnerabilities in third-party MCP clients
- Social engineering attacks

## Recognition

We appreciate security researchers who help keep Levo Agent Plugins secure. Contributors who report valid vulnerabilities will be acknowledged in our security advisories.

Thank you for helping keep our community safe!
