# Collection de Requests - Restful Booker API

## Base URL

```http
https://restful-booker.herokuapp.com
```

---

# 1. Health Check

## Endpoint

```http
GET /ping
```

## Objetivo

Verificar se a API está disponível.

## Request

```http
GET /ping
```

## Exemplo usando cURL

```bash
curl -X GET "https://restful-booker.herokuapp.com/ping"
```

## Resultado Esperado

```http
201 Created
```

---

# 2. Autenticação

## Endpoint

```http
POST /auth
```

## Objetivo

Gerar token de autenticação para operações protegidas.

## Request

```http
POST /auth
Content-Type: application/json
```

## Body

```json
{
  "username": "admin",
  "password": "password123"
}
```

## Exemplo usando cURL

```bash
curl -X POST "https://restful-booker.herokuapp.com/auth" \
-H "Content-Type: application/json" \
-d '{
  "username": "admin",
  "password": "password123"
}'
```

## Resultado Esperado

```json
{
  "token": "abc123xyz"
}
```

---

# 3. Criar Reserva

## Endpoint

```http
POST /booking
```

## Objetivo

Criar uma nova reserva.

## Request

```http
POST /booking
Content-Type: application/json
```

## Body

```json
{
  "firstname": "Joao",
  "lastname": "Silva",
  "totalprice": 500,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-05-20",
    "checkout": "2026-05-25"
  },
  "additionalneeds": "Breakfast"
}
```

## Exemplo usando cURL

```bash
curl -X POST "https://restful-booker.herokuapp.com/booking" \
-H "Content-Type: application/json" \
-d '{
  "firstname": "Joao",
  "lastname": "Silva",
  "totalprice": 500,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-05-20",
    "checkout": "2026-05-25"
  },
  "additionalneeds": "Breakfast"
}'
```

## Resultado Esperado

```json
{
  "bookingid": 1,
  "booking": {
    "firstname": "Joao",
    "lastname": "Silva",
    "totalprice": 500,
    "depositpaid": true,
    "bookingdates": {
      "checkin": "2026-05-20",
      "checkout": "2026-05-25"
    },
    "additionalneeds": "Breakfast"
  }
}
```

---

# 4. Buscar Todas as Reservas

## Endpoint

```http
GET /booking
```

## Objetivo

Listar reservas existentes.

## Request

```http
GET /booking
```

## Exemplo usando cURL

```bash
curl -X GET "https://restful-booker.herokuapp.com/booking"
```

## Resultado Esperado

```json
[
  {
    "bookingid": 1
  },
  {
    "bookingid": 2
  }
]
```

---

# 5. Buscar Reserva por ID

## Endpoint

```http
GET /booking/{id}
```

## Objetivo

Buscar detalhes de uma reserva específica.

## Request

```http
GET /booking/1
```

## Exemplo usando cURL

```bash
curl -X GET "https://restful-booker.herokuapp.com/booking/1"
```

## Resultado Esperado

```json
{
  "firstname": "Joao",
  "lastname": "Silva",
  "totalprice": 500,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-05-20",
    "checkout": "2026-05-25"
  },
  "additionalneeds": "Breakfast"
}
```

---

# 6. Atualizar Reserva Completa

## Endpoint

```http
PUT /booking/{id}
```

## Objetivo

Atualizar completamente uma reserva.

## Headers

```http
Cookie: token=SEU_TOKEN
Content-Type: application/json
```

## Request

```http
PUT /booking/1
```

## Body

```json
{
  "firstname": "Maria",
  "lastname": "Souza",
  "totalprice": 800,
  "depositpaid": false,
  "bookingdates": {
    "checkin": "2026-06-01",
    "checkout": "2026-06-10"
  },
  "additionalneeds": "Lunch"
}
```

## Exemplo usando cURL

```bash
curl -X PUT "https://restful-booker.herokuapp.com/booking/1" \
-H "Content-Type: application/json" \
-H "Cookie: token=SEU_TOKEN" \
-d '{
  "firstname": "Maria",
  "lastname": "Souza",
  "totalprice": 800,
  "depositpaid": false,
  "bookingdates": {
    "checkin": "2026-06-01",
    "checkout": "2026-06-10"
  },
  "additionalneeds": "Lunch"
}'
```

---

# 7. Atualização Parcial

## Endpoint

```http
PATCH /booking/{id}
```

## Objetivo

Atualizar parcialmente uma reserva.

## Request

```http
PATCH /booking/1
```

## Headers

```http
Cookie: token=SEU_TOKEN
Content-Type: application/json
```

## Body

```json
{
  "firstname": "Carlos",
  "totalprice": 1000
}
```

## Exemplo usando cURL

```bash
curl -X PATCH "https://restful-booker.herokuapp.com/booking/1" \
-H "Content-Type: application/json" \
-H "Cookie: token=SEU_TOKEN" \
-d '{
  "firstname": "Carlos",
  "totalprice": 1000
}'
```

---

# 8. Deletar Reserva

## Endpoint

```http
DELETE /booking/{id}
```

## Objetivo

Excluir uma reserva.

## Request

```http
DELETE /booking/1
```

## Headers

```http
Cookie: token=SEU_TOKEN
```

## Exemplo usando cURL

```bash
curl -X DELETE "https://restful-booker.herokuapp.com/booking/1" \
-H "Cookie: token=SEU_TOKEN"
```

## Resultado Esperado

```http
201 Created
```

---

# 9. Filtros e Buscas

## Buscar reservas por nome

### Endpoint

```http
GET /booking?firstname=Joao
```

### Exemplo usando cURL

```bash
curl -X GET "https://restful-booker.herokuapp.com/booking?firstname=Joao"
```

---

## Buscar reservas por sobrenome

### Endpoint

```http
GET /booking?lastname=Silva
```

---

## Buscar reservas por período

### Endpoint

```http
GET /booking?checkin=2026-05-20&checkout=2026-05-25
```

---

# 10. Validação de Campos Obrigatórios

## Cenário: firstname vazio

### Request

```json
{
  "firstname": "",
  "lastname": "Silva"
}
```

### Resultado Esperado

- API deve retornar erro de validação
- Não deve criar reserva

---

## Cenário: ausência de bookingdates

### Request

```json
{
  "firstname": "Joao",
  "lastname": "Silva"
}
```

### Resultado Esperado

- API deve rejeitar request
- Deve retornar erro 400 ou equivalente

---

# 11. Tratamento de Erros

## Token inválido

### Resultado Esperado

```http
403 Forbidden
```

---

## Booking inexistente

### Resultado Esperado

```http
404 Not Found
```

---

## Body inválido

### Resultado Esperado

```http
400 Bad Request
```