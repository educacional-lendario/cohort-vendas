# Workflow da Aula 1 — Processo Comercial & Playbook com IA

Mapa mental da Aula 1 traduzido em workflow executável. As 4 skills deste repo, orquestradas em sequência.

## A grande imagem

```
VOCE
 |
 v
 Squad Vendas (orquestrado por voce, o dono do processo comercial)
 |
 +-- AULA 1: Processo Comercial & Playbook com IA   <- voce esta aqui
 |    |
 |    +-- /desenho-processo-comercial   (etapas + criterios de saida + gatilhos)
 |    +-- /qualificacao-bant-gpct       (ICP + BANT/GPCT calibrado)
 |    +-- /discovery-script             (SPIN + Funil de Dor + Gap, com IA)
 |    +-- /playbook-vendas-vivo         (objecoes classificadas + cadencia viva)
 |
 +-- AULA 2: FUPs, Cadencia e SDR        (proxima)
 +-- AULA 3: CRM e Pipeline              (Bruno)
 +-- AULA 4: Automacao e Fechamento      (Marcondes)
```

## Output da Aula 1 (o que você sai entregando)

Um pacote de 4 documentos prontos:

1. **Processo comercial** (etapas + critério de saída VCA + gatilhos de deal e de processo) — `processo-comercial-{negocio}.md`
2. **ICP + qualificação calibrada** (mix BANT/GPCT + escala de pontuação + protocolo de validação humana) — `qualificacao-{negocio}.md`
3. **Discovery script** (6 blocos modulares, criado ou refinado com call real) — `discovery-script-{negocio}.md`
4. **Playbook de objeções vivo** (biblioteca classificada em 6 tipos + battlecard + cadência de revisão) — `playbook-objecoes-{negocio}.md`

Esse pacote vira input direto da **Aula 2 (FUPs, Cadência e SDR)**: o processo define em qual etapa cada follow-up dispara, e a qualificação define o filtro de entrada do SDR.

## Ordem de execução (4 blocos de ~50 min)

### Bloco 1 — Processo Comercial

1. `/desenho-processo-comercial [seu negócio]` → a skill diagnostica ticket, ciclo, decisores e B2B/B2C
2. Desenha as etapas com critério de saída verificável (VCA), calibradas ao perfil
3. Define gatilhos de deal (nível micro) e de processo (nível macro)
4. Output: documento único com etapas, critérios e gatilhos

### Bloco 2 — ICP e Qualificação BANT/GPCT

1. `/qualificacao-bant-gpct` → puxa o perfil do Bloco 1
2. Escolhe o mix (BANT puro, blend, ou GPCT/GPCTBA) conforme ticket/ciclo/decisores
3. Monta o ICP nas dimensões certas (B2B: firmográfico/tecnográfico/comportamental; B2C: demográfico/comportamental/gatilho)
4. Gera o roteiro de perguntas + escala de pontuação + protocolo de validação humana antes de automação

### Bloco 3 — Discovery Script com IA

1. `/discovery-script` → cria do zero (6 blocos: abertura, situação, problema, implicação+gap, pessoal, fechamento) ou refina com calls reais
2. Se houver gravação/transcrição, a skill compara cobertura de blocos, presença de quantificação de gap e proporção de fala do comprador
3. Output: script completo + (se aplicável) recomendações específicas por bloco

### Bloco 4 — Playbook de Vendas Vivo

1. `/playbook-vendas-vivo` → classifica cada objeção em 1 dos 6 tipos
2. Gera resposta com o framework certo (D.E.E.P., Empatia Tática, Feel-Felt-Found, reformulação de valor)
3. Monta biblioteca pesquisável + battlecard de 1 página
4. Define cadência de revisão (trimestral mínima, mais rápida sob gatilho) com dono nomeado

## Conexão entre as skills

```
/desenho-processo-comercial
    \
     v output: processo-comercial-{negocio}.md (critério de saída da etapa Qualificação)
/qualificacao-bant-gpct -- roteiro (blocos Goals/Challenges) ----> /discovery-script
    \                                                                    \
     v output: qualificacao-{negocio}.md                                 v output: discovery-script-{negocio}.md
                                                                     (objeções levantadas no discovery)
                                                                          \
                                                                           v
                                                                     /playbook-vendas-vivo
                                                                          \
                                                                           v output: playbook-objecoes-{negocio}.md
                                                                          --> Aula 2 (FUPs, Cadência, SDR)
```

## Reaproveitamento do squad interno de vendas

As 4 skills desta aula não reinventam frameworks de venda do zero — elas traduzem o squad `squads/sales/` (14 agentes, 4 tiers) para o contexto de qualificação com vocabulário BANT/GPCT, que é o que o mercado usa. Quando o Claude Code tiver acesso a esse squad, é possível aprofundar cada bloco:

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
- Qualificação consistente (BANT/GPCT calibrado, nunca aplicado igual pra tudo)
- Discovery que revela dor de verdade, não sintoma superficial
- Playbook de objeções que se mantém vivo, não decai em 3 meses

**O que a aula NÃO faz:**
- Não monta cadência de follow-up ou prospecção outbound (isso é Aula 2)
- Não configura CRM ou integra ferramentas (isso é Aula 3)
- Não automatiza fechamento com IA sem a camada de validação humana primeiro (isso é Aula 4 — e mesmo lá, o protocolo de validação desta aula continua valendo)

## Ferramentas necessárias

- **Claude Code** com as 4 skills instaladas (este repo)
- Nenhuma chave de API é obrigatória para esta aula — as skills são geração e refino assistidos por IA em cima do que o aluno já sabe do próprio negócio ou de gravações/transcrições que ele fornecer
