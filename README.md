# NLW Rooms API

API desenvolvida em Node.js com Fastify, Drizzle ORM e PostgreSQL para gerenciamento de salas (rooms).

## Tecnologias Utilizadas
- Node.js
- Fastify
- Drizzle ORM
- PostgreSQL (com extensão pgvector)
- TypeScript
- Zod (validação de schemas)
- Docker (para banco de dados)

## Como rodar o projeto

### 1. Suba o banco de dados com Docker
```bash
docker-compose up -d
```

### 2. Instale as dependências
```bash
npm install
```

### 3. Configure as variáveis de ambiente
Crie um arquivo `.env` na raiz do projeto com o conteúdo:
```
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

### 4. Rode as migrações e popule o banco (opcional)
```bash
npm run db:seed
```

### 5. Inicie o servidor
```bash
npm run dev
```

## Endpoints
- `GET /health` — Health check
- `GET /rooms` — Lista todas as salas

## Estrutura do Projeto
- `src/server.ts` — Inicialização do servidor Fastify
- `src/http/routes/get-rooms.ts` — Rota para listagem de salas
- `src/db/schema/rooms.ts` — Definição da tabela de salas
- `src/db/seed.ts` — Seed do banco de dados

## Banco de Dados
O banco utiliza PostgreSQL com a extensão `pgvector` habilitada (veja `docker/setup.sql`).

---

> Projeto base para estudos de API REST com Fastify, Drizzle ORM e PostgreSQL.
