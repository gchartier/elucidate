# Elucidate

Claude Code skills for crystallizing understanding through iterative questioning. Draws out what a user knows — or is trying to figure out — through phased inquiry, producing a concise document whose format emerges from the content itself.

## Skills

### `elucidate`

Socratic dialogue mode. Open-ended, emergent questioning that moves through four phases:

1. **Orient** — Understand the situation, gap, and intended use
2. **Frame** — Find the shape of the problem through candidate framings and assumption surfacing
3. **Investigate** — Build understanding through strategic questioning, contradiction surfacing, and anomaly seeking
4. **Synthesize** — Draft and verify the crystallized document

The user responds in natural conversation. Questions are open-ended, one at a time in early phases, scaling to 2-3 alongside a working model in later phases. Best for users who think generatively and are comfortable with open-ended prompts.

### `elucidate-guided`

Structured facilitation mode. Same four-phase process, but every user interaction goes through `AskUserQuestion` with curated option sets. The system narrates and synthesizes freely; the user responds through structured choices.

Best for users who find open-ended questions overwhelming or who benefit from scaffolding. The options themselves make the system's hypothesis space transparent — each option set is a claim about the shape of the problem.

Includes a full option design library (`OPTION-PATTERNS.md`) covering orienting, framing, discriminating, holistic check, verification, and meta patterns.

## How It Works

Both skills produce a **state file** (`elucidate-<topic-slug>.md`) that evolves from freeform notes into the final document. The file is always readable — early phases show working notes and open questions; late phases show clean prose.

Key mechanisms:
- **Mode detection** — Adapts between extraction (user knows the material, needs structure) and discovery (user is exploring, needs space)
- **Contradiction surfacing** — Makes conflicting beliefs explicit rather than smoothing them over
- **Cognitive escalation** — Progresses from fact to explanation to evaluation to creation
- **Meta-monitoring** — Detects loops, overload, frame fixation, rapport erosion, and diminishing returns

## Files

```
.claude/skills/
  elucidate/
    SKILL.md          # Core skill definition
    QUESTIONING.md    # Question type library (orienting, framing, discriminating, deepening, verification)
  elucidate-guided/
    SKILL.md          # Guided variant skill definition
    OPTION-PATTERNS.md # Option design library for AskUserQuestion
research.md           # Research synthesis on iterative questioning for agentic systems
```

## Research

`research.md` synthesizes findings from across active learning, Socratic method, motivational interviewing, clinical reasoning, information theory, and other fields into a convergence map of design principles for iterative questioning systems. The skills were designed from this research.
