# GUIA MÉTRICAS DO COMERCIAL — os números da Aula 1, sem virar planilha de vaidade

> **Estou perdido em:** "sei que preciso medir alguma coisa, mas não sei o quê — e nem se os números que eu tenho querem dizer alguma coisa".
> **O que você vai ter no final:** os poucos números que os entregáveis da Aula 1 já produzem, o que cada um revela, e a régua pra não confundir número bonito com negócio saudável.
> **Fontes cruzadas:** o `SKILL.md` da `/desenho-processo-comercial` (a métrica de forecast por etapa, as duas condições pra ela significar algo, e o gatilho de mudança de conversão) e da `/qualificacao-bant-gpct` (nota de corte e auditoria entre duas pessoas) · o `SKILL.md` da `/diagnostico-gargalos-funil` (Passos 2 e 3: o gate de sanidade, coorte vs estoque, gargalo aparente vs causa real, forecast ponderado e receita em risco) · o acervo interno de formação em bastidores do digital (as métricas do departamento comercial e o mapeamento de motivo de cancelamento) · pesquisa sobre benchmarks de conversão entre etapas e de envelhecimento de pipeline (consultada em 03/08/2026).

## Pré-requisitos (confira ANTES)

| Tipo | Pré-requisito | Não tem? Faça isso |
|---|---|---|
| 📖 Conhecimento | Saber o que é etapa, deal, forecast, ICP e motivo da perda | leia [guia-conceitos-comerciais.md](../02-conhecimento-minimo/guia-conceitos-comerciais.md) |
| 📄 Artefato | Um lugar onde os deals estão registrados por etapa (planilha, quadro ou CRM) | veja [guia-e-depois.md](guia-e-depois.md), Passo 2 |

## O escopo deste guia (o que ele NÃO cobre)

⚠️ Aqui só entram os números que os **entregáveis da Aula 1 já produzem**, calculáveis em planilha, na mão, sem ferramenta nenhuma. Painel de CRM, cálculo automático e diagnóstico de gargalo são a **Aula 2** — e ela já existe: `/diagnostico-gargalos-funil` faz esses mesmos números com o dado do seu pipeline e monta a calculadora.

**Por que ainda vale ler isto se a Aula 2 calcula sozinho:** porque a skill entrega o número, não o julgamento. Quem decide se aquele número quer dizer alguma coisa é você — e as duas seções abaixo (a régua antes dos números, e o que cada um revela) são justamente esse julgamento.

## A régua antes dos números

Duas frases que separam medição útil de teatro:

1. **Só meça o que muda uma decisão.** Se o número sobe ou desce e você faria exatamente a mesma coisa, não meça.
2. **Nem toda métrica se aplica ao seu modelo.** Taxa de renovação só existe se você vende recorrência. Não force.

## Os 5 números da Aula 1

### 1. Conversão entre etapas (o mais importante de todos)

**O que é:** de cada 10 deals que entram numa etapa, quantos passam pra próxima.

**Como calcular:** deals que saíram da etapa X para a Y ÷ deals que entraram na etapa X.

**O que ele revela:** a etapa onde você perde é a etapa que precisa de trabalho. E é o gatilho de processo nº 2 da Skill 1 — queda **ou alta** consistente por 2+ ciclos manda revisar o funil.

Referências de mercado, só pra você não se assustar com o próprio número:

| Conversão | Faixa comum |
|---|---|
| Lead que o marketing entrega → lead que vendas aceita como qualificado | 10% a 30% (times bem alinhados chegam a 25-40%) |
| Abaixo de 15% | sinal de problema na qualificação ou no follow-up, não no vendedor |
| Do lead qualificado até a venda fechada | 6% a 9% |

⚠️ **Leia com cuidado:** essas faixas são de mercado B2B em geral. O seu número vai depender do ticket, do ciclo e da origem do lead. O valor está em comparar você **com você mesmo** ao longo do tempo, não com a média de alguém.

**A leitura que a aula pede:** conversão travando sempre na mesma etapa, em vários deals, não é problema de vendedor.

> *"Se é uma falha do comercial, se é uma falha [de que] o cliente não está alinhado, tem que melhorar o ICP."*

#### As duas formas de calcular isso — e por que a diferença importa

A fórmula lá em cima (*saíram ÷ entraram*) é a versão **por coorte**, e é a boa. Só que ela exige uma coisa que muita planilha não tem: **data de entrada em cada etapa**. Sem isso, o que quase todo mundo acaba calculando é outra coisa:

| Forma | Como se calcula | O que ela mede |
|---|---|---|
| **Coorte** (preferencial) | dos deals que **entraram** nesta etapa nos últimos 90 dias, quantos avançaram | conversão de verdade |
| **Estoque** (fallback) | quantos estão **agora** na etapa seguinte ÷ quantos estão agora nesta | onde olhar primeiro — nada além disso |

⚠️ **Se você só tem o estoque, diga isso em voz alta ao apresentar o número.** Leitura de estoque é sensível a etapas com velocidades diferentes: uma etapa rápida sempre parece ter poucos cards, e isso não quer dizer que ela converte mal.

⚠️ **Estoque acima de 100% não é uma etapa excelente.** Chegar mais negócio na etapa seguinte do que existe na atual é matematicamente impossível como taxa real — só acontece quando entrou um lote de cards sem passar de verdade pela etapa anterior. É a assinatura de uma **etapa decorativa**, e ela contamina a média de todas as outras. Tire esse par de etapas da conta de "média saudável" antes de comparar qualquer coisa.

#### A etapa pior não é necessariamente a culpada

Antes de reformar a etapa com a pior conversão, olhe a **de trás**. Se a anterior não tem critério de saída claro, ou se é comum ver vários cards avançando de uma vez, ela está despejando negócio malqualificado na próxima — que trava e leva a culpa.

Isso tem nome: **gargalo aparente** na etapa N, **causa real** na etapa N-1. E vale o contrário também: se a etapa anterior está saudável, o gargalo aparente **é** o gargalo real. Isso é um resultado válido, não sinal de que a análise falhou — não saia procurando problema onde não tem.

### 2. Forecast por etapa (o dinheiro parado no funil)

**O que é:** a soma em R$ dos deals que estão nas 2-3 etapas finais antes do fechamento.

**A analogia:** forecast é o extrato do banco de um dinheiro que ainda não entrou. Se você conta como saldo tudo que "provavelmente vai cair", você toma decisão em cima de dinheiro imaginário. As duas condições abaixo existem justamente pra separar o que está mesmo a caminho do que é só desejo.

⚠️ **Duas condições, sem as quais o número é ficção** — são as que a própria Skill 1 registra:

1. **Todo card nessas etapas precisa ter valor preenchido.** Um card sem valor não é "zero", é um buraco.
2. **Precisa existir um piso de referência** — o volume mínimo de negócios nessas etapas por semana que sustenta a meta. Olhar só o total não cobra nada de ninguém.

E o cuidado que a pesquisa de mercado adiciona: **card velho infla o forecast**, porque ele continua contando o valor cheio mesmo quando a chance de fechar despencou. Negócio que ultrapassa o ciclo médio converte a ~23%, contra ~68% dos que fecham dentro dele. Limpe o funil antes de somar — veja [guia-gatilhos-e-cards-parados.md](guia-gatilhos-e-cards-parados.md).

**A rotina que faz o forecast valer:** revisão card a card, com quem está negociando. Não é olhar o painel — é conversar sobre cada negócio. Isso bate meta mais do que dashboard. Regra prática dessa revisão: **todo card sem próximo passo definido conta como parado**, mesmo que tenha mudado de etapa ontem.

#### A versão honesta: forecast ponderado

A soma bruta das etapas finais é o forecast de quem quer se animar. O número que decide alguma coisa é o **ponderado pela conversão de cada etapa**:

> R$ 100 mil em Proposta, numa etapa que converte a 40%, valem **R$ 40 mil** de forecast — não R$ 100 mil.

Faça isso etapa por etapa e some. A diferença entre os dois números costuma ser desconfortável, e é exatamente por isso que vale calcular: é a distância entre o que você reporta e o que você recebe.

⚠️ **Nunca comunique forecast como certeza**, nem o ponderado. É projeção baseada em padrão histórico. Isso é regra dura se o seu nicho é regulado.

#### E a receita em risco

Um número que a Aula 1 não produz e vale conhecer desde já, porque ele é o que transforma "essa etapa converte mal" em decisão: **quanto o funil geraria a mais se a etapa gargalo chegasse à média das outras**, multiplicado pelo ticket médio real e pela conversão daí até o fechamento.

Duas cautelas que vêm junto:

- **Ticket médio real** é a média dos negócios **já ganhos**. Nunca um número assumido, nunca o preço de tabela.
- **A unidade de tempo muda com o seu ciclo.** Ciclo curto e volume alto: expresse por mês, faz sentido operacional. Ciclo longo com contrato anual: mensalizar é artificial — expresse como total represado no pipeline atual, e diga que leva um ciclo completo pra se realizar.

### 3. Tempo médio por etapa

**O que é:** quantos dias um deal passa em cada etapa, em média.

**Para que serve:** é o que calibra o seu gatilho de estagnação. A referência de 7 dias que a skill usou é ponto de partida; o certo é **1,5× a 2× o seu próprio tempo médio** naquela etapa.

Faixas de referência por porte, se você ainda não tem histórico:

| Porte | Discovery | Proposta |
|---|---|---|
| Pequeno / venda rápida | 5-10 dias | 3-10 dias |
| Médio | 7-14 dias | 7-14 dias |
| Complexo / enterprise | 14-30 dias | 14-30+ dias |

### 4. Motivo da perda (o número que não é número)

**O que é:** a contagem de deals perdidos **por categoria de motivo**.

⚠️ É o dado mais negligenciado e o mais útil. Sem ele, "80 perdidos, 1 venda" não tem leitura nenhuma. Com ele, você sabe de quem é o problema:

| Motivo mais frequente | O problema está em |
|---|---|
| Lead sem fit / sem dor real | **marketing** — captação desalinhada, corrija o ICP |
| Preço | **oferta ou discovery** — a dor não virou número |
| Faltou funcionalidade / escopo | **produto** — vira roadmap |
| Concorrente | **posicionamento** — veja [guia-diferencial-e-concorrencia.md](../02-conhecimento-minimo/guia-diferencial-e-concorrencia.md) |
| Sumiu / sem resposta | **processo** — a régua de follow-up falhou |

Da aula, sobre não aceitar motivo genérico:

> *"Não é simplesmente falar que ele comprou do concorrente. Não: ele comprou do concorrente — por quê?"*

### 5. Taxa de cancelamento (se aplica ao seu modelo)

**O que é:** cancelamentos ÷ vendas no período.

E, como no motivo da perda, o número sozinho não serve. É preciso mapear **por que** cancelou: foi financeiro, foi produto, foi expectativa desalinhada, ou foi porque ele nunca chegou a usar? Veja [guia-onboarding-e-pos-venda.md](guia-onboarding-e-pos-venda.md).

⚠️ **Cancelamento por "expectativa" é métrica do comercial**, não do produto — quer dizer que a venda prometeu além.

## Os números que NÃO são desta aula

Pra você não se perder tentando medir tudo:

A boa notícia: a maior parte desta tabela **deixou de ser espera e virou endereço**. A Aula 2 já saiu.

| Métrica | Onde ela entra |
|---|---|
| Conversão calculada sozinha, gargalo apontado, receita em risco | **Aula 2** → `/diagnostico-gargalos-funil` |
| Temperatura do lead (Quente / Morno / Frio), pontuação por critério | **Aula 2** → `/lead-scoring-ia` |
| Cobertura de campo, duplicidade, card zumbi, confiabilidade da origem | **Aula 2** → `/montagem-higiene-crm` |
| Tempo médio de atendimento, tempo de primeira resposta, CSAT | quando existir ferramenta de atendimento — segue fora do escopo das duas aulas |
| Mensagens por vendedor, participação da equipe nas vendas | quando existir time — segue fora do escopo |
| SLA formal entre marketing e vendas | a Aula 1 entrega o contrato de dados, que é o insumo; formalizar é decisão sua |
| Health score, churn, NRR, expansão de conta | pós-venda → veja [guia-onboarding-e-pos-venda.md](guia-onboarding-e-pos-venda.md) e a Skill 8 (`/squad-sales-bonus`) |
| Taxa de renovação | só se você vende assinatura. Com o CRM montado na Aula 2, fica calculável |
| Custo de aquisição, retorno sobre investimento em anúncio | é do **funil de marketing**, não do comercial |

⚠️ **O que continua sendo trabalho seu, mesmo com a Aula 2 rodando:** o **motivo da perda** (número 4 abaixo). Nenhuma skill inventa motivo — ela só conta o que você categorizou. Campo de motivo vazio é o único dos 5 números que a automação não salva.

## A planilha mínima (cabe em 6 colunas)

Se você ainda não tem CRM, isto basta pra produzir os 5 números:

| Coluna | Exemplo |
|---|---|
| Cliente | Metalúrgica X |
| Etapa atual | Discovery |
| Valor (R$) | 12.000 |
| Data da última movimentação | 28/07 |
| Próxima ação + data | ligar dia 05/08 |
| Se perdido: motivo | preço / sem fit / concorrente / sumiu / produto |

Com essas seis colunas você calcula conversão por etapa, forecast, tempo parado e motivo da perda. Nada mais é necessário nesta fase.

## Peça pra IA

| Situação | Cole isto |
|---|---|
| **Calcular tudo de uma vez** | "Esta é a minha planilha de deals: [cole]. Calcule: conversão entre cada etapa, forecast (só cards com valor preenchido), tempo médio por etapa, e o motivo de perda mais frequente. Depois me diga qual é o **gargalo**, em uma frase." |
| **Montar a planilha do zero** | "Monte uma planilha simples (formato de tabela em texto) pra eu acompanhar meus deals, com as colunas mínimas pra calcular conversão por etapa, forecast e motivo de perda. Minhas etapas são: [cole as etapas do meu processo]." |
| **Limpar o funil antes de somar** | "Estes são meus deals nas etapas finais: [cole com data da última movimentação]. Meu ciclo médio é [X]. Marque quais estão velhos demais pra continuar contando no forecast, e me dê o forecast antes e depois da limpeza." |
| **Definir as categorias de motivo de perda** | "Meu negócio é [descreva]. Sugira 5 categorias fechadas de motivo de perda que eu possa usar num menu suspenso, cobrindo os casos reais do meu tipo de venda. Sem categoria 'outros'." |
| **Entender um número que me assustou** | "Minha conversão da etapa [X] para [Y] é de [N]%. Meu ticket é [valor], ciclo [tempo], e os leads vêm de [origem]. Isso é preocupante ou normal pro meu tipo de venda? E o que eu olho primeiro pra melhorar?" |

## Teste de sucesso

Responda com os seus dados reais:

1. Qual é a etapa em que você **mais perde** deals?
2. Quanto tem parado no funil (forecast) **considerando só cards com valor preenchido**?
3. Qual é o motivo de perda **mais frequente** dos seus últimos 10 deals perdidos?

**Funcionou se:** você respondeu as três olhando dado, não memória. Se travou na 3, o campo de motivo não está sendo preenchido — e é a primeira coisa a corrigir.

## POSSÍVEIS ERROS — catálogo

| # | Sintoma | Causa provável | O que fazer (em ordem) |
|---|---|---|---|
| MT1 | Meu forecast nunca bate com o que fecha | Cards velhos e cards sem valor | 1) exija valor em todo card das etapas finais 2) limpe o que passou de 2× o tempo médio da etapa 3) faça revisão card a card, não só olhar total |
| MT2 | Comparei minha conversão com um benchmark e me desesperei | Benchmark de mercado não é a sua régua | compare você com você: mês a mês. Ticket, ciclo e origem de lead mudam tudo |
| MT3 | Não consigo calcular conversão por etapa | Falta o registro de quando o deal entrou/saiu de cada etapa | acrescente a coluna "data da última movimentação". Sem histórico de etapa, não existe conversão por etapa |
| MT4 | Todo mundo preenche o CRM/planilha errado | Campo que não devolve nada pra quem preenche | corte campo que não muda decisão. A régua da Skill 1: *"só exigir informação que muda o comportamento do vendedor ou a qualidade do forecast"* — cada campo a mais é um pedágio entre o vendedor e a próxima conversa |
| MT5 | Meço tudo e não decido nada | Métrica de vaidade | fique nos 5 deste guia. O resto ou é Aula 2 (e a skill calcula sozinha), ou não muda decisão nenhuma |
| MT6 | Meu motivo de perda mais comum é "outros" | Categorias mal definidas ou preenchimento no automático | 1) limite a 5-6 categorias fechadas 2) proíba "outros" sem uma frase de explicação |
| MT7 | A conversão subiu e eu comemorei, mas o faturamento caiu | Conversão alta com volume baixo, ou tickets menores | olhe sempre conversão **e** volume juntos. Conversão de 100% em 2 deals não é performance |
| MT8 | Minha taxa de qualificação está baixíssima | Lead chegando frio demais | não é problema do vendedor: é ICP ou captação. Devolva o dado pro marketing, com o motivo categorizado |
| MT9 | Uma etapa minha converte acima de 100% | Você calculou estoque, não coorte — e essa etapa provavelmente é decorativa | 1) é matematicamente impossível como taxa real 2) confira se aquela etapa tem critério de saída de verdade 3) tire esse par de etapas da média antes de comparar as outras |
| MT10 | Reformei a etapa com a pior conversão e não melhorou nada | Gargalo aparente: a causa estava na etapa anterior | olhe a etapa **de trás**: ela tem critério de saída claro, ou os cards avançam em lote? Se avançam em lote, é ela que precisa de trabalho |
| MT11 | Rodei a Aula 2 e ela se recusou a me dar o número do gargalo | Gate de sanidade: a skill não calcula em cima de base ruim | é comportamento correto, e te poupou de um número confiante e errado. Ela vai dizer o que corrigir primeiro — normalmente duplicidade, valor vazio ou etapa sem critério. Corrija e rode de novo |

**Se nada resolver:** cole a sua planilha numa conversa e peça: *"calcule a conversão entre etapas, o forecast e o motivo de perda mais frequente destes deals, e me diga qual é o gargalo."*

## Pronto. Próximos passos

| Agora | O quê |
|---|---|
| ▶️ Fazer | monte a planilha de 6 colunas e preencha com os deals que você tem hoje — leva 20 minutos |
| 📖 Ler | [guia-gatilhos-e-cards-parados.md](guia-gatilhos-e-cards-parados.md) — pra limpar o funil antes de somar o forecast |
| ▶️ Fazer (Aula 2) | com a planilha preenchida, rode `/diagnostico-gargalos-funil` — ela calcula tudo isto com o seu dado e entrega uma calculadora onde você simula cenário |
| 🚑 Se travar | o catálogo MT1–MT11 acima |
