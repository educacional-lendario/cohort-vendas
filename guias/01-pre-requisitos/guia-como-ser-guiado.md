# GUIA COMO SER GUIADO — os 4 prompts que destravam qualquer situação

> **Estou perdido em:** "eu tenho a IA aberta e tenho os guias… mas fico travado sem saber o que PEDIR pra ela".
> **O que você vai ter no final:** 4 prompts prontos pra copiar e colar que cobrem quase toda travada, mais os atalhos por cenário desta aula. Ser guiado é uma habilidade — e cabe numa página.
> **Fontes cruzadas:** a seção "Se o aluno se perder" que existe dentro de cada `SKILL.md` deste repo, nas duas aulas (todas respondem onde você está e o que falta) · o `docs/SKILLS-INDEX.md` (FAQ de suporte) · o funcionamento real das ferramentas: elas **leem os arquivos que você apontar** · pesquisa sobre técnicas de prompt iterativo e passo a passo (consultada em 03/08/2026), que confirma por que pedir "um passo por vez" funciona melhor que pedir tudo.

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 🧰 Ferramenta | Claude Code, Claude Desktop ou Codex aberto **na pasta do projeto** | leia [guia-baixar-e-abrir-o-projeto.md](guia-baixar-e-abrir-o-projeto.md) |

## A ideia em uma frase

A IA enxerga os seus arquivos e sabe pesquisar na web — **o gargalo é você pedir do jeito certo.** Os 4 prompts abaixo cobrem quase tudo. Copie e cole trocando o que está entre colchetes.

## Os 4 prompts

| # | Situação | Cole isto |
|---|---|---|
| 1 | **Travado num passo** | "Estou tentando fazer [X] e estou preso NISTO aqui: [cole a mensagem de erro ou descreva a tela]. Me guie passo a passo a partir daqui, um passo por vez, esperando eu confirmar antes de avançar." |
| 2 | **Erro que você não entende** | "Quando eu faço [X], acontece [Y]. O que tem que ser feito? **PESQUISE** isso antes de responder." — a palavra PESQUISE faz a IA buscar na web em vez de chutar. |
| 3 | **Não sabe onde parou** | "Olhe os arquivos desta pasta e faça um **checklist** do que já foi entregue das skills do cohort e do que ainda falta." |
| 4 | **Tem um guia e preguiça de ler** | aponte o arquivo (ex.: `guias/03-insumos/guia-offerbook-do-marketing.md`) e peça: "leia este guia e **me guie por ele**, um passo por vez, conferindo comigo antes de avançar." |

## O atalho exclusivo desta aula

Todas as skills, das duas aulas, têm uma resposta pronta pra quando você se perde no meio delas. Basta pedir, com estas palavras:

```
me mostra onde eu estou
```

Ela responde quatro coisas: em qual skill você está (ex.: *"Skill 3 de 7 da Aula 1"*, ou *"Skill 1 de 3 da Aula 2"*), por que está ali, o que está construindo, e **o que falta pra entrega ficar 10/10**. Não invente uma pergunta genérica — essa frase aciona uma seção que existe dentro de cada `SKILL.md`.

## Atalhos por situação

| Situação | O que fazer |
|---|---|
| "Não sei nem por onde começar" | rode `/desenho-processo-comercial` — é a primeira skill, e ela pergunta tudo que precisa |
| "Não sei o que já entreguei" | abra o `central-de-entregas.html` na raiz do projeto, ou use o prompt 3 |
| "Não sei o que essa skill vai me perguntar" | [guia-diagnostico-antes-de-rodar.md](../02-conhecimento-minimo/guia-diagnostico-antes-de-rodar.md) |
| "A skill entregou algo que eu não gostei" | [guia-revisar-e-corrigir.md](../04-operacao/guia-revisar-e-corrigir.md) — você pode discordar e mandar refazer |
| "Não entendi um termo do documento" | [guia-conceitos-comerciais.md](../02-conhecimento-minimo/guia-conceitos-comerciais.md) |
| "A skill parou no meio" | peça `continue de onde você parou` — veja [guia-modelo-e-custo.md](guia-modelo-e-custo.md) |
| "Não sei qual problema é o meu" | volte pro [roteador de guias](../README.md) e ache a linha "Estou perdido em…" mais parecida |

## 4 manhas que multiplicam o resultado

1. **Print vale mais que descrição.** "Deu erro" não ajuda; a mensagem literal (ou o print colado) resolve.
2. **UM passo por vez.** Peça explicitamente ("me dê um passo, espere eu confirmar"). Sem isso a IA despeja 20 passos que você não vai seguir — e não é só chatice pra você: quebrar a tarefa em etapas também faz a IA prestar mais atenção em cada parte, em vez de tratar tudo por cima. É o mesmo motivo pelo qual "pense passo a passo antes de responder" melhora a resposta.
3. **O progresso mora nos ARQUIVOS, não na conversa.** Pode fechar tudo sem medo: os `.md` e `.html` continuam na pasta. Num chat novo, o prompt 3 reconstrói onde você estava.
4. **Aponte o arquivo.** "Leia `processo-comercial-minhaempresa.md` e me diga se a etapa 3 faz sentido" rende infinitamente mais que "o que você acha do meu processo?".

## Teste de sucesso

Use o prompt 3 agora:

```
Olhe os arquivos desta pasta e faça um checklist do que já foi entregue das skills do cohort e do que ainda falta.
```

**Funcionou se:** a resposta lista arquivos **reais** da sua pasta (com os nomes que existem lá) e aponta o que falta de forma concreta. Se ela responder genérico, sem citar nome de arquivo, é sinal de que a ferramenta foi aberta na pasta errada — veja o `R6` do [guia-baixar-e-abrir-o-projeto.md](guia-baixar-e-abrir-o-projeto.md).

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| I1 | A IA responde genérico, sem olhar seus arquivos | O pedido não apontou arquivo nem pasta | inclua o caminho no pedido (`processo-comercial-x.md`, `guias/...`) — apontar arquivo muda tudo |
| I2 | A IA "chuta" a solução de um erro | Faltou mandar pesquisar | use o prompt 2, com a palavra **PESQUISE** em maiúsculas |
| I3 | Resposta gigante que você não consegue seguir | Você pediu tudo de uma vez | peça "um passo por vez, espere eu confirmar" |
| I4 | Cada conversa nova "esquece" tudo | O contexto vive na conversa; os seus ARQUIVOS não somem | abra a conversa nova com o prompt 3 |
| I5 | Você nem sabe o que perguntar | Cenário do roteador | abra o [roteador de guias](../README.md), ache a linha "Estou perdido em…" mais parecida, e use o prompt 4 com o guia dela |
| I6 | Pedi "me mostra onde eu estou" e ela respondeu genérico | Você não está dentro de uma skill, ou a ferramenta está na pasta errada | 1) confira com `ls .claude/skills` 2) se estiver certo, use o prompt 3 no lugar |
| I7 | A IA reescreveu meu documento inteiro quando eu só queria mudar uma parte | Pedido amplo demais | seja cirúrgico: "no arquivo X, na seção Y, troque APENAS [isto] por [aquilo]. Não mexa em mais nada." |

**Se nada resolver:** print + descrição do que você queria, no grupo do cohort.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | use o prompt 3 agora e descubra em 30 segundos onde você está |
| 📖 Ler | [guia-conceitos-comerciais.md](../02-conhecimento-minimo/guia-conceitos-comerciais.md) — o vocabulário que os documentos vão usar |
| 🚑 Se travar | o catálogo I1–I7 acima — e sim, pode usar o prompt 1 pra pedir ajuda sobre este guia |
