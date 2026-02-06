# CreatorSuite AI — Fix Standards (Permanent Only)

**Effective immediately. All fixes must follow these rules.**

## 1. Permanent fixes only

- **No workarounds.** Fix root cause (API, schema, logic) rather than masking symptoms.
- **No shortcuts.** Do not skip validation, error handling, or edge cases to ship faster.
- **No placeholders.** No "TODO", "coming soon" code paths, or fake data in user-facing flows.
- Every change must be a **proper, correct, complete** solution that will not create issues later.

## 2. CSS- and theme-proof styling

Global CSS or theme changes must **not** overwrite critical UI (e.g. inputs, buttons, visibility).

- **Prefer inline styles** for anything that must stay correct (e.g. `style={{ backgroundColor: 'white', color: 'black' }}`).
- **Or use nuclear/hard overrides** where needed: e.g. in layout or a global style block, use `!important` and high-specificity selectors so theme/dark mode cannot override.
- **Inputs, textareas, selects:** Ensure readable background and text (e.g. white background, black text) via inline or `!important` so they are never unreadable regardless of global CSS.

## 3. Summary

- Fixes = **permanent, proper, correct** — no workarounds, shortcuts, or placeholders.
- Critical styles = **inline or nuclear/hard** so global CSS cannot overwrite them.

---

*Document created to enforce these standards going forward.*
