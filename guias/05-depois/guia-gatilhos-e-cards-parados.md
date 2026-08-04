# GUIA GATILHOS E CARDS PARADOS — o que fazer quando o negócio trava

> **Estou perdido em:** "o cliente parou de responder e eu não sei se insisto, se espero, ou se dou por perdido".
> **O que você vai ter no final:** os 4 sinais de alerta de um negócio específico e os 4 que mandam revisar o processo inteiro — cada um com a ação certa, o prazo e quem age.
> **Fontes cruzadas:** o `SKILL.md` da `/desenho-processo-comercial` (Passo 2, os dois níveis de gatilho, e a referência de SLA de 1 hora / janela de 7 dias) e da `/regua-comunicacao-comercial` (Passo 4, o escalonamento de card parado em 2h / 24h / 48h) · a Aula 1 ao vivo, onde a professora percorreu um gatilho por vez com exemplo · pesquisa sobre envelhecimento de pipeline e queda de probabilidade de fechamento (consultada em 03/08/2026).

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📖 Conhecimento | Saber o que é etapa, deal, comprador econômico e forecast | leia [guia-conceitos-comerciais.md](../02-conhecimento-minimo/guia-conceitos-comerciais.md) |
| 📄 Artefato | O `processo-comercial-{negocio}.md`, onde os seus gatilhos já estão definidos | rode `/desenho-processo-comercial` |

## Por que isso importa (o número que assusta)

Um negócio parado não fica parado — ele **apodrece**. Os dados de mercado:

| Fato | Número de referência |
|---|---|
| Negócios que fecham dentro do ciclo médio do negócio | convertem a ~**68%** |
| Negócios que ultrapassam esse ciclo médio | convertem a ~**23%** |
| Quando considerar um card "parado" | mais de **1,5× a 2×** o tempo médio daquela etapa |

⚠️ **E tem um efeito colateral perverso:** o card parado continua contando o valor cheio dele no seu forecast. Ou seja, quanto mais lixo parado no funil, mais bonito e mais mentiroso fica o número que você reporta.

**A analogia:** pense no funil como uma geladeira. Cada deal é um alimento com validade. Ninguém joga fora, então a geladeira vive cheia — e você olha e pensa "tem comida". Até abrir e ver que metade estragou. Gatilho de deal é o alarme de validade de **um** alimento. Gatilho de processo é a decisão de que a geladeira inteira precisa de faxina.

## Parte 1 — Os 4 gatilhos de DEAL (o alerta de um negócio específico)

### Gatilho 1 — Estagnação

**O sinal:** o card ficou parado além do tempo esperado para aquela etapa.

**A referência que a sua skill usou:** 7 dias como janela de corte. A aula explicou o porquê de existir um número:

> *"Esse card parado além de sete dias na semana é um alerta tanto para o vendedor quanto para o gestor comercial. Ele precisa saber que, depois de sete dias, em que etapa ele está travando aqui."*

⚠️ **Mas 7 dias não é lei — é ponto de partida.** O certo é calibrar por etapa e pelo seu ciclo. Referências de mercado, por porte:

| Porte | Discovery | Proposta |
|---|---|---|
| Pequeno / venda rápida | 5-10 dias | 3-10 dias |
| Médio | 7-14 dias | 7-14 dias |
| Complexo / enterprise | 14-30 dias | 14-30+ dias |

**A ação:** alerta para o vendedor **e** para o gestor. E a leitura que a aula pede — não é só cobrar o vendedor:

> *"Se é uma falha do comercial, se é uma falha que o cliente ali a gente não está alinhado, tem que melhorar o ICP. O ICP que a gente imaginou está travado."*

Ou seja: card travando **sempre na mesma etapa**, em vários deals, não é problema de vendedor. É problema de processo ou de ICP.

### Gatilho 2 — No-show

**O sinal:** o cliente confirmou a reunião e não apareceu.

⚠️ **Isso NÃO entra na fila de follow-up normal.** É o ponto que a aula mais frisou:

> *"Isso daqui é importantíssimo: não entrar num follow-up normal. Ele precisa estar tendo um reengajamento na hora."*

**A ação, por situação:**

| Situação | O que fazer |
|---|---|
| Ele avisou antes que não vai poder | **remarque na hora**, na mesma conversa. Não deixe pra depois |
| Ele confirmou e simplesmente não apareceu | vá pra uma etapa própria de **Reagendamento** — nunca direto pra Perdido |

O motivo de não mandar direto pra Perdido: no-show quase nunca é falta de interesse; é agenda. Tratar como perda queima um deal que ainda estava vivo.

### Gatilho 3 — Silêncio do comprador econômico

**O sinal:** quem assina sumiu por vários dias, na fase de proposta ou negociação.

Da aula, sobre o momento em que isso dói mais:

> *"É aquela etapa do forecast: a gente já enviou a proposta e ele simplesmente não responde mais. Isso é um sinal de alerta. Pode ser o valor, pode ser que ele esteja pesquisando com outros concorrentes."*

**A ação:** reabrir o contato **com o decisor final**, não com o contato intermediário. E a aula recomenda o canal:

> *"A ligação também é boa."*

Modelo de reabertura (sem soar cobrança):

> *"Oi [nome], não quero te pressionar. Só queria entender se aquele ponto de [problema que ele descreveu] continua na sua lista de prioridades, ou se mudou alguma coisa aí. Se mudou, tudo bem — só me diz que eu paro de te procurar."*

A última frase é o que gera resposta. Dar a saída honesta é o que faz a pessoa responder.

### Gatilho 4 — Concorrente entrou

**O sinal:** qualquer menção a avaliação ativa de outra solução.

**A ação:** reabre a etapa de **discovery** pra reforçar diferenciação. Não é hora de desconto. O guia inteiro disso está em [guia-diferencial-e-concorrencia.md](../02-conhecimento-minimo/guia-diferencial-e-concorrencia.md).

### E se o seu negócio é autoatendimento (sem vendedor)?

O gatilho de deal equivalente é o **abandono** — de carrinho, de checkout, de cadastro. Ele não dispara alerta pra humano: dispara a régua de recuperação automática que a Skill 2 desenhou.

## Parte 2 — O escalonamento de card parado (o padrão de 3 toques)

Isto é diferente da régua com o cliente: é a régua **com o seu vendedor**, quando o card devia ter se movido e não se moveu (ex.: a reunião já aconteceu e ninguém atualizou nada).

| Toque | Quando | Para quem | O quê |
|---|---|---|---|
| 1º | ~2h depois do evento | o dono do card | pergunta binária: *"o que aconteceu na reunião?"* |
| 2º | 24h, se continuar parado | o dono do card | mesma pergunta, tom mais direto |
| 3º | 48h | dono **+ cópia pra liderança** | com prazo curto |

⚠️ **Card que passa pelos 3 sem ação não merece um 4º lembrete.** Vira pauta de acompanhamento com gente — é sinal de gestão, não de automação.

## Parte 3 — Os 4 gatilhos de PROCESSO (o alerta de que o funil inteiro envelheceu)

Estes não olham um deal: olham o desenho. A maioria dos funis só tem os de deal, e é por isso que apodrecem.

| Gatilho | O sinal | O que revisar |
|---|---|---|
| **Lançou produto ou oferta nova** | óbvio, e sempre esquecido | as etapas, a régua de mensagens (preço mudou?), e a escada de ofertas |
| **A conversão entre etapas mudou de forma consistente** por 2+ ciclos | queda **ou alta** | onde exatamente caiu. Da aula: *"em cada etapa precisa estar entendendo como está sendo a conversão"* |
| **Mudança de mercado / concorrente novo relevante** | você começou a perder deals que antes ganhava | o diferencial e a etapa de discovery |
| **Mudança de ICP** | quem fecha não é quem você mirava | o perfil do cliente ideal |

Sobre o último, o exemplo que a aula deu:

> *"Às vezes você está mirando em pequenas e médias empresas, e só as pequenas estão fechando. Pra que ele vai gastar energia com médias empresas, sendo que são as pequenas [que compram]?"*

⚠️ **A régua pra mudar o ICP, e não mudar por impulso:** rode pelo menos **10 conversas de discovery** antes de alterar a definição. Uma conversa que contradiz sua hipótese não significa nada. Dez que contradizem significam que o ICP está errado.

E tem um quinto, que a aula acrescentou e vale registrar: **funcionalidade faltante recorrente**. Quando o mesmo "vocês não têm X" derruba vários deals, isso não é objeção — é roadmap de produto.

## Parte 4 — A revisão que roda sem gatilho nenhum

**Trimestral, no mínimo.** Mesmo que nada tenha disparado. A justificativa está no `SKILL.md` da Skill 1, e é uma frase só: *"funil não revisado apodrece silenciosamente."*

Coloque no calendário agora, com nome de dono. Sem dono e sem data, não acontece.

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Triar os cards parados da semana** | "Estes são os meus deals abertos: [cole a planilha ou a lista com etapa, valor e data da última movimentação]. Hoje é [data]. Liste os que estão parados além do esperado, agrupe por gatilho (estagnação / no-show / silêncio do decisor / concorrente) e me dê **uma ação por card**, em ordem de prioridade." |
| **Escrever a mensagem de reabertura** | "Este deal está parado há [X] dias na etapa [Y]. O último contato foi: [cole]. A dor que ele me descreveu foi: [cole a frase dele]. Escreva a mensagem de reabertura, com ângulo diferente do último toque, e terminando com uma saída honesta pra ele poder dizer não." |
| **Calibrar meus prazos de estagnação** | "Meu ciclo médio de venda é [X]. Minhas etapas são: [liste]. Sugira o prazo de estagnação de cada etapa usando 1,5× a 2× o tempo típico, e me diga em qual etapa vale ser mais rígido." |
| **Descobrir onde meu funil trava** | "Estes são meus últimos [N] deals perdidos, com etapa e motivo: [cole]. Existe um padrão? O problema está na captação, no processo ou na etapa X?" |
| **Montar o ritual semanal** | "Monte um checklist de 15 minutos pra eu rodar toda segunda-feira sobre meu funil, baseado nos gatilhos de deal do meu `processo-comercial-{negocio}.md`. Máximo 6 itens, cada um com uma pergunta objetiva." |

## Teste de sucesso

Abra a sua planilha/quadro de deals e responda:

1. Consigo ver, em menos de 1 minuto, **quais cards não se moveram nos últimos 7 dias**?
2. Cada um desses tem uma **próxima ação com data**?
3. Existe uma etapa de **Reagendamento** separada de "Perdido"?
4. Tenho a revisão trimestral do processo **marcada no calendário**, com dono?

**Funcionou se:** quatro "sim". Se o item 1 falhou, seus gatilhos existem no documento mas não na operação — e aí eles não existem.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| GT1 | Tenho os gatilhos no documento mas nunca vejo card parado | Os gatilhos não saíram do papel | crie um ritual semanal simples: toda segunda, *"quais cards não se moveram há 7 dias?"*. Não precisa de automação — precisa de rotina |
| GT2 | Meu forecast é sempre otimista e nunca bate | Cards velhos mantendo o valor cheio no total | 1) limpe: card acima de 2× o tempo médio da etapa sai ou vira Perdido com motivo 2) exija valor preenchido em todo card das etapas finais |
| GT3 | Mandei no-show pra "Perdido" e depois o cliente voltou querendo comprar | No-show tratado como desinteresse | crie a etapa de **Reagendamento**. No-show quase sempre é agenda, não recusa |
| GT4 | Fico mandando mensagem e o cliente não responde nunca | Insistência sem ângulo novo | 1) nunca repita a mesma mensagem 2) troque de canal 3) dê a saída honesta ("me diz que eu paro de te procurar") 4) esgotada a régua, mande pra nutrição — não pra Perdido |
| GT5 | Todos os meus deals travam na mesma etapa | Não é vendedor, é processo ou ICP | 1) olhe o critério de saída daquela etapa: está claro? 2) veja se o lead chega pronto pra ela 3) se não chega, o problema é a captação — devolva pro marketing |
| GT6 | 7 dias é curto/longo demais pro meu negócio | O número é benchmark, não lei | calibre por etapa usando 1,5× a 2× o SEU tempo médio. Ciclo de meses pede janelas maiores |
| GT7 | Meu vendedor não avisa quando o card trava | Falta o escalonamento interno | implante os 3 toques (2h / 24h / 48h com cópia pra liderança), sempre com pergunta binária, nunca aberta |
| GT8 | Mudei o ICP porque um cliente falou uma coisa | Mudança por impulso | espere pelo menos 10 conversas de discovery apontando na mesma direção antes de mexer na definição |
| GT9 | O comprador econômico nunca apareceu no deal inteiro | Isso não é um deal, é uma conversa | volte ao bloco de autoridade: *"além de você, quem mais precisa estar de acordo?"*. Sem ele, a proposta não tem para onde ir |

**Se nada resolver:** leve o card específico pra uma conversa com a IA: *"este deal está parado há X dias na etapa Y. Este é o histórico: [cole]. Qual é a próxima ação mais provável de destravar?"*

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | marque um ritual semanal de 15 minutos: "quais cards não se moveram?" — e a revisão trimestral no calendário |
| 📖 Ler | [guia-metricas-do-comercial.md](guia-metricas-do-comercial.md) — os números que dizem se o funil está saudável |
| 🚑 Se travar | o catálogo GT1–GT9 acima |
