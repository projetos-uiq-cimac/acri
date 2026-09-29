# {{Nome oficial da plataforma}} — API

{{1–2 frases: o que a API permite fazer. Ex.: "Permite consultar os indicadores de procura turística dos municípios do Alentejo Central."}}

## Endereço da API

```
https://{{api.plataforma-cimac.pt}}/{{v1}}
```

## Documentação

A descrição completa dos endpoints, parâmetros, respostas e erros está na especificação OpenAPI:

- **Swagger UI:** `https://{{…}}/docs`
- **Especificação OpenAPI:** `https://{{…}}/openapi.json`

## Autenticação

A API usa **OAuth 2.0 (Client Credentials)** com tokens **JWT**.

1. Pedir um token ao endpoint `POST https://{{auth.plataforma-cimac.pt}}/{{oauth2/token}}` com o `client_id` e o `client_secret`.
2. Enviar o token em todos os pedidos, no cabeçalho `Authorization: Bearer <token>`.
3. O token é válido durante {{3600}} segundos. Quando expirar, peça um novo.

## Como obter as credenciais

O acesso à API é livre, mas requer registo junto da CIMAC.

1. Envie um email para projetos.uqi@cimac.pt com:
   - nome da entidade ou do requerente;
   - contacto técnico;
   - finalidade da utilização (opcional).
2. A CIMAC envia o `client_id` e o `client_secret` para o contacto indicado.

> O `client_secret` é confidencial. Não o publique em repositórios nem o inclua em código executado no browser ou em aplicações móveis.

## Como obter e utilizar o token

**1. Obter o token**

```bash
curl -X POST "https://{{auth.plataforma-cimac.pt}}/{{oauth2/token}}" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "grant_type=client_credentials" \
  -d "client_id=$CLIENT_ID" \
  -d "client_secret=$CLIENT_SECRET"
```

```json
{
  "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9...",
  "token_type": "Bearer",
  "expires_in": 3600
}
```

**2. Utilizar o token num pedido**

```bash
curl "https://{{api.plataforma-cimac.pt}}/{{v1}}/{{recurso}}" \
  -H "Authorization: Bearer $ACCESS_TOKEN"
```

## Contacto

Questões técnicas: {{email}}
