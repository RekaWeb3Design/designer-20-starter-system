# Landing Design

Run the full UI accelerator flow: from brief + UX output to design tokens,
copy and a working local preview.

## Context
- PROJECT FOLDERS: the convention in .cursor/rules/projekt-context.mdc
  applies — inputs come from knowledge-base/briefs/<projekt-slug>/, and
  every /output/... path below gets a <projekt-slug>/ subfolder.
- Inputs: the project brief AND /output/ux-research/<projekt-slug>/ (run /ux-research
  first if it does not exist yet).
- If /output/tech-stack.md exists (from /build-project), treat it as a
  constraint; otherwise default to Astro + Tailwind, static-first.
- LANGUAGE: write all outputs (copy included!) in the language of the
  brief — Hungarian brief -> Hungarian deliverables, proper accents.
- The team playbooks live in .cursor/skills/ui/ — follow them in order.
- QUALITY FLOOR: docs/vizualis-minoseg.md is binding for creative-director,
  designer and builder. The deliverable is a page a design-literate client
  would pay for — "correct but ordinary" is a failed run.
- IMAGES: every image slot ships with a real file. If the client has no
  photos, use site/public/images/ (see its KEPEK.md) and log the gap — an
  empty grey placeholder box is never acceptable output.
- Every stage writes its artifact to /output/landing-design/ BEFORE the
  next stage starts, so the designer can review at any point.

## Steps (in this order)
1. intelligence — visual competitor & category research → intelligence.md
2. creative-director — section architecture, tone, non-negotiable design
   language → plan.md + consistency.md
3. IN PARALLEL (their outputs are independent):
   - copywriter — conversion copy per section → copy.md
   - brand-analyzer — machine-readable brand summary from any brand
     material in knowledge-base/ → brand.md (skip if no brand material;
     note the gap in plan.md)
4. designer — implementable design tokens from the brand direction
   → design-tokens.json
5. builder — assemble the site using copy.md + design-tokens.json +
   the installed UI library MCPs (shadcn/ui, Magic UI, React Bits).
   At least 4 components come from the MCP catalogs — do NOT rebuild them
   from memory. Closes with the 12-point visual self-review.
   → /output/landing-design/site/ with npm run dev working locally.

## Output
/output/landing-design/: intelligence.md, plan.md, consistency.md, copy.md,
brand.md, design-tokens.json, site/ (runnable),
VIZUALIS-ONELLENORZES.md, HIANYZO-ADATOK.md.
Finish with a short summary: what to review first, and any [ASSUMPTION]s.
