# AGENTS.md

This file defines guidelines and guardrails for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these rules at all times when working in this repository.

### Protect Sensitive Data

- Do not read, log, print, or commit secret values such as API keys, tokens, passwords, or credentials — even partially or in truncated form. Reference variable names (e.g., `$SECRET_KEY`) rather than their values.
- Do not hardcode credentials, connection strings, or secrets into source files, configuration files, or tests.
- Do not expose or transmit personally identifiable information (PII) or customer data outside the application's defined data boundaries.
- Do not add logging statements or layout configurations that output sensitive fields such as passwords, session tokens, or authentication headers. This applies directly to log4js layout definitions in this repository.
- Treat any value sourced from environment variables or external secret stores as confidential.

### Prevent Unauthorized Deployments

- Do not push commits directly to `main`, `master`, or any production-facing branch without explicit human approval.
- Do not trigger, modify, or bypass CI/CD pipelines to initiate a production deployment without explicit approval.
- Do not create or push git tags that follow release naming conventions (e.g., `v*`) or publish the package to npm unless explicitly instructed.
- Do not bump the version in `package.json` or generate a new `package-lock.json` for a release without explicit instruction.
- Do not approve or merge pull requests autonomously.

### Avoid Destructive Operations

- Do not force-push (`git push --force`) to any branch.
- Do not delete remote branches or tags.
- Do not remove or overwrite files outside of version control (e.g., generated coverage reports, local log files) in a way that cannot be recovered.
- Do not run commands with broad, hard-to-reverse side effects (e.g., `rm -rf` on non-temporary directories) without explicit instruction.
- Prefer additive, reversible changes. When in doubt, stop and ask for human confirmation before proceeding.
