# Task: Map Cross-Product Student Journey
# ID: CS-TP-007
# Executor: cs-chief
# Trigger: *map-journey command

task:
  name: "Map Cross-Product Student Journey"
  status: ready
  responsible_executor: cs-chief
  execution_type: agent
  elicit: false

  description: |
    Map the complete student journey across all products of a business.
    Identifies stages, touchpoints, owners, moments of truth, and gaps
    in the experience. Provides a unified view of the customer lifecycle
    from first contact through advocacy, spanning multiple products.

  input:
    - name: business_name
      type: string
      required: true
      description: "Business to map journey for"
    - "workspace/businesses/{business}/products/ — all products (curriculum, ICP, proof)"
    - "workspace/businesses/{business}/company/ — company profile, ICP"
    - "workspace/businesses/{business}/operations/ — pricing, CS motion"
    - "workspace/businesses/{business}/analytics/customer-success/ — existing CS outputs (onboarding, health, expansion)"

  steps:
    - id: "1"
      name: "Inventory all products"
      action: |
        1. Read workspace/businesses/{business}/products/ directory
        2. For each product, extract:
           - Product name and type
           - Ticket value and CS motion tier
           - Target ICP (product-level if exists, else company-level)
           - Curriculum structure (modules, duration)
           - Natural predecessor/successor products
        3. Order products by typical customer progression
           (e.g., free trial → fundamentals → advanced → coaching)

    - id: "2"
      name: "Map journey stages"
      action: |
        Define 7 universal stages across all products:

        1. AWARENESS — First contact with the brand
           - Touchpoints: ads, content, referral, social media
           - Owner: marketing
           - Duration: variable

        2. CONSIDERATION — Evaluating specific product
           - Touchpoints: sales page, webinar, free content, demo
           - Owner: marketing/sales
           - Duration: 1-30 days

        3. PURCHASE — Transaction complete
           - Touchpoints: checkout, welcome email, receipt
           - Owner: sales/operations
           - Duration: 1 day

        4. ONBOARDING — Getting started with product
           - Touchpoints: per onboarding-flow.yaml if exists
           - Owner: CS team
           - Duration: 7-30 days (product-dependent)

        5. VALUE REALIZATION — Achieving outcomes
           - Touchpoints: milestones, wins, proof moments
           - Owner: CS team + product
           - Duration: 30-90 days

        6. EXPANSION — Moving to next product
           - Touchpoints: per expansion playbook if exists
           - Owner: CS team + sales
           - Duration: variable

        7. ADVOCACY — Referring and promoting
           - Touchpoints: testimonial, referral, community leadership
           - Owner: CS team + marketing
           - Duration: ongoing

    - id: "3"
      name: "Map touchpoints per product x stage"
      action: |
        Create matrix: products (rows) x stages (columns)

        For each cell:
        1. List specific touchpoints (email, call, message, in-app)
        2. Assign owner (role, not person)
        3. Define expected outcome
        4. Flag if touchpoint exists vs. missing

        Pull from existing CS outputs:
        - onboarding-flow.yaml → stages 4-5
        - expansion playbook → stage 6
        - nps-cycle → stages 4-7

    - id: "4"
      name: "Identify moments of truth"
      action: |
        Moments of Truth = high-impact touchpoints that disproportionately
        affect retention, expansion, or advocacy.

        For each product, identify:
        1. FIRST WIN — The "aha moment" (from onboarding flow)
        2. PROOF MOMENT — When they achieve a measurable result
        3. DECISION POINT — When they choose to continue or leave
        4. ADVOCACY TRIGGER — When they become willing to recommend

        Score each moment:
        - Impact on retention (1-5)
        - Current quality of experience (1-5)
        - Gap = Impact - Quality (higher = bigger opportunity)

    - id: "5"
      name: "Identify gaps and handoff failures"
      action: |
        Analyze the journey for:

        1. MISSING TOUCHPOINTS:
           - Stage x product cells with no touchpoint defined
           - Critical moments without assigned owner

        2. HANDOFF FAILURES:
           - Transitions between stages without clear process
           - Owner changes without handoff protocol
           - Product transitions without bridge content

        3. EXPERIENCE GAPS:
           - Stages with no feedback mechanism (no NPS/CSAT)
           - Long periods without any touchpoint
           - Inconsistent experience across products

        4. DATA GAPS:
           - Stages where customer health is unmonitored
           - Transitions without success criteria

    - id: "6"
      name: "Generate journey map"
      action: |
        Compile into structured output:
        - Product inventory with progression order
        - 7-stage journey framework
        - Touchpoint matrix (product x stage)
        - Moments of truth with gap scores
        - Gap analysis with prioritized fixes
        - Recommended actions mapped to squad tasks

  output:
    format: "student-journey-map.yaml"
    path: "workspace/businesses/{business}/analytics/customer-success/student-journey-map.yaml"
    sections:
      - product_inventory (ordered by progression)
      - journey_stages (7 stages with definitions)
      - touchpoint_matrix (product x stage, with owners)
      - moments_of_truth (per product, with gap scores)
      - gap_analysis (missing touchpoints, handoff failures, experience gaps)
      - recommended_actions (mapped to CS squad tasks)

  acceptance_criteria:
    - "All products in workspace inventory included"
    - "7 journey stages mapped with touchpoints per product"
    - "Each touchpoint has assigned owner"
    - "Moments of truth identified per product with gap scores"
    - "Gaps categorized (missing touchpoint, handoff failure, experience gap)"
    - "Recommendations linked to specific squad tasks"
    - "Output saved to workspace/ as valid YAML"

  veto_conditions:
    - "Journey mapped without reading product data → BLOQUEAR (No Invention)"
    - "Moments of truth without impact scoring → REDO step 4"
    - "Gap analysis without prioritization → REDO step 5"
    - "Products listed without natural progression order → REDO step 1"
    - "Touchpoint matrix with > 50% empty cells and no gap flag → BLOQUEAR (incomplete)"

  action_items:
    - "Inventory all products for target business"
    - "Map 7 journey stages with touchpoints"
    - "Identify moments of truth per product"
    - "Analyze gaps and handoff failures"
    - "Generate student-journey-map.yaml to workspace/"
    - "Hand off to cs-chief for strategic planning"
