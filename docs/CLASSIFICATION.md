---
visibility: product-public
---

# Content Classification Guidelines

This document defines the classification system for content in levo-agent-plugins and provides guidance for contributors.

## Classification Levels

### Product-Public

**Visibility:** `product-public`

Content that is:
- Safe for public GitHub repositories
- Free of internal infrastructure details
- Free of customer data or identifiers
- Suitable for open-source distribution

**All skills in this repository MUST be classified as `product-public`.**

### Internal (Not Permitted)

The following classifications are NOT permitted in this repository:

- **Internal** — Company-internal tools and configurations
- **Confidential** — Customer data, credentials, secrets
- **Restricted** — Security-sensitive implementation details

## Frontmatter Requirements

Every skill file (`SKILL.md`) must include visibility frontmatter:

```yaml
---
visibility: product-public
---
```

## Content Review Checklist

Before submitting content, verify:

### ✅ Allowed

- Public Levo MCP tool names and descriptions
- Generic configuration examples with placeholder values
- Links to public documentation (docs.levo.ai)
- Open-source license references
- Generic error handling patterns

### ❌ Prohibited

| Category | Examples |
|----------|----------|
| Internal Services | platform-services, internal APIs |
| Task Management | ClickUp, CU-* identifiers |
| Infrastructure | Istio configs, service mesh details |
| Auth Details | Descope Access Keys, tenant admin |
| Customer Data | Customer names, account IDs |
| Credentials | API keys, tokens, passwords |
| Internal URLs | *.levocloud.io, internal.levo.* |

## Automated Enforcement

The CI pipeline enforces these rules by:

1. **JSON Validation** — All JSON files must be syntactically valid
2. **Frontmatter Check** — Skills must have `visibility: product-public`
3. **Deny-List Scan** — Prohibited patterns are automatically detected
4. **Secret Scan** — Potential credentials are flagged

## Remediation

If CI fails due to classification issues:

1. Review the specific patterns flagged
2. Remove or redact prohibited content
3. Replace with generic examples or placeholders
4. Re-run validation locally before pushing

## Questions

Contact the platform team or open a discussion if you're unsure about content classification.
