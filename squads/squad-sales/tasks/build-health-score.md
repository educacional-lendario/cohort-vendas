# Task: Build Health Score Model
# ID: CS-TP-003
# Executor: cs-chief (delegates to @nick-mehta for framework)
# Trigger: *build-health-score command

task:
  name: "Build Health Score Model"
  status: ready
  responsible_executor: cs-chief
  execution_type: agent
  elicit: false

  description: |
    Build a composite health score model for a specific product. Defines
    5 weighted components, thresholds (healthy/at-risk/critical), and
    observable signals per component. Delegates to @nick-mehta agent for
    the Gainsight-inspired framework and scoring methodology.

  input:
    - name: product_name
      type: string
      required: true
      description: "Product to build health score for"
    - name: available_data_sources
      type: list
      required: true
      description: "Data sources available (e.g., login frequency, completion rate, NPS, support tickets, community activity)"
    - "workspace/businesses/{business}/products/{product}/ — product data"
    - "workspace/businesses/{business}/analytics/ — existing metrics"
    - "workspace/businesses/{business}/analytics/customer-success/ — previous CS outputs (onboarding, maturity)"

  steps:
    - id: "1"
      name: "Audit available data"
      action: |
        1. Read product data from workspace
        2. List all available_data_sources provided
        3. Classify each source by reliability:
           - DIRECT: system-generated, objective (logins, completions)
           - INDIRECT: survey-based, subjective (NPS, CSAT)
           - DERIVED: calculated from other sources (engagement score)
        4. Identify data gaps (important signals with no source)

    - id: "2"
      name: "Define 5 health score components"
      action: |
        Delegate to @nick-mehta framework. Select 5 components from:

        1. ENGAGEMENT — Usage frequency, depth, recency
           Signals: login frequency, feature adoption, time in product
           Weight: 25-35%

        2. ADOPTION — Feature utilization, milestone completion
           Signals: features used / available, curriculum progress
           Weight: 20-30%

        3. SATISFACTION — Sentiment, support experience
           Signals: NPS/CSAT score, support ticket frequency/sentiment
           Weight: 15-25%

        4. OUTCOME — Results achieved, ROI realized
           Signals: goals completed, proof metrics, testimonial eligibility
           Weight: 15-25%

        5. RELATIONSHIP — Stakeholder engagement, advocacy
           Signals: community participation, referrals, event attendance
           Weight: 10-20%

        Adjust weights based on CS motion tier and product type.
        Total weights MUST sum to 100%.

    - id: "3"
      name: "Set thresholds per component"
      action: |
        For each component, define 3 zones:

        HEALTHY (green): Score >= 70
        - Customer is on track, no intervention needed
        - Monitor cadence: weekly

        AT-RISK (yellow): Score 40-69
        - Early warning, proactive outreach recommended
        - Monitor cadence: daily
        - Alert: CSM notification

        CRITICAL (red): Score < 40
        - Immediate intervention required
        - Monitor cadence: real-time
        - Alert: CSM + manager escalation
        - SLA: contact within 24h

    - id: "4"
      name: "Map signals to scores"
      action: |
        For each component, map available signals to numeric scores:

        1. Define signal → score conversion rules
           Example: login_frequency
           - Daily: 100
           - 3-5x/week: 80
           - 1-2x/week: 60
           - 1-2x/month: 30
           - No login 30+ days: 0

        2. Handle missing signals gracefully:
           - If primary signal unavailable, use fallback signal
           - If no signals available for component, mark as "unscored"
           - Unscored components redistribute weight to scored ones

    - id: "5"
      name: "Generate health-score.yaml"
      action: |
        Compile model into structured YAML:
        - product context
        - 5 components with weights, signals, thresholds
        - composite score calculation formula
        - alert rules per zone
        - data source requirements
        - fallback rules for missing data

  output:
    format: "health-score.yaml"
    path: "workspace/businesses/{business}/analytics/customer-success/{product}/health-score.yaml"
    sections:
      - model_metadata (product, version, cs_motion_tier)
      - components (5 components with weights summing to 100%)
      - thresholds (healthy/at-risk/critical per component)
      - signal_mappings (signal → score conversion rules)
      - composite_formula (weighted average calculation)
      - alert_rules (per zone, escalation paths)
      - data_requirements (sources needed, fallbacks)

  acceptance_criteria:
    - "Exactly 5 components defined with weights summing to 100%"
    - "Each component has at least 2 observable signals"
    - "Thresholds defined for all 3 zones (healthy/at-risk/critical)"
    - "Signal → score mappings are concrete and measurable"
    - "Missing data fallback strategy defined"
    - "Alert rules include escalation path and SLA"
    - "Output saved to workspace/ as valid YAML"

  veto_conditions:
    - "Weights do not sum to 100% → BLOQUEAR (mathematical error)"
    - "Component without any mappable signal from available_data_sources → REMOVER component and redistribute weight"
    - "Thresholds without actionable response (who does what) → REDO step 3"
    - "Health score model without fallback for missing data → BLOQUEAR (fragile model)"
    - "Signals invented without data source → BLOQUEAR (No Invention)"

  action_items:
    - "Audit available data sources for target product"
    - "Delegate to @nick-mehta for health score framework"
    - "Define 5 weighted components with signals"
    - "Set thresholds and alert rules"
    - "Generate health-score.yaml to workspace/"
    - "Hand off to cs-chief for integration with EWS"
