# SupplyChain Pro - Inventory Management System

## Overview

SupplyChain Pro is a full-stack inventory management and supply chain tracking application. The system enables businesses to monitor inventory levels, manage suppliers, track purchase orders, and receive automated alerts for critical stock situations. Built with a modern tech stack, it provides real-time visibility into inventory operations through an intuitive dashboard interface.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Routing**
- React with TypeScript for type-safe component development
- Wouter for lightweight client-side routing
- Component-based architecture with page-level route components

**UI Component System**
- Shadcn/ui component library (New York style variant)
- Radix UI primitives for accessible, unstyled components
- Tailwind CSS for utility-first styling with custom design tokens
- CSS variables for theming and consistent design system

**State Management**
- TanStack Query (React Query) for server state management
- Custom hooks for UI state (mobile detection, toast notifications)
- Form state managed via React Hook Form with Zod validation

**Key Design Patterns**
- Co-located component structure (UI components in `client/src/components/ui`)
- Feature-based organization (dashboard, inventory, suppliers, etc.)
- Shared schema definitions between client and server for type consistency
- Responsive design with mobile-first breakpoints

### Backend Architecture

**Server Framework**
- Express.js with TypeScript for RESTful API
- Custom middleware for request logging and JSON parsing
- Raw body preservation for webhook handling capabilities

**API Structure**
- RESTful endpoints organized by resource type
- Standardized CRUD operations for inventory, suppliers, orders, and alerts
- Dashboard analytics endpoint for aggregated statistics
- Search functionality for inventory items

**Development & Production**
- Vite middleware integration for HMR in development
- Static file serving for production builds
- Separate build process for client and server bundles

### Data Storage

**Database**
- PostgreSQL as the primary database (via Neon serverless)
- Drizzle ORM for type-safe database queries and migrations
- Schema-first approach with migrations stored in `/migrations`

**Schema Design**
- `inventoryItems`: Core product tracking with SKU, quantity, location, status
- `suppliers`: Vendor management with ratings and contact information
- `purchaseOrders`: Order tracking with status workflow (pending → in_transit → delivered)
- `orderItems`: Line items linking orders to inventory
- `alerts`: Notification system for low stock and critical events

**Data Validation**
- Drizzle-Zod integration for runtime schema validation
- Shared TypeScript types derived from database schema
- Insert schemas for API request validation

### External Dependencies

**UI & Component Libraries**
- @radix-ui/* - Accessible component primitives (dialogs, dropdowns, tooltips, etc.)
- recharts - Data visualization for dashboard charts
- embla-carousel-react - Carousel functionality
- date-fns - Date manipulation and formatting
- lucide-react - Icon system

**Database & ORM**
- @neondatabase/serverless - Serverless PostgreSQL connection
- drizzle-orm - Type-safe ORM
- drizzle-kit - Migration tooling
- connect-pg-simple - PostgreSQL session store

**Form & Validation**
- react-hook-form - Form state management
- @hookform/resolvers - Integration layer for validation
- zod - Schema validation
- drizzle-zod - Database schema to Zod validation

**Development Tools**
- vite - Build tool and dev server
- tsx - TypeScript execution for development
- esbuild - Production server bundling
- @replit/* plugins - Replit-specific development tools

**Styling**
- tailwindcss - Utility-first CSS framework
- autoprefixer - CSS vendor prefixing
- class-variance-authority - Component variant management
- tailwind-merge - Utility class merging
