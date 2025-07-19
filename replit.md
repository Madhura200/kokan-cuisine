# Kokan Restaurant Website

## Overview

This is a full-stack restaurant website for Kokan Restaurant, featuring a modern React frontend with a Node.js/Express backend. The application allows customers to view the restaurant's information, make reservations, and subscribe to a newsletter. It showcases authentic Kokan coastal cuisine with a beautiful, responsive design.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with custom Kokan Restaurant branding
- **UI Components**: Radix UI primitives via shadcn/ui component library
- **State Management**: TanStack Query (React Query) for server state
- **Routing**: Wouter for client-side routing
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **API**: RESTful endpoints for reservations and newsletter subscriptions
- **Session Management**: Built-in support with connect-pg-simple

### Project Structure
- `client/` - React frontend application
- `server/` - Express.js backend application
- `shared/` - Shared TypeScript types and database schema
- `migrations/` - Database migration files

## Key Components

### Frontend Components
- **Header**: Navigation with sticky behavior and mobile menu
- **HeroSection**: Landing section with call-to-action buttons
- **AboutSection**: Restaurant story and experience highlights
- **MenuHighlight**: Featured dishes showcase
- **ContactSection**: Reservation form and contact information
- **Footer**: Newsletter subscription and restaurant details

### Backend Services
- **Storage Layer**: Abstract interface with in-memory implementation for development
- **Reservation Service**: Handles table booking requests
- **Newsletter Service**: Manages email subscriptions
- **Validation**: Zod schema validation for all API inputs

### Database Schema
- **users**: User accounts (id, username, password)
- **reservations**: Table bookings (name, phone, email, date, time, guests, notes, status)
- **newsletter**: Email subscriptions (email, subscription date)

## Data Flow

1. **Frontend to Backend**: API requests using fetch with JSON payloads
2. **Validation**: Zod schemas validate all incoming data
3. **Storage**: Currently uses in-memory storage, designed for easy database migration
4. **Response**: Structured JSON responses with success/error status
5. **State Management**: TanStack Query handles caching and synchronization

## External Dependencies

### Frontend Dependencies
- **UI Framework**: React with TypeScript support
- **Styling**: Tailwind CSS with PostCSS processing
- **Components**: Extensive Radix UI component library
- **State**: TanStack Query for server state management
- **Utilities**: clsx, class-variance-authority for styling utilities
- **Icons**: Lucide React for consistent iconography

### Backend Dependencies
- **Database**: Drizzle ORM with PostgreSQL dialect
- **Database Client**: @neondatabase/serverless for Neon integration
- **Validation**: Zod for runtime type checking
- **Session**: connect-pg-simple for PostgreSQL session storage

### Development Tools
- **Build**: Vite with React plugin and error overlay
- **TypeScript**: Full type safety across frontend and backend
- **Database Tools**: Drizzle Kit for migrations and schema management

## Deployment Strategy

### Development
- Vite dev server for frontend with HMR
- tsx for running TypeScript backend in development
- Shared TypeScript configuration for consistent types
- Environment-based configuration for database connections

### Production Build
- Vite builds optimized React bundle to `dist/public`
- esbuild compiles Express server to `dist/index.js`
- Static file serving from Express for production deployment
- Single deployment artifact containing both frontend and backend

### Database Strategy
- Drizzle migrations for schema versioning
- Environment variable configuration for database connections
- PostgreSQL dialect with Neon serverless database
- Ready for production PostgreSQL deployment

### Hosting Considerations
- Express server serves both API routes and static frontend
- Single port deployment suitable for platforms like Railway, Render, or Heroku
- Environment variables for database and session configuration
- Health check endpoints available through Express routes

## Key Features

1. **Responsive Design**: Mobile-first approach with Tailwind CSS
2. **Form Validation**: Client and server-side validation using Zod
3. **Real-time Feedback**: Toast notifications for user actions
4. **SEO Ready**: Semantic HTML structure and meta tags
5. **Accessibility**: ARIA labels and keyboard navigation support
6. **Performance**: Optimized images and lazy loading
7. **Type Safety**: End-to-end TypeScript coverage
8. **Error Handling**: Comprehensive error boundaries and API error handling