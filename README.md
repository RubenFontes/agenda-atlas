# Agenda de Contatos (Node.js + Express + EJS)

Aplicação web de agenda de contatos com renderização server-side em EJS, persistência em MongoDB/Mongoose e UI responsiva com Bootstrap 4. Inclui autenticação baseada em sessão, proteção CSRF e mensagens flash.

## Stack
- Node.js, Express
- EJS (SSR)
- MongoDB + Mongoose
- express-session + connect-mongo
- csurf (CSRF)
- Bootstrap 4

## Requisitos
- Node.js 16+ (recomendado)
- MongoDB em execução (local ou Atlas)

## Configuração
1. Crie um arquivo `.env` na raiz com:
   ```bash
   # .env
   CONNECTIONSTRING=mongodb://localhost:27017/agenda
   SESSION_SECRET=sua_chave_segura_aqui
   ```
2. Instale as dependências:
   ```bash
   npm install
   ```

## Executando
- Desenvolvimento:
  ```bash
  npm start
  ```
- A aplicação ficará disponível em `http://localhost:3000`.

## Estrutura (essencial)
```
src/
  views/                # Templates EJS
    includes/           # Partials (head, nav, footer, messages)
    index.ejs           # Lista de contatos
    login.ejs           # Login e cadastro
    contato.ejs         # Criar/editar contato
    404.ejs             # Página de erro 404
public/                 # Arquivos estáticos (servidos por Express)
frontend/               # Código frontend (bundle servido em /assets/js/bundle.js)
server.js               # Bootstrap do servidor Express
```

## Rotas principais
- `GET /` – lista de contatos
- `GET /contato/index` – formulário de novo contato
- `POST /contato/register` – cria contato
- `POST /contato/edit/:id` – edita contato
- `GET /contato/delete/:id` – exclui contato
- `GET /login/index` – tela de login/cadastro
- `POST /login/login` – autenticação
- `POST /login/register` – cadastro de usuário
- `GET /login/logout` – logout

## Segurança
- Cookies de sessão com `express-session`
- Proteção CSRF via `csurf`
- Sessões persistidas no MongoDB via `connect-mongo`

## UI/Estilo
- Layout responsivo com Bootstrap 4

## Licença
Este projeto é distribuído sob a licença MIT. Veja `LICENSE`.


