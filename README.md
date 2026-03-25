# Recursive Deep Research Prompts

A collection of system prompts designed to drive AI-assisted scientific research beyond surface-level literature summaries. Each version builds on the last, progressively shifting from literature-driven exploration toward structure-first reasoning.

These prompts are intended for use with LLMs that have access to web search, paper fetching, and parallel sub-agent capabilities (e.g., Claude Code with WebFetch/WebSearch and Agent tools).

## Versions

### v1 — `recursive-deep-research.md`

**Literature-driven graph expansion.**

The original prompt. Treats a research topic as an expanding graph of nodes (molecules, pathways, phenotypes, studies) and edges (connections between them). Runs 5 fixed passes, each reviewing the full graph, identifying gaps, and spawning parallel sub-agents to search and read papers.

Key characteristics:
- **Fixed 5-pass loop** — each pass reviews the graph, identifies under-explored areas, spawns agents, and integrates findings
- **Paper consumption rules** — mandates fetching and reading full papers (not just abstracts/snippets), chasing citations recursively, and extracting methodology details (sample size, species, replication status, conflicts of interest)
- **Parallel agent teams** — decomposes the graph into branches and assigns one agent per branch
- **Confidence tagging** — established / probable / emerging / speculative, with justification for each
- **Flexible output structure** — adapts to the topic rather than forcing a rigid template

Best for: Broad exploratory research where you want thorough literature coverage on a topic.

---

### v2 — `recursive-deep-research-v2.md`

**Epistemologically rigorous literature-driven research.**

A major expansion that adds formal epistemic structure to the research process. Introduces the distinction between concept nodes and evidence nodes, requires scoping research questions before searching, and replaces the fixed 5-pass loop with iteration until "operational closure."

Key additions over v1:
- **Scope before search** — restate the topic as 1-3 precise research questions with defined population, level of analysis, timescale, and exclusions
- **Epistemic distinctions** — observed (association) vs. causal vs. mechanistic, tracked separately per claim
- **Mechanistic discipline** — traces mechanistic chains step by step, marks exactly where direct measurement ends and inference begins
- **Dual graph structure** — concept graph + evidence ledger, maintained as linked structures
- **Unresolved frontier** — a live list of under-explored nodes, missing edges, black-box steps, and contradictions that drives iteration
- **No fixed pass limit** — iterates until operational closure (repeated expansion fails to uncover new high-value items and every load-bearing edge is classified)
- **Adversarial sweep** — each cycle includes explicit search for contradictory evidence, null findings, rival mechanisms, and synonym variants
- **Structured output format** — 15 required sections including claim ledger, contradictions table, mechanistic breakpoints, and source log with inspection-level transparency

Best for: Deep investigation of a specific scientific question where epistemic rigor matters — you need to know not just what the literature says, but how strong the evidence actually is.

---

### v3 — `recursive-deep-research-v3.md`

**Structure-first scientific investigation.**

The fundamental paradigm shift. Instead of starting from literature and building outward, v3 starts by constructing a "primitive basis" — a first-principles structural model of the system — and then generates candidate claims from that structure *before* consulting any literature. Literature becomes a tool for testing structural predictions, not the source of hypotheses.

Key additions over v2:
- **Primitive basis construction** (Phase 1) — builds a minimal structural skeleton from first principles: state variables, components, interactions, constraints, boundary conditions, timescales, and sign structure
- **Candidate generation from structure** (Phase 2) — seven generation strategies produce claims the system's structure permits but that may never have been studied:
  1. Edge completion (missing direct connections)
  2. Control point identification (topologically influential nodes)
  3. Counterfactual perturbations (what if this edge were removed/reversed?)
  4. Alternative sign structures (context-dependent sign reversal)
  5. Boundary condition variation (extreme/unusual inputs)
  6. Emergent properties (oscillations, bistability, failure modes)
  7. Cross-scale bridging (how phenomena at one scale constrain another)
- **Literature confrontation** (Phase 3) — literature is used to falsify, constrain, calibrate, or confirm structural predictions, not to define the hypothesis space
- **Basis-literature divergence analysis** — treats conflicts between structural predictions and published findings as *symmetric* (the literature may be wrong), with systematic evaluation of both sides
- **Literature pathology screening** — actively watches for cascade citation, model system lock-in, assay artifacts, narrative capture, survivorship bias, overclaiming, and zombie findings
- **Candidate claim registry** — tracks every generated claim through confrontation with its structural derivation, plausibility, and disposition
- **New confidence level** — "structurally predicted, empirically untested" — the protocol's highest-value novel outputs
- **20-section output format** — adds primitive basis, generated candidates, confrontation results, basis-literature divergences, and structurally predicted but untested claims

Best for: Generating genuinely novel research hypotheses and identifying blind spots in existing literature. Especially powerful for well-characterized systems where first-principles reasoning can outrun what has been published.

---

### v4 — `v4/recursive-deep-research-v4.md` + `v4/init-research.md`

**Continuous refinement without fixed cycles. Persistent state. Runs indefinitely.**

Builds on v3's structure-first approach but replaces the structured research loop with a fully open-ended iteration architecture and adds a full workspace scaffolding system. This is the only version that survives across conversations and can run unattended.

**Requires setup.** Run `@init-research.md`, give it your topic, and it creates a `research/<topic>/` directory with 10+ templated state files plus `run.md`, `continue.md`, and `loop.md` prompts. Start with `@research/<topic>/run.md`.

#### Generated workspace structure

```
research/<topic>/
  PROTOCOL.md          # copy of recursive-deep-research-v4.md
  run.md               # prompt to start research (reads all state, begins working)
  continue.md          # prompt to continue from where last session stopped
  loop.md              # instructions for looped/scheduled execution
  status.md            # current progress + handoff notes (updated every stop)
  scope.md             # scoped research questions and boundaries
  basis.md             # primitive basis (structural skeleton)
  candidates.md        # candidate claim registry (7 generation strategy tables)
  graph-summary.md     # concept graph (structural + evidential layers)
  evidence-ledger.md   # evidence entries per source
  frontier.md          # unresolved frontier (ranked by priority)
  divergences.md       # basis-literature divergences
  contradictions.md    # contradictions table
  cycle-log.md         # compressed cycle history (the cross-session memory)
  sources/             # individual paper/source notes
  output/              # final deliverables
```

#### How it runs

The model works autonomously — no pausing, no asking permission, no summarizing and waiting. It writes all state to files as it goes. When context runs out, it dumps a `status.md` handoff with progress estimate, what was just completed, and prioritized next steps.

Three ways to run it:

1. **Manual** — `@research/<topic>/run.md` to start, `@research/<topic>/continue.md` to pick up later
2. **Looping** — `/loop 2m @research/<topic>/continue.md` for automatic continuation every 2 minutes
3. **Scheduled (unattended)** — `/schedule` for overnight or long-running research on a cron

Each invocation reads state files, works until context limits, writes state, exits. The next invocation picks up from the new state. This means research can run indefinitely across arbitrarily many conversations.

#### Key changes from v3

- **No fixed cycle structure** — eliminates the step 1 through step 10 loop entirely. The research process becomes a continuous assessment of "where would thinking be most productive right now?"
- **Operations, not steps** — all research activities (basis work, candidate generation, literature confrontation, cross-referencing, adversarial testing, reflection, edge classification) are available at any time, in any order, at any depth
- **Explicit anti-patterns for fixed cycles** — explains why rigid cycles fail: they force forward movement when depth is needed, treat all steps as equally needed, discourage revisiting settled conclusions, and create false convergence expectations
- **Decision rule** — at every decision point, choose the operation that maximizes expected improvement in accuracy and completeness, prioritized by: internal tension, load-bearing uncertainty, untested structural predictions, shallow examination, and staleness
- **Revisitation as a feature** — explicitly encourages returning to previously examined claims with new context. "A claim examined with 10% of the current context looks different when examined with 90%"
- **Reflection and reconsolidation** — adds metacognitive operations: "What am I most uncertain about? What have I been assuming without examining? If I had to bet on one thing being wrong, what would it be?"
- **File-based state persistence** — all research state lives in structured markdown files, enabling cross-session continuity, manual inspection/editing, and unattended execution
- **Autonomous execution model** — works at full intensity until operational closure or context exhaustion, then writes a clean handoff

Best for: Serious, extended research campaigns where you want depth that exceeds a single conversation. The only version suitable for overnight/unattended runs or research that spans days.

## Evolution Summary

| | v1 | v2 | v3 | v4 |
|---|---|---|---|---|
| **Starting point** | Literature | Literature | First principles | First principles |
| **Hypothesis source** | Literature gaps | Literature gaps | Structural reasoning | Structural reasoning |
| **Iteration** | Fixed 5 passes | Until closure (structured loop) | Until closure (structured loop) | Until closure (open-ended) |
| **State persistence** | None (single conversation) | None (single conversation) | None (single conversation) | File-based (survives across conversations) |
| **Setup** | Standalone prompt | Standalone prompt | Standalone prompt | `init-research.md` scaffolds a workspace |
| **Execution modes** | Manual | Manual | Manual | Manual / looping / scheduled |
| **Epistemic tracking** | Confidence tags | Observed/causal/mechanistic | + structure-derived vs. literature-derived | Same as v3 |
| **Literature stance** | Trusted source | Critically evaluated source | Evidence to test predictions against | Same as v3 |
| **Novel output** | Synthesis of known | Gaps and contradictions | Structurally predicted but untested claims | Same as v3 |
| **Complexity** | ~50 lines | ~480 lines | ~800 lines | ~800 lines + ~450 lines scaffolding |
