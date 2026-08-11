# GUIA O MAPA DAS SKILLS — o que cada uma pergunta, entrega, e quando pular

> **Estou perdido em:** "são vários comandos, qual eu rodo agora? o que cada um faz? e quanto tempo isso leva?".
> **O que você vai ter no final:** o mapa inteiro da Aula 1 numa página — ordem, o que cada skill pergunta, o que entrega, e as situações em que **pular** uma skill é a resposta certa.
> **Fontes cruzadas:** os `SKILL.md` deste repo (a ordem, os gates de entrada e as condições de pulo saíram de dentro deles) · o `README.md` e o `docs/workflow.md` (fluxo da aula e conexão entre skills) · o `docs/SKILLS-INDEX.md` (aliases que o aluno tenta digitar) · a Aula 1 ao vivo, onde o fluxo principal rodou em sequência · pesquisa sobre os limites de convite do LinkedIn em 2026 (consultada em 03/08/2026), que a skill não cobre e a operação real esbarra.

> **Escopo:** este guia cobre a **Aula 1** — as 5 skills do fluxo principal mais os 3 bônus. As 3 skills da **Aula 2** (`/montagem-higiene-crm`, `/lead-scoring-ia`, `/diagnostico-gargalos-funil`) aparecem no `ls` desde o primeiro dia e têm numeração própria (`1/3`, `2/3`, `3/3`); elas não entram na contagem daqui.

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 🧰 Ferramenta | Ferramenta aberta na pasta do projeto, skills carregando | leia [guia-baixar-e-abrir-o-projeto.md](../01-pre-requisitos/guia-baixar-e-abrir-o-projeto.md) |
| 📖 Conhecimento | As 8 respostas do diagnóstico | leia [guia-diagnostico-antes-de-rodar.md](../02-conhecimento-minimo/guia-diagnostico-antes-de-rodar.md) |

## O mapa em uma linha

```
1 /desenho-processo-comercial  →  2 /regua-comunicacao-comercial  →  3 /qualificacao-bant-gpct
        →  4 /discovery-script  →  5 /playbook-vendas-vivo   ← fecha o fluxo principal

        BÔNUS (só se aplicar):  6 /escada-de-ofertas   ·   7 /social-selling-comercial
                                8 /squad-sales-bonus   ← o mais avançado dos três
```

**A ordem importa?** Sim, mas não é trava. Cada skill puxa contexto da anterior se ela já rodou; se não rodou, ela pergunta o que precisa e segue. Rodar fora de ordem só significa responder mais perguntas.

⚠️ **O que a ordem realmente protege:** cada skill herda decisões da anterior. Se você aprovar um processo com etapa errada na Skill 1, as Skills 2 a 5 vão construir tudo em cima da etapa errada. Veja [guia-revisar-e-corrigir.md](guia-revisar-e-corrigir.md).

## Uma por uma

### Skill 1 — `/desenho-processo-comercial`

| | |
|---|---|
| **O que faz** | Diagnostica seu modelo de venda e desenha as etapas do funil com critério de saída verificável (VCA) e gatilhos de risco em dois níveis |
| **O que pergunta** | Se você tem o offerbook do Cohort de Marketing (Passo -1) + as 8 perguntas do diagnóstico (ticket, ciclo, decisores, B2B/B2C, tem vendedor?, nicho, origem dos leads, já tem processo?) |
| **O que entrega** | `processo-comercial-{negocio}.md` + `.html` — perfil do negócio, as flags herdáveis, tabela de etapas com VCA e contrato de dados, gatilhos de deal e de processo, métrica de forecast, cadência de revisão |
| **Tempo** | ~50 min (mais se ela precisar pesquisar concorrentes) |
| **Pular?** | **Nunca.** É o esqueleto onde as outras seis encaixam |

**O que sai daqui e todo mundo herda:** as flags `nicho_regulado`, `modelo` (com-vendedor/autoatendimento) e `insumos_cohort_mkt`. Elas ficam no topo do documento — confira se estão lá.

### Skill 2 — `/regua-comunicacao-comercial`

| | |
|---|---|
| **O que faz** | Define, por etapa, **quem fala** (humano/IA/ambos), **o que fala** e **por qual canal** — com funil de reforço por tempo parado |
| **O que pergunta** | Quais canais você realmente usa hoje · se você já tem mensagens/scripts em uso (cole!) · 2-3 concorrentes para a pesquisa de canais |
| **O que entrega** | `regua-comunicacao-{negocio}.md` + `.html` — quem atua por etapa, régua de mensagens com variação por dias parado, Mapa de Canais a Explorar (com justificativa por canal), o **mecanismo único de conversão** nomeado, e as regras transversais |
| **Tempo** | ~50 min |
| **Pular?** | Não |

**A entrega escondida mais útil:** o **Mapa de Canais a Explorar** mostra onde os seus concorrentes estão e você não. Regra dela: nenhum canal entra na lista sem justificativa baseada em dado — se não há evidência, ela marca "não recomendado agora" em vez de empurrar.

**O mecanismo único de conversão** é o nome do seu jeito de vender (2-4 palavras, ex.: *"diagnóstico antes do pitch"*). Ele atravessa as Skills 4 e 5 pra tudo soar com a mesma voz.

### Skill 3 — `/qualificacao-bant-gpct`

| | |
|---|---|
| **O que faz** | Escolhe o mix certo entre BANT e GPCT, monta o ICP e gera o roteiro de qualificação com pontuação objetiva |
| **O que pergunta** | Puxa quase tudo da Skill 1 · se você já tem ICP/avatar prévio · setor específico que converte melhor · sinais de maturidade do cliente |
| **O que entrega** | `qualificacao-{negocio}.md` + `.html` — framework escolhido com justificativa, ICP nas dimensões certas, roteiro de perguntas por bloco, escala de pontuação com nota de corte, e o protocolo de validação humana |
| **Tempo** | ~50 min |
| **Pular?** | Não. Se o modelo for autoatendimento, ela **adapta** (a qualificação vira filtro de quiz/formulário) em vez de pular |

⚠️ **A regra inegociável desta skill:** nenhum scorecard vai pra produção sem um humano revisar as primeiras rodadas. O protocolo é: rodar manual em 10-15 conversas reais → comparar as notas de 2 pessoas diferentes → só então automatizar, com revisão amostral contínua.

### Skill 4 — `/discovery-script`

| | |
|---|---|
| **O que faz** | Monta o roteiro da conversa de descoberta em 6 blocos (SPIN + Funil de Dor + quantificação de gap), **e** escreve a copy de cada mensagem da régua |
| **O que pergunta** | Se você quer criar do zero, refinar com calls reais, ou os dois |
| **O que entrega** | `discovery-script-{negocio}.md` + `.html` — os 6 blocos com intenção e exemplos, **uma peça de copy pronta pra cada linha da régua** (convite, confirmação, recap, cada follow-up, cada toque de rede social), com a técnica de copywriting nomeada em cada uma, a nota de auditoria de compliance, e a análise das suas calls (se você deu alguma) |
| **Tempo** | ~50 min — **é a mais demorada**, porque escreve muitas peças |
| **Pular?** | **Sim, se o modelo for autoatendimento.** Ela mesma avisa que discovery call não se aplica e sugere ir pra Skill 5 |

**O HTML dela tem botão "Copiar"** em cada peça escrita — feito pra você colar direto no WhatsApp/e-mail durante a operação, não só ler uma vez.

### Skill 5 — `/playbook-vendas-vivo`

| | |
|---|---|
| **O que faz** | Classifica cada objeção em 1 dos 6 tipos e gera a resposta com o framework certo, em todos os canais |
| **O que pergunta** | Como alimentar: (1) tenho lista de objeções reais · (2) não tenho, parta das típicas do nicho · (3) tenho gravações/notas de deals perdidos |
| **O que entrega** | `playbook-objecoes-{negocio}.md` + `.html` — biblioteca pesquisável por tipo e etapa, com resposta para call, WhatsApp/DM e e-mail; **battlecard de 1 página** com as 5 objeções mais frequentes; e a cadência de revisão com dono nomeado |
| **Tempo** | ~50 min |
| **Pular?** | Não. Fecha o fluxo principal |

⚠️ **Se você escolher a opção 2**, o playbook sai rotulado como *"ponto de partida a validar"* — objeções típicas do nicho, não as suas. Isso é aviso honesto, não defeito. Levante 5 objeções reais ([guia-insumos-reais.md](../03-insumos/guia-insumos-reais.md), Parte 2) e rode de novo.

### Skill 6 — `/escada-de-ofertas` (bônus)

| | |
|---|---|
| **O que faz** | Desenha a jornada de ascensão entre os seus **produtos** — nível de portfólio, não de pipeline |
| **O que pergunta** | Primeira coisa: *"vocês têm mais de uma oferta/produto, em faixas de preço ou complexidade diferentes?"* |
| **O que entrega** | `escada-de-ofertas-{negocio}.md` + `.html` — degraus com "pra quem é" e "o que entrega", critério de prontidão por degrau, o **erro comum** de cada degrau, e o discurso de ascensão |
| **Tempo** | mais curta que as do fluxo principal (as bônus não estão cronometradas no `docs/workflow.md`; na prática, cerca de metade) |
| **Pular?** | **Sim, se você só tem um produto.** A skill se recusa a inventar uma escada artificial — e isso é o comportamento certo |

### Skill 7 — `/social-selling-comercial` (bônus)

| | |
|---|---|
| **O que faz** | Monta a sequência de prospecção pela rede social — o que acontece **antes** do lead entrar no funil comercial |
| **O que pergunta** | Qual rede é o canal principal (LinkedIn / Instagram-TikTok / os dois / nenhuma ainda) · se você já tem abordagem em uso |
| **O que entrega** | `social-selling-{negocio}.md` + `.html` — checkpoint de prontidão, sequência de 5 toques em ~2 semanas (LinkedIn) e/ou o funil de DM (Instagram), regras de compliance, e a conexão de volta ao funil comercial |
| **Tempo** | mais curta que as do fluxo principal (mesma ressalva da Skill 6: as bônus não estão cronometradas) |
| **Pular?** | **Sim, em dois casos** — veja abaixo |

### Skill 8 — `/squad-sales-bonus` (bônus)

| | |
|---|---|
| **O que faz** | Abre a porta de um squad de **14 mentes** de pré e pós-venda (produzido por Fran Martins, fora deste cohort) e faz a ponte entre o seu negócio e a mente certa — nunca framework genérico |
| **O que pergunta** | Puxa o contexto da Skill 1 se ela existir. Depois, um gate de 3 perguntas que ela **não** pula: (1) em uma frase, o que você vende · (2) qual das 4 dores descreve seu momento — prospecção seca / travado entre qualificar e fechar / cliente cancela depois de fechar / quero tudo do zero · (3) tem lead ou cliente real pra usar de exemplo? |
| **O que entrega** | `squad-sales-{negocio}.md` + `.html` — o nicho detectado e **por quê**, o fluxo escolhido, e cada peça de material com a citação de origem (*"isso vem do framework X de Y, adaptado ao seu negócio"*) |
| **Tempo** | varia com o fluxo escolhido; o de retenção e pós-venda é o mais longo |
| **Pular?** | **Sim, se você ainda não rodou a Skill 1.** Ela mesma recomenda voltar. E é bônus: nada do fluxo principal depende dela |

**Antes de rodar, ela detecta seu nicho** entre 7 perfis (infoproduto low/high-ticket, SaaS SMB/enterprise, serviços, e-commerce DTC, customizado) — e isso decide quais mentes **evitar**. O exemplo que ela mesma dá: *"SPIN Selling é overkill pra um infoproduto de R$97"*. Rodar Dream 100 num ticket baixo é o erro mais caro que essa skill pode cometer, e o gate existe pra impedir isso.

⚠️ **Ela precisa da pasta `squads/`** no seu projeto: os frameworks não estão dentro da skill, são lidos em tempo de execução de `squads/squad-sales/agents/` e `squads/squad-sales/tasks/`. Sem a pasta, ela não tem o que aplicar — veja o `R11` do [guia-baixar-e-abrir-o-projeto.md](../01-pre-requisitos/guia-baixar-e-abrir-o-projeto.md).

**As 5 mentes de pós-venda** (CS Chief, Onboarding Architect, Health Monitor, Journey Mapper, Expansion Strategist) cobrem terreno que **nenhuma** das 7 skills anteriores toca: onboarding, health score, churn, jornada e expansão de conta. Se a sua dor é "fecho, mas o cliente some", é aqui — e vale ler antes o [guia-onboarding-e-pos-venda.md](../05-depois/guia-onboarding-e-pos-venda.md).

## Quando PULAR uma skill (as situações reais)

Pular na hora certa é competência, não preguiça. As skills foram escritas pra te avisar.

| Situação | Pule | Por quê |
|---|---|---|
| **Meu negócio é autoatendimento** (e-commerce, app, assinatura sem humano no meio) | **Skill 4** | Discovery call não existe sem conversa 1:1. A própria skill avisa e manda ir pra Skill 5. As demais se adaptam: etapas viram toques digitais, gatilhos viram abandono de carrinho |
| **Só tenho um produto** | **Skill 6** | Escada de ofertas resolve problema de portfólio. Com um produto só, a skill diz: *"quando vocês tiverem um segundo produto, voltamos aqui"* |
| **Não prospecto por rede social** (só recebo lead de anúncio, indicação, ou tenho fila de espera) | **Skill 7** | Ela é opcional por natureza |
| **Meu perfil ainda não está pronto pra abordar** | **Skill 7, por enquanto** | O checkpoint dela é um bloqueio real: perfil sem autoridade (foto, bio, posts recentes), oferta de call não clara, ou nenhuma forma de organizar quem já foi abordado |
| **Ainda não rodei nem a Skill 1** | **Skill 8, por enquanto** | Ela é a mais avançada das oito e trabalha em cima do que as anteriores construíram. A própria skill recomenda voltar pro `/desenho-processo-comercial`. Se você insistir, ela roda — e registra essa escolha no documento |
| **Quero fechar a aula no essencial** | **Skills 6, 7 e 8** | Os três bônus são opcionais por definição. O fluxo principal termina na Skill 5 |

⚠️ **Sobre o checkpoint da Skill 7**, direto da Aula 1:

> *"Cuidado na prospecção com social selling: não é para todo mundo que está começando. É para quem tem um perfil preparado mínimo, pra ter essa autoridade iniciada."*
>
> *"Abordar prospect com perfil fraco queima o lead e a credibilidade antes mesmo da primeira mensagem."*

E o comentário que virou critério de ICP na mesma aula: se a empresa que você quer prospectar **nem tem LinkedIn**, isso pode ser um indício forte de que ela está fora do seu ICP — ou de que o LinkedIn não é o canal certo pro seu público.

### Os nomes que vão aparecer no seu entregável

A sequência do LinkedIn não vem numerada de 1 a 5: vem **com nome em cada toque**, e são termos em inglês. Tradução:

| Toque | Nome no documento | O que é, na prática | Quando |
|---|---|---|---|
| 1 | **Profile View** | você só **visita o perfil** dele. Ele recebe a notificação de que você olhou | dia -1 |
| 2 | **Connect** | convite de conexão **com nota curta e personalizada** — nunca o convite vazio | dia 0 |
| 3 | **Engage** | curtir e comentar 2-3 posts dele. Comentário de gente, não "ótimo post!" | dias 2-5 |
| 4 | **Value DM** | primeira mensagem: você **entrega algo** (dado, insight, material) e **não pede nada** | dia 7 |
| 5 | **Bridge DM** | a ponte: conecta ao problema dele e convida pra conversa | dia 14 |

⚠️ **A regra que dá nome ao método:** nunca pule direto pro **Bridge DM**. É exatamente isso que separa social selling de spam — e é também o que mantém sua taxa de aceite acima da linha de corte (ver limites abaixo).

**No Instagram/TikTok o método tem outro nome:** *Social Selling 2.0*, e a lógica muda. Em vez de 5 toques cronometrados, é um funil: encontrar o lead por palavra-chave → **pré-aquecimento obrigatório** (curtir 2-3 posts e reagir a um story **antes** de qualquer mensagem) → abertura que termina em pergunta aberta e **nunca vende nada** → condução com etiquetas pra não perder o fio → qualificação e agendamento.

⚠️ **O pré-aquecimento não é etiqueta, é o que tira a sua mensagem da "caixa de spam mental" do lead.** Pular ele é o erro nº 1 do Instagram.

### O limite que a skill não te conta (e a plataforma impõe)

A sequência de 5 toques da Skill 7 é boa, mas o LinkedIn tem teto próprio. Vale saber antes de montar a operação:

| Restrição | Número de referência (2026) |
|---|---|
| Convites de conexão por semana | ~100 em conta gratuita e Premium; 150-200 em Sales Navigator |
| Taxa de aceite que dispara restrição | abaixo de ~30%, o algoritmo trata sua abordagem como spam e aperta o limite |
| Conta nova ou recém-restringida | rampa de 4 a 6 semanas — comece com ~5 convites por dia |

⚠️ **Isso reforça o checkpoint da skill em vez de contradizê-lo:** perfil fraco → aceite baixo → restrição de conta. O "pré-aquecimento obrigatório" (visitar perfil, curtir, comentar antes de convidar) não é só etiqueta — é o que mantém a taxa de aceite acima da linha de corte.

Se você precisa de volume maior que isso, o caminho não é forçar o LinkedIn: é combinar canais, que é exatamente a regra transversal da skill (*"social selling amplifica, nunca substitui"*).

## Se você digitar o nome errado

O `docs/SKILLS-INDEX.md` mapeia os apelidos. Os que mais confundem:

| Você digitou | Provavelmente queria |
|---|---|
| `/funil-de-vendas` | **cuidado**: pode ser a Skill 1 (funil comercial) ou a Skill 6 (escada). Veja [guia-os-tres-funis.md](../02-conhecimento-minimo/guia-os-tres-funis.md) |
| `/processo-comercial`, `/desenhar-funil`, `/etapas-de-venda` | `/desenho-processo-comercial` |
| `/follow-up`, `/cadencia-de-mensagens`, `/regua-de-comunicacao` | `/regua-comunicacao-comercial` |
| `/bant`, `/gpct`, `/icp`, `/qualificar-leads` | `/qualificacao-bant-gpct` |
| `/discovery`, `/roteiro-de-descoberta` | `/discovery-script` |
| `/playbook`, `/objecoes`, `/biblioteca-de-objecoes` | `/playbook-vendas-vivo` |
| `/value-ladder`, `/escada-de-produtos` | `/escada-de-ofertas` |
| `/social-selling`, `/vender-por-dm`, `/linkedin-outreach` | `/social-selling-comercial` |
| `/squad`, `/squad-sales`, `/mentes-de-venda`, `/prospeccao-fanatica`, `/negociacao`, `/churn`, `/pos-venda` | `/squad-sales-bonus` |
| `/crm`, `/higiene`, `/limpar-base` | `/montagem-higiene-crm` (**Aula 2**) |
| `/lead-scoring`, `/pontuar-leads`, `/temperatura` | `/lead-scoring-ia` (**Aula 2**) |
| `/gargalo`, `/funil-por-numero`, `/conversao` | `/diagnostico-gargalos-funil` (**Aula 2**) |

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Saber onde eu parei** | dentro de qualquer skill: `me mostra onde eu estou` — todas têm essa resposta pronta, com o que falta pra entrega ficar 10/10 |
| **Descobrir a próxima skill** | "Olhe os arquivos desta pasta e me diga quais skills da Aula 1 já entregaram, qual é a próxima na ordem, e se alguma se aplica ao meu caso ([descreva seu negócio em 2 linhas])." |
| **Saber se posso pular alguma** | "Meu negócio é [descreva: com vendedor ou autoatendimento, quantos produtos, prospecto por rede social ou não]. Das skills da Aula 1, quais se aplicam a mim e quais eu posso pular sem prejuízo? Justifique cada pulo." |
| **Retomar depois de dias parado** | "Faz [X] dias que não mexo nisso. Leia os arquivos da pasta, me diga em 5 linhas o que eu já construí, e qual é o próximo comando a rodar." |
| **A skill parou no meio** | `continue de onde você parou` — e, se o arquivo ficou incompleto: "releia o arquivo `[nome]` e complete o que faltou, sem reescrever o que já está pronto" |

## Teste de sucesso

Depois de rodar a Skill 1, abra o `central-de-entregas.html` na raiz do projeto.

**Funcionou se:** a barra de progresso mostra **1 de 8 entregues**, o card 1 está aceso com badge **Pronto** e dois links (Abrir HTML / Abrir MD), e os outros 7 estão apagados com "Aguardando /comando".

**A régua de "terminei":** ao fim da aula, o fluxo principal completo é **5 de 8** — e isso já é resultado completo. Os cards 6, 7 e 8 são bônus: só acendem se aplicarem ao seu caso. **Não persiga 8 de 8.** Rodar a Escada de Ofertas com um produto só, ou o Squad Sales sem ter o processo desenhado, produz documento bonito e inútil.

⚠️ O rótulo de cada card diz `/ 7` mesmo com 8 cards — é um texto fixo do template que não acompanhou a entrada do bônus. A barra de progresso conta certo. Veja `EN11` em [guia-entregaveis-e-central.md](guia-entregaveis-e-central.md).

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| SK1 | Rodei a Skill 3 e ela me perguntou tudo de novo | A Skill 1 não rodou, ou o `.md` dela não está na pasta aberta | 1) confirme com `ls *.md` que o `processo-comercial-*.md` está lá 2) se estiver, aponte: *"leia `processo-comercial-x.md` antes de continuar"* |
| SK2 | A Skill 4 disse que "não se aplica" ao meu negócio | Seu modelo é autoatendimento | comportamento correto: pule pra Skill 5, como ela sugere |
| SK3 | A Skill 6 se recusou a rodar | Você tem um produto só | comportamento correto. **5 de 8 é entrega completa no seu caso** — os bônus não contam como pendência |
| SK4 | A Skill 7 me travou num checkpoint | Perfil sem autoridade, oferta de call vaga, ou sem forma de organizar prospects | resolva o item que faltou **antes** de gerar a sequência: sequência de mensagens não compensa perfil fraco |
| SK5 | Rodei fora de ordem e agora está tudo desencontrado | Cada skill herda da anterior | 1) rode a Skill 1 primeiro 2) re-rode as posteriores na ordem — elas puxam o contexto novo 3) veja [guia-revisar-e-corrigir.md](guia-revisar-e-corrigir.md) |
| SK6 | A Skill 4 está demorando muito | Esperado: ela escreve uma peça de copy por linha da régua | espere. Se der erro de API no meio, peça *"continue de onde você parou"* ([guia-modelo-e-custo.md](../01-pre-requisitos/guia-modelo-e-custo.md)) |
| SK7 | O playbook saiu com objeções que não são as minhas | Você escolheu a opção 2 (partir das típicas do nicho) | é o modo "ponto de partida a validar". Levante 5 objeções reais e rode de novo |
| SK8 | Digitei o comando e apareceu "No commands match" | Ferramenta aberta na pasta errada | veja o `R6` do [guia-baixar-e-abrir-o-projeto.md](../01-pre-requisitos/guia-baixar-e-abrir-o-projeto.md) |
| SK9 | Não sei em qual skill eu parei | Perdeu o fio entre sessões | 1) abra o `central-de-entregas.html` 2) ou peça, dentro de qualquer skill: **"me mostra onde eu estou"** |
| SK10 | A Skill 8 me fez três perguntas e não avançou enquanto eu não respondi | É o gate obrigatório dela (Passo 0.5) | comportamento correto. Responda a pergunta 2 escolhendo **uma** das quatro dores — resposta vaga tipo "quero vender mais" faz ela repetir a pergunta, de propósito |
| SK11 | A Skill 8 rodou mas o material saiu genérico, sem citar mentor nenhum | Ela não conseguiu ler os arquivos das mentes | 1) `ls squads/squad-sales/agents` — se der erro, falta a pasta `squads/` (veja `R11` do [guia-baixar-e-abrir-o-projeto.md](../01-pre-requisitos/guia-baixar-e-abrir-o-projeto.md)) 2) com a pasta no lugar, rode de novo — cada peça tem que vir com *"isso vem do framework X de Y"* |
| SK12 | Vejo 11 pastas em `.claude/skills`, mas este guia só fala de 8 | As 3 a mais são da **Aula 2** | não é erro. Elas ficam disponíveis desde o primeiro dia e têm numeração própria (`1/3`). Rode na ordem da aula, não na ordem do `ls` |

**Se nada resolver:** dentro da skill, digite `me mostra onde eu estou`. Todas têm essa resposta pronta.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | rode a próxima skill da sequência que ainda está apagada na Central de Entregas |
| 📖 Ler | [guia-revisar-e-corrigir.md](guia-revisar-e-corrigir.md) — **leia antes de aprovar o primeiro entregável**, é a regra que evita retrabalho em todas as skills seguintes |
| 📖 Ler | [guia-entregaveis-e-central.md](guia-entregaveis-e-central.md) — onde os arquivos caem e como ler as duas Centrais |
| 🚑 Se travar | o catálogo SK1–SK12 acima |
