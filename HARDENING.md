<!-- markdownlint-disable -->

# Hardening Report: Swatinem--rust-cache/v2.8.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **Swatinem--rust-cache/v2.8.1** was hardened automatically. 17 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes, making the workflow vulnerable to supply-chain attacks if the tag is moved. Failing references: `actions/checkout@v5` (line 21).

Locations:

- `.github/workflows/buildjet.yml:21`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `actions/checkout@v5` (line 19), `actions/setup-node@v5` (line 22), `actions/upload-artifact@v4` (line 38).

Locations:

- `.github/workflows/check-dist.yml:19`
- `.github/workflows/check-dist.yml:22`
- `.github/workflows/check-dist.yml:38`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `actions/checkout@v5` (line 21), `taiki-e/install-action@cargo-llvm-cov` (line 25).

Locations:

- `.github/workflows/coverage.yml:21`
- `.github/workflows/coverage.yml:25`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `dependabot/fetch-metadata@v2` (line 15), `actions/checkout@v5` (line 18), `actions/setup-node@v5` (line 33).

Locations:

- `.github/workflows/dependabot.yml:15`
- `.github/workflows/dependabot.yml:18`
- `.github/workflows/dependabot.yml:33`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `actions/checkout@v5` (line 22).

Locations:

- `.github/workflows/git-registry.yml:22`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `actions/checkout@v5` (line 21).

Locations:

- `.github/workflows/install.yml:21`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `actions/checkout@v5` (line 21).

Locations:

- `.github/workflows/simple.yml:21`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `actions/checkout@v5` (line 21).

Locations:

- `.github/workflows/target-dir.yml:21`

### unpinned-uses (severity: high)

Workflow uses action references pinned to mutable tags instead of immutable 40-character SHA commit hashes. Failing references: `actions/checkout@v5` (line 21).

Locations:

- `.github/workflows/workspaces.yml:21`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/buildjet.yml:1`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/check-dist.yml:1`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/coverage.yml:1`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/git-registry.yml:1`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/install.yml:1`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/simple.yml:1`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/target-dir.yml:1`

### missing-permissions (severity: medium)

Workflow has no top-level `permissions:` block and no job-level `permissions:` block on any job. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad.

Locations:

- `.github/workflows/workspaces.yml:1`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses, missing-permissions

**Notes:**

Fixed all 9 workflow files:
- Pinned actions/checkout@v5 to SHA fbc6f3992d24b796d5a048ff273f7fcc4a7b6c09 in all 8 files that used it
- Pinned actions/setup-node@v5 to SHA a0853c24544627f65ddf259abe73b1d18a591444 in check-dist.yml and dependabot.yml
- Pinned actions/upload-artifact@v4 to SHA ea165f8d65b6e75b540449e92b4886f43607fa02 in check-dist.yml
- Pinned taiki-e/install-action@cargo-llvm-cov to SHA 2d2710c179509122228fa1f6bb32c8e3c78b21a9 in coverage.yml
- Pinned dependabot/fetch-metadata@v2 to SHA 21025c705c08248db411dc16f3619e6b5f9ea21a in dependabot.yml
- Added `permissions: {}` top-level block to buildjet.yml, check-dist.yml, coverage.yml, git-registry.yml, install.yml, simple.yml, target-dir.yml, and workspaces.yml
- dependabot.yml already had a permissions block (contents: write, pull-requests: write) needed for its automerge functionality, so it was preserved as-is

