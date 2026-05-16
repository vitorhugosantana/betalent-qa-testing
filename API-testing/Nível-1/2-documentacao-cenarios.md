# Documentação dos Cenários de Teste

## Objetivo

Validar os principais fluxos da API Restful Booker:

- Fluxo de autenticação
- CRUD de reservas
- Filtros e buscas
- Tratamento de erros
- Validação de campos obrigatórios

---

# Cenários de Teste

---

# CT001 - Validar Health Check da API

## Objetivo

Garantir que a API esteja online.

## Endpoint

```http
GET /ping
```

## Resultado Esperado

```http
Status Code: 201
```

---

# CT002 - Autenticação com credenciais válidas

## Objetivo

Validar geração de token.

## Endpoint

```http
POST /auth
```

## Dados de Entrada

```json
{
  "username": "admin",
  "password": "password123"
}
```

## Resultado Esperado

- Status Code: 200
- Token retornado no body

---

# CT003 - Autenticação com senha inválida

## Objetivo

Validar tratamento de erro de login.

## Resultado Esperado

- Status Code: 200 ou 401
- Mensagem de erro apropriada

---

# CT004 - Criar reserva com dados válidos

## Objetivo

Validar criação de reserva.

## Endpoint

```http
POST /booking
```

## Resultado Esperado

- Status Code: 200
- `bookingid` gerado
- Dados persistidos corretamente

---

# CT005 - Criar reserva sem firstname

## Objetivo

Validar campo obrigatório.

## Resultado Esperado

- API deve rejeitar request
- Não deve criar reserva

---

# CT006 - Criar reserva sem lastname

## Objetivo

Validar campo obrigatório.

## Resultado Esperado

- API deve retornar erro de validação

---

# CT007 - Criar reserva sem bookingdates

## Objetivo

Validar obrigatoriedade do objeto `bookingdates`.

## Resultado Esperado

```http
Status Code: 400 ou equivalente
```

---

# CT008 - Buscar reserva existente

## Objetivo

Validar consulta de reserva por ID.

## Endpoint

```http
GET /booking/{id}
```

## Resultado Esperado

- Status Code: 200
- Dados corretos retornados

---

# CT009 - Buscar reserva inexistente

## Objetivo

Validar tratamento de booking inexistente.

## Resultado Esperado

```http
Status Code: 404
```

---

# CT010 - Atualizar reserva com token válido

## Objetivo

Validar atualização completa.

## Endpoint

```http
PUT /booking/{id}
```

## Resultado Esperado

- Status Code: 200
- Dados atualizados

---

# CT011 - Atualizar reserva sem token

## Objetivo

Validar autenticação obrigatória.

## Resultado Esperado

```http
Status Code: 403
```

---

# CT012 - Atualização parcial da reserva

## Objetivo

Validar PATCH.

## Endpoint

```http
PATCH /booking/{id}
```

## Resultado Esperado

- Apenas campos enviados devem ser alterados

---

# CT013 - Deletar reserva com token válido

## Objetivo

Validar exclusão.

## Endpoint

```http
DELETE /booking/{id}
```

## Resultado Esperado

```http
Status Code: 201
```

---

# CT014 - Deletar reserva sem autenticação

## Objetivo

Validar proteção da API.

## Resultado Esperado

```http
Status Code: 403
```

---

# CT015 - Buscar reservas por firstname

## Objetivo

Validar filtros de busca.

## Endpoint

```http
GET /booking?firstname=Joao
```

## Resultado Esperado

- Lista filtrada corretamente

---

# CT016 - Buscar reservas por período

## Objetivo

Validar filtro de datas.

## Resultado Esperado

- Apenas reservas do período informado

---

# CT017 - Enviar body inválido

## Objetivo

Validar robustez da API.

## Resultado Esperado

```http
Status Code: 400
```

---

# CT018 - Validar tipo incorreto de dados

## Objetivo

Garantir validação de schema.

## Exemplo

```json
{
  "totalprice": "abc"
}
```

## Resultado Esperado

- API deve rejeitar request