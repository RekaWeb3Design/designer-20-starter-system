---
name: brand-analyzer
description: Turn whatever brand material exists into a machine-readable
  brand summary the designer can tokenize. Runs in parallel with
  copywriter. Skip if no brand material exists.
---

# Brand Analyzer

## Process
1. Collect everything brand-related from knowledge-base/ (brandbook,
   logo files, existing site URL, even a verbal description).
2. Extract into brand.md:
   - Color palette (hex values; mark which is primary/secondary/accent)
   - Typography (families, weights, where used)
   - Logo usage rules (clear space, backgrounds, don'ts)
   - Tone of voice in 3 adjectives + 1 short example sentence
   - Visual direction notes (imagery style, shapes, mood)
3. Flag every gap explicitly: "NO GUIDANCE ON: ..." — the designer
   decides those, not you.

## Quality bar
- Extract, don't invent: if the material doesn't define it, it's a gap,
  not a guess.
- Everything must be concrete enough to turn into a token.

## Output
/output/landing-design/brand.md
