# EVO Academia

### EVO Academia para Claude, ChatGPT e agentes de IA

Gestão de academia (ABC Evo / W12): alunos, planos, vendas, contas a receber, check-ins, turmas e CRM de prospects.

- 📊 **20 ferramentas**
- ✏️ **Leitura e escrita**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `EVO Academia` e **URL** `https://api.mcp.ai/p_evo`.

### Cursor

[➕ Instalar EVO Academia no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=evo&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9ldm8ifQ==)

### VS Code (Copilot Chat)

[➕ Instalar EVO Academia no VS Code](vscode:mcp/install?name=evo&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_evo%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_evo
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Quantos alunos ativos tenho e quais contas a receber estão em atraso?
Liste os check-ins de hoje e as turmas com vagas disponíveis
Mostre as vendas do mês e os prospects novos para follow-up
```

---

## 20 ferramentas disponíveis

| Tool | Descrição |
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

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_evo`.


---

## Suporte

- 📧 [evo@mcp.ai](mailto:evo@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/evo-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_evo` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
