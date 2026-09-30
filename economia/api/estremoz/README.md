


# Plataforma de Indicadores Económicos e Empresariais de Estremoz — API

Permite consultar os indicadores económicos e empresariais do município de Estremoz incluindo o número de empresas ativas por setor de atividade, a distribuição de empresas por dimensão e as organizações instaladas no território.

## URL

```
https://api.economia-cimac.pt/estremoz
```

## Documentação

A descrição completa dos endpoints, parâmetros, respostas e erros está na especificação em:

- **Swagger UI:** https://api.economia-cimac.pt/estremoz/docs
- **Especificação OpenAPI:** https://api.economia-cimac.pt/estremoz/openapi.json

## Autenticação

A API usa **OAuth 2.0 (Client Credentials)** com tokens **JWT**.

1. Peça um token ao endpoint `POST https://api.economia-cimac.pt/integrations/token`, por exemplo: 
   
   ```bash
   curl -X POST 'https://api.economia-cimac.pt/integrations/token' \
        --header 'Content-Type: application/x-www-form-urlencoded' \
        --data-urlencode 'grant_type=client_credentials' \
        --data-urlencode 'client_id=<o seu client_id>' \
        --data-urlencode 'client_secret=<o seu client_secret>'
   ```
2. Envie o token no cabeçalho (header) dos pedidos, por exemplo:

   ```bash
   curl -X GET 'https://api.economia-cimac.pt/estremoz/v1/datasets/guests-monthly?format=ngsi-ld' \
        --header 'Authorization: Bearer <o seu token>'
   ```
3. O token é válido durante 900 segundos. Quando expirar, peça um novo.

## Como obter as credenciais

O acesso à API é livre, mas requer um pedido de registo junto da CIMAC para obtenção do `client_id` e do `client_secret`:

1. Envie um email para <projetos.uiq@cimac.pt> com:
   - A indicação da API que quer utilizar;
   - Nome da entidade ou do requerente;
   - Contactos;
   - Finalidade da utilização (opcional).
2. A CIMAC fará o registo e enviará o `client_id` e o `client_secret` para os contactos disponibilizados.

> O `client_secret` é confidencial. Não o publique em repositórios nem o inclua em código executado no browser ou em aplicações móveis.

## Contacto

Questões técnicas: <projetos.uiq@cimac.pt>
