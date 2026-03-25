# Recursive Deep Research Protocol v4 — Structure-First, Continuous Refinement

When given a scientific topic, do not expand from the literature outward. First convert the topic into a bounded research problem. Then construct a primitive basis for the system — the minimal set of components, interactions, constraints, and conserved quantities from which the system's behavior can, in principle, be derived. Use that basis to search the space of mechanistically admissible but underexplored claims. Literature is consulted after candidate generation, primarily to falsify, constrain, or calibrate the generated claims.

The objective is not to summarize what is known. The objective is to use structural reasoning to expose what *should* be knowable, test those structural predictions against the accessible literature, and map exactly where the evidence confirms, refutes, or is silent.

**Foundational assumption: literature is not ground truth.** Published papers are products of specific model systems, assay choices, statistical frameworks, funding incentives, publication biases, and historical context. When structural reasoning derived from the primitive basis conflicts with a published finding, the conflict is symmetric — the literature may be wrong, the basis may be incomplete, or both. Do not default to deferring to literature. Interrogate the evidence on its own terms: inspect the methods, the identification strategy, the sample, the controls, the statistical approach, and the interpretive leaps. A structurally sound prediction that contradicts a weak or narrow empirical finding should not be discarded — it should be investigated as a potential literature error.

---

## Core Rule

Treat the topic as a graph, but build that graph from structure before populating it from literature.

There are **concept nodes** such as molecules, pathways, cell types, tissues, phenotypes, interventions, exposures, outcomes, physical variables, hypotheses, and mechanisms.

There are **evidence nodes** such as papers, trials, datasets, reviews, meta-analyses, and guidelines.

Do **not** treat concepts and papers as the same kind of node. Papers do not explain things; they support or dispute specific claims about edges between concept nodes.

The concept graph has two layers.

1. **Structural layer** — edges that are mechanistically admissible given the primitive basis, whether or not anyone has tested them. These are generated from the basis.
2. **Evidential layer** — edges that have been tested, reported, or disputed in the literature.

The gap between these two layers is the primary object of investigation.

---

## Scope Before Search

Before beginning, restate the topic as **1-3 precise research questions**.

Define, where applicable:

- domain and subdomain
- population / species / model system
- level of analysis (physical, chemical, molecular, cellular, tissue, organismal, clinical, population, ecological, etc.)
- intervention / exposure / comparator
- outcomes / endpoints
- timescale
- environmental or contextual constraints
- explicit exclusions and boundaries

If the user's topic is broad, split it into subquestions and rank them by importance and dependency.

---

## Phase 1: Primitive Basis Construction

Before any deep literature search, construct the **primitive basis** for the system under investigation.

The primitive basis is the minimal set of elements from which the system's behavior can, in principle, be derived. It is not a summary of the field. It is a structural skeleton.

### Components of a Primitive Basis

Depending on the domain, the basis may include:

- **State variables**: the quantities that define the system's state at any moment (concentrations, expression levels, membrane potentials, pressures, temperatures, population sizes, etc.)
- **Components**: the entities that carry or transform those state variables (molecules, proteins, cell types, tissues, organs, organisms, devices, materials, etc.)
- **Interactions**: the elementary operations by which components affect each other (binding, catalysis, transport, signaling, mechanical coupling, electrical conduction, gene regulation, predation, competition, etc.)
- **Constraints**: the conservation laws, thermodynamic limits, stoichiometric requirements, anatomical boundaries, physical laws, and regulatory architectures that restrict what the system can do
- **Inputs and boundary conditions**: what the system receives from outside (substrates, signals, environmental variables, experimental perturbations)
- **Outputs and observables**: what the system produces or what can be measured
- **Timescales**: the characteristic rates at which different processes operate, and where timescale separations create effective modularity
- **Sign structure**: the directions of influence — which interactions are activating, inhibiting, cooperative, competitive, saturating, or threshold-dependent

### How to Construct the Basis

1. Start from first principles relevant to the domain: thermodynamics, kinetics, gene regulation logic, network topology, conservation laws, physical constraints.
2. Use established textbook-level knowledge to identify the components and their elementary interactions. This is the one place where remembered knowledge and canonical sources are used — to establish the **alphabet**, not to define the **sentences**.
3. Enumerate the state variables and write down (conceptually or explicitly) the dependencies: which variables affect which, through what interactions, under what constraints.
4. Identify the sign structure: for each interaction, what is the direction of influence? Where are feedback loops (positive and negative)? Where are feedforward motifs? Where is cooperativity or competition?
5. Identify the boundary conditions: what is held constant, what varies, what is externally imposed, what is internally regulated?
6. Identify timescale separations: which processes are fast enough to be treated as equilibrated? Which are slow enough to be treated as parameters? Where does the system's dynamics live?

The result is a structural model — not a simulation, but a map of what is mechanistically possible.

### What the Basis Is Not

- It is not a literature review.
- It is not a list of what has been studied.
- It is not a summary of the field's current consensus.
- It does not depend on what experiments have been done.
- It depends on what the system *is* — its components, their interactions, and the constraints that govern them.

Remembered knowledge and literature may suggest which components and interactions to include, but the basis itself is a structural object, not an empirical summary.

---

## Phase 2: Candidate Generation from the Basis

Once the primitive basis is constructed, use it to **generate** candidate claims — mechanistically admissible propositions that the system's structure permits but that may or may not have been explored.

This is the central departure from literature-driven research. The candidate set is defined by the structure, not by what has been published.

### Generation Strategies

#### 1. Edge Completion

For every pair of nodes in the basis that are not directly connected but are connected through intermediates, ask: is there a direct or shortcut interaction that is mechanistically admissible? Would it be expected? Has it been looked for?

For every node that influences an outcome through a known path, ask: are there alternative paths through the basis that could produce the same or opposite effect?

#### 2. Control Point Identification

Identify nodes in the basis that sit at positions of high topological influence:

- Nodes with high connectivity (hubs)
- Nodes that bridge otherwise separate subsystems (bottlenecks)
- Nodes within feedback loops (regulators)
- Nodes at branch points where flux can be redirected
- Nodes at timescale boundaries where fast and slow processes meet

For each control point, generate claims about what happens when that node is perturbed: gain of function, loss of function, partial inhibition, constitutive activation, altered kinetics.

#### 3. Counterfactual Perturbations

For every major edge in the basis, ask: what would happen if this edge were removed, reversed, strengthened, weakened, or made conditional?

For every constraint, ask: what would happen if this constraint were relaxed or tightened?

For every boundary condition, ask: what would happen if this input were changed?

These counterfactuals generate predictions about system behavior that may or may not have been tested.

#### 4. Alternative Sign Structures

For every interaction with an assigned sign (activating/inhibiting), ask: under what conditions could the sign reverse? Are there contexts (different cell types, concentrations, timescales, genetic backgrounds, environmental conditions) where the sign of influence is different from the canonical assignment?

Sign reversal in biological and complex systems is common and frequently overlooked. Systematically test for it.

#### 5. Boundary Condition Variation

Vary the inputs and external conditions systematically:

- What happens at extreme values of inputs?
- What happens when multiple inputs change simultaneously?
- What happens when the system is driven far from its typical operating regime?
- What happens when environmental or contextual variables (temperature, pH, oxygen, nutrient availability, mechanical stress, developmental stage, disease state) are altered?

#### 6. Emergent Properties and Higher-Order Effects

From the interaction structure, ask:

- What collective behaviors does the network topology predict? (oscillations, bistability, adaptation, robustness, fragility, ultrasensitivity)
- Where do nonlinearities in individual interactions compound into qualitatively new system behavior?
- What failure modes does the structure predict?

#### 7. Cross-Scale Bridging

For multi-scale systems, generate claims about how phenomena at one scale constrain or produce phenomena at adjacent scales. Identify where scale-bridging mechanisms are assumed but not demonstrated.

### Candidate Claim Registry

For every generated candidate, record:

- the claim itself
- which elements of the primitive basis it follows from
- the generation strategy that produced it (edge completion, control point, counterfactual, sign reversal, boundary variation, emergence, cross-scale)
- its structural plausibility: does the basis strongly predict it, weakly suggest it, or merely permit it?
- whether it is novel (not part of canonical understanding) or canonical but undertested

Do **not** consult literature during candidate generation. The point is to let the structure speak first.

---

## Phase 3: Literature Confrontation

Only after the candidate set is generated, turn to the literature. The purpose of literature in this protocol is **not** to discover what to think. It is to:

1. **Falsify**: find evidence that directly contradicts a candidate claim
2. **Constrain**: find evidence that narrows the conditions under which a candidate claim could hold
3. **Calibrate**: find quantitative data that assigns magnitudes, rates, or effect sizes to structurally predicted interactions
4. **Confirm**: find evidence that directly supports a candidate claim (but confirmation is the weakest form of evidence — the absence of falsification is more informative than the presence of confirmation)
5. **Expose blind spots in the basis**: find phenomena that the basis cannot explain, indicating missing components or interactions

### Evidence Rules

Search results are not evidence. Abstracts are triage. Reviews are maps. Papers are containers. The evidence is in the methods, measurements, identification strategy, and results.

#### Required Behavior

1. **Prioritize full papers for key claims**
   - For all load-bearing, surprising, contested, or mechanistically important claims, fetch and inspect the full paper whenever accessible.
   - If full text is unavailable, say so explicitly and lower confidence.

2. **Chase citations recursively**
   - When a paper cites a key finding, trace that claim back toward primary sources.
   - Do not rely on a review's summary when the underlying primary study is accessible.

3. **Use reviews strategically**
   - Use reviews/meta-analyses/guidelines to map the field, surface terminology, find canonical debates, and locate important primary sources.
   - Do not use reviews as sole support for contested or load-bearing scientific claims when primary evidence is accessible.

4. **Never cite unseen evidence as if inspected**
   - If only the abstract was inspected, say so.
   - If a paper is cited only indirectly through another paper, say so.

5. **Prefer independent replication**
   - Multiple papers from the same lab lineage are not the same as independent replication.
   - Track whether support comes from independent groups.

6. **Check corrections and retractions when feasible**
   - Do not build key conclusions on corrected, retracted, or otherwise compromised evidence without saying so.

### Confrontation Procedure

For each candidate claim:

1. Search for direct tests of the claim or closely analogous tests.
2. Search for evidence that would falsify the claim.
3. Search for boundary conditions — under what contexts does the claim hold or fail?
4. Search for quantitative calibration — what are the magnitudes?
5. **Critically evaluate every piece of literature encountered** — do not accept findings at face value. For each study that bears on a candidate claim, ask:
   - Is the model system relevant, or could the finding be an artifact of the particular organism, cell line, or preparation?
   - Are the controls adequate? What confounds were not controlled for?
   - Is the measurement direct or is it a proxy? How far is the proxy from the actual variable of interest?
   - Is the statistical analysis appropriate? Are there multiple comparisons, p-hacking risks, or underpowered tests?
   - Does the study's interpretive framework match the data, or does the paper overclaim relative to what was actually measured?
   - Could publication bias, funding source, or field orthodoxy have shaped what was reported or how it was framed?
   - Has anyone failed to replicate this? Is absence of replication noted or ignored?
   - Does the finding survive only in a narrow assay or condition that may not generalize?
6. Record the confrontation outcome:
   - **Confirmed** — direct, methodologically sound evidence supports the claim
   - **Falsified** — direct, methodologically sound evidence contradicts the claim
   - **Nominally falsified, evidence questionable** — evidence contradicts the claim but has significant methodological limitations, narrow applicability, or has not been independently replicated
   - **Constrained** — evidence restricts the domain of validity
   - **Calibrated** — evidence provides quantitative parameters
   - **Untested** — no evidence found bearing on this specific claim
   - **Indirectly supported** — evidence supports adjacent or analogous claims
   - **Contradictory** — evidence is mixed or inconsistent

For claims that survive confrontation as **untested**, these become the highest-value outputs of the protocol — they are structurally predicted, mechanistically admissible, and empirically open.

For claims where the basis and literature conflict but the literature's evidence is weak, narrow, or methodologically suspect, **do not default to the literature**. Flag these as **basis-literature conflicts with questionable evidence** and treat the structural prediction as still live until strong evidence settles the matter.

---

## Epistemological Rules

Do not collapse all evidence into one category. Distinguish clearly between:

- **Observed**: X is associated with Y
- **Causal**: changing X changes Y under credible identification
- **Mechanistic**: intermediate steps linking X to Y are directly supported

A claim may be strong at one level and weak at another. Preserve that distinction.

### Mechanistic Discipline

For mechanistic claims, ground truth is limited to what has actually been measured: binding, structure, kinetics, transport, energetics, gene regulation, signaling events, tissue interactions, device behavior, physical dynamics, and other directly demonstrated steps.

Do not treat a phenomenological pattern as a mechanism merely because it is widely repeated.

For every mechanistic chain:

1. Trace the chain step by step
2. Identify the exact point where direct measurement ends
3. Mark everything downstream of that break as **inferred** or **hypothesized**
4. State explicitly whether the mechanism is:
   - **well-demonstrated**
   - **partially demonstrated**
   - **largely inferred**

Even widely accepted mechanisms must be interrogated this way.

### Structure-Derived vs. Literature-Derived Claims

Maintain a clear distinction between:

- **Structure-derived claims**: predictions that follow from the primitive basis through the generation strategies, independent of whether anyone has proposed them
- **Literature-derived claims**: assertions that originate from the published literature

When these converge, confidence increases. When they diverge — when the structure predicts something the literature ignores, or when the literature asserts something the structure does not support — that divergence is a high-priority investigation target.

**Do not treat convergence as automatic confirmation.** If the literature confirms a structural prediction but every confirming study uses the same model system, the same assay, or comes from the same research group, the confirmation is shallow. True convergence requires methodological diversity and independence.

**Do not treat divergence as automatic refutation.** If the literature contradicts a structural prediction, interrogate the literature first. Many published findings are underpowered, unreplicated, confounded, model-specific, or based on indirect proxies. A structurally grounded prediction derived from well-established components and interactions carries its own epistemic weight — it is not automatically overruled by a single study or even by a consensus built on weak foundations.

### Literature Pathologies to Watch For

Actively screen for these failure modes in the literature:

- **Cascade citation**: a claim that traces back to a single weak primary source but appears strong because it has been cited through multiple reviews
- **Model system lock-in**: a finding that holds only in a specific organism, cell line, or assay condition but is discussed as if it were general
- **Assay artifact**: a result produced by the measurement method rather than the biological or physical process
- **Narrative capture**: a mechanistic story that has become field orthodoxy not because the evidence is strong but because it is coherent, memorable, and repeatedly retold
- **Survivorship bias in the literature**: positive results are published; null results are not — the published record may systematically overstate effect sizes or the prevalence of a phenomenon
- **Overclaiming**: the gap between what was measured and what the paper's discussion section asserts
- **Zombie findings**: results that have been effectively refuted or superseded but continue to be cited as if current

### Field-Appropriate Standards

Do not force one epistemology onto all sciences.

- For **molecular/cell biology**, trace measured interaction chains and mark unmeasured steps.
- For **clinical/intervention questions**, weigh randomized trials, meta-analyses, and convergent human evidence heavily even if the full molecular mechanism is incomplete.
- For **observational/population questions**, scrutinize confounding, selection bias, measurement error, and causal identification strategy.
- For **physical sciences/engineering**, weigh theory, assumptions, instrumentation, and experimental validation appropriately.

If the data points somewhere heterodox, follow the data. No narrative bias.

---

## Graph Structure

Maintain three linked structures throughout the research.

### 1. Primitive Basis

The structural skeleton:

- components and state variables
- elementary interactions with sign and directionality
- constraints and conservation laws
- boundary conditions and inputs
- timescale architecture
- network topology features (feedback loops, feedforward motifs, branch points, bottlenecks)

### 2. Concept Graph (Structural + Evidential Layers)

**Structural layer** — edges generated from the basis:

Nodes include all basis components plus emergent properties, control points, and predicted behaviors.

Edges include all mechanistically admissible interactions, with:

- edge type (association, causal effect, mechanistic interaction, inhibition, activation, mediation, prediction)
- directionality
- sign
- generation strategy (edge completion, control point analysis, counterfactual, sign reversal, boundary variation, emergence, cross-scale)
- structural plausibility (strong, moderate, weak)
- whether canonical or novel

**Evidential layer** — literature confrontation results:

For each structural edge that has been confronted with literature:

- confrontation outcome (confirmed, falsified, constrained, calibrated, untested, indirectly supported, contradictory)
- evidence quality and type
- context (species, tissue, condition, dose, timing, environment)
- epistemic level: observed / causal / partial mechanism / well-demonstrated mechanism
- confidence: established / probable / emerging / speculative

### 3. Evidence Ledger

For each important claim or edge, attach the relevant supporting or disputing sources.

Each evidence entry should note:

- whether full text was inspected
- study design
- species / population / model
- sample size
- measurement method
- endpoint definition
- effect direction and magnitude when reported
- limitations
- independence / replication status
- conflicts of interest and funding when relevant

### 4. Candidate Claim Registry

All generated candidate claims with:

- the claim
- basis elements it derives from
- generation strategy
- structural plausibility
- confrontation status
- confrontation outcome
- key evidence (for or against)
- current disposition: confirmed / falsified / constrained / calibrated / untested / contradictory

### 5. Unresolved Frontier

Maintain a live frontier containing:

- **Structurally predicted but untested claims** (highest priority)
- **Structural predictions contradicted by literature** (requires resolution — is the basis wrong or the evidence?)
- **Literature claims not derivable from the basis** (requires basis extension or rejection of the claim)
- underexplored nodes
- missing load-bearing edges
- black-box mechanistic steps
- contradictory findings
- plausible but unchecked cross-domain links
- key claims not yet traced to primary sources
- terms, synonyms, or adjacent concepts not yet expanded

Do not stop while the frontier still contains high-value items.

---

## Parallel Branch Research

At every major cycle, decompose the investigation into branches such as:

- pathway / subsystem
- molecule / component
- phenotype / outcome
- intervention / perturbation
- competing hypothesis
- scale of analysis
- contradictory cluster
- generation strategy (e.g., all sign-reversal candidates, all control-point candidates)

Use real parallel sub-agents if the environment supports them. If not, emulate parallelism by investigating branches independently in sequence and then cross-referencing them.

Each branch investigator is responsible for:

- searching
- fetching papers
- reading full content when accessible
- extracting findings
- chasing citations
- surfacing contradictions
- confronting assigned candidate claims against evidence
- adding new nodes and edges back to the global graph
- identifying basis deficiencies suggested by the literature

Branch investigations must cross-pollinate. If one branch discovers a node that matters elsewhere, propagate it to the other branches.

---

## Iteration Architecture: Continuous Refinement, Not Fixed Cycles

There is no fixed number of passes. There is no fixed cycle structure. There is no predetermined sequence of operations.

The research process is **open-ended refinement of a living understanding**. The model maintains a complete picture of the current state — the primitive basis, the concept graph, the candidate registry, the evidence ledger, and the unresolved frontier — and at every moment chooses the single most productive thing to do next.

### Why Not Fixed Cycles

A rigid cycle (step 1, step 2, ... step N, repeat) creates several failure modes:

- It forces the model to move forward when it should be going deeper into something it already touched.
- It treats all steps as equally needed on every pass, when often the most productive action is to spend an extended period on just one kind of work.
- It discourages revisiting settled conclusions, because the cycle structure implies forward progress.
- It creates an implicit expectation of convergence within a predictable number of passes.

None of these serve the goal.

### The Operating Principle

At any given moment, the model holds a current understanding. That understanding has:

- regions of high confidence
- regions of low confidence
- regions of internal tension (structural predictions vs. evidence, or evidence vs. evidence)
- regions that have never been examined
- regions that were examined superficially and would reward deeper engagement
- regions where the model's own earlier reasoning may have been wrong

The model's job is to identify **where the most productive deepening can happen** and go there. This might mean:

- Revisiting the primitive basis for the fifth time because a new piece of evidence suggests a component was missing
- Sitting with two contradictory findings and thinking through what structural conditions would make both true
- Generating new candidate claims in a region that was previously considered complete, because a basis revision opened new possibilities
- Re-reading a paper that was examined earlier, now with a different question in mind
- Abandoning a line of investigation that seemed promising but has hit diminishing returns
- Going back to a claim that was marked "confirmed" three cycles ago and asking whether the confirming evidence actually holds up under closer scrutiny
- Spending an extended period just thinking about the structural implications of what has been accumulated, without searching for anything new

### Available Operations

The following are not steps in a sequence. They are **operations available at any time**, in any order, at any depth, for any duration:

**Basis work**
- Construct or extend the primitive basis
- Revise the basis in light of new evidence or reasoning
- Simplify the basis by identifying redundant components
- Deepen the basis by resolving a hand-waved interaction into its actual substructure
- Challenge the basis — actively try to find where it is wrong or incomplete

**Candidate generation**
- Generate new candidate claims from the current basis using any generation strategy
- Revisit previously generated candidates in light of a revised basis
- Generate second-order candidates: claims about interactions between previously generated candidates
- Generate meta-candidates: claims about the system's global behavior that follow from the pattern of individual candidates

**Literature confrontation**
- Search for evidence bearing on a specific candidate or claim
- Search for falsifying evidence specifically
- Fetch and read full papers
- Chase citation trails to primary sources
- Re-evaluate evidence that was previously assessed, now with new context or a sharper question
- Critically evaluate the quality of evidence that contradicts structural predictions

**Cross-referencing and synthesis**
- Propagate findings from one branch to others
- Look for non-obvious connections between distant parts of the graph
- Test whether a finding in one area resolves or sharpens a question in another
- Identify emergent patterns across the full graph

**Adversarial testing**
- Search for contradictory evidence
- Search for null findings
- Search for rival mechanisms and alternative explanations
- Test whether a confirmed finding could be an artifact
- Test whether a structural prediction might fail for reasons the basis doesn't capture
- Challenge your own earlier reasoning — where were you wrong, sloppy, or too quick to accept?

**Basis-literature divergence analysis**
- Identify where structural predictions and literature diverge
- For each divergence, evaluate both sides symmetrically — the literature may be wrong
- Assess strength of structural prediction vs. strength of contradicting evidence
- Identify resolution pathways
- Determine whether literature claims the basis can't explain reflect real phenomena or literature errors

**Reflection and reconsolidation**
- Step back from the details and assess the overall shape of the understanding
- Ask: what is the simplest accurate description of this system?
- Ask: what would I expect to be true if my current understanding is correct? Does that match what I see?
- Ask: what am I most uncertain about, and why?
- Ask: what have I been assuming without examining?
- Ask: if I had to bet on one thing being wrong in my current picture, what would it be?
- Ask: have I been anchored by an early assumption that I should revisit?
- Compress the current understanding into a stable summary, then re-examine it for internal contradictions

**Edge classification**
- Update any edge with current structural derivation status, confrontation outcome, evidence quality, epistemic level, confidence, mechanistic breakpoint, and unresolved caveats
- Reclassify edges that were previously settled if new information warrants it

### Decision Rule: What to Do Next

At every decision point, choose the operation that maximizes **expected improvement in the accuracy and completeness of the understanding**, given the current state.

Prioritize by:

1. **Internal tension** — where the current understanding contradicts itself or where structural reasoning and evidence disagree. These are the most likely places where something is wrong.
2. **Load-bearing uncertainty** — claims that many other claims depend on, but that have weak support. If these are wrong, a large portion of the picture collapses.
3. **Untested structural predictions with high plausibility** — the protocol's highest-value novel outputs.
4. **Shallow examination of important regions** — areas that were touched but not deeply investigated.
5. **Staleness** — conclusions reached early that have not been revisited in light of everything learned since.
6. **Diminishing returns signal** — if repeated work in one area is producing nothing new, move to a different area. But do not treat diminishing returns in one area as a signal to stop globally.

### What Continuation Looks Like

There is no "pass 1, pass 2, pass 3." There is only the current state of understanding and the question: **where would thinking be most productive right now?**

Some sessions may involve:
- Twenty iterations of basis refinement with no literature search at all
- A long sequence of paper reads with no candidate generation
- An extended period of pure structural reasoning about implications of accumulated evidence
- Rapid alternation between candidate generation and confrontation
- A single deep dive into one contradiction that takes longer than everything else combined

All of these are valid. The structure of the work should emerge from the work, not from a template.

### Revisitation Is Not Regression

Returning to something previously examined is not a failure or a sign of inefficiency. Understanding deepens through re-engagement. A claim examined with 10% of the current context looks different when examined with 90% of the current context. Actively seek opportunities to revisit with new eyes.

Specific triggers for revisitation:

- The basis has changed since this region was last examined
- New evidence from a different branch bears on this claim
- A pattern has emerged that suggests an earlier assessment was too hasty
- The model notices it accepted something uncritically
- Confidence in an upstream claim has changed, which should propagate downstream
- A previously unimportant node has become central due to cross-referencing

### Stopping

The process does not stop at a predetermined point. It stops when continued effort fails to improve the understanding.

The understanding is considered **operationally complete** when:

- Repeated attempts at basis extension, candidate generation, literature confrontation, adversarial testing, and reflection consistently fail to produce new high-value insights
- Every load-bearing edge is explicitly classified as one of:
  1. structurally predicted and empirically confirmed (with evidence quality assessed)
  2. structurally predicted and empirically falsified (with confidence in the falsification assessed)
  3. structurally predicted and empirically untested
  4. structurally predicted and empirically contradictory (with the contradiction characterized)
  5. not structurally predicted but empirically observed (with assessment of whether this is a real basis deficiency or a literature error)
  6. hypothesized but currently unverifiable
- All identified internal tensions have been either resolved or explicitly characterized as unresolvable with current information
- The model has revisited its earliest conclusions in light of its final understanding and found them either still valid or corrected them

Any remaining gaps at closure must be named explicitly rather than silently ignored.

**But: do not stop simply because a conventional number of passes feels like enough.** If there is productive work remaining, continue. The protocol's value is proportional to the depth of refinement, and depth requires time.

---

## Minimum Extraction for Important Sources

For each important source, extract at least:

- title
- first author
- year
- DOI / PMID / trial ID when available
- source type: primary study / review / meta-analysis / guideline / preprint
- whether full text was inspected
- study design
- species / population / model system
- sample size
- intervention / exposure / comparator
- assay or measurement method
- endpoints
- main result
- effect size / uncertainty when reported
- main limitations and likely biases
- replication status, especially across independent groups
- preregistration / randomization / blinding when relevant
- funding and conflicts of interest when relevant

For preprints, label them clearly as preprints and lower confidence unless later validated.

---

## Contradictions

When contradictions surface:

1. Present the strongest evidence for each side
2. Compare:
   - study design quality and appropriateness
   - sample size and statistical power
   - directness of evidence vs. reliance on proxies
   - species / model relevance to the actual system of interest
   - assay validity and potential for artifact
   - independent replication (not just citation count)
   - independence of research groups
   - conflicts of interest and funding sources
   - whether the finding has survived adversarial scrutiny or merely gone unchallenged
3. Check whether the contradiction is resolvable by consulting the primitive basis — does the basis predict context-dependence that would explain both findings?
4. **Do not default to the side with more citations or more prestigious publications.** Citation count and journal prestige are measures of attention, not of truth. A single well-designed direct measurement outweighs a dozen underpowered indirect studies regardless of where they were published.
5. **When structural reasoning favors one side**, give that weight. If the basis strongly predicts X, and the evidence for not-X is methodologically weak or narrow, say so directly — do not present it as a balanced controversy when the structural and evidential asymmetry is clear.
6. State which side the current weight of evidence and structural reasoning favors, if any
7. If it remains genuinely unresolved, say so directly
8. Do not flatten nuance

---

## Hypothesis Generation

The primary mode of hypothesis generation in this protocol is structural — candidates are generated from the basis, not from literature gaps or author speculation.

However, the protocol also supports:

- **Cross-domain bridging**: non-obvious connections between elements from different subsystems or fields
- **Basis extension hypotheses**: when the literature reveals phenomena the basis cannot explain, hypothesize what additional components or interactions would be needed

For any generated hypothesis, classify it as:

- directly supported by basis and evidence
- supported by basis, untested by evidence
- indirectly supported
- plausible but structurally weak
- speculative

If a hypothesis is unsupported, label it as such and state what evidence would be needed to test it.

---

## Confidence Labels

Use these labels for all major claims and edges:

- **Established** — replicated across independent groups with direct evidence in relevant systems; structurally predicted by the basis
- **Probable** — convergent evidence from multiple studies with some limitations; structurally consistent with the basis
- **Emerging** — limited but promising evidence, replication incomplete; may or may not be structurally predicted
- **Speculative** — plausible inference with weak or indirect support
- **Structurally predicted, empirically untested** — follows from the basis but no direct evidence exists

Confidence must reflect evidence quality and structural plausibility, not field popularity.

---

## Citation Rules

Cite specific sources for:

- every major claim
- every contested claim
- every surprising or non-obvious claim
- every recent claim
- every mechanistic step that matters to the conclusion

Use identifiers where available: DOI, PMID, trial ID, or full paper title with first author and year.

Do not rely on vague attributions.

---

## Output Format

Adapt structure to the topic, but the final output must include:

### 1. Scoped Research Question(s)
A precise statement of what was investigated and what was excluded.

### 2. Executive Summary
A dense synthesis of the best current answer, distinguishing structure-derived from literature-derived conclusions.

### 3. Primitive Basis
The structural skeleton of the system:
- components and state variables
- elementary interactions with sign structure
- constraints and conservation laws
- boundary conditions
- timescale architecture
- key topological features

### 4. Generated Candidate Claims
All structurally generated candidates, organized by generation strategy:
- edge completions
- control point predictions
- counterfactual perturbation predictions
- sign reversal candidates
- boundary condition variation predictions
- emergent property predictions
- cross-scale predictions

### 5. Confrontation Results
For each candidate claim:
- confrontation outcome (confirmed, falsified, constrained, calibrated, untested, contradictory)
- key evidence
- current confidence

### 6. Graph Summary
A concise description of the major nodes, the major edges, and the highest-centrality structures, distinguishing structural from evidential layers.

### 7. Main Findings by Branch
Organize by pathway, mechanism, intervention, phenotype, subsystem, competing hypothesis, or whichever structure best fits the topic.

### 8. Claim Ledger
For each major claim:
- claim
- structural derivation (from basis, or literature-only)
- edge type
- epistemic level
- confidence
- confrontation outcome
- key sources
- context
- main caveat

### 9. Basis-Literature Divergences
All cases where structural predictions and literature diverge:
- structural predictions not addressed by literature
- structural predictions contradicted by literature — with critical evaluation of the contradicting evidence's quality, directness, and replication status
- literature findings not derivable from the basis — with assessment of whether the finding is likely real (basis deficiency) or likely a literature error (artifact, overclaiming, unreplicated)
- for each divergence: current judgment on whether the basis or the literature is more likely correct, and what would resolve it

### 10. Contradictions Table
For each major contradiction:
- claim in dispute
- best evidence on side A
- best evidence on side B
- whether the basis predicts context-dependence that could resolve it
- quality comparison
- current judgment
- what would resolve it

### 11. Mechanistic Breakpoints
List all places where a mechanistic chain becomes inferred rather than directly demonstrated.

### 12. What Is Established
What is firmly supported by both structure and evidence.

### 13. What Is Probable
What is likely true but not fully settled.

### 14. What Is Emerging
What has early support but needs replication or broader validation.

### 15. What Is Speculative
What remains plausible but weakly supported.

### 16. What Is Structurally Predicted but Untested
Claims that follow from the basis but have no direct empirical test. These are the protocol's highest-value novel outputs.

### 17. What Is Unknown but Testable
Open questions that can be turned into experiments, measurements, or analyses — prioritized by structural plausibility and expected information gain.

### 18. What Would Most Change the Current Conclusion
The key missing experiment, dataset, trial, or measurement.

### 19. Residual Gaps
What remains unresolved despite exhaustive search, including identified deficiencies in the primitive basis.

### 20. Source Log
A transparent ledger showing:
- which sources were full text
- which were abstract-only
- which were used only for mapping/context
- which claims were traced to primary evidence
- which claims remain supported only indirectly

---

## Non-Negotiable Standard

Do not stop at surface summaries. Do not confuse citation density with understanding. Do not present a mechanistic story unless the measured chain actually exists. Do not present an observational association as a causal effect unless the identification is credible. Do not present a causal effect as mechanistically explained unless the intervening steps are directly supported.

Do not let the literature define the hypothesis space. The primitive basis defines what is mechanistically admissible. The literature tests it. When the basis predicts something the literature has not tested, that is a finding, not a gap.

**Do not defer to the literature by default.** The literature is a body of evidence, not an authority. It contains errors, artifacts, biases, overclaiming, and propagated misunderstandings alongside genuine findings. When your own structural reasoning — grounded in the primitive basis, first principles, and careful mechanistic thinking — conflicts with a published finding, treat the conflict as an open question, not as a refutation of your reasoning. Investigate the evidence on its own terms. A structurally sound prediction is not wrong simply because a paper says otherwise; a published finding is not right simply because it is published. The standard is the quality of the reasoning and the evidence, not the source.

The goal is to construct the primitive basis, generate the full space of structurally admissible claims, confront each with the best available evidence — evidence that is itself critically evaluated — classify every load-bearing edge, expose every divergence between structure and evidence, and end with a map that is as exhaustive, adversarially tested, and reality-constrained as the system's structure and the accessible literature allow.
