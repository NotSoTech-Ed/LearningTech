# Repository Change Audit Evidence

## Scope and purpose

This is an example evidence pack generated from the current Git working branch for learning purposes. It tests repository change traceability and approval evidence; it does **not** audit a banking production environment or prove that no unapproved changes exist outside this repository.

| Field | Observed value |
|---|---|
| Repository | `NotSoTech-Ed/LearningTech` |
| Audited branch | `information-security-grc-learning` |
| Local HEAD | `be5cae8dfda0028c2450ea355b1301de755d739b` |
| Comparison baseline used locally | `learningtech/LeaningRepository` at `c8efbaf` when the audit was run |
| Current remote default branch | `LeaningRepository` |
| GitHub PR | [#9 — Add change management demonstration guide](https://github.com/NotSoTech-Ed/LearningTech/pull/9) |
| PR merge commit | `b46a5835770632e7eb35f11ccb064109a09103ba` |
| Assessment date | 2026-09-22 |
| Evidence boundary | Git history, GitHub pull request metadata, repository paths, and diffs |

The comparison baseline was a local remote-tracking reference. Refresh it with `git fetch` before reusing this evidence. The remote branch and PR metadata are the authoritative records for merge status.

## 1. Population evidence

The local comparison produced one commit ahead of the local baseline:

| Commit | Author | Author date | Subject | Files |
|---|---|---|---|---:|
| `be5cae8dfda0028c2450ea355b1301de755d739b` | BatmanJoined | 2026-09-22 09:03:03 +0530 | Add change management demonstration guide | 2 |

Changed paths:

| Change type | Path | Lines |
|---|---|---:|
| Modified | `docs/compliance/change-management-audit/README.md` | +1 |
| Added | `docs/compliance/change-management-audit/demonstration-guide.md` | +277 |

### Reproducible commands

Run from the repository root:

```bash
git fetch <remote> LeaningRepository
git status --short --branch
git merge-base HEAD <remote>/LeaningRepository
git rev-list --count <remote>/LeaningRepository..HEAD
git log --format='%H|%an|%ae|%ad|%s' --date=iso-strict <remote>/LeaningRepository..HEAD
git diff --name-status <remote>/LeaningRepository...HEAD
git diff --stat <remote>/LeaningRepository...HEAD
```

These commands establish the local commit population and changed-file population. They do not establish production deployment or approval by themselves.

## 2. Commit evidence

Observed commit metadata:

```text
commit be5cae8dfda0028c2450ea355b1301de755d739b
Author:     BatmanJoined <ask_adrith@gmail.com>
AuthorDate: Tue Sep 22 09:03:03 2026 +0530
Commit:     BatmanJoined <ask_adrith@gmail.com>
CommitDate: Tue Sep 22 09:03:03 2026 +0530

Add change management demonstration guide
```

The commit contains the required co-author trailer:

```text
Co-authored-by: Copilot App <223556219+Copilot@users.noreply.github.com>
```

This proves authorship metadata and content change, not independent approval.

## 3. Pull-request approval evidence

GitHub PR #9 provides the repository-level approval and merge evidence:

| Field | Observed value |
|---|---|
| Title | Add change management demonstration guide |
| Base | `LeaningRepository` |
| Head | `information-security-grc-learning` |
| PR state | Merged |
| PR commit | `be5cae8dfda0028c2450ea355b1301de755d739b` |
| Merge commit | `b46a5835770632e7eb35f11ccb064109a09103ba` |
| Merged at | 2026-09-22 03:33:12 UTC |
| Changed files | 2 |
| Link | https://github.com/NotSoTech-Ed/LearningTech/pull/9 |

### What this evidence supports

- The change was proposed through a pull request.
- The pull request targeted the repository default branch.
- GitHub recorded the pull request as merged.
- The merged change contains the two documented paths.

### What this evidence does not support

- That a required independent reviewer approved the pull request, unless the PR review record is separately inspected.
- That branch protection prevented bypass.
- That the commit was deployed to any runtime environment.
- That the repository contains every change made to production.
- That no force-push, administrator bypass, or external mirror change occurred.

## 4. Content and integrity evidence

The changed content is documentation only:

- `README.md` adds the demonstration-guide link.
- `demonstration-guide.md` adds fictional banking examples and audit procedures.

There is no application source, infrastructure code, deployment manifest, database migration, secret, executable, or production configuration in this change.

The working-tree quality check returned no whitespace errors:

```text
git diff --check
```

The relative Markdown-link check returned no missing local targets for the repository documentation.

## 5. Control test results

| Control test | Result | Evidence | Limitation |
|---|---|---|---|
| Change is identifiable | Pass | Commit SHA, PR #9, merge SHA | Repository scope only |
| Change has an attributable author | Pass | Commit author and email | Author identity is Git metadata |
| Change has a recorded approval path | Partially evidenced | PR #9 merged into `LeaningRepository` | Independent review and branch-protection settings not captured here |
| Changed files are traceable | Pass | Commit diff and PR file list | Does not cover external copies |
| Change is tested for documentation integrity | Pass | `git diff --check`; link check | Not a software test |
| Change was deployed | Not applicable / not evidenced | No deployment record in repository | No production environment was audited |
| Change was validated after deployment | Not evidenced | No runtime or release telemetry | Documentation-only change |
| Population is complete | Not concluded | Git comparison only | No GitHub audit-log export, mirror, CI/CD, or production source |
| No unapproved changes exist | Not concluded | No unmatched GitHub/production reconciliation | This conclusion would exceed the evidence |

## 6. Evidence limitations

The following evidence was not available in this repository audit:

- GitHub organisation audit log and branch-protection settings.
- Required-reviewer configuration and review dismissal history.
- CI/CD run, artifact, deployment, and environment approval records.
- Cloud, host, database, network, SaaS, or vendor change logs.
- Production configuration snapshots and runtime monitoring.
- Complete list of force pushes, deleted branches, or administrator actions.
- Service-management tickets or emergency-change records.

These limitations are material if the audit objective is to conclude on production change management. Obtain and reconcile those sources before issuing a banking control conclusion.
