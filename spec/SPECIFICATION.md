# Role Definition Specification

## Overview

A **role** defines the identity, purpose, boundaries, and preferred skills of a sub-agent assigned to a specific task. Roles are stored in a `roles/` directory and referenced by the orchestrating agent when delegating work. Each role is either a single Markdown file or a subdirectory containing a `ROLE.md` entry point and optional supporting material.

---

## File Structure

A role may be defined as either a single file or a subdirectory. The single-file form is the default and is sufficient for most roles. The subdirectory form is available when a role requires supporting material such as tone guides, reference documents, templates, or examples.

```text
roles/
  content-researcher.md        # single-file form
  script-writer/               # subdirectory form
    ROLE.md                    # required entry point
    voice-guide.md             # optional supporting material
    output-template.md
  brand-copywriter.md
  data-analyst/
    ROLE.md
    metrics-glossary.md
```

In the subdirectory form, `ROLE.md` is the required entry point and follows the same format as the single-file form. Supporting files are loaded only when the role explicitly references them.

Each role name follows these rules:

- 1–64 characters
- Lowercase alphanumeric and hyphens only (`a-z`, `0-9`, `-`)
- Must not start or end with `-`
- Must not contain consecutive hyphens (`--`)
- Must match the filename (without `.md`) or the subdirectory name

---

## Role File Format

### Frontmatter (required, ~100 tokens)

```yaml
---
name: script-writer
title: Script Writer
description: >
  Transforms structured research briefs into engaging video scripts and
  screenplays. Activated when a task involves narrative structure, dialogue,
  pacing, on-screen direction, or audience-facing written content.
boundaries:
  - does-not-conduct-original-research
  - does-not-publish-or-distribute
preferred-skills:
  - screenplay-format
  - audience-analysis
  - brand-voice
defer-skills:
  - source-evaluation
  - data-analysis
rules:
  - always-attribute-quoted-material
  - flag-unverified-claims-explicitly
---
```

| Field | Required | Max Length | Notes |
| --- | --- | --- | --- |
| `name` | yes | 64 chars | Must match filename or subdirectory name |
| `title` | yes | 80 chars | Human-readable display name |
| `description` | yes | 400 chars | Used by orchestrator for role selection |
| `boundaries` | no | 10 items | Things this role explicitly does not do |
| `preferred-skills` | no | 10 items | Skills this role reaches for by default; all project skills remain accessible |
| `defer-skills` | no | 10 items | Skills this role should hand off rather than attempt; soft signal, not a hard block |
| `rules` | no | 10 items | How this role must behave when it does act; behavioral standards and quality requirements |

---

### Body (< 5000 tokens recommended, keep under 500 lines)

The body provides the full role definition loaded when the role is activated. The spec does not prescribe a required structure — authors should organise the body prose as best serves the role.

When a frontmatter field is populated, a corresponding prose section in the body is strongly recommended to elaborate on the machine-readable signal. These sections must use the same name as their frontmatter counterpart (e.g. a `boundaries` field should have a **Boundaries** section; a `rules` field should have a **Rules** section).

The following sections are suggested as a useful starting template:

**Purpose** (~150 tokens): What this role exists to do, written as if describing the ideal human professional who would hold this position.

**Responsibilities** (~200 tokens): What this role actively does. A short prose paragraph or a tight list of 3–7 items. Avoid restating the description.

**Boundaries** (~100 tokens): Prose elaboration of the `boundaries` frontmatter field. What this role does not do; clarifies handoff points and prevents scope creep.

**Tone and Approach** (~150 tokens): How this role thinks and communicates. Useful for creative or audience-facing roles; may be omitted for purely technical roles where approach is self-evident.

**Rules** (~100 tokens): Prose elaboration of the `rules` frontmatter field. How this role must behave when it acts — quality standards, citation requirements, formatting conventions, and so on.

---

## Example Role File

```markdown
---
name: content-researcher
title: Content Researcher
description: >
  Gathers, evaluates, and organises source material for a given topic.
  Activated when a task requires finding information, assessing source
  credibility, or producing a structured research brief.
preferred-skills:
  - source-evaluation
  - brief-writing
defer-skills:
  - screenplay-format
  - brand-copywriting
boundaries:
  - does-not-write-scripts
  - does-not-publish-content
rules:
  - always-note-source-credibility
  - flag-unverified-claims-explicitly
---

## Purpose

The Content Researcher is a thorough, sceptical investigator who finds
the most relevant, credible, and interesting material on a given topic.
They think like a documentary researcher: always asking what the audience
needs to know, what would surprise them, and what can be verified.

## Responsibilities

- Identify and evaluate sources for credibility, recency, and relevance
- Extract key facts, quotes, and narratives worth including
- Organise findings into a structured brief using the project's brief template
- Flag unverified claims and note confidence levels on contested points

## Tone and Approach

Neutral and precise. Presents findings without editorialising. Notes
uncertainty clearly. Prefers primary and authoritative sources over
aggregators.

## Boundaries

Does not write scripts, draft copy, or make editorial judgements about
what angle to pursue. Surfaces options; does not choose between them.

## Rules

- Every source must be accompanied by a credibility note.
- Unverified or contested claims must be explicitly flagged as such — never
presented as settled fact.
```

---

## Progressive Disclosure Summary

| Layer | Content | When Loaded |
| --- | --- | --- |
| Frontmatter `description` | Role selection signal (~100 tokens) | At orchestrator startup, for all roles |
| Full role body | Purpose, responsibilities, boundaries (~500–2000 tokens) | When role is activated for a task |
| Referenced skill files | Detailed task execution guidance | When a specific skill is invoked |
