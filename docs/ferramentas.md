# Ferramentas

EVO Academia expõe 20 ferramentas.

### 1. `evo_list_accounts`
**Input**: `account` (opcional)

List all EVO gyms/branches linked to this install.

### 2. `evo_configuration`
**Input**: `id_branch` (opcional), `account` (opcional)

Get the gym/branch configuration (name, timezone, gateway, occupation, card flags).

### 3. `evo_member_list`
**Input**: `member_ids` (opcional), `name` (opcional), `email` (opcional), `document` (opcional), `status` (opcional), `take` (opcional), `skip` (opcional), `account` (opcional)

Read gym members. Actions: list — search/paginate members (filter by name/email/document/status) get — fetch one or more members by id (member_ids) [Flattened action: list]

### 4. `evo_member_get`
**Input**: `member_ids` (opcional), `name` (opcional), `email` (opcional), `document` (opcional), `status` (opcional), `take` (opcional), `skip` (opcional), `account` (opcional)

Read gym members. Actions: list — search/paginate members (filter by name/email/document/status) get — fetch one or more members by id (member_ids) [Flattened action: get]

### 5. `evo_get_member_count`
**Input**: `account` (opcional)

Count of active members (drives the billing tier).

### 6. `evo_membership`
**Input**: `id_branch` (opcional), `account` (opcional)

List membership plans (planos) offered by the gym.

### 7. `evo_entries`
**Input**: `member_id` (opcional), `start_date` (opcional), `end_date` (opcional), `take` (opcional), `skip` (opcional), `account` (opcional), `member_ids` (opcional)

List gym entries (check-ins / turnstile access), optionally by member and date range.

### 8. `evo_receivables`
**Input**: `start_date` (opcional), `end_date` (opcional), `member_id` (opcional), `take` (opcional), `skip` (opcional), `account` (opcional), `member_ids` (opcional)

List receivables (contas a receber).

### 9. `evo_receivables_mark_received`
**Input**: `data`, `account` (opcional)

Mark a receivable as received/paid.

### 10. `evo_sales`
**Input**: `start_date` (opcional), `end_date` (opcional), `take` (opcional), `skip` (opcional), `account` (opcional)

List sales (vendas) over a date range.

### 11. `evo_sales_create`
**Input**: `data`, `account` (opcional)

Create a sale (e.g. sell a membership/plan to a member). PROBE: confirm body shape.

### 12. `evo_prospect`
**Input**: `name` (opcional), `email` (opcional), `start_date` (opcional), `end_date` (opcional), `take` (opcional), `skip` (opcional), `account` (opcional)

List prospects/leads (CRM).

### 13. `evo_prospect_write_create`
**Input**: `id_prospect` (opcional), `name` (opcional), `email` (opcional), `phone` (opcional), `id_branch` (opcional), `data` (opcional), `account` (opcional)

Create or update a prospect/lead.

### 14. `evo_prospect_write_update`
**Input**: `id_prospect` (opcional), `name` (opcional), `email` (opcional), `phone` (opcional), `id_branch` (opcional), `data` (opcional), `account` (opcional)

Create or update a prospect/lead.

### 15. `evo_activity_list`
**Input**: `date` (opcional), `id_branch` (opcional), `account` (opcional)

Read group activities/classes (turmas).

### 16. `evo_activity_schedule`
**Input**: `date` (opcional), `id_branch` (opcional), `account` (opcional)

Read group activities/classes (turmas).

### 17. `evo_activity_write_enroll`
**Input**: `data`, `account` (opcional)

Enroll a member in a class or change an enrollment status.

### 18. `evo_activity_write_change_status`
**Input**: `data`, `account` (opcional)

Enroll a member in a class or change an enrollment status.

### 19. `evo_employees`
**Input**: `name` (opcional), `email` (opcional), `take` (opcional), `skip` (opcional), `account` (opcional)

List gym employees/staff.

### 20. `evo_bank_accounts`
**Input**: `id_branch` (opcional), `account` (opcional)

List the gym's bank accounts.

## Prompts de exemplo

```
Quantos alunos ativos tenho e quais contas a receber estão em atraso?
Liste os check-ins de hoje e as turmas com vagas disponíveis
Mostre as vendas do mês e os prospects novos para follow-up
```
