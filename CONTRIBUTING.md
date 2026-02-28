# Contributing to Subagent Roles

Thank you for your interest in contributing! This document provides guidelines for contributing new role specifications or improving existing ones.

## How to Contribute

There are several ways to contribute:

1. **Create a new role specification**
2. **Improve an existing role**
3. **Fix errors or typos**
4. **Improve documentation**
5. **Share feedback on role effectiveness**

## Creating a New Role

### Before You Start

1. **Check if the role already exists** - Review `/roles` to avoid duplication
2. **Ensure it's sufficiently distinct** - The role should have a clear, unique purpose
3. **Consider scope** - Roles should be focused, not try to do everything
4. **Think about composition** - How will this role work with existing roles?

### Step-by-Step Process

1. **Copy the template**
   ```bash
   cp template/ROLE.md roles/[category]/[role-name]/ROLE.md
   ```

2. **Fill in the YAML frontmatter**
   - `name`: lowercase-with-hyphens
   - `description`: Clear, specific purpose statement
   - `category`: technical, creative, workflow, or specialized
   - `capabilities`: List of specific capabilities
   - `expertise_level`: beginner, intermediate, advanced, or expert
   - Optional fields as appropriate

3. **Write the content**
   - **Purpose**: Why does this role exist? What problems does it solve?
   - **Responsibilities**: What is the role responsible for?
   - **Approach**: How does the role think and make decisions?
   - **Examples**: At least 3 diverse, concrete examples
   - **Guidelines**: Clear do's and don'ts
   - **Constraints**: What the role does NOT do

4. **Test your role**
   - Try using the role specification with real tasks
   - Get feedback from potential users
   - Refine based on actual usage

5. **Submit your role**
   - Create a pull request with your new role
   - Explain the use case and why it's needed
   - Include any testing or validation you've done

## Quality Guidelines

### Required Elements

Every role MUST have:
- [ ] Valid YAML frontmatter with all required fields
- [ ] Clear purpose statement
- [ ] Specific responsibilities list
- [ ] At least 3 concrete examples
- [ ] Guidelines (do's and don'ts)
- [ ] Explicit constraints/boundaries

### Writing Guidelines

**Be Specific**
- ❌ "Reviews code for issues"
- ✅ "Reviews code for security vulnerabilities, focusing on OWASP Top 10, SQL injection, XSS, and authentication flaws"

**Show, Don't Just Tell**
- Include concrete code examples
- Demonstrate the role's thinking process
- Show different scenarios and edge cases

**Define Boundaries**
- State what the role does NOT do
- Clarify overlaps with other roles
- Set clear scope limits

**Use Consistent Formatting**
- Follow the template structure
- Use markdown formatting correctly
- Maintain consistent style

### Example Quality

Good examples:
- Show realistic scenarios
- Include sufficient context
- Demonstrate the role's approach
- Show actual output/results
- Cover different complexity levels

Poor examples:
- Vague or abstract scenarios
- Missing context
- No demonstration of thinking
- Trivial or unrealistic cases

## Categories

Choose the most appropriate category:

### Technical
Software development and engineering:
- Code review, testing, debugging
- Architecture and design
- Performance optimization
- Development tools

### Creative
Content creation and design:
- Writing and editing
- Visual and UX design
- Ideation and strategy
- Content planning

### Workflow
Process and coordination:
- Project management
- Planning and organization
- Documentation and knowledge management
- Process improvement

### Specialized
Domain-specific expertise:
- Security and compliance
- Data science and analytics
- DevOps and infrastructure
- Domain knowledge (legal, medical, financial, etc.)

If your role doesn't fit clearly, consider:
- Is it too broad? Break it into multiple focused roles
- Does it overlap with existing roles? Build on or extend existing role
- Is it truly specialized? It might fit in "specialized"

## Improving Existing Roles

Found a way to improve an existing role? Great!

### Small Improvements
For typos, clarifications, or minor fixes:
1. Make the change
2. Submit a pull request
3. Increment the PATCH version (1.0.0 → 1.0.1)

### Adding Content
For new examples, guidelines, or sections:
1. Ensure additions are consistent with existing role
2. Submit a pull request
3. Increment the MINOR version (1.0.0 → 1.1.0)

### Breaking Changes
For changes that significantly alter the role's behavior:
1. Discuss the change first (open an issue)
2. Consider if this should be a new role instead
3. If proceeding, increment MAJOR version (1.0.0 → 2.0.0)
4. Document what changed and why

## Review Process

All submissions will be reviewed for:

1. **Completeness**: All required sections present
2. **Quality**: Clear writing, good examples, specific guidance
3. **Consistency**: Follows the specification and existing patterns
4. **Usefulness**: Solves a real problem
5. **Uniqueness**: Doesn't duplicate existing roles

Reviewers may request:
- Additional examples
- Clarification of scope
- Refinement of boundaries
- Better organization
- Testing with real scenarios

## Testing Roles

Before submitting, test your role:

1. **Self-test**: Try to use the role yourself
2. **Peer review**: Have others read and apply the role
3. **Real scenarios**: Test with actual tasks, not hypotheticals
4. **Edge cases**: Try unusual or challenging scenarios
5. **Composition**: Test how it works with other roles

Document your testing in the pull request.

## Style Guide

### Tone
- Professional but approachable
- Educational, not prescriptive
- Specific and concrete
- Encouraging and constructive

### Formatting
- Use markdown headers appropriately
- Use code blocks for code examples
- Use lists for scannable content
- Use tables for structured data
- Use bold/italic sparingly for emphasis

### Language
- Active voice preferred
- Second person for instructions ("You should...")
- Clear, direct sentences
- Avoid jargon or define it
- Use examples to clarify

## Recognition

Contributors will be:
- Listed in the CONTRIBUTORS.md file
- Credited in the role's YAML (author field)
- Acknowledged in release notes

## Questions?

Not sure about something?

- Check the [Specification](./spec/SPECIFICATION.md)
- Review [Design Principles](./spec/DESIGN-PRINCIPLES.md)
- Look at existing roles for examples
- Open an issue to discuss before coding

## Code of Conduct

- Be respectful and constructive
- Focus on ideas, not individuals
- Welcome newcomers
- Give credit where due
- Assume good intentions

## License

By contributing, you agree that your contributions will be licensed under the Apache 2.0 License, same as this project.

## Thank You!

Your contributions help make AI subagents more effective and accessible for everyone. Thank you for taking the time to contribute!
