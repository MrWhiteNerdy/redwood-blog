# Migration `20200709111510-create-posts`

This migration has been generated by Joseph Davis at 7/9/2020, 11:15:10 AM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
PRAGMA foreign_keys=OFF;

CREATE TABLE "quaint"."Post" (
"body" TEXT NOT NULL  ,"createdAt" DATE NOT NULL DEFAULT CURRENT_TIMESTAMP ,"id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,"title" TEXT NOT NULL  )

PRAGMA "quaint".foreign_key_check;

PRAGMA foreign_keys=ON;
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200709111510-create-posts
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,16 @@
+datasource DS {
+  provider = "sqlite"
+  url = "***"
+}
+
+generator client {
+  provider      = "prisma-client-js"
+  binaryTargets = env("BINARY_TARGET")
+}
+
+model Post {
+  id Int @id @default(autoincrement())
+  title String
+  body String
+  createdAt DateTime @default(now())
+}
```


