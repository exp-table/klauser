# Initialize Deep Research Session (v4 Protocol)

You are setting up a research workspace for the Recursive Deep Research Protocol v4. Follow these instructions exactly.

## Step 1: Get the topic

The topic should be provided by the user alongside this prompt (e.g., `@init-research.md mitochondrial dysfunction in ALS`).

If no topic was provided, use **AskUserQuestion** as a fallback:

```
AskUserQuestion({
  questions: [{
    question: "What scientific topic do you want to investigate?",
    header: "Topic",
    options: [
      { label: "Enter your topic", description: "Type your research topic in the text field" }
    ],
    multiSelect: false
  }]
})
```

Otherwise, take the topic directly from the user's message and proceed immediately.

## Step 2: Create the workspace

Sanitize the topic into a short directory name (lowercase, hyphens, no special characters). Create the following structure under `research/<topic-name>/`:

```
research/<topic-name>/
  PROTOCOL.md          -> symlink or copy of recursive-deep-research-v4.md
  run.md               -> prompt to start the research
  continue.md          -> prompt to continue from where the last session stopped
  loop.md              -> instructions for looped/scheduled execution
  status.md            -> current progress, next steps (updated every stop)
  scope.md             -> scoped research questions and boundaries
  basis.md             -> primitive basis
  candidates.md        -> candidate claim registry
  graph-summary.md     -> concept graph (structural + evidential layers)
  evidence-ledger.md   -> evidence entries per source
  frontier.md          -> unresolved frontier
  divergences.md       -> basis-literature divergences
  contradictions.md    -> contradictions table
  cycle-log.md         -> compressed cycle history
  sources/             -> individual paper/source notes
  output/              -> final deliverables
```

## Step 3: Initialize each state file

Use the templates below. Each file should be ready to receive structured data — not empty, but with the correct headers and format so the protocol can write into them immediately.

### status.md
```markdown
# Research Status

**Topic**: [user's topic]
**Status**: NOT STARTED
**Operational closure estimate**: 0%
**Last updated**:

## Current state
Not yet started. Run run.md to begin.

## Next steps
1. Construct primitive basis (Phase 1)
2. Generate candidate claims (Phase 2)
3. Begin literature confrontation and continuous refinement

## Open questions / blockers
None yet.
```

### scope.md
```markdown
# Scoped Research Questions

**Topic**: [user's topic]
**Date initiated**: [today's date]

## Research Questions
<!-- 1-3 precise questions, filled during Phase 0 -->

## Boundaries
- **Domain**:
- **Population / species / model system**:
- **Level of analysis**:
- **Intervention / exposure / comparator**:
- **Outcomes / endpoints**:
- **Timescale**:
- **Environmental / contextual constraints**:
- **Explicit exclusions**:
```

### basis.md
```markdown
# Primitive Basis

<!-- The structural skeleton of the system. Built from first principles, not from literature. -->

## Components
<!-- Entities that carry or transform state variables -->

## State Variables
<!-- Quantities that define system state -->

## Interactions
<!-- Elementary operations: binding, catalysis, transport, signaling, etc. -->
<!-- For each: note sign (activating/inhibiting), directionality, and conditions -->

## Constraints
<!-- Conservation laws, thermodynamic limits, stoichiometric requirements, physical laws -->

## Boundary Conditions
<!-- External inputs, environmental variables, what is held constant vs. variable -->

## Timescale Architecture
<!-- Characteristic rates, timescale separations, effective modularity -->

## Network Topology
<!-- Feedback loops, feedforward motifs, branch points, bottlenecks, hubs -->

## Basis Revision Log
| Date | Revision | Reason | Affected regions |
|------|----------|--------|-----------------|
```

### candidates.md
```markdown
# Candidate Claim Registry

<!-- Claims generated from the primitive basis. Do NOT consult literature during generation. -->

## Edge Completions
| ID | Claim | Basis elements | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|---------------|-------------|---------------------|---------|-------|

## Control Point Predictions
| ID | Claim | Control node | Perturbation type | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|-------------|-------------------|-------------|---------------------|---------|-------|

## Counterfactual Perturbations
| ID | Claim | Edge/constraint perturbed | Predicted effect | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|--------------------------|-----------------|-------------|---------------------|---------|-------|

## Sign Reversal Candidates
| ID | Claim | Interaction | Canonical sign | Reversal context | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|------------|---------------|-----------------|-------------|---------------------|---------|-------|

## Boundary Condition Variations
| ID | Claim | Variable varied | Predicted effect | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|----------------|-----------------|-------------|---------------------|---------|-------|

## Emergent Property Predictions
| ID | Claim | Topology basis | Predicted behavior | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|---------------|-------------------|-------------|---------------------|---------|-------|

## Cross-Scale Predictions
| ID | Claim | Scales bridged | Mechanism | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|---------------|-----------|-------------|---------------------|---------|-------|

## Second-Order / Meta Candidates
| ID | Claim | Derived from | Plausibility | Confrontation status | Outcome | Notes |
|----|-------|-------------|-------------|---------------------|---------|-------|
```

### graph-summary.md
```markdown
# Concept Graph

## Structural Layer
<!-- Edges generated from the basis -->

### Major Nodes
| Node | Type | Centrality | Status |
|------|------|-----------|--------|

### Major Edges (Structure-Derived)
| From | To | Edge type | Sign | Generation strategy | Plausibility | Notes |
|------|----|-----------|------|--------------------|--------------| ------|

## Evidential Layer
<!-- Literature confrontation results mapped onto structural edges -->

### Confronted Edges
| Edge | Confrontation outcome | Evidence quality | Epistemic level | Confidence | Key source | Context |
|------|-----------------------|-----------------|-----------------|------------|------------|---------|

## Highest-Centrality Structures
<!-- Subgraphs, motifs, or clusters that are load-bearing for the main questions -->
```

### evidence-ledger.md
```markdown
# Evidence Ledger

<!-- For each important source. One entry per source. -->

## Sources

### [Source ID]: [Short label]
- **Title**:
- **First author**:
- **Year**:
- **DOI / PMID / Trial ID**:
- **Source type**: primary study / review / meta-analysis / guideline / preprint
- **Full text inspected**: yes / no / abstract only
- **Study design**:
- **Species / population / model**:
- **Sample size**:
- **Intervention / exposure / comparator**:
- **Assay / measurement method**:
- **Endpoints**:
- **Main result**:
- **Effect size / uncertainty**:
- **Limitations and likely biases**:
- **Replication status**:
- **Independence**: same group as [X] / independent
- **Preregistration / randomization / blinding**:
- **Funding / COI**:
- **Literature pathology flags**: none / cascade citation / model lock-in / assay artifact / narrative capture / overclaiming / zombie finding
- **Claims supported**:
- **Claims disputed**:
```

### frontier.md
```markdown
# Unresolved Frontier

<!-- Ranked by priority. Updated every cycle. -->

## Critical Priority
<!-- Structurally predicted but untested; basis-literature conflicts; load-bearing uncertainties -->

| Item | Type | Priority rationale | Assigned cycle |
|------|------|--------------------|---------------|

## High Priority
<!-- Underexplored high-centrality nodes; black-box mechanistic steps; unresolved contradictions -->

| Item | Type | Priority rationale | Assigned cycle |
|------|------|--------------------|---------------|

## Standard Priority
<!-- Cross-domain links; synonym expansions; citation trails not yet chased -->

| Item | Type | Priority rationale | Assigned cycle |
|------|------|--------------------|---------------|

## Resolved (Archive)
<!-- Items moved here when resolved, with resolution note -->

| Item | Resolution | Cycle resolved |
|------|-----------|---------------|
```

### divergences.md
```markdown
# Basis-Literature Divergences

## Structural Predictions Not Addressed by Literature
| Prediction | Basis elements | Plausibility | Search attempts | Status |
|-----------|---------------|-------------|----------------|--------|

## Structural Predictions Contradicted by Literature
| Prediction | Contradicting evidence | Evidence quality assessment | Structural prediction strength | Current judgment (basis vs. literature) | Resolution pathway |
|-----------|----------------------|---------------------------|-------------------------------|----------------------------------------|-------------------|

## Literature Claims Not Derivable from Basis
| Claim | Source(s) | Evidence quality | Assessment (real phenomenon vs. literature error) | If real: what basis extension needed | Status |
|-------|----------|-----------------|--------------------------------------------------|-------------------------------------|--------|
```

### contradictions.md
```markdown
# Contradictions Table

| Claim in dispute | Side A evidence | Side B evidence | Basis predicts context-dependence? | Quality comparison | Structural reasoning favors | Current judgment | What would resolve it |
|-----------------|----------------|----------------|-----------------------------------|-------------------|---------------------------|-----------------|----------------------|
```

### cycle-log.md
```markdown
# Cycle Log

<!-- Compressed history of every cycle. This is the memory that allows a new conversation to pick up where the last one left off. -->

## Cycle 1
- **Date**:
- **Operations performed**:
- **Basis changes**:
- **New candidates generated**:
- **Confrontation results**: confirmed: / falsified: / constrained: / untested:
- **Divergences identified**:
- **Frontier changes**:
- **Key insight**:
- **What remains highest priority**:
```

### sources/ directory
Create this as an empty directory. Individual source notes will be written here as `sources/<source-id>.md` during literature confrontation.

### output/ directory
Create this as an empty directory. Final deliverables (the 20-section output format) will be written here.

## Step 4: Create the run and continue prompts

Create two prompt files in the research directory:

### research/<topic-name>/run.md
```markdown
Read @recursive-deep-research-v4.md — this is your operating protocol.

You are beginning a deep research session on the topic defined in scope.md.

## Bootstrap

Read all state files in this directory:
- scope.md
- basis.md
- candidates.md
- graph-summary.md
- evidence-ledger.md
- frontier.md
- divergences.md
- contradictions.md
- cycle-log.md

If the basis is empty, you are starting fresh. Begin with Phase 1 (Primitive Basis Construction), then Phase 2 (Candidate Generation), then move into the continuous refinement loop.

If the basis is populated, you are continuing. Read cycle-log.md to understand what has been done. Pick up from wherever the most productive work is, per the protocol's decision rule.

## Autonomy rules

**You are autonomous. Do not pause between cycles. Do not ask for permission to continue. Do not summarize and wait. Just keep working.**

After completing one unit of work, immediately identify the next most productive operation and execute it. The only reasons to stop are:

1. **Operational closure** — the protocol's stopping criteria are met
2. **Hard context limit** — you are running out of context and must dump state before you lose it

If you are approaching context limits, write all current state to files, append a detailed cycle-log entry with explicit next steps, and write a file called `status.md` with:
- current overall progress (percentage estimate of operational closure)
- what was just completed
- what should happen next, in priority order
- any open questions or blockers

**Do not wind down gradually.** Work at full intensity until you either reach closure or must stop for context reasons.

## State management rules

- After every meaningful unit of work, write the updated state back to the relevant file(s). Do not accumulate unsaved state.
- After each cycle or major milestone, append a cycle entry to cycle-log.md.
- When you create a source entry, write it to both evidence-ledger.md and sources/<source-id>.md.
- When you resolve a frontier item, move it to the Resolved archive in frontier.md.
- When the basis changes, log the revision in the Basis Revision Log table.
- Always update status.md before stopping for any reason.

## Parallelism

- When decomposing the frontier into branches, use the Agent tool to spawn parallel sub-agents for independent branches.
- Each sub-agent should be given: the protocol reference, the branch assignment, the current basis, and the relevant subset of candidates.
- Sub-agent results must be integrated back into the global state files.
- Prefer launching multiple agents in parallel over sequential investigation when branches are independent.
```

### research/<topic-name>/continue.md
```markdown
Read @recursive-deep-research-v4.md — this is your operating protocol.

You are continuing a research session that was previously started. Another instance of you has already done work on this topic. Your job is to pick up exactly where it left off and keep going.

## Bootstrap

Read these files in order:
1. status.md — what just happened and what should happen next
2. cycle-log.md — full history of all work done
3. scope.md — the research questions and boundaries
4. basis.md — current primitive basis
5. frontier.md — what remains unresolved
6. candidates.md — all generated candidates and their confrontation status
7. graph-summary.md — current concept graph
8. evidence-ledger.md — all evidence collected
9. divergences.md — basis-literature conflicts
10. contradictions.md — unresolved contradictions

## Autonomy rules

**You are autonomous. Do not pause between cycles. Do not ask for permission to continue. Do not summarize and wait. Just keep working.**

Follow the same autonomy rules, state management rules, and parallelism rules as run.md.

Start from whatever status.md says is highest priority. If status.md doesn't exist, use cycle-log.md and the protocol's decision rule to determine where to begin.

**Do not re-derive work that has already been done.** Trust the state files. If the basis is built, don't rebuild it. If candidates are generated, don't regenerate them. Read what exists and push forward from there.

**Do not wind down gradually.** Work at full intensity until you either reach closure or must stop for context reasons.
```

### research/<topic-name>/loop.md
```markdown
This file configures automatic continuation of the research session.

To run this research in a continuous loop using Claude Code, use:

    /loop 2m @research/<topic-name>/continue.md

This will:
- Re-invoke the continue prompt every 2 minutes
- Each invocation reads state files, picks up where the last left off, works until context limits, dumps state, and exits
- The next invocation picks up from the new state

Adjust the interval based on how long each session runs. If sessions are running for several minutes of active work, a longer interval (5m, 10m) avoids overlap. If they're short, 2m keeps momentum.

To stop the loop, press Ctrl+C or type /stop.

For fully unattended research (e.g., overnight), use scheduled triggers:

    /schedule create --name "<topic>-research" --cron "*/10 * * * *" --prompt "Read @research/<topic-name>/continue.md and execute it"

This runs a fresh agent every 10 minutes. Each agent reads state, works, writes state, exits. The next agent continues.

To check on progress at any time, read:
- research/<topic-name>/status.md — current state and next steps
- research/<topic-name>/cycle-log.md — full history
- research/<topic-name>/frontier.md — what remains
```

## Step 5: Scope the research (autonomous)

**Do not ask the user scoping questions.** Infer all scoping parameters from the topic itself.

From the topic, determine:

1. **Research questions** — formulate 1-3 precise questions that capture the core of what the topic demands
2. **Domain and subdomain** — infer from the topic's subject matter
3. **Population / species / model system** — infer the most relevant systems (human, mouse, in vitro, etc.)
4. **Level of analysis** — infer the appropriate scales (molecular, cellular, tissue, organismal, clinical, population)
5. **Interventions / exposures / comparators** — infer from the topic, or mark as "broadly exploratory" if the topic is open-ended
6. **Outcomes / endpoints** — infer from the research questions
7. **Timescale** — infer from the biology or physics of the system
8. **Environmental / contextual constraints** — infer or leave open
9. **Exclusions** — set reasonable boundaries to prevent scope creep; mark as "inferred, user may revise"

Write all of this into scope.md. Mark every inferred field with `(inferred)` so the user can review and override if needed.

The user can always edit scope.md directly to adjust boundaries — but the default is to start working immediately, not to interrogate.

## Step 6: Start immediately

After creating all files and writing scope.md, **do not ask for confirmation**. Immediately begin executing the research protocol:

1. Read `recursive-deep-research-v4.md` (the protocol)
2. Read all state files
3. Begin Phase 1 (Primitive Basis Construction)

The workspace is set up and the research is running. The user can:

- Watch it work in real time
- Interrupt at any point to adjust scope, add constraints, or redirect
- Review `scope.md` to check or revise the inferred boundaries
- Continue later with `@research/<topic-name>/continue.md`
- Set up looping with `/loop 2m @research/<topic-name>/continue.md`
- Set up unattended scheduled runs with `/schedule`
- Monitor progress via `status.md`, `cycle-log.md`, or `frontier.md` at any time
