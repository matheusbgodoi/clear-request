# Examples

## Execute a fix

Request: “Saving contacts is weird: two clicks create two contacts and errors say it worked. Fix and test it.”

Investigate the contact flow, reproduce the behavior, fix the requested issues, and verify success, failure, and repeated submission. Do not add a global email deduplication rule without a requirement.

## Write a transferable prompt

Request: “Prompt only for another agent: login disappears on refresh, maybe the database; keep our auth provider.”

A useful prompt asks the recipient to investigate and fix session loss on refresh, treats the database as an unconfirmed hypothesis, preserves the auth provider, and asks for validation of refresh and logout. It does not execute the fix.

## Respect a planning boundary

Request: “Plan how to migrate this service, but do not change files.”

Inspect relevant context if appropriate and provide a plan. Do not implement it.

## Ask about an irreversible ambiguity

Request: “Delete old customers we don't need.”

Do not invent a retention period or delete records. Ask which customers qualify and whether the intended action is deletion or archival; continue any safe independent investigation.

## Draft versus create a goal

Request: “Draft a goal for these three checkout bugs; don't activate it.”

Use the three problems if available in context and provide a draft with observable outcomes. Do not activate a goal. If the bugs cannot be identified, ask for them.
