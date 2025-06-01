# Technology Stack Configuration

## Core Framework
- **Next.js 14**: App Router with TypeScript
- **React 18**: Functional components with hooks
- **TypeScript**: Strict mode enabled

## Styling & UI
- **Tailwind CSS**: Utility-first CSS framework
- **Shadcn/ui**: Component library built on Radix UI
- **Lucide React**: Icon library
- **Class Variance Authority**: Component variant handling

## Database & Backend
- **Supabase**: PostgreSQL database with real-time features
- **Supabase Auth**: Authentication and user management
- **Row Level Security**: Enabled for all tables

## Content Management
- **MDX**: For blog posts with React component support
- **Gray Matter**: Frontmatter parsing
- **Reading Time**: Automatic reading time calculation

## Search & Utilities
- **Fuse.js**: Client-side fuzzy search
- **Date-fns**: Date manipulation library
- **Clsx**: Conditional className utility

## Development Tools
- **ESLint**: Code linting with Next.js config
- **Prettier**: Code formatting
- **TypeScript**: Type checking

## Key Libraries Usage
- Use `@supabase/supabase-js` for database operations
- Use `@supabase/auth-helpers-nextjs` for Next.js authentication
- Use `lucide-react` for all icons
- Use `date-fns` for date formatting
- Use `clsx` for conditional CSS classes
- Always import components from `@/components/ui/` for Shadcn components