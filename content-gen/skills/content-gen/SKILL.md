---
name: content-gen
description: Create, score, review, and select social-media content from product stories or a topic. Use when a user requests the Ship Faster content-generation pipeline or any of its extraction, drafting, scoring, review, or selection stages.
---

# Content Generation

Choose the stage requested by the user, then read its source workflow from
`../../commands/` before acting:

| User intent | Source workflow |
| --- | --- |
| extract stories and themes | `content-extract-stories.md` |
| draft content for a theme | `content-generate-drafts.md` |
| score drafted content | `content-score-all.md` |
| critique scored content | `content-critic-review.md` |
| select and format the best content | `content-select-best.md` |
| run or resume the full pipeline | `content-full-pipeline.md` |

Treat the selected source workflow as the detailed procedure, with these Codex
adaptations:

- The user's request supplies every occurrence of `$ARGUMENTS`; ask only if the
  required topic, source stories, or working directory is missing.
- References to Claude agents map to the equivalent role in the current task:
  story extraction, drafting, scoring, criticism, selection, or tracking. Do not
  depend on Claude-specific agent registration.
- Read templates from `../../templates/` and role guidance from `../../agents/`
  before the matching stage.
- If Linear or another external system is unavailable, request exported stories
  or use the user-provided source material; do not claim external data was read.
- Preserve the workflow's files, scoring rubric, and pass/fail checks. Confirm
  before publishing, sending, or changing any external content.
- When running the full pipeline, persist each completed stage so it can be
  resumed, and identify exactly which stage needs attention if validation fails.
