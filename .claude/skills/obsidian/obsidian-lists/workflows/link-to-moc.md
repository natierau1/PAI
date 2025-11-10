# Link LIST to MOC Workflow

**Purpose:** Add proper MOC (Map of Content) references to a LIST in the Back Matter References section.

**Triggers:** "link to MOC", "add MOC reference", "connect to map", "link list to MOC"

---

## Overview

This workflow analyzes a LIST's topic and content to suggest relevant MOCs, then adds proper wikilink references to the Back Matter References section. MOCs provide broader context and help organize LISTS within the knowledge vault structure.

## Prerequisites

- LIST file exists
- User has specified which LIST to update
- MOC files exist in vault (typically in Atlas Maps/)

## Workflow Steps

### 1. Identify Target LIST

**Actions:**
- Extract LIST topic from user request
- Construct expected filename: `LIST [Topic].md`
- Locate file in LISTS directory

**Examples:**
```
User: "Link my books list to relevant MOCs"
Target: LIST Books.md

User: "Add MOC references to LIST Podcasts"
Target: LIST Podcasts.md

User: "Connect the AI resources list to MOCs"
Target: LIST AI Resources.md
```

**Search location:**
`/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/`

**If not found:**
- Search for variations
- Ask user for exact name
- Offer to create LIST first

### 2. Read Current LIST

**Actions:**
- Use Read tool to load LIST file
- Parse frontmatter and content
- Identify current References section
- Check for existing MOC links
- Analyze topic and content for context

**Extract information:**
```markdown
From frontmatter:
- tags: Identify subject area
- category: Understand topic

From content:
- # Title: Main topic
- ## Resources sections: Content type
- Existing items: Specific subjects
```

**Check existing References:**
```markdown
## References
<!-- Links to pages not referenced in the content. -->
- [[Entertainment MOC]]  ← Already linked
- [[Movies MOC]]          ← Already linked
```

### 3. Analyze Topic and Content

**Actions:**
- Determine LIST topic category
- Analyze content for subject indicators
- Review existing tags for context
- Classify into domain areas

**Classification examples:**

**Entertainment topics:**
- Books, Movies, TV Shows, Music, Podcasts, Documentaries
- → Entertainment, Movies, Music, Leisure MOCs

**Technology topics:**
- AI Tools, Programming Resources, Tech Articles, Research Papers
- → Ai, LLM, Research, Technology MOCs

**Personal topics:**
- Recipes, Travel, Gift Ideas, Children's Activities
- → Relevant personal/location MOCs

**Learning topics:**
- Courses, Tutorials, Papers to Read, Educational Videos
- → Research, Education MOCs + domain-specific

### 4. Suggest Relevant MOCs

**Actions:**
- Reference `assets/common-mocs.md` for available MOCs
- Match LIST topic to appropriate MOCs
- Prioritize by relevance
- Check which MOCs actually exist in vault

**Query vault for MOCs:**
```
Search pattern: "MOC.md" in Atlas Maps/
Common locations:
- /Atlas Maps/Personal/
- /Atlas Maps/
- Other organized directories
```

**Suggestion logic:**

**Primary MOC (most relevant):**
Direct topic match
- Books → Entertainment MOC
- AI Resources → Ai MOC
- Recipes → Food MOC (if exists)

**Secondary MOCs (related):**
Broader or related contexts
- Books → Leisure MOC, Reading MOC
- AI Resources → LLM MOC, Research MOC
- Recipes → Personal MOC, Health MOC

**Tertiary MOCs (contextual):**
Useful but less direct
- Books → Children MOC (if children's books)
- AI Resources → Technology MOC
- Recipes → Meal Planning MOC

### 5. Verify MOCs Exist

**Actions:**
- For each suggested MOC, verify file exists
- Use Glob or Read to check presence
- Remove suggestions for non-existent MOCs
- Note which suggested MOCs don't exist (offer to create)

**Verification:**
```bash
Check if exists:
[[Entertainment MOC]] → /Atlas Maps/Personal/Entertainment MOC.md ✓
[[Reading MOC]] → Not found ✗

Report to user:
"Found: Entertainment MOC, Leisure MOC
Not found: Reading MOC (would you like me to note this for creation?)"
```

### 6. Present Suggestions to User

**Actions:**
- Show list of suggested MOCs
- Indicate which already exist in LIST
- Mark new suggestions
- Allow user to select/deselect

**Presentation format:**
```
I analyzed LIST [Topic].md and suggest these MOC references:

Already linked:
✓ Entertainment MOC

Suggested additions:
□ Leisure MOC - For general leisure activities
□ Movies MOC - If list includes film content
□ Children MOC - If content is child-related

Which MOCs would you like to add? (Select or say "all")
```

**User can:**
- Accept all suggestions
- Select specific MOCs
- Add custom MOC not suggested
- Skip this step

### 7. Update References Section

**Actions:**
- Locate Back Matter → References section
- Add new MOC links
- Maintain formatting consistency
- Preserve existing references
- Avoid duplicates

**Edit operation:**
```markdown
OLD:
## References
<!-- Links to pages not referenced in the content. -->
- [[Entertainment MOC]]

NEW:
## References
<!-- Links to pages not referenced in the content. -->
- [[Entertainment MOC]]
- [[Leisure MOC]]
- [[Movies MOC]]
```

**Formatting rules:**
- Each MOC on separate line
- Use wikilink syntax: `[[MOC Name]]`
- Alphabetical order optional but nice
- Maintain existing comment
- Keep one blank line before MOC links

### 8. Update Modified Date

**Actions:**
- Update frontmatter `modified` field to current date
- Keep other frontmatter unchanged

**Edit frontmatter:**
```yaml
OLD:
modified: 2025-11-01

NEW:
modified: 2025-11-08
```

### 9. Confirm Changes

**Actions:**
- Verify edits successful
- Count MOCs added
- Report to user

**Confirmation message:**
```
Added [N] MOC reference(s) to LIST [Topic].md!

New references:
- [[Leisure MOC]]
- [[Movies MOC]]

Total MOCs now linked: [M]
Updated: Atlas Dots/LISTS/LIST [Topic].md
```

## Error Handling

### LIST Not Found
**Message:** "I couldn't find LIST [Topic].md. Would you like to create it?"
**Actions:**
- Offer create-list workflow
- Search for similar names
- Ask for exact filename

### References Section Not Found
**Message:** "This LIST doesn't have a References section in Back Matter. Add one?"
**Actions:**
- Offer to add complete Back Matter structure
- Or just add References section
- Show where it will be added

### MOC Already Linked
**Message:** "[[MOC Name]] is already referenced in this LIST."
**Actions:**
- Skip duplicate
- Note in confirmation
- Continue with other MOCs

### MOC Doesn't Exist
**Message:** "I couldn't find [[MOC Name]].md in your vault."
**Actions:**
- Verify MOC existence
- Ask if user wants to add anyway (future MOC)
- Offer to create MOC
- Skip this MOC

### Permission Denied
**Message:** "Unable to edit LIST [Topic].md - permission denied"
**Actions:**
- Check file permissions
- Verify file isn't locked
- Suggest manual edit

## Special Cases

### Adding Custom MOC

**User specifies MOC not in suggestions:**
```
User: "Also add the Philosophy MOC"
```

**Actions:**
- Accept custom MOC
- Verify it exists (or ask to add anyway)
- Add to References section
- Include in confirmation

### Bulk MOC Addition

**User wants same MOCs on multiple LISTS:**
```
User: "Add Entertainment MOC and Leisure MOC to all my media lists"
```

**Actions:**
- Identify all media LISTS (Books, Movies, Music, etc.)
- Loop through each LIST
- Add specified MOCs to each
- Provide summary of all updates

### Creating Missing MOCs

**User wants to create MOC that doesn't exist:**
```
User: "Link to Reading MOC and create it if it doesn't exist"
```

**Actions:**
- Check if MOC exists
- If not, offer to create basic MOC file
- Add link to LIST
- Confirm both creation and linking

## Completion Checklist

Before considering workflow complete, verify:
- [ ] Target LIST identified correctly
- [ ] Current References section read
- [ ] Topic and content analyzed
- [ ] Relevant MOCs suggested
- [ ] MOC existence verified
- [ ] User confirmed selections
- [ ] References section updated with new MOCs
- [ ] No duplicate MOCs added
- [ ] Formatting consistent
- [ ] Modified date updated
- [ ] File saved successfully
- [ ] User confirmation provided

## Example Usage

### Example 1: Simple MOC Addition
```
User: "Link my books list to relevant MOCs"

Workflow executes:
1. Target: LIST Books.md
2. Read file, check References
3. Analyze: Entertainment topic
4. Suggest: Entertainment MOC, Leisure MOC
5. Verify both exist
6. User: "Add both"
7. Update References section
8. Update modified date
9. Confirm: "Added 2 MOC references to LIST Books.md"
```

### Example 2: Multiple Suggestions with Selection
```
User: "Add MOC references to my AI tools list"

Workflow executes:
1. Target: LIST AI Tools.md
2. Current refs: None
3. Analyze: Technology/AI topic
4. Suggest:
   - Ai MOC (primary)
   - LLM MOC (secondary)
   - Research MOC (secondary)
   - Technology MOC (tertiary)
5. Verify: All exist except Technology MOC
6. Present to user with explanations
7. User: "Add Ai MOC and LLM MOC"
8. Update with 2 selected MOCs
9. Confirm: "Added Ai MOC and LLM MOC to LIST AI Tools.md"
```

### Example 3: Custom MOC Addition
```
User: "Link my podcasts list to Entertainment MOC and also add Audio MOC"

Workflow executes:
1. Target: LIST Podcasts.md
2. Read current state
3. User specified: Entertainment MOC, Audio MOC
4. Verify:
   - Entertainment MOC: Exists ✓
   - Audio MOC: Not found
5. Ask: "Audio MOC doesn't exist. Add reference anyway for future?"
6. User: "Yes"
7. Update References with both
8. Note in confirmation that Audio MOC doesn't exist yet
9. Confirm: "Added 2 MOC references (Note: Audio MOC not found in vault)"
```

### Example 4: Already Linked MOCs
```
User: "Add Entertainment MOC to my movies list"

Workflow executes:
1. Target: LIST Movie.md
2. Read References section
3. Found: Entertainment MOC already linked
4. Inform user: "Entertainment MOC is already referenced"
5. Suggest other MOCs: Leisure MOC, Movies MOC
6. User: "Add Movies MOC"
7. Update References
8. Confirm: "Added Movies MOC (Entertainment MOC was already linked)"
```

## MOC Reference Guide

**Common MOC mappings** (see `assets/common-mocs.md` for complete list):

**Entertainment LISTS:**
- Books, Movies, TV, Music, Podcasts
- → Entertainment MOC, Leisure MOC, specific media MOCs

**Technology LISTS:**
- AI, Programming, Tools, Articles
- → Ai MOC, LLM MOC, Research MOC, Technology MOC

**Personal LISTS:**
- Recipes, Travel, Gifts, Activities
- → Personal MOCs, location-specific MOCs

**Children-Related LISTS:**
- Children's books, shows, activities
- → Children MOC, Entertainment MOC

## Integration Notes

### With create-list Workflow
```
create-list asks for MOC suggestions →
Uses same analysis logic →
Pre-populates References section
```

### With convert-to-list Workflow
```
convert-to-list completes →
Suggests running link-to-moc →
Adds appropriate context references
```

### With Vault Graph
```
MOC references create connections →
LIST appears in MOC backlinks →
Graph visualization shows relationships →
Easier navigation and discovery
```

## Related Workflows

- **create-list.md** - Includes MOC suggestion during creation
- **add-items.md** - May trigger MOC review after major additions
- **convert-to-list.md** - Includes MOC linking as final step

## Assets Used

- `assets/common-mocs.md` - Reference guide of available MOCs and their typical use cases

## Notes

- MOCs are typically in `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Maps/`
- MOC references go in Back Matter → References section
- Wikilink format creates bidirectional links (LIST shows in MOC backlinks)
- MOCs provide broader context and improve discoverability
- Don't overlink - 2-4 MOCs per LIST usually sufficient
- Primary MOC should be most relevant to topic
- Can add MOC references even if MOC doesn't exist yet (future linking)
- Update modified date helps track when LIST context was refined
- Review MOC links periodically as vault structure evolves

---

**This workflow ensures LISTS are properly connected to broader knowledge maps for context and discoverability.**
