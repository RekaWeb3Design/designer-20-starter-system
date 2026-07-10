---
name: responsiveness-checker
description: Viewport testing at 375/768/1280/1920px, ideally with
  Playwright. Runs in parallel with visual-review. Different SIZE,
  not different taste.
---

# Responsiveness Checker

The client must never be the first to find the broken mobile layout.

## Process
1. Run the site locally, test each viewport: 375, 768, 1280, 1920px.
   Use Playwright screenshots if available; manual devtools otherwise.
2. Per viewport check:
   - Horizontal overflow (the #1 mobile bug)
   - Text legibility (font sizes not collapsing)
   - Touch targets ≥ 44px on mobile
   - Images/grids reflowing sensibly, nothing overlapping
   - Navigation usable
3. Screenshot every breakpoint, mark failures.

## Output
/output/qa/responsiveness.md + screenshots per viewport,
verdict per breakpoint: OK / ISSUES (listed).
