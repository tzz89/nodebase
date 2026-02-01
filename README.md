## Introduction
Code along based on Build and Deploy an N8N & Zapier Clone | Next.js 15, React, Better Auth, Polar | Full Course 2025




## Techstack
   - Foundation: Nextjs(15.5.4) + typescript
   - DB: Prisma + Neon
   - Authentication: Better Auth
   - Payments/Subscription: Polar
   - Workflow Executions: inngest
   - Observability: Sentry
   - UI component: Shadcn UI
  
## Key workflow
### Setup
1. create nextjs project (npx create-next-app@XXXXX <projectname>)
   - TS
   - Biome
   - Tailwind
   - App router
   - Turbopack
2. install component library (shadcn/materialUI)
   - shadcn@[version] init 
   - shadcn@[version] add --all

### Database and ORM
1. install prisma (npm install prisma tsx --save-dev), this is for development like cli, init etc
2. install prisma client (npm install @prisma/client)
3. initialize prisma (npx prisma init)
4. setup a connection to postgres (self hosted / cloud like neon/supabase/railway)
5. create models in schema.prisma
   1. npx prisma migrate dev 
   2. npx prisma studio (This is UI to connect to DB)
6. Setup global prisma client (refer to lib->db.ts, handle the case for hot reload)

