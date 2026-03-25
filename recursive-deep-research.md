# Recursive Deep Research Protocol

When given a topic, explore it as an expanding graph where every piece of information is a node — a molecule, a pathway, a phenotype, a study result, a clinical observation — and your job is to discover every edge between them. Execute **5 passes**. Each pass: review the full graph, identify under-explored nodes and missing connections, then dig into those. You decide what each pass focuses on based on what the previous pass revealed. Actively search for non-obvious connections between elements that aren't usually discussed together.

## First Principles

Reason from evidence upward. Never import a conclusion because it is "widely accepted." For every claim, ask: **what was actually measured vs. inferred?** If a mechanism is assumed but not directly demonstrated, flag it. If data points somewhere heterodox, follow the data. No narrative bias.

## Agent Teams

You MUST use parallel sub-agents for research. At the start of each pass:
- Decompose the current graph into branches (e.g., by pathway, by molecule, by system)
- Spawn one agent per branch, running in parallel
- Each agent is responsible for: searching, fetching full papers, extracting findings, and chasing citations

This is not optional. A single-threaded search loop will always be too shallow.

## Paper Consumption Rules

**Search results are NOT evidence. Papers are evidence.** You must:
1. **Fetch and read full papers** (via WebFetch on PMC/journal URLs) — not just search result snippets or abstracts. The abstract tells you the conclusion; the methods and results tell you whether to believe it.
2. **Chase citations recursively.** When a paper cites a key finding, fetch that cited paper too. A claim is only as strong as its primary source, not the review that summarizes it.
3. **Minimum consumption**: each agent, each pass, should fetch and read at least 3-5 full papers. Across all agents per pass, aim for 15-30 papers consumed per pass. Skimming search results does not count.
4. **Extract from papers**: sample sizes, methodology, species (mouse vs. human), replication status, year, conflicts of interest. These details determine confidence — they cannot be skipped.
5. **bioRxiv/medRxiv limitation**: these tools only filter by category + date (no keyword search). Search multiple adjacent categories (immunology, cell biology, molecular biology, physiology, developmental biology, endocrinology, systems biology) and filter results yourself.

## The Loop

```
for each pass (1 through 5):
  1. Review all accumulated knowledge — treat it as a graph of nodes and edges
  2. Identify: under-explored nodes, missing edges, black-box steps, unverified assumptions
  3. For every pair of nodes, ask: is there a connection I haven't checked? Prioritize non-obvious cross-domain edges
  4. Choose the highest-value targets for this pass (you decide — mechanisms, cross-domain links, contradictions, gaps, whatever the graph needs most)
  5. Spawn parallel agents — one per branch — each searching AND reading full papers
  6. Each agent: search → fetch top papers → read full content → extract citations → fetch cited papers → report findings
  7. Cross-reference across agents: if one agent reveals a node others missed, other agents search for it in subsequent passes
  8. Integrate all agent findings, update the graph, note contradictions and confidence levels
```

When contradictions surface: present evidence for each side, assess study quality (sample size, species, methodology, replication, conflicts of interest), and state which the weight of evidence favors — or state honestly that it's unresolved. Do not flatten nuance.

## Output

- Structure adapts to topic. Choose whatever communicates clearest: outline, narrative, relationship map, or hybrid.
- Cite specific sources (DOI, trial ID, paper title + first author + year) for major claims, novel findings, and contested points. Common knowledge needs no citation.
- Tag confidence: **established** / **probable** / **emerging** / **speculative**.
- For each confidence tag, briefly note WHY: (e.g., "established — replicated in 3 independent mouse studies + 1 human cohort" or "emerging — single 2025 preprint, n=12 mice, no replication").
- Final pass must synthesize: what is firm, what is probable, what is contested, what is unknown but testable.
