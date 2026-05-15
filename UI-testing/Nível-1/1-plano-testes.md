# Plano de Testes - SauceDemo

## Objetivo

Validar os principais fluxos funcionais da aplicação SauceDemo, garantindo funcionalidade e correta experiência de compra.

---

# Escopo de Testes

## Funcionalidades em Escopo

### Autenticação
- Login com usuário válido
- Login com usuário inválido
- Login com diferentes tipos de usuários disponíveis

### Produtos
- Visualização da lista de produtos
- Ordenação de produtos
- Filtragem/ordenação por preço e nome

### Carrinho
- Adição de produtos
- Remoção de produtos
- Atualização do badge do carrinho

### Checkout
- Fluxo completo de compra
- Preenchimento de formulário
- Finalização do pedido

### Navegação
- Navegação entre páginas
- Navegação pelo menu lateral

### Sessão
- Logout

---

# Estratégia de Testes

## Tipos de Testes

### Testes Funcionais
Validação do comportamento esperado das funcionalidades.

### Testes de UI
Validação visual e comportamento dos componentes.

### Testes Exploratórios
Identificação de falhas não previstas inicialmente.

---

# Ambiente de Testes

| Item | Valor |
|---|---|
| URL | https://www.saucedemo.com |
| Navegador Principal | Google Chrome |
| Sistema Operacional | Windows 11 |
| Resolução | 1920x1080 |

---

# Credenciais de Teste

| Usuário | Objetivo |
|---|---|
| standard_user | Fluxo padrão |
| locked_out_user | Usuário bloqueado |
| problem_user | Testes de inconsistência |
| performance_glitch_user | Testes de lentidão |

Senha:
secret_sauce

---

# Critérios de Entrada

- Aplicação disponível
- Ambiente acessível
- Navegadores instalados

---

# Critérios de Saída

- Todos os cenários críticos executados
- Bugs documentados
- Evidências registradas
- Fluxos principais validados

---

# Ferramentas Utilizadas

- Chrome DevTools
- Markdown