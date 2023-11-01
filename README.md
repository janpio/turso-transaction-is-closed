# turso transaction is closed reproduction

```
npm install
npx prisma generate

turso db create turso-prisma
turso db tokens create turso-prisma
turso db show turso-prisma

# put values into .env created from .env.example

npx prisma migrate diff --from-empty --to-schema-datamodel prisma/schema.prisma --script > baseline.sql
turso db shell turso-prisma < baseline.sql 

ts-node ./script.ts
```