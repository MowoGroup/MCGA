# MCGA-EN — Make Commits Great Again (English)

A Claude Code skill that turns plain git commit messages into dramatic Donald Trump-style tweets. In English. With CAPS. With exclamations!

> The best commit skill in history. Believe me.

For the original Russian version, see [`../MCGA`](../MCGA/).

---

## Example

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

---

## Install

Claude Code skills live in one of two directories:

| Scope | Path | When to use |
|---|---|---|
| User | `~/.claude/skills/MCGA-EN/` | Available across all projects. |
| Project | `<repo>/.claude/skills/MCGA-EN/` | Only inside this repository. |

### Option 1 — `git clone` (recommended)

Clone the whole repo, then symlink (or copy) the `MCGA-EN/` subfolder into your skills directory:

```bash
# clone once anywhere
git clone https://github.com/MowoGroup/MCGA.git /tmp/mcga-skills

# globally (all projects)
cp -r /tmp/mcga-skills/MCGA-EN ~/.claude/skills/MCGA-EN

# or per-project
cp -r /tmp/mcga-skills/MCGA-EN <your-repo>/.claude/skills/MCGA-EN
```

### Option 2 — copy by hand

Download `SKILL.md` from this folder and place it at `~/.claude/skills/MCGA-EN/SKILL.md`. That's the only required file — `README.md` is only here for GitHub.

### Verify

Launch Claude Code in any project and type:

```
make me an MCGA commit
```

If the skill is picked up, Claude will start following the workflow below.

---

## Usage

The skill activates when you say one of:

- `MCGA`
- `Make Commits Great Again`
- `Trump-style commit`
- `trumped-up commit`
- `make this commit great`
- `/mcga-en` (if set up as a command)

Flow:

1. You give a plain commit message — **or** just say "MCGA", and Claude will read `git diff --cached`.
2. Claude generates the dramatic version following the style rules.
3. Shows the result. **Does not commit on its own** — waits for your "yes".
4. On confirmation, runs `git commit -m "..."`.

---

## Style rules (short)

Full set in [SKILL.md](./SKILL.md). The core:

1. **CAPS only on key words** (DISASTER, FIXED, GREAT, HUGE), not the whole line.
2. **Choppy sentences.** Subject. Verb. Period.
3. **2–3 exclamations** per message.
4. **Self-praise** ("Best fix in history", "Nobody does it better").
5. **Blame the past** ("Previous team KNEW. Said nothing.").
6. **Final emotion** on its own line: `SAD!`, `SHAMEFUL!`, `GREAT!`, `HUGE WIN!`, `TREMENDOUS!`.
7. **No emojis. No markdown.**
8. **Headline ≤ 72 characters.** Body — 3–6 lines.
9. **Meaning is preserved** — the commit must still tell you what changed.
10. **`fix:` / `feat:` / `refactor:` prefix** stays lowercase.

### Final line by commit type

| Type | Final line |
|---|---|
| `fix:`      | `SAD that it took so long!` |
| `feat:`     | `HUGE WIN!` / `TREMENDOUS!` |
| `refactor:` | `Now — BEAUTIFUL!` |
| `perf:`     | `FAST. Very fast!` |
| `docs:`     | `Finally CLEAR!` |
| `chore:`    | `Order. REAL order!` |
| `test:`     | `NOW we know. We really know!` |

---

## More examples

**feat:**

```
feat: DARK MODE. Finally!

People ASKED for years. Nobody listened. We DELIVERED.
The most beautiful dark mode. Believe me.

TREMENDOUS WIN!
```

**refactor:**

```
refactor: VALIDATION. Its own place. Finally!

Before — a mess. Everywhere. SHAMEFUL.
Now — separate module. Clean. Perfect. As it should be.

Now — BEAUTIFUL!
```

**perf:**

```
perf: QUERY flies! Index — HUGE!

Before — SLOW. Very slow. Embarrassing to ship.
Added an email index. Instant. Nobody does it FASTER.

FAST. Very fast!
```

---

## Structure

```
MCGA-EN/
├── SKILL.md     # the skill itself (frontmatter + rules + examples)
└── README.md    # this file
```

---

## FAQ

**Good for work repos?** Your call. In serious product repos, coworkers may not appreciate `DISASTER FIXED` in `git log`. Better for pet projects, hackathons, and side repos.

**Russian version?** Yes — see [`../MCGA`](../MCGA/). Same idea, in Russian.

**Can I tweak the tone?** Yes. Open `SKILL.md`, adjust rules, examples, or the final-line table.

**Will it commit automatically?** No. The skill shows the result and waits for your "yes". `git commit` only runs after confirmation.

---

## License

[MIT](../LICENSE) © 2026 Mowo Group
