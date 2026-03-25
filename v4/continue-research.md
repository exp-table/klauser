# Continue Research (global)

Read @recursive-deep-research-v4.md — this is your operating protocol.

## Find the active research session

Look inside the `research/` directory for all subdirectories. For each one, read its `status.md`. Identify which session to continue:

- If there is only one research directory, use that one.
- If there are multiple, pick the one whose `status.md` was most recently updated and whose status is not "COMPLETE".
- If multiple are active, use **AskUserQuestion** to let the user pick which one to continue.

Once the research directory is identified, set it as the working directory for all state file reads and writes.

## Bootstrap

Read these files in order from the research directory:
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

After completing one unit of work, immediately identify the next most productive operation and execute it. The only reasons to stop are:

1. **Operational closure** — the protocol's stopping criteria are met
2. **Hard context limit** — you are running out of context and must dump state before you lose it

If you are approaching context limits, write all current state to files, append a detailed cycle-log entry with explicit next steps, and write `status.md` with:
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

## Resumption

Start from whatever status.md says is highest priority. If status.md doesn't exist, use cycle-log.md and the protocol's decision rule to determine where to begin.

**Do not re-derive work that has already been done.** Trust the state files. If the basis is built, don't rebuild it. If candidates are generated, don't regenerate them. Read what exists and push forward from there.
