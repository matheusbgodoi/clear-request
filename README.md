# Pedido Claro

**Make the request clear. Keep the intent. Get the work done.**

Pedido Claro is an open Agent Skill that helps coding agents turn informal, incomplete, or messy development requests into focused action. It works with Claude Code, Codex, and other agents that support the [Agent Skills format](https://agentskills.io/).

You can write naturally, in any language. The skill itself is in English and asks the agent to reply in your language unless you choose otherwise.

## Install globally

With Node.js and npm installed, run:

```sh
npx skills add matheusbgodoi/pedido-claro --skill pedido-claro --global
```

The [skills CLI](https://github.com/vercel-labs/skills) lets you select supported agents. To target Claude Code and Codex directly and skip interactive prompts:

```sh
npx skills add matheusbgodoi/pedido-claro --skill pedido-claro --global --agent claude-code --agent codex --yes
```

Reload your agent or start a new session if the skill is not discovered immediately. See the [CLI documentation](https://www.skills.sh/docs/cli) for other agents, updates, and removal.

### Manual installation

Clone the repository into the appropriate global skills directory:

```sh
# Codex
git clone https://github.com/matheusbgodoi/pedido-claro.git ~/.agents/skills/pedido-claro

# Claude Code
git clone https://github.com/matheusbgodoi/pedido-claro.git ~/.claude/skills/pedido-claro
```

If the destination already exists, update it using its existing installation method instead of overwriting local changes. Other agents can use the same folder in their documented skills location. See [compatibility](references/compatibility.md).

## Use it

In Codex:

```text
$pedido-claro The save button sometimes creates two contacts. Fix it and test the failure case.
```

In Claude Code:

```text
/pedido-claro The save button sometimes creates two contacts. Fix it and test the failure case.
```

You can also ask a compatible agent to use Pedido Claro by name. Automatic discovery depends on the agent and context.

## What it does

| Your request | Expected behavior |
| --- | --- |
| “Fix this error; I think it is the database.” | Investigate the error, treat the proposed cause as a hypothesis, fix and validate the actual issue. |
| “Write a prompt for another agent to add search.” | Produce a self-contained prompt without implementing the feature. |
| “Plan the migration; do not change files.” | Inspect relevant context and provide a plan without implementing it. |
| “Delete customers we no longer need.” | Ask for the missing selection criteria before an irreversible action. |

The skill makes reasonable reversible decisions, asks when ambiguity materially matters, and preserves existing permissions. It does not grant access, authorize deployment, or guarantee an agent's behavior.

## How it is organized

- [SKILL.md](SKILL.md): the instructions agents load.
- [Examples](references/examples.md): realistic requests and mode boundaries.
- [Compatibility](references/compatibility.md): portable usage guidance.
- `agents/openai.yaml`: optional Codex interface metadata.

## Contributing

Issues and pull requests are welcome. Include a concrete request and expected behavior when suggesting changes, and keep the skill portable across agents.
