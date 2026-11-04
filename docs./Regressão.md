# Plano de Testes de Regressão - Projeto NaSalinha

Este documento descreve o fluxo de testes de regressão executado para garantir que correções de bugs e novas alterações não causem efeitos colaterais nas funcionalidades legadas da aplicação.

---

## 1. Área Core: Autenticação JWT

* **Cenário de Correção Simulado:** Correção da expiração indevida do token JWT e tratamento de credenciais inválidas na rota `/api/auth/login`.
* **Suíte de Testes de Regressão Obrigatória:**
  1. `[CT-AUTH-01]` Realizar login com credenciais válidas via interface (Frontend).
  2. `[CT-AUTH-02]` Tentativa de acesso a rotas protegidas com token expirado/inválido (Frontend).
  3. `[CT-AUTH-03]` `GET /api/auth/login` - Validação de login com dados corretos e retorno de status `200 OK` + Token JWT (API).
  4. `[CT-AUTH-04]` `GET /api/auth/login` - Validação de login com senha incorreta e retorno de status `401 Unauthorized` (API).

---

## 2. Área Core: Check-in por Foto

* **Cenário de Correção Simulado:** Ajuste no middleware de upload (Multer/Cloudinary) para aceitar a chave `photo` no envio de arquivos via `multipart/form-data`.
* **Suíte de Testes de Regressão Obrigatória:**
  1. `[CT-CHK-01]` Envio de check-in com foto válida pela interface (Frontend).
  2. `[CT-CHK-02]` Tentativa de check-in sem anexar imagem na interface (Frontend).
  3. `[CT-CHK-03]` `POST /api/checkins` - Realizar check-in com foto via API (campo `photo`) retornando status `201 Created` e URL do Cloudinary (API).
  4. `[CT-CHK-04]` `POST /api/checkins` - Tentativa de check-in sem foto via API retornando `400 Bad Request` com mensagem `"Foto é obrigatória"` (API).

---

## 3. Área Core: Sistema de Pontos & Ranking

* **Cenário de Correção Simulado:** Ajuste na regra de negócio que incrementa a pontuação no perfil do utilizador após a validação do check-in.
* **Suíte de Testes de Regressão Obrigatória:**
  1. `[CT-PTS-01]` Visualização do saldo de pontos atualizado no Dashboard após check-in (Frontend).
  2. `[CT-PTS-02]` Ordenação correta da tabela de classificação de pontuação (Frontend).
  3. `[CT-PTS-03]` `GET /api/points` - Consulta do ranking geral com retorno de status `200 OK` (API).
  4. `[CT-PTS-04]` `GET /api/points` - Consulta de ranking sem token de autenticação retornando `401 Unauthorized` (API).
