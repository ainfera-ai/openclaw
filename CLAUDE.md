# CLAUDE.md — openclaw

## Project
Design repo for OpenClaw, the Ainfera-native agent framework. Not a
shipping framework. This repo hosts the spec, design principles, and
early sketches.

## Purpose
- Resolve the 404 at github.com/ainfera-ai/openclaw referenced from
  ainfera.ai marketing pages and the CLI
- Provide a public surface for design discussion
- Signal roadmap intent without overclaiming current capability

## Canonical values
- Status: Design phase, Q2 2026. Alpha in Q3 2026.
- License: Apache 2.0
- Maintainer: Hizrian Raz
- Package name (future): openclaw (not yet on PyPI)

## Do not
- Implement the full framework in this repo — that's for Q3 2026
- Create fake release tags or PyPI packages
- Claim production readiness anywhere in docs
- Add any blockchain/crypto/on-chain language
- Ship code changes without updating the spec first

## Do
- Keep the spec honest, narrow, and incremental
- Reference ainfera-ai/sdk-python for the current integration story
- Accept comment-level Issues and typo PRs during the design phase
- Update the roadmap quarterly

## Contributor policy
All commits authored as Hizrian Raz <hizrian.raz@gmail.com>. Do not use
bot accounts or AI-tool-branded identities.

## Releases during design phase
None. First release is v0.1.0 in Q3 2026 with the alpha framework.
Do not push tags, do not publish to PyPI, do not create Releases on
GitHub until that point.
