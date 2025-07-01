# NestJS Hexogen Starter

[![Star][star-img]][repo-url]
[![License][license-img]][license-url]
[![PRs Welcome][pr-img]][repo-url]

> 🧱 A minimal NestJS starter project pre-configured for use with [Hexogen](https://www.npmjs.com/package/hexogen) — the CLI tool for lightning-fast, production-grade, hexagonal CRUD API generation.

---

## ✨ What Is This?

This is a boilerplate NestJS project built for rapid prototyping using the Hexogen CLI. It comes pre-integrated with the required dependencies like:

* ✅ TypeORM with PostgreSQL (production-ready)
* ✅ Swagger/OpenAPI setup
* ✅ DTO validation (class-validator & class-transformer)
* ✅ Prettier for formatting
* ✅ Reflect metadata support
* ✅ Migration system

Use it to instantly scaffold modules with Hexogen and build a production-grade backend using hexagonal architecture — without worrying about initial setup.

---

## 📦 What's Inside

* ✅ NestJS setup with core structure (AppModule, AppController, etc.)
* ✅ Swagger setup (automatically detects routes & DTOs)
* ✅ TypeORM integration with PostgreSQL
* ✅ Global validation pipe
* ✅ Prettier setup for formatting
* ✅ Reflect metadata for decorators
* ✅ Migration system with CLI commands
* ✅ Environment-based configuration
* ✅ Ready to work with Hexogen out-of-the-box

---

## 🚀 Quick Start

1. Clone the repo

```bash
git clone https://github.com/dev-ahmadbilal/nestjs-hexogen-starter.git
cd nestjs-hexogen-starter
```

2. Install dependencies

```bash
npm install
```

3. Set up environment variables

Copy the sample environment file and update the values:

```bash
cp env.sample .env
```

Then edit `.env` with your database credentials.

4. Set up PostgreSQL database

```bash
# Create database
createdb nestjs_hexogen_starter
```

5. Run migrations

```bash
npm run migration:run
```

6. Install Hexogen CLI

```bash
npm install -g hexogen
```

7. Run the dev server

```bash
npm run start:dev
```

8. Visit Swagger Docs

```
http://localhost:3000/docs
```

9. Generate a module using Hexogen!

```bash
hexogen resource User
```

10. That's it — your hexagonal module is now live.

---

## 📂 Directory Structure

```
nestjs-hexogen-starter/
├── src/
│   ├── app.module.ts
│   ├── main.ts
│   ├── config/
│   │   └── database.config.ts
│   └── users/                    <-- Example hexagonal module
│       ├── domain/
│       ├── dto/
│       ├── infrastructure/
│       │   └── persistence/
│       │       └── relational/
│       │           ├── entities/
│       │           │   └── user.entity.ts
│       │           └── repositories/
│       └── users.module.ts
├── migrations/                   <-- Database migrations
├── typeorm.config.ts            <-- TypeORM CLI config
├── .prettierrc
├── tsconfig.json
└── ...
```

---

## ⚙️ Project Configuration

* **Database**: PostgreSQL with TypeORM
* **Configuration**: Environment-based with fallback defaults
* **Swagger path**: `/api`
* **Global Validation**: Enabled with whitelist + transform
* **Prettier**: `.prettierrc` config is included
* **Reflect Metadata**: Already imported in `main.ts`

---

## 🧪 Example Usage

Once you've created a module with:

```bash
hexogen resource Product
```

You can visit:

* DTOs in: `src/product/dto`
* Entity: `src/product/infrastructure/persistence/relational/entities`
* Service, Controller, etc.: `src/product`

Swagger will automatically expose routes and DTO schemas under `/docs`.

---

## 🤖 Schema-Driven Generation

Use a schema file instead of interactive CLI:

```bash
hexogen resource --schema ./schemas/user.json
```

Example schema:

```json
{
  "name": "User",
  "isAddTestCase": true,
  "functionalities": ["create", "findAll", "findOne", "update", "delete"],
  "fields": [
    {
      "name": "email",
      "optional": false,
      "type": "varchar",
      "dto": true
    }
  ]
}
```

---

## 🤝 Contributing

PRs welcome! This starter project aims to stay minimal and well-structured.

---

## 📄 License

MIT © Ahmad Bilal

---

## 🙋 Support

For issues and discussions, head over to:

👉 [Hexogen GitHub](https://github.com/dev-ahmadbilal/hexogen)

---

[star-img]: https://img.shields.io/github/stars/dev-ahmadbilal/nestjs-hexogen-starter?style=social
[repo-url]: https://github.com/dev-ahmadbilal/nestjs-hexogen-starter
[license-img]: https://img.shields.io/github/license/dev-ahmadbilal/nestjs-hexogen-starter
[license-url]: https://github.com/dev-ahmadbilal/nestjs-hexogen-starter/blob/main/LICENSE
[pr-img]: https://img.shields.io/badge/PRs-welcome-brightgreen.svg
