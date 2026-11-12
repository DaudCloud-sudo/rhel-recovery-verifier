# RHEL Recovery Verifier

A RHEL lab for restoring a selected backup into a test workspace, checking defined recovery requirements and retaining evidence of the result.

**Status: planning and repository setup. Recovery automation is not implemented. No recovery drill or production deployment has been verified.**

The first user is the project author operating a disposable local lab. Small teams running Linux services are a possible later audience; external use has not been established.

## Problem

A backup can finish successfully while recovery still fails. Required data may be excluded, restored files may have incorrect permissions, or a service may be unable to use its restored configuration and data.

This project will define what a successful recovery must establish and record which checks actually ran.

## Initial scope

The proposed first workflow uses restic for backup/restore and a small Python verifier for workload-specific checks. The manual procedure comes first.

- Restore an explicit snapshot into a fresh, disposable directory.
- Verify required regular files, SHA-256 contents and defined Linux file modes.
- Detect missing files, changed contents and mode mismatches.
- Record stage results, tool versions, timings and overall status.
- Keep application recovery marked as not run until it has its own checks.

## Design and next step

- [Implementation plan](docs/PLAN.md)
- [Proposed architecture](docs/ARCHITECTURE.md)
- [First recovery contract](docs/RECOVERY-CONTRACT.md)
- [First manual drill](docs/FIRST-DRILL.md)

There is no runnable verifier command yet. Start with the read-only RHEL prerequisite inventory in the first-drill guide.

| Capability | Status |
|---|---|
| Problem, architecture and first contract | Documented design |
| Manual RHEL backup/restore drill | Planned |
| Python file verifier and failure tests | Planned |
| Automated restore runner and report | Planned |
| systemd scheduling | Later milestone |
| Application recovery and storage experiments | Later profiles |

## Evidence standard

Each completed drill will identify the environment, snapshot, expected outcome, observed result and relevant output. Synthetic examples will be labelled. File recovery, application recovery and host recovery will have separate claims.

The initial same-VM exercise will test a procedure; it will not establish protection against losing the VM's storage.

Planning and repository preparation are AI-assisted. Hands-on implementation and verification are intended to follow a user-attempt, review and variation workflow. License selection is pending.
