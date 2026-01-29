# Munster CleanRooms

## Overview

A marketing website for Munster CleanRooms, a specialized cleanroom construction labour company providing elite installers for pharmaceutical wall and ceiling systems across Ireland. The application features a contact form that stores inquiries in a PostgreSQL database.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript, using Vite as the build tool
- **Routing**: Wouter for client-side routing (lightweight alternative to React Router)
- **Styling**: Tailwind CSS with shadcn/ui component library (New York style variant)
- **State Management**: TanStack React Query for server state and data fetching
- **Forms**: React Hook Form with Zod validation via @hookform/resolvers
- **Animations**: Framer Motion for entry animations and scroll reveals
- **Path Aliases**: `@/` maps to `client/src/`, `@shared/` maps to `shared/`

### Backend Architecture
- **Framework**: Express.js 5.x running on Node.js
- **Language**: TypeScript with ESM modules
- **Build Process**: Custom build script using esbuild for server and Vite for client
- **API Pattern**: REST endpoints defined in `shared/routes.ts` with Zod schemas for type-safe request/response validation

### Data Storage
- **Database**: PostgreSQL via node-postgres (pg) driver
- **ORM**: Drizzle ORM with drizzle-zod for schema-to-validation integration
- **Schema Location**: `shared/schema.ts` contains all database table definitions
- **Migrations**: Drizzle Kit with `db:push` command for schema synchronization

### API Structure
- APIs are defined in `shared/routes.ts` with method, path, input schema, and response schemas
- Current endpoint: `POST /api/contact` for contact form submissions
- Error responses follow consistent schema with message and optional field properties

### Project Structure