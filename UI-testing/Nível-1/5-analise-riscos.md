# Análise de Riscos - SauceDemo

# Matriz de Riscos

| ID | Risco | Impacto | Probabilidade | Mitigação |
|---|---|---|---|---|
| R-001 | Falha no login | Alto | Média | Automatizar cenários críticos |
| R-002 | Erro no checkout | Alto | Média | Regressão frequente |
| R-003 | Lentidão da aplicação | Médio | Média | Monitoramento contínuo |
| R-004 | Falha na remoção do carrinho | Médio | Média | Testes automatizados |
| R-005 | Navegação inconsistente | Médio | Baixa | Testes cross-browser |
| R-006 | Problemas visuais | Médio | Média | Testes de UI |
| R-007 | Falhas de logout | Baixo | Baixa | Testes de sessão |

---

# Riscos Funcionais

## Login
Problemas de autenticação impedem acesso à aplicação.

## Checkout
Falhas podem bloquear conclusão da compra.

## Carrinho
Inconsistências podem gerar perda de itens.

---

# Riscos Técnicos

## Dependência de Frontend
Grande parte da lógica está concentrada na interface.

## Compatibilidade entre Navegadores
Diferenças podem impactar:
- Renderização
- Performance
- Eventos da UI

---

# Riscos Operacionais

## Ambiente Demo Compartilhado
Mudanças externas podem impactar resultados dos testes.

## Instabilidade Temporária
Possíveis oscilações do ambiente.

---

# Recomendações

- Automatizar fluxos críticos
- Implementar testes regressivos
- Validar em múltiplos navegadores
- Executar smoke tests antes de releases