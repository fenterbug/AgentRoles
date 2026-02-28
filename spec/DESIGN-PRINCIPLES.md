# Design Principles for Subagent Roles

This document outlines the core design principles that guide the creation and evolution of the Subagent Role Specification.

## Core Principles

### 1. Clarity Over Cleverness

Role specifications should be immediately understandable. Favor explicit, clear definitions over clever or terse descriptions.

**Why**: Clarity ensures consistent interpretation by both humans and AI agents. Ambiguity leads to unpredictable behavior.

**Example**:
- ✅ Good: "Review code for security vulnerabilities, focusing on SQL injection, XSS, and authentication issues"
- ❌ Poor: "Review code for issues"

### 2. Behavior Over Implementation

Focus on *what* the role does and *how* it approaches problems, not on implementation details of the AI system.

**Why**: Role specifications should be implementation-agnostic, allowing different AI systems to adopt the roles in their own way.

**Example**:
- ✅ Good: "Analyze code systematically, checking for common patterns before edge cases"
- ❌ Poor: "Use a trained model to classify code quality"

### 3. Scoped Autonomy

Each role should have a well-defined scope with appropriate autonomy within that scope. Roles know what they're responsible for and what's outside their domain.

**Why**: Clear boundaries prevent scope creep and make roles more predictable and composable.

**Example**:
- A Code Reviewer role reviews code but doesn't make architectural decisions
- A Security Auditor identifies vulnerabilities but doesn't implement fixes

### 4. Composability

Roles should be designed to work together. Consider how roles interact, hand off work, and complement each other.

**Why**: Complex tasks often require multiple specialized perspectives. Composable roles enable sophisticated workflows.

**Example**:
- Code Reviewer → Refactoring Specialist → Test Engineer
- Technical Writer → Editor → Publication Manager

### 5. Demonstrable Through Examples

Every role should be demonstrable through concrete examples. If you can't show it, you can't specify it effectively.

**Why**: Examples bridge the gap between abstract definitions and practical application. They serve as test cases for role effectiveness.

**Guideline**: Include at least 3 diverse examples that cover:
- A typical use case
- An edge case
- A complex scenario

### 6. Explicit Constraints

What a role *doesn't* do is as important as what it does. Explicitly define boundaries and limitations.

**Why**: Prevents scope creep, reduces confusion, and makes roles more predictable.

**Example**:
```markdown
## Constraints
- Does NOT write production code (only reviews)
- Does NOT make architectural decisions
- Does NOT have access to deployment systems
```

### 7. Testable Outcomes

Role specifications should enable measurable success criteria. Good roles have clear indicators of effectiveness.

**Why**: Enables validation, improvement, and accountability.

**Example**:
```markdown
## Success Criteria
- All code review comments are actionable
- Reviews completed within 30 minutes for PRs under 500 lines
- At least 80% of suggestions are accepted
```

### 8. Consistent Communication Style

Each role should have a consistent, appropriate communication style that matches its purpose and audience.

**Why**: Communication style is part of the persona that makes roles feel natural and appropriate to their function.

**Example**:
- Mentor roles: Encouraging, explanatory
- Security auditor: Direct, specific, severity-focused
- Creative director: Inspirational, visionary

### 9. Progressive Disclosure

Start with essential information, then provide details. Roles should be useful at a glance but detailed when needed.

**Why**: Makes roles accessible to different audiences and use cases.

**Structure**:
1. Name and description (quick overview)
2. Purpose and responsibilities (core function)
3. Examples (practical application)
4. Detailed guidelines (deep reference)

### 10. Evolution Over Perfection

Roles should be versioned and improved over time based on real usage. Start good, iterate to great.

**Why**: No specification is perfect from the start. Real-world usage reveals improvements.

**Practice**:
- Use semantic versioning
- Document changes
- Gather feedback
- Iterate based on actual usage patterns

## Anti-Patterns

### ❌ Avoid: The Kitchen Sink Role

**Problem**: Trying to make one role do everything.

**Solution**: Create focused, specialized roles that compose together.

### ❌ Avoid: Vague Responsibilities

**Problem**: "Handle development tasks" or "Help with writing"

**Solution**: Specific, concrete responsibilities with clear scope.

### ❌ Avoid: Implementation Leakage

**Problem**: Specifying AI system internals like prompts or model selection.

**Solution**: Focus on behavior, outcomes, and approach.

### ❌ Avoid: No Examples

**Problem**: Pure prose descriptions without concrete demonstrations.

**Solution**: Always include multiple detailed examples.

### ❌ Avoid: Unstated Assumptions

**Problem**: Assuming context or knowledge without stating it explicitly.

**Solution**: Document all requirements, assumptions, and prerequisites.

### ❌ Avoid: Orphaned Roles

**Problem**: Roles that don't work with or relate to other roles.

**Solution**: Consider composition and collaboration patterns.

## Design Questions

When creating a new role, ask:

1. **Scope**: Can I clearly state what this role does and doesn't do?
2. **Value**: Does this role solve a real, specific problem?
3. **Examples**: Can I demonstrate this role with 3+ concrete examples?
4. **Boundaries**: Have I explicitly stated the constraints?
5. **Composition**: How does this role work with other roles?
6. **Communication**: What's the appropriate voice and style?
7. **Success**: How will I know if this role is effective?
8. **Uniqueness**: Is this distinct from existing roles?

## Evaluation Criteria

A well-designed role specification:

- ✅ Has a clear, specific purpose
- ✅ Includes concrete, diverse examples
- ✅ Defines explicit boundaries and constraints
- ✅ Specifies success criteria
- ✅ Uses consistent communication style
- ✅ Considers composition with other roles
- ✅ Is implementation-agnostic
- ✅ Can be validated and improved over time

## Version History

- **1.0.0** (2026-02-23): Initial design principles
