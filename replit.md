# TapEarn - Gamified Earning Platform

## Overview

TapEarn is a gamified earning platform where users earn virtual coins by completing tasks, inviting friends through a referral system, and tapping. The application combines fintech clarity with gamification elements to create an engaging user experience. Users can track their earnings, complete various categorized tasks, compete on leaderboards, and request withdrawals through multiple payment methods.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Build System**
- React 18 with TypeScript for type-safe component development
- Vite as the build tool and development server with hot module replacement
- Wouter for lightweight client-side routing (single-page application)
- TailwindCSS for utility-first styling with custom design system

**State Management & Data Fetching**
- TanStack Query (React Query) for server state management, caching, and synchronization
- Custom query client configured with infinite stale time to reduce unnecessary refetches
- Optimistic updates and cache invalidation for real-time UI feedback

**UI Component Library**
- Radix UI primitives for accessible, unstyled component foundations
- shadcn/ui design system with custom theme configuration
- Custom color system supporting light/dark themes via CSS variables
- Component variants using class-variance-authority for consistent styling

**Design System**
- Typography: Inter (body/data) and Poppins (headings/accents) from Google Fonts
- Spacing: Consistent Tailwind units (2, 4, 6, 8, 12)
- Components: Cards, badges, buttons with custom shadow and elevation system
- Responsive grid layouts with mobile-first approach

### Backend Architecture

**Server Framework**
- Express.js for HTTP server and API routing
- Custom middleware for JSON parsing, logging, and request timing
- Session-less architecture with single-user simulation for demo purposes

**API Design**
- RESTful endpoints organized by resource type (/api/user, /api/tasks, etc.)
- Mutation endpoints for actions (POST /api/tap, POST /api/tasks/:id/complete)
- Consistent JSON response format with error handling

**Business Logic**
- In-memory storage implementation (IStorage interface) for data persistence
- Referral system with automatic bonus attribution (500 coins per referral)
- Daily tap limits (500 taps/day) with date-based reset logic
- Task completion tracking to prevent duplicate rewards
- Withdrawal request system with method-specific minimum thresholds

### Data Storage

**Database Configuration**
- PostgreSQL as the primary database (configured via Drizzle)
- Drizzle ORM for type-safe database queries and schema management
- Schema-first approach with migrations stored in /migrations directory

**Data Models**
- **Users**: Balance, earnings, referral codes, tap counts, task completion stats
- **Tasks**: Categorized activities (video, survey, download, social, signup) with rewards
- **Completed Tasks**: Junction table tracking user-task completion with timestamps
- **Referrals**: Tracks referrer-referred relationships with earnings and status
- **Transactions**: Comprehensive activity log (task, referral, tap, bonus, withdrawal)
- **Withdrawals**: Payment requests with method (PayPal, bank, gift card) and status

**Schema Design Rationale**
- UUID primary keys for distributed-friendly identifiers
- Text fields for dates (ISO strings) for simplicity in demo environment
- Integer amounts (representing coins) to avoid floating-point precision issues
- Status fields for tracking workflow states (active, pending, completed)

### Authentication & Authorization

**Current Implementation**
- Single-user simulation mode for demo purposes
- Auto-creation of user on first request with random username
- No password authentication or session management
- User ID stored in memory and reused across requests

**Future Considerations**
- Passport.js integration prepared (imported but not actively used)
- Session store configured with connect-pg-simple for PostgreSQL-backed sessions
- Ready for multi-user authentication when scaling beyond demo

### External Dependencies

**Payment Processing**
- Withdrawal methods: PayPal, bank transfer, gift card
- No active payment gateway integration (simulated for demo)
- Minimum withdrawal thresholds enforced per method

**Social Sharing**
- WhatsApp, Twitter, Facebook sharing integrations via URL schemes
- Client-side share functionality without server dependencies

**Development Tools**
- Replit-specific plugins for runtime error overlay and development banners
- ESBuild for server-side bundling with selective dependency inclusion
- Drizzle Kit for database migrations and schema management

**Third-Party Libraries**
- React Icons for social media icons
- Lucide React for UI icons
- date-fns for date manipulation
- Zod for runtime validation and schema generation
- react-hook-form with resolvers for form state management