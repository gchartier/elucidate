# Option Design Library

Reference for designing `AskUserQuestion` option sets during elucidate-guided inquiry. Organized by purpose, not by phase — most patterns are useful across multiple phases. Each section includes the pattern structure, examples, and guidance on when to use it.

The core constraint: every user response goes through structured options. This means option design IS question design. A badly designed option set is worse than no question at all — it constrains without informing.

## Orienting Patterns

Structured self-assessment. Primary use in Phase 0, but useful whenever the inquiry shifts terrain.

**Purpose:** Establish the landscape through the user's self-categorization. Replace open-ended "what's going on?" with curated diagnostic options.

### Taxonomy Pattern
Present a typology of situations and let the user locate themselves within it.

```
Header: "Task" (or topic-relevant label)
Question: "What kind of [topic-relevant activity] is this?"
Options:
- Label: "[Type A]" / Description: "[What A implies about the inquiry]"
- Label: "[Type B]" / Description: "[What B implies]"
- Label: "[Type C]" / Description: "[What C implies]"
```

Example:
```
Header: "Task"
Question: "What kind of thinking do you need help with?"
Options:
- Label: "Articulating" / Desc: "I have a sense of something but can't get it into words"
- Label: "Organizing" / Desc: "I have pieces — notes, ideas, fragments — that need structure"
- Label: "Deciding" / Desc: "I'm choosing between options and can't see clearly"
- Label: "Understanding" / Desc: "Something confuses me and I want to make sense of it"
```

**When to use:** Opening questions. When you need to categorize the user's situation before you can generate more specific options. When the user hasn't given enough context for targeted questions.

**Design principle:** Categories should be mutually exclusive in their implications, even if the user's real situation crosses boundaries. The user will select the closest fit; the gap between their situation and the category is informative.

### Starting-Point Assessment
Gauge what material the user brings.

```
Header: "Starting pt"
Question: "Where are you starting from?"
Options ranging from least to most developed material.
```

**Design principle:** Order options from least to most structured starting material. This gives you a single axis — raw to refined — that directly maps to mode detection (discovery vs. extraction).

### Readiness Check
Assess whether the user is ready to move to the next phase.

```
Header: "Ready?"
Question: "I think we have enough to [next phase activity]. How does that feel?"
Options ranging from enthusiastic agreement to wanting more time.
```

**When to use:** At phase transitions. Gives the user explicit control over pacing.

## Framing Patterns

Competitive framing and assumption surfacing. Primary use in Phase 1, but useful whenever a frame starts failing.

**Purpose:** Find the shape of the problem by presenting competing interpretations and letting the user select or reject them.

### Competitive Frame Pattern
Present 2-3 distinct framings with markdown previews.

```
Header: "Framing"
Question: "Which of these best captures what you're working through?"
Options (each with markdown preview):
- Label: "[Frame A name]"
  Desc: "[One-sentence summary]"
  Preview: "[2-3 paragraph expansion showing what inquiry looks like under this frame]"
- Label: "[Frame B name]"
  Desc: "[One-sentence summary]"
  Preview: "[2-3 paragraph expansion]"
- Label: "[Frame C name]"
  Desc: "[One-sentence summary]"
  Preview: "[2-3 paragraph expansion]"
```

**Design principle:** At least one frame should be a provocative reframe — one the user probably hasn't considered. This is the productive-struggle element: it introduces an option that challenges their default self-description. If they select it, you've found something important. If they reject it, the rejection is clarifying.

**Design principle:** Frames should be genuinely different, not gradations. "It's a communication problem" vs. "It's a structural problem" vs. "It's a values problem" — each implies different questions, different evidence, different documents.

### Stasis Diagnosis Pattern
Identify the kind of question at the core.

```
Header: "Question type"
Question: "What kind of question is this at its core?"
Options:
- Label: "What's true?" / Desc: "A factual question — resolved by evidence"
- Label: "What does it mean?" / Desc: "A definitional question — resolved by agreeing on terms"
- Label: "Is it good?" / Desc: "An evaluative question — resolved by establishing criteria"
- Label: "What to do?" / Desc: "A procedural question — resolved by connecting goals to actions"
```

**When to use:** When the framing question doesn't resolve cleanly, or when the user's selections suggest they're operating at the wrong stasis level (e.g., debating definitions when they think they're debating facts).

### Assumption Audit Pattern
Surface and test assumptions via multiSelect.

```
Header: "Assumptions"
Question: "This framing rests on several assumptions. Which feel solid to you?"
multiSelect: true
Options:
- Label: "[Assumption 1]" / Desc: "[What it means if this is wrong]"
- Label: "[Assumption 2]" / Desc: "[What it means if this is wrong]"
- Label: "[Assumption 3]" / Desc: "[What it means if this is wrong]"
```

**Design principle:** What the user does NOT select identifies the productive targets for investigation. Unselected assumptions are where the inquiry should focus.

### Deeper Question Pattern
Test whether the surface question hides a deeper concern.

```
Header: "Deeper"
Question: "I wonder if the real question might be slightly different. Which resonates?"
Options:
- Label: "[Surface question as stated]" / Desc: "The question as you originally framed it"
- Label: "[Reconstructed deeper question]" / Desc: "[Why you think this might be the real concern]"
- Label: "[Alternative deeper question]" / Desc: "[Another possibility]"
```

**When to use:** When orientation signals suggest the stated question is a proxy. Present your reconstruction alongside the original and let the user judge.

## Discriminating Patterns

Questions where competing interpretations predict different answers. Primary use in Phase 3. This is the most natural pattern for `AskUserQuestion` — it's what structured options were made for.

**Purpose:** Separate hypotheses that look similar from a distance but differ on specifics. Each option represents a different interpretation, and the user's selection eliminates alternatives.

### Binary Discrimination Pattern
Force a choice between two interpretations.

```
Header: "[Topic]"
Question: "Is [concept] more like [A] or [B]?"
Options:
- Label: "[A]" / Desc: "[What A implies — specific prediction or consequence]"
- Label: "[B]" / Desc: "[What B implies — different prediction or consequence]"
```

**Design principle:** The ideal binary discrimination is one where you genuinely can't predict which the user will choose. If you can predict it, the question confirms rather than informs. Seek genuine uncertainty.

**Design principle:** Both options should be defensible. If one option is obviously wrong, the question is rhetorical, not discriminating.

### Relationship Pattern
Identify how two concepts connect.

```
Header: "Connection"
Question: "What's the relationship between [X] and [Y]?"
Options:
- Label: "X causes Y" / Desc: "[What this would mean for the understanding]"
- Label: "They're aspects of the same thing" / Desc: "[What this would mean]"
- Label: "They're in tension" / Desc: "[What this would mean]"
- Label: "They're independent" / Desc: "[What this would mean]"
```

**When to use:** When two concepts have both appeared in the inquiry but their relationship is unclear. The answer restructures the document's organization.

### Priority Pattern
Establish relative importance.

```
Header: "Priority"
Question: "If you had to choose, which matters more here?"
Options:
- Label: "[Factor A]" / Desc: "Prioritizing A means [consequence]"
- Label: "[Factor B]" / Desc: "Prioritizing B means [consequence]"
- Label: "They're equally important" / Desc: "The real insight is their interaction"
- Label: "Wrong question" / Desc: "The priority framing doesn't apply here"
```

**Design principle:** Include "wrong question" or equivalent as an option when the question structure itself might be incorrect. This lets the user reject the premise, not just the options.

### Edge Case Pattern
Test boundaries with a specific scenario.

```
Header: "Boundary"
Question: "Does this still hold in [edge case scenario]?"
Options:
- Label: "Yes, fully" / Desc: "The principle applies even here"
- Label: "Partially" / Desc: "It applies but needs qualification"
- Label: "No, it breaks down" / Desc: "This case is outside the boundary"
- Label: "This case doesn't apply" / Desc: "The scenario isn't relevant to what we're discussing"
```

**When to use:** After a principle or claim has been established. Edge cases reveal boundaries better than central cases. The boundary of a concept tells you more about what it means than the center does.

### Contradiction Pattern
Surface and resolve tensions between prior selections.

```
Header: "Tension"
Question: "Earlier you said [X]. Now you're saying [Y]. These seem to be in tension."
Options:
- Label: "X is more fundamental" / Desc: "Y is a special case or was overstated"
- Label: "Y is more fundamental" / Desc: "My thinking has evolved — X needs revision"
- Label: "Both, in different contexts" / Desc: "The key is knowing when each applies"
- Label: "The tension is the insight" / Desc: "Don't resolve it — the contradiction itself is what I'm trying to articulate"
```

**When to use:** When prior selections genuinely conflict. Don't smooth over contradictions — present them explicitly. The user's way of resolving the tension is often the deepest insight in the inquiry.

## Holistic Check Patterns

Model verification through multiSelect. Primary use in Phase 3, every 3-4 targeted questions.

**Purpose:** Present your current working model and let the user confirm, correct, or extend it. Catches accumulated drift, blind spots, and unstated assumptions.

### Model Verification Pattern

```
Header: "Check"
Question: "Here's what I think we've established. Which of these feel right?"
multiSelect: true
Options:
- Label: "[Established claim 1]" / Desc: "[Brief elaboration]"
- Label: "[Established claim 2]" / Desc: "[Brief elaboration]"
- Label: "[Established claim 3]" / Desc: "[Brief elaboration]"
- Label: "[Established claim 4]" / Desc: "[Brief elaboration]"
```

**Design principle:** Include at least one claim you're less confident about. If the user deselects it, your uncertainty was warranted. If they confirm it, you've learned something. What's NOT selected is as informative as what is — each deselection identifies something the user disagrees with or considers insufficiently established.

**When to use:** Every 3-4 targeted probes. Accompany with a prose summary of the current model — the multiSelect tests the model; the prose communicates it.

### Gap Detection Pattern

```
Header: "Missing?"
Question: "Is there something important we haven't touched yet?"
Options:
- Label: "Yes — [area A]" / Desc: "We haven't discussed [specific gap]"
- Label: "Yes — [area B]" / Desc: "We're missing [specific gap]"
- Label: "No — we've covered the key ground" / Desc: "Ready to move toward synthesis"
- Label: "I'm not sure" / Desc: "Something feels incomplete but I can't name it"
```

**Design principle:** Generate the gap options from your own analysis of what the inquiry hasn't covered. The last option — "something feels incomplete but I can't name it" — is a crucial design element. It gives voice to the user's inarticulate sense that something is missing, which is often the most important signal.

## Verification Patterns

Draft verification and robustness testing. Primary use in Phase 4.

**Purpose:** Test whether the understanding is genuine and durable through structured review of the draft document.

### Section Verification Pattern

```
Header: "Verify"
Question: "Does this section capture what you mean?"
Options (with markdown preview showing the draft section):
- Label: "Yes, exactly" / Desc: "This is right — move on"
- Label: "Direction is right" / Desc: "The idea is correct but emphasis or wording needs adjustment"
- Label: "Something is missing" / Desc: "The section is incomplete — an important element isn't here"
- Label: "Doesn't capture it" / Desc: "This needs fundamental rethinking, not just editing"
```

**Design principle:** Each non-confirming option implies a different follow-up action. "Direction is right" leads to refinement questions about emphasis. "Something is missing" leads to gap-identification questions. "Doesn't capture it" triggers a return to Phase 3 investigation for this section.

### Robustness Test Pattern

```
Header: "Stress test"
Question: "What's the strongest objection to this understanding?"
Options:
- Label: "[Objection A]" / Desc: "[What this objection challenges]"
- Label: "[Objection B]" / Desc: "[What this objection challenges]"
- Label: "[Objection C]" / Desc: "[What this objection challenges]"
```

**Design principle:** Generate objections from genuinely different angles — a practical objection, a theoretical objection, an objection from a different stakeholder's perspective. The user's selection of the strongest objection reveals what they consider most vulnerable in the understanding.

### Application Test Pattern

```
Header: "Application"
Question: "If you applied this understanding tomorrow, what would you do differently?"
Options:
- Label: "[Behavioral implication A]" / Desc: "[Specific action this implies]"
- Label: "[Behavioral implication B]" / Desc: "[Specific action this implies]"
- Label: "Nothing concrete yet" / Desc: "The understanding is real but hasn't translated to action"
- Label: "Something else" / Desc: "The most important application isn't listed"
```

**When to use:** After section verification, before closing. Tests whether the understanding is actionable or merely intellectual. If the user selects "nothing concrete yet," the understanding may need to be made more specific.

### Authenticity Check Pattern

```
Header: "Authentic?"
Question: "Does this feel true, or does it just feel tidy?"
Options:
- Label: "True" / Desc: "This captures something real, even if it's messy"
- Label: "Tidy" / Desc: "It's well-organized but something is being smoothed over"
- Label: "Both" / Desc: "The core is true but some parts are too neat"
- Label: "Neither" / Desc: "It doesn't feel right at all"
```

**When to use:** As a final check before closing. Neat frameworks can disguise shallow understanding. This question gives the user permission to say the document looks good but doesn't feel right.

## Meta Patterns

Process monitoring through structured questions. Used by the meta-monitor throughout.

### Process Check Pattern

```
Header: "Process"
Question: "How is this working for you right now?"
Options:
- Label: "Well — keep going" / Desc: "The pace and questions feel right"
- Label: "Too fast / too hard" / Desc: "I need simpler questions or more time to think"
- Label: "Show me the big picture" / Desc: "I've lost the thread — where are we?"
- Label: "Format is constraining" / Desc: "I need to explain something that doesn't fit options"
```

**When to use:** When you detect disengagement signals (rapid clicking, consistent first-option selection, very short "Other" responses). Also useful at natural breakpoints between phases.

**Design principle:** If the user selects "Format is constraining," temporarily invite a free-form "Other" response on the next question, then use that response to redesign your option space going forward.

### Recalibration Pattern

```
Header: "Recalibrate"
Question: "My options haven't been matching your thinking well. What's going on?"
Options:
- Label: "Right questions, narrow options" / Desc: "You're asking about the right things but the choices are too limited"
- Label: "Wrong questions" / Desc: "We should be exploring different territory entirely"
- Label: "Topic has shifted" / Desc: "My thinking has moved since we started — we need to reorient"
- Label: "Need free-form" / Desc: "I need to explain something that structured options can't capture"
```

**When to use:** When Other frequency exceeds roughly a third of recent questions. This is the meta-monitor's primary diagnostic tool.

## Selection Principles

How to choose among option design patterns at any moment in the inquiry.

**Maximize uncertainty reduction.** The best question is the one where you genuinely can't predict which option the user will select. If one option is obviously right, the question wastes a turn. Design option sets where each selection would lead you in a meaningfully different direction.

**Span the space, don't cluster.** Options should cover the range of plausible positions, not variations of the same position. "Strongly agree / agree / neutral" is a bad option set — it clusters around agreement. "Yes / No / It depends on context / Wrong question" spans the space.

**Include the uncomfortable option.** At least one option in each set should be something the user might not want to admit. "I haven't really thought this through," "I'm afraid this might be true," "My earlier answer was wrong." These create productive discomfort — the structured format makes it easier to select a difficult truth than to volunteer it in open conversation.

**Include the "reject the premise" option.** Especially in discriminating patterns, include an option that challenges whether the question itself is right. "This isn't the right way to think about it" or "The distinction doesn't apply here." This prevents forced choices between inadequate alternatives.

**Let descriptions carry nuance.** Labels should be short and decisive. Descriptions should explain implications, tradeoffs, and what the selection means for the inquiry. A user who reads only labels gets a quick choice; a user who reads descriptions gets a richer one.

**Don't design leading options.** If you want the user to select a particular option, you're not inquiring — you're persuading. Design options as if you genuinely don't know which is correct. If you DO know the answer, you're in the wrong phase — this should be narration, not a question.

**Track selection patterns, not just selections.** A user who always selects the first option may be disengaged. A user who alternates between options across questions is engaged. A user who consistently selects Other is telling you your model is wrong. A user who never selects Other may be too deferential to the structure. Patterns across questions are as informative as individual selections.
