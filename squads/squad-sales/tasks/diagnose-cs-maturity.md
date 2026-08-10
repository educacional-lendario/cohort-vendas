# Task: Diagnose CS Maturity
# ID: CS-TP-001
# Executor: cs-chief
# Trigger: *diagnose-maturity command

task:
  name: "Diagnose CS Maturity"
  status: ready
  responsible_executor: cs-chief
  execution_type: agent
  elicit: false

  description: |
    Diagnose the Customer Success maturity level of a business by scoring
    6 dimensions against industry benchmarks. Reads workspace product and
    operations data to ground the assessment in real evidence. Outputs a
    prioritized gap report with concrete next steps per dimension.

  input:
    - "workspace/businesses/{business}/products/ — product catalog, proof, testimonials"
    - "workspace/businesses/{business}/operations/ — pricing, CS motion, retention data"
    - "workspace/businesses/{business}/company/ — company profile, ICP"
    - "workspace/businesses/{business}/analytics/ — existing KPIs, dashboards"
    - "workspace/businesses/{business}/analytics/customer-success/ — any previous CS outputs"

  steps:
    - id: "1"
      name: "Load workspace data"
      action: |
        1. Read all products under workspace/businesses/{business}/products/
        2. Read operations data (pricing-strategy, retention, CS motion if exists)
        3. Read company profile and ICP for context
        4. Read any existing CS outputs from previous runs

    - id: "2"
      name: "Score 6 dimensions"
      action: |
        Score each dimension 1-5 (1=ad hoc, 5=optimized):

        1. ONBOARDING — Structured flow? Time-to-first-win defined?
           Activation metrics tracked? Re-engagement triggers?
        2. HEALTH SCORE — Composite score exists? Weighted components?
           Thresholds defined? Automated alerts?
        3. CHURN PREVENTION — EWS in place? Severity levels?
           Response playbooks? SLAs for intervention?
        4. NPS/CSAT — Survey cadence? Touchpoints mapped?
           Action plans by score range? Closed-loop feedback?
        5. EXPANSION — Cross-sell/upsell triggers? Timing defined?
           Conversion targets? Anti-expansion signals?
        6. KPIs — North star metric? 5-7 supporting metrics?
           Owners assigned? Cadence defined?

        For each dimension:
        - Evidence found (file paths, data points)
        - Evidence missing
        - Score justification (1 sentence)

    - id: "3"
      name: "Calculate composite maturity"
      action: |
        1. Calculate weighted average (all dimensions equal weight)
        2. Classify maturity level:
           - 1.0-1.9: REACTIVE (firefighting mode)
           - 2.0-2.9: DEFINED (some processes, inconsistent)
           - 3.0-3.9: PROACTIVE (systematic, gaps remain)
           - 4.0-4.9: PREDICTIVE (data-driven, mostly automated)
           - 5.0: OPTIMIZED (best-in-class across all dimensions)
        3. Identify top 3 gaps (lowest scores)

    - id: "4"
      name: "Generate prioritized gap report"
      action: |
        For each gap (sorted by score ascending):
        1. Current state description
        2. Target state description
        3. Recommended task to close the gap (reference squad task)
        4. Estimated effort (S/M/L)
        5. Expected impact on retention/expansion
        6. Dependencies on other dimensions

  output:
    format: "CS Maturity YAML (workspace canonical)"
    path: "workspace/businesses/{business}/analytics/customer-success/cs-maturity.yaml"
    template: "workspace/_templates/customer-success/cs-maturity.yaml"
    note: "This is HIGH-VALUE data loaded on every CS session. Lives in workspace, NOT outputs."
    sections:
      - maturity (level, composite score, scale)
      - dimensions (6 dimensions with evidence_found and evidence_missing)
      - gaps (prioritized with remediation tasks)
      - delegation_plan (internal + external experts)
      - product_tiers (CS motion per product)

  acceptance_criteria:
    - "All 6 dimensions scored with evidence references"
    - "Each score justified with workspace data (not invented)"
    - "Composite maturity level calculated and classified"
    - "Top 3 gaps identified with specific remediation tasks"
    - "Output saved to workspace/businesses/{business}/analytics/customer-success/cs-maturity.yaml"
    - "No dimension scored without at least 1 evidence file read"

  veto_conditions:
    - "Dimension scored without reading any workspace data → BLOQUEAR (No Invention)"
    - "Gap report without mapping to specific squad tasks → REDO step 4"
    - "Maturity level OPTIMIZED (5.0) without evidence for every dimension → REJEITAR"
    - "Output contains business-specific data inside squads/ → BLOQUEAR (Squad Agnosticism)"

  action_items:
    - "Load workspace data for target business"
    - "Score 6 CS dimensions with evidence"
    - "Generate prioritized gap report"
    - "Save output to workspace/businesses/{business}/analytics/customer-success/cs-maturity.yaml"
    - "Hand off to cs-chief for action planning"
