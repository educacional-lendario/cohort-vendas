# GUIA MODELO E CUSTO — qual IA usar em cada etapa, e quanto isso vai custar

> **Estou perdido em:** "vou ser cobrado? qual modelo eu escolho? e por que ficou aparecendo **API Error** no meio da aula?".
> **O que você vai ter no final:** a regra de bolso de qual modelo usar em cada momento da aula, o que gasta e o que não gasta, e a certeza de que erro de API não apaga o seu trabalho.
> **Fontes cruzadas:** o `.env.example` deste repo (*"nenhuma das skills desta aula depende de chave de API"*) · o Passo 5 da `diagnostico-gargalos-funil/SKILL.md` (o servidor local e o que ele faz com o token) · a Aula 1 ao vivo, onde o erro de API apareceu 3 vezes e a professora deu a regra de qual modelo usar quando · a documentação oficial de erros da API Claude (códigos 429, 500 e 529).

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 🧰 Ferramenta | Claude Code, Claude Desktop ou Codex instalado | leia [guia-instalar-e-escolher-ferramenta.md](guia-instalar-e-escolher-ferramenta.md) |

## O que esta aula NÃO cobra de você

Boa notícia primeiro, direto do `.env.example` deste repo:

> *"Nenhuma das skills desta aula depende de chave de API. Elas são geração e refino assistidos por IA em cima do que você já sabe do seu negócio."*

Traduzindo:

| Item | Custa? |
|---|---|
| Baixar o projeto (`git clone`) | **Não.** Zero. |
| As skills (todas, das duas aulas) | **Não.** São arquivos de texto dentro do projeto. |
| Chave de API do Apify, Meta, Hotmart | **Não se aplica.** Nenhuma é usada no cohort. |
| Chave de API do **seu CRM** | **Não custa nada** — é gerada por você, de graça, no painel da sua própria ferramenta. Só entra na Aula 2, e **só se** o seu CRM tiver API pública. Sem API, o caminho é exportar CSV, e a aula funciona igual. |
| O `ANTHROPIC_API_KEY` do `.env.example` | **Só se** você for rodar as skills por programa, fora do Claude Code. Se você vai usar o Claude Code normal, deixe em branco. |
| Sua assinatura do Claude ou do ChatGPT/Codex | **Sim** — é o único custo real, e é obrigatório: o Claude Code não roda em plano gratuito. |

⚠️ **O plano gratuito do Claude.ai NÃO roda o Claude Code.** Não é questão de "dar conta" ou não: a documentação oficial é categórica — o Claude Code exige conta **Pro, Max, Team, Enterprise ou Console**. O plano gratuito não inclui acesso, ponto.

Suas opções se você não quer assinar agora:

| Opção | Como |
|---|---|
| **Colar o `SKILL.md`** numa IA de chat gratuita (ChatGPT, Gemini, Claude.ai grátis) | é a **Opção D** do [guia-instalar-e-escolher-ferramenta.md](guia-instalar-e-escolher-ferramenta.md). Funciona pior (a IA não sabe qual arquivo vem depois), mas resolve o problema comercial igual — vá uma skill por dia |
| **Codex** com assinatura ChatGPT paga | se você já paga OpenAI, não precisa pagar Anthropic também |
| **Assinar** | é o único custo real desta aula |

## A regra de qual modelo usar (a da Aula 1)

Um aluno perguntou ao vivo: *"vocês chegaram a fazer teste usando versões mais baratas, ou sempre usa a mais cara?"*. A resposta virou a regra desta seção:

| Momento da aula | Modelo | Por quê (fala da aula) |
|---|---|---|
| **Pesquisa** — concorrentes, mapa de canais, ICP montado do zero | **o mais forte que você tiver** | *"Você não vai fazer pesquisa todo dia do teu concorrente. Cara, usa o melhor. Usa todas as armas que você tem."* |
| **Executar uma skill que já está pronta** — a maior parte da aula | um modelo **intermediário** já resolve | *"quando você já tem um direcionamento, já tem uma skill, não tem necessidade de ser o mais caro."* |
| **Revisar e corrigir** um documento que a skill já entregou | intermediário | é edição em cima de texto existente, não criação do zero |

Traduzindo pra prática: as skills que mais se beneficiam do modelo forte são a **Skill 1** (quando você não tem offerbook e ela vai pesquisar concorrentes na web), a **Skill 2** (Mapa de Canais a Explorar, que também pesquisa) e a **Skill 3** (ICP montado do zero). As demais rodam bem em modelo intermediário.

Na **Aula 2**, a mesma regra: a Skill 3 (`/diagnostico-gargalos-funil`) é a que pede mais do modelo, porque monta calculadora e gráficos junto com a leitura. As outras duas rodam bem em intermediário.

## O servidor local da Aula 2 (o que é, e o que ele NÃO gasta)

Se o seu CRM tiver API, a Skill 3 da Aula 2 pode subir um **servidor local** (Node.js ou Python) na sua máquina pra buscar as oportunidades por etapa. Isso assusta quem nunca viu, então, em ordem:

| Pergunta | Resposta |
|---|---|
| **Isso custa alguma coisa?** | Não. Roda na sua máquina, não é serviço contratado. Não há mensalidade, não há consumo. |
| **Isso gasta a minha assinatura de IA?** | Não. Quem conversa com o CRM é o servidor, não o modelo. O gasto de IA é o de sempre: a conversa da skill. |
| **Fica ligado pra sempre?** | Não. Ele só busca dado quando você abre a página ou clica em "atualizar". Não fica escutando nada em tempo real. |
| **Meu token de API vai parar no navegador?** | **Não.** É exatamente por isso que existe o servidor local: quem faz a chamada é ele, e o navegador só recebe o número já calculado. |
| **Sou obrigado a usar?** | Não. Se o seu CRM não tem API — ou se você não quer —, o caminho é exportar CSV. A skill entrega o mesmo diagnóstico. |

⚠️ **A regra de segurança que vale pra Aula 2 inteira:** nenhuma skill pede a **senha** do seu CRM pra guardar em lugar nenhum. Token de API você gera e revoga no painel; senha, não se entrega. Se algo pedir sua senha em texto, pare.

**Como trocar de modelo:**

| Ferramenta | Como |
|---|---|
| Claude Code / Claude Desktop | digite `/model` e escolha da lista |
| Codex | escolha o modelo no menu da interface, ou `codex --model <nome>` |

## Erro de API: o que é, e por que não é culpa sua

Na Aula 1 isso apareceu três vezes ao vivo (*"mais um erro de API"*, *"olha lá, mais um erro de API"*). A professora comentou que hoje o Claude **espera e tenta de novo sozinho**, e não trava mais como travava antes.

Os três erros que você pode ver, e o que cada um significa:

| Código | O que significa | Conta contra sua cota? | O que fazer |
|---|---|---|---|
| **529 — `overloaded_error`** | O serviço está lotado **para todo mundo** naquele instante | **Não** | Espere alguns minutos. A ferramenta já tentou de novo antes de te mostrar a mensagem. |
| **500 — `api_error`** | Erro interno do lado deles | **Não** | Espere e tente de novo. Se repetir muito, cheque a página de status oficial. |
| **429 — `rate_limit_error`** | Você mandou pedidos demais / bateu o limite do **seu** plano | **Sim** | Espere a janela do seu plano renovar, ou reduza o ritmo. |

⚠️ **O mais importante:** erro de API **não apaga o seu trabalho**. Tudo que a skill já escreveu está salvo em arquivo na sua pasta. Se ela parou no meio, você pede *"continue de onde parou"* e ela retoma. Não recomece a skill do zero por causa disso.

## Passo a passo — quando o erro aparecer

1. **Não feche nada.** Leia o número do erro na mensagem.
2. Se for **529 ou 500**: espere de 1 a 5 minutos. Não fique apertando Enter repetidamente — isso piora.
3. Peça pra continuar:
   ```
   continue de onde você parou
   ```
4. Se depois de 3 tentativas espaçadas continuar: troque de modelo com `/model` e tente de novo (às vezes a lotação é só de um modelo específico).
5. Se for **429**: pare por hoje nessa ferramenta. Ou continue pela **Opção D** (colar o `SKILL.md` em outra IA), ou espere a renovação do seu plano.
6. Antes de recomeçar qualquer coisa, confira o que já foi salvo: abra o `central-de-entregas.html` da pasta do projeto (veja [guia-entregaveis-e-central.md](../04-operacao/guia-entregaveis-e-central.md)).

## Teste de sucesso

Rode `/model` na sua ferramenta. **Funcionou se:** aparece uma lista de modelos e você consegue identificar qual está ativo agora. Escolha um intermediário pra rodar a aula, e guarde na cabeça que na Skill 1 (se você for sem offerbook) vale subir pro mais forte.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| Q1 | "Vou ser cobrado por rodar as skills?" | Confusão entre o projeto e a assinatura | o projeto é gratuito; o custo é a sua assinatura de IA, que você já paga independente desta aula |
| Q2 | O `.env.example` pede uma chave e eu não tenho | Leitura fora de contexto | você **não precisa** preencher nada pra esta aula. O `ANTHROPIC_API_KEY` só serve pra quem vai rodar as skills por programa. Deixe em branco |
| Q3 | Acabou meu limite no meio da Skill 4 | Erro 429 (limite do plano) | 1) confira o que já foi salvo na Central de Entregas 2) espere a renovação 3) ou continue naquela skill pela Opção D (colar o `SKILL.md` em outra IA) 4) não refaça as skills já entregues |
| Q4 | `API Error 529` / `overloaded_error` no meio da execução | Serviço lotado do lado do fornecedor, não seu | 1) espere 1-5 min 2) peça *"continue de onde você parou"* 3) se repetir 3x, troque de modelo com `/model` 4) **não** conta contra sua cota |
| Q5 | `API Error 500` e a skill parou na metade do documento | Erro interno do fornecedor | 1) o que já foi escrito está salvo em arquivo 2) peça *"continue de onde você parou"* 3) se o arquivo ficou pela metade, peça *"releia o arquivo X e complete o que faltou"* |
| Q6 | Troquei pro modelo mais barato e o resultado ficou raso | Modelo fraco demais para a etapa de pesquisa | volte pro modelo forte **nas etapas de pesquisa** (Skills 1, 2 e 3 sem offerbook) e rode aquela skill de novo — veja [guia-revisar-e-corrigir.md](../04-operacao/guia-revisar-e-corrigir.md) |
| Q7 | A ferramenta ficou minutos "pensando" sem responder | Normal: as skills desta aula geram documentos longos | espere. A Skill 4 (Discovery Script) é a mais demorada porque escreve uma peça de copy por canal |

**Se nada resolver:** print da mensagem com o código do erro + *"o que tem que ser feito? PESQUISE isso antes de responder"*.

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | escolha o modelo (`/model`) e siga pra Skill 1 |
| 📖 Ler | [guia-como-ser-guiado.md](guia-como-ser-guiado.md) — como pedir as coisas pra IA quando travar |
| 🚑 Se travar | o catálogo Q1–Q7 acima |
