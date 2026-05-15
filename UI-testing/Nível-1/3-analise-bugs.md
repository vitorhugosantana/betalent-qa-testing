# Análise de Bugs - SauceDemo

# BUG-001 - Inconsistência visual com problem_user

## Severidade
Média

## Prioridade
Alta

## Ambiente
Chrome - Windows 11

## Descrição
Ao utilizar o usuário "problem_user", algumas imagens de produtos aparecem quebradas ou incorretas.

## Passos para Reprodução
1. Fazer login com:
   - Username: problem_user
   - Password: secret_sauce
2. Acessar lista de produtos

## Resultado Esperado
Todas as imagens devem carregar corretamente.

## Resultado Atual
Imagens inconsistentes são exibidas.

## Impacto
Compromete a experiência visual do usuário.

---

# BUG-002 - Lentidão no login com performance_glitch_user

## Severidade
Baixa

## Prioridade
Média

## Descrição
Login apresenta tempo de resposta significativamente maior.

## Passos para Reprodução
1. Fazer login com performance_glitch_user

## Resultado Esperado
Login rápido e responsivo.

## Resultado Atual
Demora perceptível durante autenticação.

## Impacto
Experiência degradada.
