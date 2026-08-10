# 🎯 Squad Sales v2.0 — Elite Sales Methodology + Customer Success

> **Nove mentes lendárias da venda + cinco arquitetos de pós-venda, operando como um time de IA.** Do primeiro contato à expansão da conta — sem mimimi, sem ruído, sem desculpa.

[![Version](https://img.shields.io/badge/version-2.0.0-gold)](./CHANGELOG.md)
[![Agents](https://img.shields.io/badge/agents-14-blue)](./agents)
[![Tasks](https://img.shields.io/badge/tasks-19-green)](./tasks)
[![Funil](https://img.shields.io/badge/funil-completo-purple)](#)

---

## 🚀 Quick Start

```bash
@sales-chief
```

O orquestrador diagnostica a situação em 6 dimensões e direciona para o especialista certo. Mande `*help` para ver todos os comandos.

**Tudo começa por aqui:** `@sales-chief *diagnose`

---

## 📋 O que mudou na v2.0

A v2.0 integra o **customer-success squad** do [AIOX-enterprise](https://github.com/AIOXsquad/AIOX-enterprise) e adota o padrão **wrapper enterprise**.

| | v1.0.0 | **v2.0.0** | Δ |
|---|---|---|---|
| Agentes | 9 | **14** | +5 |
| Tasks | 9 | **19** | +10 |
| Workflows | 0 | **3** | +3 |
| Templates | 0 | **2** | +2 |
| Checklists | 2 | **4** | +2 |
| Tiers | 3 | **4** | +1 (Pós-Venda) |
| Slash commands | 0 | **14** | +14 (`/sales:*`) |

📖 Detalhes completos em [`ANTES-DEPOIS.md`](./ANTES-DEPOIS.md)

---

## 🎭 Os 14 Agentes do Squad

### 🏛️ Orchestrator
| Agente | Quando usar |
|---|---|
| **sales-chief** | Sempre o primeiro contato. Diagnostica e roteia. |

### 🔬 Tier 0 — Diagnóstico
| Agente | Especialidade | Framework |
|---|---|---|
| **neil-rackham** | Descoberta consultiva | SPIN Selling |

### ⚔️ Tier 1 — Masters (Execução principal)
| Agente | Especialidade | Framework |
|---|---|---|
| **david-sandler** | Controle do processo de venda | Sandler Submarine System |
| **keenan** | Venda centrada em problema | Gap Selling |
| **chris-voss** | Negociação tática | Never Split the Difference |

### 📐 Tier 2 — Systematizers (Frameworks ensináveis)
| Agente | Especialidade | Framework |
|---|---|---|
| **challenger-sale** | Ensino e reframe | Teach-Tailor-Take Control |
| **jeb-blount** | Prospecting fanático | Fanatical Prospecting + Sales EQ |
| **chet-holmes** | Máquina de vendas | Ultimate Sales Machine + Dream 100 |

### 🚂 Tier 3 — Specialists (Escala)
| Agente | Especialidade | Framework |
|---|---|---|
| **aaron-ross** | Outbound engine | Predictable Revenue + Cold Calling 2.0 |

### 💚 Tier 4 — Pós-Venda (NOVO na v2.0)
| Agente | Especialidade | Framework |
|---|---|---|
| **cs-chief** | Coordenação CS | Customer Success Frameworks |
| **onboarding-architect** | Onboarding & ativação | Time-to-Value, Activation Points |
| **health-monitor** | Health Score & churn | Predictive Churn EWS |
| **journey-mapper** | Jornada do cliente | Journey Mapping, Touchpoints |
| **expansion-strategist** | Upsell & retenção | NRR, Expansion Playbook |

---

## ⚡ Comandos do Orchestrator (`sales-chief`)

### Pré-Venda
| Comando | O que faz |
|---|---|
| `*diagnose` | Diagnóstico completo em 6 dimensões + detecção de nicho |
| `*prospect` | Roteia para prospecting (Jeb Blount / Aaron Ross) |
| `*qualify` | Roteia para qualificação (Neil Rackham / Keenan / Sandler) |
| `*negotiate` | Roteia para negociação (Chris Voss) |
| `*close` | Roteia para fechamento (David Sandler) |
| `*scale` | Roteia para escala (Aaron Ross / Chet Holmes) |
| `*followup` | Cria sequências de follow-up para qualquer estágio |
| `*email-sequence` | Cria sequências de email (nurture, launch, cart, onboarding) |
| `*sales-copy` | Cria copy de vendas (sales page, VSL, webinar, proposta) |
| `*scripts` | Cria scripts (discovery call, demo, closing, objeções, DMs) |

### Pós-Venda (NOVO v2.0)
| Comando | O que faz |
|---|---|
| `*onboard` | Design completo de onboarding (onboarding-architect) |
| `*retain` | Diagnóstico de risco de churn (health-monitor) |
| `*expand` | Plano de expansão de conta (expansion-strategist) |
| `*journey` | Mapeamento da jornada do cliente (journey-mapper) |
| `*cs-health` | Health Score completo + EWS (cs-chief) |

### Sistema
| Comando | O que faz |
|---|---|
| `*help` | Lista todos os comandos |
| `*exit` | Sai do modo Sales Squad |

---

## 🗺️ Fluxos Prontos

### Fluxo 1: Fechando um deal consultivo
```
1. @sales-chief *diagnose            → Diagnóstico inicial
2. /sales:neil-rackham *spin-discovery → Discovery profunda
3. /sales:keenan *gap-analysis        → Quantifica o gap
4. /sales:david-sandler *pain-funnel  → Aprofunda a dor
5. /sales:chris-voss *negotiate       → Negocia termos
6. /sales:david-sandler *sandler-close → Fecha o deal
```

### Fluxo 2: Montando operação de prospecting
```
1. /sales:aaron-ross *outbound-engine → Estrutura operação
2. /sales:jeb-blount *prospect-plan   → Plano de prospecting
3. /sales:chet-holmes *dream-100      → Seleciona Dream 100
```

### Fluxo 3: Funil completo pré + pós-venda (NOVO v2.0)
```
1. @sales-chief *diagnose                       → Diagnóstico
2. /sales:neil-rackham *spin-discovery          → Discovery
3. /sales:david-sandler *sandler-close          → Fechar deal
4. /sales:onboarding-architect *onboarding-design → Onboarding
5. /sales:health-monitor *health-score          → Monitoramento
6. /sales:journey-mapper *journey-map           → Mapear evolução
7. /sales:expansion-strategist *expansion-plan  → Upsell estratégico
```

### Fluxo 4: Prevenção de churn (NOVO v2.0)
```
1. /sales:health-monitor *churn-ews             → Detecta sinais
2. /sales:journey-mapper *friction-audit        → Identifica fricções
3. /sales:cs-chief *cs-route                    → Roteia para playbook
4. /sales:expansion-strategist *retention-plan  → Plano de retenção
```

---

## 🎯 Os 7 Nichos Cobertos

O squad detecta automaticamente o nicho (**Dimensão 0** do diagnóstico) e adapta o playbook. SPIN não funciona pra ebook de R$97. Challenger não funciona sem buyer committee. **O método se adapta — ou não funciona.**

| Nicho | Ticket | Recomendado |
|---|---|---|
| Infoproduto Low-Ticket | R$47–997 | aaron-ross, jeb-blount + sales-page/VSL |
| Infoproduto High-Ticket | R$2k–30k | neil-rackham, sandler, chris-voss |
| SaaS SMB | R$200–2k/mês | challenger-sale, gap-selling, demos |
| SaaS Enterprise | R$10k+/mês | challenger-sale, sandler, buyer committee |
| Serviços/Consultoria | R$5k–500k | sandler, neil-rackham, chris-voss |
| E-commerce DTC | B2C volume | copy + email sequences + aaron-ross |
| Custom Niche | personalizado | Classificação adaptativa (3 perguntas) |

---

## 📁 Estrutura do Squad

```
squads/sales/
├── agents/                   # 14 agentes
│   ├── sales-chief.md
│   ├── neil-rackham.md
│   ├── david-sandler.md
│   ├── keenan.md
│   ├── chris-voss.md
│   ├── challenger-sale.md
│   ├── jeb-blount.md
│   ├── chet-holmes.md
│   ├── aaron-ross.md
│   ├── cs-chief.md           # NOVO v2.0
│   ├── onboarding-architect.md  # NOVO v2.0
│   ├── health-monitor.md     # NOVO v2.0
│   ├── journey-mapper.md     # NOVO v2.0
│   └── expansion-strategist.md  # NOVO v2.0
├── tasks/                    # 19 tasks
├── workflows/                # 3 workflows (NOVO v2.0)
│   ├── churn-prevention.yaml
│   ├── cs-setup.yaml
│   └── onboarding-design.yaml
├── templates/                # 2 templates (NOVO v2.0)
│   ├── cs-report-tmpl.yaml
│   └── expansion-playbook-tmpl.yaml
├── checklists/               # 4 checklists
├── config.yaml               # v2.0.0
├── ARCHITECTURE.md           # Arquitetura e data flow
├── CHANGELOG.md              # Histórico de versões
├── ANTES-DEPOIS.md           # Comparativo v1.0 → v2.0
└── README.md                 # Este arquivo
```

---

## 🚦 Integração com Claude Code

### Opção A: Slash Commands (mais rápido)
```
/sales:sales-chief             → Ativa o orchestrator
/sales:neil-rackham            → Direto para SPIN Selling
/sales:cs-chief                → Direto para CS
```

### Opção B: @ Agent (estilo wrapper enterprise)
```
@sales--sales-chief            → Ativa via wrapper
@sales--cs-chief               → Ativa CS via wrapper
```

### Opção C: Agent Tool (programático)
```
Use the Agent tool with subagent_type="sales--sales-chief"
```

---

## 💡 Exemplos de Uso por Cenário

### "Acabei de gerar um lead high-ticket"
```
@sales-chief *diagnose
→ Identifica nicho + dor + urgência
→ Roteia automaticamente
```

### "Tenho 50 leads frios"
```
/sales:aaron-ross *cold-email-sequence
→ Gera sequência de 7 emails personalizados
```

### "Cliente entrando em renovação"
```
/sales:health-monitor *health-score
/sales:expansion-strategist *expansion-plan
→ Avalia risco + plano de upsell
```

### "Time perdendo deals na proposta"
```
/sales:chet-holmes *sales-machine-audit
→ Auditoria das 12 estratégias da Sales Machine
```

### "Não sei por onde começar"
```
@sales-chief *diagnose
→ O squad faz as perguntas certas
```

---

## 📊 Stats da v2.0

| Métrica | Valor |
|---|---|
| Agentes ativos | **14** |
| Tasks executáveis | **19** |
| Workflows automatizados | **3** |
| Templates prontos | **2** |
| Checklists de qualidade | **4** |
| Mentes pesquisadas | 18 (sales) + 5 (CS) |
| Nichos cobertos | 7 |
| Tiers de profundidade | 4 (Orch + 3 Tiers + Pós-venda) |
| Slash commands | 14 (`/sales:*`) |

---

## 🔄 Histórico de Versões

- **v2.0.0** (2026-05-25) — Integração com customer-success (AIOX-enterprise) + padrão wrapper
- **v1.0.0** (2026-03-30) — Squad inicial com 9 agentes de venda

Ver [`CHANGELOG.md`](./CHANGELOG.md) para detalhes.

---

## 🤝 Origem & Créditos

- **Squad Sales original:** Squad Architect (v1.0)
- **Customer Success integration:** Importado de [AIOX-enterprise/customer-success](https://github.com/AIOXsquad/AIOX-enterprise/tree/main/squads/customer-success)
- **Padrão Wrapper Enterprise:** AIOX-enterprise framework

**Frameworks documentados:**
- Neil Rackham — *SPIN Selling*
- David Sandler — *Sandler Selling System*
- Chris Voss — *Never Split the Difference*
- Keenan — *Gap Selling*
- Brent Adamson & Matthew Dixon — *The Challenger Sale*
- Jeb Blount — *Fanatical Prospecting + Sales EQ*
- Chet Holmes — *The Ultimate Sales Machine*
- Aaron Ross — *Predictable Revenue*

---

## 📞 Comece agora

No Claude Code:

```
@sales-chief
```

Não sabe por onde começar? Mande `*diagnose`.

---

**Movimento Lendário** · Squad Sales v2.0.0 · Elite Sales + Customer Success
