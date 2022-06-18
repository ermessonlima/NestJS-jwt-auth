# NestJS - Autenticação e Autorização com JWT

## Tópicos

[TOC]

## Prisma

### Instalar o prisma

```bash
npm install prisma -D
```

### Inicializar o prisma

```bash
npx prisma init
```

### `prisma/schema.prisma`

```java
datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}

generator client {
  provider        = "prisma-client-js"
}

model User {
  id Int @id @default(autoincrement())

  email    String  @unique
  password String

  name      String
}

```

## Arquivo .env

```bash
# Configuration

JWT_SECRET=""

# Database

DATABASE_URL=""

```

### Exemplo de Arquivo .env preenchido

```bash
# Configuration

JWT_SECRET="aksdo23joi5j234otb32o4itvb4813uc34hvt13839"

# Database

DATABASE_URL="mysql://root@localhost:3306/nestjs_auth"
```

## Migrar o banco

```bash
npx prisma migrate dev --name init
```

Esse comando deverá instalar a dependência `@prisma/client` no projeto.

### Criação do módulo do prisma

#### Comandos na CLI para criação dos arquivos

```bash
nest g module prisma
nest g service prisma
```
