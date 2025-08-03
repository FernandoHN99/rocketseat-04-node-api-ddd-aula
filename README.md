# 🧠 Rocketseat Node API - DDD Forum

Este projeto visa demonstrar boas práticas de organização de código, arquitetura em camadas, testes automatizados e uso de eventos de domínio para desacoplamento.

API RESTful desenvolvida em **Node.js com TypeScript**, seguindo os princípios de **Domain-Driven Design (DDD)**. Simula um fórum de perguntas e respostas, com recursos como perguntas, respostas, comentários e notificações automáticas.


## ⚙️ Pré-requisitos

* [Node.js](https://nodejs.org/) >= 18.x
* [npm](https://www.npmjs.com/) >= 9.x
* Banco de dados (ex: SQLite ou PostgreSQL — configurável)
* (Opcional) [Docker](https://www.docker.com/) para facilitar o setup

## 🚀 Como iniciar o projeto

### 1. Clone o repositório

```sh
git clone <url-do-repo>
cd <nome-do-repo>
```

### 2. Instale as dependências
```sh
npm install
```

### 3. Copie o arquivo de variáveis de ambiente

```sh
cp .env.example .env
```

### 4. Execute as migrations

```sh
npm run migrate
```

### 5. Rodar os testes

```sh
npm run test
```

## 📮 Endpoints

> Controllers ainda mão implementadas.

| Método | Rota                                      | Descrição                                 | Observação                       |
|--------|-------------------------------------------|-------------------------------------------|----------------------------------|
| POST   | `/questions`                              | Criar uma nova pergunta                   | Requer autenticação              |
| GET    | `/questions/recent?page={n}`              | Listar perguntas recentes (paginado)      | Pública                          |
| GET    | `/questions/:slug`                        | Buscar pergunta pelo slug                 | Pública                          |
| PUT    | `/questions/:id`                          | Editar pergunta                           | Somente autor                    |
| DELETE | `/questions/:id`                          | Deletar pergunta                          | Somente autor                    |
| POST   | `/questions/:id/comments`                 | Comentar em uma pergunta                  | Requer autenticação              |
| GET    | `/questions/:id/comments?page={n}`        | Listar comentários de uma pergunta        | Pública                          |
| DELETE | `/questions/comments/:commentId`          | Deletar comentário de pergunta            | Somente autor do comentário      |
| POST   | `/answers`                                | Criar resposta para uma pergunta          | Requer autenticação              |
| PUT    | `/answers/:id`                            | Editar resposta                           | Somente autor                    |
| DELETE | `/answers/:id`                            | Deletar resposta                          | Somente autor                    |
| POST   | `/answers/:id/comments`                   | Comentar em uma resposta                  | Requer autenticação              |
| GET    | `/answers/:id/comments?page={n}`          | Listar comentários de uma resposta        | Pública                          |
| DELETE | `/answers/comments/:commentId`            | Deletar comentário de resposta            | Somente autor do comentário      |
| GET    | `/questions/:id/answers?page={n}`         | Listar respostas de uma pergunta          | Pública                          |
| POST   | `/questions/:id/best-answer`              | Escolher melhor resposta                  | Somente autor da pergunta        |

