# Task: Update Customer Success Squad

**Task ID:** update-cs-squad
**Executor:** cs-chief
**Duration:** 10-30 min
**Elicit:** true

## Purpose

Update the Customer Success squad: add/modify agents, update configs, refresh DNA, adjust workflows, update task definitions.

## Input

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `update_request` | string | Yes | Description of the update to apply |
| `--agents` | flag | No | Update agent definitions |
| `--config` | flag | No | Update config.yaml |
| `--tasks` | flag | No | Update task definitions |
| `--workflows` | flag | No | Update workflows |
| `--templates` | flag | No | Update templates |

If no flags provided, scope is determined from `update_request`.

task:
  name: "Update CS Squad"
  status: ready
  responsible_executor: cs-chief
  execution_type: hybrid
  elicit: true

## Steps

```
1. IDENTIFY CHANGES
   - Parse update_request
   - Determine affected components (agents, config, tasks, workflows, templates)
   → Elicit: "Confirm scope of changes:"
     - List affected files
     - Estimated impact

2. VALIDATE CURRENT STATE
   - Read squads/customer-success/config.yaml
   - Verify target files exist
   - Check version compatibility
   → Se inconsistency found: WARN and elicit confirmation

3. BACKUP CURRENT STATE
   - Record current config.yaml version
   - Document current state of affected files

4. APPLY UPDATES
   IF --agents:
     → Read target agent .md file(s)
     → Apply modifications inside ```yaml block
     → Preserve existing content outside YAML block

   IF --config:
     → Update config.yaml fields
     → Bump version (patch for minor, minor for features)

   IF --tasks:
     → Update task definitions
     → Validate against CS-TP-001 task anatomy (8 required fields)
     → Register in config.yaml if new task

   IF --workflows:
     → Update workflow definitions
     → Validate phase references

   IF --templates:
     → Update template files
     → Verify template variables match task inputs

5. VALIDATE CONFIG
   - Verify config.yaml YAML syntax
   - Verify all agent IDs referenced in tasks exist
   - Verify all agent IDs referenced in workflows exist
   - Verify task anatomy compliance (8 required fields)
   → Se validation FAIL: rollback and report

6. SMOKE TEST
   - Verify all referenced agent files exist in agents/
   - Verify all referenced task files exist in tasks/
   - Verify stats section matches actual counts
   - Report any discrepancies

7. FINALIZE
   - Update config.yaml version
   - Report summary of changes applied
```

## Output

| Field | Type | Description |
|-------|------|-------------|
| `updated_artifacts` | list | Files that were modified |
| `version` | string | New config version |
| `validation_result` | string | PASS or FAIL with details |

## Acceptance Criteria

- All modified files pass YAML syntax validation
- Config version bumped appropriately
- All cross-references (agent IDs in tasks/workflows) valid
- Task anatomy compliance verified for any new/modified tasks

## Veto Conditions

- **VETO se config.yaml não encontrado** - squad não inicializado
- **VETO se YAML syntax inválido após update** - rollback automático
- **VETO se agent ID referenciado não existe** - referência quebrada
- **VETO se task sem 8 campos obrigatórios** - CS-TP-001 violation
- **VETO se versão não bumped** - rastreabilidade perdida

## Action Items

- Parse update request and identify scope
- Validate current state
- Apply updates with validation
- Smoke test cross-references
- Bump version and finalize

## Handoff

| Para | Quando | Contexto |
|------|--------|----------|
| @dev | Commit das mudanças | `{updated_artifacts[], version}` |
| @qa | Validação pós-update | `{validation_result}` |
