# {{Nome oficial da plataforma}} — API

{{1–2 frases: o que a API permite fazer. Ex.: "Permite consultar os indicadores de procura turística dos municípios do Alentejo Central."}}

## URL

```
https://{{api.plataforma-cimac.pt}}/{{v1}}
```

## Documentação

A descrição completa dos endpoints, parâmetros, respostas e erros está na especificação em:

- **Swagger UI:** `https://{{…}}/docs`
- **Especificação OpenAPI:** `https://{{…}}/openapi.json`

## Autenticação

A API usa **OAuth 2.0 (Client Credentials)** com tokens **JWT**.

1. Pedir um token ao endpoint `POST https://{{auth.plataforma-cimac.pt}}/{{oauth2/token}}` com o `client_id` e o `client_secret` (ver a secção **Como obter as credenciais**).
2. Enviar o token em todos os pedidos, no cabeçalho `Authorization: Bearer <token>`.
3. O token é válido durante {{3600}} segundos. Quando expirar, peça um novo.

## Como obter as credenciais

O acesso à API é livre, mas requer um pedido de registo junto da CIMAC para obtenção do `client_id` e do `client_secret`:

1. Envie um email para projetos.uiq@cimac.pt com:
   - A indicação da API que quer utilizar;
   - Nome da entidade ou do requerente;
   - Contactos;
   - Finalidade da utilização (opcional).
2. A CIMAC fará o registo e enviará o `client_id` e o `client_secret` para os contactos disponibilizados.

> O `client_secret` é confidencial. Não o publique em repositórios nem o inclua em código executado no browser ou em aplicações móveis.

## Contacto

Questões técnicas: projetos.uiq@cimac.pt
