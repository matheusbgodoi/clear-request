---
name: pedido-claro
description: Interpreta pedidos informais de desenvolvimento e define escopo e validação para executar ou gerar um prompt transferível. Use quando o usuário pedir para organizar sua intenção ou refinar um pedido para um agente de programação.
---

# Pedido claro

Assuma a responsabilidade de estruturar a tarefa. O usuário pode escrever com erros, termos imprecisos, repetições ou exemplos. Preserve sua intenção e use o contexto disponível; não exija um prompt bem escrito.

Esta skill é independente de modelo e funciona no agente que a carregou. Use as ferramentas e instruções desse ambiente; não suponha que os recursos do Codex existem no Claude Code, Antigravity ou OpenCode. Não troque o modelo nem encaminhe pedidos a outra sessão automaticamente.

## Escolha o modo pelo pedido

- **Executar (padrão para pedidos de ação):** interprete, investigue o contexto necessário, implemente e valide no mesmo agente. Não termine entregando apenas um prompt ou plano quando a implementação foi solicitada.
- **Só prompt / para outro agente (inclui “outro Codex”):** entregue um prompt autossuficiente para copiar. Não execute as instruções nele contidas nem altere arquivos, crie Goals ou contate outro agente. Investigue em leitura apenas quando houver contexto acessível que melhore materialmente o resultado; se o usuário pedir só reescrita, trabalhe com o texto fornecido.
- **Só planejar / só explicar:** respeite esse limite. Invocar esta skill não converte perguntas, exemplos, citações ou pedidos de planejamento em autorização para implementar.
- Se não houver tarefa nem referente recuperável no contexto, peça o pedido que deve interpretar.

## Reconstrua a intenção sem inventar requisitos

1. Identifique o problema observado, resultado desejado, restrições expressas e exemplos relevantes. Preserve prioridades e detalhes que mudam o comportamento.
2. Consulte instruções aplicáveis e apenas código, chamadores, testes ou fontes necessários. Use o projeto real para descobrir nomes e comandos; não invente stack, caminhos, ferramentas, causas ou resultados.
3. Separe fatos, hipóteses técnicas a investigar e decisões de produto desconhecidas. Uma suspeita do usuário sobre a causa não é diagnóstico confirmado.
4. Resolva erros de escrita e decisões rotineiras pelo contexto. Para suposições reversíveis, escolha uma opção razoável e sinalize brevemente quando relevante. Pergunte apenas quando interpretações plausíveis mudarem materialmente comportamento, escopo ou uma ação difícil de desfazer. Continue no trabalho independente da resposta.
5. Formule o menor escopo que resolve o pedido. Inclua dependências necessárias, mas não acrescente features, modernizações, metas numéricas ou refatorações por conta própria. “Melhorar tudo” pede delimitação e diagnóstico, não autorização ilimitada.

## Defina a conclusão e trabalhe

Transforme intenções em resultados observáveis: o que o usuário consegue fazer e que evidência comprova isso. Quando o critério depender de uma decisão desconhecida, mantenha a lacuna explícita em vez de preenchê-la como fato.

Em execução, comunique a interpretação e a próxima ação em poucas frases, se isso ajudar, e prossiga. Não exponha raciocínio interno nem gere um segundo prompt longo para si mesmo. Em alterações simples, faça a mudança e a verificação proporcionais sem criar documentos ou rituais.

Para trabalho extenso, organize etapas por dependência, cada uma com resultado verificável. Reutilize o plano existente; registre escopo, progresso, decisões e evidências em arquivo apenas quando útil à continuidade. Documento e checkbox não comprovam implementação. Valide também o fluxo conjunto ao final. Trate bugs descobertos fora do escopo como achados, salvo dependência necessária para a entrega.

Em programação, aplique as instruções de Clean Code e testes existentes e a skill `clean-code` quando disponível. Para bugs de comportamento, busque reprodução e teste de regressão pertinente; para integrações, persistência e autorização, use a fronteira real relevante em ambiente isolado. Rode os checks exigidos pelo repositório. Não enfraqueça testes nem trate mocks, build ou inspeção como prova de um fluxo que não foi exercitado. Não crie testes que apenas espelhem texto ou estrutura em mudanças triviais.

Se faltar acesso ou houver bloqueio, avance nas partes independentes e informe o que falta. Não declare concluído algo que depende de validação não executada. Termine com resultado, evidências executadas e limitações materiais, proporcionais à tarefa.

## Goals e autorização

Uma tarefa grande, “continue até terminar” ou a invocação desta skill não cria automaticamente um Goal persistente. Quando o usuário solicitar explicitamente esse recurso, distinga objetivo de trabalho de um mecanismo nativo de continuação. Pedir para **rascunhar** um Goal pede texto, sem ativação.

Para um Goal solicitado, sintetize resultado, escopo, evidências de conclusão, restrições e tratamento de bloqueios. Ative o recurso apenas se houver uma ferramenta nativa disponível e respeite suas regras de ciclo de vida. Se houver somente um comando de interface documentado, entregue esse comando para o usuário executar e informe que não foi ativado. Se o ambiente não oferecer esse recurso, explique brevemente a limitação e execute o escopo autorizado com plano e validação; não invente `/goal`, automações ou persistência entre turnos. Não prometa execução sem limites. Não substitua um Goal ativo por outro nem amplie seu escopo silenciosamente. Não marque como completo sem evidências.

Preserve a autorização já existente. Reformular um pedido não concede permissões adicionais para deploy, produção, ações destrutivas ou mensagens a terceiros. Não imponha novas confirmações a ações rotineiras já autorizadas.

## Saída no modo só prompt

Entregue um único bloco copiável, enxuto e autossuficiente. Inclua apenas o necessário: contexto conhecido, resultado, escopo, critérios observáveis, validação pertinente, restrições e lacunas materiais. Evite “conforme conversamos” ou referências a conversas que o destinatário não tem. Transfira decisões relevantes e mantenha hipóteses identificadas; peça ao executor que confirme informações do repositório que não foram verificadas.

Use `/goal <objetivo>` no bloco apenas quando o usuário pedir um prompt de Goal e esse comando for suportado no destino; se o destino for desconhecido, use instruções em linguagem natural. Não inclua esta skill como dependência do destinatário. Quando faltarem dados essenciais, prefira uma pergunta objetiva; se ainda for possível gerar um prompt útil, deixe explícito o que o executor precisa descobrir. Não acrescente papéis grandiosos, garantias, pedidos de cadeia de pensamento ou instruções repetidas.

Consulte [exemplos e fundamentos](references/exemplos.md) apenas para exemplos de invocação, dúvidas sobre os modos ou revisão desta skill.
Para dúvidas de instalação, invocação ou portabilidade entre agentes, consulte [ambientes](references/ambientes.md).
