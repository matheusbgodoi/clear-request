# Exemplos e fundamentos

## Interpretar e executar no mesmo Codex

Pedido:

> $pedido-claro o salvar ta estranho clico 2x cria 2 contatos e quando da erro fala que deu certo arruma e testa

Comportamento: localizar o fluxo de contatos, confirmar reprodução e semântica de duplicação, corrigir os comportamentos pedidos e validar sucesso, erro e repetição. Não acrescentar deduplicação universal por e-mail sem requisito. Uma apresentação suficiente: “Vou investigar o salvamento de contatos, corrigir a repetição do envio e a mensagem de erro, e validar esses cenários.” Nenhum Goal é criado só pela extensão do trabalho.

## Preparar para outra conversa

Pedido:

> $pedido-claro só prompt pro outro codex: o login cai quando dou f5, acho q é o banco, quero arrumar sem trocar o auth

Possível saída:

```text
Investigue e corrija a perda de sessão ao recarregar a página,
preservando o provedor de autenticação existente.

A causa ainda não foi confirmada; banco de dados é uma hipótese.
Leia as instruções aplicáveis e o fluxo de autenticação, sessão
e recarregamento. Reproduza a falha no ambiente de teste, corrija
a causa identificada e valide que uma sessão válida continua
autenticada após recarregar e que logout continua funcionando.

Use os comandos e testes pertinentes do repositório. Relate as
validações executadas e qualquer limitação de acesso. Mantenha
as mudanças relacionadas ao problema e preserve alterações
existentes do usuário.
```

Não é necessário o outro Codex ter esta skill. Credenciais e estado oculto da conversa não são transferidos.

## Preparar um Goal

Pedido:

> $pedido-claro monta um /goal pra corrigir esses 3 problemas do checkout, sem ativar

Comportamento: incorporar os três problemas recuperáveis no contexto, com resultado verificável, preservação dos contratos pertinentes e evidências. Entregar o comando sem criar Goal. Se “esses três” não tiver referente acessível, pedir a lista. Se o pedido for “crie e execute um Goal”, a ativação foi solicitada; use as ferramentas existentes após definir o escopo.

## Decisão que não pode ser adivinhada

Pedido:

> $pedido-claro apaga os clientes velhos que não servem

Comportamento: não inventar que “velhos” significa 90 dias nem apagar registros. Esclarecer quais clientes, o critério de seleção e se o resultado é arquivamento ou exclusão. Não converter linguagem vaga em autorização concreta para uma alteração irreversível.

## Fontes de manutenção

Esta skill não precisa buscar documentação OpenAI a cada utilização. Consulte fontes atuais apenas para dúvidas sobre recursos do Codex ou manutenção de suas instruções:

- [Skills: invocação e descoberta](https://learn.chatgpt.com/docs/build-skills)
- [Goals: resultado, verificação e limites](https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex)
- [Planos para trabalho longo](https://developers.openai.com/cookbook/articles/codex_exec_plans)
- [Prompts e contexto sem excesso de instruções](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra)
