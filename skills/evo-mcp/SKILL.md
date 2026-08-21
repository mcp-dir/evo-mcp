---
name: evo-mcp
description: Skill da REST API do EVO Academia na MCP.AI: 18 endpoints em /api/evo. Gestão de academia (ABC Evo / W12): alunos, planos, vendas, contas a receber, check-ins, turmas e CRM de prospects. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# EVO Academia — REST API skill

Você tem acesso à **EVO Academia** REST API na MCP.AI.

> Gestão de academia (ABC Evo / W12): alunos, planos, vendas, contas a receber, check-ins, turmas e CRM de prospects.

## Base URL

```
https://api.mcp.ai/api/evo
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/evo/activity/list \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/evo/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (18)

#### `evo_activity_list`

Read group activities/classes (turmas). _(POST /api/evo/activity/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `date` | string | Não | schedule: date (YYYY-MM-DD) |
| `id_branch` | string | Não |  |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_activity_schedule`

Read group activities/classes (turmas). _(POST /api/evo/activity/schedule)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `date` | string | Não | schedule: date (YYYY-MM-DD) |
| `id_branch` | string | Não |  |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_activity_write`

Enroll a member in a class or change an enrollment status. _(POST /api/evo/activity/write)_

#### `evo_bank_accounts`

List the gym's bank accounts. _(POST /api/evo/bank/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id_branch` | string | Não | Optional branch id |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_configuration`

Get the gym/branch configuration (name, timezone, gateway, occupation, card flags). _(POST /api/evo/configuration)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id_branch` | string | Não | Optional branch id (multi-unit gyms). |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_employees`

List gym employees/staff. _(POST /api/evo/employees)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Não |  |
| `email` | string | Não |  |
| `take` | integer | Não |  |
| `skip` | integer | Não |  |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_entries`

List gym entries (check-ins / turnstile access), optionally by member and date range. _(POST /api/evo/entries)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `member_id` | string | Não | Filter by member id |
| `start_date` | string | Não | Register date start (YYYY-MM-DD) |
| `end_date` | string | Não | Register date end (YYYY-MM-DD) |
| `take` | integer | Não |  |
| `skip` | integer | Não |  |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |
| `member_ids` | string[] | Não | Bulk mode: multiple values for member_id |

#### `evo_get_member_count`

Count of active members (drives the billing tier). _(POST /api/evo/get/member/count)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_list_accounts`

List all EVO gyms/branches linked to this install. _(POST /api/evo/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_member_get`

Read gym members. _(POST /api/evo/member/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `member_ids` | string[] | Não | get: member ids (1–50) |
| `name` | string | Não | list: filter by name |
| `email` | string | Não | list: filter by email |
| `document` | string | Não | list: filter by CPF/document |
| `status` | string | Não | list: member status filter (PROBE: confirm codes) |
| `take` | integer | Não | list: page size (max 100) |
| `skip` | integer | Não | list: offset |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_member_list`

Read gym members. _(POST /api/evo/member/list)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `member_ids` | string[] | Não | get: member ids (1–50) |
| `name` | string | Não | list: filter by name |
| `email` | string | Não | list: filter by email |
| `document` | string | Não | list: filter by CPF/document |
| `status` | string | Não | list: member status filter (PROBE: confirm codes) |
| `take` | integer | Não | list: page size (max 100) |
| `skip` | integer | Não | list: offset |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_membership`

List membership plans (planos) offered by the gym. _(POST /api/evo/membership)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id_branch` | string | Não | Optional branch id |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_prospect`

List prospects/leads (CRM). _(POST /api/evo/prospect)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Não |  |
| `email` | string | Não |  |
| `start_date` | string | Não | Registration date start (YYYY-MM-DD) |
| `end_date` | string | Não | Registration date end (YYYY-MM-DD) |
| `take` | integer | Não |  |
| `skip` | integer | Não |  |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_prospect_write`

Create or update a prospect/lead. _(POST /api/evo/prospect/write)_

#### `evo_receivables`

List receivables (contas a receber). _(POST /api/evo/receivables)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `start_date` | string | Não | Registration/due date start (YYYY-MM-DD) |
| `end_date` | string | Não | Registration/due date end (YYYY-MM-DD) |
| `member_id` | string | Não | Filter by member id |
| `take` | integer | Não |  |
| `skip` | integer | Não |  |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |
| `member_ids` | string[] | Não | Bulk mode: multiple values for member_id |

#### `evo_receivables_mark_received`

Mark a receivable as received/paid. _(POST /api/evo/receivables/mark/received)_

#### `evo_sales`

List sales (vendas) over a date range. _(POST /api/evo/sales)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `start_date` | string | Não | Sale date start (YYYY-MM-DD) |
| `end_date` | string | Não | Sale date end (YYYY-MM-DD) |
| `take` | integer | Não |  |
| `skip` | integer | Não |  |
| `account` | string | Não | Optional account selector when multiple EVO gyms/branches are linked in this install. Pass the account id, dns, or label (full or partial). Omit if only one is linked. Use evo_list_accounts to discover. |

#### `evo_sales_create`

Create a sale (e.g. sell a membership/plan to a member). PROBE: confirm body shape. _(POST /api/evo/sales/create)_

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_evo` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
