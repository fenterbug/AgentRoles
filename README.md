# Agent Roles

Agent Roles are a simple, open format for giving agents and subagents scope to their expertise.

Roles are files (or folders) of instructions, scripts, and resources that agents can use to perform better at specific tasks. Write once, use everywhere.

## What about AGENTS.md and Agent Skills?

**Agent Roles extend AGENTS.md for specialized subagents.**

[AGENTS.md](https://agents.md/) provides project-wide guidelines for all agents. As project guidelines and task complexity grow, you can extend AGENTS.md with specialized roles that have focused expertise—like hiring staff with specific skills rather than expecting one person to master everything. This reduces token overhead and cognitive load, letting agents perform their specific tasks more effectively.

**Agent Roles work with or without SKILL.md.**

Agent Roles and [Agent Skills](https://agentskills.io/) work in parallel to do different things, and they compliment each other well. With Agent Skills, roles can reference skills to load task-specific procedures. Without Agent Skills, skill references degrade gracefully into descriptive capability hints. And since roles only need to reference applicable skills, you furthur reduce token and context load for the agent.

- **AGENTS.md** defines _what_ is being worked on.
- **Agent Skills** defines _how_ to do the work.
- **Agent Roles** defines _who_ is doing the work.

## Getting Started

- Documentation - Guides and tutorials
- Specification - Format details
- Example Roles - See what's possible

This repo contains the specification, documentation, and reference SDK.

## About

Agent Roles is an open format maintained by Jason (me) and open to contributions from the community.

## License

Code in this repository is licensed under [Apache 2.0](LICENSE). Documentation is licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/). See individual directories for details.
