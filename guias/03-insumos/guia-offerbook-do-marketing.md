# GUIA OFFERBOOK DO MARKETING — o insumo que separa "mediano" de "robusto"

> **Estou perdido em:** "a skill perguntou se eu tenho o offerbook do Cohort de Marketing. Eu não sei o que é isso, ou não sei onde está, ou não fiz aquele cohort".
> **O que você vai ter no final:** o material do Cohort de Marketing conectado a esta aula (ou a decisão consciente de seguir sem ele, com as 4 perguntas substitutas na mão).
> **Fontes cruzadas:** o `SKILL.md` da `/desenho-processo-comercial` (Passo -1, o gate de entrada que faz essa pergunta) e da `/qualificacao-bant-gpct` (Passo 2, que aproveita o ICP já validado) · o `README.md` deste repo · a Aula 1 ao vivo, onde a aula inteira foi rodada **sem** o offerbook, de propósito, e a professora deu o veredito no fim · pesquisa sobre validação de ICP em negócio em fase inicial (consultada em 03/08/2026).

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📖 Conhecimento | Saber o que é ICP e offerbook | leia [guia-conceitos-comerciais.md](../02-conhecimento-minimo/guia-conceitos-comerciais.md) |
| 📄 Artefato | O offerbook e o ICP gerados no Cohort de Marketing | não tem? **não bloqueia** — vá pro Caminho B abaixo |

## O que é o offerbook, e por que ele importa aqui

O **offerbook** é o entregável central da Aula 1 do **Cohort de Marketing** (outro cohort, outro professor). Ele traz, já pesquisado e revisado por você:

- o avatar / ICP do cliente ideal (com desejo, problema, dores);
- a oferta desenhada;
- a pesquisa de concorrentes;
- as objeções mapeadas.

Repare que essas quatro coisas são **exatamente** o que a Skill 1 desta aula pergunta quando você não tem o offerbook, e o que a Skill 3 tenta montar do zero, e o que a Skill 5 precisa pra não inventar objeção. É por isso que ele é o insumo mais valioso desta aula.

## O veredito honesto (dado ao vivo, na Aula 1)

A aula inteira foi rodada de propósito **sem** o offerbook, a pedido do aluno-cobaia, que queria ver o que a IA faria sozinha. No fechamento, a professora disse:

> *"O que a gente rodou aqui foi realmente cru do zero. Ele já entregou um resultado — sinceramente, foi **mediano**. Eu usei num outro processo em que usei o cohort de marketing junto: ele entregou um resultado **bem melhor, bem mais robusto**."*

E, no meio da aula, sobre a pesquisa de concorrentes:

> *"Lembrando que, se tivesse o offerbook, eu nem iria fazer essa busca."*

⚠️ **Mas não é obrigatório.** O `SKILL.md` é explícito: *"oriente o aluno a rodar as skills de ICP/offerbook do Cohort de Marketing quando tiver tempo, mas **não bloqueie esta aula por isso**"*.

## Caminho A — Você tem o offerbook

### Passo A1 — Ache os arquivos

Eles estão na pasta do projeto do Cohort de Marketing, normalmente em `projetos/{slug-do-seu-projeto}/`. Os nomes costumam conter:

| Procure por | O que é |
|---|---|
| `offerbook*` | o livro da oferta |
| `avatar*` / `icp*` | a pesquisa de avatar / perfil de cliente ideal |
| `*concorrent*` | a pesquisa de concorrentes / dossiê do espião |
| `*objec*` / `*dor*` | mapa de dores e objeções |
| `copy*` | a fundação de mensagem, se você rodou |

**Não acha?** Abra um terminal na pasta do projeto de marketing e rode:

```bash
ls projetos/*/
```

### Passo A2 — Decida como entregar pra skill

Existem duas formas, e as duas funcionam:

| Forma | Como | Quando usar |
|---|---|---|
| **1. Dar o caminho** | Quando a Skill 1 perguntar, responda: *"sim, estão em `/caminho/completo/da/pasta`"* | quando o projeto de marketing está na **mesma máquina** |
| **2. Deixar ela procurar** | Responda: *"sim, mas procure você mesma no projeto"* — ela varre por `offerbook*`, `icp*`, `*pesquisa*concorrent*`, `*mapa*dor*`, `*objec*` e confirma com você antes de usar | quando você copiou os arquivos pra dentro da pasta desta aula |

**A forma mais segura, se você está em dúvida:** copie os arquivos do offerbook pra dentro da pasta `cohort-vendas` (ou pra dentro do seu projeto, se você seguiu o Cenário 2). Aí qualquer uma das duas formas funciona.

```bash
cp /caminho/do/marketing/projetos/meu-projeto/offerbook*.md ./
```

### Passo A3 — Confirme que ela leu de verdade

Depois de responder, a skill deve **citar a origem** ao usar o material — algo como *"conforme o seu offerbook, o cliente ideal é…"*. Se ela começar a te perguntar coisas que já estão no offerbook (quem é o cliente ideal, quais são as dores), ela **não leu**. Veja o erro `OB4`.

### Passo A4 — A flag que fica registrada

A Skill 1 registra no topo do documento final: `insumos_cohort_mkt: sim` + o caminho da pasta. As 6 skills seguintes herdam isso e não perguntam de novo.

## Caminho B — Você NÃO tem o offerbook

Você tem três opções, em ordem de qualidade de resultado:

### Opção B1 — Rodar o offerbook agora (melhor resultado)

Se você tem acesso ao Cohort de Marketing, rode lá `/offerbook` (e, se der, `/avatar-funil` e `/espiao-do-concorrente`) antes de voltar aqui. Recomendação da própria aula:

> *"Eu aconselho vocês também a rodar o offerbook junto."*

**Custo:** algumas horas. **Ganho:** a diferença entre "mediano" e "robusto", na palavra de quem testou os dois.

### Opção B2 — Responder as 4 perguntas substitutas (o caminho da aula)

A Skill 1 faz estas quatro no lugar. Prepare as respostas antes:

1. **Quem é o cliente ideal hoje?** (porte, segmento, cargo de quem decide)
2. **Quais são as 2-3 dores mais fortes que fazem esse cliente comprar?** — *nas palavras dele*, não no seu jargão
3. **Quais objeções mais aparecem hoje**, mesmo que sem lista formal?
4. **O que te diferencia** de quem esse cliente também considera?

⚠️ **A pergunta 2 é a mais importante e a mais mal respondida.** "Ele precisa de organização" é o seu jargão. "Eu perco cliente porque esqueço de dar retorno" são as palavras dele. A segunda versão é a que faz a copy das skills 4 e 5 não sair genérica.

### Opção B3 — Deixar a IA pesquisar do zero

É o que aconteceu na Aula 1. Quando você diz que não tem concorrentes mapeados, a Skill 1 e a Skill 2 pesquisam na web por conta própria (concorrentes do nicho, canais que eles usam, presença digital).

**Vantagem** (argumento do próprio aluno em aula): *"eu já tenho alguma coisa em mente, mas prefiro que ele comece do zero, porque às vezes ele acha alguma coisa que eu não tinha pensado."*

**Custo honesto:** essa pesquisa consome bem mais tokens, e é aqui que vale usar o modelo mais forte (veja [guia-modelo-e-custo.md](../01-pre-requisitos/guia-modelo-e-custo.md)).

⚠️ **E um alívio, se você está começando:** antes dos 10 primeiros clientes, **todo ICP é hipótese** — inclusive o do offerbook. O que muda é a qualidade do chute: com offerbook você parte de pesquisa; sem ele, de intuição. Nos dois casos, a revisão de verdade só acontece quando você tiver de 5 a 10 clientes reais e puder olhar quem de fato deu certo. Não trave esperando certeza que ainda não existe.

## Rodar de novo depois, com o offerbook

Se você rodou sem e depois conseguiu o offerbook, **não precisa recomeçar tudo**. O plano que a professora deu em aula:

> *"Você traz todo o contexto do cohort da Aula 1 de marketing, com o offerbook, com a pesquisa de concorrente, e roda de novo as skills com todo aquele contexto."*

Ordem prática de re-rodagem, por retorno sobre o esforço:

| Prioridade | Skill | Por que ela muda mais com offerbook |
|---|---|---|
| 1ª | `/qualificacao-bant-gpct` | o ICP sai muito mais robusto quando não é hipótese |
| 2ª | `/playbook-vendas-vivo` | as objeções deixam de ser "típicas do nicho" e viram as suas |
| 3ª | `/regua-comunicacao-comercial` | os hooks e a pesquisa de canais ganham a pesquisa de concorrentes pronta |
| 4ª | `/desenho-processo-comercial` | muda menos: a estrutura de etapas depende mais do ticket/ciclo que do offerbook |

Antes de re-rodar, leia [guia-revisar-e-corrigir.md](../04-operacao/guia-revisar-e-corrigir.md) — tem a regra de o que fazer com o arquivo antigo.

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Achar o offerbook na minha máquina** | "Procure nesta pasta e nas subpastas por arquivos que pareçam offerbook, ICP, avatar, pesquisa de concorrentes ou mapa de objeções. Liste o que encontrou com o caminho, e me diga qual serve como insumo pro meu processo comercial." |
| **Conferir se ela leu de verdade** | "Leia o arquivo `[nome do offerbook]` inteiro e me diga, com as palavras que estão lá: quem é o cliente ideal, quais são as 3 dores principais e quais objeções estão mapeadas. Não resuma — cite o que está escrito." |
| **Não tenho offerbook e preciso responder as 4 perguntas** | "Vou responder 4 perguntas sobre meu negócio pra alimentar o desenho do meu processo comercial. Me pergunte **uma por vez** e me ajude a melhorar cada resposta antes de passar pra próxima: (1) quem é o cliente ideal, (2) as 2-3 dores que fazem ele comprar, (3) as objeções que mais aparecem, (4) o que me diferencia. Meu negócio: [descreva]." |
| **Transformar o que eu sei em insumo** | "Vou descrever meu cliente ideal e as dores dele do jeito que me vem à cabeça: [descreva de corrido]. Reescreva isso **nas palavras que o cliente usaria**, não no meu jargão — é assim que a skill precisa receber." |
| **Reaproveitar depois que consegui o offerbook** | "Eu rodei minhas skills sem o offerbook e agora consegui. Leia `[caminho do offerbook]` e o meu `qualificacao-{negocio}.md` atual, e me diga exatamente o que muda no ICP — antes de eu rodar a skill de novo." |

## Teste de sucesso

Depois de rodar a Skill 1, abra o `processo-comercial-{seunegocio}.md` e olhe o topo do documento.

**Funcionou se:** a flag `insumos_cohort_mkt` está lá, com o valor correto (`sim` + caminho, ou `não`).

**Teste extra, se você respondeu "sim":** procure no documento por uma frase que cite o offerbook (algo como *"conforme o seu offerbook…"*). Se a skill nunca menciona o material, ela provavelmente não leu — vá pro `OB4`.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| OB1 | Não sei se o que eu tenho é "offerbook" | Nome do arquivo diferente do esperado | abra o arquivo: se tiver avatar/ICP, oferta, dores e objeções, serve. Diga à skill *"tenho um documento com ICP, oferta e objeções, está em [caminho]"* |
| OB2 | Dei o caminho e a skill disse que não encontrou | Caminho errado, ou arquivos em outra máquina | 1) rode `ls <caminho>` no terminal pra confirmar que existe 2) se estiver em outro computador, copie os arquivos pra dentro da pasta desta aula 3) se não der, siga o Caminho B — não trave a aula |
| OB3 | Pedi pra ela procurar e ela não achou nada | Os arquivos não estão dentro da pasta em que a ferramenta foi aberta | copie o offerbook pra dentro da pasta do projeto e peça pra procurar de novo. A ferramenta só enxerga o que está na pasta aberta |
| OB4 | Ela disse que leu, mas está me perguntando coisas que estão no offerbook | Ela não leu de verdade, ou leu só o nome do arquivo | peça explicitamente: *"leia o arquivo `offerbook-x.md` inteiro antes de continuar e me diga qual é o ICP que está escrito lá"* — se ela repetir o conteúdo real, leu |
| OB5 | Nunca fiz o Cohort de Marketing e me sinto travado | Achar que é pré-requisito | **não é.** O `SKILL.md` manda explicitamente não bloquear. Siga a Opção B2 (4 perguntas) e toque a aula |
| OB6 | Rodei sem offerbook, o resultado ficou genérico demais | Comportamento esperado, avisado em aula | não descarte o que saiu: use-o como rascunho, consiga o offerbook, e re-rode na ordem de prioridade da tabela acima |
| OB7 | A pesquisa de concorrentes que ela fez sozinha veio fraca / errada | Modelo fraco demais pra pesquisa, ou nicho pouco documentado na web | 1) troque pro modelo mais forte (`/model`) e peça pra refazer só a pesquisa 2) se você conhece os concorrentes, **diga os nomes** — a Skill 2 pergunta por 2-3 nomes justamente pra isso |
| OB8 | Achei que o offerbook substituía as 8 perguntas do Passo 0 | São coisas diferentes | offerbook cobre o Passo -1 (cliente, dores, objeções, diferencial). As 8 perguntas do Passo 0 (ticket, ciclo, decisores, modelo…) ela pergunta de qualquer jeito — veja [guia-diagnostico-antes-de-rodar.md](../02-conhecimento-minimo/guia-diagnostico-antes-de-rodar.md) |

**Se nada resolver:** cole o caminho da pasta numa conversa com a IA e peça *"liste os arquivos que existem em [caminho] e me diga quais deles servem como offerbook/ICP"*.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | separe o offerbook (ou as 4 respostas substitutas) e rode `/desenho-processo-comercial` |
| 📖 Ler | [guia-insumos-reais.md](guia-insumos-reais.md) — o segundo insumo que mais muda o resultado: as suas calls e objeções reais |
| 🚑 Se travar | o catálogo OB1–OB8 acima |
