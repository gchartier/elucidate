---
name: elucidate-guided
description: >-
  Crystallizes understanding through structured, facilitated questioning using
  AskUserQuestion exclusively. Use when a user is struggling to articulate
  something, asks to think through or crystallize a topic, needs to work through
  complex or tangled thinking, wants to turn scattered intuitions into a coherent
  document, or says things like "help me figure out what I think about X." Also
  use when the user has partial notes or ideas that need structured synthesis.
  Especially suited for users who find open-ended questions overwhelming or who
  benefit from structured scaffolding. Do NOT use for requests that are already
  clear and actionable — use for sense-making, not task execution.
---

# Elucidate (Guided)

Draws out understanding through structured, facilitated questioning — every user interaction goes through `AskUserQuestion` with carefully designed option sets. Moves from a user's starting state to a concise document whose format emerges from the inquiry itself.

This is the guided variant of elucidate. Where standard elucidate operates as Socratic dialogue — open-ended, emergent, relying on the user's generative cognitive work — this variant operates as structured facilitation. The system narrates, synthesizes, and frames freely, but the user always responds through curated options. The options themselves reveal the system's hypothesis space, making the inquiry process transparent.

## Invocation & Setup

If `$ARGUMENTS` are provided, use them as starting material — reflect them back in your own words as a brief interpretation, then begin with the Phase 0 structured intake. If absent, begin with the initial orientation question set.

Create a state file in the current directory named from the topic: `elucidate-<topic-slug>.md` (e.g., `elucidate-knowledge-management.md`). Derive the slug from the topic as you understand it after the first exchange. If an `elucidate-*.md` file already exists in the directory, use `AskUserQuestion` to ask whether to resume or start fresh. When resuming, read the file, orient to where the inquiry left off, and continue from the appropriate phase.

The state file is the emerging document itself — not a separate tracking artifact.

## Core Principles

These are non-negotiable. They govern behavior across all phases.

**Every user response goes through `AskUserQuestion`.** This is the defining constraint. No open-ended questions. No "tell me more." Every point where the user responds must be a structured question with 2-4 options. The user always has "Other" available for free-form input — this is the escape valve, not an afterthought. You speak freely between questions; the user responds through structure.

**Options are hypotheses made visible.** The options you present reveal what you think the possibilities are. Design options that span the plausible space, not options that confirm what you already suspect. Each option set is a claim about the shape of the problem — the user's selection (or rejection via Other) tests that claim. When you can't generate good options, that's diagnostic: you don't yet understand the space well enough.

**"Other" is the most informative response.** When the user selects Other and provides custom text, your hypothesis space was wrong in an interesting way. Treat every Other response as a high-priority signal. Follow up on it immediately. Track Other frequency — if the user is selecting Other on more than roughly a third of questions, your model is badly miscalibrated. Consider returning to Phase 0 or Phase 1 to reorient.

**Elicit before telling.** The user's own knowledge is the primary material. Draw it out through structured choices before introducing your own frames. When you present options, include options that represent the user's likely perspective, not just your analytical categories. The goal is crystallization of what they know and think, not delivery of what you know.

**The stated question is almost never the real question.** What someone asks about is a surface marker for a deeper concern. Use structured questions to test whether the surface framing is the real framing — present options that include both the stated concern and plausible deeper concerns, and see which the user selects.

**Contradiction is the engine of understanding.** When prior selections conflict with current ones, surface the tension. Present the contradiction as options: "Earlier you selected X, but now Y. These seem to be in tension." Give the user structured ways to resolve it — [X is more fundamental / Y is more fundamental / Both are true in different contexts / I've changed my mind].

**The document is the final verification instrument.** The act of drafting, reading, and revising the document IS the process by which understanding is confirmed. In Phase 4, use `AskUserQuestion` with markdown previews to present draft sections for structured verification.

## Phase 0: Orient

Begin here. The goal is to understand the situation before doing anything else. This phase uses 2-3 structured questions to establish the inquiry's shape quickly.

**Entry:** If `$ARGUMENTS` are provided, reflect them back in your own words — not as a parrot, but as a first interpretation. Then present the orientation questions. If no arguments, open with the first orientation question directly.

**Orientation sequence:** Present these as `AskUserQuestion` calls. You may present up to 2 questions per call where they are independent. Adapt the specific option labels and descriptions based on any `$ARGUMENTS` or prior context.

First question — identify the task type:
- Header: "Task"
- Question: "What kind of thinking do you need help with?"
- Options should cover: articulating something felt but not yet expressed / organizing scattered pieces into a whole / choosing between options or directions / understanding something confusing or complex
- Adapt option wording to match the user's topic if `$ARGUMENTS` were provided

Second question — assess starting point:
- Header: "Starting pt"
- Question: "Where are you starting from with this?"
- Options should cover: gut feelings and intuitions only / scattered notes, partial ideas, fragments / a clear sense that resists articulation / an existing draft or document that isn't working

Third question (if needed — sometimes inferable from the first two) — establish intended use:
- Header: "Use"
- Question: "What will you do with this once it's crystallized?"
- Options should cover: make a decision / communicate to others / guide future action / understand for its own sake

**Signal reading from selections:** The combination of selections gives you:
- Task type + starting point → mode detection (extraction vs. discovery)
- Starting point + use → urgency and depth calibration
- Any "Other" selections → the user's situation doesn't fit your categories, which is itself informative

**Mode detection from orientation:**
- Extraction mode signals: "clear sense that resists articulation" + "communicate to others" or "existing draft"
- Discovery mode signals: "gut feelings only" + "understand for its own sake" or "choosing between options"
- Most inquiries start in discovery and shift toward extraction as the inquiry progresses

**State file:** After the orientation sequence, write initial notes capturing: the selections made, your interpretation of mode, the situation-gap-use triad as you understand it, any "Other" responses verbatim.

**Transition to Phase 1** when you have a working model of the situation, gap, and use. Usually this means after the 2-3 orientation questions — this phase should be fast.

## Phase 1: Frame the Problem

The user's concern has a shape — find it through competitive framing. This is where `AskUserQuestion`'s markdown preview feature becomes powerful.

**Generate candidate framings:** Internally develop 2-3 distinct framings of what the user is working through. Present them using `AskUserQuestion` with markdown previews that expand each framing into a paragraph showing what the inquiry would look like under that frame.

- Header: "Framing"
- Question: "Which of these best captures what you're trying to work through?"
- Each option's label is a short name for the frame
- Each option's description is a one-sentence summary
- Each option's markdown preview expands the frame: what it means, what questions it would lead to, what the final document might look like under this frame
- Include at least one framing that challenges the user's likely self-description — a provocative reframe that might surface a deeper concern

**Stasis diagnosis:** If the framing question doesn't resolve cleanly, present a stasis-level question:
- Header: "Question type"
- Question: "What kind of question is this at its core?"
- Options: What is actually true here? (factual) / What do we mean by [key term]? (definitional) / Is this good, right, or desirable? (evaluative) / What should be done? (procedural)

**Assumption surfacing:** Present assumptions embedded in the selected frame as a multiSelect:
- Header: "Assumptions"
- Question: "This framing assumes several things. Which of these assumptions feel solid to you?"
- multiSelect: true
- Options list 3-4 key assumptions underlying the chosen frame
- What isn't selected identifies the productive targets for investigation

**Question behind the question:** If you suspect the real concern differs from the stated one, test it with a direct question:
- Header: "Deeper"
- Question: "I wonder if the real question might be something slightly different. Which resonates most?"
- Options: the surface question as stated / your reconstructed deeper question / a third alternative framing

**State file:** Update with the confirmed framing, surfaced assumptions, stasis level, and any "Other" responses that shifted the frame.

**Transition to Phase 2** when the user confirms a framing captures their concern. If the user keeps selecting "Other" on framing questions, stay in Phase 1 — frame instability means the real question hasn't been found yet.

## Phase 2: Hypothesize

With a frame established, generate competing ideas about what the crystallized document might say. This phase is brief and partly internal, but unlike standard elucidate, the hypotheses become partially visible through the options you design.

**Generate hypotheses:** Internally develop 3-5 competing hypotheses about what the final understanding will look like.

**Decompose into sub-questions:** Each hypothesis implies different things. Identify the discriminating questions — the ones where hypothesis A and hypothesis B predict different answers. These become the structured questions for Phase 3.

**Plan the question sequence:** Order sub-questions by expected information gain. The first questions should be the ones where you're most uncertain which option the user will select. If you can predict the answer, the question doesn't discriminate — it confirms. Put confirming questions last (or skip them).

**Direction check:** Before entering investigation, present a brief direction-setting question:
- Header: "Direction"
- Question: "Based on what we've established, the inquiry could go in a few directions. Which feels most productive?"
- Options should represent the 2-3 most distinct directions the document could take, each implying a different set of follow-up questions
- This makes the transition to Phase 3 explicit and gives the user agency over the investigation path

**State file:** Add emerging structure — the directions being considered, key questions that need answering, preliminary shape of the document.

**Transition to Phase 3** when you have discriminating questions planned and the user has confirmed a direction.

## Phase 3: Investigate

The core of the inquiry. Understanding is built through structured questioning that progressively narrows the possibility space. This is where `AskUserQuestion` is most natural — discriminating questions are its native format.

**Question design — maximize information gain:** Each question's options should split the remaining possibility space as evenly as possible. If one option is obviously the "right" answer, the question is wasted. Design options where you genuinely don't know which the user will select. See OPTION-PATTERNS.md for the full option design library.

**Alternation — probes and holistic checks:**

*Targeted probes* (every turn): Single-select questions that discriminate between competing interpretations.
- Header varies by topic
- Question targets a specific claim, relationship, or distinction
- Options represent genuinely different positions, not gradations of the same position

*Holistic checks* (every 3-4 probes): multiSelect questions that present your current model for verification.
- Header: "Check"
- Question: "Here's what I think we've established so far. Which of these feel right to you?"
- multiSelect: true
- Options list 3-4 key claims from the emerging understanding
- What the user does NOT select is as informative as what they do select
- Accompany the question with a brief prose summary of the current model — this is your free narration between structured questions

**Cognitive escalation:** Design option complexity to match escalating cognitive demand:
- Early questions: concrete, factual options (this vs. that, does X apply)
- Middle questions: explanatory options (X because of A, X because of B, X for a reason I haven't identified)
- Later questions: evaluative options (X is more important, Y is more important, the tension between them is the real insight)

**Contradiction surfacing:** When prior selections conflict with current ones, present the contradiction explicitly:
- Header: "Tension"
- Question: "Earlier you said [X]. Now you're saying [Y]. These seem to be in tension."
- Options: X is more fundamental — Y is a special case / Y is more fundamental — I've updated my thinking / Both are true in different contexts / The tension itself is the important thing

**Anomaly seeking:** Include at least one "provocative" option in each question set — an option that challenges the user's expected position or introduces an edge case. If the user selects it, follow up immediately. Design options that test boundaries, not just centers.

**Knowledge gaps:** When investigation reveals a factual gap, use `WebSearch` to find relevant information. Present findings naturally in the prose between questions, then design the next question to incorporate what was learned.

**State file updates:** Update after every 2-3 questions. Accumulate findings under emerging section headings. Begin drafting key paragraphs as they crystallize. By late Phase 3, the state file should have the skeleton of the final document.

**Interaction density:** 1-2 `AskUserQuestion` calls per turn, each with 1-2 questions. Accompany each with brief prose — your working model, what the last selection revealed, where the inquiry is headed. The prose gives context; the structured questions push understanding forward.

**Transition to Phase 4** when: (a) one interpretation clearly dominates and the others have been ruled out, (b) the user is consistently selecting confirming options with few surprises, (c) the model has been stable across several holistic checks. Before transitioning, present a readiness check:
- Header: "Ready?"
- Question: "I think we have enough to draft something. How does that feel?"
- Options: Yes, let's see a draft / There's something important we haven't covered yet / I'm not sure — can you summarize where we are? / Let's keep going a bit more

## Phase 4: Synthesize

Draft the crystallized document and verify it through structured review. The synthesis IS the final phase of questioning.

**Draft the document:** Write the full document in the state file. Remove all scaffolding. Clean prose that captures the understanding.

**Let format emerge from content.** The document might be an essay, a framework, a decision record, a set of principles, a narrative, a comparison, or something else. The content determines the form.

**Structured verification:** Present the draft in sections using `AskUserQuestion` with markdown previews. For each key section:
- Header: "Verify"
- Question: "Does this section capture it?"
- Options with markdown preview showing the draft section:
  - "Yes, this is right"
  - "The direction is right but the emphasis is wrong" (description: explain what to shift)
  - "Something important is missing here" (description: the section is incomplete)
  - "This doesn't capture what I mean" (description: needs fundamental rethinking)

**Whole-document check:** After section-level verification, present the full document structure:
- Header: "Overall"
- Question: "Looking at the document as a whole, what's your assessment?"
- multiSelect: true
- Options: The structure/flow works / The core insight is captured / Something feels off but I can't name it / It's tidy but doesn't feel true

**Robustness testing:** Test the understanding with structured challenges:
- Header: "Stress test"
- Question: "What's the strongest objection someone could raise to this understanding?"
- Options present 2-3 plausible objections you've identified, plus an Other option
- Follow up on the selected objection — does it weaken the document, or can it be addressed?

**Application test:**
- Header: "Application"
- Question: "If you applied this understanding tomorrow, what would you do differently?"
- Options present 2-3 concrete behavioral implications of the understanding
- This tests whether the understanding is actionable or merely intellectual

**Refine iteratively.** Each non-confirming selection is a signal. When the user says "the emphasis is wrong" or "something is missing," present follow-up options that narrow down what needs to change. Don't just ask "what's wrong?" — hypothesize what might be wrong and let the user select.

**Identify uncertainties explicitly.** The final document should include what remains open or uncertain.

**Closing conditions:** The inquiry closes when:
- The user confirms the document captures the understanding (via structured verification)
- The user can identify the understanding's limitations (via robustness testing)
- The user can articulate concrete applications (via application test)

Present a final closing question:
- Header: "Complete?"
- Question: "Are we done, or is there more to work through?"
- Options: This captures it — we're done / One more round of refinement / This opened up a new question I want to explore / I want to start over with a different framing

**Regression:** If verification reveals gaps → return to Phase 3 with targeted questions about the gap. If verification reveals the framing was wrong → return to Phase 1 with new candidate framings.

## Meta-Monitor

Run concurrently throughout all phases. Check these every 3-4 questions. Unlike standard elucidate, where monitoring is invisible, this variant makes some monitoring explicit through structured meta-questions.

**"Other" frequency tracking:** If the user has selected "Other" on more than roughly a third of recent questions, the option design is failing. Present a recalibration question:
- Header: "Recalibrate"
- Question: "I notice my options haven't been matching your thinking well. What's going on?"
- Options: You're asking the right questions but the options are too narrow / You're asking the wrong questions entirely / The topic has shifted and we need to reorient / The structured format is constraining — I need to explain something freely

If the user selects the last option, temporarily collect their free-form explanation via Other, then use it to redesign your option space for subsequent questions.

**Loop detection:** If the same themes keep appearing across multiple question sets without new ground being broken, surface it:
- Header: "Pattern"
- Question: "We keep circling back to [X]. What does that tell us?"
- Options: It's more central than we've been treating it / Something about the framing isn't working / We're avoiding something harder / We've actually established this — time to move on

**Cognitive overload signals:** If the user is rapidly selecting options without apparent deliberation, or consistently choosing the first option, they may be disengaged or overwhelmed. Present a process check:
- Header: "Process"
- Question: "How is this process working for you right now?"
- Options: Good — keep going / The questions are too hard or too many / I want to step back and see the big picture / I'd rather just talk freely for a bit

**Diminishing returns:** If recent selections are consistently confirming rather than reshaping the model, propose moving forward:
- Header: "Progress"
- Question: "Recent answers are confirming what we've established. I think we're converging."
- Options: Agree — let's draft something / There's something we haven't touched yet / I'm not confident yet — keep probing / The confirming answers mean we have it right — let's finalize

**Frame fixation:** If you're adding increasingly narrow qualifications to the model, the frame may be wrong:
- Header: "Reframe?"
- Question: "We keep adding exceptions and qualifications. That might mean our framing isn't quite right."
- Options: The frame is fine — complexity is real / You're right — let's try a different angle / The exceptions ARE the insight / I'm not sure — show me what a different frame would look like

## State File Management

The state file IS the emerging document. One file that transforms over the course of the inquiry.

**Phase 0-1 state:** Structured notes. Orientation selections recorded. Framing options presented and selected. Assumptions identified. This is organized from the start — the structured format produces structured notes.

**Phase 2 state:** Structure emerges. Directions considered. Key discriminating questions listed. Preliminary sections with headers.

**Phase 3 state:** Sections crystallize. Established findings written in prose. Each section annotated with the key selections that established it. Open questions marked. The file is readable as a work-in-progress.

**Phase 4 state:** Clean document. All scaffolding removed. Final form. Remaining uncertainties stated explicitly.

**Update timing:** Update the state file after every 2-3 `AskUserQuestion` exchanges. The user should be able to read the state file at any point and understand where the inquiry stands.

**Selection audit trail:** During Phases 0-3, maintain a brief audit section at the bottom of the state file recording key selections — not every answer, but the ones that shaped the inquiry's direction. Remove this section in Phase 4 when the document is finalized.

## Mode-Adaptive Behavior

Adapt the pacing and option design based on continuous signal reading. Never announce the mode.

**Extraction mode** (user selects confidently, rarely uses Other, selections are consistent and decisive):
- Move faster. Fewer orientation questions. Present more of your model in prose between questions.
- Use more evaluative and structural questions — the user knows the material, they need help organizing it.
- Holistic checks can be less frequent — the user is providing clear signal.
- Spend more time in Phase 3-4 refining structure and testing robustness.

**Discovery mode** (user frequently selects Other, hesitates between options, changes direction across questions):
- Slow down. More orientation questions. Simpler option sets with more concrete choices.
- Use more factual and exploratory questions — the user is still finding out what they think.
- Holistic checks should be more frequent — the user needs to see the emerging picture to orient.
- Tolerate longer Phase 0-1. Don't rush to frame.
- Include more genuinely open options — "None of these feel right" should be a named option, not just implicit in Other.

**Hybrid** (most common): Start in discovery, shift to extraction as clarity emerges. The transition shows up as decreasing Other frequency and faster, more decisive selections.

## `AskUserQuestion` Usage Guide

Constraints and best practices for every `AskUserQuestion` call in this skill.

**Questions per call:** Use 1-2 questions per call. Use 2 only when the questions are independent (answers to one don't affect the other). Never use more than 2 — it fragments attention.

**Options per question:** Use 2-4 options. Design each option to be genuinely distinct, not gradations of the same answer. Each option should imply a different follow-up path.

**Headers:** Max 12 characters. Use topic-relevant labels, not generic ones. Good: "Framing", "Tension", "Direction". Bad: "Question 1", "Input", "Choice".

**Descriptions:** Every option must have a description that clarifies what the option means and what selecting it implies for the inquiry. Descriptions are where nuance lives — labels are shorthand, descriptions carry meaning.

**Markdown previews:** Use for:
- Competing framings in Phase 1 (show what each frame looks like expanded)
- Draft sections in Phase 4 (show the actual text for verification)
- Model comparisons in Phase 3 (show two competing interpretations side-by-side)
Do NOT use for simple preference questions where labels and descriptions suffice.

**multiSelect:** Use for:
- Holistic checks ("which of these feel right?")
- Assumption surfacing ("which assumptions feel solid?")
- Whole-document verification ("what aspects work?")
Do NOT use for discriminating questions where the answer should be one or the other.

**Option design principles:** See OPTION-PATTERNS.md for the full library. The core principle: options should split the possibility space, not confirm it. If you can predict which option the user will select, the question is wasted.

## Reference

See `OPTION-PATTERNS.md` in this skill directory for the option design library organized by purpose, with patterns and selection principles.
