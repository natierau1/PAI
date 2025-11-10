# Create LIST Workflow

**Purpose:** Create a new LIST with formal template structure in the Atlas Dots/LISTS folder.

**Triggers:** "create list", "new list", "make a list", "start a list"

---

## Overview

This workflow creates a properly formatted LIST file following the formal template structure with complete frontmatter, dataview queries, content sections, and Back Matter.

## Prerequisites

- User has provided a topic for the LIST
- LIST does not already exist with this name
- User has appropriate permissions in Atlas Dots/LISTS/

## Workflow Steps

### 1. Identify Topic and Validate

**Actions:**
- Extract the topic name from user request
- Normalize to proper capitalization (title case for multi-word topics)
- Confirm topic with user if ambiguous
- Check if LIST already exists

**Example:**
```
User: "Create a list for sci-fi books"
Topic: "Sci-Fi Books"
Filename: "LIST Sci-Fi Books.md"
```

**Validation:**
```bash
# Check if file exists
ls "/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/LIST [Topic].md"
```

If exists, ask user:
- "A list for [Topic] already exists. Would you like to:"
  - Add items to the existing list
  - Create a new list with a different name
  - View the existing list

### 2. Load Template

**Actions:**
- Read the formal template from `assets/list-template.md`
- This template includes all required frontmatter and structure

**Template location:**
`/Users/irautenbach/Documents/Obsidian/Personal/.claude/skills/obsidian-lists/assets/list-template.md`

### 3. Populate Template Fields

**Actions:**
Fill in template with topic-specific information:

**Frontmatter:**
- `tags: [type/list]` - Always include
- `created: [YYYY-MM-DD, HH:MM]` - Current timestamp
- `modified: YYYY-MM-DD` - Current date
- `category: "[[LIST [Topic]]]"` - Self-reference

**Content:**
- Title: `# [Topic]`
- Lead paragraph: Ask user for brief description or leave placeholder
- Resources section: Create initial structure based on topic type

**Example topic-specific structures:**

For media LISTS (Books, Movies, Music, TV):
```markdown
# Resources

## To Read/Watch/Listen
-

## Currently Reading/Watching/Listening
-

## Completed
-
```

For reference LISTS (Tools, Articles, Resources):
```markdown
# Resources

## Essential
-

## To Explore
-

## Archive
-
```

For tracking LISTS (Travel, Recipes, Ideas):
```markdown
# Resources

## Wishlist
-

## In Progress
-

## Done
-
```

### 4. Suggest MOC References

**Actions:**
- Analyze topic to suggest relevant MOCs
- Reference `assets/common-mocs.md` for common MOCs
- Ask user to confirm MOC selections

**Common mappings:**

Entertainment topics → Entertainment MOC, Leisure MOC, Movies MOC, Music MOC
Technology topics → Ai MOC, LLM MOC, Research MOC
Personal topics → Children MOC, relevant location MOCs
Learning topics → Research MOC, relevant domain MOCs

**Add to References section:**
```markdown
## References
<!-- Links to pages not referenced in the content. -->
- [[MOC Name]]
- [[Another MOC]]
```

### 5. Ask for Initial Items (Optional)

**Actions:**
- Ask user: "Would you like to add some initial items to this list?"
- If yes, collect items and add to appropriate sections
- If no, leave sections with placeholder dashes

**Format items appropriately:**
- Simple items: `- Item name`
- Items with links: `- [Item name](URL)`
- Items with descriptions: `- Item name - brief description`
- Wikilinks: `- [[Note Name]]`

### 6. Create File

**Actions:**
- Write populated template to file
- Use standardized naming: `LIST [Topic].md`
- Location: `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/`

**Create command:**
```
Write to: /Users/irautenbach/Documents/Obsidian/Personal/Atlas Dots/LISTS/LIST [Topic].md
```

### 7. Confirm Creation

**Actions:**
- Verify file was created successfully
- Provide confirmation message to user
- Offer next actions

**Confirmation message:**
```
Created LIST [Topic].md successfully!

Location: Atlas Dots/LISTS/LIST [Topic].md
Structure: Formal template with full frontmatter and Back Matter
MOCs linked: [list MOCs]
Initial items: [count] items added

Would you like to:
- Add more items
- View the created list
- Create another list
```

## Error Handling

### File Already Exists
**Message:** "A LIST for [Topic] already exists at Atlas Dots/LISTS/LIST [Topic].md"
**Actions:**
- Ask if user wants to view existing list
- Suggest add-items workflow instead
- Offer to create with different name

### Permission Denied
**Message:** "Unable to create file in Atlas Dots/LISTS/ directory"
**Actions:**
- Check directory permissions
- Verify path exists
- Suggest manual creation if needed

### Invalid Topic Name
**Message:** "Topic name contains invalid characters"
**Actions:**
- Suggest sanitized version
- Ask for alternative name
- Explain naming convention

## Completion Checklist

Before considering workflow complete, verify:
- [ ] File created in correct location
- [ ] Filename follows `LIST [Topic].md` convention
- [ ] All required frontmatter fields populated
- [ ] type/list tag present
- [ ] Created and modified dates set
- [ ] Template structure intact (headers, sections, Back Matter)
- [ ] Dataview query present
- [ ] MOC references added (if applicable)
- [ ] Initial items added (if requested)

## Example Usage

### Example 1: Simple LIST Creation
```
User: "Create a list for podcasts"

Workflow executes:
1. Topic: "Podcasts"
2. Filename: "LIST Podcasts.md"
3. Structure: Media-style (To Listen / Currently Listening / Completed)
4. MOCs suggested: Entertainment MOC, Leisure MOC
5. Initial items: None (user says no)
6. File created successfully

Output: "Created LIST Podcasts.md with Entertainment and Leisure MOC references!"
```

### Example 2: LIST with Initial Items
```
User: "Create a list for documentaries and add Planet Earth, Blue Planet, and Cosmos"

Workflow executes:
1. Topic: "Documentaries"
2. Filename: "LIST Documentaries.md"
3. Structure: Media-style sections
4. MOCs: Entertainment MOC, Movies MOC, Leisure MOC
5. Initial items added:
   ## To Watch
   - Planet Earth
   - Blue Planet
   - Cosmos
6. File created successfully

Output: "Created LIST Documentaries.md with 3 documentaries in the 'To Watch' section!"
```

### Example 3: Specialized Topic
```
User: "Make a list for AI research papers I want to read"

Workflow executes:
1. Topic: "AI Research Papers"
2. Filename: "LIST AI Research Papers.md"
3. Structure: Reference-style (Essential / To Explore / Archive)
4. MOCs: Ai MOC, LLM MOC, Research MOC
5. Initial items: User will add later
6. File created successfully

Output: "Created LIST AI Research Papers.md linked to Ai, LLM, and Research MOCs!"
```

## Related Workflows

- **add-items.md** - Add items to this newly created LIST
- **link-to-moc.md** - Add additional MOC references later
- **convert-to-list.md** - Alternative if starting from existing note

## Assets Used

- `assets/list-template.md` - Formal template structure
- `assets/common-mocs.md` - MOC reference guide

## Notes

- Always use uppercase "LIST" in filename (standardized)
- Created timestamp includes time, modified only includes date
- Dataview query helps discover orphaned connections
- Lead paragraph can be placeholder initially, refined later
- Visual and link fields optional, can remain placeholders
- Template version "1.18" matches existing note templates

---

**This workflow ensures consistent, properly formatted LISTS that integrate seamlessly with your GTD system.**
