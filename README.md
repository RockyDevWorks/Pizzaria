# PIZZARIA

**Build Together. Ship Together.**

Product Overview · v0.1.0

## Overview

Pizzaria is a standalone, web-based platform for managing multi-repository version sets, coordinating integration tests, and orchestrating software releases through GitHub Actions.

It enables developers to combine independently built and tested repositories into one immutable, version-locked release configuration, without manually maintaining a separate orchestration repository or GitHub Actions workflows.

## How it works

1. **Connect GitHub**  
   Authorize repositories and create a Workspace.

2. **Select Components**  
   Choose repositories with successful builds and unit tests.

3. **Create Recipe & Lockfile**  
   Define the version set and pin exact commits and artifact digests.

4. **Bake**  
   Trigger GitHub Actions with the combined Lockfile.

5. **Test, Bundle & Release**  
   Run integration tests, assemble artifacts and publish verified releases.

## Core terminology

| Term | Definition |
|---|---|
| Workspace | Collection of related GitHub repositories |
| Component | Independently verified repository build |
| Recipe | Definition of the component version set |
| Lockfile | Immutable record of exact revisions and artifact identities |
| Bake | Resolve, verify and dispatch a locked version set |
| Bundle | Combined artifact produced by GitHub Actions |
| Pipeline | Integration or release workflow |
| Release | Published, verified Bundle |

## Key capabilities — v0.1.0

- GitHub authentication and repository connection.
- Web dashboard for Workspaces, Components and builds.
- Visual Recipe configuration and version selection.
- Combined immutable Lockfile generation.
- Automated GitHub Actions workflow provisioning and dispatch.
- Integration pipeline execution and status monitoring.
- Bundle tracking and release publishing.
- Release history and traceability to exact source commits.

## Proposed technology stack

| Layer | Technology |
|---|---|
| Frontend | React + TypeScript |
| Backend | Rust + Axum |
| Database | PostgreSQL |
| GitHub integration | GitHub App |
| Pipeline engine | GitHub Actions only |
| Artifact storage | GitHub Actions artifacts / GitHub Releases |
| Execution model | Managed GitHub execution repository per Workspace |

## Product boundaries

Pizzaria manages version selection, locking, orchestration and release visibility. Individual repositories remain responsible for their own unit tests and builds. GitHub Actions performs integration testing, Bundle assembly and release publishing.

Pizzaria does not implement its own CI runners, build engine, or support additional CI providers in v0.1.0.

## Initial use case

The first Workspace will be LINGUA FRANCA, combining elang-rs, elang-hub, aion-rs and elang-studio into a reproducible, integration-tested release.

**Product principle: One Recipe. One Lockfile. One verified release.**
