# Common MOCs Reference Guide

**Purpose:** Reference guide for linking LISTS to relevant Maps of Content (MOCs) organized by topic category.

**Location:** MOC files are typically located in `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Maps/`

---

## Entertainment & Leisure

### Entertainment MOC
**Use for:** Books, Movies, TV Shows, Music, Podcasts, Documentaries, Games
**Description:** General entertainment content of all types
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST Books.md
- LIST Movies.md
- LIST Music.md
- LIST Podcasts.md
- LIST Documentaries.md
- LIST TV Shows.md

### Movies MOC
**Use for:** Films, Documentaries, Cinema-related content
**Description:** Specific to movie and film content
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST Movie.md
- LIST Documentaries.md
- LIST TV Shows.md (if includes films)

### Music MOC
**Use for:** Songs, Albums, Artists, Playlists, Music theory
**Description:** All music-related content
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST Music.md
- LIST Concerts.md
- LIST Artists.md
- LIST Albums.md

### Leisure MOC
**Use for:** Hobbies, Recreation, Entertainment, Relaxation activities
**Description:** Broader leisure and recreational activities
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST Books.md
- LIST Music.md
- LIST Movies.md
- LIST Hobbies.md
- LIST Travel.md
- LIST Recipes.md

---

## Technology & Research

### Ai MOC
**Use for:** Artificial Intelligence, Machine Learning, AI tools and resources
**Description:** AI and machine learning focused content
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST Ai Tools.md
- LIST AI Research Papers.md
- LIST Ai Daily.md
- LIST Machine Learning Resources.md

### LLM MOC
**Use for:** Large Language Models, ChatGPT, Claude, GPT-related content
**Description:** Specific to LLMs and generative AI
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST AI Tools.md
- LIST LLM Papers.md
- LIST Prompts.md
- LIST Ai Daily.md

### Research MOC
**Use for:** Research papers, Academic content, Studies, Investigations
**Description:** Research and academic resources across domains
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST AI Research Papers.md
- LIST Papers to Read.md
- LIST Research Resources.md
- LIST Academic Articles.md

### Technology MOC
**Use for:** General tech tools, Software, Hardware, Tech news
**Description:** Broad technology topics beyond AI
**Verified:** Check vault (may not exist)

**Typical LISTS:**
- LIST Tech Tools.md
- LIST Programming Resources.md
- LIST Tech Articles.md
- LIST Software.md

---

## Personal & Family

### Children MOC
**Use for:** Children's content, Kids activities, Parenting resources
**Description:** Content related to children and family
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- LIST TV Children.md
- LIST Children's Books.md
- LIST Kids Activities.md
- LIST Educational Content.md

### Personal MOC
**Use for:** Personal development, Life management, Self-improvement
**Description:** Personal growth and life organization
**Verified:** Check vault

**Typical LISTS:**
- LIST Books.md (personal development)
- LIST Courses.md
- LIST Habits.md
- LIST Goals.md

---

## Locations

### Liverpool MOC
**Use for:** Liverpool-specific content, Local activities, Places
**Description:** Content specific to Liverpool
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- List Travel.md
- LIST Restaurants Liverpool.md
- LIST Places to Visit.md

### Ireland MOC
**Use for:** Ireland-related content, Irish culture, Travel in Ireland
**Description:** Content specific to Ireland
**Verified:** ✓ Exists in vault

**Typical LISTS:**
- List Travel.md
- LIST Ireland Destinations.md
- LIST Irish History.md

---

## Common MOC Patterns by LIST Type

### Media Consumption LISTS
**Examples:** Books, Movies, TV Shows, Music, Podcasts, Documentaries

**Primary MOCs:**
- Entertainment MOC (always)
- Specific media MOC (Movies MOC, Music MOC)

**Secondary MOCs:**
- Leisure MOC
- Children MOC (if children's content)

**Example:**
```markdown
LIST Books.md should link to:
- Entertainment MOC
- Leisure MOC
```

### Technology LISTS
**Examples:** AI Tools, Programming Resources, Tech Articles, Research Papers

**Primary MOCs:**
- Domain-specific (Ai MOC, LLM MOC, Technology MOC)
- Research MOC (for papers/articles)

**Secondary MOCs:**
- Related domain MOCs

**Example:**
```markdown
LIST AI Research Papers.md should link to:
- Ai MOC
- LLM MOC
- Research MOC
```

### Personal/Lifestyle LISTS
**Examples:** Recipes, Travel, Gift Ideas, Activities, Hobbies

**Primary MOCs:**
- Personal MOC
- Location MOCs (if relevant)
- Leisure MOC

**Secondary MOCs:**
- Topic-specific MOCs

**Example:**
```markdown
LIST Recipes.md should link to:
- Personal MOC
- Leisure MOC
```

### Learning LISTS
**Examples:** Courses, Tutorials, Papers to Read, Educational Videos

**Primary MOCs:**
- Research MOC
- Domain-specific MOC (Ai MOC for AI courses, etc.)

**Secondary MOCs:**
- Education MOC (if exists)

**Example:**
```markdown
LIST Courses.md should link to:
- Research MOC
- [Domain] MOC (based on subject)
```

---

## MOC Selection Guidelines

### How Many MOCs to Link?

**Ideal:** 2-3 MOCs per LIST
- One primary (most relevant)
- One or two secondary (related context)

**Minimum:** 1 MOC
- At least link to the primary relevant MOC

**Maximum:** 4-5 MOCs
- Avoid over-linking - reduces signal

### Determining Relevance

**Primary MOC (always include):**
- Direct topic match
- Most specific applicable MOC
- Where you'd expect to find this LIST

**Secondary MOC (usually include):**
- Broader context
- Related domain
- Complementary perspective

**Tertiary MOC (sometimes include):**
- Tangentially related
- Provides additional context
- Useful but not essential

### Example Decision Tree

```
LIST Topic: "Sci-Fi Books"
    ↓
Primary category: Books → Entertainment MOC ✓
    ↓
Specific genre: Sci-Fi → Science Fiction MOC (if exists) ✓
    ↓
General context: Reading for leisure → Leisure MOC ✓
    ↓
Result: Link to Entertainment MOC, Science Fiction MOC (if exists), Leisure MOC
```

---

## Verification Process

Before suggesting a MOC, verify it exists:

1. **Check primary location:**
   `/Users/irautenbach/Documents/Obsidian/Personal/Atlas Maps/`

2. **Check specific subdirectories:**
   - `Atlas Maps/Personal/`
   - `Atlas Maps/Work/`
   - `Atlas Maps/` (root)

3. **Search pattern:**
   Look for files ending in "MOC.md"

4. **If not found:**
   - Note MOC doesn't exist
   - Ask user if they want to create it
   - Or add reference for future linking

---

## Creating New MOCs

If a relevant MOC doesn't exist, consider creating:

**When to create:**
- Topic has multiple LISTS
- Recurring theme across notes
- Valuable organizational node
- User requests it

**When not to create:**
- Single LIST only
- Temporary/experimental topic
- Better suited as tag
- Redundant with existing MOC

---

## MOC Naming Conventions

**Standard format:** `[Topic] MOC.md`

**Examples:**
- Entertainment MOC.md
- Ai MOC.md
- Movies MOC.md
- Research MOC.md

**Not:** "MOC Entertainment" or "EntertainmentMOC" or "entertainment-moc"

---

## Integration with Workflows

### During LIST Creation (create-list workflow)
- Analyze topic
- Suggest 2-3 relevant MOCs
- Add to References section from start

### During LIST Conversion (convert-to-list workflow)
- Extract any existing MOC references
- Suggest additional relevant MOCs
- Ensure proper placement in References

### Dedicated Linking (link-to-moc workflow)
- Analyze existing LIST
- Suggest missing MOCs
- Update References section
- Avoid duplicates

---

## Notes

- MOC references go in Back Matter → References section
- Use wikilink format: `[[MOC Name]]`
- MOCs create bidirectional links (LIST appears in MOC backlinks)
- Review MOC links periodically as vault structure evolves
- MOCs improve discoverability in graph view
- Not all MOCs may exist in your vault - verify first
- Can add MOC reference even if file doesn't exist yet (future linking)
- MOCs are maps that provide context, not categories
- A LIST can (and should) link to multiple MOCs for different contexts

---

**This reference guide helps ensure LISTS are properly connected to the broader knowledge structure through appropriate MOC linkages.**
