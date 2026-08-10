# Task: Run NPS/CSAT Cycle
# ID: CS-TP-006
# Executor: cs-chief
# Trigger: *run-nps-cycle command

task:
  name: "Run NPS/CSAT Cycle"
  status: ready
  responsible_executor: cs-chief
  execution_type: hybrid
  elicit: true

  description: |
    Design and plan an NPS/CSAT survey cycle for a specific product and
    journey stage. Defines touchpoints, question design, benchmarks,
    and action plans by score range. Hybrid execution: agent designs
    the survey, human reviews and approves before deployment.

  input:
    - name: product_name
      type: string
      required: true
      description: "Product to run NPS/CSAT for"
    - name: journey_stage
      type: string
      required: true
      description: "Journey stage: onboarding | activation | proficiency | renewal | post-churn"
    - "workspace/businesses/{business}/products/{product}/ — product data, ICP"
    - "workspace/businesses/{business}/products/{product}/onboarding-flow.yaml — onboarding phases (if exists)"
    - "workspace/businesses/{business}/analytics/customer-success/{product}/health-score.yaml — health model (if exists)"

  elicitation_points:
    - point: "survey_design_review"
      when: "Step 3 complete"
      ask: |
        Survey design para {product_name} ({journey_stage}):
        - Tipo: {survey_type} (NPS/CSAT/CES)
        - Pergunta principal: "{main_question}"
        - Follow-up aberta: "{followup_question}"
        - Touchpoint: {touchpoint_description}
        - Timing: {timing}

        Aprova o design? Quer ajustar a pergunta ou o timing?

    - point: "action_plan_review"
      when: "Step 5 complete"
      ask: |
        Plano de ação por faixa de score:
        - Promoters (9-10): {promoter_action}
        - Passives (7-8): {passive_action}
        - Detractors (0-6): {detractor_action}

        SLA de resposta para detractors: {detractor_sla}

        Aprova os planos de ação?

  steps:
    - id: "1"
      name: "Load context"
      action: |
        1. Read product data (ICP, proof, testimonials)
        2. Load onboarding flow if exists (to map touchpoints)
        3. Load health score model if exists (to correlate)
        4. Identify journey stage specifics:
           - Onboarding: activation metrics, first win
           - Activation: feature adoption, time-to-value
           - Proficiency: advanced usage, outcome achievement
           - Renewal: satisfaction, expansion readiness
           - Post-churn: exit reasons, recovery opportunity

    - id: "2"
      name: "Select survey type and touchpoint"
      action: |
        Match survey type to journey stage:

        | Stage | Primary | Secondary | Touchpoint |
        |-------|---------|-----------|------------|
        | Onboarding | CES | CSAT | After first win milestone |
        | Activation | CSAT | NPS | 30 days post-start |
        | Proficiency | NPS | CSAT | After key outcome achieved |
        | Renewal | NPS | CES | 60 days before renewal |
        | Post-churn | CSAT | — | 7 days after cancellation |

        Define exact trigger moment within the journey.

    - id: "3"
      name: "Design survey questions"
      action: |
        1. Main question (standard for type):
           - NPS: "De 0 a 10, qual a probabilidade de recomendar {product} para um colega?"
           - CSAT: "Como você avalia sua experiência com {aspect}?"
           - CES: "Quão fácil foi {action}?"

        2. Follow-up open question:
           - For high scores: "O que mais contribuiu para essa experiência?"
           - For low scores: "O que podemos melhorar?"

        3. Optional contextual question (max 1):
           - Relevant to journey stage
           - Actionable (can drive specific improvement)

        4. Survey constraints:
           - Max 3 questions total
           - Completion time < 60 seconds
           - Mobile-friendly
        → Elicit: survey_design_review

    - id: "4"
      name: "Set benchmarks"
      action: |
        Define benchmarks per survey type:

        NPS BENCHMARKS (education/SaaS):
        - Industry average: 30-40
        - Good: 50+
        - Excellent: 70+
        - Response rate target: 20-30%

        CSAT BENCHMARKS:
        - Industry average: 75-80%
        - Good: 85%+
        - Excellent: 90%+
        - Response rate target: 25-35%

        CES BENCHMARKS:
        - Industry average: 5.0-5.5 (7-point scale)
        - Good: 6.0+
        - Excellent: 6.5+
        - Response rate target: 30-40%

        Set specific targets for this product based on maturity.

    - id: "5"
      name: "Create action plans by score range"
      action: |
        NPS ACTION PLANS:

        PROMOTERS (9-10):
        - Thank and acknowledge
        - Request testimonial/case study
        - Invite to referral program
        - Flag as expansion candidate
        - SLA: acknowledgment within 48h

        PASSIVES (7-8):
        - Thank and probe for improvement areas
        - Address specific feedback within 7d
        - Monitor for score decline
        - Personal follow-up if open-text reveals issue
        - SLA: follow-up within 72h

        DETRACTORS (0-6):
        - Immediate CSM alert
        - Personal outreach within SLA
        - Root cause analysis
        - Recovery plan with milestones
        - Executive involvement for white-glove accounts
        - SLA: contact within 24h (mid/white-glove), 48h (light), 72h (digital)

        CLOSED-LOOP REQUIREMENT:
        Every detractor MUST receive personal follow-up.
        Track: response rate, resolution rate, score recovery rate.
        → Elicit: action_plan_review

    - id: "6"
      name: "Generate survey design output"
      action: |
        Compile into structured output:
        - survey metadata (type, product, stage)
        - touchpoint definition (trigger, timing, channel)
        - questions (max 3)
        - benchmarks and targets
        - action plans by score range
        - closed-loop tracking metrics
        - cadence and recurrence plan

  output:
    format: "nps-cycle.yaml"
    path: "workspace/businesses/{business}/analytics/customer-success/{product}/nps-cycle-{stage}.yaml"
    sections:
      - survey_metadata (type, product, journey stage)
      - touchpoint (trigger moment, timing, delivery channel)
      - questions (main, followup, optional contextual)
      - benchmarks (industry, targets, response rate goals)
      - action_plans (promoters, passives, detractors with SLAs)
      - closed_loop (tracking metrics, follow-up requirements)
      - cadence (frequency, recurrence, exclusion rules)

  acceptance_criteria:
    - "Survey type matched to journey stage with rationale"
    - "Max 3 questions, completion time < 60 seconds"
    - "Benchmarks set with industry reference and product-specific target"
    - "Action plan defined for all score ranges (promoters/passives/detractors)"
    - "Detractor closed-loop process with SLA per CS motion tier"
    - "Output saved to workspace/ as valid YAML"

  veto_conditions:
    - "Survey with > 3 questions → CORTAR extras (survey fatigue)"
    - "No action plan for detractors → BLOQUEAR (closed-loop is mandatory)"
    - "Detractor SLA not differentiated by motion tier → REDO step 5"
    - "Benchmarks without industry reference → BLOQUEAR (no baseline = no insight)"
    - "Survey at post-churn stage without recovery path → REDO step 5"

  action_items:
    - "Load product and journey context"
    - "Select survey type and touchpoint"
    - "Design survey questions (max 3)"
    - "Set benchmarks and targets"
    - "Create action plans by score range"
    - "Generate nps-cycle.yaml to workspace/"
    - "Hand off to cs-chief for deployment planning"
