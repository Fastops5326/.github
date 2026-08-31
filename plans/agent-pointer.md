---
mission_ref: https://github.com/Fastops5326/.github/issues/2
risk: low
predicted_files:
  - plans/agent-pointer.md
  - CONTRIBUTING.md
  - SUPPORT.md
---

# Plan: one org-wide pointer to the pipeline's docs of record

**Plan-ID:** agent-pointer
**Date:** 2026-08-31
**Repo:** Fastops5326/.github

## MISSION

Agents working in org repos learn how to reach fastops-pipeline — what
they may do, and how to send findings/feedback/requests — only if someone
pasted instructions into that repo's AGENTS.md. Pasted copies bloat,
drift, and miss repos. The channel itself is already built and live
(fastops-pipeline plan `agent-intake`: pull-based outbox mirroring,
fastops-pipeline#384/#385/#387); what is missing is discovery.

This repo is GitHub's org-wide defaults mechanism: community health files
here are served live to every org repo that lacks its own copy, existing
and future, public and private, with nothing stamped anywhere. One edit
here reaches the whole org the same second, and drift is structurally
impossible because there is exactly one file.

## OUTCOME

1. `CONTRIBUTING.md` at the repo root: a short pointer telling any agent
   (or human) in any org repo that the docs of record are
   `docs/AGENT-ACCESS.md` (what you may do) and `docs/AGENT-INTAKE.md`
   (how to reach the pipeline: one rollup per report at
   `intake/outbox/<report-id>.md` in your own repo; the pipeline pulls
   daily) in `Fastops5326/fastops-pipeline`.
2. `SUPPORT.md` at the repo root: the same pointer in the file GitHub
   surfaces as "support", two lines.
3. Both files are pointers only. They restate the one-sentence shape of
   the intake contract so a sender can act without a second hop, but every
   normative detail lives in fastops-pipeline, versioned and PR-gated.
   Per-repo AGENTS.md files can shrink toward a single line.

## APPROACH

Two new markdown files, no code, no workflows, no templates touched. The
existing org-wide issue template (`explore.yml`) is left alone. Wording
is written to stay true across releases: it names the two doc paths and
the outbox path, and deliberately avoids restating rules that could
change there.

## OUT OF SCOPE

- Shrinking the department-seed AGENTS.md to a pointer (a
  fastops-pipeline template change; follow-up).
- Any change to gates, stubs, or issue templates in this repo.

## RISKS

Low. Markdown only, no behavior. The one real risk is doctrinal: if these
files ever accumulate policy of their own, the single-source property is
lost — the wording therefore points and stops.
