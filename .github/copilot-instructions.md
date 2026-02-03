# Copilot Instructions for SportsZ

## Project Overview
SportsZ is a Node.js Express application for sports-related functionality, using Neon serverless PostgreSQL with Drizzle ORM. The app supports real-time features via WebSockets.

## Architecture
- **Main Entry**: `src/index.js` - Express server setup
- **Database**: `src/db/db.js` - Drizzle ORM connection to Neon PostgreSQL
- **Structure**: ES modules, source code in `src/` directory

## Key Patterns
- **Environment Variables**: Load via `import 'dotenv/config';` at file top (see `src/db/db.js`)
- **Database Queries**: Use exported `db` instance from `src/db/db.js` for all Drizzle operations
- **Server Config**: Express app configured in `src/index.js` with JSON middleware

## Development Workflow
- **Start Dev Server**: `npm run dev` (uses `node --watch` for auto-restart)
- **Production Start**: `npm run start`
- **Database Migrations**: Use `drizzle-kit` commands (e.g., `drizzle-kit generate`, `drizzle-kit push`)
- **Schema Location**: Place Drizzle schemas in `src/db/` directory

## Dependencies
- **Database**: Neon PostgreSQL via `@neondatabase/serverless`
- **ORM**: Drizzle ORM with `drizzle-orm` and `drizzle-kit`
- **Web Framework**: Express.js
- **Real-time**: WebSocket support with `ws` (not yet implemented)

## Conventions
- Use ES modules (`import`/`export`) throughout
- Database URL from `DATABASE_URL` env var
- Port 8000 for local development
- Follow Node.js best practices for async/await with database operations