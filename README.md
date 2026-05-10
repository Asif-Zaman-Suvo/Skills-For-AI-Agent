# Skills for AI Agent

A curated set of **[Cursor Agent Skills](https://docs.cursor.com)** — reusable `SKILL.md` playbooks that steer coding agents through real engineering workflows: from idea refinement through implementation, review, security, CI, and shipping.

Each skill is a **folder** containing a **`SKILL.md`** with YAML frontmatter (`name`, `description`) and structured instructions the agent follows when the task matches that skill.

## Quick start

1. **Clone** this repository (or copy the skill folders you care about).
2. **Cursor:** **Install skills** where Cursor resolves them — for example your user skills directory (see [Cursor Agent Skills docs](https://docs.cursor.com) for paths, e.g. `~/.cursor/skills-cursor/…`), or keep them in-repo and wire them via project rules/skills.
3. **Claude:** Use the **same files** via Project instructions, attachments, or `CLAUDE.md` — see [Using these skills in Cursor and Claude](#using-these-skills-in-cursor-and-claude) below (no Cursor install needed).
4. **Start with** [`using-agent-skills`](using-agent-skills/SKILL.md): how to pick the right skill for a task.

## Using these skills in **Cursor** and **Claude**

Each skill is just instructions in **`SKILL.md`** (often with YAML frontmatter). You can reuse the **same files** everywhere; **only Cursor** loads them automatically when they sit in a configured Cursor skills location.

### Cursor

1. **Install** skill folders where Cursor resolves agent skills — commonly under `~/.cursor/` (e.g. paths like `~/.cursor/skills-cursor/` for user skills); exact paths and UI differ by Cursor version — use [Cursor Agent Skills docs](https://docs.cursor.com) as the source of truth.
2. Alternatively, keep skills **inside this repo** and wire them through **project rules** or your team’s Cursor setup so agents can read them consistently.
3. In chat, rely on automatic matching from the skill **`description`** in frontmatter, or say explicitly: **follow `<skill-folder>` / open `that-skill/SKILL.md`**.

In Cursor, skills are invoked when that description matches your request or when you name the skill explicitly.

### Claude (web / app)

Claude does **not** read your `~/.cursor` tree by default. To use these playbooks:

- **Projects:** Add the repo (or copies of skill folders) to the project **knowledge base**, or paste the contents of **`SKILL.md`** into **project instructions**.
- **Per chat:** Paste a skill’s body, attach **`SKILL.md`**, or point the model at the file in your workspace if your client supports file/context attachment.
- **Tip:** YAML frontmatter is for tooling; Claude follows the Markdown body the same whether or not Cursor parsed the frontmatter.

### Claude Code (CLI / IDE extension)

Treat each **`SKILL.md`** as reusable policy: copy the sections you care about into **`CLAUDE.md`**, workspace docs, or whatever persistent instructions that environment reads for your repo.

---

**Summary:** **Cursor** — install skills where Cursor resolves them (and optionally rules). **Claude ecosystem** — same Markdown, wired in via Project instructions, chat attachments, **`CLAUDE.md`**, or docs in-repo.

## What’s included

Rough flow (see `using-agent-skills` for the full decision tree):

| Phase | Skill folder |
|-------|----------------|
| Refine ideas | [`idea-refine`](idea-refine/SKILL.md) |
| Specs | [`spec-driven-development`](spec-driven-development/SKILL.md) |
| Planning | [`planning-and-task-breakdown`](planning-and-task-breakdown/SKILL.md) |
| Implementation | [`incremental-implementation`](incremental-implementation/SKILL.md) |
| UI | [`frontend-ui-engineering`](frontend-ui-engineering/SKILL.md) |
| APIs | [`api-and-interface-design`](api-and-interface-design/SKILL.md) |
| Context / retrieval | [`context-engineering`](context-engineering/SKILL.md) |
| Doc-aligned code | [`source-driven-development`](source-driven-development/SKILL.md) |
| Tests | [`test-driven-development`](test-driven-development/SKILL.md), [`test-engineer`](test-engineer/SKILL.md), [`browser-testing-with-devtools`](browser-testing-with-devtools/SKILL.md) |
| Debug | [`debugging-and-error-recovery`](debugging-and-error-recovery/SKILL.md) |
| Review & quality | [`code-review-and-quality`](code-review-and-quality/SKILL.md) |
| Security | [`security-auditor`](security-auditor/SKILL.md), [`security-and-hardening`](security-and-hardening/SKILL.md) |
| Performance | [`performance-optimization`](performance-optimization/SKILL.md) |
| Simplification | [`code-simplification`](code-simplification/SKILL.md) |
| Git | [`git-workflow-and-versioning`](git-workflow-and-versioning/SKILL.md) |
| CI/CD | [`ci-cd-and-automation`](ci-cd-and-automation/SKILL.md) |
| Docs / ADRs | [`documentation-and-adrs`](documentation-and-adrs/SKILL.md) |
| Deprecation | [`deprecation-and-migration`](deprecation-and-migration/SKILL.md) |
| Shipping | [`shipping-and-launch`](shipping-and-launch/SKILL.md) |
| Meta | [`using-agent-skills`](using-agent-skills/SKILL.md) |

The [`idea-refine`](idea-refine/) skill also includes supporting scripts and reference markdown for structured refinement.

## Repository layout

```
├── README.md
├── using-agent-skills/
│   └── SKILL.md
├── code-review-and-quality/
│   └── SKILL.md
├── … (one directory per skill)
└── idea-refine/
    ├── SKILL.md
    ├── scripts/
    └── …
```

## Contributing / customizing

Fork or copy skills and adjust `description` in frontmatter so your agent triggers the right skill for your stack and conventions.

## Courtesy

Courtesy and inspiration to **Addy Osmani** — Director, Google Cloud AI; best-selling author; speaker on AI, DX, and UX.

## License

No license file is bundled by default. Add one (e.g. MIT) if you want explicit terms for reuse.
