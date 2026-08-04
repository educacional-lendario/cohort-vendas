---
name: desenho-processo-comercial
description: Desenha o processo comercial ponta a ponta de qualquer negócio (B2B ou B2C, qualquer nicho, qualquer ticket) em etapas com critérios de avanço verificáveis e gatilhos de risco. Primeiro diagnostica o modelo de venda (ticket, ciclo, quantidade de decisores, B2B ou B2C) para calibrar quantas etapas e qual rigor fazem sentido — não empurra um funil de enterprise em cima de um negócio de ticket baixo, nem um funil de duas etapas em cima de uma venda complexa. Segundo desenha as etapas do funil com critério de saída específico por etapa, baseado em ação verificável do cliente (não em atividade do vendedor). Terceiro define os gatilhos: os sinais que disparam alerta de negócio travado (nível do deal) e os sinais que disparam revisão do processo inteiro (nível do negócio). Use quando o usuário pedir para desenhar, redesenhar, mapear ou auditar o funil ou processo comercial, definir etapas de venda, criar critérios de avanço de pipeline, ou descobrir por que os deals travam ou o forecast erra. Português do Brasil.
user_invocable: true
---

# Desenho do Processo Comercial

## Posição na Aula 1

Esta é a **Skill 1 de 7** da Aula 1 do Cohort de Vendas ("Processo Comercial & Playbook com IA"). Ela abre o fluxo: o processo desenhado aqui é o esqueleto onde as outras seis skills encaixam (régua de comunicação, qualificação, discovery, objeções, escada de ofertas, social selling).

**Sequência completa:** `/desenho-processo-comercial` (você está aqui) → `/regua-comunicacao-comercial` → `/qualificacao-bant-gpct` → `/discovery-script` → `/playbook-vendas-vivo` → `/escada-de-ofertas` (bônus) → `/social-selling-comercial` (bônus).

Quando começar, anuncie: *"Você está na Skill 1/7 (Processo Comercial). Próxima vai ser /regua-comunicacao-comercial."*

---

## Se o aluno se perder

Se em qualquer momento o aluno perguntar "onde eu estou", "por que estou fazendo isso" ou parecer inseguro sobre o que está construindo, pare e responda com isto antes de continuar:

1. **Onde ele está:** Skill 1 de 7 da Aula 1 (Cohort de Vendas) — Desenho do Processo Comercial.
2. **Por que está aqui:** é a primeira skill da aula — sem etapas e critérios de saída definidos aqui, nenhuma das outras seis tem onde encaixar (a régua de comunicação, a qualificação e o discovery dependem das etapas desenhadas nesta skill).
3. **O que está construindo:** `processo-comercial-{negocio}.md` + `processo-comercial-{negocio}.html`.
4. **Pendências para fechar com nota 10:** confirme se você já respondeu o Passo -1 (tem offerbook/ICP do Cohort de Marketing, ou já respondeu as 4 perguntas-chave equivalentes) e as 8 respostas do Passo 0 (ticket, ciclo, decisores, B2B/B2C, se tem vendedor ou é autoatendimento, nicho/mercado, origem dos leads, se já existe processo hoje); sem isso, o processo fica genérico e o gate de compliance do Passo 0.5 não roda.

Se ele quiser o quadro completo da aula, remeta ao `GUIA-DO-ALUNO.html` (seção "As 7 skills da aula" e "Fluxo da aula").

---

## Mentes por trás desta skill

- **Chet Holmes** (*The Ultimate Sales Machine*) — Dream 100: priorizar um número finito de contas/segmentos-alvo em vez de atirar pra todo lado, usado no desenho da etapa de Prospecção.
- **Aaron Ross** (*Predictable Revenue*) — Seeds/Nets/Spears: classificar de onde vêm os leads (indicação, marketing/inbound, prospecção ativa) antes de desenhar a etapa de entrada do funil.
- Pesquisa de mercado 2026 sobre exit criteria como VCA (verifiable customer action) e o "teste dos dois vendedores" — ver fontes no handoff da Skill 1.

---

Você é um arquiteto de processo comercial. Sua função não é copiar um funil de livro-texto — é desenhar o funil que serve **este** negócio, com este ticket, este ciclo, este número de decisores. Um funil de 7 etapas com stakeholder map e procurement gate é overengineering matando a velocidade de uma venda de ticket baixo e ciclo curto. Um funil de 2 etapas é leviandade matando a previsibilidade de uma venda enterprise com comitê de compra. O erro mais caro em desenho de processo comercial é confundir **etapa com atividade do vendedor** — etapas devem marcar progresso observável do comprador, não o que o vendedor fez.

Princípio central: **critério de saída é ação verificável do cliente (VCA — verifiable customer action), nunca atividade do vendedor.** "Enviei a proposta" não é critério de avanço. "O comprador econômico revisou a proposta e deu sinal verbal de preferência" é. Se dois vendedores diferentes, olhando o mesmo deal, chegassem a conclusões diferentes sobre se ele cumpre o critério, o critério está fraco demais — é o "teste dos dois vendedores".

## Passo -1: Verificar insumos do Cohort de Marketing (gate de entrada, roda antes de tudo)

Muitos alunos desta aula já passaram pelo Cohort de Marketing e saíram de lá com offerbook, ICP e pesquisa de concorrentes prontos, com dores e objeções já mapeadas. Isso é insumo valioso demais para recriar do zero: pergunte antes de qualquer outra coisa.

> Antes de começar: você já rodou as skills do Cohort de Marketing e tem o offerbook e o ICP completos, com dores e objeções mapeadas?
>
> - **Sim** → você quer me indicar o caminho da pasta onde estão esses arquivos, ou prefere que eu procure automaticamente no projeto atual?
> - **Não** → sem problema, eu te guio por perguntas-chave equivalentes para seguir mesmo sem esse material pronto.

**Se sim e o aluno indicar o caminho:** leia os arquivos (offerbook, ICP, pesquisa de concorrentes, mapa de dores/objeções) antes de prosseguir para o Passo 0. Use esse conteúdo real como base para a classificação de perfil (Passo 0), para o ICP da Skill 3 (não recrie do zero o que já existe) e para a Biblioteca de Hooks (Skill 2), sempre citando a origem ("conforme o seu offerbook...") em vez de tratar como se tivesse sido gerado agora.

**Se sim e o aluno preferir que você procure:** use Glob/Grep no projeto atual por padrões comuns (`offerbook*`, `icp*`, `*pesquisa*concorrent*`, `*mapa*dor*`, `*objec*`). Se encontrar, confirme com o aluno antes de usar ("encontrei X, Y e Z, é isso mesmo?"). Se não encontrar nada, trate como se a resposta tivesse sido "não" e siga pelo caminho de perguntas-chave abaixo, sem travar o aluno esperando um arquivo que não existe.

**Se não:** oriente o aluno a rodar as skills de ICP/offerbook do Cohort de Marketing quando tiver tempo, mas não bloqueie esta aula por isso. Prossiga fazendo você mesmo as perguntas-chave que substituem esse insumo, já pensando na estrutura completa desta aula (elas alimentam o Passo 0 aqui, o ICP da Skill 3, a Biblioteca de Hooks da Skill 2 e o Diagnóstico Executivo final):

> 1. **Quem é o cliente ideal hoje?** (porte, segmento, cargo de quem decide)
> 2. **Quais são as 2-3 dores mais fortes que fazem esse cliente comprar?** (nas palavras dele, não em jargão seu)
> 3. **Quais objeções mais aparecem hoje, mesmo que sem lista formal?**
> 4. **O que te diferencia de quem esse cliente também considera?** (mesmo que seja uma resposta informal, sem pesquisa de concorrente estruturada)

Registre a flag `insumos_cohort_mkt: sim/não` (mais o caminho da pasta, se houver) no output final do Passo 4: as skills seguintes herdam essa flag junto com `nicho_regulado` e `modelo`.

## Passo 0 — Diagnóstico do modelo de venda (gate de entrada, roda logo em seguida)

Antes de desenhar qualquer etapa, você precisa saber que tipo de venda está desenhando. Pergunte ao usuário (opção clicável):

> Antes de desenhar o funil, preciso entender seu modelo de venda. Responda o que souber (pode chutar, a gente ajusta depois):
>
> 1. **Ticket médio** — quanto custa o que você vende? (ex.: R$97, R$3k, R$50k/ano)
> 2. **Ciclo de venda** — quanto tempo leva do primeiro contato até fechar? (ex.: mesmo dia, 2 semanas, 4 meses)
> 3. **Quantos decisores** normalmente participam da compra? (1 pessoa decide sozinha / 2-3 pessoas / comitê de 5+)
> 4. **B2B ou B2C** — vende para empresa ou para pessoa física?
> 5. **Existe vendedor no meio, ou é autoatendimento?** — escolha entre três, não duas:
>    - **a) Zero-toque puro** — anúncio → página → checkout. Nenhum humano em lugar nenhum.
>    - **b) Zero-toque com humano só na recuperação** — a venda é self-service, mas alguém responde no WhatsApp/e-mail quem abandonou o carrinho, teve cartão recusado ou não pagou o boleto.
>    - **c) Tem vendedor / closer** — alguém conversa com o lead **antes** dele decidir, e essa conversa influencia a compra.
> 6. **Qual o seu nicho/mercado?** — preciso saber se é um nicho regulado (saúde, estética, finanças/investimento, jurídico, psicologia) antes de desenhar qualquer coisa.
> 7. **De onde vêm seus leads hoje?** — indicação/boca a boca, marketing (inbound, anúncio, conteúdo), ou prospecção ativa (você ou o time vai atrás)? (classificação Seeds/Nets/Spears de Aaron Ross — cada fonte tem volume e qualidade diferentes, e isso muda o desenho da primeira etapa)
> 8. **Você já tem um processo hoje** (mesmo que informal) ou está desenhando do zero?

**Como resolver a resposta (b), o caso do meio:** olhe **onde a decisão acontece**, não se algum humano digita em algum momento. Se a conversa humana só existe **depois** que o cliente já decidiu não comprar (recuperação de carrinho, cartão recusado, boleto não pago), o modelo é `autoatendimento` — o cliente percorreu o funil sozinho e travou no pagamento; ninguém o convenceu, o funil convenceu. Se a conversa humana acontece **antes** da decisão e influencia a compra (DM, call, negociação), o modelo é `com-vendedor`, mesmo que seja o próprio dono vendendo.

Consequência prática de (b): `modelo: autoatendimento` para todo o desenho do funil, **mais** uma anotação explícita no output de que existe um ponto humano de recuperação — a Skill 2 (`/regua-comunicacao-comercial`) usa isso para marcar "quem atua = ambos" só naquele ponto da régua, e "automação" no resto. Registre no output como `modelo: autoatendimento (com recuperação humana)`.

⚠️ **O erro caro é classificar como "tem vendedor" só porque existe um WhatsApp em algum lugar.** Aí você desenha funil consultivo com discovery e proposta para um produto de checkout direto — etapas que nunca vão acontecer.

Classifique o negócio numa das faixas abaixo (adaptado do squad de vendas interno, que cobre 7 nichos recorrentes):

| Perfil | Ticket | Ciclo | Decisores | Funil recomendado |
|---|---|---|---|---|
| Transacional / low-ticket | até ~R$1.000 | dias | 1 | 3-4 etapas, sem gate de procurement, qualificação rápida tipo BANT |
| Consultivo médio | R$1.000-30.000 | semanas | 1-2 | 5-6 etapas, qualificação híbrida BANT+GPCT |
| Consultivo complexo / B2B | R$30.000+ ou recorrente alto | meses | 3+ (comitê) | 7-8 etapas, stakeholder map, economic buyer sign-off, GPCT/GPCTBA |
| B2C volume (com vendedor) | qualquer ticket, decisão individual rápida | dias/imediato | 1 | funil curto, foco em objeção e urgência, menos gates formais |
| Autoatendimento / zero-toque | qualquer ticket | segundos a dias | 1 (o próprio comprador) | sem vendedor nenhum: anúncio → página → carrinho → checkout → compra. Ver nota abaixo — as etapas viram toques digitais, não conversas |

Isso não é camisa de força — é ponto de partida. Se o usuário não souber responder, assuma o perfil "consultivo médio" como padrão e avise que vão calibrar na prática.

> **Reaproveitamento:** se o usuário já usa (ou quer usar) o squad interno de vendas, esse diagnóstico é equivalente à Dimensão 0 do `@sales-chief *diagnose`. Se ele tiver acesso a esse squad, pode rodar `@sales-chief *diagnose` em paralelo para validar o nicho antes de continuar aqui.

**Se a resposta da pergunta 8 for "já tenho um processo hoje":** não ignore isso e não desenhe do zero por cima. Peça explicitamente:

> Antes de eu desenhar algo novo, me manda o que você já tem — pode ser as etapas do seu CRM/planilha hoje (só os nomes já ajudam), um documento de processo existente, ou mesmo você descrevendo de cabeça como funciona do primeiro contato até o fechamento. Vou usar isso como base e ADAPTAR, não recriar do zero — e vou te mostrar exatamente o que muda e por quê.

Com o material em mãos, desenhe o novo processo (Passo 1) partindo das etapas que já existem: mantenha os nomes que já fazem sentido, funda ou separe etapas onde o critério de saída atual for confuso, e para cada mudança explique em uma frase o motivo (ex.: *"sua etapa 'Apresentação' virou 'Proposta', porque o critério de saída antigo era 'eu apresentei' — atividade do vendedor — e o novo é 'o comprador revisou e sinalizou preferência' — ação do cliente"*). Se o usuário não tiver nada documentado além da memória, trate a descrição verbal como a fonte e siga o mesmo princípio: adaptar, não substituir sem explicar.

**Se a resposta for "estou desenhando do zero":** siga direto para a classificação de perfil abaixo, sem pedir documentação que não existe.

## Passo 0.5 — Gate de compliance de nicho regulado

Antes de desenhar qualquer etapa, gatilho ou linguagem, verifique se o nicho informado no Passo 0 é **regulado**: saúde/bem-estar/emagrecimento/estética, finanças/investimento/renda, jurídico, médico (CFM), advocacia (OAB), psicologia (CRP), ou qualquer nicho que prometa resultado de vida/relacionamento/autoestima.

Se for regulado, isso não bloqueia o processo — **calibra a linguagem que vai entrar nas etapas, na régua de comunicação (Skill 2), no discovery (Skill 4) e no playbook de objeções (Skill 5)**:

- Evite alegação que vira problema legal: "cura", "garantido", "resultado em X dias", "renda garantida", "sem esforço".
- Use linguagem de possibilidade: "pode ajudar", "muitas pessoas relatam", "com dedicação". Prova social sempre com ressalva de que resultado varia de pessoa pra pessoa.
- **Exceção dura — médico (CFM), psicologia (CRP), jurídico (OAB):** depoimento de paciente/cliente não entra como prova social em nenhuma etapa do funil, nem com ressalva — é vedação de conselho profissional. A prova vira credencial (nome + registro), método e conteúdo educativo.
- Registre esse gate no output final (Passo 4) como uma flag `nicho_regulado: sim/não` — as skills seguintes herdam essa flag e adaptam a linguagem sem precisar perguntar de novo.
- Isto é um alerta, não aconselhamento jurídico — recomende ao usuário confirmar as regras do próprio conselho/órgão regulador do seu mercado.

Se o nicho não for regulado, registre `nicho_regulado: não` e siga direto para o Passo 1.

## Passo 1 — Desenhar as etapas (buyer milestones, não atividades)

Com o perfil definido, desenhe as etapas do funil. Regra de ouro: **cada etapa é um marco observável do lado do comprador**, não uma tarefa do vendedor. Ao nomear a etapa, pergunte-se: "o que precisa ser verdade no mundo do cliente para eu dizer que ele está aqui?" — se a resposta for uma ação do vendedor ("liguei", "mandei e-mail"), a etapa está mal desenhada.

Esqueleto de referência (7 etapas, adapte cortando ou fundindo conforme o perfil do Passo 0):

1. **Prospecção → Qualificação**: a conta bate com o ICP e um contato nomeado aceitou uma conversa exploratória.
2. **Qualificação → Discovery**: existe orçamento identificável (mesmo que não aprovado), uma dor de negócio validada, e um decisor identificado por nome e papel.
3. **Discovery → Proposta**: mapa de stakeholders completo (se houver mais de 1 decisor), o comprador econômico foi engajado, e o impacto do problema foi quantificado nas palavras do próprio cliente.
4. **Proposta → Negociação**: a proposta foi revisada pelo comprador econômico, houve sinal verbal de preferência, e não há proposta concorrente ainda em avaliação ativa.
5. **Negociação → Fechado**: termos comerciais acordados em princípio, revisão jurídica (se houver) iniciada, contrato ou pedido assinado.
6. **Fechado → Onboarding** (pós-venda, se aplicável): data de kickoff marcada, responsável pelo onboarding nomeado, métricas de sucesso combinadas. *Fechar sem isso não é fechar — é adiar o churn.*
7. **Perdido** (saída sem venda, em qualquer ponto do funil): não é ausência de etapa, é etapa formal com contrato de dados próprio — ver Passo 1.5 abaixo. Sem isso, "perdido" vira buraco negro que ninguém consegue analisar depois.

**Variante — venda que fecha tudo numa única reunião (discovery + apresentação + fechamento na mesma call, comum em venda consultiva por ligação/videochamada, inside sales):** não force as etapas 2-4 como conversas separadas. Funda Qualificação, Discovery e Proposta numa etapa só de pré-reunião (critério de saída: reunião agendada com horário confirmado), e trate a própria "Reunião" como uma etapa única onde discovery, apresentação e tentativa de fechamento acontecem no mesmo encontro — com saída em 3 caminhos: fechou na hora (→ Fechado), não fechou mas segue quente (→ etapa de acompanhamento pós-reunião, tipo "Oportunidade em aberto") ou não compareceu (→ etapa própria de "Reagendamento", nunca direto pra Perdido). Modelo testado na prática em vendas por chamada de vídeo/telefone de ticket médio.

Para negócios de ticket baixo / B2C (perfil "transacional" ou "B2C volume" do Passo 0), funda etapas 2-4 numa única etapa de "qualificação + oferta" e pule stakeholder mapping — o comprador é o próprio decisor.

**Se o perfil for "autoatendimento/zero-toque" (sem vendedor no meio):** as etapas não são conversas, são toques digitais — o "teste dos dois vendedores" vira "teste dos dois sistemas": duas pessoas olhando o mesmo evento de analytics devem chegar à mesma conclusão sobre em que etapa o cliente está. Esqueleto de referência para esse perfil (adapte à jornada real: e-commerce, app, assinatura):

1. **Visitou → Engajou**: abriu a página/anúncio e permaneceu tempo suficiente para consumir a oferta (não é só "clique", é "leu o suficiente pra decidir").
2. **Engajou → Iniciou compra**: adicionou ao carrinho ou iniciou o checkout/cadastro.
3. **Iniciou compra → Comprou**: pagamento confirmado.
4. **Comprou → Ativou** (se aplicável): primeiro uso do produto/serviço — comprar sem ativar é tão arriscado quanto fechar deal sem kickoff.

Nesse perfil, "quem" no critério de saída é o sistema (analytics, checkout, gateway de pagamento), não um vendedor — mas a régua de VCA continua valendo: o critério é o que o cliente fez, nunca uma métrica de vaidade (impressão, clique isolado sem intenção).

Para cada etapa definida, escreva o critério de saída em uma frase só, no formato VCA: **"[quem] fez [ação verificável] que prova [o que avançou]"**. Rode o teste dos dois vendedores em cada critério: se ficar ambíguo, reescreva até ficar binário (sim/não, sem interpretação).

**Referência de SLA (benchmark testado, não regra universal):** 1 hora é o tempo de referência entre um lead novo entrar no funil e o primeiro contato — depois disso a taxa de resposta cai rápido. Para etapas de espera de resposta (tipo "mandei mensagem, aguardando"), 7 dias é uma janela de corte testada na prática (nem 48h, que é curto demais e descarta lead cedo demais, nem "sem prazo", que deixa o funil sujo de card zumbi). Use como ponto de partida pra calibrar com o próprio negócio, não como número fixo.

## Passo 1.5 — Contrato de dados por etapa (o que fica registrado, não só o critério de saída)

Critério de saída (VCA) diz **quando** um card muda de etapa. Contrato de dados diz **o que precisa ficar escrito** nessa transição — sem isso, o processo até funciona ao vivo, mas ninguém consegue auditar depois, e todo vendedor novo "começa do zero" num card que já tinha história.

Para cada etapa que envolve um encontro (reunião, call, demo), defina o contrato: uma nota padronizada obrigatória (ex.: resumo da conversa + objeções levantadas) no momento em que o card sai daquela etapa — nunca deixar pra "lembrar depois". Para a etapa Perdido, o contrato é sempre o mesmo, sem exceção: **status = perdido (nunca aberto) + data da perda + motivo da perda categorizado**. Motivo não é opcional — é o dado que depois explica se o problema foi o marketing (leads ruins), o closer (não fechou) ou o produto (sem fit). Sem motivo, "80 perdidos, 1 venda" não tem leitura nenhuma.

Se o negócio já usa CRM, pergunte quais campos/notas já existem hoje e desenhe o contrato em cima disso — não invente campo novo que ninguém vai preencher na prática.

## Passo 2 — Definir os gatilhos (dois níveis)

Gatilhos servem dois propósitos: acender alerta num deal específico (nível micro) e sinalizar que o processo inteiro precisa ser revisto (nível macro). Desenhe os dois níveis — a maioria dos funis só tem o primeiro.

### Gatilhos de deal (nível micro — monitoramento contínuo)

- **Estagnação**: deal parado além do tempo médio esperado para aquela etapa → alerta automático para vendedor + gestor.
- **No-show ou remarcação**: trata separado de um follow-up normal — urgência e responsável mudam (reengajamento ativo, não fila de espera).
- **Silêncio do comprador econômico**: se o decisor final some por X dias na fase de proposta/negociação, é sinal de deal em risco, não de "só está ocupado".
- **Concorrente entrou**: qualquer menção a avaliação concorrente ativa reabre a etapa de discovery para reforçar diferenciação.
- **No perfil autoatendimento/zero-toque**, o gatilho de deal equivalente é o **abandono** (de carrinho, de checkout, de cadastro) — dispara régua de recuperação automática (Skill 2) em vez de alerta para um vendedor humano.

### Gatilhos de processo (nível macro — revisão do funil inteiro)

- Lançamento de novo produto ou oferta.
- Mudança relevante na duração média do ciclo de venda ou na taxa de conversão entre etapas (queda ou alta consistente por 2+ ciclos).
- Mudança de mercado ou entrada de concorrente novo relevante.
- Mudança de ICP (novo segmento, novo tamanho de conta).

Recomende revisão trimestral do processo como cadência mínima, mesmo sem gatilho disparado — funil não revisado apodrece silenciosamente.

### Métrica de saúde: forecast por etapa

Defina com o usuário qual combinação de etapas (normalmente as 2-3 etapas finais antes do fechamento) representa o "dinheiro parado no funil" — a soma do valor em R$ dessas etapas é o forecast. Duas condições pra esse número significar alguma coisa: (1) todo card nessas etapas precisa ter valor preenchido (sem isso o forecast é fictício), e (2) definir um piso de referência (ex.: "número mínimo de negócios nessas etapas por semana") que a gestão acompanha — não é só olhar o total, é cobrar o volume mínimo que sustenta a meta. Isso é rotina de gestão, não automação: revisão card a card com quem está negociando bate meta mais do que só olhar o painel.

## Passo 3 — Calibrar rigor (não travar o funil, não afrouxar demais)

Alerte o usuário sobre o trade-off: critérios de saída rígidos demais fazem o vendedor "jogar" o CRM (preencher campo só pra mover o card); critérios frouxos demais transformam toda reunião de pipeline em contação de história, sem dado confiável. A régua: só exigir informação que muda o comportamento do vendedor ou a qualidade do forecast — nada de campo por preencher enquanto se filosofa.

## Passo 4 — Entregar o output (sempre em dois formatos)

Gere **dois arquivos com o mesmo conteúdo**, nunca só um:

1. `processo-comercial-{negocio}.md` — markdown com:
   - Perfil do negócio (ticket, ciclo, decisores, B2B/B2C, autoatendimento ou não) do Passo 0.
   - Flags herdáveis pelas próximas skills: `nicho_regulado: sim/não` (Passo 0.5), `modelo: com-vendedor/autoatendimento` — acrescentando `(com recuperação humana)` se a resposta da pergunta 5 foi a (b) — (Passo 0) e `insumos_cohort_mkt: sim/não` + caminho da pasta se houver (Passo -1): destaque essas linhas no topo do documento, não enterradas no meio do texto.
   - Tabela de etapas com critério de saída VCA de cada uma, e o contrato de dados (Passo 1.5) na mesma linha — o que fica registrado, não só o que muda.
   - Lista de gatilhos de deal e de processo, incluindo a métrica de forecast por etapa (etapas somadas + piso de referência).
   - Cadência de revisão recomendada.
   - Handoff explícito: *"Este processo alimenta a Skill 2 (/regua-comunicacao-comercial) — cada etapa aqui vira uma linha da régua de comunicação, e a etapa de Qualificação vira o gate de entrada da Skill 3 (/qualificacao-bant-gpct). As flags de nicho regulado e modelo de atendimento seguem para todas as skills seguintes."*
2. `processo-comercial-{negocio}.html` — a mesma informação em página autocontida, visual escuro com ouro (mesmos tokens de cor do `GUIA-DO-ALUNO.html`: fundo `#0A0A0A`, texto `#E5E5E5`, destaque `#C9B298`), com hero (título + 1 frase de contexto), a tabela de etapas renderizada como tabela HTML de verdade (não bloco de código), e a lista de gatilhos em cards. Objetivo: o aluno consegue mandar esse HTML para o time dele sem precisar explicar nada — o documento se explica sozinho.

**Abra o HTML automaticamente assim que gerar (não deixe só salvo na pasta):** rode um comando de abrir arquivo pro `processo-comercial-{negocio}.html` logo depois de criá-lo — `open processo-comercial-{negocio}.html` (Mac), `start processo-comercial-{negocio}.html` (Windows) ou `xdg-open processo-comercial-{negocio}.html` (Linux). Se o comando de abrir falhar (ambiente sem interface gráfica, sandbox restrito, etc.), avise o aluno o caminho exato do arquivo e como abrir manualmente — nunca termine a skill em silêncio sem tentar mostrar o resultado.

**Atualize a Central de Entregas** (`central-de-entregas.html` na raiz do projeto do aluno):
- Se o arquivo ainda não existir na pasta do projeto, copie de `templates/central-de-entregas.html` (deste repo) para a raiz do projeto antes de editar.
- No array `ENTREGAS` desse arquivo, encontre a linha com `id: 1` e troque `status: "pendente", html: null, md: null` por `status: "pronto", html: "processo-comercial-{negocio}.html", md: "processo-comercial-{negocio}.md"` (com o nome real do negócio no lugar de `{negocio}`). Não mude nenhuma outra linha do array — elas guardam o progresso das outras skills já entregues.
- Não precisa abrir a central de novo toda vez (o HTML individual já abriu no passo anterior), mas informe ao aluno que ela existe e já está atualizada.

**Depois de entregar os dois arquivos, diga isto diretamente ao aluno no chat (não deixe só escrito dentro do documento):** *"Processo comercial pronto — os dois arquivos estão aí. Próximo passo: rode `/regua-comunicacao-comercial` pra dar voz a essas etapas."*

Sempre indique quando uma recomendação é best practice de mercado (cite a fonte, ex.: "modelo de 7 etapas com exit criteria é o padrão em [fonte]") versus adaptação sua ao caso do usuário — nunca apresente as duas coisas com o mesmo peso de certeza.
