# Trading Daily Template Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Convert the trading journal notes to a daily-note style template while preserving the existing trade-entry table.

**Architecture:** Keep the vault's date-per-file workflow, but wrap each note in a stable daily-note structure with frontmatter and headings. Store the reusable empty note in `交易记录/Templates/Trading Daily Template.md`, add a `Trading Daily.base` aggregate view, and migrate the existing trading notes to match it.

**Tech Stack:** Obsidian Markdown, Obsidian core Templates plugin, JSON config files

---

### Task 1: Add planning artifacts

**Files:**
- Create: `docs/plans/2026-04-22-trading-daily-template-design.md`
- Create: `docs/plans/2026-04-22-trading-daily-template.md`

**Step 1: Write the approved design summary**

Document the chosen approach:
- daily-style frontmatter
- `## Notes`
- `## Trades`
- reusable template file

**Step 2: Save the implementation plan**

Document the exact files to create and update so the migration is reproducible.

### Task 2: Add template support files

**Files:**
- Create: `交易记录/Templates/Trading Daily Template.md`
- Create: `交易记录/Templates/Bases/Trading Daily.base`
- Create: `交易记录/.obsidian/templates.json`

**Step 1: Create the reusable trading daily template**

Include:
- frontmatter with `daily` and `trading` tags
- `## Notes`
- `## Daily Records`
- `## Trades`
- empty trade table matching the current schema

**Step 2: Create the daily aggregate Base**

Add a Base view that collects all daily trading notes in `交易记录/` and sorts them by date.

**Step 3: Configure the Templates plugin**

Set the templates folder to `Templates` so the vault can insert the new template directly.

### Task 3: Migrate existing trading notes

**Files:**
- Modify: `交易记录/20260422.md`
- Modify: `交易记录/20260423.md`
- Modify: `交易记录/20260424.md`
- Modify: `交易记录/20260425.md`
- Modify: `交易记录/20260426.md`
- Modify: `交易记录/20260427.md`
- Modify: `交易记录/20260428.md`
- Modify: `交易记录/20260429.md`

**Step 1: Wrap each note in the daily structure**

For every file:
- add frontmatter
- add `## Notes`
- add `## Daily Records`
- add `## Trades`

**Step 2: Preserve the populated table in `20260422.md`**

Keep all existing values intact under `## Trades`.

**Step 3: Keep future dates empty**

Ensure `20260423.md` through `20260429.md` contain the same empty table shape as the template.

### Task 4: Verify the migration

**Files:**
- Verify: `交易记录/Templates/Trading Daily Template.md`
- Verify: `交易记录/Templates/Bases/Trading Daily.base`
- Verify: `交易记录/.obsidian/templates.json`
- Verify: `交易记录/20260422.md`
- Verify: `交易记录/20260423.md`
- Verify: `交易记录/20260429.md`

**Step 1: Read back the template and config**

Confirm they were written to the intended locations.

**Step 2: Read back migrated notes**

Confirm:
- frontmatter exists
- headings exist
- Base embed exists
- trade data remains in `20260422.md`
- empty tables remain in the new blank days

**Step 3: Report actual status**

Summarize the exact files changed and note that verification was structural rather than automated, since this task only modified Markdown and Obsidian config files.
