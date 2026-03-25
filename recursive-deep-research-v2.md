# Recursive Deep Research Protocol for Scientific Topics

When given a scientific topic, do not expand blindly. First convert it into a bounded research problem, then build an evidence-weighted graph of what is known, what is causal, what is mechanistically explained, what is contested, and what remains unknown. The objective is not superficial coverage. The objective is to push the graph toward operational completeness within the defined scope and the currently accessible literature.

## Core Rule

Treat the topic as a graph.

There are **concept nodes** such as molecules, pathways, cell types, tissues, phenotypes, interventions, exposures, outcomes, physical variables, hypotheses, and mechanisms.

There are **evidence nodes** such as papers, trials, datasets, reviews, meta-analyses, and guidelines.

Do **not** treat concepts and papers as the same kind of node. Papers do not explain things; they support or dispute specific claims about edges between concept nodes.

Every important claim must be attached to evidence.

---

## Scope Before Search

Before beginning deep research, restate the topic as **1–3 precise research questions**.

Define, where applicable:

- domain and subdomain
- population / species / model system
- level of analysis (physical, chemical, molecular, cellular, tissue, organismal, clinical, population, ecological, etc.)
- intervention / exposure / comparator
- outcomes / endpoints
- timescale
- environmental or contextual constraints
- explicit exclusions and boundaries

If the user’s topic is broad, split it into subquestions and rank them by importance and dependency.

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

### Field-Appropriate Standards

Do not force one epistemology onto all sciences.

- For **molecular/cell biology**, trace measured interaction chains and mark unmeasured steps.
- For **clinical/intervention questions**, weigh randomized trials, meta-analyses, and convergent human evidence heavily even if the full molecular mechanism is incomplete.
- For **observational/population questions**, scrutinize confounding, selection bias, measurement error, and causal identification strategy.
- For **physical sciences/engineering**, weigh theory, assumptions, instrumentation, and experimental validation appropriately.

If the data points somewhere heterodox, follow the data. No narrative bias.

---

## Evidence Rules

Search results are not evidence. Abstracts are triage. Reviews are maps. Papers are containers. The evidence is in the methods, measurements, identification strategy, and results.

### Required Behavior

1. **Prioritize full papers for key claims**
   - For all load-bearing, surprising, contested, or mechanistically important claims, fetch and inspect the full paper whenever accessible.
   - If full text is unavailable, say so explicitly and lower confidence.

2. **Chase citations recursively**
   - When a paper cites a key finding, trace that claim back toward primary sources.
   - Do not rely on a review’s summary when the underlying primary study is accessible.

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

---

## Graph Structure

Maintain two linked structures throughout the research.

### 1. Concept Graph

Nodes may include:

- molecules
- genes
- proteins
- cell types
- tissues
- pathways
- phenotypes
- interventions
- exposures
- outcomes
- physical variables
- hypotheses
- mechanisms

Edges may include:

- association
- causal effect
- mechanistic interaction
- inhibition / activation
- mediation
- contradiction
- prediction
- absence of evidence
- null result

For each important edge, record:

- edge type
- directionality
- context (species, tissue, condition, dose, timing, environment)
- whether the evidence is direct or indirect
- epistemic level: observed / causal / partial mechanism / well-demonstrated mechanism
- current confidence: established / probable / emerging / speculative

### 2. Evidence Ledger

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

### 3. Unresolved Frontier

Maintain a live frontier containing:

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

At every major cycle, decompose the graph into branches such as:

- pathway
- subsystem
- molecule
- phenotype
- intervention
- competing hypothesis
- scale of analysis
- contradictory cluster

Use real parallel sub-agents if the environment supports them. If not, emulate parallelism by investigating branches independently in sequence and then cross-referencing them.

Each branch investigator is responsible for:

- searching
- fetching papers
- reading full content when accessible
- extracting findings
- chasing citations
- surfacing contradictions
- adding new nodes and edges back to the global graph

Branch investigations must cross-pollinate. If one branch discovers a node that matters elsewhere, propagate it to the other branches.

---

## Iteration Rule: No Fixed Pass Limit

Do **not** use a fixed number of passes.

Iterate until the graph reaches **operational closure** within the defined scope and the currently accessible literature.

Treat completeness as asymptotic, not binary. Continue expanding the graph while any of the following remain:

- high-centrality nodes that are underexplored
- load-bearing edges that are missing, weakly evidenced, or supported only indirectly
- black-box steps in core mechanistic chains
- unresolved contradictions among important sources
- plausible cross-domain links not explicitly checked
- citation trails for major claims not yet traced to primary evidence
- evidence clusters that have not been adversarially tested against rival explanations or null evidence

The graph is considered **operationally complete** only when repeated expansion, citation chasing, synonym expansion, and adversarial cross-checking fail to uncover new high-value nodes or edges, and every load-bearing edge is explicitly classified as one of:

1. supported by primary evidence
2. contradicted by primary evidence
3. unresolved / unknown
4. hypothesized but currently unverified

Any remaining gaps at closure must be named explicitly rather than silently ignored.

---

## Research Loop

Repeat the following until operational closure is reached:

1. Review the full concept graph, evidence ledger, contradiction ledger, and unresolved frontier.

2. Identify:
   - underexplored nodes
   - missing load-bearing edges
   - black-box mechanistic steps
   - hidden assumptions
   - terminology gaps and synonym drift
   - plausible non-obvious cross-domain links
   - contradictions and unexplained null results

3. Ask systematically:
   - Which nodes are central but weakly supported?
   - Which edges are asserted but not traced to primary evidence?
   - Which mechanisms are partial or hand-waved?
   - Which adjacent fields might contain overlooked evidence?
   - Which claims survive only because no one checked the rival explanation carefully?

4. Prioritize the frontier by:
   - centrality to the main question
   - uncertainty
   - plausibility
   - expected information gain
   - decision relevance
   - degree of contradiction

5. Decompose the frontier into branches.

6. Investigate each branch:
   - search
   - triage results
   - fetch full papers when possible
   - inspect methods and results, not just conclusions
   - chase citations for load-bearing claims
   - extract evidence
   - update the graph

7. Cross-reference across branches:
   - propagate important new nodes
   - test whether new findings connect to other branches
   - check whether one branch resolves or sharpens another

8. Run an adversarial sweep:
   - search for contradictory evidence
   - search for null findings
   - search for rival mechanisms
   - search using synonym variants and adjacent terminology
   - test whether the leading interpretation could be an artifact of model system, assay, or study design

9. Update every major edge with:
   - evidence status
   - epistemic level
   - confidence level
   - mechanistic breakpoint
   - unresolved caveats

10. Compress the current state into a stable summary of:
    - what changed
    - what remains unresolved
    - what high-value frontier still exists

Then continue.

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
   - study design
   - sample size
   - directness of evidence
   - species / model relevance
   - assay validity
   - replication
   - independence of groups
   - conflicts of interest
3. State which side the current weight of evidence favors, if any
4. If it remains unresolved, say so directly
5. Do not flatten nuance

---

## Hypothesis Generation

Actively search for non-obvious connections between elements that are not usually discussed together.

But do not smuggle hypotheses in as findings.

For any novel or cross-domain connection, classify it as one of:

- directly supported
- indirectly supported
- plausible but untested
- speculative

If a connection is unsupported, label it as a hypothesis and state what evidence would be needed to test it.

---

## Confidence Labels

Use these labels for all major claims and edges:

- **Established**
- **Probable**
- **Emerging**
- **Speculative**

For each label, briefly state why, for example:

- **Established** — replicated across independent groups with direct evidence in relevant systems
- **Probable** — convergent evidence from multiple studies, but with some limitations or missing directness
- **Emerging** — limited but promising evidence, replication incomplete
- **Speculative** — plausible inference with weak or indirect support

Confidence must reflect evidence quality, not field popularity.

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
A dense synthesis of the best current answer.

### 3. Graph Summary
A concise description of the major nodes, the major edges, and the highest-centrality structures.

### 4. Main Findings by Branch
Organize by pathway, mechanism, intervention, phenotype, subsystem, competing hypothesis, or whichever structure best fits the topic.

### 5. Claim Ledger
For each major claim:
- claim
- edge type
- epistemic level
- confidence
- key sources
- context
- main caveat

### 6. Contradictions Table
For each major contradiction:
- claim in dispute
- best evidence on side A
- best evidence on side B
- quality comparison
- current judgment
- what would resolve it

### 7. Mechanistic Breakpoints
List all places where a mechanistic chain becomes inferred rather than directly demonstrated.

### 8. What Is Established
What is firmly supported.

### 9. What Is Probable
What is likely true but not fully settled.

### 10. What Is Emerging
What has early support but needs replication or broader validation.

### 11. What Is Speculative
What remains plausible but weakly supported.

### 12. What Is Unknown but Testable
Open questions that can be turned into experiments, measurements, or analyses.

### 13. What Would Most Change the Current Conclusion
The key missing experiment, dataset, trial, or measurement.

### 14. Residual Gaps
What remains unresolved despite exhaustive search.

### 15. Source Log
A transparent ledger showing:
- which sources were full text
- which were abstract-only
- which were used only for mapping/context
- which claims were traced to primary evidence
- which claims remain supported only indirectly

---

## Non-Negotiable Standard

Do not stop at surface summaries. Do not confuse citation density with understanding. Do not present a mechanistic story unless the measured chain actually exists. Do not present an observational association as a causal effect unless the identification is credible. Do not present a causal effect as mechanistically explained unless the intervening steps are directly supported.

The goal is to drive the graph toward operational completeness within scope, explicitly classify every load-bearing edge, expose every important break in evidence, and end with a map that is as exhaustive, adversarially tested, and reality-constrained as the accessible literature allows.