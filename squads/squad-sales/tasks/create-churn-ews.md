# Task: Create Early Warning System
# ID: CS-TP-004
# Executor: cs-chief
# Trigger: *create-ews command

task:
  name: "Create Churn Early Warning System"
  status: ready
  responsible_executor: cs-chief
  execution_type: agent
  elicit: false

  description: |
    Create an Early Warning System (EWS) for churn prevention. Defines
    severity levels (red/yellow/green), behavioral triggers, response
    playbooks with specific actions, and SLAs per severity. Inputs include
    product context and CS motion tier to calibrate trigger sensitivity.

  input:
    - name: product_name
      type: string
      required: true
      description: "Product to create EWS for"
    - name: cs_motion_tier
      type: string
      required: true
      description: "CS motion tier: digital | light-touch | mid-touch | white-glove"
    - "workspace/businesses/{business}/products/{product}/ — product data, proof"
    - "workspace/businesses/{business}/analytics/customer-success/{product}/health-score.yaml — health score model (if exists)"
    - "workspace/businesses/{business}/products/{product}/onboarding-flow.yaml — onboarding flow (if exists)"

  steps:
    - id: "1"
      name: "Load context and dependencies"
      action: |
        1. Read product data from workspace
        2. Load health-score.yaml if exists (use thresholds as EWS input)
        3. Load onboarding-flow.yaml if exists (use milestones as trigger points)
        4. Determine trigger sensitivity based on CS motion tier:
           - Digital: automated triggers only, high volume tolerance
           - Light-touch: automated + periodic manual review
           - Mid-touch: tighter thresholds, CSM-level alerts
           - White-glove: tightest thresholds, immediate escalation

    - id: "2"
      name: "Define severity levels"
      action: |
        GREEN (healthy):
        - All health score components >= 70
        - On track with onboarding milestones
        - Positive or neutral sentiment
        - Action: standard monitoring cadence

        YELLOW (at-risk):
        - 1-2 health score components 40-69
        - Onboarding milestone delayed by 1 phase
        - Declining engagement trend (2+ consecutive drops)
        - Action: proactive outreach within SLA

        RED (critical):
        - Any health score component < 40
        - Onboarding stalled (no milestone hit in 2+ phases)
        - Negative sentiment or support escalation
        - Explicit churn signals (cancellation request, competitor mention)
        - Action: immediate intervention within SLA

    - id: "3"
      name: "Map behavioral triggers"
      action: |
        For each severity level, define specific triggers:

        ENGAGEMENT TRIGGERS:
        - Login gap: Yellow (7d no login), Red (14d no login)
        - Usage decline: Yellow (50% drop week-over-week), Red (80% drop)
        - Session duration: Yellow (avg < 5min), Red (avg < 1min)

        MILESTONE TRIGGERS:
        - Onboarding delay: Yellow (1 phase behind), Red (2+ phases behind)
        - First win not achieved: Yellow (2x target time), Red (3x target time)
        - Feature adoption stall: Yellow (< 30% features), Red (< 10% features)

        SENTIMENT TRIGGERS:
        - NPS: Yellow (score 6-7), Red (score 0-5)
        - Support tickets: Yellow (3+ in 30d), Red (5+ in 30d or escalation)
        - Community: Yellow (no posts in 30d), Red (negative posts)

        COMMERCIAL TRIGGERS:
        - Payment: Yellow (late payment), Red (failed payment 2x)
        - Contract: Yellow (renewal < 60d, no engagement), Red (cancellation request)

        Adjust thresholds per CS motion tier.

    - id: "4"
      name: "Create response playbooks"
      action: |
        For each severity + trigger combination:

        1. YELLOW PLAYBOOK:
           - Automated nudge (email/notification per motion tier)
           - CSM review within SLA
           - Check-in call/message if no response in 48h
           - Document in CRM/tracking system

        2. RED PLAYBOOK:
           - Immediate CSM notification
           - Personal outreach within SLA (call for mid/white-glove)
           - Root cause analysis
           - Recovery plan with specific milestones
           - Escalation to manager if no improvement in 7d
           - Executive sponsor involvement for white-glove

        3. RECOVERY PLAYBOOK:
           - Re-onboarding fast track
           - Dedicated support window
           - Progress monitoring (daily for 2 weeks)
           - Success criteria to return to GREEN

    - id: "5"
      name: "Define SLAs per severity and motion"
      action: |
        | Severity | Digital | Light-touch | Mid-touch | White-glove |
        |----------|---------|-------------|-----------|-------------|
        | YELLOW   | 72h     | 48h         | 24h       | 12h         |
        | RED      | 48h     | 24h         | 4h        | 1h          |

        SLA = time from trigger detection to first outreach.
        Escalation if SLA breached: next level manager notification.

    - id: "6"
      name: "Generate EWS YAML"
      action: |
        Compile into structured output:
        - severity_levels with definitions
        - triggers grouped by category
        - playbooks per severity
        - sla_matrix per motion tier
        - escalation_paths
        - integration_points (health score, onboarding)

  output:
    format: "churn-ews.yaml"
    path: "workspace/businesses/{business}/analytics/customer-success/{product}/churn-ews.yaml"
    sections:
      - ews_metadata (product, motion tier, version)
      - severity_levels (green/yellow/red definitions)
      - triggers (engagement, milestone, sentiment, commercial)
      - playbooks (yellow, red, recovery)
      - sla_matrix (per severity x motion tier)
      - escalation_paths (per level)
      - dependencies (health score, onboarding flow)

  acceptance_criteria:
    - "3 severity levels defined with clear boundaries"
    - "At least 3 trigger categories with specific thresholds"
    - "Response playbook for each severity level"
    - "SLAs defined per severity x CS motion tier"
    - "Escalation path defined for SLA breaches"
    - "Thresholds calibrated to CS motion tier (not one-size-fits-all)"
    - "Output saved to workspace/ as valid YAML"

  veto_conditions:
    - "Triggers without specific numeric thresholds → REDO step 3 (vague triggers are useless)"
    - "Playbook without named action owner (CSM/manager/system) → BLOQUEAR"
    - "SLAs identical across all motion tiers → REDO step 5 (must differentiate)"
    - "RED severity without escalation path → BLOQUEAR (critical gap)"
    - "EWS designed without reading product context → BLOQUEAR (No Invention)"

  action_items:
    - "Load product context and existing CS outputs"
    - "Define severity levels calibrated to motion tier"
    - "Map behavioral triggers with numeric thresholds"
    - "Create response playbooks per severity"
    - "Define SLA matrix"
    - "Generate churn-ews.yaml to workspace/"
    - "Hand off to cs-chief for integration with health score"
