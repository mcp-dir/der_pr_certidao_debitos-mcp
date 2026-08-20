---
name: der_pr_certidao_debitos-mcp
description: Skill da REST API do DER PR: Certidão Negativa de Débitos (por placa) na MCP.AI: 1 endpoint em /api/der_pr_certidao_debitos. DER PR: Certidão Negativa de Débitos (por placa), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DER PR: Certidão Negativa de Débitos (por placa) — REST API skill

Você tem acesso à **DER PR: Certidão Negativa de Débitos (por placa)** REST API na MCP.AI.

> DER PR: Certidão Negativa de Débitos (por placa), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/der_pr_certidao_debitos
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
curl -X POST https://api.mcp.ai/api/der_pr_certidao_debitos/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"placa":"...","endereco":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/der_pr_certidao_debitos/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `der_pr_certidao_debitos_consultar`

DER PR: Certidão Negativa de Débitos (por placa), consulta em fonte oficial. _(POST /api/der_pr_certidao_debitos/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `placa` | string | Sim | Parâmetro de consulta "placa". |
| `endereco` | string | Sim | Parâmetro de consulta "endereco". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_der_pr_certidao_debitos` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
