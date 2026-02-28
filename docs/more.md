# ROLE.md vs AGENTS.md

## The Problem with One-Size-Fits-All

AGENTS.md is like a business owner who tries to do everything: accounting, marketing, development, customer service, and operations. It works for small projects, but as your project grows, this approach becomes inefficient.

## Specialization Through ROLE.md

ROLE.md is like building a team of specialists. Instead of every agent loading every project rule:

- **Token efficiency**: Agents load only relevant instructions for their task
- **Better performance**: Focused context yields better results
- **Easier maintenance**: Update specialist roles without touching global rules
- **Clearer boundaries**: Each role has defined responsibilities

**When to use each:**

- **AGENTS.md**: Universal rules (code style, git conventions, testing standards)
- **ROLE.md**: Task-specific expertise (database migrations, API design, documentation generation)

Your main agent follows AGENTS.md. When it spawns a subagent for a specialized task, that subagent gets the relevant ROLE.md instead of the entire project rulebook.
