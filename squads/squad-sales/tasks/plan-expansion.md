# Task: Plan Expansion Strategy
# ID: CS-TP-005
# Executor: cs-chief
# Trigger: *plan-expansion command

task:
  name: "Plan Expansion Strategy"
  status: ready
  responsible_executor: cs-chief
  execution_type: hybrid
  elicit: true

  description: |
    Plan an expansion strategy (cross-sell/upsell) from a source product
    to a target product. Defines composite triggers, optimal timing windows,
    channels per CS motion tier, conversion targets, and anti-expansion
    signals that should pause outreach.

  input:
    - name: source_product
      type: string
      required: true
      description: "Product the customer currently uses"
    - name: target_product
      type: string
      required: true
      description: "Product to expand into"
    - "workspace/businesses/{business}/products/{source}/ — source product data"
    - "workspace/businesses/{business}/products/{target}/ — target product data"
    - "workspace/businesses/{business}/operations/pricing-strategy.yaml — pricing context"
    - "workspace/businesses/{business}/analytics/customer-success/{source}/health-score.yaml — source health (if exists)"
    - "workspace/businesses/{business}/products/{source}/onboarding-flow.yaml — source onboarding (if exists)"

  elicitation_points:
    - point: "expansion_path_confirmation"
      when: "Step 2 complete"
      ask: |
        Expansion path: {source_product} → {target_product}
        Ticket delta: {source_ticket} → {target_ticket}
        Natural bridge: {bridge_description}
        ICP overlap: {overlap_percentage}

        Faz sentido esse caminho de expansão? Existe uma jornada natural entre os dois produtos?

    - point: "trigger_review"
      when: "Step 3 complete"
      ask: |
        Triggers compostos propostos (precisa de 3+ para ativar):
        {trigger_list}

        Anti-expansion signals:
        {anti_signal_list}

        Algum ajuste nos triggers ou sinais?

  steps:
    - id: "1"
      name: "Load product pair context"
      action: |
        1. Read source product data (proof, testimonials, curriculum, ICP)
        2. Read target product data (proof, testimonials, curriculum, ICP)
        3. Read pricing strategy for ticket values
        4. Load source health score model if exists
        5. Identify ICP overlap between products

    - id: "2"
      name: "Map expansion path"
      action: |
        1. Identify natural bridge between products:
           - What outcome in source creates need for target?
           - What skill/knowledge from source enables target?
           - What pain point remains unsolved after source?
        2. Define expansion type:
           - UPSELL: same category, higher tier (Fundamentals → Advanced)
           - CROSS-SELL: different category, complementary (Course → Coaching)
           - UPGRADE: same product, premium features
        3. Calculate ticket delta and expansion revenue potential
        → Elicit: expansion_path_confirmation

    - id: "3"
      name: "Define composite triggers"
      action: |
        Expansion signal = 3+ triggers firing simultaneously.
        Single trigger alone is NOT sufficient.

        READINESS TRIGGERS:
        - Health score >= 80 for 30+ days
        - All onboarding milestones completed
        - Product proficiency demonstrated (advanced features used)
        - Time in product >= minimum maturity period

        INTENT TRIGGERS:
        - Questions about topics covered in target product
        - Community posts showing interest in target domain
        - Support tickets about limitations solved by target
        - Attendance at target product webinars/events

        TIMING TRIGGERS:
        - Contract renewal window (60-90 days before)
        - Post-success moment (big win achieved, testimonial given)
        - Cohort completion (for education products)
        - Budget cycle alignment

        COMPOSITE RULE: activate expansion outreach when
        >= 1 readiness + >= 1 intent + >= 1 timing trigger.
        → Elicit: trigger_review

    - id: "4"
      name: "Define anti-expansion signals"
      action: |
        Signals that MUST pause expansion outreach:

        HARD STOPS (never expand):
        - Health score < 50 (fix retention first)
        - Active support escalation
        - Cancellation request in progress
        - Payment issues unresolved

        SOFT STOPS (delay, don't cancel):
        - Health score 50-69 (stabilize first)
        - Recent negative NPS (address feedback first)
        - Mid-onboarding (let them finish current journey)
        - Recent price increase (sensitivity period)

    - id: "5"
      name: "Design expansion playbook"
      action: |
        Per CS motion tier:

        DIGITAL (automated):
        - Channel: email sequence, in-app messaging
        - Timing: trigger-based, automated
        - Content: case studies, comparison, limited-time offer
        - Conversion target: 5-10%

        LIGHT-TOUCH:
        - Channel: personalized email + webinar invitation
        - Timing: CSM-reviewed, batch cadence
        - Content: success story bridge, demo offer
        - Conversion target: 10-15%

        MID-TOUCH:
        - Channel: 1:1 CSM conversation + tailored proposal
        - Timing: CSM-initiated at trigger point
        - Content: ROI analysis, custom transition plan
        - Conversion target: 15-25%

        WHITE-GLOVE:
        - Channel: executive sponsor meeting + pilot program
        - Timing: account planning cycle
        - Content: strategic business case, pilot with success criteria
        - Conversion target: 25-40%

    - id: "6"
      name: "Generate expansion playbook"
      action: |
        Compile into structured output:
        - expansion path (source → target, type, bridge)
        - composite triggers with activation rule
        - anti-expansion signals (hard/soft stops)
        - playbook per motion tier
        - conversion targets and tracking metrics
        - timeline from trigger to close

  output:
    format: "expansion-playbook.yaml"
    path: "workspace/businesses/{business}/analytics/customer-success/expansion/{source}-to-{target}.yaml"
    sections:
      - expansion_metadata (products, type, ticket delta)
      - expansion_path (bridge, ICP overlap)
      - composite_triggers (readiness + intent + timing)
      - anti_expansion_signals (hard stops, soft stops)
      - playbook_per_tier (digital, light, mid, white-glove)
      - conversion_targets (per tier with tracking metrics)
      - timeline (trigger to close, per tier)

  acceptance_criteria:
    - "Both source and target product data loaded from workspace"
    - "Natural bridge between products clearly articulated"
    - "Composite trigger rule requires 3+ simultaneous signals"
    - "Anti-expansion signals defined with hard/soft stop distinction"
    - "Playbook differentiated by CS motion tier"
    - "Conversion targets set per tier with rationale"
    - "Output saved to workspace/ as valid YAML"

  veto_conditions:
    - "Expansion triggered by single signal (not composite) → REDO step 3"
    - "No anti-expansion signals defined → BLOQUEAR (predatory expansion risk)"
    - "Conversion targets identical across tiers → REDO step 5"
    - "Expansion path without evidence of ICP overlap → BLOQUEAR (forced fit)"
    - "Playbook without specific channel and content per tier → REDO step 5"

  action_items:
    - "Load source and target product data"
    - "Map natural expansion bridge"
    - "Define composite triggers (3+ required)"
    - "Define anti-expansion signals"
    - "Design tier-differentiated playbook"
    - "Generate expansion playbook to workspace/"
    - "Hand off to cs-chief for portfolio integration"
