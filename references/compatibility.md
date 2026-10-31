# Compatibility

This is an Agent Skills folder: `SKILL.md` has YAML frontmatter and Markdown instructions. `agents/openai.yaml` supplies optional Codex interface metadata; other agents can ignore it. The host determines discovery, permissions, tools, and invocation. The skill does not require a particular model or automatically enable persistent goals.

The [skills CLI](https://github.com/vercel-labs/skills) supports global installation for multiple agents. See the [CLI documentation](https://www.skills.sh/docs/cli) for current agent names and options. Alternatively, copy this skill folder to an agent's documented skills directory. Restart or reload the agent if it does not discover a newly installed skill.

In Codex, invoke `$clear-request`. In Claude Code, invoke `/clear-request`. Other environments may allow asking the agent to use the skill by name. Automatic selection depends on the host and context.
