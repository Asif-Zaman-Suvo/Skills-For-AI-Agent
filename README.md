# Skills for AI Agent

A curated set of **[Cursor Agent Skills](https://docs.cursor.com)** — reusable `SKILL.md` playbooks that steer coding agents through real engineering workflows: from idea refinement through implementation, review, security, CI, and shipping.

Each skill is a **folder** containing a **`SKILL.md`** with YAML frontmatter (`name`, `description`) and structured instructions the agent follows when the task matches that skill.

## Quick start

1. **Clone** this repository (or copy the skill folders you care about).
2. **Install skills** where Cursor loads them — for example your user skills directory (see Cursor docs for the current path, e.g. `~/.cursor/skills-cursor/…`) or project-specific rules/skills.
3. **Start with** [`using-agent-skills`](using-agent-skills/SKILL.md): it describes how to pick the right skill for a given task.

Skills are invoked when their description matches the user’s request, or when you explicitly ask the agent to follow a named skill.

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
