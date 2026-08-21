# GUIA OS TRÊS FUNIS — funil de marketing × funil comercial × escada de ofertas

> **Estou perdido em:** "qual é a diferença entre a aula de funil do marketing e esta aqui? Parece a mesma coisa com nome diferente".
> **O que você vai ter no final:** os três funis separados na sua cabeça de uma vez por todas, sabendo qual documento resolve qual problema — e por que misturar os três é o erro que mais confunde a turma.
> **Fontes cruzadas:** o `docs/SKILLS-INDEX.md` deste repo (seção *"Cuidado com a confusão 'funil comercial' x 'funil de vendas'"*, escrita justamente porque o aluno pergunta) · o `SKILL.md` da `/escada-de-ofertas` (Passo 4, "Conectar de volta ao funil comercial") · o `SKILL.md` da `/montagem-higiene-crm` (Passo 2, a tradução etapa → stage) e da `/diagnostico-gargalos-funil` (Passos 2 e 3, coorte vs estoque e gargalo aparente vs causa real) · a Aula 1 ao vivo, onde essa foi a pergunta mais direta que apareceu no chat · pesquisa sobre a passagem de bastão entre marketing e vendas (consultada em 03/08/2026), que quantifica o custo de fazer essa entrega errado.

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📖 Conhecimento | Saber o que é lead, deal e etapa | leia [guia-conceitos-comerciais.md](guia-conceitos-comerciais.md) (seção "Os termos da estrutura") |

## A pergunta que abriu este guia

Um aluno perguntou ao vivo, com estas palavras:

> *"Como posso separar a aula da Érica, aula dois do marketing, e essa? Vejo um pouco de sobreposição."*

A resposta da professora, resumida: **um capta, o outro converte, o terceiro faz o cliente subir.**

## Os três, lado a lado

| | **Funil de MARKETING** | **Funil COMERCIAL** | **ESCADA DE OFERTAS** |
|---|---|---|---|
| **Pergunta que responde** | Como o desconhecido vira lead? | Como este lead vira venda? | Qual produto meu ofereço pra este cliente, e quando? |
| **O que ele acompanha** | Canais e campanhas | O status de **UM deal específico** | O **portfólio inteiro**, ao longo do tempo |
| **Quem cuida** | Marketing | Comercial | Dono do negócio / produto |
| **Onde vive nesta aula** | Não é desta aula — é do Cohort de Marketing | `/desenho-processo-comercial` (Skill 1) | `/escada-de-ofertas` (Skill 6, bônus) |
| **Documento gerado** | offerbook, avatar, páginas | `processo-comercial-{negocio}.md` | `escada-de-ofertas-{negocio}.md` |
| **Unidade de medida** | leads gerados, custo por lead | deals por etapa, taxa de conversão | degraus, taxa de ascensão |

## Onde um entrega pro outro

```
   FUNIL DE MARKETING                FUNIL COMERCIAL
   (Cohort de Marketing)             (esta aula, Skill 1)
   anúncio, conteúdo, página   →     Prospecção → Qualificação →
   captura o lead                    Discovery → Proposta →
          │                          Negociação → Fechado → Onboarding
          │                                   │
          │  se o lead chegou frio demais     │
          └───────── volta ◄──────────────────┘
                (nutrição, elevar consciência)
```

**O ponto de contato é um só.** Na Aula 1:

> *"A única etapa em que o marketing e vendas vão se comunicar é essa questão do início: para a gente entender se o cliente chegou com um nível de consciência mínimo para continuar dentro do funil comercial, ou se ele precisa voltar para o marketing."*

Ou seja: se o lead cai no comercial sem saber nem qual é o problema dele, você **não** o empurra pelas etapas. Você marca como perdido **com motivo** e devolve pro fluxo de nutrição do marketing. Esse motivo é justamente o dado que ajusta o ICP depois.

### O tamanho do problema (números de mercado)

Essa passagem de bastão é onde mais se perde dinheiro em B2B, e ela é medível:

| Fato | Referência |
|---|---|
| Leads que o marketing gera e que vendas rejeita ou que somem no caminho | **85% a 87%** |
| Conversão saudável de lead entregue → lead aceito como qualificado | 10% a 30% (times bem alinhados: 25-40%) |
| Abaixo de 15% | sinal de problema na definição ou no follow-up, não no vendedor |
| Follow-up feito **na primeira hora** vs. 24h depois | 53% vs. 17% de conversão em lead qualificado |

⚠️ **A causa nº 1 desse desperdício é banal:** marketing e vendas **nunca escreveram** o que conta como lead pronto. Sem essa definição acordada por escrito, o marketing entrega o que acha e o comercial rejeita o que quer — e ninguém aprende nada.

É exatamente isso que o **contrato de dados** da Skill 1 resolve: ele define, por escrito, o que precisa vir preenchido quando o lead entra no comercial (nome, cargo, origem, o que ele já sabe). E a referência de **1 hora** para o primeiro contato, que aparece no seu processo, vem daí — não é capricho.

## O funil comercial depois que vira CRM (Aula 2)

O funil comercial da Skill 1 é um **documento**. Na Aula 2 ele vira **estrutura numa ferramenta** — e a tradução é literal, item por item:

| No documento da Aula 1 | Vira, no CRM |
|---|---|
| cada **etapa** do funil | um **stage** (estágio, coluna — o nome muda por ferramenta) |
| cada **critério de saída (VCA)** | um **campo customizado** — e, onde a ferramenta permitir, uma **trava de avanço**: o card não muda de etapa sem o campo preenchido |
| cada item do **contrato de dados** | um campo obrigatório naquela etapa |
| a origem **Seeds / Nets / Spears** | um campo ou tag de origem |
| — | um campo de **responsável** pelo deal, se mais de uma pessoa mexe no CRM |

⚠️ **A diferença entre campo informativo e trava de avanço é o guia inteiro em uma linha.** Campo informativo detecta o problema depois; trava de avanço impede ele. Uma etapa cujo critério de saída é só informativo é a mesma "etapa decorativa" que o funil da Aula 1 já alertava — ela continua existindo, só que agora com nome de stage.

**E a conversão entre etapas?** É a Skill 3 da Aula 2 (`/diagnostico-gargalos-funil`). Duas coisas de lá valem saber já ao desenhar o funil:

- **Conversão de coorte ≠ conversão de estoque.** Coorte é: *dos negócios que entraram nesta etapa nos últimos 90 dias, quantos avançaram*. Estoque é: *quantos estão na etapa seguinte dividido por quantos estão nesta agora*. A primeira mede conversão de verdade; a segunda é fallback, serve pra apontar onde olhar primeiro, não pra cravar número.
- **Conversão de estoque acima de 100% não é um funil bom, é um sinal de defeito.** Matematicamente, chegar mais negócio na etapa seguinte do que existe na atual só acontece quando entrou lote sem passar de verdade pela etapa anterior. É a assinatura de uma etapa decorativa.

⚠️ **A etapa com pior conversão não é necessariamente a culpada.** Ela pode estar só recebendo negócio malqualificado da etapa anterior. Isso tem nome: **gargalo aparente** na etapa N, **causa real** na etapa N-1. Antes de mexer na etapa que parece ruim, olhe a de trás — ela tem critério de saída claro, ou é comum ver vários cards avançando de uma vez?

Nada disso muda o desenho do seu funil. Muda o que você exige dele: **etapa boa é etapa com critério de saída verificável**, porque é isso que torna a conversão legível depois.

## E a escada de ofertas, onde entra?

A escada é de **outro nível**: ela não acompanha um deal, ela mapeia como o cliente sobe entre os seus produtos.

```
Degrau 3 — Enterprise / consultoria
   ▲
Degrau 2 — Completo
   ▲
Degrau 1 — Básico (porta de entrada)
```

E aí vem a conexão que confunde todo mundo. O `SKILL.md` da Skill 6 fecha com ela (Passo 4, "Conectar de volta ao funil comercial"):

> *"Um lead pode entrar pelo Degrau 1 e, meses depois, abrir um novo deal no funil comercial para o Degrau 2 — são deals diferentes, na mesma jornada de escada."*

Em outras palavras: entrar no Degrau 1 abre **um deal**. Querer subir pro Degrau 2 abre **outro deal**, do mesmo cliente. **Dois deals diferentes, uma escada só.**

Exemplo real da aula, sobre um CRM vendido pra indústrias:

> *"Uma metalúrgica entra hoje pelo degrau 1. Seis meses depois, ao perceber que quer automação, abre um novo deal no funil comercial para o degrau 2."*

## O apelido que causa o problema

O termo **"funil de vendas"** é usado no mercado pras duas coisas. Por isso o `docs/SKILLS-INDEX.md` deste repo registra:

| Se você ouvir… | Provavelmente é… |
|---|---|
| "funil de vendas" no sentido de **status de um deal** | funil comercial → Skill 1 |
| "funil de vendas" no sentido de **jornada entre produtos** | escada de ofertas → Skill 6 |

Quando estiver em dúvida, faça uma pergunta só: **estou falando de UM negócio específico, ou do portfólio inteiro?**

## Quem precisa de qual

| Seu caso | Funil de marketing | Funil comercial | Escada de ofertas |
|---|---|---|---|
| Um produto só, leads vêm de indicação | opcional | **sim** | não se aplica |
| Um produto só, leads vêm de anúncio | sim (Cohort de Marketing) | **sim** | não se aplica |
| Três planos (básico/completo/enterprise) | sim | **sim** | **sim** |
| E-commerce sem vendedor no meio | sim | **sim** (etapas viram toques digitais) | se tiver mais de uma faixa de produto |

⚠️ A Skill 6 **se recusa** a criar uma escada artificial se você só tem um produto. Isso é comportamento correto, não erro: *"essa skill não se aplica ainda — quando vocês tiverem um segundo produto, voltamos aqui."*

### O "Stadium Pitch" que pode aparecer no seu documento

Se a Skill 6 rodar, ela pode sugerir um reforço com esse nome (é de Chet Holmes). A ideia:

> Em vez de descobrir na conversa, um por um, em qual degrau cada cliente está, você cria **um conteúdo educativo** (aula gratuita, webinário, material de diagnóstico) que aquece **vários degraus ao mesmo tempo**. A pessoa se auto-identifica ao consumir.

A imagem é um estádio: em vez de convencer cada pessoa individualmente, você fala uma vez para a arquibancada inteira, e cada um se reconhece no lugar em que está.

⚠️ **Vale só se você tem volume de leads que justifique produzir conteúdo.** Negócio começando, com poucos leads, ganha mais no discurso um a um — e a própria skill diz isso.

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Saber de qual funil eu estou falando** | "Estou tentando resolver este problema: [descreva]. Isso é assunto do funil de marketing (captação), do funil comercial (status de um deal) ou da escada de ofertas (portfólio)? Justifique." |
| **Definir o que é lead pronto pro comercial** | "Meu negócio é [descreva]. Escreva a definição, por escrito, do que conta como lead pronto pra entrar no meu funil comercial: quais informações precisam vir preenchidas e qual nível de consciência ele precisa ter. É isso que marketing e vendas vão acordar." |
| **Decidir se devolvo o lead pro marketing** | "Este lead chegou assim: [descreva o contexto e o que ele já sabe]. Ele tem consciência suficiente pra avançar no funil comercial, ou devo marcar como perdido com motivo e devolver pra nutrição? Qual motivo eu registro?" |

## Teste de sucesso

Responda estas três, com suas palavras:

1. Um lead entrou por um anúncio e virou cliente do plano básico. **Quantos funis participaram disso?** (resposta: dois — o de marketing captou, o comercial converteu)
2. Esse mesmo cliente sobe pro plano completo em 6 meses. **Isso é o mesmo deal ou um deal novo?** (resposta: deal novo, no funil comercial, guiado pela escada)
3. O lead chegou sem saber que tinha o problema. **Ele avança no funil comercial?** (resposta: não — volta pra nutrição do marketing, com motivo registrado)

**Funcionou se** você acertou as três sem consultar a tabela.

## POSSÍVEIS ERROS — catálogo

| # | Confusão | Consequência prática | Como desfazer |
|---|---|---|---|
| FU1 | Achar que o funil comercial "começa no anúncio" | O documento fica com etapas de marketing misturadas (impressão, clique), que não têm ação de cliente verificável | a primeira etapa do funil comercial é **"a conta bate com o ICP e um contato nomeado aceitou conversar"**, não "viu o anúncio" |
| FU2 | Rodar a `/escada-de-ofertas` tendo um produto só | Sai uma escada inventada, que ninguém usa | pule a Skill 6. Ela é bônus, e o próprio `SKILL.md` avisa que não se aplica |
| FU3 | Achar que a escada substitui o funil comercial | Você perde o acompanhamento do deal — sabe qual produto oferecer, mas não em que pé está a negociação | são complementares: escada diz **o quê** oferecer, funil comercial diz **em que ponto está** |
| FU4 | Empurrar o lead frio pelas etapas em vez de devolver pro marketing | Funil sujo, forecast fictício, vendedor gastando tempo com quem não vai comprar | marque como perdido **com motivo**, e devolva pra nutrição. O motivo é o que corrige o ICP depois |
| FU5 | Achar que esta aula substitui o Cohort de Marketing | Você fica sem canal de aquisição: o funil comercial mais lindo do mundo sem lead entrando não vende nada | são aulas de cohorts diferentes, complementares. O offerbook do marketing é o melhor insumo desta aula — veja [guia-offerbook-do-marketing.md](../03-insumos/guia-offerbook-do-marketing.md) |
| FU6 | Chamar de "funil de vendas" e não saber qual dos dois é | Conversa com o time vira ruído: cada um entende uma coisa | adote o vocabulário do repo: **funil comercial** (deal) e **escada de ofertas** (portfólio). Nunca "funil de vendas" solto |
| FU7 | Registrar o mesmo cliente como um único deal eterno que nunca fecha | Forecast quebrado e histórico ilegível | cada compra (ou tentativa) é um deal próprio. Cliente que sobe de degrau abre deal novo |
| FU8 | Criar no CRM etapas com nome diferente das que você desenhou na Skill 1 | A Aula 2 inteira lê o funil pelas etapas: se os nomes divergem, a conversão sai errada e o gargalo aponta pro lugar errado | traduza etapa por etapa, mantendo o nome. Se o CRM já tinha estrutura própria, a Skill 1 da Aula 2 **adapta** em vez de recriar — mas ela precisa que você diga qual etapa antiga corresponde a qual nova |
| FU9 | Comemorar uma etapa com conversão acima de 100% | Você está lendo estoque como se fosse conversão, e o número esconde uma etapa decorativa | acima de 100% é sinal de avanço em lote, não de eficiência. Confira se aquela etapa tem critério de saída de verdade — veja a seção do CRM acima |

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | se você tem mais de um produto, anote quais são — a Skill 6 vai pedir |
| 📖 Ler | [guia-bant-gpct-spin.md](guia-bant-gpct-spin.md) — os frameworks que as skills 3 e 4 usam |
| ▶️ Fazer (Aula 2) | com o funil desenhado, rode `/montagem-higiene-crm` — é ele que traduz etapa por etapa pra dentro da sua ferramenta |
| 🚑 Se travar | o catálogo FU1–FU9 acima |
