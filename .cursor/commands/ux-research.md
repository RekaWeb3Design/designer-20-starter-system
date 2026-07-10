# UX Research

Run the full UX research flow based on a brief from knowledge-base/briefs/.

## Context
- PROJECT FILING (always the FIRST step): briefs arrive in the inbox
  folder knowledge-base/briefs/. If it contains any LOOSE brief file
  (not inside a project folder), create a project folder named after
  the client/project in kebab-case (e.g.
  knowledge-base/briefs/zold-sarok-kerteszet/) and MOVE the file into
  it. Related loose materials (client emails, transcripts, brand files)
  move into the same project folder. Work from the project folder from
  then on.
- ACTIVE PROJECT: a freshly filed loose brief is the active project.
  If there is no loose brief and several project folders exist, ask
  which one to run — lettered menu (A, B, C...), one project per
  option. Never merge two projects in one run.
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
  validation-question-generator and transcript-analyzer do the work;
  report-designer packages the result for the client.

## Steps
1. Act as ux-orchestrator: read the brief, extract the project context
   brief summary that every specialist will receive.
2. persona-builder: generate 3-5 personas using the Cooper frame
   (goals, motivations, frustrations, typical daily routine).
3. journey-mapper: build a user journey for each persona
   (stages, actions, thoughts, emotions, touchpoints, opportunities).
4. validation-question-generator: create a validation question set —
   qualitative interview guide + quantitative survey questions.
5. If transcripts are available in the project folder: transcript-analyzer
   analyzes them and cross-references the findings with the personas.
6. report-designer: after summary.md is written, generate report.html —
   a single self-contained, client-presentable HTML report from the
   markdown outputs (see .cursor/skills/ux/report-designer/SKILL.md).

## Output
Write all results to /output/ux-research/<projekt-slug>/ (same slug
as the project folder) as separate files: personas.md, journeys.md,
validation.md (and transcript-insights.md if run), summary.md, and
report.html as the client-facing package.

Mark every statement that is NOT supported by the source material
with [ASSUMPTION], so the designer can review it.
