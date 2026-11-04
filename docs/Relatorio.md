# Relatório Final de Testes - Projeto NaSalinha

Este relatório consolida os resultados do processo de garantia de qualidade (QA) realizado no sistema NaSalinha ao longo do desafio de 7 semanas.

---

## 1. Visão Geral e Escopo
O objetivo desta auditoria de testes foi avaliar a estabilidade, a segurança e a integridade das regras de negócio das 3 funcionalidades *Core* do projeto:
1. **Autenticação JWT** (Login, Permissões e Gestão de Sessão)
2. **Check-in por Foto** (Upload de mídia e validações de arquivo)
3. **Sistema de Pontos** (Persistência no banco de dados e atualização de ranking)

---

## 2. Métricas Gerais de Execução

| Métrica | Quantidade | Percentual |
| :--- | :--- | :--- |
| **Casos de Teste Planeados** | 12 | 100% |
| **Casos de Teste Executados** | 12 | 100% |
| **Testes com Sucesso (Pass)** | 6 | 50% |
| **Testes com Falha (Fail)** | 6 | 50% |

---

## 3. Distribuição dos Bug Reports por Severidade

Foram documentados **6 Bug Reports principais** decorrentes dos testes de Interface e API:

**Críticos (2):** Bloqueiam o uso principal do sistema (Ex: Erro no upload de imagem no Check-in por ausência de temporada ativa; Exposição de mensagens de erro interno do Prisma no formulário de registo).
**Maiores (3):** Causam falhas na regra de negócio ou lógica do backend (Ex: Permissão indevida para criação de contas com cargos elevados; Não envio de e-mail para redefinição de senha; Mensagem "Credenciais inválidas" em conta não verificada).
**Menores (1):** Falhas visuais, alinhamento ou pequenos desvios de UX.

---

## 4. Estratégia de Regressão e Re-teste
Durante a Semana 6, realizou-se o re-teste dos cenários onde as correções de ambiente/backend foram aplicadas. Os fluxos de login, geração de token JWT e upload de foto para o check-in demonstraram estabilidade, confirmando que as alterações não causaram regressão nas áreas de autenticação e pontuação.

---

## 5. Parecer Final de Qualidade
A aplicação NaSalinha apresenta uma estrutura base sólida, porém necessita de atenção em tratamentos de exceção no backend, validação de tipos de dados recebidos e sanitização de dados de entrada. Com as correções mapeadas nas Issues e validadas nos testes de regressão, o sistema encontra-se apto para avançar na esteira de desenvolvimento.
