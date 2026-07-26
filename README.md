# Cohort de Vendas — Aula 1

> **Academia Lendária · Squad Vendas**
>
> Processo Comercial & Playbook com IA

Bem-vindo ao repositório da **Aula 1** do Cohort de Vendas. Este repo contém tudo o que você precisa para desenhar o processo comercial ponta a ponta, calibrar a qualificação de leads e construir um playbook de objeções vivo — com o Claude Code orquestrando a construção. Funciona para qualquer nicho, B2B ou B2C.

---

## Comece por aqui

**Antes de qualquer coisa, abra o guia visual no navegador:**

👉 **[`GUIA-DO-ALUNO.html`](./GUIA-DO-ALUNO.html)** — clica e abre. Tem tudo o que você precisa saber para começar (5 minutos de leitura).

Se preferir markdown puro, o conteúdo está abaixo.

---

## O que você ganha na Aula 1

4 skills para o Claude Code que constroem, em sequência, o esqueleto comercial do seu negócio:

| Skill | O que faz | Output |
|---|---|---|
| `/desenho-processo-comercial` | Diagnostica seu modelo de venda (ticket, ciclo, decisores, B2B/B2C) e desenha as etapas do funil com critério de saída verificável (VCA) e gatilhos de risco em 2 níveis | Processo comercial completo com etapas, critérios de avanço e gatilhos |
| `/qualificacao-bant-gpct` | Escolhe o mix certo entre BANT e GPCT para o seu tipo de venda, monta o ICP nas dimensões certas (B2B ou B2C) e gera o roteiro de qualificação com escala de pontuação consistente | ICP + roteiro de qualificação + protocolo de validação humana antes de automação |
| `/discovery-script` | Gera o script de discovery em 6 blocos modulares (SPIN + Funil de Dor + quantificação de gap), ou refina um script existente comparando com calls reais gravadas/transcritas | Discovery script completo, criado ou refinado com dado real |
| `/playbook-vendas-vivo` | Classifica objeções em 6 tipos, gera resposta com o framework certo por tipo (D.E.E.P., Empatia Tática, Feel-Felt-Found) e define a cadência que mantém o playbook vivo | Biblioteca de objeções pesquisável + battlecard de 1 página |

**Tese-mãe da Aula 1:** desenhar o processo, calibrar a qualificação e construir o playbook — para o aluno sair com o problema comercial resolvido, não com mais um framework na cabeça.

---

## Setup em 5 minutos

### Pré-requisitos

- **Claude Code** instalado ([download](https://docs.claude.com/claude-code))
- **Git** instalado

### Passo a passo

**1. Clone este repo**

```bash
git clone https://github.com/marketingLendario/cohort-vendas.git
cd cohort-vendas
```

**2. Abra o Claude Code no diretório**

```bash
claude
```

As 4 skills em `.claude/skills/` são carregadas automaticamente. Funciona também no Codex.

**3. Teste que as skills estão instaladas**

No Claude Code, digite:

```
/desenho-processo-comercial
```

Se aparecer o menu da skill, está funcionando.

---

## Fluxo da aula (4 blocos, ~50 min cada)

### Bloco 1 — Processo Comercial com `/desenho-processo-comercial`

```
/desenho-processo-comercial [seu negócio]
```

Diagnostica ticket, ciclo, número de decisores e B2B/B2C, depois desenha as etapas do funil com critério de saída verificável (ação do cliente, nunca atividade do vendedor) e os gatilhos de risco em dois níveis: deal travado e processo desatualizado.

### Bloco 2 — ICP e Qualificação com `/qualificacao-bant-gpct`

```
/qualificacao-bant-gpct
```

Puxa o perfil do Bloco 1 e decide o mix certo entre BANT e GPCT — nunca aplicando o mesmo checklist para todo tipo de venda. Monta o ICP e gera o roteiro de qualificação com escala de pontuação objetiva.

### Bloco 3 — Discovery Script com `/discovery-script`

```
/discovery-script
```

Gera o script em 6 blocos (abertura, situação, problema, implicação + gap, pessoal, fechamento parcial) ou refina um script existente comparando com calls reais — a IA aponta o que o roteiro previa versus o que aconteceu de fato.

### Bloco 4 — Playbook de Vendas Vivo com `/playbook-vendas-vivo`

```
/playbook-vendas-vivo
```

Classifica cada objeção em um dos 6 tipos (preço, urgência, confiança, concorrente, autoridade, desalinhamento interno), gera a resposta com o framework certo, e define a cadência de revisão que mantém o playbook vivo.

**Output final:** pacote comercial completo — processo, qualificação, discovery e playbook — pronto para rodar e para alimentar a Aula 2 (FUPs, Cadência e SDR).

---

## Estrutura do repo

```
.
├── README.md                       este arquivo
├── GUIA-DO-ALUNO.html              guia visual interativo (leia primeiro)
├── .env.example                    template de variáveis (opcional para esta aula)
├── .claude/
│   └── skills/                     as 4 skills (Claude Code carrega automático)
│       ├── desenho-processo-comercial/
│       ├── qualificacao-bant-gpct/
│       ├── discovery-script/
│       └── playbook-vendas-vivo/
├── templates/                      templates em branco dos 4 outputs
├── exemplos/                       exemplos preenchidos
└── docs/
    ├── workflow.md                 fluxo completo da Aula 1
    └── SKILLS-INDEX.md             mapa de nomes (aliases → canônico) para suporte
```

---

## Onde você está no cohort

```
VOCÊ
 |
 v
 Squad Vendas
 |
 +-- AULA 1: Processo Comercial & Playbook com IA   <- você está aqui
 +-- AULA 2: FUPs, Cadência e SDR                    próxima
 +-- AULA 3: CRM, Integrações e Gestão de Pipeline   depois
 +-- AULA 4: Automação e Fechamento com IA           final
```

---

## Regras de ouro

### Critério de saída é ação do cliente, nunca do vendedor

"Enviei a proposta" não é critério de avanço de etapa. "O comprador econômico revisou e deu sinal verbal de preferência" é. Rode o teste dos dois vendedores: se dois vendedores diferentes chegassem a conclusões diferentes sobre o mesmo deal, o critério está fraco.

### Framework é guia de conversa, nunca checklist mecânico

BANT e GPCT existem para orientar a conversa, não para engessar. Se a pergunta soa interrogatório, o framework virou muleta.

### Sem número não é dor, é sentimento

Quantifique o gap entre estado atual e estado desejado nas próprias palavras do cliente. "É chato" não justifica preço; "custa R$40 mil por mês" justifica.

### Objeção é diagnóstico, não obstáculo

Classifique o tipo (preço, urgência, confiança, concorrente, autoridade, desalinhamento interno) antes de responder. Responder "preço" quando a objeção real é "confiança" nunca fecha o deal.

### Nenhuma automação de IA entra sem validação humana primeiro

Rode manual em 10-15 casos reais, audite a consistência entre pessoas diferentes pontuando o mesmo caso, só depois escale com IA — e continue revisando por amostragem, não só na largada. Consistência de resultado vem de régua auditada, não de IA sozinha.

---

## Suporte

- **Dúvidas técnicas:** abra issue neste repo
- **Dúvidas de conteúdo:** canal do cohort
- **Bug ou melhoria:** PR direto neste repo

---

## Próxima aula

**Aula 2 — FUPs, Cadência e SDR:** prospecção outbound, follow-ups e qualificação de entrada, construindo em cima do processo e da qualificação desenhados aqui.

---

**Construído com:** Academia Lendária + Claude Code
