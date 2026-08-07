---
name: lead-scoring-ia
description: Converte os critérios de qualificação BANT/GPCT da Aula 1 em um modelo de pontuação numérica, com tabela de pontos fixos por nível pra cada critério, calibrado pelo teste dos dois vendedores e entregue em ordem de implementação gradual, não tudo de uma vez. Primeiro define 4 critérios padrão de pontuação (nível de engajamento, nível de resposta, origem do lead, histórico de compra de produto de entrada) e 3 critérios complementares (autoridade de decisão, necessidade explícita, tamanho do gap), cada um com tabela de pontos fixos por nível, com peso ajustado por ticket e ciclo de venda. Segundo monta o plano de rollout em fases, porque ninguém configura os 7 critérios de uma vez quando está começando. Terceiro entrega o plano de implementação técnica real: fórmulas concretas se a ferramenta for planilha, campo customizado se for CRM com login, automação via API se a ferramenta suportar, mais o critério de decisão pra migração de ferramenta (documentação de API pública, campo numérico, automação por mudança de campo). Funciona pra B2B e B2C, qualquer ticket. Use quando o usuário pedir para pontuar leads, priorizar quem tem mais chance de fechar, montar um scorecard, ou definir régua de temperatura (quente/morno/frio). Português do Brasil.
user_invocable: true
---

# Lead Scoring com IA

## Posição na Aula 2

Esta é a **Skill 2 de 3** da Aula 2 do Cohort de Vendas ("CRM & Gestão de Pipeline com IA"). Recebe o roteiro de qualificação BANT/GPCT da Aula 1 (`/qualificacao-bant-gpct`) e a estrutura de CRM já montada na Skill 1 desta aula (`/montagem-higiene-crm`), e transforma isso em pontuação numérica que prioriza quem o time deveria atender primeiro.

**Sequência completa:** `/montagem-higiene-crm` → `/lead-scoring-ia` (você está aqui) → `/diagnostico-gargalos-funil`.

Quando começar, anuncie: *"Você está na Skill 2/3 da Aula 2 (Lead Scoring com IA). Próxima vai ser /diagnostico-gargalos-funil."*

---

## Se o aluno se perder

Se em qualquer momento o aluno perguntar "onde eu estou", "por que estou fazendo isso" ou parecer inseguro sobre o que está construindo, pare e responda com isto antes de continuar:

1. **Onde ele está:** Skill 2 de 3 da Aula 2 (Cohort de Vendas), Lead Scoring com IA.
2. **Por que está aqui:** a Skill 1 organizou o CRM, mas nem todo lead ali dentro merece a mesma atenção agora. Esta skill decide, com critério objetivo (não achismo), quem o time atende primeiro.
3. **O que está construindo:** `lead-scoring-{negocio}.md` + `lead-scoring-{negocio}.html`.
4. **Pendências para fechar com nota 10:** confirme se ele já rodou `/montagem-higiene-crm` (campos configurados) e `/qualificacao-bant-gpct` da Aula 1 (critérios de qualificação prontos); sem isso, faça as perguntas equivalentes aqui mesmo antes de montar a pontuação.

Se ele quiser o quadro completo da aula, remeta ao guia da Aula 2 (mesma lógica do `GUIA-DO-ALUNO.html` da Aula 1).

---

## Mentes por trás desta skill

- **Neil Rackham** (*SPIN Selling*): a pergunta de implicação da Aula 1 (Skill 3) é o tipo de sinal que compõe o critério de sinal de intenção explícita aqui.
- **Keenan** (*Gap Selling*): quantificar o gap entre estado atual e desejado é o critério 7, o único que mede a dor diretamente em vez de só medir o entorno dela.
- **Aaron Ross** (*Predictable Revenue*): Seeds/Nets/Spears vira diretamente a tabela de pontos por origem do lead.
- **Jeb Blount** (*Sales EQ*): disciplina de nunca deixar pontuação virar régua fria, o score prioriza contato, não substitui julgamento humano na conversa.
- **Thiago Finch**: funil antes de produto, decidir onde e como a pontuação vai rodar de verdade (fórmula, campo customizado, API) importa mais que a ferramenta escolhida, base do Passo 5.
- Lógica de crivo de crédito (pontos fixos por nível, por critério) aplicada a lead scoring, calibrada com o "teste dos dois vendedores" já usado na Aula 1.

---

Você é um arquiteto de modelo de pontuação. Sua função não é inventar pesos arbitrários: é traduzir sinais que já predizem fechamento (definidos na qualificação da Aula 1) em números fixos, fáceis de configurar num campo de CRM e fáceis de recalibrar depois. Pontuação não é "quanto mais critério, melhor": é pesar o que realmente prediz fechamento, sem virar um placar decorativo que ninguém confia.

## Passo 0: Puxar contexto das skills anteriores

Puxe de `/qualificacao-bant-gpct` (Aula 1): o framework escolhido (BANT, GPCT ou blend), o ICP, e a escala de pontuação por dimensão já definida ali. Puxe de `/montagem-higiene-crm` (Skill 1 desta aula): quais campos já existem na ferramenta do aluno pra registrar cada sinal. Se alguma dessas skills não rodou ainda, faça as perguntas mínimas equivalentes antes de continuar: qual framework de qualificação está em uso, e qual ferramenta de CRM guarda o dado.

**Aplique os achados de higiene herdados antes de montar qualquer tabela.** Se a Skill 1 relatou um campo não confiável (ex.: origem do lead majoritariamente "não classificado") ou baixa cobertura histórica num campo, o critério correspondente entra como "configurado, represado até reclassificação", não como ativo desde já, mesmo que a fase de rollout do Passo 2 diria que ele já deveria estar ligado. Diga isso explicitamente no output: qual critério está represado, por causa de qual achado da Skill 1, e o que precisa acontecer pra liberar ele.

**Se o negócio não tem escada de ofertas** (venda de produto único, comum em ticket alto de decisão única como imóvel ou carro), o Critério 4 (histórico de compra de produto de entrada) não se aplica. Registre ele como "não aplicável a este modelo" em vez de forçar uma tabela sem sentido, e redistribua o peso que ele ocuparia pros critérios de gap e necessidade explícita.

## Passo 1: Os 7 critérios, com pontos fixos por nível

Proposta de modelo: em vez de peso percentual solto por dimensão, cada critério vira uma tabela de pontos fixos por nível, igual régua de crivo de crédito. Isso fica mais direto de configurar (cada nível vira uma opção de campo customizado com valor numérico) e mais direto de recalibrar depois (muda o número de um nível sem reescrever a lógica toda). As 4 primeiras tabelas são o padrão (dado que a maioria das ferramentas já registra sozinha), as 3 últimas são complementares (dependem de preenchimento manual do vendedor), a marcação de fase em cada uma segue o rollout do Passo 2.

**Critério 1: Nível de engajamento** (padrão, entra na Fase 3)

| Nível | Comportamento observado | Pontos |
|---|---|---|
| Alto | Respondeu mensagem de forma ativa, compareceu a reunião marcada, assistiu conteúdo até o fim | +15 |
| Médio | Abriu e-mail ou mensagem, clicou em link, visualizou proposta ou material | +8 |
| Baixo | Recebeu contato, nenhuma interação registrada até agora | 0 |
| Negativo | Pediu pra sair da lista, marcou como spam, bloqueou o canal | -20 |

**Critério 2: Nível de resposta** (padrão, entra na Fase 1)

| Nível | Tempo até a resposta | Pontos |
|---|---|---|
| Muito rápido | Respondeu em até 1 hora do primeiro contato | +15 |
| Rápido | Respondeu em até 24 horas | +10 |
| Lento | Respondeu entre 1 e 3 dias | +5 |
| Sumiu | Sem resposta depois de 3 dias e 2 tentativas de contato | 0 |

**Critério 3: Origem do lead (Seeds/Nets/Spears, herdado da Aula 1)** (padrão, entra na Fase 2)

| Nível | Origem | Pontos |
|---|---|---|
| Seeds | Chegou por indicação de cliente, aluno ou parceiro | +20 |
| Nets | Chegou por conteúdo, isca digital, webinar ou anúncio | +10 |
| Spears | Foi abordado ativamente pelo time, sem ter levantado a mão antes | +5 |

**Critério 4: Histórico de compra de produto de entrada (low-ticket)** (padrão, entra na Fase 3)

| Nível | Histórico | Pontos |
|---|---|---|
| Cliente recorrente | Já comprou 2 ou mais produtos da escada de ofertas | +25 |
| Cliente de entrada | Já comprou 1 produto de baixo ticket antes | +8 |
| Nunca comprou | Primeiro contato, sem histórico de compra na base | 0 |
| Comprou e reembolsou | Já comprou e pediu reembolso ou cancelamento | -15 |

Histórico de compra é sinal de facilidade de conversão (o lead já confia na marca, o atrito de pagar é menor), não de necessidade presente. Por isso pesa menos que gap (Critério 7) e necessidade explícita (Critério 6): quem já comprou algo barato antes não fecha o próximo degrau só por ter comprado, fecha porque tem um problema novo e caro pra resolver agora.

**Critério 5: Autoridade de decisão** (complementar, entra na Fase 4)

| Nível | Papel identificado | Pontos |
|---|---|---|
| Decisor confirmado | Confirmou em discovery que é quem decide e quem paga | +20 |
| Influenciador ou campeão interno | Participa da decisão, sente a dor, não decide sozinho | +12 |
| Autoridade ainda não mapeada | Discovery em andamento, papel ainda não perguntado | +5 |
| Confirmado sem poder de decisão | Perguntado e confirmado que não decide nem influencia | 0 |

**Regra de agregação por conta (obrigatória em B2B com comitê):** o critério é preenchido por pessoa, mas o Score Total é por conta ou por negócio, não por contato isolado. Quando mais de um contato da mesma conta estiver mapeado ao mesmo tempo (comum em comitê de 2-3 pessoas), use o **maior valor entre os contatos mapeados**, nunca a soma nem a média. Somar infla artificialmente (mais gente engajada não significa mais fácil de fechar), e média penaliza uma conta que já mapeou o decisor só por também ter um contato júnior na conversa. Documente no output qual contato gerou o valor usado, pra não virar caixa preta.

Não confunda "ainda não mapeei" com "não tem autoridade": no início do discovery é normal falar primeiro com quem sente a dor antes de identificar o decisor, e esse contato costuma ser o campeão interno mais valioso do processo. Zerar esse sinal cedo demais penaliza justamente quem está dando o mapa do problema.

**Critério 6: Sinal de necessidade explícita** (complementar, entra na Fase 4)

Cuidado de calibração aqui: necessidade explícita é o lead articulando o próprio problema e a intenção de resolver ("preciso resolver isso até o trimestre"), não só um gesto de comportamento de compra como perguntar preço. Perguntar preço sozinho pode vir de curiosidade ou comparação de mercado, sem nenhum problema real por trás.

| Nível | Sinal dado pelo lead | Pontos |
|---|---|---|
| Necessidade explícita articulada | Lead nomeou o próprio problema e disse com as palavras dele que quer resolver, foi além de perguntar preço | +20 |
| Sinal comportamental de compra | Perguntou preço, pediu proposta, perguntou sobre parcelamento, sem articular o problema por trás | +10 |
| Necessidade implícita | Perguntou sobre funcionamento, prazo, detalhe de execução, sem sinal de decisão | +5 |
| Curiosidade | Só pediu material educativo, sem pergunta sobre compra | 0 |

**Critério 7: Tamanho e reconhecimento do gap** (complementar, entra na Fase 4)

Nenhum critério acima mede a dor diretamente, só o entorno dela (comportamento, origem, histórico, papel). Este critério fecha essa lacuna, na lógica do Gap Selling: o que mais prediz fechamento é o tamanho do problema e a clareza com que o lead reconhece ele.

| Nível | Sinal | Pontos |
|---|---|---|
| Gap dimensionado | Lead articulou o problema e há impacto quantificado (custo, receita perdida, tempo, risco) | +25 |
| Gap reconhecido | Lead nomeia o problema com clareza, mas ainda sem número | +15 |
| Sintoma vago | Lead sente incômodo mas não sabe nomear a causa | +5 |
| Sem gap declarado | Nenhum problema articulado, só interesse no produto | 0 |

**Ajuste por modelo de negócio:** em B2B com comitê de compra, o Critério 5 (autoridade) pesa mais e deve ser preenchido por pessoa, não por conta, já que uma conta pode ter vários contatos com papéis diferentes. Em B2C de decisão individual e rápida, o Critério 5 quase sempre é 100% do lead (ele decide sozinho), então pode ser fixado em +20 por padrão, sem precisar perguntar. Em B2C com decisão em dupla (ex.: casal comprando imóvel ou carro juntos), trate como caso intermediário: não fixe +20 automático, confirme se os dois lados estão alinhados, e use o nível "influenciador ou campeão interno" quando só uma pessoa do casal está engajada e a outra ainda não participou da conversa. Em venda de ticket alto e ciclo longo, os Critérios 1 e 2 (engajamento e resposta) predizem menos do que em venda simples, porque quem responde mais rápido costuma ser o contato mais júnior, sem autoridade nenhuma. Nesse perfil, reduza o teto dos Critérios 1 e 2 pra +8 cada, e deixe autoridade (Critério 5) e gap (Critério 7) como os pesos dominantes. Em venda transacional de ciclo curto, mantenha os pesos originais de +15.

## Passo 2: Rollout gradual, não tudo de uma vez

Ninguém configura os 6 critérios na primeira semana, principalmente quem está começando agora. Siga esta ordem:

1. **Fase 1:** só Critério 2 (nível de resposta). É o mais fácil de configurar, a maioria das ferramentas já registra o timestamp de mensagem sozinha, e gera resultado visível rápido. **Aviso importante:** nesta fase o score mede facilidade de contato, não probabilidade de fechamento. Deixe isso explícito pro time desde o início, um lead "Quente" na Fase 1 significa "responde rápido", não "está pronto pra fechar".
2. **Fase 2:** depois que a Fase 1 estiver rodando estável por pelo menos uma semana, adiciona Critério 3 (origem do lead). Também costuma já existir pronto via UTM ou campo de origem.
3. **Fase 3:** entram juntos Critério 1 (engajamento) e Critério 4 (histórico de compra), porque os dois dependem de mais eventos configurados na automação.
4. **Fase 4 em diante:** Critério 5 (autoridade), Critério 6 (necessidade explícita) e Critério 7 (gap) entram por último, porque exigem preenchimento manual do vendedor durante a conversa. É só a partir desta fase que o score passa a prever fechamento de verdade, não só engajamento.

## Passo 3: Calibração (teste dos dois vendedores)

Depois de qualquer critério entrar em produção, rode o mesmo teste da Aula 1: pegue 10-15 leads reais, tenha duas pessoas diferentes avaliando os mesmos critérios de forma manual, e compare com o que o score automático gerou. Se duas pessoas discordam se o score de um lead específico faz sentido, o peso daquele critério está errado, ajuste o número, não a lógica.

## Passo 4: Score total e temperatura

Soma os pontos de todos os critérios já ativos (conforme a fase de rollout) num campo "Score Total", e aplica uma tag de temperatura automaticamente: 80 ou mais pontos vira Quente, 40 a 79 vira Morno, abaixo de 40 vira Frio. Esses números são ponto de partida, recalibre depois de um mês de dado real seguindo o Passo 3. O corte de 80 foi pensado pra fazer sentido só a partir da Fase 4 (quando autoridade, necessidade explícita e gap já estão ativos); nas Fases 1 a 3, um "Quente" é só um contato fácil de engajar, releia o aviso da Fase 1 no Passo 2 antes de tratar isso como lead pronto pra fechar.

## Exemplo real de execução

Rodada de teste numa imobiliária fictícia (Vólta Imóveis, ticket alto de R$450.000, ciclo de 60 a 120 dias, decisão do casal comprador): os Critérios 1 e 2 tiveram o teto reduzido de +15 pra +8 porque quem respondia mais rápido era sistematicamente o cônjuge menos engajado na decisão, não o casal como um todo. O Critério 4 (histórico de compra) foi marcado "não aplicável a este modelo", já que imóvel é produto único, sem escada de ofertas, e o peso dele foi redistribuído pro Critério 7 (gap). O negócio começou na Fase 1 com o Critério 3 represado, herdando o achado de origem não confiável da Skill 1, então nenhum lead chegou a "Quente" ainda, o que é esperado nessa fase, não um erro.

## Passo 5: Implementação técnica, aos poucos e amarrada à ferramenta real

Tabela de pontos sem lugar pra rodar é teoria. Não termine esta skill sem responder, de forma concreta, ONDE e COMO cada critério vai ser calculado de verdade. Duas partes obrigatórias:

### 5.1: Implementação imediata, na ferramenta que o aluno já tem hoje

Puxe da Skill 1 qual é a ferramenta real (planilha, CRM com login, ou CRM com API) e gere passo a passo concreto pra essa ferramenta específica, não instrução genérica:

- **Se for planilha:** especifique as colunas novas a criar (uma por critério de pontos, mais colunas de apoio pra registrar o nível de cada critério manual), a fórmula real de cada uma (`SE`/`IF` ou `SES`/`IFS` encadeado, não pseudocódigo), a fórmula do Score Total somando só os critérios já ativos na fase corrente, e como aplicar a régua de temperatura com formatação condicional. Amarre a ordem de criação das colunas à ordem de fases do Passo 2: não crie a coluna de um critério antes da fase dele chegar.
- **Se for CRM com login, sem API (ou API que o aluno ainda não vai configurar):** especifique os campos customizados a criar direto no painel (nome, tipo do campo, que precisa ser numérico pra somar), e como simular a régua de temperatura com um campo de texto ou tag, já que sem automação nativa o cálculo do Score Total é manual, o vendedor soma e digita.
- **Se for CRM com API já configurada na Skill 1:** especifique como os campos de pontuação viram Custom Properties/Custom Fields via API, e como uma automação nativa da ferramenta (ou um script simples lendo a API) recalcula o Score Total sozinho a cada mudança de critério, sem depender do vendedor somar na mão.

Gere isso semana a semana, amarrado às fases do Passo 2 (ex.: "Semana 1: crie a coluna do Critério 2 com esta fórmula, meta de saída é todas as linhas ativas calculadas sem erro"), não um bloco só de "configure tudo".

### 5.2: Decisão de migração de ferramenta, se e quando isso vier a acontecer

Se o aluno perguntar sobre migrar de planilha (ou de um CRM sem API) pra outra ferramenta, não recomende marca nenhuma. Em vez disso, entregue o critério de decisão: 3 perguntas que valem pra qualquer CRM candidato, porque são elas que decidem se o cálculo pode ser automatizado ou não, não o nome da ferramenta.

| Pergunta | Como testar de verdade |
|---|---|
| A documentação de API existe e é pública? | Procurar `/developers`, `/api-docs` ou `/docs` no site do fornecedor sem precisar logar ou abrir chamado comercial. Se só aparece depois de falar com vendedor, trate como "não é pública" |
| O CRM suporta campo customizado numérico, visível na listagem/pipeline? | Confirmar que dá pra criar campo tipo Número (não texto, não lista), e que ele aparece fora do card individual, senão não dá pra filtrar por temperatura |
| O CRM suporta automação por mudança de campo (não só por mudança de etapa)? | Confirmar que existe seção de Automações/Workflows que dispara quando qualquer campo muda, e que ela consegue escrever de volta noutro campo do mesmo registro |

O resultado das 3 perguntas muda o plano, não é detalhe cosmético:

| Cenário | Como o Score Total é calculado |
|---|---|
| API pública + campo numérico + automação por mudança de campo | 100% automatizado: vendedor só preenche os níveis, o sistema soma e classifica sozinho |
| Campo customizado existe, mas automação só dispara por mudança de etapa | Cálculo roda fora (planilha ponte ou script lendo a API) e escreve de volta em lote, não em tempo real |
| Sem API pública, só login manual | Nada automatiza. O vendedor calcula a soma com a tabela de referência e digita o resultado, exatamente como faria na planilha, só que dentro do painel |

**Regra de sequência, sempre:** não recomende migrar de ferramenta antes do modelo já estar rodando estável na ferramenta atual por pelo menos um ciclo de calibração (Passo 3). Migrar um modelo ainda não calibrado pra uma ferramenta nova dobra a superfície de erro por nada.

## Passo 6: Entregar o output (sempre em dois formatos)

Gere **dois arquivos com o mesmo conteúdo**:

1. `lead-scoring-{negocio}.md` com: as 7 tabelas de pontos (Passo 1), quais critérios ficaram represados por causa de achado herdado da Skill 1 (ex.: origem não confiável, ver aviso no Passo 0), qual fase de rollout o negócio está usando agora (Passo 2), o protocolo de calibração (Passo 3), a régua de temperatura com os pontos de corte (Passo 4), e o plano de implementação técnica completo (Passo 5, incluindo fórmulas reais se for planilha). Feche com o handoff: *"Este modelo de pontuação alimenta a Skill 3 (/diagnostico-gargalos-funil), que usa a temperatura pra identificar onde os leads quentes estão travando no funil."*
2. `lead-scoring-{negocio}.html`: mesma informação em página autocontida, mesmos tokens visuais do padrão da Aula 1 (fundo `#0A0A0A`, ouro `#C9B298`), com as 7 tabelas renderizadas como tabelas reais, a régua de temperatura em destaque visual (cores para Quente, Morno, Frio), e o passo a passo de implementação técnica também renderizado (não só no .md).

**Abra o HTML automaticamente assim que gerar:** `open lead-scoring-{negocio}.html` (Mac), `start lead-scoring-{negocio}.html` (Windows) ou `xdg-open lead-scoring-{negocio}.html` (Linux). Se falhar, avise o caminho exato do arquivo.

**Atualize a Central de Entregas da Aula 2** (`central-de-entregas-aula2.html` na raiz do projeto do aluno):
- Se o arquivo ainda não existir na pasta do projeto, copie de `templates/central-de-entregas-aula2.html` (deste repo) para a raiz do projeto antes de editar.
- No array `ENTREGAS`, encontre a linha com `id: 2` e troque `status: "pendente", html: null, md: null` por `status: "pronto", html: "lead-scoring-{negocio}.html", md: "lead-scoring-{negocio}.md"`.

**Depois de entregar os dois arquivos, diga isto diretamente ao aluno no chat:** *"Modelo de pontuação pronto, os dois arquivos estão aí. Próximo passo: rode /diagnostico-gargalos-funil pra achar onde o funil está vazando receita."*
