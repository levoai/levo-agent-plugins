# Contributing to Levo Agent Plugins

Thank you for your interest in contributing to Levo Agent Plugins! This document provides guidelines for contributions.

## Code of Conduct

Be respectful, inclusive, and constructive. We welcome contributors of all backgrounds and experience levels.

## Before You Contribute

1. **Read the CLA**: By submitting a contribution, you agree to the [Contributor License Agreement](CLA.md).
2. **Check existing issues**: Look for open issues or discussions before starting work.
3. **Open an issue first**: For significant changes, open an issue to discuss your proposal.

## Accepted Contributions

We welcome contributions that:

- **Fix bugs** in existing skills
- **Improve documentation** (typos, clarity, examples)
- **Add tests** for existing functionality
- **Enhance error handling** and user experience
- **Add new skills** that use Levo MCP tools (`levo_list_applications`, `levo_get_application_details_by_name`, `levo_list_application_endpoints`)
- **Improve CI/CD** workflows and validation

## Not Accepted

The following contributions will be rejected:

### Content Restrictions

- **Platform-services references** — Internal platform infrastructure details
- **ClickUp integrations** — Internal task management references
- **CU-* identifiers** — Internal ticket/task identifiers
- **Istio configurations** — Internal service mesh details
- **Tenant Admin references** — Multi-tenant administration details
- **Descope Access Key references** — Authentication infrastructure secrets
- **Internal API endpoints** — Non-public Levo API references
- **Customer-specific data** — Any customer names, IDs, or configurations
- **Internal tooling** — References to internal-only tools or services

### Technical Restrictions

- **Hardcoded credentials** — API keys, tokens, passwords
- **Internal URLs** — Non-public endpoints or services
- **Private IP addresses** — Internal network references
- **Environment-specific configs** — Production/staging environment details

## How to Contribute

### 1. Fork and Clone

```bash
git clone https://github.com/YOUR_USERNAME/levo-agent-plugins.git
cd levo-agent-plugins
```

### 2. Create a Branch

```bash
git checkout -b feature/your-feature-name
```

### 3. Make Changes

- Follow existing code style and conventions
- Add appropriate frontmatter to skill files
- Include `visibility: product-public` in all skills
- Test your changes locally

### 4. Validate

```bash
# Run JSON validation
npm run validate

# Or manually validate marketplace files
npx jsonlint .claude-plugin/marketplace.json
npx jsonlint .agents/plugins/marketplace.json
```

### 5. Commit

Write clear, descriptive commit messages:

```bash
git commit -m "feat(skill): add endpoint discovery capability"
```

### 6. Push and Create PR

```bash
git push origin feature/your-feature-name
```

Then open a Pull Request against the `main` branch.

## Pull Request Guidelines

- Fill out the PR template completely
- Reference any related issues
- Ensure CI checks pass
- Wait for review from maintainers

## Skill File Format

Skills must follow this structure:

```markdown
---
visibility: product-public
triggers:
  - description of when to activate
---

# Skill Name

Brief description of what this skill does.

## Prerequisites

List any requirements.

## Instructions

Step-by-step guide for the agent.
```

## Questions?

- Open a [GitHub Discussion](https://github.com/levoai/levo-agent-plugins/discussions)
- Email: oss@levo.ai

## License

By contributing, you agree that your contributions will be licensed under the [Apache License 2.0](LICENSE).
