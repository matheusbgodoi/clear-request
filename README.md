# Pedido claro

Uma skill para agentes de programação que transforma pedidos informais em trabalho bem delimitado. Ela ajuda o agente a entender a intenção, investigar o contexto necessário, executar e validar — ou escrever um prompt transferível quando essa for a solicitação.

## Quando usar

- **Implementar:** “o botão de salvar às vezes não funciona, dá uma olhada e corrige”. O agente investiga o comportamento, corrige e valida.
- **Refinar um pedido:** “transforma isso num prompt para outro agente: quero um painel com os dados que já temos”. A skill entrega um prompt copiável sem executar a tarefa.
- **Planejar:** “me ajuda a planejar a migração desse serviço”. O agente respeita o limite de planejamento.
- **Lidar com ambiguidade:** “melhora essa tela, ela tá confusa”. O agente usa o contexto, evita inventar requisitos e pergunta apenas quando uma decisão relevante estiver realmente em aberto.

A skill preserva as permissões e instruções do ambiente. Ela não cria autorização para produção, ações destrutivas ou mensagens a terceiros.

## Instalação

Clone este repositório no diretório de skills do seu agente. Por exemplo, para o Codex:

```sh
git clone https://github.com/matheusbgodoi/pedido-claro.git ~/.agents/skills/pedido-claro
```

Para o Claude Code:

```sh
git clone https://github.com/matheusbgodoi/pedido-claro.git ~/.claude/skills/pedido-claro
```

Depois, abra uma nova sessão ou recarregue as skills se necessário. No Codex, invoque com `$pedido-claro`; no Claude Code, com `/pedido-claro`. A descoberta automática depende do ambiente. Consulte [ambientes e portabilidade](references/ambientes.md) para outros agentes e detalhes de versão.

## Exemplos

```text
$pedido-claro o cadastro tá quebrando quando o email já existe, arruma
```

```text
$pedido-claro só cria um prompt para outro agente implementar busca na lista de clientes
```

```text
$pedido-claro só planeja como migrar esse serviço, sem alterar arquivos
```

Mais exemplos e fundamentos estão em [references/exemplos.md](references/exemplos.md). As instruções completas estão em [SKILL.md](SKILL.md); `agents/openai.yaml` contém metadados opcionais para o Codex.

## Como funciona

A skill identifica o resultado desejado e as restrições, consulta o contexto necessário, distingue fatos de hipóteses e define evidências de conclusão proporcionais ao risco. Para pedidos de ação, orienta o agente a executar e validar; para pedidos de prompt ou planejamento, respeita esse limite. O resultado depende das capacidades e permissões do agente utilizado.

## Contribuindo

Issues e pull requests são bem-vindos. Ao propor mudanças, inclua um exemplo concreto do comportamento desejado e preserve a portabilidade entre agentes.
