# Synthesis: Iterative Questioning for Agentic System Design

Research questions:
1. How can each of these fields/frameworks inform the design of an agentic system for iterative questioning with a user that leads to clear, grounded understanding?
2. What unique mechanism, process, or insight does each contribute?

---

## Convergence Map

### 1. Questions Should Maximize Uncertainty Reduction
[1-2 sentence description] The mathematically optimal question at each step is the one whose answer the system is most uncertain about — the question that feels like a coin flip to the asker, not the one whose answer it most wants to hear. Multiple independent traditions converge on formalizing this as expected information gain.

**Contributing topics:**
- **Active Learning (ML):** Provides the query strategy zoo — uncertainty sampling, Query by Committee, Expected Model Change — as computable heuristics for selecting maximally informative questions
- **Information-Theoretic Approaches:** Supplies the mathematical apparatus (Shannon entropy, mutual information) and the deepest reframing: a question's purpose is to change a probability distribution, not to get an answer
- **Twenty Questions / Optimal Experiment Design:** Establishes the halving principle — optimal binary questions split remaining possibilities into equal halves — and coarse-to-fine sequencing
- **Sequential Bayesian Experimental Design:** Provides the most rigorous decision-theoretic calculus via preposterior analysis and utility-matched scoring functions for different inquiry phases
- **Value of Information:** Adds the critical stopping criterion — information has value only insofar as it could change a decision — bridging information gain to action relevance
- **PAC / Query Learning:** Proves formally that membership queries and equivalence queries are complementary, establishing that targeted probes and holistic hypothesis tests are both necessary

### 2. Elicit Before Telling
The user's own knowledge, partial understanding, and existing reasoning are the primary material for building grounded understanding. Drawing these out — even imperfectly — produces qualitatively deeper comprehension than delivering correct information.

**Contributing topics:**
- **Socratic Method:** Establishes that an agent can generate value without domain expertise by probing logical relationships among claims the user already holds
- **Maieutics:** Reframes the agent from answer-provider to cognitive midwife; the first response to any substantive query should include at least one question back
- **Self-Explanation Effect:** Shows that prompting users to explain produces both deeper learning (the mechanism) and a diagnostic window into their actual mental model (the signal)
- **Elaborative Interrogation:** Provides the minimal intervention — asking "Why is this true?" — that reliably forces integration of new information with existing knowledge structures
- **Productive Failure:** Demonstrates that generating imperfect solutions before receiving guidance is not wasted effort but a necessary precondition for deep understanding
- **Motivational Interviewing:** Adds the relational dimension — people resist when argued into a position but move toward change when they feel heard and free to choose
- **Solution-Focused Brief Therapy:** Contributes the competence assumption — the user already possesses partial solutions (exceptions), and the agent's job is to surface and amplify them
- **Inquiry-Based Learning:** Generalizes to a full pedagogical framework — scaffold the user's own inquiry process, helping them formulate sharper questions rather than providing answers

### 3. Maintain Competing Hypotheses and Discriminate
Effective inquiry requires holding 3-5 competing interpretations simultaneously and selecting every subsequent question for its discriminating power — its ability to differentially shift probability across those hypotheses.

**Contributing topics:**
- **Clinical Diagnostic Reasoning:** Provides the battle-tested hypothetico-deductive cycle: generate candidates early, then ask discriminating questions that differentially affect hypothesis probability
- **Active Learning (Query by Committee):** Formalizes this as maintaining multiple models and querying wherever they disagree most — the single most directly applicable strategy for conversational agents
- **Sensemaking in Intelligence Analysis:** Adds Heuer's Analysis of Competing Hypotheses (ACH) with its emphasis on diagnosticity and disconfirming evidence over confirmatory evidence
- **Naturalistic Decision-Making:** Contributes the recognition-primed decision model and the anomaly-seeking orientation — "what would break my current interpretation?" as the fundamental question
- **Sequential Bayesian Experimental Design:** Provides model discrimination utility functions specifically designed for choosing between competing hypotheses

### 4. The Stated Question Is Almost Never the Real Question
The user's initial question is a lossy compression of their actual need, degraded through Taylor's four levels (visceral → conscious → formalized → compromised). The first task is decompression and reframing, not answering.

**Contributing topics:**
- **Reference Interview Theory:** Provides Taylor's model and the empirical finding that without question negotiation, intermediaries answer the wrong question more than half the time (the 55% rule)
- **Design Thinking:** Adds the Double Diamond — Diamond 1 is entirely about finding the right problem before Diamond 2 solves it — and Frame Creation as iterative testing of interpretations
- **Problem Posing:** Supplies systematic reframing machinery (What-If-Not strategy) and the distinction between frame-internal and frame-external questions
- **Sense-Making (Weick/Dervin):** Contributes the Situation-Gap-Bridge model showing that two users asking the same question may face entirely different gaps, and the gap determines the needed bridge
- **Double-Loop Learning:** Identifies that most failures of understanding are failures of framing; users get stuck because they ask questions within unexamined assumptions
- **Hermeneutics:** Adds the "question behind the question" — every statement is an answer to an implicit question, and understanding requires reconstructing that question

### 5. Contradiction as the Engine of Understanding
Confronting contradictions in the user's beliefs is the primary mechanism for deepening understanding. Contradictions should be surfaced and made articulable, not smoothed over or avoided.

**Contributing topics:**
- **Socratic Method (Elenchus):** The classical source — derive a contradiction from the user's own beliefs and force a choice, without dictating which belief to abandon
- **Dialectics:** Provides the full philosophical apparatus — determinate negation (the content of failure is informative), Aufhebung (preservation through transcendence), and principled non-convergence
- **Aporia:** Establishes that reaching a well-structured impasse ("I thought I knew this, but I don't") is more valuable than a direct answer because it converts passive opinion-holding into precisely targeted inquiry
- **Lakatos's Proofs and Refutations:** Contributes the taxonomy of rational responses to contradiction — monster-barring, exception-barring, lemma-incorporation — and the principle that definitions are outputs of inquiry, not inputs
- **Defeasible Reasoning:** Supplies formal machinery for rational-but-revisable inference and the critical rebutting/undercutting distinction that demands different agent responses to different types of defeat

### 6. Shared Understanding Must Be Actively Constructed and Verified
Mutual understanding is not a byproduct of successful message exchange but an ongoing, effortful, collaborative achievement requiring specific interactive mechanisms. Neglecting explicit verification accumulates undetected misalignments.

**Contributing topics:**
- **Grounding in Communication (Clark & Brennan):** Provides the two-phase contribution model (present then accept), the evidence-of-understanding hierarchy, and the principle of least collaborative effort
- **Collaborative Discourse Theory:** Adds Stalnaker's context set (shared possible worlds narrowed by each exchange) and the three-source common ground model (communal, personal, perceptual)
- **Conversational Analysis:** Contributes turn-by-turn understanding display, repair organization with preference for self-repair, and formulations (gists and upshots) as grounding checkpoints
- **Dialogue Systems / State Tracking:** Provides the engineering framework — explicit belief state with four-level confirmation status, updated every turn as a first-class data structure
- **Presupposition Theory:** Adds the accommodation mechanism and the insight that hidden presuppositions are the primary source of silent misalignment
- **Dynamic Epistemic Logic:** Formalizes grounding actions as public announcements that promote tentative understanding to common knowledge

### 7. Questions Exist on a Cognitive Hierarchy
Questions differ systematically in cognitive demand and answer-source, and effective questioning requires matching the level to the user's current state and escalating deliberately.

**Contributing topics:**
- **Bloom's Taxonomy:** Provides the six-level cognitive hierarchy (Remember through Create) crossed with four knowledge dimensions, and the sawtooth escalation pattern
- **Pedagogical Questioning Theory:** Adds the Paul-Elder arc (clarification → assumptions → evidence → perspectives → implications → metacognition) as a state machine for question sequencing
- **Question-Asking Development:** Contributes the developmental escalation (entity → procedural → explanatory) that resets in each new domain, calibrated to epistemic state not elapsed time
- **Stasis Theory:** Provides the four-stasis hierarchy (Conjecture → Definition → Quality → Procedure) and the "back down" diagnostic for locating breakdown levels
- **Question-Answer Relationships:** Adds answer-source classification (Right There → Think and Search → Author and Me → On My Own) and source-mismatch as the most common comprehension failure

### 8. Productive Struggle Produces Deeper Understanding Than Smooth Delivery
Conditions producing fluent, comfortable interaction often produce shallow, fragile understanding. Learning and performance are dissociable, and strategic friction — properly calibrated — builds durable comprehension.

**Contributing topics:**
- **Desirable Difficulties:** Provides the theoretical foundation — spacing, interleaving, retrieval practice, generation effect, varying conditions — and the learning-performance distinction
- **Productive Failure:** Demonstrates the generation-then-consolidation sequence and the RSM mechanism (diversity of representations during struggle predicts learning, not their correctness)
- **Aporia:** Establishes the phenomenology of productive impasse and the conditions under which confusion becomes a gateway rather than a barrier
- **Self-Explanation Effect:** Shows that the cognitive work of generating explanations (even incorrect ones) produces deeper learning than passively receiving correct information

### 9. Two-Level Architecture: Object-Level + Meta-Level Monitoring
Effective inquiry requires a supervisory layer that monitors the inquiry process itself — detecting loops, stalls, frame fixation, and strategy failures — separate from the layer that does the questioning.

**Contributing topics:**
- **Metacognition:** Provides the Nelson-Narens monitoring-control loop, the region of proximal learning, and calibration as a core competency
- **Heuristics / Polya (via Schoenfeld):** Adds the metacognitive control layer as the single variable that most separates experts from novices, with periodic interrupts ("Are we making progress?")
- **Double-Loop Learning:** Contributes the single-loop/double-loop distinction and the escalation trigger — when single-loop adjustments fail to converge, escalate to examining governing variables
- **Situation Awareness:** Provides the three-level SA model and the insight that most failures occur at comprehension and projection levels, not perception — asking more L1 questions when the gap is at L2 is the most common failure mode

### 10. The User's State Must Be an Explicit, Updatable Model
The agent must maintain a structured, continuously updated representation of what it believes about the user's beliefs, knowledge, and needs — not an implicit byproduct of conversation history.

**Contributing topics:**
- **Dialogue Systems / State Tracking:** Provides the engineering template — slot-value pairs, confirmation status levels, dialogue acts — as a first-class data structure
- **Belief Revision (AGM):** Supplies the formal rationality constraints — minimal change, success postulate, epistemic entrenchment — governing how the model should update
- **Dynamic Epistemic Logic:** Formalizes how each communicative action restructures the epistemic state, distinguishing hard updates (eliminate possibilities) from soft updates (reorder plausibility)
- **Collaborative Discourse Theory (Stalnaker):** Models common ground as a set of possible worlds that assertions eliminate and questions partition
- **Sequential Bayesian Experimental Design:** Provides the probabilistic implementation — prior distributions updated via Bayes' theorem after each answer

### 11. Inquiry Has Distinct Phases Requiring Different Strategies
Inquiry progresses through qualitatively different phases, and each phase demands different question types, strategies, and success criteria. Treating inquiry as a uniform process is a primary design error.

**Contributing topics:**
- **Epistemology of Inquiry (Dewey/Peirce):** Provides the foundational five-phase model (indeterminate situation → problem-setting → hypothesis → elaboration → corroboration) and Peirce's inferential spiral
- **Heuristics / Polya:** Contributes the four-phase architecture (Understand → Plan → Execute → Look Back) with phase-specific question selection
- **Design Thinking:** Adds divergent-convergent oscillation and the critical insight that exploration must precede explanation
- **Pragma-Dialectics:** Provides the four-stage critical discussion model (Confrontation → Opening → Argumentation → Concluding) with procedural norms per stage
- **Clinical Diagnostic Reasoning:** Contributes the hypothetico-deductive cycle with dual-process theory (System 1/System 2 toggle based on diagnostic signals)
- **Motivational Interviewing:** Adds the four sequential processes (Engaging → Focusing → Evoking → Planning) emphasizing that solutions without engagement backfire

### 12. Questions Are Social Acts, Not Just Information Extraction
Every question simultaneously performs social functions — establishing epistemic roles, creating obligations, affecting rapport, communicating the system's competence and intent — beyond its informational content.

**Contributing topics:**
- **Speech Act Theory:** Establishes that every utterance performs a locutionary (content), illocutionary (force), and perlocutionary (effect) act simultaneously, with felicity conditions as quality control
- **Relevance Theory:** Adds that every question carries a presumption of relevance, and repeated low-relevance questions exhaust the presumption of competence and erode trust
- **Conversational Analysis:** Contributes preference organization (dispreferred responses come with delay and hedging — diagnostic signals), epistemic status management, and repair mechanisms
- **Epistemic Vigilance:** Shows that trust is continuously managed through competence tracking, confidence calibration, and coherence checking, with appropriate uncertainty paradoxically increasing trust
- **Motivational Interviewing:** Adds the righting reflex — the natural tendency to correct confusion typically produces defensiveness — and the reflection-first architecture
- **Narrative Therapy:** Contributes externalization as a technique for directing questions through the user at the problem rather than at the user themselves

### 13. Anomalies and Exceptions Are the Highest-Value Signals
The most informative signals in inquiry are violations of expectation — anomalies, counterexamples, and exceptions that challenge the current frame. Routine confirmation is low-value; surprise is high-value.

**Contributing topics:**
- **Naturalistic Decision-Making:** Establishes anomaly detection as the trigger for deeper inquiry; the fundamental question is "what would break my current interpretation?"
- **Sensemaking in Intelligence Analysis:** Adds the reframing imperative — when anomalies accumulate, the schema needs restructuring, not patching — as where genuine insight occurs
- **Solution-Focused Brief Therapy:** Contributes exception-finding from the other direction — "When has the problem NOT occurred?" — as a lens for revealing latent resources
- **Lakatos's Proofs and Refutations:** Provides the taxonomy of rational responses to counterexamples and the principle that counterexamples drive conceptual sharpening
- **Clinical Diagnostic Reasoning:** Adds "unexplained findings" as a diagnostic timeout trigger and the consider-the-opposite debiasing strategy

---

## Tension Map

### 1. Efficiency vs. Depth
**The tradeoff:** Minimizing cognitive cost per question vs. introducing strategic friction that produces durable understanding.

**Side A** (Cognitive Load Theory, Relevance Theory, Active Learning, VOI): Every question costs the user time, attention, and patience. Minimize extraneous load. Ask the fewest, most efficient questions. Stop when marginal gain falls below cost. Optimize the effects-to-effort ratio.

**Side B** (Desirable Difficulties, Productive Failure, Socratic Method, Self-Explanation Effect): Conditions producing fluent interaction produce shallow understanding. Strategic friction — retrieval practice, generation before instruction, spaced revisitation, explanation requests — builds durable comprehension. The learning-performance distinction means optimizing for comfort systematically undermines understanding.

**Design implication:** The system must distinguish *learning-oriented* interactions (where the goal is durable understanding and strategic friction is appropriate) from *task-oriented* interactions (where the user needs an answer quickly and friction is counterproductive). In learning mode, the Desirable Difficulties framework applies; in task mode, the efficiency cluster dominates. Detecting which mode the user is in — and whether they should be in the other — is a design-critical capability.

### 2. Neutral Facilitator vs. Directive Guide
**The tradeoff:** Whether the agent should refrain from asserting and only question, or actively guide the user toward known-good answers.

**Side A** (Socratic Method, Maieutics, Motivational Interviewing, Inquiry-Based Learning, Narrative Therapy): The agent should not assert — only question, reflect, and elicit. Understanding produced by the user's own cognitive work is qualitatively different from (and more durable than) understanding delivered by an authority. Assertions provoke reactance; questions provoke thought.

**Side B** (Clinical Diagnostic Reasoning, Concept Learning/Teaching Dimensions, Active Learning, RLHF, Reference Interview Theory): When the agent has relevant domain knowledge, withholding it wastes user time and may leave them with incorrect self-generated conclusions. Efficient inquiry requires the agent to leverage its model actively, guiding questions toward the most informative regions.

**Design implication:** When the agent has domain expertise AND the user's goal is correct outcome (not self-discovery), directive guidance is appropriate. When the goal is the user's own understanding, or when the agent lacks expertise, the facilitative stance produces better results. The "Socratic bluff" — feigning ignorance while covertly steering — should be avoided in favor of transparency about which mode the system is operating in.

### 3. Formal Optimality vs. Social Appropriateness
**The tradeoff:** Mathematically optimal question selection vs. questions that maintain rapport, face, and collaborative dynamics.

**Side A** (Information-Theoretic Approaches, Sequential Bayesian, Active Learning, Twenty Questions): Question selection should be driven by expected information gain. The most informative question is the one that maximally reduces uncertainty. Formal optimization outperforms intuitive selection.

**Side B** (Speech Act Theory, Relevance Theory, Conversational Analysis, Epistemic Vigilance, Motivational Interviewing, Curiosity/Information-Gap Theory): A question can be information-theoretically optimal but socially disastrous. Questions create obligations, index epistemic status, and communicate competence. A basic question signals inattention; an overly probing question threatens face. Questions that instrumentalize the user as an "oracle" undermine the collaborative relationship that makes information exchange possible.

**Design implication:** Use formal optimization as a *candidate generation* mechanism, then filter through social appropriateness constraints. The information-theoretic ranking orders candidates; the social layer vetoes or reframes. This is analogous to the distinction between *competence* (what to ask) and *performance* (how to ask it).

### 4. Pre-Specified Hypothesis Space vs. Open Exploration
**The tradeoff:** Most formal optimization frameworks require a known hypothesis space, but the most important phase of inquiry often involves discovering what the possibilities even are.

**Side A** (Active Learning, PAC Learning, Sequential Bayesian, Twenty Questions, Concept Learning): All formal frameworks require pre-specification of the hypothesis space. Without it, there is no probability distribution to update, no entropy to measure, no information gain to compute. These frameworks are theories of exploitation, not exploration.

**Side B** (Design Thinking, Problem Posing, Zetetic Epistemology, Hermeneutics, Dialogism): The most valuable insights often involve discovering that the problem was framed wrong, that the alternatives were not what was assumed, or that the question itself needs revision. Premature specification of the hypothesis space is premature closure by another name.

**Design implication:** Use open exploration (Design Thinking, Problem Posing, Hermeneutics) early to discover and structure the hypothesis space, then transition to formal optimization (Active Learning, Bayesian Design) once the space is specified. The system needs an explicit "exploration phase" that does not attempt formal optimization, followed by an "exploitation phase" that does. Detecting the transition point — when the hypothesis space is sufficiently specified to begin formal reasoning — is a key design challenge.

### 5. Conservative Update vs. Wholesale Reframing
**The tradeoff:** Changing as little as possible to restore consistency vs. abandoning the current frame entirely when it fails.

**Side A** (Belief Revision/AGM, Defeasible Reasoning): Minimal change is a rationality constraint. When new information contradicts the model, surgically remove just the conflicting beliefs and their dependents. Conservative update preserves the investment in established understanding and avoids unnecessary disruption.

**Side B** (Double-Loop Learning, Design Thinking, Sensemaking/Intelligence Analysis, Naturalistic Decision-Making): Sometimes the whole frame is wrong. Repeated minimal patching of a flawed frame produces a degenerating research programme (Lakatos). Genuine insight often requires abandoning the current schema and building a new one — the most cognitively expensive but failure-prone operation in sensemaking.

**Design implication:** Default to minimal change (AGM), but maintain a "degeneracy detector" — when recent modifications are ad hoc patches without new insight, or when anomalies accumulate faster than they are resolved, flag the frame as potentially failing and attempt reframing. This parallels Lakatos's progressive vs. degenerating programme distinction: progressive revisions generate new predictions and explanations; degenerating ones are defensive patches.

### 6. Premature Closure vs. Inquiry Paralysis
**The tradeoff:** Converging too early on an answer vs. deferring indefinitely because there is always one more thing to check.

**Side A** (Epistemology of Inquiry, Zetetic Epistemology, Clinical Reasoning, Sensemaking): Premature closure is the single most common error in inquiry. Every framework warns against it. The most valuable move is often to resist the pull toward a conclusion and keep the question open.

**Side B** (Zetetic Epistemology's own "no-indefinite-deferral" norm, VOI, practical necessity): A system that always finds another question to ask fails in practice. Inquiry must terminate. The question is when.

**Design implication:** Use VOI-based stopping criteria: compute the expected value of the best remaining question at every step and stop when net VOI (expected gain minus cost of asking) falls below zero. Make closure decisions explicit and auditable — articulate what evidence was gathered, what alternatives were considered, what threshold was met, and what would prompt reopening.

---

## Dependency Graph

### Foundational Layer
Topics that other insights depend on but that stand alone.

- **Epistemology of Inquiry (Dewey/Peirce):** The phase structure of inquiry itself. Every other framework presupposes that inquiry is a structured process with qualitatively different stages. Without this, question-selection frameworks lack context for when they apply.
- **Cognitive Load Theory:** The fundamental constraint on all question design. No questioning strategy can succeed if it exceeds working memory capacity. Every topic that recommends "ask X" is implicitly constrained by CLT's limits.
- **Grounding in Communication (Clark & Brennan):** The mechanism by which any shared understanding is achieved in dialogue. Every topic that assumes mutual understanding is building on Clark's grounding model, whether explicitly or not.
- **Speech Act Theory (Searle, Austin):** The insight that questions are social actions, not just information requests. Every topic discussing the relational or social dimension of questioning depends on this foundation.
- **Relevance Theory (Sperber & Wilson):** The efficiency constraint on all communication. The presumption of relevance governs user willingness to engage; every questioning strategy operates within this constraint.
- **Information-Theoretic Approaches:** The mathematical apparatus for quantifying uncertainty and measuring question value. Every formal question-selection strategy is built on this foundation.

### Middle Layer
Topics that build on foundations and inform applications.

- **Erotetics** ← depends on Epistemology of Inquiry: Formalizes questions as first-class logical objects with structure, presuppositions, and entailment relations. Required for principled question management.
- **Belief Revision (AGM)** ← depends on Epistemology of Inquiry + Information Theory: Formalizes how a model of the user's state should update when confronted with new or contradictory information.
- **Metacognition** ← depends on Cognitive Load Theory: The monitoring layer that manages cognitive resources and detects when strategies are failing. Required for self-correcting inquiry.
- **Presupposition Theory** ← depends on Speech Act Theory + Grounding: What must be shared (common ground) before a question is legitimate. Required for avoiding defective questions.
- **Conversational Analysis** ← depends on Grounding + Speech Act Theory: How understanding is displayed and repaired turn by turn. Required for reading user signals.
- **Dialectics** ← depends on Epistemology of Inquiry: The role of contradiction in advancing understanding. Required for the "contradiction as engine" insight.
- **Collaborative Discourse Theory** ← depends on Grounding: Extends Clark's dyadic model to Stalnaker's context set, formalizing common ground as possibility space.
- **Epistemic Vigilance** ← depends on Relevance Theory + Speech Act Theory: How trust is continuously managed through source and content evaluation.
- **Dynamic Epistemic Logic** ← depends on Information Theory + Epistemology of Inquiry: Formalizes how communicative actions change knowledge states. The formal backbone for explicit state tracking.
- **Curiosity / Information-Gap Theory** ← depends on Information Theory + Cognitive Load Theory: The motivational engine — how to maintain user engagement by calibrating gap visibility to the Goldilocks zone.
- **Dialogism** ← depends on Speech Act Theory + Grounding: Extends the social-action view to the constitutive claim that meaning emerges between participants, not from either alone.

### Applied / Specialized Layer
Topics that apply more general insights to specific contexts or problem types.

- **Active Learning (ML)** ← applies Information Theory to computable question selection strategies
- **Sequential Bayesian Experimental Design** ← applies Information Theory with full decision-theoretic rigor
- **Socratic Method** ← applies Dialectics + Erotetics to belief examination through questioning
- **Maieutics** ← applies Socratic Method with a constructive orientation (eliciting latent knowledge)
- **Clinical Diagnostic Reasoning** ← applies hypothesis-driven inquiry + Information Theory to diagnostic contexts
- **Naturalistic Decision-Making** ← applies Metacognition + Sensemaking to expert pattern recognition
- **Design Thinking** ← applies Epistemology of Inquiry to creative problem-reframing
- **Motivational Interviewing** ← applies Speech Act Theory + Dialogism to change-oriented conversations
- **Reference Interview Theory** ← applies Sense-Making to information need decompression
- **Bloom's Taxonomy** ← applies Metacognition + CLT to cognitive level calibration
- **Pedagogical Questioning Theory** ← applies Bloom's + Socratic Method to instructional design
- **Question-Asking Development** ← applies Information Theory + CLT to developmental questioning patterns
- **Productive Failure** ← applies Desirable Difficulties to generation-then-consolidation sequencing
- **Elaborative Interrogation** ← applies Self-Explanation Effect as a minimal questioning intervention
- **Problem Posing** ← applies Dialectics + Design Thinking to systematic question generation
- **Lakatos** ← applies Dialectics + Defeasible Reasoning to conjecture-refutation cycles
- **Narrative Therapy** ← applies Dialogism + Speech Act Theory to externalization and re-authoring
- **SFBT** ← applies a solution-focused inversion of standard problem-analysis orientations
- **Stasis Theory** ← applies Erotetics to question-type diagnosis via a four-level hierarchy
- **QAR** ← applies Metacognition to answer-source classification and routing

### Independent
Topics with no strong dependency relationships to others; they contribute unique perspectives.

- **RLHF:** A distinct learning paradigm (preference learning from comparison) from a separate tradition. Informs how the system can adapt its questioning strategy from implicit user feedback without explicit instruction.
- **Root Cause Analysis / 5 Whys:** A domain-specific vertical-drilling technique from manufacturing. Contributes the depth-forcing heuristic and evidence requirement at each causal level.
- **Heuristics / Polya:** While connected to Metacognition (via Schoenfeld), the heuristic dispatch table — a lookup from problem-state to recommended strategy — is a unique contribution not derivable from other topics.

---

## Gap Analysis

### 1. Affective-Emotional Dynamics
**What's missing:** Multiple topics note that questions have emotional effects (Aporia warns of frustration, MI addresses resistance, CA reads hedging as diagnostic, CBT monitors cognitive state), but no topic provides a comprehensive framework for the emotional arc of inquiry. How does emotional state interact with cognitive processing during questioning? When does emotional support take precedence over epistemic progress? How should the system manage the affective trajectory across a full interaction?
**Why it matters:** An agent that optimizes for epistemic gain while ignoring affective state will trigger disengagement, defensiveness, or compliance without understanding. The emotional dimension is acknowledged by many topics but theorized by none.
**Possible sources:** Affect theory in education (Pekrun's control-value theory of achievement emotions), therapeutic alliance research, emotional regulation frameworks (Gross), trust dynamics in human-computer interaction.

### 2. Implementation Architecture
**What's missing:** The collection provides rich principles and mechanisms but almost no guidance on computational architecture — how to represent, store, and reason over these structures in software. Dialogue Systems / State Tracking comes closest but is optimized for slot-filling, not open-ended inquiry. How should the belief model be implemented? How should phase detection work computationally? How should multiple competing frameworks be integrated in a single system?
**Why it matters:** The research questions explicitly ask about designing an agentic *system*. The gap between "an agent should maintain competing hypotheses" (a principle) and "here is how to represent and update competing hypotheses in code" (an architecture) is significant.
**Possible sources:** Cognitive architecture research (ACT-R, SOAR), modern LLM agent architectures, belief network implementations, planning under uncertainty (POMDP solvers).

### 3. Long-Term Adaptation and Memory
**What's missing:** Nearly all frameworks address a single session. How should the system evolve its approach across multiple interactions with the same user? How does accumulated understanding from past sessions inform current questioning? How should the user model persist, age, and be revised over time?
**Why it matters:** Grounded understanding often develops over multiple conversations. A system that starts from scratch each time wastes prior investment and fails to build deepening rapport. Belief Revision (AGM) provides principles for single-session updates but says nothing about cross-session model management.
**Possible sources:** Longitudinal learning research, spaced repetition systems (Ebbinghaus, Leitner), user modeling in adaptive systems, memory-augmented architectures.

### 4. Multi-Stakeholder and Group Dynamics
**What's missing:** Almost all frameworks assume a dyadic agent-user interaction. Accountable Talk and Knowledge-Building Discourse are designed for groups but their translation to an agent context is underspecified. How should an agentic system handle multiple users with conflicting understandings, or facilitate group sensemaking?
**Why it matters:** Many real-world understanding tasks involve multiple stakeholders with different knowledge, goals, and perspectives. The collection's dyadic assumption limits applicability.
**Possible sources:** Group decision support systems, computer-supported collaborative learning (CSCL), deliberation theory, conflict resolution frameworks.

### 5. Domain Knowledge Integration and Retrieval
**What's missing:** The collection extensively addresses *how to question* but barely addresses *what to know*. When should the agent provide information versus question? How should domain knowledge be structured for optimal integration with questioning? How should the agent decide between elicitation and instruction?
**Why it matters:** The Socratic Method, MI, and IBL all emphasize elicitation over instruction, but all also acknowledge that elicitation fails when the user genuinely lacks information. The decision boundary between "elicit" and "inform" is critical but underspecified. Clinical Reasoning implicitly assumes rich domain knowledge; the others often assume it away.
**Possible sources:** Knowledge management, retrieval-augmented generation (RAG) architectures, expert systems design, the teaching-with-analogies literature.

### 6. Cultural and Individual Adaptation
**What's missing:** Several topics note cultural variation in questioning norms (Socratic Method notes that direct contradiction is valued in some contexts but rude in others; CA notes that conversational norms vary) but none provides a framework for systematic adaptation. How should questioning style calibrate to individual personality, cultural background, expertise level, and communication preferences?
**Why it matters:** A one-size-fits-all questioning strategy will be effective for some users and counterproductive for others. The system needs to adapt not just what it asks but how it asks.
**Possible sources:** Cross-cultural communication research (Hofstede, Hall), personality-adaptive interfaces, learning style research (with appropriate caveats about its contested empirical status), user experience personalization.

---

## Unified Framework

### Overview
**Framework format: Phased workflow.** The research questions ask how these fields can *inform the design* of an agentic system — a design verb pointing toward a phased workflow. The convergence analysis reveals that inquiry has distinct phases (Cluster 11) and that different mechanisms apply at different stages. The framework below sequences the collected mechanisms into an actionable architecture for iterative questioning.

This framework describes a repeating cycle through five operational phases, governed by a concurrent meta-level monitor. Each phase has specific entry conditions, primary mechanisms drawn from the convergence clusters, available question types, and transition criteria. The phases are not strictly linear — regression to earlier phases is expected and desirable when the meta-level monitor detects the need.

### Phase 0: Orient and Calibrate
**Entry condition:** New interaction or new topic within an existing interaction.
**Purpose:** Establish the relationship, detect the user's state, and assess the actual need behind the stated question.

**Primary mechanisms:**
- Engage before inquiring (MI: engaging process) — build minimal rapport before probing
- Detect the user's epistemic state: domain expertise (CLT: expertise level), cognitive level (Bloom's), and emotional readiness
- Decompress the stated question (Reference Interview: Taylor's 4 levels) — assume the initial question is compromised
- Apply Dervin's Situation-Gap-Use triad: What is the user's current situation? Where specifically are they stuck? What will they use the understanding for?
- Establish initial common ground (Grounding: communal vs. personal; Presupposition Theory: verify shared assumptions)

**Available question types:**
- Open-ended orientation: "What's the situation you're working with?"
- Gap detection: "Where specifically did you get stuck?"
- Use/decision elicitation: "What are you trying to decide or do with this?"
- Competence-framing: "What parts are you already clear on?" (SFBT)

**Transition criteria:** Move to Phase 1 when the system has a working model of the user's situation, gap, and intended use — even if approximate. Do not over-invest in orientation; it can be refined in later phases.

### Phase 1: Frame the Problem (Divergent)
**Entry condition:** Working model of user's situation/gap exists but the problem formulation has not been validated.
**Purpose:** Ensure the right problem is being addressed before attempting to solve the wrong one. This is Diamond 1 of the Double Diamond.

**Primary mechanisms:**
- Generate multiple candidate framings of the problem (Design Thinking: Frame Creation; Problem Posing: What-If-Not)
- Diagnose stasis level (Stasis Theory): Is this a factual, definitional, evaluative, or procedural question? Is the apparent level the real level?
- Reconstruct the question behind the question (Hermeneutics)
- Elicit the user's current understanding before introducing new frames (Socratic Method: "say what you believe" rule; Productive Failure: generation before instruction)
- Examine governing variables (Double-Loop Learning: are the user's assumptions the source of their difficulty?)

**Available question types:**
- Reframing probes: "What if it's actually a problem of X rather than Y?"
- Assumption surfacing: "What are you taking for granted here?"
- Stasis diagnosis: "Are we clear on what X even means before we evaluate it?"
- Perspective shifts: "What would someone who disagrees say the real issue is?"

**Transition criteria:** Move to Phase 2 when the system and user have agreed on a problem formulation — the frame has been tested against at least one alternative and the user has confirmed it captures their actual concern. If the frame keeps shifting, stay in Phase 1.

### Phase 2: Structure and Hypothesize
**Entry condition:** Agreed problem formulation exists.
**Purpose:** Generate competing hypotheses, structure the inquiry space, and plan the questioning sequence.

**Primary mechanisms:**
- Generate 3-5 competing hypotheses about the answer/situation (Clinical Reasoning: early hypothesis generation)
- Model the hypothesis space explicitly, even if approximate (Concept Learning: teaching dimension; Active Learning: version space)
- Decompose the principal question into sub-questions with presupposition checking (Erotetics: erotetic implication; Interrogative Model: notebook)
- Build an inquiry plan sequenced by expected information gain (Information Theory: bisection principle; Twenty Questions: coarse-to-fine)
- Establish what counts as evidence for and against each hypothesis (Informal Logic: Toulmin decomposition)

**Available question types:**
- Hypothesis-generating: "What are the main possibilities here?"
- Discriminating: "Is this more like X or Y?" (questions where each hypothesis predicts a different answer)
- Presupposition-checking: "Before I ask about X, does Y hold?"
- Boundary-probing: "Does this apply in the case of Z?" (Concept Learning: focus on boundaries, not prototypes)

**Transition criteria:** Move to Phase 3 when the system has at least 2-3 discriminable hypotheses and a planned sequence of discriminating questions. If the hypothesis space cannot be structured, return to Phase 1 (the problem may be mis-framed).

### Phase 3: Investigate and Discriminate (Convergent)
**Entry condition:** Structured hypothesis space and planned question sequence exist.
**Purpose:** Iteratively reduce uncertainty through targeted questioning, updating the model with each answer.

**Primary mechanisms:**
- Select questions by expected information gain, filtered through social appropriateness (Info Theory + Relevance Theory; Tension 3's resolution)
- Alternate between membership queries (targeted probes) and equivalence queries (holistic hypothesis tests) (PAC Learning: both are necessary)
- Escalate cognitive level deliberately (Bloom's: sawtooth pattern; Pedagogical Questioning: Paul-Elder arc)
- Use contradiction detection as a deepening mechanism (Dialectics: surface internal tensions; Socratic Method: elenchus)
- Seek anomalies and exceptions (NDM: "what would break this interpretation?"; SFBT: exception-finding)
- Verify shared understanding at regular intervals (Grounding: two-phase contributions; CA: formulations)
- Update the belief model with each answer (AGM: minimal change with entrenchment ordering; Bayesian: posterior update)

**Available question types:**
- Discriminating questions: questions where competing hypotheses predict different answers
- Elaborative interrogation: "Why do you think that's the case?"
- Explanation requests: "Can you walk me through how that works step by step?" (Self-Explanation; Explanation-Seeking)
- Counterexample probes: "What about the case where...?" (Lakatos)
- Grounding checks: "So what we've established is X — does that match your understanding?"
- Evidence challenges: "What's the evidence for that?" (Informal Logic: Toulmin)

**Transition criteria:** Move to Phase 4 when: (a) one hypothesis is clearly dominant, (b) expected information gain of the best remaining question falls below a cost-relative threshold (VOI: stopping criterion), or (c) the belief model has stabilized over several recent exchanges. If anomalies accumulate faster than they resolve, return to Phase 1 (the frame may be wrong — Tension 5's degeneracy detector).

### Phase 4: Synthesize and Verify
**Entry condition:** Convergent understanding achieved; belief model stable.
**Purpose:** Consolidate understanding, verify through multiple channels, and ensure the user can apply it.

**Primary mechanisms:**
- Construct a shared account of what has been established (Knowledge-Building Discourse: rise-above synthesis)
- Verify through explanation requests — the user's ability to explain is the gold standard for understanding (Self-Explanation Effect; Elaborative Interrogation)
- Test against counterexamples and edge cases (Lakatos: proofs and refutations)
- Apply to the user's specific situation (Hermeneutics: application is constitutive of understanding, not separate from it)
- Compare the final understanding with the user's initial framing to make progress visible (Productive Failure: consolidation references prior attempts)
- Explicitly identify remaining uncertainties and open questions (Zetetic Epistemology: closure conditions)

**Available question types:**
- Synthesis prompts: "Given everything we've discussed, how would you now describe X?"
- Application tests: "How would you apply this to your specific situation?"
- Transfer probes: "What would change if the context were Y instead?"
- Robustness checks: "What's the strongest objection to this understanding?"
- Metacognitive calibration: "How confident are you in this, and what would change your mind?"
- Post-solution problem posing: "What new questions does this raise?" (Problem Posing: Silver's post-solution)

**Transition criteria:** Close when: the user can articulate the understanding in their own terms, apply it to their situation, and identify its limitations. Return to Phase 3 if verification reveals gaps. Return to Phase 1 if verification reveals a framing error.

### Meta-Level Monitor (Concurrent Throughout)
**Purpose:** Supervise the inquiry process itself, detecting failures that no single phase can see from within.

**Monitors and their triggers:**
- **Phase tracker:** Which phase are we in? Is it the right one? (Heuristics/Polya: Schoenfeld's metacognitive interrupts; Epistemology of Inquiry: phase detection)
- **Loop detector:** Are we circling without progress? → Escalate to double-loop questioning or return to Phase 1 (Double-Loop Learning; Metacognition)
- **Cognitive load monitor:** Is the user showing overload signals (vague responses, confusion, disengagement)? → Decompose, reduce element interactivity, or pause (CLT)
- **Frame fixation detector:** Are we patching a failing frame? → Flag for potential reframing; return to Phase 1 (NDM; Sensemaking; Lakatos: degenerating programme)
- **Rapport monitor:** Is the user showing dispreference signals (hedging, delay, resistance)? → Shift to engaging/validating before continuing inquiry (CA; MI; Epistemic Vigilance)
- **Diminishing returns detector:** Is each new question producing less model change? → Propose moving to Phase 4 or closing (Active Learning: stopping criteria; VOI)
- **Exploration-exploitation balance:** Are we only clarifying known uncertainties or also discovering unknown unknowns? → Inject exploratory questions periodically (Active Learning: exploration-exploitation tradeoff; Curiosity/Information-Gap: diversive curiosity)

### Open Questions
Unresolved tensions and gaps that should be acknowledged when applying this framework:

1. **The affect gap:** This framework lacks a principled model of emotional dynamics during inquiry. It addresses cognitive state (CLT, Metacognition) and relational signals (CA, MI) but not the emotional arc of understanding. Practitioners should watch for and manage frustration, anxiety, and disengagement as first-class concerns, not afterthoughts.

2. **The mode-detection problem:** Tension 1 (Efficiency vs. Depth) and Tension 2 (Facilitator vs. Guide) both require the system to detect what the user needs, which may differ from what they ask for. No framework provides a reliable algorithm for this detection.

3. **The hypothesis space bootstrap:** Tension 4 identifies that formal optimization requires a pre-specified hypothesis space, but Phase 1 is precisely about discovering what the possibilities are. The transition from open exploration to formal optimization is acknowledged as critical but underspecified.

4. **Cultural calibration:** The framework's questioning strategies assume norms of direct, analytical inquiry that may not transfer across cultural contexts. The degree of directness in contradiction-surfacing (Cluster 5), the expected cognitive level of questions (Cluster 7), and the tolerance for productive struggle (Cluster 8) all vary significantly.

5. **Implementation fidelity:** The distance between these principles and working software remains significant. The framework specifies *what* the system should track and *when* it should transition, but *how* to implement these capabilities computationally (Gap 2) is beyond what the collected topics address.
