---
description: Orchestrated multi-angle research using strategic query decomposition and 2-3 perplexity subagents
globs: ""
alwaysApply: false
---

# 🎯 ORCHESTRATED RESEARCH WORKFLOW

**YOU (Main Claude or research-orchestrator agent) are reading this because orchestrated research mode was triggered.**

This workflow provides step-by-step instructions for conducting strategic, multi-angle research using intelligent query decomposition and parallel perplexity-researcher agents.

## 🎯 WHEN TO USE ORCHESTRATED MODE

**Activate orchestrated research when:**
- User says "orchestrate research", "strategic research", "research from multiple angles"
- Query requires thoughtful angle selection rather than broad exploration
- Product recommendations needing multiple perspectives
- Strategic decisions requiring different viewpoints
- Complex topics where quality > quantity matters

**DON'T use orchestrated mode for:**
- Simple factual queries (use single perplexity call)
- Time-sensitive quick answers (use quick mode)
- Broad exploration (use standard/extensive modes)

## 🚀 WORKFLOW: 5 PHASES

### PHASE 1: DEEP QUERY ANALYSIS (2-3 minutes thinking time)

Before launching ANY subagents, analyze the query deeply:

**ANALYSIS CHECKLIST:**

1. **Core Question**
   - What is fundamentally being asked?
   - What's the actual decision or understanding needed?

2. **Domain Classification**
   - [ ] Technical/Engineering
   - [ ] Market/Business
   - [ ] Academic/Research
   - [ ] Product/Consumer
   - [ ] Strategic/Advisory
   - [ ] Other: ___________

3. **Key Perspectives**
   - What viewpoints will provide the most value?
   - What angles does the user NOT see but should?

4. **Success Criteria**
   - What would make this research "complete"?
   - What specific information is needed for a decision?

5. **Hidden Assumptions**
   - What has the user assumed?
   - What constraints exist? (budget, timeframe, geography, etc.)

**DOCUMENT YOUR ANALYSIS:**
Write out your thinking clearly before proceeding to Phase 2.

---

### PHASE 2: STRATEGIC DECOMPOSITION (Choose 2-3 Angles)

Based on your analysis, select a decomposition strategy and identify specific angles.

**AVAILABLE STRATEGIES:**

**A. Broad-Focused-Alternative** (Most Common)
```
Angle 1: Comprehensive overview and current state
Angle 2: Deep dive into most critical aspect
Angle 3: Alternative perspectives or contrarian views
```

**B. Temporal**
```
Angle 1: Current state and latest developments
Angle 2: Historical context and evolution
Angle 3: Future trends and predictions
```

**C. Comparative**
```
Angle 1: Option A analysis (strengths, weaknesses, use cases)
Angle 2: Option B analysis (strengths, weaknesses, use cases)
Angle 3: Comparative assessment and recommendations
```

**D. Multi-Domain**
```
Angle 1: Technical/Engineering perspective
Angle 2: Business/Market perspective
Angle 3: User Experience/Practical perspective
```

**E. Problem-Solution-Validation**
```
Angle 1: Problem space analysis (what's the real challenge?)
Angle 2: Solution landscape (what options exist?)
Angle 3: Validation and evidence (what actually works?)
```

**DECOMPOSITION RULES:**
- ✅ NO OVERLAP: Each angle explores different territory
- ✅ COMPLEMENTARY: Angles fit together like puzzle pieces
- ✅ SPECIFIC: Each angle has concrete focus
- ✅ BALANCED: Equal scope across all angles

**DOCUMENT YOUR DECOMPOSITION:**
```
Selected Strategy: [A/B/C/D/E]

Angle 1: [Name]
Focus: [Specific research focus]
Why: [Why this angle matters]

Angle 2: [Name]
Focus: [Specific research focus]
Why: [Why this angle matters]

Angle 3: [Name]
Focus: [Specific research focus]
Why: [Why this angle matters]
```

---

### PHASE 3: INTELLIGENT PROMPT ENGINEERING

For each angle, craft a highly specific Perplexity-optimized prompt.

**PROMPT TEMPLATE:**

```
"[Specific focus area] - [key information needed].
Focus on [particular aspects, constraints, or priorities].
Include [specific types of information required]."
```

**GOOD PROMPT CHARACTERISTICS:**
- ✅ Clear scope definition
- ✅ Specific information requests
- ✅ Relevant constraints (2025, budget, geography, etc.)
- ✅ Output expectations
- ✅ Optimized for web search (Perplexity's strength)

**EXAMPLES:**

✅ **GOOD:**
"Latest mechanical keyboards 2025 for developers - focus on build quality, typing feel, and durability. Include specific model recommendations with pricing and where to buy."

✅ **GOOD:**
"Developer community discussions about mechanical keyboards - what do professional programmers on Reddit, HackerNews, and GitHub actually use? Focus on real usage experiences over 6+ months, not marketing claims."

✅ **GOOD:**
"Ergonomic analysis of mechanical keyboards for 8+ hour coding sessions - typing strain, wrist positioning, actuation force recommendations. Focus on health research and medical advice for heavy computer users."

❌ **BAD:**
"Research mechanical keyboards" (too vague)

❌ **BAD:**
"Find information about keyboards for programming" (no clear angle)

❌ **BAD:**
"What are the best keyboards?" (not specific enough)

**DOCUMENT YOUR PROMPTS:**
```
Prompt 1 (for Angle 1):
"[Your specific prompt here]"

Prompt 2 (for Angle 2):
"[Your specific prompt here]"

Prompt 3 (for Angle 3):
"[Your specific prompt here]"
```

---

### PHASE 4: PARALLEL AGENT LAUNCH

Launch 2-3 perplexity-researcher agents in parallel.

**CRITICAL: Use a SINGLE message with 2-3 Task tool calls**

This ensures true parallel execution for maximum speed.

**LAUNCH TEMPLATE:**

```typescript
// Launch all agents in ONE message (parallel execution)

Task({
  subagent_type: "perplexity-researcher",
  description: "[Angle 1 short name]",
  prompt: `Research the following using Perplexity API and return comprehensive findings:

[Angle 1 prompt from Phase 3]

Return:
- Key findings with sources
- Specific recommendations or data points
- Confidence level (High/Medium/Low)
- Any limitations or gaps

You have 2-3 minutes to complete this research.`,
  model: "sonnet"
})

Task({
  subagent_type: "perplexity-researcher",
  description: "[Angle 2 short name]",
  prompt: `Research the following using Perplexity API and return comprehensive findings:

[Angle 2 prompt from Phase 3]

Return:
- Key findings with sources
- Specific recommendations or data points
- Confidence level (High/Medium/Low)
- Any limitations or gaps

You have 2-3 minutes to complete this research.`,
  model: "sonnet"
})

Task({
  subagent_type: "perplexity-researcher",
  description: "[Angle 3 short name]",
  prompt: `Research the following using Perplexity API and return comprehensive findings:

[Angle 3 prompt from Phase 3]

Return:
- Key findings with sources
- Specific recommendations or data points
- Confidence level (High/Medium/Low)
- Any limitations or gaps

You have 2-3 minutes to complete this research.`,
  model: "sonnet"
})
```

**TIMING:**
- Expected completion: 2-3 minutes per agent
- Hard timeout: 5 minutes total
- If an agent hasn't returned after 5 minutes, proceed with available results

---

### PHASE 5: INTELLIGENT SYNTHESIS

When agents return, synthesize findings using this framework:

**SYNTHESIS STEPS:**

**Step 1: Pattern Recognition**
- What findings appear across multiple agents? → HIGH CONFIDENCE
- What unique insights did each angle provide? → MEDIUM CONFIDENCE
- What surprising discoveries emerged? → HIGHLIGHT

**Step 2: Cross-Validation**
- Where do findings corroborate each other?
- Where do findings conflict?
- How reliable is each source?

**Step 3: Confidence Scoring**
- **HIGH**: Multiple agents found same information from different sources
- **MEDIUM**: Single agent, multiple credible sources
- **LOW**: Single agent, single/weak source or uncertainty expressed

**Step 4: Conflict Resolution**
- Explicitly note contradictions
- Provide context for disagreements
- Explain possible reasons for conflicts
- Recommend follow-up if needed

**Step 5: Narrative Construction**
- Build coherent story from multiple perspectives
- Show how angles interconnect and inform each other
- Address the original question directly and clearly
- Provide actionable recommendations

**SYNTHESIS OUTPUT STRUCTURE:**

```markdown
## Executive Summary
[2-3 paragraph direct answer to the user's core question. Be specific and actionable.]

## Multi-Angle Findings

### [Angle 1 Name] - [Brief description]

**High Confidence Findings:**
- [Finding] (Sources: Agent 1, Agent 2)
- [Finding] (Corroborated by multiple sources)

**Medium Confidence Findings:**
- [Finding] (Source: Single credible source)

**Unique Insights:**
- [Novel information discovered from this angle]

### [Angle 2 Name] - [Brief description]

**High Confidence Findings:**
- [Finding] (Sources: Agent 2, Agent 3)

**Medium Confidence Findings:**
- [Finding] (Source: Single credible source)

**Unique Insights:**
- [Novel information discovered from this angle]

### [Angle 3 Name] - [Brief description]

[Same structure as above]

## Cross-Angle Synthesis

**Common Themes:**
- [Pattern found across all perspectives]
- [Consensus view from multiple angles]

**Interconnections:**
- How [Angle 1] findings relate to [Angle 2]
- How [Angle 2] complements [Angle 3]
- Unexpected connections discovered

**Surprising Discoveries:**
- [Findings that challenge assumptions]
- [Unexpected patterns or insights]

## Contradictions & Uncertainties

**Where Sources Disagree:**
- [Specific conflict between agents/sources]
- Possible reasons: [Why this conflict might exist]

**Unexplained Gaps:**
- [Areas where research was incomplete]
- [Questions that remain unanswered]

**Recommended Follow-Up:**
- [Specific additional research needed]
- [Angles not yet explored]

## Actionable Recommendations

Based on synthesized findings:

1. **Primary Recommendation:** [Clear, specific action based on research]
   - Rationale: [Why this is recommended]
   - Confidence: [High/Medium/Low]

2. **Alternative Options:** [If applicable]
   - [Option with trade-offs]

3. **Next Steps:** [What user should do with this information]

## Research Metadata

- **Agents Used:** 2-3 perplexity-researcher agents
- **Total Queries:** [count]
- **Decomposition Strategy:** [A/B/C/D/E - which one used]
- **Angles Explored:** [List 2-3 angles]
- **Sources Consulted:** [estimate from agent reports]
- **Overall Confidence Level:** [High/Medium/Low] ([percentage]%)
- **Research Duration:** [time taken]
- **Coverage Assessment:** [Comprehensive/Focused/Partial]
```

---

## 🎯 MANDATORY OUTPUT FORMAT

After completing orchestrated research, return results using this format:

📅 [current date from date command]
**📋 SUMMARY:** Brief overview of research query and orchestration approach used
**🔍 ANALYSIS:** Query decomposition strategy, angles selected, why these angles were chosen
**⚡ ACTIONS:** Subagents launched (how many, which prompts), research coordination steps
**✅ RESULTS:** [PASTE FULL SYNTHESIS FROM PHASE 5 HERE]
**📊 STATUS:** Research completeness, confidence levels, source validation status
**➡️ NEXT:** Recommended follow-up research, additional angles to explore, or actions to take
**🎯 COMPLETED:** Orchestrated multi-angle research on [topic]
**🗣️ CUSTOM COMPLETED:** [Voice-optimized under 8 words]

---

## 📊 QUALITY CHECKLIST

Before returning results, verify:

- [ ] Deep query analysis completed (Phase 1)
- [ ] Strategy selected and documented (Phase 2)
- [ ] 2-3 non-overlapping angles identified
- [ ] Specific prompts crafted for each angle (Phase 3)
- [ ] All agents launched in parallel (single message)
- [ ] All agent results collected (or timeout reached)
- [ ] Cross-validation performed
- [ ] Confidence levels assigned
- [ ] Contradictions addressed
- [ ] Synthesis narrative constructed
- [ ] Actionable recommendations provided
- [ ] Mandatory output format used

---

## 💡 EXAMPLE EXECUTION

**User Query:** "Research the best mechanical keyboard for programming under $300"

**Phase 1: Analysis**
```
Core Question: Product recommendation for specific use case with budget constraint
Decision Context: User wants to buy keyboard for professional coding
Domain: Consumer tech + Professional tools
Key Perspectives: Market/reviews, Ergonomics, Community experience
Budget Constraint: Under $300
Strategy: Multi-Domain (3 angles)
```

**Phase 2: Decomposition**
```
Selected Strategy: D (Multi-Domain)

Angle 1: Market Analysis
Focus: Current market leaders under $300, specs, availability
Why: Need to know what options exist in budget range

Angle 2: Ergonomics & Health
Focus: Typing comfort, strain prevention for 8+ hour sessions
Why: Professional use requires long-term comfort

Angle 3: Developer Community
Focus: What programmers actually use and recommend
Why: Real-world experience trumps marketing
```

**Phase 3: Prompts**
```
Prompt 1 (Market):
"Best mechanical keyboards under $300 in 2025 for programming - comprehensive reviews, specs, build quality. Include specific models with current pricing and where to buy. Focus on value for money in sub-$300 range."

Prompt 2 (Ergonomics):
"Mechanical keyboard ergonomics for programmers - typing feel, actuation force, key travel, wrist strain prevention for 8+ hour coding sessions. Focus on health research and comfort for keyboards under $300."

Prompt 3 (Community):
"Developer community recommendations for mechanical keyboards under $300 - what do programmers on Reddit r/MechanicalKeyboards, r/programming, and HackerNews actually recommend? Real usage experiences from developers."
```

**Phase 4: Launch**
[Launch 3 perplexity-researcher agents with above prompts in single message]

**Phase 5: Synthesis**
[Wait for results, apply synthesis framework, construct final report]

---

## 🔄 INTEGRATION WITH RESEARCH SKILL

This workflow is Mode 4 in the research skill:

- **Mode 1 - Quick (3 agents):** Fast broad coverage using different agent types
- **Mode 2 - Standard (9 agents):** Comprehensive coverage with multiple agent types
- **Mode 3 - Extensive (24 agents):** Exhaustive research with creative decomposition
- **Mode 4 - Orchestrated (2-3 agents):** Strategic angles with thoughtful synthesis ← THIS WORKFLOW

**When to use Orchestrated vs others:**
- Use Orchestrated when: Query needs strategic thinking, custom angles, focused depth
- Use Quick when: Need fast answer, straightforward query
- Use Standard when: Comprehensive coverage needed, broad exploration
- Use Extensive when: Exhaustive research required, creative angles beneficial

---

**Remember: Orchestrated research is about STRATEGIC THINKING + FOCUSED EXECUTION = HIGH-QUALITY INSIGHTS**
