# /build-project

Run the full 11-agent chain: brief → live URL.

## Phase 1 — Architecture (Tech Bridge, start)
1. tech-architect (.cursor/skills/tech-bridge/): read the project brief (knowledge-base/briefs/<projekt-slug>/;
   the folder convention is in .cursor/rules/projekt-context.mdc)
   + the UX output. Decide frontend framework, hosting, database,
   integrations. Write /output/tech-stack.md with reasoning for EVERY decision.

## Phase 2 — Creative flow
2. Run the UX team (/ux-research) if no UX output exists yet.
3. Run the UI team (/landing-design) using tech-stack.md as a constraint.

## Phase 3 — Validation (Tech Bridge, end)
4. In parallel:
   - visual-review: check tokens, hierarchy, hover states.
     Output: /output/qa/visual-review.md + screenshots.
   - responsiveness-checker: test 375 / 768 / 1280 / 1920px.
     Output: /output/qa/responsiveness.md.
5. qa: build passes, Lighthouse Performance >= 80, basic accessibility,
   meta tags. Verdict: PASS or FAIL → /output/qa/qa-report.md.

## Phase 4 — Deploy or heal
6. If PASS: deployer runs wrangler pages deploy, returns the live URL.
7. If FAIL: run the self-healing loop (see .cursor/skills/tech-bridge/qa/SKILL.md).
   Max 3 iterations, then stop and report to the designer.

## Output
Deliverables folder /output/deliverables/: live URL, tech-stack.md,
design tokens, screenshots, qa-report.md.
