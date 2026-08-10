# Health Score Model Validation Checklist

## Overview

Valida se um modelo de health score está completo, calibrado e pronto para uso em produção. Usado pelo @health-monitor após criar ou recalibrar um modelo, e pelo @cs-chief durante QA do setup de CS.

---

## Validation Threshold

| Checks Passing | Verdict | Ação |
|----------------|---------|------|
| 100% | APPROVED | Modelo pronto para produção |
| 80-99% | CONDITIONAL | Pode usar com gaps documentados, fix em 30 dias |
| 60-79% | NEEDS WORK | Retornar ao @health-monitor para ajustes |
| < 60% | REJECTED | Redesenhar modelo (delegar para @nick-mehta) |

---

## 1. Components (5 Required)

- [ ] Modelo tem exatamente 5 componentes?
- [ ] Cada componente tem nome descritivo?
- [ ] Cada componente tem definição clara (o que mede)?
- [ ] Componentes cobrem dimensões distintas (sem sobreposição significativa)?
- [ ] Componentes são relevantes para o produto específico?

**Componentes do modelo:**

| # | Nome | Definição | Relevância |
|---|------|-----------|------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

---

## 2. Weights

- [ ] Cada componente tem peso atribuído?
- [ ] Pesos somam exatamente 100%?
- [ ] Nenhum componente tem peso < 5% (se tem, questionar se é necessário)?
- [ ] Nenhum componente tem peso > 40% (evitar dependência excessiva)?
- [ ] Justificativa documentada para a distribuição de pesos?
- [ ] Pesos refletem importância relativa para retenção?

**Distribuição de pesos:**

| Componente | Peso | Justificativa |
|------------|------|---------------|
| | % | |
| | % | |
| | % | |
| | % | |
| | % | |
| **Total** | **100%** | |

---

## 3. Thresholds

- [ ] Três faixas definidas (healthy / at_risk / critical)?
- [ ] Threshold healthy → at_risk definido (ex: score < 70)?
- [ ] Threshold at_risk → critical definido (ex: score < 40)?
- [ ] Thresholds fazem sentido para o tier de CS motion?
- [ ] Ações definidas para cada faixa?
- [ ] Thresholds calibrados com dados históricos (ou plano para calibrar)?

**Thresholds:**

| Faixa | Range | Ação Esperada |
|-------|-------|---------------|
| Healthy | ___-100 | Monitorar, expansion eligible |
| At Risk | ___-___ | Intervenção proativa, playbook ativado |
| Critical | 0-___ | Alerta imediato, rescue intervention |

---

## 4. Product-Specific Signals

- [ ] Sinais são específicos para este produto (não genéricos)?
- [ ] Pelo menos 1 sinal de engajamento com conteúdo/plataforma?
- [ ] Pelo menos 1 sinal de progresso/milestone?
- [ ] Pelo menos 1 sinal de sentimento (NPS, feedback, suporte)?
- [ ] Pelo menos 1 sinal de adoção de features-chave?
- [ ] Sinais são mensuráveis (não subjetivos)?
- [ ] Sinais mapeados para o componente correspondente?
- [ ] Frequência de cada sinal documentada?

**Mapa de sinais:**

| Sinal | Tipo | Componente | Frequência | Mensurável? |
|-------|------|------------|------------|-------------|
| | | | | |
| | | | | |
| | | | | |
| | | | | |

---

## 5. Data Sources

- [ ] Fonte de dados identificada para cada componente?
- [ ] Todas as fontes são acessíveis (API, DB, manual)?
- [ ] Cadência de coleta definida para cada fonte?
- [ ] Formato dos dados documentado?
- [ ] Responsável pela coleta definido (automático ou manual)?
- [ ] Plano de fallback se fonte primária indisponível?
- [ ] Dados históricos suficientes para baseline (ou plano para coletar)?

**Fontes de dados:**

| Componente | Fonte Primária | Tipo | Cadência | Fallback |
|------------|---------------|------|----------|----------|
| | | API/DB/Manual | | |
| | | API/DB/Manual | | |
| | | API/DB/Manual | | |
| | | API/DB/Manual | | |
| | | API/DB/Manual | | |

---

## 6. Operational Readiness

- [ ] Refresh automático configurado (ou plano com data)?
- [ ] Alertas automáticos para transições de faixa?
- [ ] Dashboard ou visualização disponível?
- [ ] Processo de recalibração definido (cadência)?
- [ ] Owner do modelo definido (quem mantém)?

---

## Summary

| Seção | Checks Passing | Total | % |
|-------|---------------|-------|---|
| Components | /5 | 5 | |
| Weights | /6 | 6 | |
| Thresholds | /6 | 6 | |
| Product Signals | /8 | 8 | |
| Data Sources | /7 | 7 | |
| Operational | /5 | 5 | |
| **Total** | **/37** | **37** | |

**Verdict:** _______________

**Critical Issues:**
1.
2.

**Delegations Needed:**

| Issue | Expert | Expected Output |
|-------|--------|-----------------|
| | | |

**Next Calibration Date:** _______________
