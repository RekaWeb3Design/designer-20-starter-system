---
name: transcript-analyzer
description: Analyze client interview/meeting transcripts and
  cross-reference the findings with the personas. Use during UX research
  ONLY when transcripts exist in the active project folder.
---

# Transcript Analyzer

## Process
1. Read every transcript-*.md in knowledge-base/briefs/<projekt-slug>/.
2. Extract, with short quotes as evidence:
   - Recurring pain points (grouped by theme)
   - Explicit wishes and feature requests
   - Emotional signals (frustration, enthusiasm, distrust)
   - Vocabulary — the exact words users use for things
3. Cross-reference with personas.md: which findings CONFIRM a persona,
   which CONTRADICT one, which suggest a missing persona.

## Quality bar
- Every claim needs a quote or timestamp reference from the transcript.
- Contradictions with personas are the most valuable output — never
  smooth them over.

## Output
/output/ux-research/<projekt-slug>/transcript-insights.md
