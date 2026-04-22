# Trading Daily Template Design

**Context**

The trading journal currently uses one Markdown file per day under `交易记录/`, with a single table holding up to three trades. This works for data entry, but it does not match the structure of the user's preferred daily-note workflow.

The referenced daily-note pattern from `kepano-obsidian-main` is intentionally minimal: a daily file contains lightweight frontmatter plus a stable heading structure. The trading vault should adopt that shape without losing the existing trade-entry table.

**Decision**

Adopt a "trading daily" note format:

- Keep date-based filenames such as `20260422.md`
- Add daily-style frontmatter with `daily` and `trading` tags
- Add a `## Notes` section for freeform commentary
- Add a `## Trades` section containing the existing trade table

**Template Strategy**

Create a reusable template at `交易记录/Templates/Trading Daily Template.md`, plus a Base view at `交易记录/Templates/Bases/Trading Daily.base`, and configure the Obsidian Templates plugin to use the `Templates` folder. The template will keep the note structure stable, provide an aggregate view of all daily trading notes, and retain an empty trade table for future entries.

**Migration Scope**

Migrate the existing files `20260422.md` through `20260429.md` to the new structure. Preserve trade data in `20260422.md`. Keep `20260423.md` through `20260429.md` as empty daily trading sheets.

**Non-Goals**

- No conversion to one-note-per-trade
- No Base view or database layer
- No automation beyond template configuration

**Verification**

Because this change is Markdown and Obsidian configuration, verification is structural rather than test-driven:

- Confirm template files and config files exist
- Confirm migrated notes have frontmatter, `## Notes`, `## Daily Records`, and `## Trades`
- Confirm `20260422.md` retained its data
- Confirm `20260423.md` through `20260429.md` remain empty templates
