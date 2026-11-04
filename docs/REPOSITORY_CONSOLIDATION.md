# Repository consolidation

**Canonical public repository:** [W3V0RA/signal-to-meeting](https://github.com/W3V0RA/signal-to-meeting)  
**Retired development-history repository:** [W3V0RA/signal-to-meeting-engine](https://github.com/W3V0RA/signal-to-meeting-engine)

On November 3, 2026, `signal-to-meeting` became the sole intended home for new source changes, documentation, issues, pull requests, security updates, and releases. The former `signal-to-meeting-engine` repository is retained only to preserve its historical commits and discussions, and should be archived in GitHub repository settings.

## What was retained

Both repositories' `main` branches were compared before consolidation. All functional code and supporting infrastructure already matched by Git blob SHA: `src/`, `web/`, `scripts/`, `tests/`, `config/`, `deploy/`, `schema/`, `fixtures/`, and `.github/`. The shared build, security, license-status, and implementation documentation also matched. **There was no missing feature or implementation in the old repository that needed to be reimplemented or copied.**

The canonical public repository also retains the improvements specific to public distribution:

- Repository-aware installation commands and setup instructions.
- Explicit MIT license metadata and the canonical repository URL in `package.json` and `package-lock.json`.
- `CONTRIBUTING.md`, which was absent from the earlier development repository.
- All of the engine's existing safety gates, tests, offline defaults, local installation flow, and integrations.

No production installation, credentials, database, email delivery, or deployed integration was moved by this repository-level consolidation.

## Original history and provenance

The original development repository contains nine commits and two merged pull requests at the time of consolidation:

- [Original commit history](https://github.com/W3V0RA/signal-to-meeting-engine/commits/main)
- [Pull request #1: Improve local installation and configurable outreach controls](https://github.com/W3V0RA/signal-to-meeting-engine/pull/1)
- [Pull request #2: Update GitHub account references](https://github.com/W3V0RA/signal-to-meeting-engine/pull/2)

The canonical repository was independently published on October 30, 2026, and does **not** share Git commit ancestry with the original. Keeping the original repository archived preserves that history without attempting a potentially disruptive unrelated-history merge.

## Maintainer rules

1. Make all future changes, reviews, issue reports, releases, and security fixes in [the canonical repository](https://github.com/W3V0RA/signal-to-meeting).
2. Do not sync commits back into the retired development repository or create releases from it.
3. Keep the original repository public and read-only using GitHub's **Archive this repository** setting. The README in that repository redirects readers here.
4. Before retiring any downstream integration, check that it does not depend on the original GitHub repository path. This step is not implied by identical code.
5. Do not commit runtime configuration, API keys, mailbox contents, or customer data.

## Moving a local installation

A fresh checkout is recommended because the repositories have unrelated Git histories:

```sh
git clone https://github.com/W3V0RA/signal-to-meeting.git
cd signal-to-meeting
npm run setup
npm start
```

**Do not blindly `git pull` from the new repository into an existing old-repository clone.** Preserve any unpublished local changes first, then migrate configuration and local data only through an intentional, reviewed process. Review [the installation guide](SETUP.md) and [operations and recovery guidance](OPERATIONS.md). This consolidation does not enable email sending: each installation still requires its own verified integration and human authorization.

## Completion checklist

- [x] Designate the canonical public repository.
- [x] Confirm functional code, configuration, and tests match the original.
- [x] Preserve public-distribution improvements and contributor instructions.
- [x] Document old commit and pull-request history.
- [x] Retire the old repository from active maintenance and link to the canonical location.
- [ ] Archive `W3V0RA/signal-to-meeting-engine` in GitHub's repository settings, then verify that GitHub displays its archived state.
