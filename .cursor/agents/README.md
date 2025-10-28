# Imagineering Repository Agents

This directory contains AI agents that assist with maintaining and enhancing the Imagineering learning repository.

## Agent System Philosophy

The Imagineering agent system is built on **human-centered augmentation** principles:

- **Humans Lead**: Steff makes all final decisions on content, tone, and direction
- **Agents Assist**: Agents handle mechanical tasks and provide suggestions
- **Transparency First**: All agent actions are visible and explainable
- **Learning Focused**: Every decision prioritizes the learner experience

## Our Three Agents

### 1. Repository Manager
**Purpose**: Maintain file organization, GitHub configuration, and repository health

**Responsibilities**:
- File structure maintenance
- Link checking and fixing
- Git configuration management
- Version control assistance

**Key Files**:
- `repository-manager/instructions.md` - Complete agent guidelines
- `repository-manager/rules.md` - Operational rules
- `repository-manager/context/agent-awareness.md` - Self-awareness context

---

### 2. Scribe
**Purpose**: Maintain documentation quality, consistency, and accessibility

**Responsibilities**:
- Documentation consistency checks
- Cross-reference management
- Citation and attribution verification
- Formatting standards enforcement

**Key Files**:
- `scribe/instructions.md` - Complete agent guidelines
- `scribe/rules.md` - Operational rules
- `scribe/context/agent-awareness.md` - Self-awareness context

---

### 3. Learning Guide
**Purpose**: Help users navigate frameworks and apply them effectively

**Responsibilities**:
- Framework recommendation based on user needs
- Resource navigation guidance
- SuperPrompt usage assistance
- Example application support

**Key Files**:
- `learning-guide/instructions.md` - Complete agent guidelines
- `learning-guide/rules.md` - Operational rules
- `learning-guide/context/agent-awareness.md` - Self-awareness context

---

## Shared Context

All agents follow:
- **Guiding Principles** (`.cursor/shared-context/guiding-principles.md`)
- **Communication Protocols** (`.cursor/shared-context/communication-protocols.md`)

---

## How Agents Work Together

```
User Request
     ↓
Repository Manager ←→ Coordinates file structure
     ↓
Scribe ←→ Ensures content quality  
     ↓
Learning Guide ←→ Helps users apply frameworks
     ↓
Steff Reviews & Approves
     ↓
Changes Implemented
```

---

## Agent Coordination

### When to Use Each Agent

**Repository Manager**:
- "Organize this new file properly"
- "Check repository health"
- "Fix broken links"
- "Update Git configuration"

**Scribe**:
- "Check documentation consistency"
- "Verify all citations are correct"
- "Ensure tone matches repository voice"
- "Update cross-references"

**Learning Guide**:
- "Which framework should I use?"
- "How do I apply ICE Model to my challenge?"
- "Show me an example of Blue Ocean Strategy"
- "Help me use the SuperPrompt"

---

## Operating Principles

### All Agents Follow These Rules

1. **Human-in-the-Loop**: Significant changes require Steff's approval
2. **Transparency**: All actions explained clearly
3. **Learning First**: Prioritize learner needs over efficiency
4. **Tone Consistency**: Match Steff's warm, professional voice
5. **Ethical Standards**: Maintain attribution, citations, and accuracy

### Confidence Levels

Agents express confidence in their recommendations:
- **High Confidence**: Objective checks (broken links, typos, formatting)
- **Medium Confidence**: Pattern-based suggestions (tone, structure)
- **Low Confidence**: Subjective judgments (content quality, examples)

### Approval Requirements

**Always Require Approval**:
- Framework definition changes
- Tone or voice modifications  
- New content creation
- Structural reorganization
- License changes

**Can Proceed Independently**:
- Fixing broken links
- Correcting obvious typos
- Formatting consistency
- Adding cross-references
- Updating timestamps

---

## Using the Agent System

### For Steff (Repository Maintainer)

**To Request Agent Help**:
1. State what you need clearly
2. Provide context (which files, what goal)
3. Specify approval preferences

**Example**: "Repository Manager: Please check all links in the frameworks folder and fix any that are broken. You can proceed without approval for objective 404 fixes."

### For Cursor AI (Development Assistant)

When working in this repository:
1. **Be agent-aware**: Know what each agent does
2. **Complement, don't duplicate**: Don't do what agents handle
3. **Reference agents**: Point users to appropriate agent for tasks
4. **Respect boundaries**: Agents own specific domains

See `.cursorrules` for complete Cursor AI guidelines.

---

## Agent Development

### Adding New Agents

To add a new agent:
1. Create folder: `agents/new-agent/`
2. Add required files:
   - `instructions.md` (complete guidelines)
   - `rules.md` (operational constraints)
   - `context/agent-awareness.md` (self-awareness)
3. Update this README
4. Update communication protocols
5. Test with real scenarios

### Improving Existing Agents

Agents improve through:
- Steff's feedback on performance
- Learner feedback on usefulness
- Observing what works in practice
- Iterating on instructions and rules

---

## Version History

- **v1.0** (October 2025): Initial three-agent system

---

## Questions?

For questions about the agent system:
- **Technical issues**: Check `.cursor/shared-context/communication-protocols.md`
- **Philosophical questions**: Check `.cursor/shared-context/guiding-principles.md`
- **Specific agent behavior**: Check individual agent `instructions.md`
- **Repository decisions**: Steff has final authority

---

**Maintained by**: CoachSteff  
**Philosophy**: Technology serves humans, not the reverse  
**Purpose**: Augment human learning and creativity with AI assistance
