# Friute Cap - E-commerce Cap Store

## Overview
This is a modern e-commerce website for selling custom caps and headwear. The project features a beautiful streetwear-inspired design with product showcases, collections, and promotional sections.

**Last Updated:** October 14, 2025

## Project Architecture

### Tech Stack
- **Frontend:** React 18 + TypeScript + Vite
- **UI Framework:** Tailwind CSS + Radix UI Components
- **Backend:** Express.js + TypeScript
- **Database:** PostgreSQL with Drizzle ORM
- **Authentication:** Passport.js (Local Strategy)
- **State Management:** TanStack React Query

### Project Structure
```
├── client/               # React frontend
│   ├── src/
│   │   ├── components/  # UI components
│   │   ├── pages/       # Page components
│   │   ├── hooks/       # Custom React hooks
│   │   └── lib/         # Utilities
│   └── index.html       # Entry HTML
├── server/              # Express backend
│   ├── index.ts        # Server entry point
│   ├── routes.ts       # API routes
│   ├── storage.ts      # Database operations
│   └── vite.ts         # Vite dev server setup
├── shared/             
│   └── schema.ts       # Database schema (Drizzle)
└── attached_assets/    # Stock images
```

### Key Features
- Responsive design with mobile-first approach
- Hero carousel/slider with promotional content
- Product collections and categories
- Flash sale sections with countdown timers
- Shopping cart and wishlist functionality
- User authentication system
- Modern streetwear aesthetic
- **AI-Powered Cap Designer** - Custom cap design generation using OpenAI's DALL-E 3
  - Text-to-image cap design generation
  - Multiple cap style options (baseball, trucker, snapback, bucket, dad hat)
  - Download generated designs
  - Example prompts for inspiration
  - Auto-save designs to database
- **Design Preview & Management** - View and manage all AI-generated designs
  - Gallery view of all saved designs
  - Design details preview with full image
  - **Edit Cap** - Re-open designs in AI designer with pre-filled settings
  - **Order This Cap** - Order custom caps (coming soon)
  - Download and delete functionality
  - Sorted by newest first

## Development Setup

### Environment Variables
The following secrets are automatically configured:
- `DATABASE_URL` - PostgreSQL connection string
- `PGHOST`, `PGPORT`, `PGUSER`, `PGPASSWORD`, `PGDATABASE` - PostgreSQL credentials

### Running the Project
The project uses a single workflow that serves both frontend and backend:

```bash
npm run dev    # Start development server (port 5000)
npm run build  # Build for production
npm run start  # Start production server
```

### Database Management
```bash
npm run db:push        # Push schema changes to database
npm run db:push --force # Force push (use if data-loss warning)
```

**Important:** Never manually write SQL migrations. Always use `npm run db:push` to sync schema changes.

### Replit Configuration
- **Port:** 5000 (both frontend and backend)
- **Host:** 0.0.0.0 (configured for Replit proxy)
- **Vite Config:** Already configured with `allowedHosts: true` for Replit's iframe proxy
- **Deployment:** Autoscale deployment configured

## Design Guidelines
See `design_guidelines.md` for detailed design specifications including:
- Color palette (light and dark modes)
- Typography system
- Component library
- Layout principles
- Interaction patterns

## Database Schema

### Current Tables
- **users** - User authentication and profiles
  - id (varchar, UUID primary key)
  - username (text, unique)
  - password (text, hashed)
- **designs** - AI-generated cap designs
  - id (serial primary key)
  - imageUrl (text, URL to generated image)
  - prompt (text, design description)
  - capStyle (text, cap type)
  - createdAt (timestamp, auto-generated)

### Adding New Models
1. Add table definition to `shared/schema.ts`
2. Update `server/storage.ts` with new operations
3. Run `npm run db:push` to apply changes

## API Endpoints

### AI Design Generation
- `POST /api/ai/generate-cap-design` - Generate custom cap designs using AI
  - Request body: `{ prompt: string, capStyle: string }`
  - Response: `{ imageUrl: string, prompt: string }`
  - Rate limit: 5 requests per minute per IP

### Design Management
- `GET /api/designs` - Get all saved designs (sorted by newest first)
- `GET /api/designs/:id` - Get a specific design by ID
- `POST /api/designs` - Save a new design
  - Request body: `{ imageUrl: string, prompt: string, capStyle: string }`
- `DELETE /api/designs/:id` - Delete a design by ID

## Current Status
✅ Project successfully set up in Replit environment
✅ Database created and schema pushed (users + designs tables)
✅ Frontend and backend running on port 5000
✅ Vite HMR (Hot Module Replacement) working
✅ Deployment configuration complete
✅ All dependencies installed
✅ OpenAI integration configured for AI cap designer
✅ AI Cap Designer page fully functional
✅ Design Preview & Management page fully functional
✅ Database storage using Drizzle ORM with PostgreSQL

## Notes
- The server uses middleware mode with Vite in development
- In production, it serves pre-built static files from `dist/public`
- All API routes are prefixed with `/api`
- Session management uses PostgreSQL store (connect-pg-simple)
