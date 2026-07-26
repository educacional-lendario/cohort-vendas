# Workflow da Aula 1 — Processo Comercial & Playbook com IA

Mapa mental da Aula 1 traduzido em workflow executável. As 6 skills deste repo, orquestradas em sequência (5 no fluxo principal, 1 bônus).

## A grande imagem

```
VOCE
 |
 v
 Squad Vendas (orquestrado por voce, o dono do processo comercial)
 |
 +-- AULA 1: Processo Comercial & Playbook com IA   <- voce esta aqui
 |    |
 |    +-- /desenho-processo-comercial     (etapas + criterios de saida + gatilhos)
 |    +-- /regua-comunicacao-comercial    (quem fala, o que fala, por qual canal + mecanismo unico)
 |    +-- /qualificacao-bant-gpct         (ICP + BANT/GPCT calibrado)
 |    +-- /discovery-script               (SPIN + Funil de Dor + Gap, com IA)
 |    +-- /playbook-vendas-vivo           (objecoes classificadas + cadencia viva, multi-canal)
 |    +-- /escada-de-ofertas (bonus)      (jornada entre produtos — funil de vendas, nao comercial)
 |
 +-- AULA 2: CRM, Integracoes e Pipeline  (Bruno — proxima)
 +-- AULA 3: FUPs, Cadencia e SDR         (Adavio)
 +-- AULA 4: Automacao e Fechamento       (Marcondes)
```

## Dois funis, dois níveis — não confundir

**Funil comercial** (`/desenho-processo-comercial`) acompanha o status de **um deal específico**: em que etapa do pipeline aquele lead está agora. **Escada de ofertas** (`/escada-de-ofertas`, bônus) mapeia **o portfólio inteiro**: como um cliente sobe de um produto para outro ao longo do tempo, possivelmente abrindo um novo deal no funil comercial a cada subida de degrau. São documentos diferentes, resolvendo problemas diferentes — um negócio de produto único usa só o primeiro; um negócio com portfólio usa os dois.

## Output da Aula 1 (o que você sai entregando)

Um pacote de 5 documentos prontos (6 se o negócio tiver mais de uma oferta), cada um em **markdown + HTML**:

1. **Processo comercial** (etapas + critério de saída VCA + gatilhos de deal e de processo) — `processo-comercial-{negocio}.md` + `.html`
2. **Régua de comunicação** (quem fala, o que fala, por canal, funil de reforço por tempo parado, mecanismo único de conversão) — `regua-comunicacao-{negocio}.md` + `.html`
3. **ICP + qualificação calibrada** (mix BANT/GPCT + escala de pontuação + protocolo de validação humana) — `qualificacao-{negocio}.md` + `.html`
4. **Discovery script** (6 blocos modulares, criado ou refinado com call real) — `discovery-script-{negocio}.md` + `.html`
5. **Playbook de objeções vivo** (biblioteca classificada em 6 tipos, multi-canal, + battlecard + cadência de revisão) — `playbook-objecoes-{negocio}.md` + `.html`
6. **Escada de ofertas** (bônus, se aplicável) — `escada-de-ofertas-{negocio}.md` + `.html`

Esse pacote vira input direto da **Aula 2 (CRM, Integrações e Gestão de Pipeline)**: as etapas viram os estágios configurados no CRM, e a régua de comunicação vira a especificação das automações/templates de mensagem.

## Ordem de execução (5 blocos principais de ~50 min + 1 bônus)

### Bloco 1 — Processo Comercial

1. `/desenho-processo-comercial [seu negócio]` → a skill diagnostica ticket, ciclo, decisores e B2B/B2C
2. Desenha as etapas com critério de saída verificável (VCA), calibradas ao perfil
3. Define gatilhos de deal (nível micro) e de processo (nível macro)
4. Output: `processo-comercial-{negocio}.md` + `.html`

### Bloco 2 — Régua de Comunicação por Etapa

1. `/regua-comunicacao-comercial` → puxa as etapas do Bloco 1
2. Define quem atua (humano/IA/ambos) e o canal certo por etapa
3. Constrói o funil de reforço por tempo parado, variando o texto a cada toque
4. Ajuda a nomear o mecanismo único de conversão do negócio
5. Output: `regua-comunicacao-{negocio}.md` + `.html`

### Bloco 3 — ICP e Qualificação BANT/GPCT

1. `/qualificacao-bant-gpct` → puxa o perfil do Bloco 1 e a régua do Bloco 2
2. Escolhe o mix (BANT puro, blend, ou GPCT/GPCTBA) conforme ticket/ciclo/decisores
3. Monta o ICP nas dimensões certas (B2B: firmográfico/tecnográfico/comportamental; B2C: demográfico/comportamental/gatilho)
4. Gera o roteiro de perguntas + escala de pontuação + protocolo de validação humana antes de automação
5. Output: `qualificacao-{negocio}.md` + `.html`

### Bloco 4 — Discovery Script com IA

1. `/discovery-script` → cria do zero (6 blocos: abertura, situação, problema, implicação+gap, pessoal, fechamento) ou refina com calls reais
2. Se houver gravação/transcrição, a skill compara cobertura de blocos, presença de quantificação de gap e proporção de fala do comprador
3. Output: `discovery-script-{negocio}.md` + `.html`

### Bloco 5 — Playbook de Vendas Vivo

1. `/playbook-vendas-vivo` → classifica cada objeção em 1 dos 6 tipos
2. Gera resposta com o framework certo (D.E.E.P., Empatia Tática, Feel-Felt-Found, reformulação de valor), adaptada para call, WhatsApp/DM e e-mail — sempre com a mesma voz do mecanismo único definido no Bloco 2
3. Monta biblioteca pesquisável + battlecard de 1 página
4. Define cadência de revisão (trimestral mínima, mais rápida sob gatilho) com dono nomeado
5. Output: `playbook-objecoes-{negocio}.md` + `.html`

### Bônus — Escada de Ofertas

1. `/escada-de-ofertas` → só roda se o negócio já tem mais de um produto/oferta
2. Mapeia os degraus, o critério de qualificação por degrau e o discurso de ascensão
3. Output: `escada-de-ofertas-{negocio}.md` + `.html`

## Conexão entre as skills

```
/desenho-processo-comercial
    \
     v output: processo-comercial-{negocio}.md (etapas + criterio de saida da Qualificacao)
/regua-comunicacao-comercial -- quem fala/canal/mecanismo unico -->
    \
     v output: regua-comunicacao-{negocio}.md
/qualificacao-bant-gpct -- roteiro (blocos Goals/Challenges) ----> /discovery-script
    \                                                                    \
     v output: qualificacao-{negocio}.md                                 v output: discovery-script-{negocio}.md
                                                                     (objecoes levantadas no discovery)
                                                                          \
                                                                           v
                                                                     /playbook-vendas-vivo
                                                                          \
                                                                           v output: playbook-objecoes-{negocio}.md
                                                                          --> Aula 2 (CRM, Integracoes e Pipeline)

/escada-de-ofertas (bonus, paralelo — opera no nivel do portfolio, nao do deal)
```

## Reaproveitamento do squad interno de vendas

As 6 skills desta aula não reinventam frameworks de venda do zero — elas traduzem o squad `squads/sales/` (14 agentes, 4 tiers) para o contexto de qualificação com vocabulário BANT/GPCT e régua de comunicação, que é o que o mercado usa. Quando o Claude Code tiver acesso a esse squad, é possível aprofundar cada bloco:

- **Desenho de processo** → `@sales-chief *diagnose` (6 dimensões + detecção automática de nicho)
- **Discovery** → `/sales:neil-rackham *spin-discovery` (SPIN Selling completo)
- **Quantificação de dor** → `/sales:keenan *gap-analysis` (Gap Selling: estado atual vs desejado)
- **Aprofundamento de dor e budget/decisão** → `/sales:david-sandler *pain-funnel`
- **Negociação e objeções de risco/confiança** → `/sales:chris-voss *negotiate`
- **Fechamento** → `/sales:david-sandler *sandler-close`

Fluxo consultivo completo de referência (do squad): `@sales-chief *diagnose` → `neil-rackham *spin-discovery` → `keenan *gap-analysis` → `david-sandler *pain-funnel` → `chris-voss *negotiate` → `david-sandler *sandler-close`.

## Regras da Aula 1

**O que a aula resolve:**
- Desenho de processo comercial ponta a ponta, calibrado por tipo de venda
- Régua de comunicação por etapa, com mecanismo único de conversão nomeado
- Qualificação consistente (BANT/GPCT calibrado, nunca aplicado igual pra tudo)
- Discovery que revela dor de verdade, não sintoma superficial
- Playbook de objeções multi-canal que se mantém vivo, não decai em 3 meses
- (Bônus) Escada de ofertas, para quem já tem mais de um produto

**O que a aula NÃO faz:**
- Não configura CRM ou integra ferramentas (isso é Aula 2)
- Não monta cadência de prospecção outbound fria (isso é Aula 3)
- Não automatiza fechamento com IA sem a camada de validação humana primeiro (isso é Aula 4 — e mesmo lá, o protocolo de validação desta aula continua valendo)

## Ferramentas necessárias

- **Claude Code** com as 6 skills instaladas (fonte canônica: `.claude/skills/`) — opção recomendada, zero setup além do clone
- **Codex CLI** também funciona: lê `AGENTS.md` na raiz e as skills espelhadas em `.agents/skills/`
- Sem nenhuma das duas ferramentas: cada `SKILL.md` funciona como prompt colável em qualquer IA de chat (ver `AGENTS.md`, seção final)
- Nenhuma chave de API é obrigatória para esta aula — as skills são geração e refino assistidos por IA em cima do que o aluno já sabe do próprio negócio ou de gravações/transcrições que ele fornecer
