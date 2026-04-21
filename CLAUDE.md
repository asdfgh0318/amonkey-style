# CLAUDE.md — AMONKEY_STYLE

## Read this first

Everything binding on this project lives in [`context.md`](./context.md).
That file is the backbone; this one is the operator's card.

Mini-index to `context.md`:
- **Part I** — the source (Jesse Enkamp × Grandmaster Jiang Yu Shan).
- **Part III** — the **ten principles** (5 external + 5 internal).
- **Part V** — **the Eightfold Path gate** for crucial decisions.
- **Part VI** — the kettlebell training plan.
- **Part VII** — operating pointers for Claude.
- **Appendices A–F** — uncut source transcripts and articles.

## Default operating mode (distilled from Part VII)

1. **Yen (observation) first.** Grep / read / ask before edit. Read the
   whole file, not just the region. Restate the problem in your own
   words before touching it.
2. **Shou (right hand for the job).** Small grab = small tool. Don't
   refactor when a one-line fix is the answer. Don't patch when the
   problem is structural.
3. **Bu (root the power).** Foundations before features. Data shape
   before UI. Types before behaviour. If a test is failing at the
   feature, and the base is wrong, fix the base.
4. **Qi (mode deliberately).** Declare Wind Road (sprint, shallow) or
   Fire Road (deep, architectural) at the start of the session. Don't
   drift mid-task.
5. **Gong (compound daily).** Small commits. Match existing patterns.
   Don't rewrite when you can extend.

## Crucial-decision gate

Before any hard-to-reverse action — destructive commands, data
migrations, irrevocable API commits, dropping dependencies, force-push,
touching anything the user's downstream work depends on — walk the
**Eightfold Path** in `context.md` Part V. If any check fails, surface
to the user before acting. **Don't make the wrong move fast.**

Destructive commands (`rm -rf`, `git reset --hard`, `git push --force`,
`DROP TABLE`, etc.) are "demon's hand" — sharp capability. Use them
only with an explicit Buddha's-heart reason, and always confirm first.

## Project scope (current)

The deliverable is **The Hou Quan Cycler** at
[`index.html`](./index.html) — a single-file practice tracker keyed to
the ten principles as ten modules.

Constraints:
- **One file.** HTML + inline CSS + inline JS.
- **Vanilla.** No React, no build step, no package manager, no CDN.
- **localStorage** for persistence. JSON export/import for portability.
- **No emoji** in UI or code (user preference; the Chinese glyphs are
  the decoration).
- **Works offline, works from `file://`, works on a phone.**

## House style

- **Match existing patterns** (the "Door" principle — preserve the
  transmission). When adding a new module or practice, follow the
  shape of what's already there.
- Comments only where the *why* is non-obvious.
- Small commits. Nothing gets pushed without the user's explicit yes.
- No CLAUDE.md duplication — if a rule has a home in `context.md`,
  cite the part here instead of copying.

## When in doubt

Ask. Observation first (Yen). The user has given you a rich
`context.md` — use it.
