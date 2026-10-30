# Contributing

Install Node.js 24 or later, clone this repository, and create a branch for your change. No npm dependencies are required.

```sh
npm run check
```

The check runs isolated tests, synthetic evaluations and a heuristic privacy scan. Run it before opening a pull request. Describe the problem, the behavior your change produces and how you verified it. Include meaningful regression coverage for changes to approval, evidence, pacing or transport.

Use fictional fixtures and your own local ignored configuration. Never commit real prospect lists, mailbox messages, customer research, account identifiers, credentials, runtime databases or signing keys. Tests must remain offline and must not send email or create provider drafts. Preserve human approval, suppression, cancellation and fail-closed defaults.

Use issues for reproducible bugs and feature proposals. For suspected vulnerabilities, use this repository's Security tab to report privately; do not post credentials or private business data in public issues. See [SECURITY.md](SECURITY.md) for the security boundary.

Contributions to this repository are provided under its [MIT License](LICENSE).
