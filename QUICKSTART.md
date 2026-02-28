# Quick Start Guide

Get started with Subagent Roles in 5 minutes.

## What Are Subagent Roles?

Subagent roles are structured specifications that define how AI agents should behave when performing specific types of tasks. Think of them as "personas" or "job descriptions" that an AI can adopt to handle specialized work consistently and effectively.

## When to Use Roles

Use role specifications when you need:

- **Consistency**: Same type of task should be handled the same way every time
- **Expertise**: Specialized knowledge or approach for specific tasks
- **Clarity**: Clear boundaries and expectations for what the agent should do
- **Composition**: Multiple specialized agents working together on complex tasks

## Project Structure

```
SubagentRoles/
├── README.md              # Project overview and documentation
├── CONTRIBUTING.md        # How to contribute new roles
├── LICENSE                # Apache 2.0 license
├── roles/                 # Role specifications by category
│   ├── technical/         # Software development roles
│   ├── creative/          # Content and design roles
│   ├── workflow/          # Process and coordination roles
│   └── specialized/       # Domain-specific roles
├── spec/                  # The role specification standard
│   ├── SPECIFICATION.md   # Formal spec document
│   ├── DESIGN-PRINCIPLES.md
│   └── README.md
└── template/              # Template for creating new roles
    ├── ROLE.md            # Complete role template
    └── README.md
```

## Exploring Existing Roles

Start by looking at the example roles to understand the pattern:

1. **[Code Reviewer](./roles/technical/code-reviewer/ROLE.md)** - Reviews code for quality and correctness
2. **[Technical Writer](./roles/creative/technical-writer/ROLE.md)** - Creates developer documentation
3. **[Security Auditor](./roles/specialized/security-auditor/ROLE.md)** - Identifies security vulnerabilities

Each role demonstrates:
- How to structure role definitions
- The level of detail needed
- How to provide concrete examples
- How to define boundaries

## Creating Your First Role

### Step 1: Copy the Template

```bash
cp template/ROLE.md roles/[category]/[your-role-name]/ROLE.md
```

### Step 2: Fill in the Metadata

Update the YAML frontmatter at the top:

```yaml
---
name: my-new-role
description: What this role does and when to use it
category: technical  # or creative, workflow, specialized
capabilities:
  - capability-1
  - capability-2
expertise_level: intermediate  # beginner, intermediate, advanced, expert
---
```

### Step 3: Define the Role

Complete these key sections:

1. **Purpose**: Why does this role exist? What problems does it solve?
2. **Responsibilities**: What is the role responsible for?
3. **Approach**: How does the role think and make decisions?
4. **Examples**: Show 3+ concrete scenarios (this is the most important part!)
5. **Guidelines**: Clear do's and don'ts
6. **Constraints**: What the role does NOT do

### Step 4: Write Great Examples

Examples are the most critical part. Good examples:

- Show realistic scenarios
- Include sufficient context
- Demonstrate the role's thinking process
- Show the actual output or result
- Cover different types of situations

**Example format:**

```markdown
### Example 1: [Descriptive Scenario Name]

**Context**: [Describe the situation and background]

**Approach**: [Show how the role handles this situation]

**Outcome**: [Show the result and what was accomplished]
```

### Step 5: Test Your Role

Before considering it complete:

1. Try using the role for real tasks
2. Have someone else read and use it
3. Refine based on actual usage
4. Ensure it's different from existing roles

## Using Roles in Your System

How you actually use these role specifications depends on your AI system:

### Option 1: Direct Instruction
Include the role specification in your agent's context/prompt:

```
You are adopting the Code Reviewer role. Follow the guidelines in this role specification:
[paste ROLE.md content]
```

### Option 2: Dynamic Loading
Load roles dynamically based on task requirements:

```python
def get_role_spec(role_name):
    with open(f'roles/{category}/{role_name}/ROLE.md') as f:
        return f.read()

role_spec = get_role_spec('code-reviewer')
agent.set_context(role_spec)
```

### Option 3: Role Composition
Combine multiple roles for complex tasks:

```python
pipeline = [
    RoleAgent('code-reviewer'),
    RoleAgent('security-auditor'),
    RoleAgent('technical-writer')
]
```

## Understanding the Specification

The [specification](./spec/SPECIFICATION.md) defines:

- Required and optional YAML fields
- Expected markdown sections
- Validation criteria
- Best practices

Key points:

- **Required fields**: name, description, category, capabilities, expertise_level
- **Required sections**: Purpose, Responsibilities, Approach, Examples, Guidelines
- **Minimum examples**: At least 2-3 concrete demonstrations
- **Versioning**: Use semantic versioning (MAJOR.MINOR.PATCH)

## Design Principles

The [design principles](./spec/DESIGN-PRINCIPLES.md) guide role creation:

1. **Clarity Over Cleverness**: Be explicit and clear
2. **Behavior Over Implementation**: Focus on what, not how
3. **Scoped Autonomy**: Clear boundaries and appropriate authority
4. **Composability**: Roles should work together
5. **Demonstrable**: Show through concrete examples

## Common Pitfalls

Avoid these mistakes:

❌ **Kitchen Sink Role** - Trying to do everything
✅ Create focused, specialized roles

❌ **Vague Responsibilities** - "Help with development"
✅ Specific, concrete responsibilities

❌ **No Examples** - Only prose descriptions
✅ Multiple detailed, realistic examples

❌ **Unclear Boundaries** - What does the role NOT do?
✅ Explicit constraints and limitations

## Next Steps

Now that you understand the basics:

1. **Explore** - Read through the example roles
2. **Experiment** - Try using a role specification with your AI system
3. **Create** - Build a role for your specific use case
4. **Contribute** - Share useful roles back to the community

## Getting Help

- **Questions about the spec?** See [spec/SPECIFICATION.md](./spec/SPECIFICATION.md)
- **Design guidance?** See [spec/DESIGN-PRINCIPLES.md](./spec/DESIGN-PRINCIPLES.md)
- **Contributing?** See [CONTRIBUTING.md](./CONTRIBUTING.md)
- **Examples?** Browse [roles/](./roles/)

## Examples of Role Usage

### Example: Code Review Workflow

```
1. Developer submits PR
2. AI adopts Code Reviewer role
3. AI reviews code following role guidelines
4. AI provides structured feedback
5. Developer addresses feedback
```

### Example: Documentation Pipeline

```
1. Code changes are merged
2. AI adopts Technical Writer role
3. AI updates relevant documentation
4. AI ensures examples still work
5. AI maintains consistent style
```

### Example: Security Pipeline

```
1. Code ready for review
2. AI adopts Security Auditor role
3. AI performs security analysis
4. AI reports findings with severity
5. Critical issues block deployment
```

## Best Practices

When working with roles:

1. **One Role, One Focus** - Don't try to do everything in one role
2. **Test with Real Tasks** - Validate with actual work, not hypotheticals
3. **Iterate Based on Usage** - Improve roles based on real experience
4. **Compose for Complexity** - Use multiple roles for complex workflows
5. **Version Changes** - Track role evolution with semantic versioning

## Resources

- [Main Documentation](./README.md)
- [Specification](./spec/SPECIFICATION.md)
- [Design Principles](./spec/DESIGN-PRINCIPLES.md)
- [Template](./template/ROLE.md)
- [Contributing Guide](./CONTRIBUTING.md)
- [Example Roles](./roles/)

---

**Ready to create your first role?** Start with the [template](./template/ROLE.md) and follow the pattern from the [example roles](./roles/).
