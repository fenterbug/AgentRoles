# Template

This folder contains the template for creating new subagent role specifications.

## Using the Template

The `ROLE.md` file in this folder serves as a comprehensive starting point for creating new roles. 

### Quick Start

1. Copy the `ROLE.md` file to a new folder under `roles/[category]/[role-name]/`
2. Update the YAML frontmatter with your role's metadata
3. Replace all placeholder text with role-specific content
4. Remove sections that aren't applicable (but consider keeping most)
5. Add any custom sections needed for your specific role

### Template Sections

The template includes the following sections (all are recommended but some may be optional depending on your role):

- **Frontmatter** (Required): YAML metadata defining the role
- **Purpose** (Required): Clear statement of what the role does
- **Responsibilities** (Required): Specific duties and scope
- **Approach & Methodology** (Required): How the role operates
- **Capabilities** (Recommended): What the role can do
- **Communication Style** (Recommended): How the role interacts
- **Examples** (Required): Concrete scenarios and responses
- **Guidelines** (Required): Do's and don'ts
- **Constraints & Boundaries** (Recommended): Limitations and scope
- **Success Criteria** (Recommended): How to measure effectiveness
- **Collaboration** (Optional): How this role works with others
- **Knowledge & Skills** (Optional): Prerequisites
- **Tools & Resources** (Optional): Supporting materials
- **Anti-Patterns** (Recommended): Common mistakes to avoid

### Tips for Writing Effective Roles

1. **Be Specific**: Vague roles lead to inconsistent behavior
2. **Provide Examples**: Show, don't just tell
3. **Define Boundaries**: Clear constraints improve focus
4. **Consider Context**: Think about when and how the role will be used
5. **Test Thoroughly**: Validate the role specification with real scenarios
6. **Iterate**: Refine based on actual usage

### Frontmatter Fields

Required fields:
- `name`: Unique identifier (lowercase, hyphenated)
- `description`: Clear purpose statement
- `category`: One of: technical, creative, workflow, specialized
- `capabilities`: List of specific capabilities
- `expertise_level`: One of: beginner, intermediate, advanced, expert

Optional fields:
- `tags`: Additional categorization
- `version`: Semantic versioning for the role spec
- `author`: Creator of the role
- `dependencies`: Other roles this depends on
- `context_requirements`: What context the role needs
