# EVO Academia

### EVO Academia for Claude, ChatGPT and AI agents

Gym management (ABC Evo / W12): members, plans, sales, receivables, check-ins, classes and prospect CRM.

- 📊 **20 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `EVO Academia`, URL `https://api.mcp.ai/p_evo`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=evo&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9ldm8ifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=evo&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_evo%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_evo
```

---

## 20 tools

| Tool | Description |
|---|---|
| `evo_list_accounts` | List all EVO gyms/branches linked to this install. |
| `evo_configuration` | Get the gym/branch configuration (name, timezone, gateway, occupation, card flags). |
| `evo_member_list` | Read gym members. Actions: list — search/paginate members (filter by name/email/document/status) get — fetch one or more members by id (member_ids) [Flattened action: list] |
| `evo_member_get` | Read gym members. Actions: list — search/paginate members (filter by name/email/document/status) get — fetch one or more members by id (member_ids) [Flattened action: get] |
| `evo_get_member_count` | Count of active members (drives the billing tier). |
| `evo_membership` | List membership plans (planos) offered by the gym. |
| `evo_entries` | List gym entries (check-ins / turnstile access), optionally by member and date range. |
| `evo_receivables` | List receivables (contas a receber). |
| `evo_receivables_mark_received` | Mark a receivable as received/paid. |
| `evo_sales` | List sales (vendas) over a date range. |
| `evo_sales_create` | Create a sale (e.g. sell a membership/plan to a member). PROBE: confirm body shape. |
| `evo_prospect` | List prospects/leads (CRM). |
| `evo_prospect_write_create` | Create or update a prospect/lead. |
| `evo_prospect_write_update` | Create or update a prospect/lead. |
| `evo_activity_list` | Read group activities/classes (turmas). |
| `evo_activity_schedule` | Read group activities/classes (turmas). |
| `evo_activity_write_enroll` | Enroll a member in a class or change an enrollment status. |
| `evo_activity_write_change_status` | Enroll a member in a class or change an enrollment status. |
| `evo_employees` | List gym employees/staff. |
| `evo_bank_accounts` | List the gym's bank accounts. |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_evo` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
