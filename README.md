# proejto-sa-samuel

## Deploy na Vercel

Crie um unico projeto Vercel usando a raiz do repositorio como **Root Directory**. O `vercel.json` da raiz configura o frontend e a API serverless juntos.

Configure `DATABASE_URL` com a URL de um banco PostgreSQL e `JWT_SECRET` com um segredo forte nas variaveis de ambiente da Vercel.

O `postinstall` do backend gera o Prisma Client automaticamente. Antes do primeiro uso, aplique as migracoes no banco de producao:

```powershell
cd backend
npx prisma migrate deploy
```

Para desenvolvimento local, mantenha `VITE_API_URL` ausente: o frontend usara `/api` e a API local removera esse prefixo automaticamente.
