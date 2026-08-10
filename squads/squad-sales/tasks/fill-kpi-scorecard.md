# Task: Fill KPI Scorecard
# ID: CS-TP-008
# Executor: cs-chief
# Trigger: *fill-kpi-scorecard command

task:
  name: "Fill KPI Scorecard"
  status: ready
  responsible_executor: cs-chief
  execution_type: hybrid
  elicit: true

  description: |
    Fill the KPI scorecard for a business with CS metrics. Reads the
    workspace kpi-scorecards.yaml template, fills with north star metric,
    5-7 supporting metrics with owners, cadences, targets, and data sources.
    Hybrid execution: agent proposes metrics, human validates and assigns owners.

  input:
    - name: business_name
      type: string
      required: true
      description: "Business to fill scorecard for"
    - "workspace/_templates/customer-success/ — KPI scorecard template"
    - "workspace/businesses/{business}/products/ — product data"
    - "workspace/businesses/{business}/operations/ — existing KPIs, pricing"
    - "workspace/businesses/{business}/analytics/ — existing metrics"
    - "workspace/businesses/{business}/analytics/customer-success/ — existing CS outputs (health score, EWS, NPS)"

  elicitation_points:
    - point: "north_star_confirmation"
      when: "Step 2 complete"
      ask: |
        North Star Metric proposta: {north_star_name}
        Definição: {north_star_definition}
        Fórmula: {north_star_formula}
        Target: {north_star_target}

        Essa é a métrica que melhor reflete o sucesso do cliente nesse negócio?

    - point: "metrics_review"
      when: "Step 3 complete"
      ask: |
        KPI Scorecard proposto ({metric_count} métricas):

        | Métrica | Cadência | Target | Owner |
        |---------|----------|--------|-------|
        {metrics_table}

        Alguma métrica faltando? Owners corretos? Targets realistas?

  steps:
    - id: "1"
      name: "Load context and template"
      action: |
        1. Read KPI scorecard template from workspace/_templates/customer-success/
        2. Read product data for all products
        3. Read existing operations/analytics data
        4. Load existing CS outputs (health score, EWS, NPS, journey map)
        5. Identify what metrics are already tracked vs. missing

    - id: "2"
      name: "Define north star metric"
      action: |
        Select THE single metric that best represents customer success:

        CANDIDATES (select 1):
        - Net Revenue Retention (NRR): for SaaS with expansion revenue
        - Gross Retention Rate (GRR): for education with fixed cohorts
        - Student Outcome Rate: for education where outcomes are measurable
        - Time-to-Value: for products where speed matters
        - Customer Lifetime Value (CLV): for multi-product portfolios

        Selection criteria:
        - Reflects actual customer success (not just company revenue)
        - Measurable with available data sources
        - Actionable by CS team
        - Aligned with business model (education vs SaaS vs hybrid)
        → Elicit: north_star_confirmation

    - id: "3"
      name: "Define 5-7 supporting metrics"
      action: |
        Select from these categories (1-2 per category):

        ACQUISITION/ONBOARDING:
        - Time-to-First-Win (days from purchase to first outcome)
        - Onboarding Completion Rate (% completing all milestones)
        - Activation Rate (% reaching proficiency within target time)

        ENGAGEMENT/HEALTH:
        - Health Score Average (composite from health-score.yaml)
        - Feature Adoption Rate (% of features used)
        - Active Usage Rate (DAU/MAU or equivalent)

        RETENTION:
        - Churn Rate (monthly/quarterly by cohort)
        - Renewal Rate (for subscription/cohort products)
        - At-Risk Account Rate (% in yellow/red health)

        SATISFACTION:
        - NPS Score (from nps-cycle.yaml)
        - CSAT Score (per touchpoint)
        - Support Resolution Time

        EXPANSION:
        - Expansion Revenue Rate (upsell + cross-sell)
        - Cross-Product Adoption Rate (multi-product customers)
        - Referral Rate (customers who refer)

        For each metric define:
        - Name and definition
        - Formula / calculation method
        - Data source
        - Cadence (daily/weekly/monthly/quarterly)
        - Target (with rationale)
        - Owner (role)
        - Alert threshold (when to escalate)
        → Elicit: metrics_review

    - id: "4"
      name: "Set cadences and review rhythm"
      action: |
        Define review cadence per metric:

        | Cadence | Metrics | Forum |
        |---------|---------|-------|
        | Daily | Health score, at-risk accounts | CSM dashboard |
        | Weekly | Churn, NPS responses, tickets | CS team standup |
        | Monthly | North star, retention, expansion | CS review meeting |
        | Quarterly | CLV, NRR, strategic metrics | Business review |

        Define escalation rules:
        - Metric below target for 2+ consecutive periods → owner escalates
        - North star below target → executive review

    - id: "5"
      name: "Generate KPI scorecard"
      action: |
        Fill the template with:
        - North star metric with full definition
        - 5-7 supporting metrics with all fields
        - Review cadences and forums
        - Escalation rules
        - Data source inventory (what exists vs. what needs setup)

  output:
    format: "kpi-scorecard.yaml"
    path: "workspace/businesses/{business}/operations/kpi-scorecards.yaml"
    sections:
      - scorecard_metadata (business, version, last updated)
      - north_star (metric, formula, target, owner)
      - supporting_metrics (5-7 metrics with full definition)
      - review_cadences (daily, weekly, monthly, quarterly)
      - escalation_rules (thresholds, owners, forums)
      - data_sources (available vs. needed)

  acceptance_criteria:
    - "Exactly 1 north star metric defined with clear rationale"
    - "5-7 supporting metrics covering all categories (onboarding, health, retention, satisfaction, expansion)"
    - "Each metric has: name, formula, target, cadence, owner, data source"
    - "Review cadences defined with specific forums"
    - "Escalation rules set for below-target metrics"
    - "Data source gaps identified (available vs. needs setup)"
    - "Output saved to workspace/ as valid YAML"

  veto_conditions:
    - "North star metric not measurable with available data → REDO step 2 with feasible alternative"
    - "Metrics without assigned owner → BLOQUEAR (accountability gap)"
    - "All metrics at same cadence → REDO step 4 (differentiation needed)"
    - "No escalation rules for north star → BLOQUEAR"
    - "Metrics invented without data source path → BLOQUEAR (No Invention)"
    - "< 5 or > 7 supporting metrics → AJUSTAR to range"

  action_items:
    - "Load workspace data and KPI template"
    - "Define north star metric for business"
    - "Select 5-7 supporting metrics with full definitions"
    - "Set review cadences and escalation rules"
    - "Generate kpi-scorecard.yaml to workspace/"
    - "Hand off to cs-chief for operational rollout"
