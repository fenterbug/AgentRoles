# Roles

This folder contains example subagent role specifications organized by category.

## Categories

### [Technical](./technical/)
Roles focused on software development and engineering tasks:
- [Code Reviewer](./technical/code-reviewer/) - Systematic code review and quality analysis

### [Creative](./creative/)
Roles focused on content creation and design:
- [Technical Writer](./creative/technical-writer/) - Technical documentation and API references

### [Workflow](./workflow/)
Roles focused on process and coordination:
- Coming soon: Project Manager, Scrum Master, Release Coordinator

### [Specialized](./specialized/)
Domain-specific expertise roles:
- [Security Auditor](./specialized/security-auditor/) - Security analysis and vulnerability assessment

## Using These Roles

Each role folder contains a `ROLE.md` file with:

- **YAML Frontmatter**: Metadata about the role (name, description, category, capabilities)
- **Detailed Instructions**: How the role operates and makes decisions
- **Concrete Examples**: Real scenarios showing the role in action
- **Guidelines**: Do's and don'ts for the role
- **Boundaries**: Clear constraints on what the role does and doesn't do

## Contributing New Roles

When adding a new role:

1. Create a new folder under the appropriate category: `[category]/[role-name]/`
2. Copy the template from `/template/ROLE.md`
3. Fill in all required sections with role-specific content
4. Provide at least 3 diverse, concrete examples
5. Clearly define responsibilities and constraints
6. Update this README with a link to the new role

## Role Design Tips

**Good roles are:**
- Focused on a specific type of work
- Clearly scoped with explicit boundaries
- Demonstrated through concrete examples
- Composable with other roles
- Implementation-agnostic

**Avoid:**
- Kitchen sink roles that try to do everything
- Vague or abstract descriptions
- Roles without clear examples
- Overlapping responsibilities with existing roles
- Implementation-specific details

See [/spec/DESIGN-PRINCIPLES.md](../spec/DESIGN-PRINCIPLES.md) for more guidance.

## Future Roles

Roles we're considering adding:

**Technical:**
- Refactoring Specialist
- Test Engineer
- Performance Optimizer
- API Designer
- Database Architect

**Creative:**
- Content Strategist
- UX Writer
- Visual Designer
- Editor

**Workflow:**
- Project Manager
- Scrum Master
- Release Coordinator
- Sprint Planner
- Stakeholder Liaison

**Specialized:**
- Data Analyst
- DevOps Engineer
- Accessibility Specialist
- Compliance Auditor
- ML Engineer

Have an idea for a role? See [CONTRIBUTING.md](../CONTRIBUTING.md) for how to propose new roles.
