# Análise de Bugs

---

# BUG001 - API permite criação sem firstname

## Severidade

Alta

## Prioridade

Alta

## Descrição

A API permite criar reserva mesmo sem o campo `firstname`.

## Passos para Reproduzir

1. Enviar `POST /booking`
2. Omitir `firstname` no body
3. Executar request

## Resultado Atual

Reserva criada com sucesso.

## Resultado Esperado

API deveria retornar erro `400 Bad Request`.

---

# BUG002 - API permite criação sem lastname

## Severidade

Alta

## Prioridade

Alta

## Descrição

Campo `lastname` não está sendo validado.

## Resultado Atual

Reserva criada normalmente.

## Resultado Esperado

Retornar erro de validação.

---

# BUG003 - Mensagens de erro pouco descritivas

## Severidade

Média

## Prioridade

Média

## Descrição

A API retorna respostas genéricas em alguns cenários de erro.

## Impacto

Dificulta troubleshooting e automação dos testes.

---

# BUG004 - Inconsistência de status code

## Severidade

Média

## Prioridade

Baixa

## Descrição

Alguns endpoints retornam status diferentes do padrão REST esperado.

## Exemplo

```http
DELETE /booking/{id}
```

Retorna:

```http
201 Created
```

Ao invés de:

```http
200 OK
```

ou

```http
204 No Content
```

---

# Recomendações

- Implementar validação obrigatória de schema
- Melhorar mensagens de erro
- Padronizar status codes
- Adicionar documentação OpenAPI/Swagger mais detalhada