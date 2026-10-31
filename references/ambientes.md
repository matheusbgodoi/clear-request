# Ambientes e portabilidade

O conteúdo de `SKILL.md` usa o formato Agent Skills: frontmatter YAML com `name` e `description` e instruções Markdown. O aplicativo descobre e carrega a skill; o modelo interpreta as instruções. `agents/openai.yaml` é metadado específico do Codex, sem dependência para os demais agentes.

## Onde instalar e como chamar

| Ambiente | Diretório global por skill | Invocação explícita |
| --- | --- | --- |
| Codex | `~/.agents/skills/pedido-claro/` ou o diretório de skills configurado do Codex | `$pedido-claro <pedido>` |
| Claude Code | `~/.claude/skills/pedido-claro/` | `/pedido-claro <pedido>` |
| Antigravity IDE | `~/.gemini/config/skills/pedido-claro/` | Pedir “Use a skill pedido-claro para…”; conferir a interface de Customizations |
| Antigravity CLI | `~/.gemini/antigravity-cli/skills/pedido-claro/` | `/pedido-claro <pedido>` |
| OpenCode 2 | `~/.config/opencode/skills/pedido-claro/`; também descobre `~/.claude/skills/` e `~/.agents/skills/` | `@pedido-claro <pedido>` |

No Antigravity App, a documentação também prevê `/<skill-name>`. Não presuma que todas as versões e superfícies do IDE tenham o mesmo seletor do App/CLI; pedir pelo nome é a alternativa portátil.

No OpenCode 1, peça para carregar `pedido-claro` com a ferramenta `skill`; não suponha que a sintaxe de menção da versão 2 se aplica. No OpenCode 2, o identificador passado à ferramenta é `id`; na versão 1 é `name`. Use o esquema efetivamente exposto pela ferramenta.

Skills não forçam a própria ativação: descoberta automática depende da descrição, das permissões e do agente. Para garantir que este fluxo seja solicitado, invoque explicitamente. Se a interface não atualizar a lista, recarregue as skills conforme o suporte do aplicativo ou abra nova sessão. Não reinicie sessões de trabalho do usuário sem autorização.

## Modelos e Goals

Opus e Qwen são modelos; a instalação é no aplicativo que os utiliza. Não fixe modelo, provedor, tamanho de contexto ou raciocínio nesta skill. Em modelos locais, a integração de ferramentas e a capacidade de seguir instruções afetam o resultado; a instalação não demonstra qualidade de execução.

Metadados de um provedor como `tool_call: true` indicam configuração, não comprovam que o servidor do modelo executa chamadas de ferramentas corretamente. Para diagnosticar falhas, diferencie skill não descoberta, skill não carregada e instruções mal seguidas.

Goals persistentes são recursos do aplicativo, não uma propriedade transmitida pelo arquivo da skill. O Codex pode expor ferramentas de Goal. Antigravity documenta `/goal` no App/CLI, mas disponibilidade e controle precisam ser verificados na superfície usada. Não presuma comando equivalente no Claude Code ou OpenCode. Seguir etapas dentro da execução atual não equivale a instalar continuação automática.

## Fontes oficiais

Verificadas em 24/10/2026. Consultar novamente para mudanças de versão; não é necessário navegar a cada uso normal da skill.

- [Claude Code: skills, caminhos, symlinks e invocação](https://code.claude.com/docs/en/skills)
- [Antigravity: skills por App, CLI e IDE](https://antigravity.google/docs/skills)
- [Antigravity: comandos e Goal](https://antigravity.google/docs/slash-commands/)
- [OpenCode 2: skills, descoberta, precedência e menção](https://dev.opencode.ai/v2/docs/skills/)
- [OpenCode 1: skills](https://docs.opencode.ai/docs/skills/)
