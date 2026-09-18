# Contributing to Obsernia Projects

Thank you for helping improve Obsernia's open-source observability, IT monitoring, and cybersecurity projects. Contributions of code, documentation, tests, bug reports, operational experience, and design feedback are welcome.

This document provides organization-wide defaults. Instructions in an individual repository's documentation take precedence where they differ.

## Before You Contribute

- Read the repository's `README`, documentation, license, and any project-specific contribution guidance.
- Search existing issues and pull requests before opening a new one.
- For a substantial change, open a feature request or discussion first so that scope and design can be agreed before significant work begins.
- Follow our [Code of Conduct](CODE_OF_CONDUCT.md) in all project spaces.
- Never include credentials, private keys, access tokens, customer data, internal hostnames, unredacted logs, or other sensitive information in a contribution.

## Reporting Bugs

Use the repository's bug-report template when one is available. A useful report includes:

- A clear, descriptive title.
- The affected project version, commit, or container image tag.
- The operating system, runtime, deployment model, and relevant dependencies.
- Minimal steps to reproduce the problem.
- The expected and actual behavior.
- Sanitized logs, traces, metrics, screenshots, or a minimal reproduction, where helpful.
- Any workaround and an assessment of operational impact.

Reduce the report to the smallest reproducible example where practical. Remove secrets and identifying infrastructure or customer data before attaching diagnostic output.

If the issue could expose data, bypass access controls, compromise a system, or otherwise represent a security vulnerability, **do not open a public issue**. Follow the instructions in [SECURITY.md](SECURITY.md).

## Requesting Features

Open a feature request in the most relevant repository and describe:

- The problem or operational need, not only the proposed implementation.
- The users and environments affected.
- The desired outcome and possible alternatives.
- Compatibility, performance, privacy, security, and migration considerations.
- Examples of relevant telemetry, workflows, or integrations, with sensitive data removed.

Maintainers may ask for clarification, suggest a smaller scope, or decline proposals that do not fit the project's direction or maintenance capacity.

## Preparing a Change

1. Fork the repository unless you have permission to create branches directly.
2. Create a branch from the repository's current default branch.
3. Make one focused change, including tests and documentation where appropriate.
4. Run the repository's documented formatting, linting, test, build, and security checks.
5. Open a pull request against the default branch unless the repository states otherwise.

### Branches

Follow repository-specific naming rules when present. Otherwise, use a short, descriptive name with a category prefix, for example:

- `feat/add-prometheus-exporter`
- `fix/alert-deduplication`
- `docs/deployment-guide`
- `test/parser-edge-cases`
- `chore/update-dependencies`

Do not publish exploit code or vulnerability details on a normal branch or public fork. Security fixes should be coordinated through the private process described in [SECURITY.md](SECURITY.md).

### Commits

- Keep commits small, coherent, and reviewable.
- Write an imperative, descriptive subject line, such as `Fix timeout handling in probe scheduler`.
- Explain the reason for non-obvious changes in the commit body.
- Reference the relevant issue when appropriate.
- Avoid mixing formatting, refactoring, generated files, and behavioral changes without a clear need.
- Preserve meaningful attribution and comply with the licenses of all third-party material.

Use Conventional Commits only when the repository requires or already follows that convention. Before requesting review, clean up temporary or accidental commits while preserving useful review history.

### Tests and Quality

Add or update tests for changed behavior. Depending on the project, this may include unit, integration, end-to-end, regression, compatibility, performance, or security tests.

Tests should be deterministic, isolated, and safe to run. They must not depend on production credentials, customer systems, or destructive actions. Use synthetic and sanitized fixtures. For monitoring and observability changes, consider failure modes, partial data, high-cardinality inputs, timeouts, retries, clock differences, and degraded dependencies.

If a relevant test cannot be added or run, explain why in the pull request and describe the validation performed instead.

## Pull Requests

A pull request should:

- Have a concise title and explain what changed and why.
- Be limited to a reviewable scope.
- Link related issues using GitHub keywords where appropriate.
- Describe testing performed and the environments used.
- Identify compatibility, deployment, configuration, migration, performance, privacy, and security effects.
- Update user-facing documentation, examples, schemas, and release notes when required.
- Include sanitized screenshots or sample output for visible changes.
- Pass all required automated checks.

Mark unfinished work as a draft. Respond constructively to review, and resolve conversations only when the concern has been addressed or agreement has been reached. Maintainers may edit, squash, rebase, or close a pull request to keep project history and scope manageable.

By submitting a contribution, you affirm that you have the right to provide it and that it may be distributed under the repository's license. Do not submit copied code or assets without compatible licensing and required attribution.

## Security-Sensitive Contributions

Treat anything involving authentication, authorization, cryptography, secret handling, network boundaries, parsers, agents, collectors, privileged execution, or telemetry containing personal or infrastructure data as security-sensitive.

Do not disclose suspected vulnerabilities in issues, discussions, pull requests, public forks, commit messages, or chat channels. Use the private reporting process in [SECURITY.md](SECURITY.md). Maintainers will coordinate validation, remediation, and disclosure with the reporter.

## Review and Acceptance

Submitting a contribution does not guarantee acceptance. Maintainers consider correctness, security, maintainability, compatibility, project direction, and long-term support cost. They may request changes or close inactive contributions. Respectful disagreement is welcome; final decisions rest with the maintainers of the affected repository.

Thank you for contributing to safer and more dependable systems.
