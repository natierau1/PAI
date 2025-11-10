---
name: obsidian-find-connections
description: |
  Discover meaningful connections between notes and suggest bidirectional links.

  USE WHEN user says 'find connections', 'link notes', 'discover relationships', 'related notes'
---

# Find Connections Skill

Discover meaningful connections between notes and suggest links to build your knowledge graph in ~/Documents/Obsidian/Personal/

## What This Skill Does

Analyzes notes to find:
- Thematic relationships between concepts
- Related content across different domains
- People and projects that share contexts
- Potential for new Map of Content (MOC) creation
- Missing backlinks and connection opportunities
- Cross-domain insights and patterns

## Usage

Invoke this skill with various scopes:
- "Find connections for [[Note Name]]"
- "Find related notes about [topic]"
- "Show connections between [concept1] and [concept2]"
- "Discover patterns in [folder/tag]"
- "What connects to [[Project Name]]?"
- "Find orphaned notes" (notes with no connections)

The skill will:
1. Analyze the specified note(s)
2. Search vault for related content
3. Identify connection types
4. Rate confidence levels
5. Present findings with recommendations
6. Wait for approval to add links
7. Create bidirectional connections

## Connection Types

### 1. Direct Thematic (High Confidence)
Notes that share core concepts or themes:
- Same topic from different angles
- Complementary information
- Parts of a larger concept
- Sequential development of ideas

### 2. Cross-Domain (Medium Confidence)
Connections across different Planes/ or Atlas areas:
- Similar patterns in different contexts
- Transferable principles
- Analogies and parallels
- Interdisciplinary insights

### 3. People & Project Connections (High Confidence)
Linking through relationships:
- Same person involved
- Related companies/organizations
- Connected projects
- Shared stakeholders

### 4. Temporal Connections (Medium Confidence)
Related by time:
- Ideas developing over time (diary entries)
- Projects that led to insights
- Evolution of thinking
- Before/after relationships

### 5. Weak but Interesting (Low Confidence)
Speculative or tangential:
- Potential metaphorical connections
- Emerging patterns
- Worth exploring further
- Serendipitous discoveries

## Output Format

```markdown
# Connection Analysis: [[Note Name]]

## Summary
Analyzed: [[Note Name]]
Total connections found: [X]
High confidence: [X] | Medium confidence: [X] | Low confidence: [X]

## Existing Links
Currently linked to [X] notes:
- [[Existing Link 1]]
- [[Existing Link 2]]

## Suggested Connections

### High Confidence - Direct Thematic
#### [[Related Note 1]]
- **Connection Type**: Direct thematic
- **Shared Concepts**: [concept1], [concept2]
- **Evidence**: "[Quote or excerpt showing connection]"
- **Recommendation**: Add bidirectional link
- **Context for Link**: "Related: [[Related Note 1]] explores [aspect]"

#### [[Related Note 2]]
- **Connection Type**: Complementary information
- **Why Related**: [explanation]
- **Link Text Suggestion**: "See also [[Related Note 2]] for [specific aspect]"

### Medium Confidence - Cross-Domain
#### [[Note from Different Domain]]
- **Connection Type**: Cross-domain pattern
- **Domain**: Planes/[domain1] ↔ Planes/[domain2]
- **Shared Pattern**: [what's similar]
- **Potential Insight**: [value of making connection]
- **Recommendation**: Consider linking with explanation

### Project & People Connections
#### [[Project Name]]
- **Connection Type**: Application/relevance
- **How Connected**: [this note provides context/research/background for project]
- **Action**: Link from project to this note
- **Value**: [why the project team should know about this]

#### [[Person Name]]
- **Connection Type**: Person mentioned/relevant
- **Context**: [why person relates to note]
- **Action**: Add to person's note as topic they care about

### Low Confidence - Exploratory
#### [[Potentially Related Note]]
- **Connection Type**: Speculative
- **Possible Relationship**: [hypothesis]
- **Worth Exploring**: [yes/no/maybe]
- **Action**: [Add to "explore further" list / Skip for now]

## Orphan Status
- **Incoming Links**: [count] notes link TO this note
- **Outgoing Links**: [count] notes this note links to
- **Status**: Well-connected / Needs more links / Orphaned / Hub note

## MOC Opportunities
Based on connection patterns, consider creating:
- **[[New MOC Name]]** - Could organize: [[Note 1]], [[Note 2]], [[Note 3]], [this note]
- **Or add to existing**: [[Existing MOC]] - [why it fits]

## Proposed Actions
- [ ] Add bidirectional link: [[This Note]] ↔ [[Related Note 1]]
- [ ] Add bidirectional link: [[This Note]] ↔ [[Related Note 2]]
- [ ] Add to MOC: [[Existing MOC]]
- [ ] Create new MOC: [[Topic MOC]]
- [ ] Link from [[Project]] to this note
- [ ] Add tag: #[suggested-tag]

**Approve all? / Select specific actions? / Modify?**
```

## Search Strategy

The skill uses multiple search methods:

1. **Content Similarity**
   - Extract key terms from note
   - Search for similar terms across vault
   - Look for concept overlap

2. **Tag Analysis**
   - Find notes with shared tags
   - Discover notes that should share tags

3. **Link Analysis**
   - Check existing links' links (2nd degree)
   - Find patterns in well-connected notes

4. **People & Project**
   - Search for mentioned names
   - Look for project references

5. **Temporal Proximity**
   - Check daily notes from same period
   - Find notes created/modified around same time

6. **Domain Mapping**
   - Look across all Planes/ folders
   - Check relevant Atlas Maps/

## Pattern Detection

When analyzing multiple notes, detect:

**Emerging Themes**:
```markdown
## Theme Detected: [Theme Name]

Found in [X] notes across [Y] domains:
- [[Note 1]] - [how theme appears]
- [[Note 2]] - [how theme appears]
- [[Note 3]] - [how theme appears]

**Recommendation**: Create MOC "[[Theme Name]]" to organize these notes
```

**Cross-Domain Patterns**:
```markdown
## Pattern: [Pattern Name]

This pattern appears in:
- **Business** (Atlas Maps/Business): [[Note A]]
- **Psychology** (Planes/Psychology): [[Note B]]
- **Personal Development** (Atlas Maps/Personal): [[Note C]]

**Insight**: [What this pattern reveals]
**Action**: [Create synthesis note / Link together / Note in MOC]
```

## Connection Strength Criteria

**High Confidence** connections have:
- Shared specific terminology (3+ shared key terms)
- Same named entities (people, places, companies)
- Direct citations or references
- Complementary information on same topic
- Part of same project or theme

**Medium Confidence** connections have:
- Similar concepts, different terminology
- Analogous patterns
- Related but different aspects of topic
- Could inform each other
- Transferable insights

**Low Confidence** connections have:
- Tangential relationship
- Metaphorical similarity
- Weak thematic overlap
- Speculative connection
- Requires more research to confirm

## Bidirectional Linking

When adding links, create both directions:

**From original note**:
```markdown
## Related
- [[Related Note]] - [brief context of relationship]
```

**From related note**:
```markdown
## Related
- [[Original Note]] - [brief context of relationship]
```

## Special Connection Cases

### Bible Study Connections
Links Scripture passages to:
- Life application in diary
- Business ethics in projects
- Wisdom in decision-making notes
- Character studies to real people

### Project to Knowledge
Links projects to:
- Research that informed the work
- Concepts being applied
- People involved
- Lessons learned for future

### Clipping Integration
Links processed clippings to:
- Existing concepts they expand
- Projects they could inform
- People they mention
- Themes they develop

## Automated Actions

After approval, the skill can:
- Add links to specified notes
- Update MOCs with new entries
- Create new MOC if needed
- Add tags consistently
- Update metadata
- Create connection log

## Connection Quality Checks

Before finalizing connections:
- [ ] Link is bidirectional
- [ ] Context is clear (why they're connected)
- [ ] Doesn't create redundancy
- [ ] Adds value to both notes
- [ ] Respects note scope (doesn't stretch too far)
- [ ] Maintains vault organization principles

## Visualization Suggestions

Where beneficial, suggest:
- Create Canvas to show relationships
- Build concept map
- Generate graph view
- Timeline visualization for temporal connections

## When to Use

- After creating a substantial new note
- When a note feels isolated
- During weekly reviews
- When researching a topic
- Before creating a MOC
- To discover your vault's structure
- When feeling disconnected from knowledge base
- To find unexpected insights
- Cleaning up orphaned notes
- Building knowledge clusters

## Integration with Other Tools

Works with:
- **knowledge-synthesizer agent** - For MOC creation
- **vault-organizer agent** - For structural improvements
- **research-processor agent** - Linking processed research
- **project-manager agent** - Connecting projects to knowledge
- Graph view plugins
- Link analysis tools
- Tag management plugins

## Best Practices Applied

- Suggests, doesn't force connections
- Provides rationale for each connection
- Respects different confidence levels
- Creates bidirectional links
- Adds context to links (not just bare links)
- Discovers cross-domain insights
- Supports serendipitous discovery
- Maintains vault integrity
- Encourages organic knowledge growth
