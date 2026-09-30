Trilha QA - Desafio NaSalinha Comp Jr

Repositório destinado à documentação e execução da trilha de auditoria de qualidade (QA) do ecossistema “NaSalinha”, desenvolvido durante a trilha de QA da Comp Jr.

- Escopo do Projeto e Áreas Core
A auditoria foca em validar 3 funcionalidades essenciais do sistema:
1- Autenticação JWT: Validação de login, cadastro e controle de acesso.
2- Check-in por foto: Upload e validação de imagens de comprovação.
3-Sistema de pontos: Cálculo, armazenamento em banco e atualização em ranking.

- Tecnologias e ferramentas utilizadas
*Ambiente e conteinerização: Docker e Docker compose;
*Sistema operacional: Linux (Ubuntu);
*Gestão de versão: Git e GitHub;
*Testes de API: Insomnia / Postman;
*Gestão de QA: GitHub Issues (Bug Reports) e GitHub Projects (Kanban e Casos de Teste)

- Como executar o ambiente localmente
*Pré-requisitos: 
     Docker e Docker compose instalados;
     Git instalado;

- Passo a passo
1- Clonar o repositório do desafio: 
```bash 
git clone [https://github.com/Gustavohmmagalhaes/nasalinha-qa-challenge.git](https://github.com/Gustavohmmagalhaes/nasalinha-qa-challenge.git) cd nasalinha-qa-challenge

2- Configurar as variáveis do ambiente do Backend
cp backend/.env.example backend/.env

3- Subir os contêineres da aplicação:
docker compose up -d

4- Acessar o navegador:
http://localhost:3000

