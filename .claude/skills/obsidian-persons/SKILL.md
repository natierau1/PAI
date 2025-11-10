---
name: obsidian-persons
description: Manage people and relationships in Obsidian vault - track who you work with, assess relationship closeness/importance (Tier 1-5), update people lists from active projects, and analyze collaboration patterns. USE WHEN user says 'update people list', 'how close am I to [person]', 'who am I working with', 'assess my relationships', or needs relationship/collaborator tracking.
---

# Obsidian Persons - Relationship Management

## When to Activate This Skill

**Explicit triggers:**
- "Update my people list"
- "Refresh active project collaborators"
- "How close am I to [person]?"
- "Who am I working with on [project]?"
- "Assess my relationship with [person]"
- "Who are my Tier 1 relationships?"
- "Find people I depend on"
- "Show me relationship risks"

**Implicit triggers:**
- Weekly/monthly reviews involving relationship assessment
- After significant project updates involving team changes
- When user mentions relationship management or networking
- During strategic planning around key collaborators

## Core Capabilities

### 1. Update People Lists from Active Projects
Scan ON/Ongoing project folders, extract all collaborators, categorize by relationship tier, update master people list.

### 2. Relationship Tier Assessment
Evaluate how close/important someone is using 5-tier framework:
- **Tier 1:** Core (Pivotal to life & work) - Family, daily partners
- **Tier 2:** Strategic Partners (High importance) - Key collaborators
- **Tier 3:** Active Collaborators (Regular contact) - Project-based
- **Tier 4:** Occasional/Emerging (New or infrequent) - Early-stage
- **Tier 5:** Passive (Past or minimal contact) - Archived

### 3. Collaboration Pattern Analysis
Map people to projects, identify multi-project collaborators, find single-point dependencies, discover emerging strategic relationships.

### 4. Person Note Management
Create/update individual person notes with relationship context, expertise, project history, and communication preferences.

### 5. Relationship Health Monitoring
Track last contact dates, response patterns, project health correlation, flag relationships needing attention.

## Quick Workflows

**Update people list:**
```
1. Scan /3 Efforts/ON/ and /3 Efforts/Ongoing/
2. Extract people + roles
3. Categorize by tier
4. Update Atlas Dots/Lists/People - Active Projects.md
5. Report changes
```

**Assess person's tier:**
```
1. Count project appearances
2. Check last contact date
3. Review project outcomes
4. Evaluate strategic importance
5. Recommend tier (1-5)
```

**Find relationship risks:**
```
1. Map people to critical projects
2. Identify sole contacts for important work
3. Flag single-point dependencies
4. Suggest diversification
```

## Key Paths

**Obsidian Vault:** `/Users/irautenbach/Documents/Obsidian/Personal/`

**Important locations:**
- `3 Efforts/ON/` - Active projects (PT*/OPT*)
- `3 Efforts/Ongoing/` - Ongoing projects
- `Atlas Dots/Lists/` - People lists
- `Atlas Dots/` - Individual person notes
- `Diary/` - Interaction history

## Relationship Tier Quick Reference

| Tier | Name | Interaction | Impact | Examples |
|------|------|-------------|--------|----------|
| 1 | Core | Daily/weekly | Pivotal to life/work | Family, Kirsty, Ron, Michael C. |
| 2 | Strategic | Weekly/bi-weekly | Key to major projects | Yanis, David H., Adam Shore |
| 3 | Active | Project-based | Specific expertise | Shailendra, Steward, Jim F. |
| 4 | Occasional | Infrequent | Potential/exploratory | Judy (Mazars), Keith Zammit |
| 5 | Passive | Rare/none | Historical | Past collaborators |

## Common Operations

**Full refresh:**
```
"Update my people list from active projects"
```

**Single person assessment:**
```
"How important is [person] to my work?"
"Assess my relationship with [person]"
```

**Pattern analysis:**
```
"Who am I working with most?"
"Show me my multi-project collaborators"
"Find my relationship dependencies"
```

**Tier queries:**
```
"List all Tier 1 relationships"
"Who should I promote to Tier 2?"
"Show me emerging strategic relationships"
```

## Integration Points

- **Project files:** Extract team members, roles, references
- **Diary entries:** Track interaction frequency and context
- **Weekly reviews:** Automate relationship tier updates
- **Person notes:** Maintain individual relationship records

## Supplementary Resources

For detailed methodology, tier criteria, person note templates, and advanced workflows:

```bash
read ~/PAI/.claude/skills/obsidian-persons/CLAUDE.md
```

## Key Principles

1. **Relationship-centric view:** People are foundation of all work
2. **Objective assessment:** Tier based on data (frequency, projects, impact)
3. **Proactive maintenance:** Monitor health, flag issues early
4. **Privacy-conscious:** Professional focus, sensitive handling
5. **Graph-aware:** Leverage Obsidian's bidirectional linking
