# Task: Design Onboarding Flow
# ID: CS-TP-002
# Executor: cs-chief (delegates to @nick-mehta for framework)
# Trigger: *design-onboarding command

task:
  name: "Design Onboarding Flow"
  status: ready
  responsible_executor: cs-chief
  execution_type: hybrid
  elicit: true

  description: |
    Design a structured onboarding flow for a specific product. Reads existing
    workspace data (product, ICP, curriculum) to ground the design in real
    product context. Outputs an onboarding-flow.yaml with phases, milestones,
    first win definition, and re-engagement triggers.

  input:
    - name: product_name
      type: string
      required: true
      description: "Product to design onboarding for (e.g., cohort_advanced)"
    - name: ticket_value
      type: string
      required: true
      description: "Ticket value to determine CS motion tier (digital/light/mid/white-glove)"
    - name: icp_profile
      type: string
      required: false
      description: "ICP name if different from product-level ICP"
    - "workspace/businesses/{business}/products/{product}/ — product data"
    - "workspace/businesses/{business}/company/icp.yaml — company-level ICP"
    - "workspace/_templates/customer-success/ — onboarding templates"

  elicitation_points:
    - point: "product_confirmation"
      when: "Step 1 complete"
      ask: |
        Produto: {product_name}
        Ticket: {ticket_value} → CS Motion: {motion_tier}
        ICP: {icp_name}
        Dados encontrados: {file_count} arquivos

        Confirma? Algum dado adicional sobre o onboarding atual?

    - point: "first_win_definition"
      when: "Step 3 complete"
      ask: |
        Proposta de First Win:
        - Ação: {first_win_action}
        - Tempo alvo: {time_to_first_win}
        - Métrica: {first_win_metric}

        Isso reflete o momento "aha" real do produto?

  steps:
    - id: "1"
      name: "Load product context"
      action: |
        1. Read workspace/businesses/{business}/products/{product}/
           - curriculum.yaml (what they learn/use)
           - icp.yaml (who they are, pain points)
           - proof.yaml (what success looks like)
           - testimonials.yaml (real language, real outcomes)
        2. Read existing onboarding data if any
        3. Determine CS motion tier from ticket value:
           - Digital: < R$500
           - Light-touch: R$500-R$8K
           - Mid-touch: R$8K-R$50K
           - White-glove: > R$50K
        → Elicit: product_confirmation

    - id: "2"
      name: "Map onboarding phases"
      action: |
        Design 3-5 phases based on product structure:

        Phase 1: ACTIVATION (Day 0-3)
        - Welcome touchpoint (email/message/call per motion tier)
        - Access setup and environment check
        - Orientation to key resources

        Phase 2: FIRST WIN (Day 3-14)
        - Guided path to first meaningful outcome
        - Milestone: first win achieved
        - Celebration touchpoint

        Phase 3: HABIT FORMATION (Day 14-30)
        - Regular usage pattern established
        - Community integration (if applicable)
        - Progress checkpoint

        Phase 4: PROFICIENCY (Day 30-60)
        - Advanced features introduced
        - Independent usage confirmed
        - NPS/CSAT touchpoint

        Phase 5: ADVOCACY (Day 60+)
        - Expansion signal detection
        - Referral/testimonial opportunity
        - Renewal preparation

    - id: "3"
      name: "Define first win and milestones"
      action: |
        1. Analyze proof.yaml and testimonials.yaml for real outcomes
        2. Identify the earliest meaningful result (first win)
        3. Define time-to-first-win target
        4. Create milestone checklist for each phase
        5. Map milestones to measurable signals
        → Elicit: first_win_definition

    - id: "4"
      name: "Design re-engagement triggers"
      action: |
        Define triggers for students who fall off track:

        1. YELLOW triggers (risk signals):
           - No login in X days (per phase)
           - Milestone not hit by deadline
           - Low engagement score
           → Action: automated nudge + CSM alert

        2. RED triggers (churn risk):
           - No activity in 2X days
           - Multiple milestones missed
           - Negative sentiment detected
           → Action: personal outreach + escalation

        3. Recovery playbook per trigger type

    - id: "5"
      name: "Generate onboarding-flow.yaml"
      action: |
        Compile all phases, milestones, triggers into structured YAML:
        - phases[] with timeline, touchpoints, milestones
        - first_win definition with metric and target
        - re_engagement_triggers[] with conditions and actions
        - cs_motion_tier with appropriate touch frequency
        - success_criteria per phase

  output:
    format: "onboarding-flow.yaml"
    path: "workspace/businesses/{business}/products/{product}/onboarding-flow.yaml"
    sections:
      - product_context (name, ticket, ICP, motion tier)
      - phases (3-5 structured phases with timelines)
      - first_win (action, metric, time target)
      - milestones (per phase, measurable)
      - re_engagement_triggers (yellow/red with playbooks)
      - success_criteria (per phase completion rates)

  acceptance_criteria:
    - "Product context loaded from workspace (not invented)"
    - "CS motion tier correctly derived from ticket value"
    - "First win grounded in real proof/testimonial data"
    - "At least 3 onboarding phases with clear timelines"
    - "Re-engagement triggers defined with specific conditions and actions"
    - "Output is valid YAML saved to workspace/"
    - "No business-specific data inside squads/"

  veto_conditions:
    - "Onboarding designed without reading product data → BLOQUEAR (No Invention)"
    - "First win not traceable to proof or testimonial evidence → REDO step 3"
    - "No re-engagement triggers defined → BLOQUEAR (incomplete deliverable)"
    - "Phases without measurable milestones → REDO step 2"
    - "Output saved inside squads/ → BLOQUEAR (Squad Agnosticism)"

  action_items:
    - "Load product context from workspace"
    - "Design onboarding phases aligned to CS motion tier"
    - "Define first win from real product outcomes"
    - "Create re-engagement trigger system"
    - "Generate onboarding-flow.yaml to workspace/"
    - "Hand off to cs-chief for review and integration"
