# Changelog — Squad Sales

## [2.0.0] - 2026-05-25

### Added — Integração com AIOX-enterprise

#### Tier 4 — Pós-Venda (novo, importado de customer-success)
- 5 agentes: cs-chief, onboarding-architect, health-monitor, journey-mapper, expansion-strategist
- 10 tasks: build-health-score, create-churn-ews, design-onboarding, diagnose-cs-maturity, fill-kpi-scorecard, map-student-journey, plan-expansion, run-nps-cycle, delete-cs-squad, update-cs-squad
- 2 templates: cs-report-tmpl.yaml, expansion-playbook-tmpl.yaml
- 3 workflows: churn-prevention.yaml, cs-setup.yaml, onboarding-design.yaml
- 2 checklists: cs-readiness-checklist, health-score-checklist

#### Padrão enterprise
- 14 wrappers em `.claude/agents/sales--*.md` (formato wrapper fino)
- 14 slash commands em `.claude/commands/sales/*.md` (`/sales:agente`)
- Estrutura completa de diretórios: agents/, tasks/, templates/, workflows/, checklists/, data/, docs/, scripts/

#### 5 novos comandos
- `*onboard` — Roteia para onboarding-architect
- `*retain` — Diagnóstico de risco de churn (health-monitor)
- `*expand` — Plano de expansão de conta (expansion-strategist)
- `*journey` — Mapeamento de jornada (journey-mapper)
- `*cs-health` — Health Score completo (cs-chief)

### Changed
- Versão: 1.0.0 → 2.0.0
- Funil ampliado: pré-venda → **pré-venda + pós-venda** (5 tiers)
- README.md atualizado com Tier 4 e fluxo completo
- config.yaml expandido para v2.0 com tier_4_post_sale

### Source
- Importação direta de `AIOX-enterprise/squads/customer-success/`
- Repo origem: https://github.com/AIOXsquad/AIOX-enterprise

---

## [1.0.0] - 2026-03-30

### Added
- 9 agents: sales-chief (orchestrator), neil-rackham, david-sandler, keenan, chris-voss, challenger-sale, jeb-blount, chet-holmes, aaron-ross
- 5 tasks: diagnose-deal, qualify-prospect, create-cold-outreach, negotiate-deal, close-deal
- 2 checklists: deal-qualification-checklist, discovery-quality-checklist
- README.md com Quick Start, Tier Organization, comandos por agent
- ARCHITECTURE.md com tier system, data flow, routing protocol
- config.yaml com tier organization e component references
- voice_dna em 9/9 agents
- objection_algorithms em 9/9 agents
- output_examples em 9/9 agents
- handoff_to em 9/9 agents

### Validation
- Score: 7.9/10 (PASS — Production Ready)
- Type: Expert (dominant signal: 100% voice_dna)
- Tier 1 Structure: 16/16 checks passed
- Tier 2 Coverage: All metrics passed
- Tier 3 Quality: 7.7/10
- Tier 4 Contextual: 9.0/10
- 0 veto conditions triggered

### Research
- 18 minds pesquisadas, 8 selecionadas
- Modo de criação: YOLO
- Total: 15,768 linhas
