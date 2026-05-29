# CIO DataHub n8n Workflows

n8n workflow definitions and supporting data for the CIO DataHub SRE team.

## Structure

```
workflows/    — n8n workflow JSON exports (push to prod via n8n_client.py)
data/         — Reference data (DAG support lists, CSV lookups)
```

## Active Workflows

| Workflow | ID | Description |
|----------|----|-------------|
| Datahub-Composer-Dags-Enrichment | iumcttnrUl3Rq6PH | Receives PagerDuty webhook, validates DAG support status, enriches incident context |

## Workflow IDs (prod)

- n8n prod: `https://n8n.ai.telus.com`
- Workflow: `iumcttnrUl3Rq6PH`

## Deploying

```bash
PYTHON=~/.claude/skills/.venv/bin/python3
N8N="python3 ~/.claude/skills/n8n/scripts/n8n_client.py"

# Push to prod
$N8N --env prod push workflows/Datahub-Composer-Dags-Enrichment.json --id iumcttnrUl3Rq6PH
```

## Data Tables

| Table | ID | Description |
|-------|----|-------------|
| SRE_Supported_Composer_Dags | dvMXwohR5lwZAx3g | DAG support list used by the enrichment workflow |
