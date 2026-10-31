---
name: clear-request
description: Turn informal or ambiguous software requests into clear, scoped execution, plans, or transferable prompts while preserving the user's intent and permissions. Use when a user asks you to interpret, refine, or act on an unclear development request.
---

# Clear Request

Take responsibility for understanding the request. Users do not need polished prompts: interpret informal language, typos, examples, and available context without inventing requirements. Respond in the user's language unless asked otherwise.

## Choose the mode

- **Execute by default:** When the user asks for an action, investigate, implement, and validate it in the current environment. Do not stop at a plan or a rewritten prompt.
- **Prompt only:** When asked for a prompt for another agent or session, provide a self-contained prompt. Do not execute it, create a persistent goal, or contact another agent. Read context only when it materially improves the prompt and is within scope.
- **Plan or explain only:** Respect that boundary; do not implement.
- If there is no actionable request or recoverable referent, ask for the missing request.

## Understand and scope

1. Identify the desired outcome, observed problem, explicit constraints, and relevant examples. Preserve details that change behavior.
2. Inspect applicable instructions and the minimum relevant project context. Discover actual names, tools, callers, and tests rather than assuming them.
3. Separate established facts, hypotheses to investigate, and unknown product decisions. A user's proposed cause is not a diagnosis.
4. Resolve routine choices using context. State material assumptions briefly. Ask when plausible interpretations materially change behavior, scope, or an action that is hard to reverse; continue independent work where possible.
5. Choose the smallest scope that achieves the outcome, including necessary dependencies. Do not add unrelated features, arbitrary targets, or broad rewrites.

## Execute and validate

Describe the intended action briefly when useful, then carry it through. Define observable outcomes and validate according to risk and the repository's conventions. For behavior bugs, seek a reproducible failure and a meaningful regression test when practical. For integrations, persistence, permissions, or concurrency, seek evidence at the relevant real boundary in an isolated environment. Do not present mocks, a build, or inspection as proof of a flow they did not exercise.

Preserve existing user changes. Investigate failures instead of weakening checks to make them pass. Review the resulting changes. Report what was done, validation actually performed, and material limitations. If blocked, complete independent work and explain what remains.

For larger work, sequence steps by dependency and record progress only when useful. A checklist is not evidence that a task works. Treat unrelated discoveries as findings unless they are necessary to complete the request.

## Transferable prompts

For prompt-only requests, provide one concise, self-contained block containing the known context, desired result, relevant scope, observable acceptance criteria, validation, constraints, and material unknowns. Mark suspected causes as hypotheses. Do not rely on hidden conversation context or require the recipient to have this skill. Do not add a role, invented stack, or chain-of-thought request for decoration.

## Goals and authorization

A large task or invocation of this skill does not itself create a persistent goal. If explicitly asked to draft one, provide text without activating it. If asked to create one, use an available native mechanism and its lifecycle rules; do not invent commands or promise persistence. Preserve existing goals and scope.

Follow the user's instructions and the host environment's permissions. Clarifying a request does not authorize deployment, destructive actions, transactions, or messages to others. Do not introduce extra approval gates for work already authorized.

See [examples](references/examples.md) for mode boundaries and realistic use cases. See [compatibility](references/compatibility.md) for installation and invocation guidance.
