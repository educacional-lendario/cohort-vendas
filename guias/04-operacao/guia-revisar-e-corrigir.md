# GUIA REVISAR E CORRIGIR — o que fazer quando o entregável não ficou bom

> **Estou perdido em:** "a skill entregou o documento, mas tem etapa que não faz sentido pro meu negócio — e o texto tem cara de IA. Posso mexer? Como?".
> **O que você vai ter no final:** o hábito de revisar **antes** de avançar, os prompts de correção cirúrgica, e o filtro anti-"cara de IA" pra rodar em qualquer texto que você for usar com cliente.
> **Fontes cruzadas:** o `SKILL.md` da `/discovery-script` (Passo 1.6, a auditoria de compliance e voz, com o checklist de 8 itens literal) e da `/playbook-vendas-vivo` (Passo 3.5, a mesma auditoria, agora obrigatória também no playbook) · os `SKILL.md` das Skills 1 e 2 (que mandam adaptar o que você já tem em vez de recriar) · a Aula 1 ao vivo, onde a professora explicou por que criou essa auditoria e avisou 3 vezes pra revisar antes de avançar · pesquisa sobre marcas de texto gerado por IA em português (consultada em 03/08/2026), que acrescentou o vocabulário-denúncia ao checklist.

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📄 Artefato | Pelo menos um entregável gerado (`*.md` na pasta do projeto) | rode `/desenho-processo-comercial` — veja [guia-mapa-das-skills.md](guia-mapa-das-skills.md) |
| 📖 Conhecimento | Saber o que é critério de saída (VCA), etapa e gatilho | leia [guia-conceitos-comerciais.md](../02-conhecimento-minimo/guia-conceitos-comerciais.md) |

## A regra que evita todo o retrabalho

⚠️ **A ordem certa: rodar a skill → LER o entregável → corrigir o que não bate → só então rodar a próxima.**

Fala literal da Aula 1, sobre o processo entregue pela Skill 1:

> *"Por isso que é importante a gente ler atentamente e concordar com essas etapas. Aí você pode vir aqui e falar: cara, não gostei dessas etapas, quero colocar uma coisa a mais, não faz sentido — vou rodar essa skill de novo, quero corrigir isso, corrige aquilo."*
>
> *"E aí, porque agora, a partir dos próximos passos: **se você não corrigiu aqui para trás, aqui para frente vai continuar do mesmo jeitinho.**"*

Traduzindo o custo: uma etapa mal desenhada na Skill 1 se propaga para a régua (Skill 2), a qualificação (Skill 3), o discovery (Skill 4) e o playbook (Skill 5). Corrigir na hora custa 5 minutos. Corrigir depois custa re-rodar quatro skills.

## Passo 1 — A revisão de 10 minutos (o que olhar em cada entregável)

Não leia o documento inteiro linha a linha. Olhe estes pontos, na ordem:

### No `processo-comercial-*.md` (Skill 1)

| Cheque | Como saber se está errado |
|---|---|
| **As flags no topo** | `nicho_regulado`, `modelo` e `insumos_cohort_mkt` estão lá, em destaque? Se não, peça pra acrescentar |
| **Cada critério de saída** | Ele descreve uma **ação do cliente** ou uma atividade sua? Se aparece "enviei", "liguei", "apresentei" → está errado |
| **O teste dos dois vendedores** | Dois vendedores olhando o mesmo deal chegariam à mesma conclusão? Se o critério deixa margem pra interpretação, peça pra reescrever até ficar binário |
| **O número de etapas** | Bate com o seu ciclo real? 7 etapas num negócio que fecha no mesmo dia é overengineering; 2 etapas numa venda de 4 meses é leviandade |
| **A etapa Perdido** | Existe, e exige **motivo categorizado**? Sem motivo, o dado não serve pra nada |
| **Os gatilhos** | Os prazos fazem sentido pro seu ciclo? "7 dias parado" é benchmark, não lei — se o seu ciclo é de meses, talvez sejam 15 |

### No `regua-comunicacao-*.md` (Skill 2)

| Cheque | Como saber se está errado |
|---|---|
| **Os canais** | Ela sugeriu algum canal que você **não opera**? Não deveria — o Passo 0 pergunta isso |
| **As mensagens** | Duas mensagens consecutivas dizem a mesma coisa com outras palavras? A regra é ângulo diferente a cada toque |
| **O mecanismo único** | O nome que ela deu soa como você, ou como manual de vendas? Se não soa, renomeie você mesmo |
| **O Mapa de Canais** | Cada canal sugerido tem justificativa com dado (concorrente usa, comportamento do nicho)? Se for "toda empresa precisa", questione |

### No `qualificacao-*.md` (Skill 3)

| Cheque | Como saber se está errado |
|---|---|
| **O mix escolhido** | A justificativa bate com o seu ticket/ciclo/decisores? |
| **O ICP** | Está marcado como "hipótese a validar"? Se você tem clientes reais, corrija com o que você **sabe** |
| **As perguntas** | Lidas em voz alta, soam como conversa ou como interrogatório? Se soam mecânicas, o framework virou muleta |
| **A nota de corte** | O número faz sentido? Nota de corte alta demais descarta lead bom; baixa demais suja o funil |

### No `discovery-script-*.md` (Skill 4) e `playbook-objecoes-*.md` (Skill 5)

| Cheque | Como saber se está errado |
|---|---|
| **As peças de copy** | Você mandaria esse texto **hoje**, com o seu nome? Se sentiria vergonha, rode a auditoria do Passo 3 |
| **Os rótulos "a validar"** | Algum bloco está marcado como ponto de partida? Aquilo ainda não é seu — precisa da sua experiência real |
| **As objeções** | São as que os seus clientes falam, ou genéricas do nicho? |
| **A resposta de preço** | Ela volta ao número da dor quantificada, ou oferece desconto? Desconto reflexo é erro |

## Passo 2 — Como corrigir (os 3 níveis)

### Nível 1 — Correção cirúrgica (o mais usado)

Quando é um ponto específico. Seja explícito sobre **não mexer no resto**:

```
No arquivo processo-comercial-minhaempresa.md, na tabela de etapas:
a etapa 4 tem como critério de saída "enviei a proposta". Isso é atividade minha,
não ação do cliente. Reescreva SÓ esse critério no formato VCA.
Não mexa em mais nada do documento.
```

Outros exemplos que funcionam bem:

| Quero | Cole isto |
|---|---|
| Renomear uma etapa | "renomeie a etapa 'Apresentação' para 'Demonstração' no documento inteiro, ajustando o critério de saída pra refletir isso. Não mude mais nada." |
| Acrescentar uma etapa | "acrescente uma etapa entre a 3 e a 4 chamada [X], com critério de saída no formato VCA e contrato de dados. Renumere as seguintes." |
| Ajustar um prazo | "troque o gatilho de estagnação de 7 para 15 dias, e explique em uma frase no documento por que 15 faz sentido pro meu ciclo de [X] meses." |
| Trocar o tom de uma mensagem | "a mensagem do toque D+3 está formal demais pro meu público. Reescreva mantendo o ângulo (oferta de valor) mas no tom de [descreva]." |

⚠️ **Sempre peça pra atualizar o `.html` também.** Os dois arquivos precisam ficar iguais:

```
atualize também o .html correspondente com a mesma mudança
```

### Nível 2 — Rodar a skill de novo

Quando a base está errada (o diagnóstico saiu torto, você deu informação errada, ou conseguiu o offerbook depois).

**Antes de rodar de novo, salve o antigo** — às vezes tinha coisa boa lá:

```bash
cp processo-comercial-minhaempresa.md processo-comercial-minhaempresa-v1.md
```

Depois rode `/desenho-processo-comercial` de novo e, quando ela perguntar, dê as informações corrigidas. Se quiser aproveitar o que já existia:

```
Roda de novo, mas leia antes o processo-comercial-minhaempresa-v1.md.
Mantenha o que está bom lá e corrija só o seguinte: [liste]
```

### Nível 3 — Editar na mão

Nada impede. O `.md` é texto puro: abre em qualquer editor. **Só não esqueça de refletir a mudança no `.html`** — ou peça pra IA: *"atualize o .html pra bater com o .md, que eu editei na mão"*.

## Passo 3 — A auditoria anti-"cara de IA"

### Por que ela existe

Fala da Aula 1:

> *"Por mais que passasse por um offerbook, ele vinha com aquelas coisinhas chatas… tá nítido que eu copiei e colei uma conversa. Falei: nossa, foi muito IA."*
>
> *"E é importante ter essa auditoria. Inclusive em páginas que vocês forem fazer, em tudo que vocês forem fazer, criando skills do zero: passa por essa auditoria pra eliminar o que é cara de IA."*

**Duas skills já rodam essa auditoria sozinhas**, com o mesmo checklist: a Skill 4 no **Passo 1.6**, e a Skill 5 no **Passo 3.5**. Nenhuma das duas entrega peça sem passar. Mas vale você rodar em **qualquer** texto seu — inclusive nos que nenhuma skill escreveu.

### O que a skill já checa e o que continua sendo trabalho seu

Isto é o mais útil desta seção: saber onde parar de refazer o que já foi feito, e onde não relaxar.

| A skill checa sozinha | Continua sendo seu |
|---|---|
| os 8 itens do checklist abaixo, peça por peça | o **vocabulário-denúncia** em português (a tabela mais adiante) — não está no checklist da skill |
| a flag `nicho_regulado` calibrando promessa e depoimento | se o texto soa como **você** — a skill garante que não tem vício, não que tem a sua voz |
| registra numa **nota de auditoria** o que achou e corrigiu | ler essa nota. Ela é o mapa dos vícios que quase entraram no seu texto |
| que nenhuma peça sai sem a rodada | se a **prova** citada existe de verdade. A auditoria pega "claim sem prova"; ela não confere se o seu número é real |
| — | o teste da voz alta, e o julgamento final. Ferramenta nenhuma faz isso |

⚠️ **O ponto cego mais importante:** a auditoria valida a **forma**, não a **verdade**. Se a peça afirma "11 metalúrgicas atendidas" e você atendeu 4, ela passa limpa nos 8 itens — está específica, tem número, não tem jargão. O único jeito de pegar isso é você ler.

⚠️ **A nota de auditoria vem vazia?** Isso pode significar duas coisas: nada foi encontrado, ou a auditoria não rodou de verdade. Confira se a nota existe e diz explicitamente o que checou. Ausência de nota não é sinônimo de texto limpo.

### O checklist de 8 itens (o mesmo que a skill usa)

| # | Proibido | Por quê |
|---|---|---|
| 1 | Travessão no meio de frase | marca registrada de texto gerado |
| 2 | Promessa de resultado garantido ("garante", "cura", "sempre") | compliance, além de soar falso |
| 3 | **"não é X, é Y"** — em qualquer variação ("não é sobre X, é sobre Y", "não era X, era Y") | *"este é o vício mais comum, verifique com atenção redobrada"* |
| 4 | "nós" em vez de "a gente" | tom empolado |
| 5 | Jargão de guru ("mindset", "virada de chave", "despertar") | queima credibilidade |
| 6 | Três adjetivos seguidos sem dado por trás | enche linguiça |
| 7 | Claim sem prova ("resultado incrível", "dezenas de milhares" quando existe número exato) | troque pelo número real |
| 8 | Depoimento de paciente/cliente, se o nicho for regulado (CFM, CRP, OAB) | vedação de conselho profissional |

### O vocabulário que denuncia (bônus, específico do português)

Além dos 8 itens da skill, existe um conjunto de palavras que a IA usa muito mais que gente. Se aparecerem no seu documento, quase sempre dá pra trocar por algo mais direto:

| Palavra | Troque por |
|---|---|
| **crucial** | importante, decisivo, ou reescreva sem adjetivo |
| **fundamental** | idem — ou diga *por que* é importante, que é mais forte |
| **insight** | "o que a gente descobriu foi…" |
| **mergulhar** (em um tema) | "olhar", "entender", "estudar" |
| **particularmente** | corte; quase sempre não faz falta |
| **é importante ressaltar que** | corte a frase inteira e vá direto ao ponto |

⚠️ **Sobre o travessão:** ele é característica forte de texto gerado, e por isso está no item 1 do checklist. Mas ele **não prova** nada sozinho — gente também usa travessão. O que denuncia é o conjunto: travessão + "não é X, é Y" + tríade de adjetivos + vocabulário acima, tudo no mesmo parágrafo.

**O teste mais rápido de todos:** leia em voz alta. Se você não falaria aquilo pra um cliente numa mesa de bar, reescreva.

### O prompt pra rodar em qualquer texto

```
Audite este texto contra o checklist do Passo 1.6 da skill /discovery-script
(o mesmo do Passo 3.5 da /playbook-vendas-vivo):
travessão no meio de frase, promessa de resultado garantido, construção "não é X é Y"
em qualquer variação, "nós" em vez de "a gente", jargão de guru, tríade de adjetivos
vazios, e claim sem prova.

Depois, some a checagem que a skill NÃO faz: aponte o vocabulário-denúncia em português
(crucial, fundamental, insight, mergulhar, particularmente, "é importante ressaltar que").

Para cada violação, mostre a frase exata e a substituição sugerida, sem perder a força
persuasiva. Depois entregue o texto corrigido.

Texto: [cole aqui]
```

## Passo 4 — Quando a correção afeta as skills seguintes

Se você mudou algo na Skill 1 **depois** de já ter rodado as outras, o efeito cascata é real:

| Você mudou | Precisa re-rodar |
|---|---|
| Uma etapa ou critério de saída (Skill 1) | Skills 2, 3, 4 (a régua, a qualificação e o script se ancoram nas etapas) |
| Uma flag (`nicho_regulado`, `modelo`) | **Todas** as seguintes — a flag muda a linguagem de tudo |
| Os canais (Skill 2) | Skill 4 (ela escreve uma peça por linha da régua) |
| O mecanismo único (Skill 2) | Skills 4 e 5 (é a voz que atravessa as duas) |
| Só o texto de uma mensagem (Skill 2) | nada — correção local |
| As objeções (Skill 5) | nada — é a última do fluxo principal |

**Atalho:** em vez de re-rodar tudo, peça a correção cirúrgica em cada arquivo afetado:

```
Eu mudei a etapa 3 do processo-comercial-x.md (novo critério: [Y]).
Leia o arquivo atualizado e ajuste SÓ a linha correspondente da régua no
regua-comunicacao-x.md e no .html dela. Não mexa no resto.
```

## Teste de sucesso

Pegue o entregável mais recente e responda **sim ou não** a estas três:

1. Todos os critérios de saída descrevem ação do **cliente**?
2. Você mandaria as mensagens desse documento hoje, com o seu nome, sem vergonha?
3. Não existe nenhum bloco marcado como "ponto de partida a validar" que você ainda não validou?
4. Todo número que aparece no documento **existe de verdade** — você conferiu, não a auditoria?

**Funcionou se:** as quatro são "sim". Qualquer "não" é uma correção pendente — e é mais barato fazer agora que depois.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| RV1 | Pedi uma correção e ela reescreveu o documento inteiro | Pedido amplo demais | seja cirúrgico: cite arquivo, seção e o que mudar, e termine com *"não mexa em mais nada"*. Se já reescreveu, use a cópia `-v1` (é por isso que se salva antes) |
| RV2 | Corrigi o `.md` mas o `.html` continua com o texto antigo | São dois arquivos separados | peça *"atualize o .html pra bater com o .md"* — sempre, a cada correção |
| RV3 | Rodei a skill de novo e ela sobrescreveu o arquivo anterior | Mesmo nome de arquivo | **salve uma cópia antes** de re-rodar (`cp arquivo.md arquivo-v1.md`). Se já perdeu, procure o conteúdo no histórico da conversa |
| RV4 | Mudei a Skill 1 e não sei o que mais precisa mudar | Efeito cascata | use a tabela do Passo 4. Na dúvida: *"eu mudei [X] no processo. Quais dos meus outros documentos ficaram desatualizados por causa disso?"* |
| RV5 | O texto continua com cara de IA mesmo depois da auditoria | O checklist pega os vícios de forma, não o tom | acrescente ao prompt: *"reescreva no tom de alguém que fala assim: [cole 3 mensagens suas reais]"* |
| RV6 | Discordo do que a skill entregou, mas não sei se estou errado | Insegurança normal em quem está desenhando processo pela primeira vez | peça a defesa dela: *"me explique por que você desenhou assim, e o que aconteceria se eu fizesse [minha alternativa]"*. Quem decide é você — é o seu negócio |
| RV7 | Editei na mão e agora a skill seguinte parece ignorar minha edição | Ela leu o arquivo antes da sua edição, ou está lendo o `.html` | aponte explicitamente: *"leia o arquivo `x.md` NOVAMENTE — eu editei — e continue a partir dele"* |
| RV8 | O documento tem uma seção que não faz sentido nenhum pro meu caso | A skill aplicou um bloco de referência genérico | peça pra remover: *"remova a seção [X], ela não se aplica ao meu modelo de negócio porque [motivo]"*. Documento com seção morta é documento que ninguém usa |
| RV9 | A auditoria passou limpa, mas a peça afirma um número que eu não tenho | A auditoria valida **forma**, não **verdade** | é o ponto cego dela: um número inventado passa nos 8 itens porque é específico. Só você pega isso. Confira cada número antes de mandar pro cliente |
| RV10 | Não achei nota de auditoria nenhuma no meu documento | Ou nada foi encontrado, ou a rodada não aconteceu | ausência de nota ≠ texto limpo. Peça: *"rode a auditoria de 8 itens neste documento e me devolva a nota, mesmo que não encontre nada"* |
| RV11 | Rodei a auditoria e ela não pegou "crucial", "insight", "é importante ressaltar" | O vocabulário-denúncia em português **não** está no checklist da skill | é a parte que continua sendo sua. Use o prompt do Passo 3, que já soma as duas checagens |

**Se nada resolver:** cole o trecho problemático numa conversa e peça *"me guie passo a passo pra corrigir isto, um passo por vez"*.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | releia o último entregável com a checagem do Passo 1 e corrija o que achar — **antes** de rodar a próxima skill |
| 📖 Ler | [guia-entregaveis-e-central.md](guia-entregaveis-e-central.md) — onde ficam os arquivos e como acompanhar o progresso |
| 🚑 Se travar | o catálogo RV1–RV11 acima |
