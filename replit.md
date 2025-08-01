# FinanceFlow Investment Management System

## Overview

This is a full-stack investment management system built with React, Express.js, and TypeScript. The application provides a comprehensive dashboard for managing investors, tracking investment portfolios, and analyzing financial metrics in Indian Rupees (INR). It features a modern, responsive UI built with shadcn/ui components and uses Drizzle ORM for database operations.

## User Preferences

Preferred communication style: Simple, everyday language.
Currency: Indian Rupees (INR) - all amounts displayed in ₹ with proper formatting (Cr for Crores, L for Lakhs).

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Style**: RESTful API design
- **Development Server**: Custom Vite integration for full-stack development
- **Request Logging**: Custom middleware for API request/response logging

### Database Architecture
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Database**: Configured for Neon Database (PostgreSQL)
- **Schema Management**: Type-safe schema definitions with automatic TypeScript generation
- **Migrations**: Drizzle Kit for database migrations
- **Validation**: Zod schemas for runtime type validation

## Key Components

### Data Models
1. **Investors**: Core entity storing investor information including contact details, investment amounts, categories, and status
2. **Company Metrics**: Annual performance data including AUM (Assets Under Management), CAGR, and active investment counts
3. **Investment Categories**: Portfolio allocation breakdown by investment type (Equity, Debt, Real Estate, etc.)

### Frontend Components
- **Dashboard**: Main overview with metrics cards, charts, and recent investor data
- **Investor Management**: CRUD operations for investor records with data tables and forms
- **Admin Panel**: Administrative functions and system management
- **Charts & Visualizations**: Pie charts for allocation and line charts for performance metrics

### API Endpoints
- `GET/POST /api/investors` - Investor CRUD operations
- `GET /api/dashboard/summary` - Dashboard summary data
- `GET /api/metrics` - Company performance metrics
- Investment category management endpoints

## Data Flow

1. **Client Requests**: React components use TanStack Query to fetch data
2. **API Layer**: Express.js routes handle HTTP requests and validate input
3. **Business Logic**: Service layer processes business rules and data transformation
4. **Data Storage**: Currently uses in-memory storage with interface for easy database integration
5. **Response Flow**: JSON responses flow back through the query client to update React components

## External Dependencies

### UI & Styling
- **Radix UI**: Primitive components for accessibility and behavior
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide React**: Icon library
- **Recharts**: Chart library for data visualization

### Data & Validation
- **Drizzle ORM**: Type-safe database operations
- **Zod**: Runtime schema validation
- **React Hook Form**: Form state management and validation
- **TanStack Query**: Server state management and caching

### Development Tools
- **TypeScript**: Static typing across the entire stack
- **Vite**: Fast development server and build tool
- **ESBuild**: Fast JavaScript bundler for production builds

## Deployment Strategy

### Development
- Vite dev server with HMR (Hot Module Replacement)
- Concurrent frontend and backend development
- Custom Vite integration for serving both React app and API

### Production Build
- **Frontend**: Vite builds optimized React bundle to `dist/public`
- **Backend**: ESBuild bundles Express server to `dist/index.js`
- **Database**: Drizzle migrations manage schema changes
- **Environment**: Configured for deployment on platforms supporting Node.js

### Environment Configuration
- Database connection via `DATABASE_URL` environment variable
- Separate development and production configurations
- TypeScript path mapping for clean imports
- CSS variables for consistent theming across environments

The application is designed as a monorepo with shared TypeScript types between frontend and backend, ensuring type safety across the entire stack. The current implementation uses in-memory storage but is architected to easily switch to a PostgreSQL database using the existing Drizzle ORM setup.