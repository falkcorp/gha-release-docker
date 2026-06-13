<!-- file: .github/copilot-instructions.md -->
<!-- version: 2.4.0 -->
<!-- guid: 4d5e6f7a-8b9c-0d1e-2f3a-4b5c6d7e8f9a -->
<!-- last-edited: 2026-06-13 -->

# gha-release-docker — Additional Context

Org-wide coding standards (file headers, language rules, commit format) are at
**https://github.com/falkcorp/.github** and apply automatically to this repo.

For full project context: **CLAUDE.md** at the repo root.

## Project overview

GHA composite action: Docker image release builds. Language: Shell/YAML.
The primary entrypoint is `action.yml` — a single composite action that handles
multi-platform Docker builds, tagging, and registry pushes for release workflows.

## Critical constraints

- This is a GHA composite action repo — no application code, no test suite.
- Changes to `action.yml` must be validated by calling repos before merging.
- All GitHub Action step `uses:` references must be pinned to SHAs, not tags.
