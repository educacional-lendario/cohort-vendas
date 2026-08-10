# Task: Delete Customer Success Squad

**Task ID:** delete-cs-squad
**Executor:** cs-chief
**Duration:** 2-5 min
**Elicit:** true

## Purpose

Safely remove the Customer Success squad from the workspace, archiving artifacts and updating the registry.

task:
  name: "Delete CS Squad"
  status: ready
  responsible_executor: cs-chief
  execution_type: hybrid
  elicit: true

## Input

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `confirmation` | string | Yes | Must type "DELETE customer-success" to confirm |
| `--force` | flag | No | Skip interactive confirmations |
| `--archive` | flag | No | Archive to .aiox/archive/ before deletion (default: true) |

## Steps

```
1. CONFIRM INTENT
   → Elicit: "You are about to DELETE the entire customer-success squad."
     "This will remove all agents, tasks, workflows, templates, and configs."
     "Type 'DELETE customer-success' to confirm."
   → Se confirmation != "DELETE customer-success": ABORT

2. LIST DEPENDENCIES
   - Check if other squads reference customer-success agents
   - Check if workflows reference customer-success tasks
   - Check if .aiox-core references customer-success
   - Check if workspace/businesses/{business}/analytics/customer-success/ contains generated artifacts
   → Se dependencies found:
     → Elicit: "Found dependencies:"
       - List each dependency
       "Proceed anyway? These references will break."
       1. Proceed (will leave broken references)
       2. Cancel

3. ARCHIVE (unless --archive=false)
   - Create .aiox/archive/customer-success-{date}/
   - Copy entire squads/customer-success/ directory
   - Record archive manifest:
     - version: current config.yaml version
     - date: current timestamp
     - files: complete file list
     - reason: "User-requested deletion"

4. REMOVE
   - Delete squads/customer-success/ directory
   - Remove customer-success entry from squad registry (if exists)
   - Remove customer-success from any workspace indexes

5. UPDATE REGISTRY
   - Update .aiox-core squad listings
   - Remove slash_prefix "CustomerSuccess" from command registry
   - Log deletion event

6. REPORT
   - Confirm deletion complete
   - Show archive location (if archived)
   - List any broken references that need manual cleanup
   - Note: workspace CS analytics data is NOT deleted (preserved for reference)
```

## Output

| Field | Type | Description |
|-------|------|-------------|
| `deletion_report` | object | Summary of deletion |
| `archive_path` | string | Path to archived squad (if archived) |
| `broken_references` | list | References that need manual cleanup |

## Acceptance Criteria

- Confirmation string matches exactly "DELETE customer-success"
- Archive created before deletion (unless explicitly skipped)
- All squad files removed from squads/customer-success/
- Registry updated to remove squad references
- Broken references listed for manual cleanup

## Veto Conditions

- **VETO se confirmação não corresponde** - safety check
- **VETO se squad não encontrado** - nada para deletar
- **VETO se archive falha** - sem safety net para rollback
- **VETO se workspace CS data seria deletado** - workspace analytics data é preservado sempre

## Action Items

- Confirm user intent with explicit confirmation string
- Check and list all dependencies
- Archive squad before deletion
- Remove squad directory and registry entries
- Report results with broken references

## Handoff

| Para | Quando | Contexto |
|------|--------|----------|
| Nenhum | Task é self-contained | - |
