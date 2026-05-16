# Variáveis de Ambiente

# Objetivo

Centralizar variáveis utilizadas nos testes da API.

---

# Variáveis

| Variável      | Valor Exemplo                           | Descrição                     |
|----------------|------------------------------------------|--------------------------------|
| BASE_URL       | https://restful-booker.herokuapp.com     | URL base da API               |
| USERNAME       | admin                                    | Usuário de autenticação       |
| PASSWORD       | password123                              | Senha de autenticação         |
| TOKEN          | {{token}}                                | Token gerado dinamicamente    |
| BOOKING_ID     | {{bookingid}}                            | ID da reserva criada          |
| CONTENT_TYPE   | application/json                         | Header padrão                 |

---

# Exemplo de Ambiente para Postman

```json
{
  "id": "restful-booker-env",
  "name": "Restful Booker Environment",
  "values": [
    {
      "key": "BASE_URL",
      "value": "https://restful-booker.herokuapp.com",
      "enabled": true
    },
    {
      "key": "USERNAME",
      "value": "admin",
      "enabled": true
    },
    {
      "key": "PASSWORD",
      "value": "password123",
      "enabled": true
    },
    {
      "key": "TOKEN",
      "value": "",
      "enabled": true
    },
    {
      "key": "BOOKING_ID",
      "value": "",
      "enabled": true
    }
  ]
}
```

---

# Fluxo de Utilização

1. Executar autenticação
2. Salvar token na variável `TOKEN`
3. Criar reserva
4. Salvar ID na variável `BOOKING_ID`
5. Utilizar variáveis nos endpoints `PUT`, `PATCH` e `DELETE`

---

# Headers Padrão

## JSON

```http
Content-Type: application/json
```

## Autenticação

```http
Cookie: token={{TOKEN}}
```