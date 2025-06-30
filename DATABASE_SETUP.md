# Database Setup Guide

This project uses TypeORM with PostgreSQL. Follow these steps to set up your database:

## Prerequisites

1. Install PostgreSQL on your system
2. Create a database named `nestjs_hexogen_starter`

## Environment Configuration

Create a `.env` file in the root directory with the following variables:

```env
# Database Configuration
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=your_password
DB_DATABASE=nestjs_hexogen_starter
DB_SYNCHRONIZE=false
DB_LOGGING=true

# Application Configuration
PORT=3000
NODE_ENV=development
```

## Database Setup Commands

### 1. Install Dependencies
```bash
npm install
```

### 2. Run Migrations
```bash
# Generate a new migration (when you make entity changes)
npm run migration:generate -- migrations/YourMigrationName

# Run pending migrations
npm run migration:run

# Show migration status
npm run migration:show

# Revert last migration
npm run migration:revert
```

### 3. Schema Management
```bash
# Sync schema (development only - don't use in production)
npm run schema:sync

# Drop all tables (dangerous!)
npm run schema:drop
```

## Available Scripts

- `npm run migration:generate` - Generate a new migration
- `npm run migration:run` - Run pending migrations
- `npm run migration:revert` - Revert the last migration
- `npm run migration:show` - Show migration status
- `npm run schema:sync` - Sync database schema with entities
- `npm run schema:drop` - Drop all tables

## Entity Structure

Entities are located in `src/entities/` and automatically discovered by TypeORM.

## Migration Files

Migrations are stored in the `migrations/` directory and follow the naming convention:
`{timestamp}-{MigrationName}.ts`

## Development vs Production

- **Development**: Set `DB_SYNCHRONIZE=true` for automatic schema updates
- **Production**: Always use migrations and set `DB_SYNCHRONIZE=false` 