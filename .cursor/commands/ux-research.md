# UX Research

Run the full UX research flow based on the brief in /knowledge-base.

## Context
- Read knowledge-base/brief.md first. If client emails or transcripts
  exist in knowledge-base/, use them as source material.
- Work from best practices, production grade quality.
- LANGUAGE: write ALL outputs in the language of the brief (Hungarian
  brief -> Hungarian deliverables, with proper accents). Keep the
  [ASSUMPTION] marker itself unchanged.
- HARD GATE — check this BEFORE writing any output file: if the brief
  does not explicitly define the target audience, STOP. Do NOT create
  any files. Ask the designer ONE clarifying question about the
  audience, then WAIT for the answer. Noting the gap and proceeding
  with [ASSUMPTION] tags is NOT acceptable — that path is only allowed
  after the designer explicitly replies "proceed" / "dolgozz tovabb".
- GATE QUESTION FORMAT: ask as a multiple-choice menu, not an open
  question. Offer 3-5 plausible audience options inferred from the
  brief as a lettered list (A, B, C...), always ending with:
  "X) Egyeb — ird le roviden" and "Y) Dolgozz feltetelezesekkel
  ([ASSUMPTION] jelolessel)". Tell the designer a single letter is a
  valid answer, and multiple letters (e.g. "A+C") combine options.
- The team playbooks live in .cursor/skills/ux/ — follow them:
  ux-orchestrator coordinates; persona-builder, journey-mapper,
  validation-question-generator and transcript-analyzer do the work.

## Steps
1. Act as ux-orchestrator: read the brief, extract the project context
   brief summary that every specialist will receive.
2. persona-builder: generate 3-5 personas using the Cooper frame
   (goals, motivations, frustrations, typical daily routine).
3. journey-mapper: build a user journey for each persona
   (stages, actions, thoughts, emotions, touchpoints, opportunities).
4. validation-question-generator: create a validation question set —
   qualitative interview guide + quantitative survey questions.
5. If transcripts are available in knowledge-base/: transcript-analyzer
   analyzes them and cross-references the findings with the personas.

## Output
Write all results to /output/ux-research/ as separate files:
personas.md, journeys.md, validation.md (and transcript-insights.md if run).

Mark every statement that is NOT supported by the source material
with [ASSUMPTION], so the designer can review it.
