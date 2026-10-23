# AGENTS.md

This file defines guidelines and guardrails for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these rules at all times when working in this repository.

### Protect Sensitive Data

- Do not read, log, print, or commit secret values such as API keys, tokens, passwords, or credentials. Reference variable names (e.g., `$SECRET_KEY`) rather than their values.
- Do not hardcode credentials, database connection strings, or secrets into source files, configuration files, or test fixtures.
- Do not expose or transmit personally identifiable information (PII) or customer/warehouse data outside the application's defined data boundaries.
- Do not add logging statements that output sensitive fields such as passwords, session tokens, or customer personal details.
- Treat any value sourced from environment variables or external secret stores as confidential.
- Do not include sensitive data in commit messages, comments, or documentation.

### Prevent Unauthorized Deployments

- Do not push commits directly to `main`, `master`, or any production-targeting branch without explicit human approval.
- Do not trigger, invoke, or modify CI/CD pipelines or deploy workflows that target production or staging environments without explicit instruction from a human reviewer.
- Do not create or push release tags unless explicitly instructed to do so.
- Do not modify infrastructure-as-code or deployment configuration in ways that would cause an immediate or automatic deployment to a live environment.
- Do not approve or merge pull requests autonomously.

### Avoid Destructive Operations

- Do not force-push (`git push --force`) to any branch under any circumstances.
- Do not delete branches, tags, or remote refs.
- Do not drop, truncate, or irreversibly alter database tables or records. Do not run migrations that destroy data without explicit human approval.
- Do not run irreversible Django migrations (e.g., removing columns or tables) without a rollback path being reviewed and approved first.
- Do not execute commands that have broad, hard-to-reverse side effects (e.g., `rm -rf` on non-temporary directories, bulk data deletion) without explicit instruction.
- Do not delete or destroy cloud infrastructure resources (e.g., databases, storage buckets, VMs) without explicit human sign-off.
- Prefer additive, reversible changes. When in doubt, stop and ask for human confirmation before proceeding.
