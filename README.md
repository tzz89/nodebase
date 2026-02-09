## Introduction
Code along based on Build and Deploy an N8N & Zapier Clone | Next.js 15, React, Better Auth, Polar | Full Course 2025
https://www.youtube.com/watch?v=ED2H_y6dmC8


## Techstack
   - Foundation: Nextjs(15.5.4) + typescript
   - DB: Prisma + Neon
   - Authentication: Better Auth
   - Payments/Subscription: Polar
   - Workflow Executions: inngest
   - Observability: Sentry
   - UI component: Shadcn UI

## Patterns
1. ZodResolver + react-hook-form for forms handling


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

### Data access layer using TRPC
We will prefetch in the server component and hand off to the client component using hydration boundary and suspensequery
1. install tanstack (react query, https://trpc.io/docs/client/tanstack-react-query/server-components)
   - npm install @trpc/server @trpc/client @trpc/tanstack-react-query @tanstack/react-query@latest zod client-only server-only
2. create src/trpc/init.ts 
3. create trpc/routers/_app.ts (this is like the endpoint)
   1. procedures are like workflows, eg, we can create protectedProcedure and add in middleware to check if the user is login
4. create app/api/trpc/[trpc]/route.ts (route.ts is a reserve file)
5. Create trpc/query-client.ts 
6. Create trpc/client.tsx, this is the client component (need to wrap the entire app, in layout.tsx with this provider)
7. Create trpc/server.tsx this is server component

### Authentication
Using better Auth: https://www.better-auth.com/docs/introduction
1. create (auth) folder, In nextjs (folderName) is a route group. when a folder is wrap with bracket, it does not appear in the URL



### background test 
Using inngest https://www.inngest.com/docs?ref=nav
#### Starting inngest server
npx inngest-cli@1.12.1 dev


#### Progession
george@gmail.com
12345678

Stop 3hr 06