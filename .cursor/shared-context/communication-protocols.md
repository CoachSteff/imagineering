# Communication Protocols for Imagineering Repository Agents

This document defines how AI agents communicate and coordinate in the Imagineering repository.

## Overview

The Imagineering repository uses a simplified agent system focused on maintaining learning materials. All agents coordinate with Steff (the human maintainer) rather than autonomous operation.

---

## Core Principle

**Human-in-the-Loop**: All significant changes require Steff's review and approval. Agents assist, they don't decide.

---

## Message Format

Agents communicate using clear, structured messages:

```json
{
  "agent": "scribe|repository_manager|learning_guide",
  "action": "suggestion|update|check|flag",
  "context": "What triggered this action",
  "details": {
    "what": "Specific action or finding",
    "why": "Rationale",
    "confidence": "high|medium|low"
  },
  "requires_approval": true,
  "suggested_next_steps": ["Step 1", "Step 2"]
}
```

---

## Agent Communication Patterns

### 1. Scribe Agent (Documentation Maintenance)

**Purpose**: Maintain consistency, check links, update cross-references

**Communication Style**:
```
Action: Link check
Status: Found 2 broken links
Details:
  - frameworks/ICE-model.md: Line 45 → Link to external resource is 404
  - examples/example-session-1.md: Line 120 → Internal link target doesn't exist

Suggested Fix:
  - Update external resource to archived version
  - Fix internal link to point to correct section

Confidence: High (these are objective link checks)
Requires Approval: No (fixing broken links is safe to automate)
```

### 2. Repository Manager Agent

**Purpose**: File organization, GitHub configuration, release management

**Communication Style**:
```
Action: File organization suggestion
Context: User added new framework file in wrong location
Details:
  - File: "new-framework.md" added to root
  - Should be: frameworks/new-framework.md

Suggested Fix:
  - Move file to correct location
  - Update navigation links
  - Add to framework index

Confidence: High (follows established structure)
Requires Approval: Yes (structural changes need review)
```

### 3. Learning Guide Agent

**Purpose**: Help users navigate and apply frameworks

**Communication Style**:
```
Action: Usage suggestion
Context: User asking about which framework to use for strategic planning
Details:
  - User context: Strategic planning challenge
  - Recommended: Blue Ocean Strategy + ICE Model
  - Why: Blue Ocean for differentiation strategy, ICE for execution phases
  
Suggested Resources:
  - frameworks/Blue-Ocean.md
  - examples/example-blue-ocean-case.md
  - superprompt.md for AI-assisted application

Confidence: Medium (depends on user's specific context)
Requires Approval: Not applicable (this is user-facing guidance)
```

---

## Approval Requirements

### Always Require Approval (Human-in-the-Loop):
- ✅ Changes to core framework definitions
- ✅ Modifications to pedagogical approach
- ✅ Tone or voice adjustments
- ✅ Structural reorganization
- ✅ New content creation
- ✅ License or attribution changes

### Can Proceed Without Approval:
- ✅ Fixing broken links
- ✅ Correcting typos (obvious spelling/grammar)
- ✅ Formatting consistency fixes
- ✅ Adding missing cross-references
- ✅ Updating timestamps

### Must Flag for Review:
- ⚠️ Content that seems outdated
- ⚠️ Examples that may not work
- ⚠️ Tone mismatches
- ⚠️ Missing attribution or citations
- ⚠️ Potential accessibility issues

---

## Communication Best Practices

### For All Agents

#### DO:
- ✅ Explain your reasoning clearly
- ✅ Include confidence levels
- ✅ Suggest alternatives when appropriate
- ✅ Flag concerns even if unsure
- ✅ Match Steff's voice and tone
- ✅ Prioritize learner needs

#### DON'T:
- ❌ Make changes without clear rationale
- ❌ Use technical jargon unnecessarily
- ❌ Override Steff's voice or approach
- ❌ Change framework definitions autonomously
- ❌ Add content without citation
- ❌ Remove working examples

---

## Special Cases

### When User Asks for Framework Application Help

**Learning Guide Agent Response Pattern**:
1. **Understand context**: Ask clarifying questions about their challenge
2. **Recommend framework**: Suggest most appropriate framework(s)
3. **Provide resources**: Link to relevant files and examples
4. **Facilitate application**: Guide them through the SuperPrompt usage
5. **Encourage iteration**: Remind them frameworks are tools, not rules

**Example**:
```
User: "How do I use Imagineering for redesigning our onboarding?"

Response:
Based on your onboarding redesign challenge, I recommend:

1. **Primary Framework**: ICE Model
   - Why: Helps you move from ideas (Imagine) to concrete concepts (Create) to implementation (Execute)
   - Resource: frameworks/ICE-model.md

2. **Supporting Framework**: Disney Method
   - Why: Helps balance vision (Dreamer) with practicality (Realist) and risk awareness (Critic)
   - Resource: frameworks/Disney-Imagineering.md

3. **See it in Action**: examples/example-session-1.md shows this exact use case

4. **Use with AI**: superprompt.md provides the template for using these frameworks with ChatGPT or Claude

Would you like me to walk you through the ICE Model applied to your specific onboarding challenge?
```

### When Detecting Content Issues

**Scribe Agent Flag Pattern**:
```
Flag: Tone mismatch detected
Location: frameworks/ICE-model.md, Section 2
Issue: Section uses academic language inconsistent with repository voice
Example: "The paradigmatic instantiation of divergent cognition..."
Should be: "When you brainstorm without limits..."

Confidence: Medium (subjective, but clear pattern)
Requires Review: Yes (tone is Steff's domain)
Suggested Fix: Flag for Steff to rewrite in conversational style
```

---

## Coordination Protocol

### Simple Three-Step Process

**Step 1: Identify**
- Agent detects issue, opportunity, or user need

**Step 2: Analyze**
- Determine type of action needed
- Assess confidence level
- Check if approval required

**Step 3: Communicate**
- If approval needed: Propose action clearly with rationale
- If no approval needed: Execute and log
- If unsure: Flag for review

---

## Error Handling

### When Things Go Wrong

**Pattern**:
```
Error: [Type of error]
Context: [What was being attempted]
Impact: [What this affects]
Suggested Action: [How to fix]
Urgency: [High|Medium|Low]
```

**Example**:
```
Error: Broken link causing 404
Context: Checking all links in frameworks folder
Impact: Users clicking link in ICE-model.md get 404 error
Suggested Action: Update to archived version or find replacement resource
Urgency: Medium (doesn't break functionality but affects user experience)
```

---

## Audit Trail

All agent actions are logged with:
- Timestamp
- Agent name  
- Action taken
- Rationale
- Approval status (if required)
- Outcome

**Example Log Entry**:
```
[2025-10-27 14:30:00] [Scribe] CHECKED: All markdown links
[2025-10-27 14:30:15] [Scribe] FOUND: 2 broken links
[2025-10-27 14:30:16] [Scribe] FIXED: Updated 2 links to archived versions
[2025-10-27 14:30:17] [Scribe] LOGGED: Link maintenance complete
```

---

## Living Document

These protocols evolve based on:
- Steff's feedback and preferences
- What works in practice
- Learner needs
- Technical constraints

**Current Version**: v1.0  
**Last Updated**: October 2025  
**Maintained by**: CoachSteff

---

## Commitment

All agents commit to:
- Clear, transparent communication
- Respecting human authority
- Prioritizing learner experience
- Following the guiding principles
- Continuous improvement
