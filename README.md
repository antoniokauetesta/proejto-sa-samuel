<div align="center">

# 🐾✨ Little Ville

### 📍 Registre avistamentos e acompanhe tudo num mapa interativo!

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

</div>

---

## 💫 Sobre o projeto

**Little Ville** é uma aplicação web feita para **registrar e visualizar avistamentos** em um mapa interativo 🗺️. Qualquer usuário cadastrado pode reportar uma ocorrência com título, descrição e localização, acompanhar estatísticas gerais no dashboard, e administradores contam com um painel próprio para gerenciar tudo com carinho 💛.

---

## 👥 Grupo

| 🧑‍💻 Integrante |
|---|
| Antonio Kaue |
| Kaunay Bairros |
| Henrique Silva |

---

## ✨ Funcionalidades

- 🔐 **Autenticação** — cadastro, login e edição de perfil
- 📌 **Avistamentos** — criar, editar, excluir e listar, com localização em mapa
- 🗺️ **Mapa interativo** — visualização com Leaflet
- 📊 **Dashboard** — estatísticas gerais (avistamentos, usuários e últimos registros)
- 🛡️ **Painel administrativo** — gerenciamento de usuários e moderação de avistamentos
- ☁️ **Deploy pronto para Vercel** — frontend e API serverless no mesmo projeto

---

## 🛠️ Tecnologias

<div align="center">

| 🖥️ Backend | 🎨 Frontend |
|---|---|
| Node.js + Express | React + Vite |
| Prisma ORM | React Router DOM |
| PostgreSQL | Leaflet / React-Leaflet |
| bcrypt 🔒 | Axios |
| JWT 🔑 | TypeScript |

</div>

---

## 📁 Estrutura do projeto

```
proejto-sa-samuel/
├── ☁️ api/
│   └── index.mjs          # Handler serverless para a Vercel
├── 📦 backend/
│   ├── prisma/             # Schema e migrations do banco de dados
│   ├── createadmin.js      # Script para criar um usuário admin
│   └── src/
│       ├── controllers/    # Regras de negócio (auth, admin, avistamentos)
│       ├── lib/             # Conexão com o Prisma e segredos
│       ├── middlewares/    # Autenticação e autorização
│       ├── routes/          # Rotas da API
│       └── index.js         # Ponto de entrada do servidor
├── 🎨 frontend/
│   └── src/
│       ├── contexts/        # Contexto de autenticação
│       ├── layouts/          # Layout geral da aplicação
│       ├── services/         # Configuração de chamadas à API
│       └── pages/            # Telas (Login, Registro, Dashboard, Avistamentos, Admin)
└── vercel.json              # Configuração de deploy (frontend + API juntos)
```

---

## 🚀 Como executar localmente

### ✅ Pré-requisitos
- Node.js
- PostgreSQL

### 🖥️ Backend

```bash
cd backend
npm install

# configure a variável DATABASE_URL em um arquivo .env
# ex: DATABASE_URL="postgresql://usuario:senha@localhost:5432/littleville"

npx prisma migrate dev
npm run dev
```

### 🎨 Frontend

```bash
cd frontend
npm install
npm run dev
```

> 💡 Em desenvolvimento local, deixe `VITE_API_URL` ausente: o frontend usará `/api` e a API local removerá esse prefixo automaticamente.

---

## ☁️ Deploy na Vercel

1. Crie um **único projeto** na Vercel usando a **raiz do repositório** como *Root Directory*.
2. O `vercel.json` já configura o frontend e a API serverless juntos.
3. Nas variáveis de ambiente da Vercel, defina:
   - `DATABASE_URL` → URL de um banco PostgreSQL
   - `JWT_SECRET` → um segredo forte
4. O `postinstall` do backend gera o Prisma Client automaticamente.
5. Antes do primeiro uso, aplique as migrações no banco de produção:

```bash
cd backend
npx prisma migrate deploy
```

---

## 📡 Principais rotas da API

<div align="center">

| Método | Rota | Descrição |
|:---:|---|---|
| `POST` | `/auth/register` | 🆕 Cria um novo usuário |
| `POST` | `/auth/login` | 🔑 Autentica um usuário |
| `PUT` | `/auth/profile` | ✏️ Atualiza o perfil do usuário logado |
| `GET` | `/sightings` | 📋 Lista todos os avistamentos |
| `GET` | `/sightings/:id` | 🔍 Busca um avistamento específico |
| `POST` | `/sightings` | ➕ Cria um novo avistamento |
| `PUT` | `/sightings/:id` | ✏️ Atualiza um avistamento |
| `DELETE` | `/sightings/:id` | 🗑️ Remove um avistamento |
| `GET` | `/sightings/stats` | 📊 Estatísticas do dashboard |
| `GET` | `/admin/users` | 👥 Lista usuários (admin) |
| `PUT` | `/admin/users/:id` | ✏️ Atualiza um usuário (admin) |
| `DELETE` | `/admin/users/:id` | 🗑️ Remove um usuário (admin) |
| `DELETE` | `/admin/sightings/:id` | 🗑️ Remove um avistamento (admin) |

</div>

---

<div align="center">

## 📄 Licença

Distribuído sob a licença **ISC**.

Feito com 💛 pelo grupo **Little Ville** 🐾

</div>
