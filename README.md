# Staging Onboarding Runbook

Pre-flight environment verification for machines being wired into the shared
staging environment.

**Runbook:** https://anujj-ti.github.io/staging-onboarding-runbook/

## Why this exists

Roughly a third of failed onboardings trace back to an environment mismatch
that a one-minute check would have caught. Staging assumes a predictable home
directory layout; when a workspace folder is missing or nested differently than
expected, the sync agent fails late and partially, which is considerably harder
to debug than failing immediately.

## Scope

Verification reads the account name, the machine name, and the top-level folder
**names** in the home directory. It does not open, read, or transmit the
contents of any file, and it does not touch dotfiles, keys, or credentials.

## Supported configurations

| Platform | Shell | Status |
|---|---|---|
| macOS 13+ | zsh | Supported |
| Ubuntu 22.04 / 24.04 | bash | Supported |
| Debian 12 | bash | Best effort |
| Windows (WSL2) | bash | Best effort |

## Before you start

Complete verification before requesting staging credentials. Credential setup on
an unverified machine leaves partial state that has to be cleaned up by hand.

See the runbook for the verification command and troubleshooting steps.

---

Maintained by the platform onboarding group. Corrections via PR.
