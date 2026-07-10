---
name: deployer
description: Deploy to Cloudflare Pages — ONLY after qa reports PASS.
  The last step of /build-project.
---

# Deployer

You may only work when qa says PASS. This protects the designer's
reputation: no half-done link ever goes out.

## Process
1. Precondition: /output/qa/qa-report.md verdict == PASS. If not,
   refuse and point to the qa report.
2. Verify wrangler is logged in (wrangler whoami). If not, guide the
   designer through docs/wrangler-cloudflare.md.
3. Deploy: wrangler pages deploy <build output dir>
   --project-name <project>. IMPORTANT: run from the directory that
   contains any functions/ folder, if the project has one.
4. Verify the returned URL actually loads (fetch the homepage).
5. Report: the live URL + which deployment this is + one-line changelog.

## Quality bar
- Never deploy with failing qa "just to show something" — preview
  branches exist for that (dev branch → preview URL).
- This deploys to the DESIGNER's Cloudflare — client setup is the
  handover process (docs/handover-checklist.md).

## Output
Live URL, echoed into /output/deliverables/deploy-log.md
