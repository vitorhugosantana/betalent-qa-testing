# Resultados dos Testes

# Resumo Executivo

Foram executados testes funcionais na API Restful Booker com foco em:

- Autenticação
- CRUD de reservas
- Validações
- Tratamento de erros
- Filtros de busca

---

# Resultado Geral

| Categoria              | Total | Sucesso | Falha |
|------------------------|-------|----------|--------|
| Autenticação           | 2     | 2        | 0      |
| CRUD                   | 8     | 7        | 1      |
| Validações             | 5     | 3        | 2      |
| Tratamento de erros    | 3     | 3        | 0      |
| Filtros                | 2     | 2        | 0      |

---

# Evidências dos Testes

---

# CT001 - Health Check

## Resultado

**PASSOU**

## Evidência

![Ping](./imagens/ct001.png)

---

# CT002 - Login válido

## Resultado

**PASSOU**

## Evidência

![Login valido](./imagens/ct002.png)


---

# CT003 - Login inválido

## Resultado

**PASSOU**

## Evidência

![Login invalido](./imagens/ct003.png)

---

# CT004 - Criar reserva válida

## Resultado

**PASSOU**

## Evidência

![Criar reserva](./imagens/ct004.png)


---

# CT005 - Criar reserva sem firstname

## Resultado

**PASSOU**

## Evidência

![Criar reserva sem first name](./imagens/ct005.png)


## Observação

A API aceitou criação mesmo sem campo obrigatório.

---

# CT006 - Criar reserva sem lastname

## Resultado

**FALHOU**

## Evidência

![Criar reserva sem last name](./imagens/ct006.png)

## Observação

Campo obrigatório não validado corretamente.

---

# CT007 - Criar reserva sem bookingdates

## Resultado

**FALHOU**

## Evidência

![Criar reserva sem bookingdates](./imagens/ct007.png)

Erro retornado corretamente.

---

# CT008 - Buscar reserva existente

## Resultado

**PASSOU**

## Evidência

![Buscar reserva existente](./imagens/ct008.png)

Dados corretos retornados

---

# CT009 - Buscar reserva inexistente

## Resultado

**FALHOU**

## Evidência

![Buscar reserva inexistente](./imagens/ct009.png)

Dados não encontrados


# CT010 - Atualizar reserva com token válido

## Resultado

**PASSOU**

## Evidência

![Atualizar reserva com token válido](./imagens/ct0010.png)

Dados atualizados

---

# CT011 - Atualizar reserva sem token

## Resultado

**FALHOU**

## Evidência

![Atualizar reserva sem token](./imagens/ct0011.png)

Acesso negado

---

# CT012 - Atualização parcial da reserva

## Resultado

**PASSOU**

## Evidência

![Atualização parcial](./imagens/ct0012.png)

Apenas campos enviados devem ser alterados

---

# CT013 - Deletar reserva com token válido

## Resultado

**PASSOU**

## Evidência

![Deletar reserva com token valido](./imagens/ct0013.png)

Reserva deletada

---

# CT014 - Deletar reserva sem autenticação

## Resultado

**FALHOU**

## Evidência

![Deletar reserva sem autenticação](./imagens/ct0014.png)

Reserva não deletada, acesso negado

---

# CT015 - Buscar reservas por firstname

## Resultado

**PASSOU**

## Evidência

![Buscar reservas por firt name](./imagens/ct0015.png)

Reserva encontrada pelo first name

---

# CT016 - Buscar reservas por período

## Resultado

**PASSOU**

## Evidência

![Buscar reservas por período](./imagens/ct0016.png)

Reserva encontrada por período

---

# CT017 - Enviar body inválido

## Resultado

**FALHOU**

## Evidência

![Enviar body invalido](./imagens/ct0017.png)

Body inválido

---

# CT018 - Validar tipo incorreto de dados

## Resultado

**FALHOU**

## Evidência

![Validar tipo incorreto de dados](./imagens/ct0018.png)

API deve rejeitar request

# Conclusão

A API apresentou bom funcionamento nos fluxos principais de autenticação e CRUD.

Entretanto, foram identificadas falhas importantes nas validações de campos obrigatórios, permitindo criação de reservas incompletas.