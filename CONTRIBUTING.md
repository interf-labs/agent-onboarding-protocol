# Contributing to the Agent Onboarding Protocol

The canonical dependency types grow over time as more enterprise rollouts are documented. We welcome contributions that expand coverage across new systems, sectors, and use-cases.

## Adding a New Canonical Type

1. **Find the right category** — `integration`, `auth`, `data`, `infrastructure`, `stakeholder`, or `process`
2. **Create or update the `.md` file** in `skills/protocol/types/<category>/`
3. **Use this format:**

```markdown
---
id: category.subcategory.name
name: Human Readable Name
category: category
systems: [system-a, system-b]
requires: [other.type.id]
blocked_by: [other.type.id]
related: [other.type.id]
sectors: [all]  # or specific: [healthcare, financial-services]
---

# Human Readable Name

One paragraph description. When does a vendor need this? Why?

## Template

- **what:** What the vendor says they need (plain English)
- **ready:** How enterprise verifies it's done (acceptance criteria)

## Matches

Use this type when vendor says: "keyword", "phrase", "another phrase"
```

4. **Update the category `overview.md`** — add your type to the table
5. **Update `types/index.md`** — update the type count
6. **Submit a PR** with a clear description of what use-case this covers

## What Makes a Good Canonical Type

- **Real** — it comes from an actual enterprise rollout, not speculation
- **Common** — it applies across multiple vendors/enterprises, not just one
- **Distinct** — it's not already covered by an existing type
- **Actionable** — the template `what` + `ready` is specific enough to act on

## Review Process

1. PR is submitted with the new type
2. Maintainers review for accuracy, uniqueness, and formatting
3. We may ask clarifying questions or suggest improvements
4. Once approved, the type is merged and becomes part of the canonical registry
