# Repository standards

This document is the common baseline for repositories under `lerston`. A repository may add stricter rules in `CONTRIBUTING.md` and `AGENTS.md`, but should not silently weaken these rules.

## Change path

- Direct commits to `main` are limited to typos and small documentation clarifications that do not change behavior.
- Code, configuration, automation, deployment, dependencies, interfaces and large documentation changes use a short-lived branch and pull request.
- One pull request addresses one reviewable outcome. Dependent work may use stacked pull requests.

## Required pull request context

Every non-trivial PR states:

- purpose and scope;
- risks and affected systems;
- automated and manual checks;
- deployment or live-application status;
- unverified scenarios;
- rollback procedure.

## Validation and merge

- All relevant CI checks pass before merge.
- Generated production files are rebuilt and committed when the repository tracks them.
- Documentation and changelog are updated with user-visible behavior.
- A merge never implies that a configuration was deployed or tested on hardware; that status is recorded explicitly.

## Releases

- Tags are created from verified commits in `main`.
- Software or device-facing projects use `vX.Y.Z`; multi-app repositories may use `<app>-vX.Y.Z`.
- A GitHub Release is added when users benefit from release notes or downloadable artifacts.

## Security and provenance

- Secrets, credentials, private keys, environment files, backups, execution data and sensitive device dumps stay out of Git, including private repositories.
- Third-party assets record their source and license or rights status.
- Historical observations include dates and are not presented as current live state.

## Keeping the standard coherent

When this baseline changes, review active repositories and update their local `CONTRIBUTING.md`, PR template and `AGENTS.md` in the same maintenance batch. Project-specific rules remain next to the project because they are part of its operational context.
