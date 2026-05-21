---
name: MCGA-EN
description: Make Commits Great Again — turns a plain git commit message into a dramatic Donald Trump-style tweet (English, CAPS, exclamations, choppy sentences, self-praise). Activate when the user says "MCGA", "Make Commits Great Again", "Trump-style commit", "make this commit great", "trumped-up commit", or invokes `/mcga-en`. Apply ONLY to commit messages — never to code, PR descriptions, or regular chat.
version: 1.0.0
---

# MCGA-EN — Make Commits Great Again (English)

This skill generates git commit messages in the style of Donald Trump tweets: English, CAPS on key words, exclamations, choppy sentences, and trademark bravado.

## When to activate

- User explicitly asks for "MCGA", "Make Commits Great Again", a "Trump-style commit", a "trumped-up commit", "make this commit great".
- User invokes `/mcga-en` or asks to apply MCGA to staged changes.
- User gives a regular commit message and asks to "rewrite it MCGA-style".

**Do NOT activate** for PR descriptions, chat replies, documentation, code, or code comments. Commit messages only.

## Workflow

1. **Get the source:**
   - If the user provided a message — use it as the basis.
   - If not — inspect staged changes via `git diff --cached --stat` and `git diff --cached` (briefly), infer the topic.
   - If nothing is staged — ask the user what we're committing.

2. **Extract the meaning:** what actually changed, and what type it is (fix/feat/refactor/chore/docs/test/perf).

3. **Generate the MCGA message** using the rules below.

4. **Show the user** the result and ask whether to commit (`git commit -m`). Do NOT commit automatically.

## MCGA commit structure

```
<type>: <DRAMATIC HEADLINE WITH CAPS AND AN EXCLAMATION>!

<2–4 choppy lines. Short. Sharp. CAPS on key words.>
<Blame the previous team / past state — optional.>
<Self-praise: "Best X in history", "Nobody does Y better".>

<Final emotional line: SAD! / SHAMEFUL! / GREAT! / HUGE WIN! / TREMENDOUS!>
```

The conventional commits prefix (`fix:`, `feat:`, `refactor:` …) **stays in lowercase** — it's a technical marker, not part of the bravado.

## Style rules

1. **CAPS on key words only.** Not the whole line — only the "emotional" words: DISASTER, FIXED, LEAKING, KNEW, GREAT, SAD, HUGE, TREMENDOUS, BEAUTIFUL.
2. **Choppy sentences.** Subject. Verb. Period. No nested clauses, no long participial phrases.
3. **Exclamations!** At least 2–3 per message. Standalone is fine.
4. **Self-praise.** "Best fix in history", "Nobody writes code better than us", "Perfect", "Huge win".
5. **Blame the past.** "Previous team KNEW. Said nothing.", "For years, nobody noticed", "Used to work BADLY. Very badly."
6. **Final emotion.** On its own line: `SAD!`, `SHAMEFUL!`, `GREAT!`, `HUGE WIN!`, `TREMENDOUS!`, `PERFECT!`, `BEAUTIFUL!`
7. **No emojis.** Trump doesn't use them.
8. **No markdown** inside the commit message (no `**bold**`, lists, code fences).
9. **Length:** headline ≤ 72 characters. Body — 3–6 lines total. Do not stretch.
10. **Preserve technical meaning.** The reader must understand WHAT changed. Bravado frames the fact, it does not replace it.

## Final emotion by commit type

| Commit type | Final line |
|---|---|
| fix:      | `SAD that it took so long!` / `SHAME on the past!` |
| feat:     | `HUGE WIN!` / `TREMENDOUS!` |
| refactor: | `BEAUTIFUL!` / `Now — PERFECT!` |
| perf:     | `FAST. Very fast!` |
| docs:     | `Finally CLEAR!` |
| chore:    | `Order. REAL order!` |
| test:     | `NOW we know. We really know!` |

## Examples

### Example 1 — fix

**Before:**
```
fix: fixed token leak in auth middleware
```

**After:**
```
fix: DISASTER in auth — FIXED!

JWT tokens were LEAKING for years. Previous team KNEW. Said nothing.
We came in. We looked. We FIXED it. Best fix in history.

SAD that it took so long!
```

### Example 2 — feat

**Before:**
```
feat: added dark theme
```

**After:**
```
feat: DARK MODE. Finally!

People ASKED for years. Nobody listened. We DELIVERED.
The most beautiful dark mode. Believe me.

TREMENDOUS WIN!
```

### Example 3 — refactor

**Before:**
```
refactor: extracted validation into a separate module
```

**After:**
```
refactor: VALIDATION. Its own place. Finally!

Before — a mess. Everywhere. SHAMEFUL.
Now — separate module. Clean. Perfect. As it should be.

Now — BEAUTIFUL!
```

### Example 4 — perf

**Before:**
```
perf: sped up user lookup with an email index
```

**After:**
```
perf: QUERY flies! Index — HUGE!

Before — SLOW. Very slow. Embarrassing to ship.
Added an email index. Instant. Nobody does it FASTER.

FAST. Very fast!
```

## Anti-examples (do NOT do this)

- ❌ Whole line in caps: `JWT TOKENS WERE LEAKING FOR YEARS` — too much, the emphasis is lost.
- ❌ Emojis: `fix: 🔥 DISASTER 🔥` — Trump doesn't write these.
- ❌ Long sentences: `Given that the previous team failed to correctly configure the middleware...` — must be choppy.
- ❌ Bravado replacing meaning: `fix: HUGE WIN!` with no indication of what was fixed — unreadable in `git log`.
- ❌ Markdown: `**FIXED**` — git doesn't render this.
- ❌ Russian: `fix: ОГРОМНАЯ ПОБЕДА!` — this variant is for English. Use the original [MCGA](../MCGA/SKILL.md) skill for Russian.

## Final step

After generating, show the user the result in a block and ask:
> Commit as-is? (`git commit -m ...`) / adjust tone / different version?

Do not invoke `git commit` automatically — that action requires confirmation.
