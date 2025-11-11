# Orchestrated Research Mode - Quick Start Guide

## What is Orchestrated Research?

Orchestrated research is a strategic research mode that thinks deeply about your query, decomposes it into 2-3 focused angles, and launches parallel perplexity-researcher agents with custom prompts for each angle. It then synthesizes findings across perspectives with intelligent cross-validation.

**Think of it as:** A research director who carefully plans the investigation rather than just throwing agents at the problem.

## When to Use Orchestrated Mode

✅ **Use Orchestrated Research for:**
- Product recommendations requiring multiple perspectives (e.g., "best laptop for development")
- Strategic decisions needing different viewpoints (e.g., "should I migrate to serverless?")
- Complex topics benefiting from angle-based decomposition (e.g., "future of AI coding assistants")
- Research where quality > quantity matters

❌ **Don't Use Orchestrated Research for:**
- Simple factual queries ("what is Docker?") → use single perplexity call
- Time-sensitive quick answers → use Quick mode (3 agents)
- Broad exploration → use Standard (9 agents) or Extensive (24 agents) modes

## How to Invoke Orchestrated Research

### Option 1: Natural Language (Easiest)

Just say what you want naturally:
```
"Orchestrate research on the best mechanical keyboard for programming"
"Do strategic research on AI coding assistants"
"Research from multiple angles: serverless vs containerization"
"I need multi-perspective research on noise-canceling headphones"
```

### Option 2: Explicit Agent Invocation

Use the Task tool to invoke the research-orchestrator agent:
```
Task({
  subagent_type: "research-orchestrator",
  description: "Research best keyboards",
  prompt: "Research the best mechanical keyboard for programming under $300",
  model: "sonnet"
})
```

### Option 3: Via Research Skill

When using the research skill, specify orchestrated mode:
```
"Use orchestrated research mode to investigate..."
"Run the orchestrated workflow for..."
```

## What Happens During Orchestrated Research

1. **Deep Query Analysis (30 seconds)**
   - Analyzes what you're really asking
   - Identifies key perspectives needed
   - Plans research strategy

2. **Strategic Decomposition (30 seconds)**
   - Breaks query into 2-3 non-overlapping angles
   - Each angle explores different territory
   - Selects decomposition strategy (Comparative, Multi-Domain, Temporal, etc.)

3. **Intelligent Prompt Engineering (30 seconds)**
   - Crafts specific, optimized prompt for each angle
   - No generic prompts - each is customized
   - Optimized for Perplexity API's strengths

4. **Parallel Agent Launch (immediate)**
   - Launches 2-3 perplexity-researcher agents
   - All run in parallel (single message)
   - Each agent gets unique focused prompt

5. **Intelligent Synthesis (2-3 minutes)**
   - Cross-validates findings across agents
   - Identifies patterns and contradictions
   - Assigns confidence levels
   - Builds coherent narrative
   - Provides actionable recommendations

**Total Time: ~3-4 minutes**

## Example: What You Get

**Your Query:** "Research the best mechanical keyboard for programming under $300"

**What Orchestrator Does:**

1. **Analyzes:** Product recommendation, consumer tech domain, budget constraint, need multiple perspectives

2. **Decomposes into 3 angles:**
   - Angle 1 (Market): Current options under $300, specs, pricing, availability
   - Angle 2 (Ergonomics): Typing comfort, health for 8+ hour sessions
   - Angle 3 (Community): What developers actually use and recommend

3. **Launches 3 agents** with custom prompts for each angle

4. **Synthesizes findings:**
   ```markdown
   ## Executive Summary
   Based on multi-angle research, the Keychron K8 Pro ($189) emerges as the top
   recommendation for programming under $300...

   ## Multi-Angle Findings

   ### Market Analysis
   High Confidence: Keychron K8 Pro, Leopold FC980C, GMMK Pro all under $300
   Medium Confidence: Newer models from Nuphy and Epomaker...

   ### Ergonomic Assessment
   High Confidence: Tactile switches (Brown, Clear) best for typing
   Unique Insights: Key travel of 3.5-4mm reduces strain...

   ### Developer Community Experience
   High Confidence: Keychron most recommended on r/MechanicalKeyboards
   Contradictions: Some prefer Leopold despite higher price...

   ## Cross-Angle Synthesis
   Keychron K8 Pro appears in all three perspectives...

   ## Actionable Recommendations
   1. Primary: Keychron K8 Pro with Brown switches ($189)
   2. Alternative: Leopold FC980C if budget allows ($275)
   3. Next Steps: Try switches at local store before buying
   ```

## Configuration Options

The orchestrator is intelligent and adapts automatically, but you can guide it:

**Number of angles:**
- "Research from 2 angles..." → Uses 2 subagents
- "Research from 3 perspectives..." → Uses 3 subagents
- Default: 3 angles (optimal balance)

**Specific perspectives:**
- "Research technical and business perspectives..." → Uses Multi-Domain strategy
- "Compare option A vs option B..." → Uses Comparative strategy
- "Research current state and future trends..." → Uses Temporal strategy

**Agent type:**
- Default: perplexity-researcher (you have Perplexity API)
- Can specify: "use Claude researchers" or "use Gemini researchers"

## Advantages Over Other Modes

**vs Quick Mode (3 agents - 1 of each type):**
- Orchestrated: Custom prompts, strategic angles, focused depth
- Quick: Generic split, broad coverage, faster but less thoughtful

**vs Standard Mode (9 agents - 3 of each type):**
- Orchestrated: Fewer agents, deeper thinking, better synthesis
- Standard: More agents, broader coverage, comprehensive but generic

**vs Extensive Mode (24 agents - 8 of each type):**
- Orchestrated: Strategic focus, quality over quantity
- Extensive: Exhaustive coverage, creative angles, broader exploration

**When Orchestrated is best:**
- Strategic decisions
- Product recommendations
- Multi-perspective analysis needed
- Quality and depth > breadth

## Troubleshooting

**"Orchestrator seems to take a long time"**
- Analysis + decomposition + prompt engineering takes ~1-2 minutes (intentional thinking time)
- Total research: 3-4 minutes
- This is strategic research, not instant answers

**"I want faster results"**
- Use Quick mode (3 agents, ~2 minutes)
- Or just call perplexity-researcher directly

**"I need more comprehensive coverage"**
- Use Standard mode (9 agents) or Extensive mode (24 agents)
- Orchestrated prioritizes depth over breadth

**"How do I know which mode to use?"**
- Simple query → Quick
- Comprehensive research → Standard
- Exhaustive exploration → Extensive
- Strategic/multi-perspective → Orchestrated

## Technical Details

- **Agent Used:** research-orchestrator (coordinates subagents)
- **Subagents:** 2-3 perplexity-researcher instances
- **Timeout:** 3 minutes per subagent, 5 minutes hard timeout
- **Model:** Sonnet (for orchestrator and subagents)
- **Parallelism:** True parallel (single message, multiple Task calls)
- **Voice Notification:** Yes (when voice system configured)

## Files

- **Agent Definition:** `.claude/agents/research-orchestrator.md`
- **Workflow:** `.claude/skills/research/workflows/orchestrated.md`
- **Skill Integration:** `.claude/skills/research/SKILL.md` (Mode 4)
- **This Guide:** `.claude/skills/research/workflows/README-ORCHESTRATED.md`

---

**Ready to try it?**

Just say: "Orchestrate research on [your topic]" and watch the magic happen!
